# ATL::CComSafeArray<ushort *,8>::CComSafeArray<ushort *,8>(tagSAFEARRAY const *)

- ea: `0x18001c7bc`
- end: `0x18001c85f`
- name: `??0?$CComSafeArray@PEAG$07@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, struct tagSAFEARRAY *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e100`
- `0x18001e4f8`
- `0x18001e9b8`

## callees

- `0x18001886c`
- `0x18001c7bc`
- `0x18001cfa0`
- `0x18001d74c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18001c834`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001c834`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001c81a`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001c81a`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned short *,8>::CComSafeArray<unsigned short *,8>(
        SAFEARRAY **ppsaOut,
        struct tagSAFEARRAY *a2)
{
  int ActualVartype; // eax
  int v5; // eax
  HRESULT v6; // eax
  HRESULT v7; // eax
  unsigned __int16 v9; // [rsp+30h] [rbp+8h] BYREF

  *ppsaOut = 0;
  if ( !a2 )
    goto LABEL_13;
  v9 = 0;
  ActualVartype = ATL::AtlSafeArrayGetActualVartype(a2, &v9);
  if ( ActualVartype < 0 )
    ATL::AtlThrowImpl(ActualVartype);
  if ( v9 != 8 )
LABEL_13:
    ATL::AtlThrowImpl(-2147024809);
  v5 = ATL::CComSafeArray<unsigned short *,8>::Destroy(ppsaOut);
  if ( v5 < 0 )
    ATL::AtlThrowImpl(v5);
  v6 = SafeArrayCopy(a2, ppsaOut);
  if ( v6 < 0 )
    ATL::AtlThrowImpl(v6);
  if ( *ppsaOut )
  {
    v7 = SafeArrayLock(*ppsaOut);
    if ( v7 < 0 )
      ATL::AtlThrowImpl(v7);
  }
  return ppsaOut;
}

```

## disassembly

```asm
0x18001c7bc  mov     [rsp+arg_8], rbx
0x18001c7c1  push    rdi
0x18001c7c2  sub     rsp, 20h
0x18001c7c6  mov     qword ptr [rcx], 0
0x18001c7cd  mov     rdi, rdx
0x18001c7d0  mov     rbx, rcx
0x18001c7d3  test    rdx, rdx
0x18001c7d6  jz      short loc_18001C854
0x18001c7d8  xor     eax, eax
0x18001c7da  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 *
0x18001c7df  mov     rcx, rdi; struct tagSAFEARRAY *
0x18001c7e2  mov     [rsp+28h+arg_0], ax
0x18001c7e7  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18001c7ec  test    eax, eax
0x18001c7ee  jns     short loc_18001C7F8
0x18001c7f0  mov     ecx, eax; int
0x18001c7f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001c7f8  cmp     [rsp+28h+arg_0], 8
0x18001c7fe  jnz     short loc_18001C854
0x18001c800  mov     rcx, rbx
0x18001c803  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001c808  test    eax, eax
0x18001c80a  jns     short loc_18001C814
0x18001c80c  mov     ecx, eax; int
0x18001c80e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001c814  mov     rdx, rbx; ppsaOut
0x18001c817  mov     rcx, rdi; psa
0x18001c81a  call    cs:__imp_SafeArrayCopy
0x18001c820  test    eax, eax
0x18001c822  jns     short loc_18001C82C
0x18001c824  mov     ecx, eax; int
0x18001c826  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001c82c  mov     rcx, [rbx]; psa
0x18001c82f  test    rcx, rcx
0x18001c832  jz      short loc_18001C846
0x18001c834  call    cs:__imp_SafeArrayLock
0x18001c83a  test    eax, eax
0x18001c83c  jns     short loc_18001C846
0x18001c83e  mov     ecx, eax; int
0x18001c840  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001c846  mov     rax, rbx
0x18001c849  mov     rbx, [rsp+28h+arg_8]
0x18001c84e  add     rsp, 20h
0x18001c852  pop     rdi
0x18001c853  retn
0x18001c854  mov     ecx, 80070057h; int
0x18001c859  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
