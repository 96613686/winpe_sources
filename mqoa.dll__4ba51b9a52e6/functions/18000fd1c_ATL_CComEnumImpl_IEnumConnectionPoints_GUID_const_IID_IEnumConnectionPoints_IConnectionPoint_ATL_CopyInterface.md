# ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Next(ulong,IConnectionPoint * *,ulong *)

- ea: `0x18000fd1c`
- end: `0x18000fe0f`
- name: `?Next@?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJKPEAPEAUIConnectionPoint@@PEAK@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000fd10`

## callees

- `0x18000a6cc`
- `0x18000fd1c`
- `0x180012d1c`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Next(
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
        *a4 = (__int64)(a1[3] - a1[4]) >> 3;
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
  v9 = (v8 - a1[4]) >> 3;
  v10 = (unsigned int)v9 < a2;
  if ( (unsigned int)v9 > a2 )
    LODWORD(v9) = a2;
  if ( a4 )
    *a4 = v9;
  for ( i = (unsigned __int64)a3; ; i += 8LL )
  {
    if ( !(_DWORD)v9 )
      return v10;
    v12 = ATL::_CopyInterface<IConnectionPoint>::copy(i, a1[4]);
    if ( v12 < 0 )
      break;
    LODWORD(v9) = v9 - 1;
    a1[4] += 8LL;
  }
  while ( (unsigned __int64)v5 < i )
  {
    v13 = v5++;
    ATL::_CopyInterface<IConnectionPoint>::destroy(v13);
  }
  if ( a4 )
    *a4 = 0;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000fd1c  push    rbx
0x18000fd1e  push    rbp
0x18000fd1f  push    rsi
0x18000fd20  push    rdi
0x18000fd21  push    r12
0x18000fd23  push    r14
0x18000fd25  push    r15
0x18000fd27  sub     rsp, 20h
0x18000fd2b  mov     r14, r9
0x18000fd2e  mov     rsi, r8
0x18000fd31  mov     rdi, rcx
0x18000fd34  test    edx, edx
0x18000fd36  jnz     short loc_18000FD5C
0x18000fd38  test    r8, r8
0x18000fd3b  jnz     short loc_18000FD6A
0x18000fd3d  test    r9, r9
0x18000fd40  jz      loc_18000FDFB
0x18000fd46  mov     rax, [rcx+18h]
0x18000fd4a  sub     rax, [rcx+20h]
0x18000fd4e  sar     rax, 3
0x18000fd52  mov     [r9], eax
0x18000fd55  xor     eax, eax
0x18000fd57  jmp     loc_18000FE00
0x18000fd5c  test    rsi, rsi
0x18000fd5f  jz      loc_18000FDFB
0x18000fd65  cmp     edx, 1
0x18000fd68  jz      short loc_18000FD73
0x18000fd6a  test    r14, r14
0x18000fd6d  jz      loc_18000FDFB
0x18000fd73  cmp     qword ptr [rcx+10h], 0
0x18000fd78  jz      short loc_18000FDF4
0x18000fd7a  mov     rbx, [rcx+18h]
0x18000fd7e  test    rbx, rbx
0x18000fd81  jz      short loc_18000FDF4
0x18000fd83  cmp     qword ptr [rcx+20h], 0
0x18000fd88  jz      short loc_18000FDF4
0x18000fd8a  sub     rbx, [rcx+20h]
0x18000fd8e  xor     r12d, r12d
0x18000fd91  sar     rbx, 3
0x18000fd95  cmp     ebx, edx
0x18000fd97  setb    r12b
0x18000fd9b  cmova   ebx, edx
0x18000fd9e  test    r14, r14
0x18000fda1  jz      short loc_18000FDA6
0x18000fda3  mov     [r9], ebx
0x18000fda6  mov     rbp, rsi
0x18000fda9  test    ebx, ebx
0x18000fdab  jz      short loc_18000FDEF
0x18000fdad  mov     rdx, [rdi+20h]
0x18000fdb1  mov     rcx, rbp
0x18000fdb4  call    ?copy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAJPEAPEAUIConnectionPoint@@0@Z; ATL::_CopyInterface<IConnectionPoint>::copy(IConnectionPoint * *,IConnectionPoint * *)
0x18000fdb9  mov     r15d, eax
0x18000fdbc  test    eax, eax
0x18000fdbe  js      short loc_18000FDD9
0x18000fdc0  dec     ebx
0x18000fdc2  add     rbp, 8
0x18000fdc6  add     qword ptr [rdi+20h], 8
0x18000fdcb  jmp     short loc_18000FDA9
0x18000fdcd  mov     rcx, rsi
0x18000fdd0  add     rsi, 8
0x18000fdd4  call    ?destroy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAXPEAPEAUIConnectionPoint@@@Z; ATL::_CopyInterface<IConnectionPoint>::destroy(IConnectionPoint * *)
0x18000fdd9  cmp     rsi, rbp
0x18000fddc  jb      short loc_18000FDCD
0x18000fdde  test    r14, r14
0x18000fde1  jz      short loc_18000FDEA
0x18000fde3  mov     dword ptr [r14], 0
0x18000fdea  mov     eax, r15d
0x18000fded  jmp     short loc_18000FE00
0x18000fdef  mov     eax, r12d
0x18000fdf2  jmp     short loc_18000FE00
0x18000fdf4  mov     eax, 80004005h
0x18000fdf9  jmp     short loc_18000FE00
0x18000fdfb  mov     eax, 80004003h
0x18000fe00  add     rsp, 20h
0x18000fe04  pop     r15
0x18000fe06  pop     r14
0x18000fe08  pop     r12
0x18000fe0a  pop     rdi
0x18000fe0b  pop     rsi
0x18000fe0c  pop     rbp
0x18000fe0d  pop     rbx
0x18000fe0e  retn
```
