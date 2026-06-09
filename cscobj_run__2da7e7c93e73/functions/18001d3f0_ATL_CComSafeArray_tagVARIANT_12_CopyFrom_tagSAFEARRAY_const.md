# ATL::CComSafeArray<tagVARIANT,12>::CopyFrom(tagSAFEARRAY const *)

- ea: `0x18001d3f0`
- end: `0x18001d47d`
- name: `?CopyFrom@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEAAJPEBUtagSAFEARRAY@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(SAFEARRAY **ppsaOut, struct tagSAFEARRAY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001c898`
- `0x18001cb40`

## callees

- `0x18001886c`
- `0x18001cfa0`
- `0x18001d3f0`
- `0x18001d74c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayLock` at `0x18001d461`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001d461`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001d447`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001d447`

## pseudocode

```c
int __fastcall ATL::CComSafeArray<tagVARIANT,12>::CopyFrom(SAFEARRAY **ppsaOut, struct tagSAFEARRAY *a2)
{
  int ActualVartype; // eax
  int v5; // eax
  int result; // eax
  unsigned __int16 v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    goto LABEL_12;
  v7 = 0;
  ActualVartype = ATL::AtlSafeArrayGetActualVartype(a2, &v7);
  if ( ActualVartype < 0 )
    ATL::AtlThrowImpl(ActualVartype);
  if ( v7 != 12 )
LABEL_12:
    ATL::AtlThrowImpl(-2147024809);
  v5 = ATL::CComSafeArray<unsigned short *,8>::Destroy(ppsaOut);
  if ( v5 < 0 )
    ATL::AtlThrowImpl(v5);
  result = SafeArrayCopy(a2, ppsaOut);
  if ( result < 0 )
    ATL::AtlThrowImpl(result);
  if ( *ppsaOut )
    return SafeArrayLock(*ppsaOut);
  return result;
}

```

## disassembly

```asm
0x18001d3f0  mov     [rsp+arg_0], rbx
0x18001d3f5  push    rdi
0x18001d3f6  sub     rsp, 20h
0x18001d3fa  mov     rdi, rdx
0x18001d3fd  mov     rbx, rcx
0x18001d400  test    rdx, rdx
0x18001d403  jz      short loc_18001D472
0x18001d405  xor     eax, eax
0x18001d407  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 *
0x18001d40c  mov     rcx, rdi; struct tagSAFEARRAY *
0x18001d40f  mov     [rsp+28h+arg_8], ax
0x18001d414  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18001d419  test    eax, eax
0x18001d41b  jns     short loc_18001D425
0x18001d41d  mov     ecx, eax; int
0x18001d41f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d425  cmp     [rsp+28h+arg_8], 0Ch
0x18001d42b  jnz     short loc_18001D472
0x18001d42d  mov     rcx, rbx
0x18001d430  call    ?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ; ATL::CComSafeArray<ushort *,8>::Destroy(void)
0x18001d435  test    eax, eax
0x18001d437  jns     short loc_18001D441
0x18001d439  mov     ecx, eax; int
0x18001d43b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d441  mov     rdx, rbx; ppsaOut
0x18001d444  mov     rcx, rdi; psa
0x18001d447  call    cs:__imp_SafeArrayCopy
0x18001d44d  test    eax, eax
0x18001d44f  jns     short loc_18001D459
0x18001d451  mov     ecx, eax; int
0x18001d453  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d459  mov     rcx, [rbx]; psa
0x18001d45c  test    rcx, rcx
0x18001d45f  jz      short loc_18001D467
0x18001d461  call    cs:__imp_SafeArrayLock
0x18001d467  mov     rbx, [rsp+28h+arg_0]
0x18001d46c  add     rsp, 20h
0x18001d470  pop     rdi
0x18001d471  retn
0x18001d472  mov     ecx, 80070057h; int
0x18001d477  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
