# ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(tagSAFEARRAY const *)

- ea: `0x18003aa18`
- end: `0x18003aabb`
- name: `??0?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAA@PEBUtagSAFEARRAY@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003b380`

## callees

- `0x18003aa18`
- `0x18003ac98`
- `0x18003acec`
- `0x18003ad1c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18003aa90`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003aa90`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18003aa76`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18003aa76`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<tagVARIANT,12>::CComSafeArray<tagVARIANT,12>(
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
  if ( v9 != 12 )
LABEL_13:
    ATL::AtlThrowImpl(-2147024809);
  v5 = ATL::CComSafeArray<tagVARIANT,12>::Destroy(ppsaOut);
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
0x18003aa18  mov     [rsp+arg_8], rbx
0x18003aa1d  push    rdi
0x18003aa1e  sub     rsp, 20h
0x18003aa22  mov     qword ptr [rcx], 0
0x18003aa29  mov     rdi, rdx
0x18003aa2c  mov     rbx, rcx
0x18003aa2f  test    rdx, rdx
0x18003aa32  jz      short loc_18003AAB0
0x18003aa34  xor     eax, eax
0x18003aa36  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 *
0x18003aa3b  mov     rcx, rdi; struct tagSAFEARRAY *
0x18003aa3e  mov     [rsp+28h+arg_0], ax
0x18003aa43  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18003aa48  test    eax, eax
0x18003aa4a  jns     short loc_18003AA54
0x18003aa4c  mov     ecx, eax; int
0x18003aa4e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003aa54  cmp     [rsp+28h+arg_0], 0Ch
0x18003aa5a  jnz     short loc_18003AAB0
0x18003aa5c  mov     rcx, rbx
0x18003aa5f  call    ?Destroy@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJXZ; ATL::CComSafeArray<tagVARIANT,12>::Destroy(void)
0x18003aa64  test    eax, eax
0x18003aa66  jns     short loc_18003AA70
0x18003aa68  mov     ecx, eax; int
0x18003aa6a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003aa70  mov     rdx, rbx; ppsaOut
0x18003aa73  mov     rcx, rdi; psa
0x18003aa76  call    cs:__imp_SafeArrayCopy
0x18003aa7c  test    eax, eax
0x18003aa7e  jns     short loc_18003AA88
0x18003aa80  mov     ecx, eax; int
0x18003aa82  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003aa88  mov     rcx, [rbx]; psa
0x18003aa8b  test    rcx, rcx
0x18003aa8e  jz      short loc_18003AAA2
0x18003aa90  call    cs:__imp_SafeArrayLock
0x18003aa96  test    eax, eax
0x18003aa98  jns     short loc_18003AAA2
0x18003aa9a  mov     ecx, eax; int
0x18003aa9c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003aaa2  mov     rax, rbx
0x18003aaa5  mov     rbx, [rsp+28h+arg_8]
0x18003aaaa  add     rsp, 20h
0x18003aaae  pop     rdi
0x18003aaaf  retn
0x18003aab0  mov     ecx, 80070057h; int
0x18003aab5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
