# CDCM::CanIBePooled_ThreadingModel(void)

- ea: `0x180072968`
- end: `0x180072a61`
- name: `?CanIBePooled_ThreadingModel@CDCM@@QEAA_NXZ`
- size: `249`
- prototype: `bool __fastcall(CDCM *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180064720`

## callees

- `0x180022bf8`
- `0x180072968`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180072a0c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180072a0c`
- `ole32!CoTaskMemFree` at `0x180072a2d`
- `ole32!CoTaskMemFree` at `0x180072a37`
- `ole32!CoTaskMemFree` at `0x180072a2d`
- `ole32!CoTaskMemFree` at `0x180072a37`

## pseudocode

```c
bool __fastcall CDCM::CanIBePooled_ThreadingModel(CDCM *this)
{
  bool v1; // bl
  __int64 Provider; // rax
  __int64 v3; // rdi
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  int v6; // [rsp+38h] [rbp-38h] BYREF
  int v7; // [rsp+3Ch] [rbp-34h] BYREF
  int *v8; // [rsp+40h] [rbp-30h] BYREF
  int v9; // [rsp+48h] [rbp-28h]
  GUID v10; // [rsp+4Ch] [rbp-24h]

  v1 = 1;
  pv = 0;
  v7 = 1;
  v6 = 169;
  v10 = DBPROPSET_DATASOURCEINFO;
  v8 = &v6;
  v9 = 1;
  Provider = GetProviderPointer<CDCM>(this, &IID_IDBProperties);
  v3 = Provider;
  if ( !Provider )
    return 0;
  if ( (*(int (__fastcall **)(__int64, __int64, int **, int *, LPVOID *))(*(_QWORD *)Provider + 24LL))(
         Provider,
         1,
         &v8,
         &v7,
         &pv) < 0 )
    SetErrorInfo(0, 0);
  else
    v1 = ((*(_DWORD *)(*(_QWORD *)pv + 56LL) - 2) & 0xFFFFFFFD) != 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( pv )
  {
    CoTaskMemFree(*(LPVOID *)pv);
    CoTaskMemFree(pv);
  }
  return v1;
}

```

## disassembly

```asm
0x180072968  mov     [rsp-8+arg_8], rbx
0x18007296d  mov     [rsp-8+arg_10], rdi
0x180072972  push    rbp
0x180072973  mov     rbp, rsp
0x180072976  sub     rsp, 70h
0x18007297a  mov     rax, cs:__security_cookie
0x180072981  xor     rax, rsp
0x180072984  mov     [rbp+var_10], rax
0x180072988  movups  xmm0, xmmword ptr cs:DBPROPSET_DATASOURCEINFO.Data1
0x18007298f  mov     ebx, 1
0x180072994  mov     [rbp+pv], 0
0x18007299c  lea     rax, [rbp+var_38]
0x1800729a0  mov     [rbp+var_34], ebx
0x1800729a3  lea     rdx, IID_IDBProperties
0x1800729aa  mov     [rbp+var_38], 0A9h
0x1800729b1  movdqu  [rbp+var_24], xmm0
0x1800729b6  mov     [rbp+var_30], rax
0x1800729ba  mov     [rbp+var_28], ebx
0x1800729bd  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x1800729c2  mov     rdi, rax
0x1800729c5  test    rax, rax
0x1800729c8  jz      short loc_180072A3F
0x1800729ca  mov     rcx, [rax]
0x1800729cd  lea     r9, [rbp+var_34]
0x1800729d1  lea     r8, [rbp+var_30]
0x1800729d5  mov     edx, ebx
0x1800729d7  mov     rax, [rcx+18h]
0x1800729db  lea     rcx, [rbp+pv]
0x1800729df  mov     [rsp+70h+var_50], rcx
0x1800729e4  mov     rcx, rdi
0x1800729e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729ec  test    eax, eax
0x1800729ee  js      short loc_180072A08
0x1800729f0  mov     rax, [rbp+pv]
0x1800729f4  mov     rcx, [rax]
0x1800729f7  mov     eax, [rcx+38h]
0x1800729fa  sub     eax, 2
0x1800729fd  test    eax, 0FFFFFFFDh
0x180072a02  jnz     short loc_180072A12
0x180072a04  xor     bl, bl
0x180072a06  jmp     short loc_180072A12
0x180072a08  xor     edx, edx; perrinfo
0x180072a0a  xor     ecx, ecx; dwReserved
0x180072a0c  call    cs:__imp_SetErrorInfo
0x180072a12  mov     rax, [rdi]
0x180072a15  mov     rcx, rdi
0x180072a18  mov     rax, [rax+10h]
0x180072a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a21  mov     rcx, [rbp+pv]
0x180072a25  test    rcx, rcx
0x180072a28  jz      short loc_180072A41
0x180072a2a  mov     rcx, [rcx]; pv
0x180072a2d  call    cs:__imp_CoTaskMemFree
0x180072a33  mov     rcx, [rbp+pv]; pv
0x180072a37  call    cs:__imp_CoTaskMemFree
0x180072a3d  jmp     short loc_180072A41
0x180072a3f  xor     bl, bl
0x180072a41  mov     al, bl
0x180072a43  mov     rcx, [rbp+var_10]
0x180072a47  xor     rcx, rsp; StackCookie
0x180072a4a  call    __security_check_cookie
0x180072a4f  lea     r11, [rsp+70h+var_s0]
0x180072a54  mov     rbx, [r11+18h]
0x180072a58  mov     rdi, [r11+20h]
0x180072a5c  mov     rsp, r11
0x180072a5f  pop     rbp
0x180072a60  retn
```
