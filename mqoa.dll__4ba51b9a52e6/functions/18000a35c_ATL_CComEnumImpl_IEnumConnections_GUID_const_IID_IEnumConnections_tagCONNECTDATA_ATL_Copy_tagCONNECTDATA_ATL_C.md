# ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Next(ulong,tagCONNECTDATA *,ulong *)

- ea: `0x18000a35c`
- end: `0x18000a44f`
- name: `?Next@?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@V?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJKPEAUtagCONNECTDATA@@PEAK@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000a350`

## callees

- `0x18000a35c`
- `0x18000a6a0`
- `0x18000a6cc`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Next(
        _QWORD *a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4)
{
  __int64 *v5; // rsi
  __int64 v8; // rbx
  __int64 v9; // rbx
  BOOL v10; // r12d
  unsigned __int64 i; // rbp
  int v12; // r15d
  __int64 *v13; // rcx

  v5 = a3;
  if ( !a2 )
  {
    if ( !a3 )
    {
      if ( a4 )
      {
        *a4 = (__int64)(a1[3] - a1[4]) >> 4;
        return 0;
      }
      return 2147500035LL;
    }
    goto LABEL_7;
  }
  if ( !a3 )
    return 2147500035LL;
  if ( a2 != 1 )
  {
LABEL_7:
    if ( a4 )
      goto LABEL_8;
    return 2147500035LL;
  }
LABEL_8:
  if ( !a1[2] )
    return 2147500037LL;
  v8 = a1[3];
  if ( !v8 || !a1[4] )
    return 2147500037LL;
  v9 = (v8 - a1[4]) >> 4;
  v10 = (unsigned int)v9 < a2;
  if ( (unsigned int)v9 > a2 )
    LODWORD(v9) = a2;
  if ( a4 )
    *a4 = v9;
  for ( i = (unsigned __int64)a3; ; i += 16LL )
  {
    if ( !(_DWORD)v9 )
      return v10;
    v12 = ATL::_Copy<tagCONNECTDATA>::copy(i, a1[4]);
    if ( v12 < 0 )
      break;
    LODWORD(v9) = v9 - 1;
    a1[4] += 16LL;
  }
  while ( (unsigned __int64)v5 < i )
  {
    v13 = v5;
    v5 += 2;
    ATL::_CopyInterface<IConnectionPoint>::destroy(v13);
  }
  if ( a4 )
    *a4 = 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000a35c  push    rbx
0x18000a35e  push    rbp
0x18000a35f  push    rsi
0x18000a360  push    rdi
0x18000a361  push    r12
0x18000a363  push    r14
0x18000a365  push    r15
0x18000a367  sub     rsp, 20h
0x18000a36b  mov     r14, r9
0x18000a36e  mov     rsi, r8
0x18000a371  mov     rdi, rcx
0x18000a374  test    edx, edx
0x18000a376  jnz     short loc_18000A39C
0x18000a378  test    r8, r8
0x18000a37b  jnz     short loc_18000A3AA
0x18000a37d  test    r9, r9
0x18000a380  jz      loc_18000A43B
0x18000a386  mov     rax, [rcx+18h]
0x18000a38a  sub     rax, [rcx+20h]
0x18000a38e  sar     rax, 4
0x18000a392  mov     [r9], eax
0x18000a395  xor     eax, eax
0x18000a397  jmp     loc_18000A440
0x18000a39c  test    rsi, rsi
0x18000a39f  jz      loc_18000A43B
0x18000a3a5  cmp     edx, 1
0x18000a3a8  jz      short loc_18000A3B3
0x18000a3aa  test    r14, r14
0x18000a3ad  jz      loc_18000A43B
0x18000a3b3  cmp     qword ptr [rcx+10h], 0
0x18000a3b8  jz      short loc_18000A434
0x18000a3ba  mov     rbx, [rcx+18h]
0x18000a3be  test    rbx, rbx
0x18000a3c1  jz      short loc_18000A434
0x18000a3c3  cmp     qword ptr [rcx+20h], 0
0x18000a3c8  jz      short loc_18000A434
0x18000a3ca  sub     rbx, [rcx+20h]
0x18000a3ce  xor     r12d, r12d
0x18000a3d1  sar     rbx, 4
0x18000a3d5  cmp     ebx, edx
0x18000a3d7  setb    r12b
0x18000a3db  cmova   ebx, edx
0x18000a3de  test    r14, r14
0x18000a3e1  jz      short loc_18000A3E6
0x18000a3e3  mov     [r9], ebx
0x18000a3e6  mov     rbp, rsi
0x18000a3e9  test    ebx, ebx
0x18000a3eb  jz      short loc_18000A42F
0x18000a3ed  mov     rdx, [rdi+20h]
0x18000a3f1  mov     rcx, rbp
0x18000a3f4  call    ?copy@?$_Copy@UtagCONNECTDATA@@@ATL@@SAJPEAUtagCONNECTDATA@@0@Z; ATL::_Copy<tagCONNECTDATA>::copy(tagCONNECTDATA *,tagCONNECTDATA *)
0x18000a3f9  mov     r15d, eax
0x18000a3fc  test    eax, eax
0x18000a3fe  js      short loc_18000A419
0x18000a400  dec     ebx
0x18000a402  add     rbp, 10h
0x18000a406  add     qword ptr [rdi+20h], 10h
0x18000a40b  jmp     short loc_18000A3E9
0x18000a40d  mov     rcx, rsi
0x18000a410  add     rsi, 10h
0x18000a414  call    ?destroy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAXPEAPEAUIConnectionPoint@@@Z; ATL::_CopyInterface<IConnectionPoint>::destroy(IConnectionPoint * *)
0x18000a419  cmp     rsi, rbp
0x18000a41c  jb      short loc_18000A40D
0x18000a41e  test    r14, r14
0x18000a421  jz      short loc_18000A42A
0x18000a423  mov     dword ptr [r14], 0
0x18000a42a  mov     eax, r15d
0x18000a42d  jmp     short loc_18000A440
0x18000a42f  mov     eax, r12d
0x18000a432  jmp     short loc_18000A440
0x18000a434  mov     eax, 80004005h
0x18000a439  jmp     short loc_18000A440
0x18000a43b  mov     eax, 80004003h
0x18000a440  add     rsp, 20h
0x18000a444  pop     r15
0x18000a446  pop     r14
0x18000a448  pop     r12
0x18000a44a  pop     rdi
0x18000a44b  pop     rsi
0x18000a44c  pop     rbp
0x18000a44d  pop     rbx
0x18000a44e  retn
```
