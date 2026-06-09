# DLNACommon::GetDefaultFriendlyName(HSTRING__ * *)

- ea: `0x1800330bc`
- end: `0x180033257`
- name: `?GetDefaultFriendlyName@DLNACommon@@YAJPEAPEAUHSTRING__@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(HSTRING *string, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800304a8`

## callees

- `0x18000d9bc`
- `0x180014a00`
- `0x18001bbe0`
- `0x18001bfc0`
- `0x18002b5d8`
- `0x18003308c`
- `0x1800330bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003312a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180033172`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003312a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180033172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331a5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18003319b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18003319b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800331e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800331e2`

## pseudocode

```c
__int64 __fastcall DLNACommon::GetDefaultFriendlyName(HSTRING *string, HSTRING *a2)
{
  __int64 v3; // rdx
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // ebx
  BOOL ComputerNameW; // eax
  WCHAR *Buffer; // rax
  signed int LastError; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  const WCHAR *v13; // rax
  UINT32 v14; // edx
  __int64 v15; // rax
  __int64 v16; // r10
  int v18; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+34h] [rbp-1Ch]
  int v20; // [rsp+3Ch] [rbp-14h]
  __int64 v21; // [rsp+40h] [rbp-10h]
  DWORD nSize; // [rsp+68h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ba5befb4ba033b5c17730f7d3136e8a4_Traceguids);
  v18 &= 0xFFFFFFF8;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  nSize = 0;
  if ( GetComputerNameExW(ComputerNamePhysicalDnsHostname, 0, &nSize) )
  {
    v3 = 16;
    nSize = 16;
  }
  else
  {
    if ( GetLastError() != 234 )
    {
      Buffer = (WCHAR *)CMFBaseStringT<unsigned short>::GetBuffer(&v18, 15);
      if ( !Buffer )
        goto LABEL_9;
      nSize = 16;
      ComputerNameW = GetComputerNameW(Buffer, &nSize);
      goto LABEL_13;
    }
    v3 = nSize;
  }
  v4 = (WCHAR *)CMFBaseStringT<unsigned short>::GetBuffer(&v18, v3);
  if ( !v4 )
  {
LABEL_9:
    v7 = -2147024882;
    goto LABEL_19;
  }
  ComputerNameW = GetComputerNameExW(ComputerNamePhysicalDnsHostname, v4, &nSize);
LABEL_13:
  if ( ComputerNameW )
  {
    CMFBaseStringT<unsigned short>::ReleaseBuffer(&v18, nSize);
    v12 = HIDWORD(v19);
    if ( (int)v19 < 0 )
      v12 = 0;
    v13 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(&v18, v12, v11);
    v7 = WindowsCreateString(v13, v14, string);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_19:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v7 >> 31) & 0xFFFFFFFD) + 5 )
  {
    v15 = CMFBaseStringT<unsigned short>::PContents(&v18, v5, v6);
    WPP_SF_dS(*(_QWORD *)(v16 + 16), 16, (unsigned int)WPP_ba5befb4ba033b5c17730f7d3136e8a4_Traceguids, v7, v15);
  }
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800330bc  mov     [rsp-8+arg_0], rbx
0x1800330c1  mov     [rsp-8+arg_10], r12
0x1800330c6  push    rbp
0x1800330c7  mov     rbp, rsp
0x1800330ca  sub     rsp, 50h
0x1800330ce  mov     rbx, rcx
0x1800330d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330d8  lea     r12, WPP_GLOBAL_Control
0x1800330df  cmp     rcx, r12
0x1800330e2  jz      short loc_1800330FF
0x1800330e4  test    byte ptr [rcx+1Ch], 2
0x1800330e8  jz      short loc_1800330FF
0x1800330ea  mov     rcx, [rcx+10h]
0x1800330ee  lea     r8, WPP_ba5befb4ba033b5c17730f7d3136e8a4_Traceguids
0x1800330f5  mov     edx, 0Fh
0x1800330fa  call    WPP_SF_
0x1800330ff  and     [rbp+var_20], 0FFFFFFF8h
0x180033103  lea     r8, [rbp+nSize]; nSize
0x180033107  xor     edx, edx; lpBuffer
0x180033109  mov     [rbp+var_1C], 0
0x180033111  mov     [rbp+var_10], 0
0x180033119  mov     [rbp+var_14], 0
0x180033120  mov     [rbp+nSize], 0
0x180033127  lea     ecx, [rdx+5]; NameType
0x18003312a  call    cs:__imp_GetComputerNameExW
0x180033130  test    eax, eax
0x180033132  jz      short loc_18003313E
0x180033134  mov     edx, 10h
0x180033139  mov     [rbp+nSize], edx
0x18003313c  jmp     short loc_18003314E
0x18003313e  call    cs:__imp_GetLastError
0x180033144  cmp     eax, 0EAh
0x180033149  jnz     short loc_18003317A
0x18003314b  mov     edx, [rbp+nSize]
0x18003314e  lea     rcx, [rbp+var_20]
0x180033152  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x180033157  test    rax, rax
0x18003315a  jnz     short loc_180033166
0x18003315c  mov     ebx, 8007000Eh
0x180033161  jmp     loc_1800331EA
0x180033166  lea     r8, [rbp+nSize]; nSize
0x18003316a  mov     rdx, rax; lpBuffer
0x18003316d  mov     ecx, 5; NameType
0x180033172  call    cs:__imp_GetComputerNameExW
0x180033178  jmp     short loc_1800331A1
0x18003317a  mov     edx, 0Fh
0x18003317f  lea     rcx, [rbp+var_20]
0x180033183  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x180033188  test    rax, rax
0x18003318b  jz      short loc_18003315C
0x18003318d  lea     rdx, [rbp+nSize]; nSize
0x180033191  mov     [rbp+nSize], 10h
0x180033198  mov     rcx, rax; lpBuffer
0x18003319b  call    cs:__imp_GetComputerNameW
0x1800331a1  test    eax, eax
0x1800331a3  jnz     short loc_1800331BC
0x1800331a5  call    cs:__imp_GetLastError
0x1800331ab  mov     ebx, eax
0x1800331ad  test    eax, eax
0x1800331af  jle     short loc_1800331EA
0x1800331b1  movzx   ebx, ax
0x1800331b4  or      ebx, 80070000h
0x1800331ba  jmp     short loc_1800331EA
0x1800331bc  mov     edx, [rbp+nSize]
0x1800331bf  lea     rcx, [rbp+var_20]
0x1800331c3  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x1800331c8  mov     edx, dword ptr [rbp+var_1C+4]
0x1800331cb  lea     rcx, [rbp+var_20]
0x1800331cf  xor     eax, eax
0x1800331d1  cmp     dword ptr [rbp+var_1C], eax
0x1800331d4  cmovl   edx, eax
0x1800331d7  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800331dc  mov     rcx, rax; sourceString
0x1800331df  mov     r8, rbx; string
0x1800331e2  call    cs:__imp_WindowsCreateString
0x1800331e8  mov     ebx, eax
0x1800331ea  mov     r10, cs:WPP_GLOBAL_Control
0x1800331f1  cmp     r10, r12
0x1800331f4  jz      short loc_18003323C
0x1800331f6  test    byte ptr [r10+1Ch], 2
0x1800331fb  jz      short loc_18003323C
0x1800331fd  movzx   eax, byte ptr [r10+19h]
0x180033202  mov     r9d, ebx
0x180033205  sar     r9d, 1Fh
0x180033209  and     r9d, 0FFFFFFFDh
0x18003320d  add     r9d, 5
0x180033211  cmp     eax, r9d
0x180033214  jb      short loc_18003323C
0x180033216  lea     rcx, [rbp+var_20]
0x18003321a  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18003321f  mov     rcx, [r10+10h]
0x180033223  lea     r8, WPP_ba5befb4ba033b5c17730f7d3136e8a4_Traceguids
0x18003322a  mov     edx, 10h
0x18003322f  mov     [rsp+50h+var_30], rax
0x180033234  mov     r9d, ebx
0x180033237  call    WPP_SF_dS
0x18003323c  lea     rcx, [rbp+var_20]
0x180033240  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x180033245  mov     r12, [rsp+50h+arg_10]
0x18003324a  mov     eax, ebx
0x18003324c  mov     rbx, [rsp+50h+arg_0]
0x180033251  add     rsp, 50h
0x180033255  pop     rbp
0x180033256  retn
```
