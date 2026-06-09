# CContext::Invoke(IDispatch *,long,ushort,tagDISPPARAMS *,tagVARIANT *)

- ea: `0x18005afb8`
- end: `0x18005b18e`
- name: `?Invoke@CContext@@QEAA_NPEAUIDispatch@@JGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `470`
- prototype: `bool __fastcall(CContext *__hidden this, struct IDispatch *, int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001fb90`

## callees

- `0x18005afb8`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005b11b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b12b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b13b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b11b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b12b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b13b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18005b0eb`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18005b0eb`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18005b05f`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18005b05f`

## pseudocode

```c
bool __fastcall CContext::Invoke(
        CContext *this,
        struct IDispatch *a2,
        unsigned int a3,
        __int64 a4,
        struct tagDISPPARAMS *a5,
        struct tagVARIANT *a6)
{
  int v9; // ebx
  __int16 v11; // [rsp+20h] [rbp-49h]
  IErrorInfo *perrinfo; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v13[8]; // [rsp+60h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-1h]
  BSTR v15; // [rsp+70h] [rbp+7h]
  BSTR v16; // [rsp+78h] [rbp+Fh]
  unsigned int v17; // [rsp+80h] [rbp+17h]
  int v18; // [rsp+98h] [rbp+2Fh]
  ICreateErrorInfo *pperrinfo; // [rsp+C8h] [rbp+5Fh] BYREF

  memset_0(v13, 0, 0x40u);
  v11 = 2;
  v9 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, __int64, __int16, struct tagDISPPARAMS *, struct tagVARIANT *, _BYTE *, _QWORD))a2->lpVtbl->Invoke)(
         a2,
         a3,
         &GUID_NULL,
         2048,
         v11,
         a5,
         a6,
         v13,
         0);
  if ( v9 == -2147352567 )
  {
    v9 = v18;
    *((_DWORD *)this + 10) = v18;
    pperrinfo = 0;
    perrinfo = 0;
    if ( CreateErrorInfo(&pperrinfo) || !pperrinfo )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(off_18012A220[0], 660489, L"<CContext::Invoke|ADO|ERR>  line %d\n", 645);
    }
    else
    {
      ((void (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetSource)(pperrinfo, bstrString);
      ((void (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v15);
      ((void (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, v16);
      ((void (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(pperrinfo, v17);
      ((void (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
        pperrinfo,
        &IID_IErrorInfo,
        &perrinfo);
      SetErrorInfo(0, perrinfo);
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
      SysFreeString(bstrString);
      SysFreeString(v15);
      SysFreeString(v16);
    }
  }
  return v9 < 0;
}

```

## disassembly

```asm
0x18005afb8  mov     [rsp-8+arg_0], rbx
0x18005afbd  mov     [rsp-8+arg_10], rsi
0x18005afc2  push    rbp
0x18005afc3  push    rdi
0x18005afc4  push    r15
0x18005afc6  lea     rbp, [rsp-37h]
0x18005afcb  sub     rsp, 0A0h
0x18005afd2  mov     rdi, rdx
0x18005afd5  mov     ebx, r8d
0x18005afd8  xor     edx, edx; Val
0x18005afda  mov     rsi, rcx
0x18005afdd  lea     rcx, [rbp+47h+var_50]; void *
0x18005afe1  lea     r8d, [rdx+40h]; Size
0x18005afe5  call    memset_0
0x18005afea  mov     rax, [rdi]
0x18005afed  lea     rcx, [rbp+47h+var_50]
0x18005aff1  mov     [rsp+0B0h+var_70], 0
0x18005affa  lea     r8, GUID_NULL
0x18005b001  mov     [rsp+0B0h+var_78], rcx
0x18005b006  mov     r15d, 2
0x18005b00c  mov     rcx, [rbp+47h+arg_28]
0x18005b010  mov     r9d, 800h
0x18005b016  mov     rax, [rax+30h]
0x18005b01a  mov     edx, ebx
0x18005b01c  mov     [rsp+0B0h+var_80], rcx
0x18005b021  mov     rcx, [rbp+47h+arg_20]
0x18005b025  mov     [rsp+0B0h+var_88], rcx
0x18005b02a  mov     rcx, rdi
0x18005b02d  mov     [rsp+0B0h+var_90], r15w
0x18005b033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b038  mov     ebx, eax
0x18005b03a  cmp     eax, 80020009h
0x18005b03f  jnz     loc_18005B170
0x18005b045  mov     ebx, [rbp+47h+var_18]
0x18005b048  lea     rcx, [rbp+47h+pperrinfo]; pperrinfo
0x18005b04c  mov     [rsi+28h], ebx
0x18005b04f  mov     [rbp+47h+pperrinfo], 0
0x18005b057  mov     [rbp+47h+perrinfo], 0
0x18005b05f  call    cs:__imp_CreateErrorInfo
0x18005b066  nop     dword ptr [rax+rax+00h]
0x18005b06b  test    eax, eax
0x18005b06d  jnz     loc_18005B149
0x18005b073  mov     rcx, [rbp+47h+pperrinfo]
0x18005b077  test    rcx, rcx
0x18005b07a  jz      loc_18005B149
0x18005b080  mov     rax, [rcx]
0x18005b083  mov     rdx, [rbp+47h+bstrString]
0x18005b087  mov     rax, [rax+20h]
0x18005b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b090  mov     rcx, [rbp+47h+pperrinfo]
0x18005b094  mov     rdx, [rbp+47h+var_40]
0x18005b098  mov     rax, [rcx]
0x18005b09b  mov     rax, [rax+28h]
0x18005b09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0a4  mov     rcx, [rbp+47h+pperrinfo]
0x18005b0a8  mov     rdx, [rbp+47h+var_38]
0x18005b0ac  mov     rax, [rcx]
0x18005b0af  mov     rax, [rax+30h]
0x18005b0b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0b8  mov     rcx, [rbp+47h+pperrinfo]
0x18005b0bc  mov     edx, [rbp+47h+var_30]
0x18005b0bf  mov     rax, [rcx]
0x18005b0c2  mov     rax, [rax+38h]
0x18005b0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0cb  mov     rcx, [rbp+47h+pperrinfo]
0x18005b0cf  lea     r8, [rbp+47h+perrinfo]
0x18005b0d3  lea     rdx, IID_IErrorInfo
0x18005b0da  mov     rax, [rcx]
0x18005b0dd  mov     rax, [rax]
0x18005b0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0e5  mov     rdx, [rbp+47h+perrinfo]; perrinfo
0x18005b0e9  xor     ecx, ecx; dwReserved
0x18005b0eb  call    cs:__imp_SetErrorInfo
0x18005b0f2  nop     dword ptr [rax+rax+00h]
0x18005b0f7  mov     rcx, [rbp+47h+perrinfo]
0x18005b0fb  mov     rax, [rcx]
0x18005b0fe  mov     rax, [rax+10h]
0x18005b102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b107  mov     rcx, [rbp+47h+pperrinfo]
0x18005b10b  mov     rax, [rcx]
0x18005b10e  mov     rax, [rax+10h]
0x18005b112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b117  mov     rcx, [rbp+47h+bstrString]; bstrString
0x18005b11b  call    cs:__imp_SysFreeString
0x18005b122  nop     dword ptr [rax+rax+00h]
0x18005b127  mov     rcx, [rbp+47h+var_40]; bstrString
0x18005b12b  call    cs:__imp_SysFreeString
0x18005b132  nop     dword ptr [rax+rax+00h]
0x18005b137  mov     rcx, [rbp+47h+var_38]; bstrString
0x18005b13b  call    cs:__imp_SysFreeString
0x18005b142  nop     dword ptr [rax+rax+00h]
0x18005b147  jmp     short loc_18005B170
0x18005b149  test    byte ptr cs:_bidGblFlags, r15b
0x18005b150  jz      short loc_18005B170
0x18005b152  mov     rcx, cs:off_18012A220; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005b159  lea     r8, aCcontextInvoke; "<CContext::Invoke|ADO|ERR>  line %d\n"
0x18005b160  mov     r9d, 285h
0x18005b166  mov     edx, 0A1409h
0x18005b16b  call    _bidTraceW
0x18005b170  shr     ebx, 1Fh
0x18005b173  lea     r11, [rsp+0B0h+var_10]
0x18005b17b  mov     rsi, [r11+30h]
0x18005b17f  mov     al, bl
0x18005b181  mov     rbx, [r11+20h]
0x18005b185  mov     rsp, r11
0x18005b188  pop     r15
0x18005b18a  pop     rdi
0x18005b18b  pop     rbp
0x18005b18c  retn
```
