# GetObjectFromMoniker

- ea: `0x18004c5ac`
- end: `0x18004c723`
- name: `GetObjectFromMoniker`
- size: `375`
- prototype: `__int64 __fastcall(COleScript *this, LPCOLESTR szUserName)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180031f24`

## callees

- `0x180043e08`
- `0x18004c5ac`
- `0x18004c72c`
- `0x180073a98`
- `0x180073dec`
- `0x18007409c`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18004c5d0`
- `OLEAUT32!__imp_SysStringLen` at `0x18004c5d0`
- `ole32!CreateBindCtx` at `0x18004c621`
- `ole32!CreateBindCtx` at `0x18004c621`
- `ole32!BindMoniker` at `0x18004c66f`
- `ole32!BindMoniker` at `0x18004c66f`
- `ole32!MkParseDisplayName` at `0x18004c63e`
- `ole32!MkParseDisplayName` at `0x18004c63e`

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
0x18004c5ac  mov     [rsp-18h+arg_0], rbx
0x18004c5b1  mov     [rsp-18h+arg_8], rsi
0x18004c5b6  push    rbp
0x18004c5b7  push    rdi
0x18004c5b8  push    r14
0x18004c5ba  mov     rbp, rsp
0x18004c5bd  sub     rsp, 80h
0x18004c5c4  mov     rdi, rcx
0x18004c5c7  mov     r14, r8
0x18004c5ca  mov     rcx, rdx; pbstr
0x18004c5cd  mov     rbx, rdx
0x18004c5d0  call    cs:__imp_SysStringLen
0x18004c5d6  test    eax, eax
0x18004c5d8  jnz     short loc_18004C5E4
0x18004c5da  mov     eax, 800A0005h
0x18004c5df  jmp     loc_18004C70B
0x18004c5e4  xor     edx, edx; struct _GUID *
0x18004c5e6  mov     rcx, rdi; this
0x18004c5e9  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x18004c5ee  test    eax, eax
0x18004c5f0  jz      short loc_18004C5FC
0x18004c5f2  mov     eax, 800A01ADh
0x18004c5f7  jmp     loc_18004C70B
0x18004c5fc  lea     rdx, [rbp+ppbc]; ppbc
0x18004c600  mov     [rbp+ppbc], 0
0x18004c608  xor     ecx, ecx; reserved
0x18004c60a  mov     [rbp+pchEaten], 0
0x18004c611  mov     [rbp+ppmk], 0
0x18004c619  mov     [rbp+ppvResult], 0
0x18004c621  call    cs:__imp_CreateBindCtx
0x18004c627  test    eax, eax
0x18004c629  js      loc_18004C70B
0x18004c62f  mov     rcx, [rbp+ppbc]; pbc
0x18004c633  lea     r9, [rbp+ppmk]; ppmk
0x18004c637  lea     r8, [rbp+pchEaten]; pchEaten
0x18004c63b  mov     rdx, rbx; szUserName
0x18004c63e  call    cs:__imp_MkParseDisplayName
0x18004c644  mov     rcx, [rbp+ppbc]
0x18004c648  mov     ebx, eax
0x18004c64a  mov     rdx, [rcx]
0x18004c64d  mov     rax, [rdx+10h]
0x18004c651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c656  test    ebx, ebx
0x18004c658  js      loc_18004C709
0x18004c65e  mov     rcx, [rbp+ppmk]; pmk
0x18004c662  lea     r9, [rbp+ppvResult]; ppvResult
0x18004c666  lea     r8, IID_IUnknown; iidResult
0x18004c66d  xor     edx, edx; grfOpt
0x18004c66f  call    cs:__imp_BindMoniker
0x18004c675  mov     [rbp+arg_18], eax
0x18004c678  mov     ebx, eax
0x18004c67a  test    eax, eax
0x18004c67c  jns     short loc_18004C6CD
0x18004c67e  mov     rsi, [rdi+2A0h]
0x18004c685  test    rsi, rsi
0x18004c688  jz      short loc_18004C6CD
0x18004c68a  mov     rcx, [rbp+ppmk]; struct IUnknown *
0x18004c68e  call    ?FSupportsErrorInfo@@YAHPEAUIUnknown@@AEBU_GUID@@@Z; FSupportsErrorInfo(IUnknown *,_GUID const &)
0x18004c693  test    eax, eax
0x18004c695  jz      short loc_18004C6CD
0x18004c697  xor     edx, edx; Val
0x18004c699  lea     rcx, [rbp+var_40]; void *
0x18004c69d  lea     r8d, [rdx+40h]; Size
0x18004c6a1  call    memset_0
0x18004c6a6  lea     rcx, [rbp+var_40]; struct tagEXCEPINFO *
0x18004c6aa  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x18004c6af  test    eax, eax
0x18004c6b1  jnz     short loc_18004C6CD
0x18004c6b3  lea     r8, [rbp+arg_18]; int *
0x18004c6b7  mov     [rbp+var_40.wCode], ax
0x18004c6bb  lea     rdx, [rbp+var_40]; struct tagEXCEPINFO *
0x18004c6bf  mov     [rbp+var_40.scode], ebx
0x18004c6c2  mov     rcx, rsi; this
0x18004c6c5  call    ?RecordExcepInfoAndClear@CSession@@QEAAXPEAUtagEXCEPINFO@@PEAJ@Z; CSession::RecordExcepInfoAndClear(tagEXCEPINFO *,long *)
0x18004c6ca  mov     ebx, [rbp+arg_18]
0x18004c6cd  mov     rcx, [rbp+ppmk]
0x18004c6d1  mov     rdx, [rcx]
0x18004c6d4  mov     rax, [rdx+10h]
0x18004c6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6dd  test    ebx, ebx
0x18004c6df  js      short loc_18004C709
0x18004c6e1  mov     r8, [rbp+ppvResult]; struct IUnknown *
0x18004c6e5  mov     r9, r14; struct VAR *
0x18004c6e8  mov     rcx, [rdi+2A0h]; struct CSession *
0x18004c6ef  mov     rdx, rdi; struct COleScript *
0x18004c6f2  call    ?PrepareObject@@YAJPEAVCSession@@PEAVCOleScript@@PEAUIUnknown@@PEAVVAR@@@Z; PrepareObject(CSession *,COleScript *,IUnknown *,VAR *)
0x18004c6f7  mov     rcx, [rbp+ppvResult]
0x18004c6fb  mov     ebx, eax
0x18004c6fd  mov     rdx, [rcx]
0x18004c700  mov     rax, [rdx+10h]
0x18004c704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c709  mov     eax, ebx
0x18004c70b  lea     r11, [rsp+80h+var_s0]
0x18004c713  mov     rbx, [r11+20h]
0x18004c717  mov     rsi, [r11+28h]
0x18004c71b  mov     rsp, r11
0x18004c71e  pop     r14
0x18004c720  pop     rdi
0x18004c721  pop     rbp
0x18004c722  retn
```
