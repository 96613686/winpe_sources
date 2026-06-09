# ConvertDevicePathToDosPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180014690`
- end: `0x1800148d1`
- name: `?ConvertDevicePathToDosPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `577`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800164b0`

## callees

- `0x18000be40`
- `0x18000c7e8`
- `0x1800138d4`
- `0x18001415c`
- `0x180014190`
- `0x1800142a8`
- `0x180014458`
- `0x180014690`
- `0x1800161a0`
- `0x180016480`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001480b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001480b`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1800146d8`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180014709`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x1800146d8`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180014709`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180014797`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180014797`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ConvertDevicePathToDosPath(__int64 a1, __int64 a2)
{
  DWORD LogicalDriveStringsW; // r15d
  WCHAR *v5; // rax
  DWORD v7; // edi
  _WORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  const WCHAR *v11; // rax
  unsigned __int64 v12; // r14
  const WCHAR *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  _BYTE v17[32]; // [rsp+50h] [rbp-288h] BYREF
  _BYTE v18[32]; // [rsp+70h] [rbp-268h] BYREF
  WCHAR TargetPath[264]; // [rsp+90h] [rbp-248h] BYREF

  LogicalDriveStringsW = GetLogicalDriveStringsW(0, 0);
  std::wstring::wstring(v17);
  std::wstring::resize(v17, LogicalDriveStringsW);
  v5 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  if ( GetLogicalDriveStringsW(LogicalDriveStringsW, v5) )
  {
    memset_0(TargetPath, 0, 0x208u);
    std::wstring::wstring(v18, L" :");
    v7 = 0;
    while ( 1 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      v8 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
      *v8 = *(_WORD *)(v10 + 2 * v9);
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
      if ( !QueryDosDeviceW(v11, TargetPath, 0x104u) )
        goto LABEL_11;
      v12 = -1;
      do
        ++v12;
      while ( TargetPath[v12] );
      if ( *(_QWORD *)(a2 + 16) < v12 )
      {
        std::wstring::wstring(a1, a2);
        std::wstring::~wstring(v18);
        std::wstring::~wstring(v17);
        return a1;
      }
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      if ( CompareStringOrdinal(v13, v12, TargetPath, v12, 1) == 2 )
        break;
      do
      {
LABEL_11:
        if ( v7 >= LogicalDriveStringsW )
          goto LABEL_15;
        ++v7;
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
      }
      while ( *(_WORD *)(v15 + 2 * v16) );
      if ( v7 >= LogicalDriveStringsW || !*(_WORD *)(v15 + 2LL * v7) )
      {
LABEL_15:
        std::wstring::~wstring(v18);
        std::wstring::wstring(a1, a2);
        std::wstring::~wstring(v17);
        return a1;
      }
    }
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    std::operator+<unsigned short>(a1, v18, v14 + 2 * v12);
    std::wstring::~wstring(v18);
    std::wstring::~wstring(v17);
    return a1;
  }
  else
  {
    std::wstring::wstring(a1, a2);
    std::wstring::~wstring(v17);
    return a1;
  }
}

```

## disassembly

```asm
0x180014690  mov     rax, rsp
0x180014693  push    rsi
0x180014694  push    rdi
0x180014695  push    r12
0x180014697  push    r14
0x180014699  push    r15
0x18001469b  sub     rsp, 2B0h
0x1800146a2  mov     [rsp+2D8h+var_290], 0FFFFFFFFFFFFFFFEh
0x1800146ab  mov     [rax+18h], rbx
0x1800146af  mov     rax, cs:__security_cookie
0x1800146b6  xor     rax, rsp
0x1800146b9  mov     [rsp+2D8h+var_38], rax
0x1800146c1  mov     rsi, rdx
0x1800146c4  mov     rbx, rcx
0x1800146c7  mov     [rsp+2D8h+var_2A8], rcx
0x1800146cc  mov     [rsp+2D8h+var_298], rdx
0x1800146d1  xor     r12d, r12d
0x1800146d4  xor     edx, edx; lpBuffer
0x1800146d6  xor     ecx, ecx; nBufferLength
0x1800146d8  call    cs:__imp_GetLogicalDriveStringsW
0x1800146de  mov     r15d, eax
0x1800146e1  lea     rcx, [rsp+2D8h+var_288]
0x1800146e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800146eb  nop
0x1800146ec  mov     edx, r15d
0x1800146ef  lea     rcx, [rsp+2D8h+var_288]
0x1800146f4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800146f9  lea     rcx, [rsp+2D8h+var_288]
0x1800146fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014703  mov     rdx, rax; lpBuffer
0x180014706  mov     ecx, r15d; nBufferLength
0x180014709  call    cs:__imp_GetLogicalDriveStringsW
0x18001470f  test    eax, eax
0x180014711  jnz     short loc_180014731
0x180014713  mov     rdx, rsi
0x180014716  mov     rcx, rbx
0x180014719  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001471e  nop
0x18001471f  lea     rcx, [rsp+2D8h+var_288]
0x180014724  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014729  mov     rax, rbx
0x18001472c  jmp     loc_1800148A9
0x180014731  xor     edx, edx; Val
0x180014733  mov     r8d, 208h; Size
0x180014739  lea     rcx, [rsp+2D8h+TargetPath]; void *
0x180014741  call    memset_0
0x180014746  lea     rdx, asc_180025DC0; " :"
0x18001474d  lea     rcx, [rsp+2D8h+var_268]
0x180014752  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014757  nop
0x180014758  mov     edi, r12d
0x18001475b  lea     rcx, [rsp+2D8h+var_288]
0x180014760  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014765  mov     r8, rax
0x180014768  mov     edx, edi
0x18001476a  lea     rcx, [rsp+2D8h+var_268]
0x18001476f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014774  movzx   ecx, word ptr [r8+rdx*2]
0x180014779  mov     [rax], cx
0x18001477c  lea     rcx, [rsp+2D8h+var_268]
0x180014781  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014786  mov     rcx, rax; lpDeviceName
0x180014789  mov     r8d, 104h; ucchMax
0x18001478f  lea     rdx, [rsp+2D8h+TargetPath]; lpTargetPath
0x180014797  call    cs:__imp_QueryDosDeviceW
0x18001479d  test    eax, eax
0x18001479f  jz      loc_18001484A
0x1800147a5  lea     rax, [rsp+2D8h+TargetPath]
0x1800147ad  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800147b1  inc     r14
0x1800147b4  cmp     [rax+r14*2], r12w
0x1800147b9  jnz     short loc_1800147B1
0x1800147bb  cmp     [rsi+10h], r14
0x1800147bf  jnb     short loc_1800147EA
0x1800147c1  mov     rdx, rsi
0x1800147c4  mov     rcx, rbx
0x1800147c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800147cc  nop
0x1800147cd  lea     rcx, [rsp+2D8h+var_268]
0x1800147d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147d7  nop
0x1800147d8  lea     rcx, [rsp+2D8h+var_288]
0x1800147dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800147e2  mov     rax, rbx
0x1800147e5  jmp     loc_1800148A9
0x1800147ea  mov     rcx, rsi
0x1800147ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800147f2  mov     [rsp+2D8h+bIgnoreCase], 1; bIgnoreCase
0x1800147fa  mov     r9d, r14d; cchCount2
0x1800147fd  lea     r8, [rsp+2D8h+TargetPath]; lpString2
0x180014805  mov     edx, r14d; cchCount1
0x180014808  mov     rcx, rax; lpString1
0x18001480b  call    cs:__imp_CompareStringOrdinal
0x180014811  cmp     eax, 2
0x180014814  jnz     short loc_18001484A
0x180014816  mov     rcx, rsi
0x180014819  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001481e  lea     r8, [rax+r14*2]
0x180014822  lea     rdx, [rsp+2D8h+var_268]
0x180014827  mov     rcx, rbx
0x18001482a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18001482f  nop
0x180014830  lea     rcx, [rsp+2D8h+var_268]
0x180014835  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001483a  nop
0x18001483b  lea     rcx, [rsp+2D8h+var_288]
0x180014840  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014845  mov     rax, rbx
0x180014848  jmp     short loc_1800148A9
0x18001484a  cmp     edi, r15d
0x18001484d  jnb     short loc_180014874
0x18001484f  mov     edx, edi
0x180014851  inc     edi
0x180014853  lea     rcx, [rsp+2D8h+var_288]
0x180014858  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001485d  cmp     [rax+rdx*2], r12w
0x180014862  jnz     short loc_18001484A
0x180014864  cmp     edi, r15d
0x180014867  jnb     short loc_180014874
0x180014869  cmp     [rax+rdi*2], r12w
0x18001486e  jnz     loc_18001475B
0x180014874  lea     rcx, [rsp+2D8h+var_268]
0x180014879  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001487e  nop
0x18001487f  mov     rdx, rsi
0x180014882  mov     rcx, rbx
0x180014885  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001488a  nop
0x18001488b  lea     rcx, [rsp+2D8h+var_288]
0x180014890  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014895  mov     rax, rbx
0x180014898  jmp     short loc_1800148A9
0x18001489a  lea     rcx, [rsp+2D8h+var_288]
0x18001489f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800148a4  mov     rax, [rsp+2D8h+var_2A8]
0x1800148a9  mov     rcx, [rsp+2D8h+var_38]
0x1800148b1  xor     rcx, rsp; StackCookie
0x1800148b4  call    __security_check_cookie
0x1800148b9  mov     rbx, [rsp+2D8h+arg_10]
0x1800148c1  add     rsp, 2B0h
0x1800148c8  pop     r15
0x1800148ca  pop     r14
0x1800148cc  pop     r12
0x1800148ce  pop     rdi
0x1800148cf  pop     rsi
0x1800148d0  retn
```
