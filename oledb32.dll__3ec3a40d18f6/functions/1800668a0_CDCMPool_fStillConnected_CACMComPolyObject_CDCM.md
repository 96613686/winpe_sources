# CDCMPool::fStillConnected(CACMComPolyObject<CDCM> *)

- ea: `0x1800668a0`
- end: `0x180066a0a`
- name: `?fStillConnected@CDCMPool@@QEAA_NPEAV?$CACMComPolyObject@VCDCM@@@@@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021df0`

## callees

- `0x180022bf8`
- `0x1800668a0`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `msvcrt!time` at `0x1800668ce`
- `msvcrt!time` at `0x1800668ce`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800669a2`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800669a2`
- `ole32!CoTaskMemFree` at `0x1800669d8`
- `ole32!CoTaskMemFree` at `0x1800669e2`
- `ole32!CoTaskMemFree` at `0x1800669d8`
- `ole32!CoTaskMemFree` at `0x1800669e2`

## pseudocode

```c
char __fastcall CDCMPool::fStillConnected(__int64 a1, __int64 a2)
{
  time_t v4; // rax
  __int64 v5; // rcx
  bool v7; // bl
  __int64 Provider; // rax
  __int64 v9; // rdi
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  int v11; // [rsp+38h] [rbp-38h] BYREF
  int v12; // [rsp+3Ch] [rbp-34h] BYREF
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp-30h] BYREF
  int *v14; // [rsp+48h] [rbp-28h] BYREF
  int v15; // [rsp+50h] [rbp-20h]
  GUID v16; // [rsp+54h] [rbp-1Ch]

  if ( !g_fAlwaysTestConn )
  {
    v4 = time(0);
    v5 = v4 - *(_QWORD *)(a2 + 536);
    *(_QWORD *)(a2 + 536) = v4;
    if ( v5 <= 2 )
      return 1;
  }
  v7 = 1;
  pv = 0;
  v12 = 1;
  v16 = DBPROPSET_DATASOURCEINFO;
  v11 = 244;
  v14 = &v11;
  v15 = 1;
  if ( *(_DWORD *)(a1 + 152) != 1 )
  {
    Provider = GetProviderPointer<CDCM>(a2 + 24, &IID_IDBProperties);
    v9 = Provider;
    if ( Provider )
    {
      if ( (*(int (__fastcall **)(__int64, __int64, int **, int *, LPVOID *))(*(_QWORD *)Provider + 24LL))(
             Provider,
             1,
             &v14,
             &v12,
             &pv) < 0 )
      {
        if ( pv && *(_DWORD *)(*(_QWORD *)pv + 8LL) == 1 )
          *(_DWORD *)(a1 + 152) = 1;
        pperrinfo = 0;
        GetErrorInfo(0, &pperrinfo);
        if ( pperrinfo )
          ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
      }
      else
      {
        v7 = *(_DWORD *)(*(_QWORD *)pv + 56LL) != 2;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      if ( pv )
      {
        CoTaskMemFree(*(LPVOID *)pv);
        CoTaskMemFree(pv);
      }
    }
    else
    {
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800668a0  mov     [rsp-18h+arg_10], rbx
0x1800668a5  push    rbp
0x1800668a6  push    rsi
0x1800668a7  push    rdi
0x1800668a8  mov     rbp, rsp
0x1800668ab  sub     rsp, 70h
0x1800668af  mov     rax, cs:__security_cookie
0x1800668b6  xor     rax, rsp
0x1800668b9  mov     [rbp+var_8], rax
0x1800668bd  cmp     cs:?g_fAlwaysTestConn@@3_NA, 0; bool g_fAlwaysTestConn
0x1800668c4  mov     rdi, rdx
0x1800668c7  mov     rsi, rcx
0x1800668ca  jnz     short loc_1800668F5
0x1800668cc  xor     ecx, ecx; Time
0x1800668ce  call    cs:__imp_time
0x1800668d4  mov     rcx, rax
0x1800668d7  sub     rcx, [rdi+218h]
0x1800668de  mov     [rdi+218h], rax
0x1800668e5  cmp     rcx, 2
0x1800668e9  jg      short loc_1800668F5
0x1800668eb  mov     eax, 1
0x1800668f0  jmp     loc_1800669EE
0x1800668f5  movups  xmm0, xmmword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x1800668fc  mov     ebx, 1
0x180066901  mov     [rbp+pv], 0
0x180066909  lea     rax, [rbp+var_38]
0x18006690d  mov     [rbp+var_34], ebx
0x180066910  movdqu  [rbp+var_1C], xmm0
0x180066915  mov     [rbp+var_38], 0F4h
0x18006691c  mov     [rbp+var_28], rax
0x180066920  mov     [rbp+var_20], ebx
0x180066923  cmp     [rsi+98h], ebx
0x180066929  jz      loc_1800669EC
0x18006692f  lea     rcx, [rdi+18h]
0x180066933  lea     rdx, IID_IDBProperties
0x18006693a  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x18006693f  mov     rdi, rax
0x180066942  test    rax, rax
0x180066945  jz      loc_1800669EA
0x18006694b  mov     rcx, [rax]
0x18006694e  lea     r9, [rbp+var_34]
0x180066952  lea     r8, [rbp+var_28]
0x180066956  mov     edx, ebx
0x180066958  mov     rax, [rcx+18h]
0x18006695c  lea     rcx, [rbp+pv]
0x180066960  mov     [rsp+70h+var_50], rcx
0x180066965  mov     rcx, rdi
0x180066968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006696d  test    eax, eax
0x18006696f  mov     rax, [rbp+pv]
0x180066973  js      short loc_180066981
0x180066975  mov     rcx, [rax]
0x180066978  cmp     dword ptr [rcx+38h], 2
0x18006697c  setnz   bl
0x18006697f  jmp     short loc_1800669BD
0x180066981  test    rax, rax
0x180066984  jz      short loc_180066994
0x180066986  mov     rax, [rax]
0x180066989  cmp     [rax+8], ebx
0x18006698c  jnz     short loc_180066994
0x18006698e  mov     [rsi+98h], ebx
0x180066994  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180066998  mov     [rbp+pperrinfo], 0
0x1800669a0  xor     ecx, ecx; dwReserved
0x1800669a2  call    cs:__imp_GetErrorInfo
0x1800669a8  mov     rcx, [rbp+pperrinfo]
0x1800669ac  test    rcx, rcx
0x1800669af  jz      short loc_1800669BD
0x1800669b1  mov     rax, [rcx]
0x1800669b4  mov     rax, [rax+10h]
0x1800669b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669bd  mov     rax, [rdi]
0x1800669c0  mov     rcx, rdi
0x1800669c3  mov     rax, [rax+10h]
0x1800669c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669cc  mov     rcx, [rbp+pv]
0x1800669d0  test    rcx, rcx
0x1800669d3  jz      short loc_1800669EC
0x1800669d5  mov     rcx, [rcx]; pv
0x1800669d8  call    cs:__imp_CoTaskMemFree
0x1800669de  mov     rcx, [rbp+pv]; pv
0x1800669e2  call    cs:__imp_CoTaskMemFree
0x1800669e8  jmp     short loc_1800669EC
0x1800669ea  xor     bl, bl
0x1800669ec  mov     al, bl
0x1800669ee  mov     rcx, [rbp+var_8]
0x1800669f2  xor     rcx, rsp; StackCookie
0x1800669f5  call    __security_check_cookie
0x1800669fa  mov     rbx, [rsp+70h+arg_10]
0x180066a02  add     rsp, 70h
0x180066a06  pop     rdi
0x180066a07  pop     rsi
0x180066a08  pop     rbp
0x180066a09  retn
```
