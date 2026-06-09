# PostHResult(long,_GUID const *)

- ea: `0x180061814`
- end: `0x180061a32`
- name: `?PostHResult@@YAJJPEBU_GUID@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(int, const struct _GUID *)`
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fef0`
- `0x180021610`
- `0x180026390`
- `0x18002c410`
- `0x1800350e8`
- `0x180035af4`
- `0x1800460a0`
- `0x180046830`
- `0x180047270`
- `0x1800478c0`
- `0x1800484f0`
- `0x1800485a0`
- `0x180048710`
- `0x1800487c0`
- `0x180069750`
- `0x18006a080`
- `0x18006aa90`
- `0x18006bae0`

## callees

- `0x180013870`
- `0x180029560`
- `0x180061814`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180061851`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180061851`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800619bb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800619bb`
- `ole32!CoCreateInstance` at `0x18006187d`
- `ole32!CoCreateInstance` at `0x18006187d`

## pseudocode

```c
__int64 __fastcall PostHResult(unsigned int a1, const struct _GUID *a2)
{
  IErrorInfo *v4; // rcx
  HRESULT Instance; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  __int128 v9; // xmm0
  int v10; // eax
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp-9h] BYREF
  __int64 v13; // [rsp+48h] [rbp-1h] BYREF
  _DWORD v14[2]; // [rsp+50h] [rbp+7h] BYREF
  GUID v15; // [rsp+58h] [rbp+Fh]
  __int128 v16; // [rsp+68h] [rbp+1Fh]
  int v17; // [rsp+78h] [rbp+2Fh]

  pperrinfo = 0;
  v13 = 0;
  GetErrorInfo(0, &pperrinfo);
  v4 = pperrinfo;
  if ( !pperrinfo )
  {
    Instance = CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&pperrinfo);
    v6 = Instance;
    if ( Instance < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(Instance, L"<PostHResult|OLEDB|ERR> ", 0xDDu);
        if ( (bidGblFlags & 2) != 0 )
        {
          v7 = 226313;
LABEL_6:
          bidTraceHR(off_1800C8428[0], v7, L"<PostHResult|Trace|HR> ", v6);
          goto LABEL_17;
        }
      }
      goto LABEL_17;
    }
    v4 = pperrinfo;
  }
  v8 = ((__int64 (__fastcall *)(IErrorInfo *, GUID *, __int64 *))v4->lpVtbl->QueryInterface)(
         v4,
         &IID_IErrorRecords,
         &v13);
  v6 = v8;
  if ( v8 >= 0 )
  {
    v9 = (__int128)*a2;
    v14[0] = a1;
    v15 = CLSID_MSDAINITIALIZE;
    v17 = 0;
    v16 = v9;
    v14[1] = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v13 + 24LL))(
            v13,
            v14,
            0x10000000,
            0,
            0,
            0);
    v6 = v10;
    if ( v10 >= 0 )
    {
      SetErrorInfo(0, pperrinfo);
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v10, L"<PostHResult|OLEDB|ERR> ", 0xF1u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v7 = 246793;
        goto LABEL_6;
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(v8, L"<PostHResult|OLEDB|ERR> ", 0xE3u);
    if ( (bidGblFlags & 2) != 0 )
    {
      v7 = 232457;
      goto LABEL_6;
    }
  }
LABEL_17:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( pperrinfo )
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8428[0], 260105, L"<PostHResult|Trace|HR> ", a1);
  return a1;
}

```

## disassembly

```asm
0x180061814  mov     [rsp-8+arg_10], rbx
0x180061819  push    rbp
0x18006181a  push    rsi
0x18006181b  push    rdi
0x18006181c  lea     rbp, [rsp-47h]
0x180061821  sub     rsp, 90h
0x180061828  mov     rax, cs:__security_cookie
0x18006182f  xor     rax, rsp
0x180061832  mov     [rbp+57h+var_20], rax
0x180061836  mov     rsi, rdx
0x180061839  mov     [rbp+57h+pperrinfo], 0
0x180061841  mov     edi, ecx
0x180061843  mov     [rbp+57h+var_58], 0
0x18006184b  lea     rdx, [rbp+57h+pperrinfo]; pperrinfo
0x18006184f  xor     ecx, ecx; dwReserved
0x180061851  call    cs:__imp_GetErrorInfo
0x180061857  mov     rcx, [rbp+57h+pperrinfo]
0x18006185b  test    rcx, rcx
0x18006185e  jnz     short loc_1800618DB
0x180061860  lea     rax, [rbp+57h+pperrinfo]
0x180061864  xor     edx, edx; pUnkOuter
0x180061866  lea     r8d, [rcx+1]; dwClsContext
0x18006186a  mov     [rsp+0A0h+ppv], rax; ppv
0x18006186f  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x180061876  lea     r9, IID_IErrorInfo; riid
0x18006187d  call    cs:__imp_CoCreateInstance
0x180061883  mov     ebx, eax
0x180061885  test    eax, eax
0x180061887  jns     short loc_1800618D7
0x180061889  test    byte ptr cs:_bidGblFlags, 2
0x180061890  jz      loc_1800619C1
0x180061896  mov     r8d, 0DDh; unsigned int
0x18006189c  lea     rdx, aPosthresultOle; "<PostHResult|OLEDB|ERR> "
0x1800618a3  mov     ecx, eax; int
0x1800618a5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800618aa  test    byte ptr cs:_bidGblFlags, 2
0x1800618b1  jz      loc_1800619C1
0x1800618b7  mov     edx, 37409h
0x1800618bc  mov     rcx, cs:off_1800C8428; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800618c3  lea     r8, aPosthresultTra; "<PostHResult|Trace|HR> "
0x1800618ca  mov     r9d, ebx
0x1800618cd  call    _bidTraceHR
0x1800618d2  jmp     loc_1800619C1
0x1800618d7  mov     rcx, [rbp+57h+pperrinfo]
0x1800618db  mov     rax, [rcx]
0x1800618de  lea     r8, [rbp+57h+var_58]
0x1800618e2  lea     rdx, IID_IErrorRecords
0x1800618e9  mov     rax, [rax]
0x1800618ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618f1  mov     ebx, eax
0x1800618f3  test    eax, eax
0x1800618f5  jns     short loc_18006192C
0x1800618f7  test    byte ptr cs:_bidGblFlags, 2
0x1800618fe  jz      loc_1800619C1
0x180061904  mov     r8d, 0E3h; unsigned int
0x18006190a  lea     rdx, aPosthresultOle; "<PostHResult|OLEDB|ERR> "
0x180061911  mov     ecx, eax; int
0x180061913  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180061918  test    byte ptr cs:_bidGblFlags, 2
0x18006191f  jz      loc_1800619C1
0x180061925  mov     edx, 38C09h
0x18006192a  jmp     short loc_1800618BC
0x18006192c  movups  xmm1, xmmword ptr cs:CLSID_MSDAINITIALIZE.Data1
0x180061933  mov     rcx, [rbp+57h+var_58]
0x180061937  xor     r9d, r9d
0x18006193a  movups  xmm0, xmmword ptr [rsi]
0x18006193d  mov     [rbp+57h+var_50], edi
0x180061940  mov     r8d, 10000000h
0x180061946  movdqu  [rbp+57h+var_48], xmm1
0x18006194b  mov     [rbp+57h+var_28], 0
0x180061952  lea     rdx, [rbp+57h+var_50]
0x180061956  movdqu  [rbp+57h+var_38], xmm0
0x18006195b  mov     [rbp+57h+var_4C], 0
0x180061962  mov     rax, [rcx]
0x180061965  mov     [rsp+0A0h+var_78], 0
0x18006196d  mov     [rsp+0A0h+ppv], 0
0x180061976  mov     rax, [rax+18h]
0x18006197a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006197f  mov     ebx, eax
0x180061981  test    eax, eax
0x180061983  jns     short loc_1800619B5
0x180061985  test    byte ptr cs:_bidGblFlags, 2
0x18006198c  jz      short loc_1800619C1
0x18006198e  mov     r8d, 0F1h; unsigned int
0x180061994  lea     rdx, aPosthresultOle; "<PostHResult|OLEDB|ERR> "
0x18006199b  mov     ecx, eax; int
0x18006199d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800619a2  test    byte ptr cs:_bidGblFlags, 2
0x1800619a9  jz      short loc_1800619C1
0x1800619ab  mov     edx, 3C409h
0x1800619b0  jmp     loc_1800618BC
0x1800619b5  mov     rdx, [rbp+57h+pperrinfo]; perrinfo
0x1800619b9  xor     ecx, ecx; dwReserved
0x1800619bb  call    cs:__imp_SetErrorInfo
0x1800619c1  mov     rcx, [rbp+57h+var_58]
0x1800619c5  test    rcx, rcx
0x1800619c8  jz      short loc_1800619D6
0x1800619ca  mov     rax, [rcx]
0x1800619cd  mov     rax, [rax+10h]
0x1800619d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619d6  mov     rcx, [rbp+57h+pperrinfo]
0x1800619da  test    rcx, rcx
0x1800619dd  jz      short loc_1800619EB
0x1800619df  mov     rax, [rcx]
0x1800619e2  mov     rax, [rax+10h]
0x1800619e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619eb  test    byte ptr cs:_bidGblFlags, 2
0x1800619f2  jz      short loc_180061A11
0x1800619f4  mov     rcx, cs:off_1800C8428; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800619fb  lea     r8, aPosthresultTra; "<PostHResult|Trace|HR> "
0x180061a02  mov     r9d, edi
0x180061a05  mov     edx, 3F809h
0x180061a0a  call    _bidTraceHR
0x180061a0f  mov     edi, eax
0x180061a11  mov     eax, edi
0x180061a13  mov     rcx, [rbp+57h+var_20]
0x180061a17  xor     rcx, rsp; StackCookie
0x180061a1a  call    __security_check_cookie
0x180061a1f  mov     rbx, [rsp+0A0h+arg_10]
0x180061a27  add     rsp, 90h
0x180061a2e  pop     rdi
0x180061a2f  pop     rsi
0x180061a30  pop     rbp
0x180061a31  retn
```
