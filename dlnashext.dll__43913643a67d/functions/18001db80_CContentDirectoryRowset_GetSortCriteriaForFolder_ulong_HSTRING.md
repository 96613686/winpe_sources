# CContentDirectoryRowset::_GetSortCriteriaForFolder(ulong,HSTRING__ * *)

- ea: `0x18001db80`
- end: `0x18001dd0e`
- name: `?_GetSortCriteriaForFolder@CContentDirectoryRowset@@AEAAJKPEAPEAUHSTRING__@@@Z`
- size: `398`
- prototype: `int(CContentDirectoryRowset *__hidden this, unsigned int, HSTRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c744`
- `0x18001cc50`

## callees

- `0x18001049c`
- `0x18001b084`
- `0x18001d3ec`
- `0x18001db80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dc0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dc0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dbca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dbca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001dcea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001dcea`

## pseudocode

```c
__int64 __fastcall CContentDirectoryRowset::_GetSortCriteriaForFolder(HSTRING *this, int a2, HSTRING *a3)
{
  HRESULT String; // ebx
  PCNZWCH v6; // rsi
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v8; // rdi
  __int64 v9; // r15
  int i; // edi
  unsigned int j; // eax
  __int64 v12; // r14
  PCNZWCH sourceString; // [rsp+30h] [rbp-28h] BYREF
  UINT32 v15[2]; // [rsp+38h] [rbp-20h]
  __int64 v16; // [rsp+40h] [rbp-18h]
  UINT32 length; // [rsp+A8h] [rbp+50h] BYREF

  length = 0;
  sourceString = 0;
  String = 0;
  *(_QWORD *)v15 = 0;
  v6 = 0;
  v16 = 0;
  *a3 = 0;
  if ( a2 != 1 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(this[49], &length);
    v8 = L"object.container";
    if ( *StringRawBuffer )
      v8 = StringRawBuffer;
    while ( (unsigned int)String < 6 )
    {
      v9 = 2LL * (unsigned int)String;
      if ( CompareStringOrdinal(
             v8,
             length,
             *((LPCWCH *)&CContentDirectoryRowset::s_arrClassPrefixToSortCriteria + 2 * (unsigned int)String),
             -1,
             1) == 2 )
      {
        for ( i = dword_1800387A8[4 * String]; ; i = dword_1800387AC[2 * v9] )
        {
          if ( i != 1 && (i & a2) != 0 )
          {
            for ( j = 0; j < 3; ++j )
            {
              v12 = 2LL * j;
              if ( i == dword_180038778[4 * j] )
              {
                if ( !v6
                  || !*v6
                  || (String = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Concat(
                                 &sourceString,
                                 L","),
                      String >= 0) )
                {
                  String = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Concat(
                             &sourceString,
                             L"+");
                  if ( String >= 0 )
                  {
                    String = Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::Concat(
                               &sourceString,
                               *((_QWORD *)&CContentDirectoryRowset::s_arrSortCapabilities + v12));
                    if ( String >= 0 )
                    {
                      v6 = sourceString;
                      break;
                    }
                  }
                }
                goto LABEL_23;
              }
            }
          }
          if ( i == dword_1800387AC[2 * v9] )
            break;
        }
        break;
      }
      ++String;
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
    String = WindowsCreateString(sourceString, v15[0], a3);
  }
LABEL_23:
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&sourceString);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18001db80  push    rbp
0x18001db82  push    rbx
0x18001db83  push    rsi
0x18001db84  push    rdi
0x18001db85  push    r12
0x18001db87  push    r13
0x18001db89  push    r14
0x18001db8b  push    r15
0x18001db8d  mov     rbp, rsp
0x18001db90  sub     rsp, 58h
0x18001db94  xor     r14d, r14d
0x18001db97  mov     r12, r8
0x18001db9a  mov     [rbp+length], r14d
0x18001db9e  mov     r13d, edx
0x18001dba1  mov     [rbp+sourceString], r14
0x18001dba5  mov     ebx, r14d
0x18001dba8  mov     qword ptr [rbp+var_20], r14
0x18001dbac  mov     esi, r14d
0x18001dbaf  mov     [rbp+var_18], r14
0x18001dbb3  mov     [r8], r14
0x18001dbb6  cmp     edx, 1
0x18001dbb9  jz      loc_18001DCF2
0x18001dbbf  mov     rcx, [rcx+188h]; string
0x18001dbc6  lea     rdx, [rbp+length]; length
0x18001dbca  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dbd0  lea     rdi, aObjectContaine_4; "object.container"
0x18001dbd7  cmp     [rax], r14w
0x18001dbdb  cmovnz  rdi, rax
0x18001dbdf  lea     rax, __ImageBase
0x18001dbe6  cmp     ebx, 6
0x18001dbe9  jnb     loc_18001DCD7
0x18001dbef  mov     edx, [rbp+length]; cchCount1
0x18001dbf2  or      r9d, 0FFFFFFFFh; cchCount2
0x18001dbf6  mov     r15d, ebx
0x18001dbf9  mov     rcx, rdi; lpString1
0x18001dbfc  add     r15, r15
0x18001dbff  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18001dc07  mov     r8, ds:rva ?s_arrClassPrefixToSortCriteria@CContentDirectoryRowset@@0QBUContainerClassToSortCriteria@1@B[rax+r15*8]; lpString2
0x18001dc0f  call    cs:__imp_CompareStringOrdinal
0x18001dc15  cmp     eax, 2
0x18001dc18  jz      short loc_18001DC1E
0x18001dc1a  inc     ebx
0x18001dc1c  jmp     short loc_18001DBDF
0x18001dc1e  lea     rcx, __ImageBase
0x18001dc25  mov     edi, ds:rva dword_1800387A8[rcx+r15*8]
0x18001dc2d  cmp     edi, 1
0x18001dc30  jz      loc_18001DCC4
0x18001dc36  test    r13d, edi
0x18001dc39  jz      loc_18001DCC4
0x18001dc3f  mov     eax, r14d
0x18001dc42  cmp     eax, 3
0x18001dc45  jnb     short loc_18001DCC1
0x18001dc47  mov     r14d, eax
0x18001dc4a  add     r14, r14
0x18001dc4d  cmp     edi, ds:rva dword_180038778[rcx+r14*8]
0x18001dc55  jz      short loc_18001DC5B
0x18001dc57  inc     eax
0x18001dc59  jmp     short loc_18001DC42
0x18001dc5b  xor     eax, eax
0x18001dc5d  test    rsi, rsi
0x18001dc60  jz      short loc_18001DC7D
0x18001dc62  cmp     [rsi], ax
0x18001dc65  jz      short loc_18001DC7D
0x18001dc67  lea     rdx, asc_18003C008; ","
0x18001dc6e  lea     rcx, [rbp+sourceString]
0x18001dc72  call    ?Concat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Concat(ushort const *)
0x18001dc77  mov     ebx, eax
0x18001dc79  test    eax, eax
0x18001dc7b  js      short loc_18001DCF2
0x18001dc7d  lea     rdx, asc_18003C00C; "+"
0x18001dc84  lea     rcx, [rbp+sourceString]
0x18001dc88  call    ?Concat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Concat(ushort const *)
0x18001dc8d  mov     ebx, eax
0x18001dc8f  test    eax, eax
0x18001dc91  js      short loc_18001DCF2
0x18001dc93  lea     rdx, __ImageBase
0x18001dc9a  mov     rdx, ds:rva ?s_arrSortCapabilities@CContentDirectoryRowset@@0QBUUPnPElementToSortCapability@1@B[rdx+r14*8]; CContentDirectoryRowset::UPnPElementToSortCapability const near * const CContentDirectoryRowset::s_arrSortCapabilities ...
0x18001dca2  lea     rcx, [rbp+sourceString]
0x18001dca6  call    ?Concat@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::Concat(ushort const *)
0x18001dcab  xor     r14d, r14d
0x18001dcae  mov     ebx, eax
0x18001dcb0  test    eax, eax
0x18001dcb2  js      short loc_18001DCF2
0x18001dcb4  mov     rsi, [rbp+sourceString]
0x18001dcb8  lea     rcx, __ImageBase
0x18001dcbf  jmp     short loc_18001DCC4
0x18001dcc1  xor     r14d, r14d
0x18001dcc4  mov     eax, ds:rva dword_1800387AC[rcx+r15*8]
0x18001dccc  cmp     edi, eax
0x18001dcce  jz      short loc_18001DCD7
0x18001dcd0  mov     edi, eax
0x18001dcd2  jmp     loc_18001DC2D
0x18001dcd7  lea     rcx, [rbp+sourceString]
0x18001dcdb  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x18001dce0  mov     edx, [rbp+var_20]; length
0x18001dce3  mov     r8, r12; string
0x18001dce6  mov     rcx, [rbp+sourceString]; sourceString
0x18001dcea  call    cs:__imp_WindowsCreateString
0x18001dcf0  mov     ebx, eax
0x18001dcf2  lea     rcx, [rbp+sourceString]
0x18001dcf6  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x18001dcfb  mov     eax, ebx
0x18001dcfd  add     rsp, 58h
0x18001dd01  pop     r15
0x18001dd03  pop     r14
0x18001dd05  pop     r13
0x18001dd07  pop     r12
0x18001dd09  pop     rdi
0x18001dd0a  pop     rsi
0x18001dd0b  pop     rbx
0x18001dd0c  pop     rbp
0x18001dd0d  retn
```
