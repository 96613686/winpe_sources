# GetObjectFromMoniker

- ea: `0x18004d254`
- end: `0x18004d3e4`
- name: `GetObjectFromMoniker`
- size: `400`
- prototype: `HRESULT __fastcall(struct CSession **this, OLECHAR *szUserName, struct VAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004b744`

## callees

- `0x1800309ec`
- `0x18004d254`
- `0x18004d3ec`
- `0x180074f64`
- `0x1800752cc`
- `0x18007558c`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18004d278`
- `OLEAUT32!__imp_SysStringLen` at `0x18004d278`
- `ole32!CreateBindCtx` at `0x18004d2cf`
- `ole32!CreateBindCtx` at `0x18004d2cf`
- `ole32!BindMoniker` at `0x18004d329`
- `ole32!BindMoniker` at `0x18004d329`
- `ole32!MkParseDisplayName` at `0x18004d2f2`
- `ole32!MkParseDisplayName` at `0x18004d2f2`

## pseudocode

```c
HRESULT __fastcall GetObjectFromMoniker(struct CSession **this, OLECHAR *szUserName, struct VAR *a3)
{
  HRESULT result; // eax
  HRESULT v7; // ebx
  const struct _GUID *v8; // rdx
  CSession *v9; // rsi
  ULONG pchEaten; // [rsp+20h] [rbp-60h] BYREF
  LPMONIKER ppmk; // [rsp+28h] [rbp-58h] BYREF
  LPBC ppbc; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppvResult; // [rsp+38h] [rbp-48h] BYREF
  struct tagEXCEPINFO v14; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+B8h] [rbp+38h] BYREF

  if ( !SysStringLen(szUserName) )
    return -2146828283;
  if ( (unsigned int)COleScript::InSafeMode((COleScript *)this, 0) )
    return -2146827859;
  ppbc = 0;
  pchEaten = 0;
  ppmk = 0;
  ppvResult = 0;
  result = CreateBindCtx(0, &ppbc);
  if ( result >= 0 )
  {
    v7 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    if ( v7 >= 0 )
    {
      v15 = BindMoniker(ppmk, 0, &IID_IUnknown, &ppvResult);
      v7 = v15;
      if ( v15 < 0 )
      {
        v9 = this[84];
        if ( v9 )
        {
          if ( (unsigned int)FSupportsErrorInfo((struct IUnknown *)ppmk, v8) )
          {
            memset_0(&v14, 0, sizeof(v14));
            if ( !(unsigned int)GetErrorInfo(&v14) )
            {
              v14.wCode = 0;
              v14.scode = v7;
              CSession::RecordExcepInfoAndClear(v9, &v14, &v15);
              v7 = v15;
            }
          }
        }
      }
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
      if ( v7 >= 0 )
      {
        v7 = PrepareObject(this[84], (struct COleScript *)this, (struct IUnknown *)ppvResult, a3);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppvResult + 16LL))(ppvResult);
      }
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18004d254  mov     [rsp-18h+arg_0], rbx
0x18004d259  mov     [rsp-18h+arg_8], rsi
0x18004d25e  push    rbp
0x18004d25f  push    rdi
0x18004d260  push    r14
0x18004d262  mov     rbp, rsp
0x18004d265  sub     rsp, 80h
0x18004d26c  mov     rdi, rcx
0x18004d26f  mov     r14, r8
0x18004d272  mov     rcx, rdx; pbstr
0x18004d275  mov     rbx, rdx
0x18004d278  call    cs:__imp_SysStringLen
0x18004d27f  nop     dword ptr [rax+rax+00h]
0x18004d284  test    eax, eax
0x18004d286  jnz     short loc_18004D292
0x18004d288  mov     eax, 800A0005h
0x18004d28d  jmp     loc_18004D3CB
0x18004d292  xor     edx, edx; struct _GUID *
0x18004d294  mov     rcx, rdi; this
0x18004d297  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x18004d29c  test    eax, eax
0x18004d29e  jz      short loc_18004D2AA
0x18004d2a0  mov     eax, 800A01ADh
0x18004d2a5  jmp     loc_18004D3CB
0x18004d2aa  lea     rdx, [rbp+ppbc]; ppbc
0x18004d2ae  mov     [rbp+ppbc], 0
0x18004d2b6  xor     ecx, ecx; reserved
0x18004d2b8  mov     [rbp+pchEaten], 0
0x18004d2bf  mov     [rbp+ppmk], 0
0x18004d2c7  mov     [rbp+ppvResult], 0
0x18004d2cf  call    cs:__imp_CreateBindCtx
0x18004d2d6  nop     dword ptr [rax+rax+00h]
0x18004d2db  test    eax, eax
0x18004d2dd  js      loc_18004D3CB
0x18004d2e3  mov     rcx, [rbp+ppbc]; pbc
0x18004d2e7  lea     r9, [rbp+ppmk]; ppmk
0x18004d2eb  lea     r8, [rbp+pchEaten]; pchEaten
0x18004d2ef  mov     rdx, rbx; szUserName
0x18004d2f2  call    cs:__imp_MkParseDisplayName
0x18004d2f9  nop     dword ptr [rax+rax+00h]
0x18004d2fe  mov     rcx, [rbp+ppbc]
0x18004d302  mov     ebx, eax
0x18004d304  mov     rdx, [rcx]
0x18004d307  mov     rax, [rdx+10h]
0x18004d30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d310  test    ebx, ebx
0x18004d312  js      loc_18004D3C9
0x18004d318  mov     rcx, [rbp+ppmk]; pmk
0x18004d31c  lea     r9, [rbp+ppvResult]; ppvResult
0x18004d320  lea     r8, IID_IUnknown; iidResult
0x18004d327  xor     edx, edx; grfOpt
0x18004d329  call    cs:__imp_BindMoniker
0x18004d330  nop     dword ptr [rax+rax+00h]
0x18004d335  mov     [rbp+arg_18], eax
0x18004d338  mov     ebx, eax
0x18004d33a  test    eax, eax
0x18004d33c  jns     short loc_18004D38D
0x18004d33e  mov     rsi, [rdi+2A0h]
0x18004d345  test    rsi, rsi
0x18004d348  jz      short loc_18004D38D
0x18004d34a  mov     rcx, [rbp+ppmk]; struct IUnknown *
0x18004d34e  call    ?FSupportsErrorInfo@@YAHPEAUIUnknown@@AEBU_GUID@@@Z; FSupportsErrorInfo(IUnknown *,_GUID const &)
0x18004d353  test    eax, eax
0x18004d355  jz      short loc_18004D38D
0x18004d357  xor     edx, edx; Val
0x18004d359  lea     rcx, [rbp+var_40]; void *
0x18004d35d  lea     r8d, [rdx+40h]; Size
0x18004d361  call    memset_0
0x18004d366  lea     rcx, [rbp+var_40]; struct tagEXCEPINFO *
0x18004d36a  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x18004d36f  test    eax, eax
0x18004d371  jnz     short loc_18004D38D
0x18004d373  lea     r8, [rbp+arg_18]; int *
0x18004d377  mov     [rbp+var_40.wCode], ax
0x18004d37b  lea     rdx, [rbp+var_40]; struct tagEXCEPINFO *
0x18004d37f  mov     [rbp+var_40.scode], ebx
0x18004d382  mov     rcx, rsi; this
0x18004d385  call    ?RecordExcepInfoAndClear@CSession@@QEAAXPEAUtagEXCEPINFO@@PEAJ@Z; CSession::RecordExcepInfoAndClear(tagEXCEPINFO *,long *)
0x18004d38a  mov     ebx, [rbp+arg_18]
0x18004d38d  mov     rcx, [rbp+ppmk]
0x18004d391  mov     rdx, [rcx]
0x18004d394  mov     rax, [rdx+10h]
0x18004d398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d39d  test    ebx, ebx
0x18004d39f  js      short loc_18004D3C9
0x18004d3a1  mov     r8, [rbp+ppvResult]; struct IUnknown *
0x18004d3a5  mov     r9, r14; struct VAR *
0x18004d3a8  mov     rcx, [rdi+2A0h]; struct CSession *
0x18004d3af  mov     rdx, rdi; struct COleScript *
0x18004d3b2  call    ?PrepareObject@@YAJPEAVCSession@@PEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(CSession *,COleScript *,IUnknown *,VAR *)
0x18004d3b7  mov     rcx, [rbp+ppvResult]
0x18004d3bb  mov     ebx, eax
0x18004d3bd  mov     rdx, [rcx]
0x18004d3c0  mov     rax, [rdx+10h]
0x18004d3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d3c9  mov     eax, ebx
0x18004d3cb  lea     r11, [rsp+80h+var_s0]
0x18004d3d3  mov     rbx, [r11+20h]
0x18004d3d7  mov     rsi, [r11+28h]
0x18004d3db  mov     rsp, r11
0x18004d3de  pop     r14
0x18004d3e0  pop     rdi
0x18004d3e1  pop     rbp
0x18004d3e2  retn
```
