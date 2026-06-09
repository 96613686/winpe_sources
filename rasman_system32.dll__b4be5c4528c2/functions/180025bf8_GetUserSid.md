# GetUserSid

- ea: `0x180025bf8`
- end: `0x180025de6`
- name: `GetUserSid`
- size: `494`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800030d0`
- `0x18001c280`
- `0x18001d770`

## callees

- `0x180021b14`
- `0x1800254c4`
- `0x1800254e0`
- `0x180025798`
- `0x180025bf8`
- `0x180026f3c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025d8f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025cbf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025cbf`
- `rtutils!TracePrintfExA` at `0x180025d79`
- `rtutils!TracePrintfExA` at `0x180025d79`

## string_xrefs

- `0x180025d6d`: `GetUserSid: returning %d `

## pseudocode

```c
__int64 __fastcall GetUserSid(__int64 a1)
{
  LPCWSTR v2; // rdi
  unsigned int CurrentToken; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int SidFromToken; // eax
  LPCWSTR lpString; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 5000);
  }
  v2 = 0;
  lpString = 0;
  hObject = 0;
  CurrentToken = GetCurrentToken(&hObject);
  v4 = CurrentToken;
  if ( CurrentToken )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 30;
LABEL_10:
      v7 = CurrentToken;
LABEL_11:
      WPP_SF_d(v5[2], v6, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v7);
    }
  }
  else
  {
    SidFromToken = GetSidFromToken(hObject, (HGLOBAL *)&lpString);
    v4 = SidFromToken;
    if ( SidFromToken )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, SidFromToken);
      }
      v2 = lpString;
    }
    else
    {
      v2 = lpString;
      if ( (unsigned int)lstrlenW(lpString) < 0x9C4 )
      {
        CurrentToken = StringCchCopyWrapW(a1, 2500, v2);
        v4 = CurrentToken;
        if ( CurrentToken )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v6 = 32;
            goto LABEL_10;
          }
        }
      }
      else
      {
        v4 = 603;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 31;
          v7 = 603;
          goto LABEL_11;
        }
      }
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetUserSid: returning %d ", v4);
  if ( hObject )
    CloseHandle(hObject);
  Free0(v2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180025bf8  mov     [rsp+arg_0], rbx
0x180025bfd  mov     [rsp+arg_8], rsi
0x180025c02  push    rdi
0x180025c03  push    r14
0x180025c05  push    r15
0x180025c07  sub     rsp, 20h
0x180025c0b  mov     rsi, rcx
0x180025c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c15  lea     r14, WPP_GLOBAL_Control
0x180025c1c  lea     r15, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x180025c23  cmp     rcx, r14
0x180025c26  jz      short loc_180025C4B
0x180025c28  test    byte ptr [rcx+1Ch], 4
0x180025c2c  jz      short loc_180025C4B
0x180025c2e  cmp     byte ptr [rcx+19h], 6
0x180025c32  jb      short loc_180025C4B
0x180025c34  mov     rcx, [rcx+10h]
0x180025c38  mov     edx, 1Dh
0x180025c3d  mov     r9d, 1388h
0x180025c43  mov     r8, r15
0x180025c46  call    WPP_SF_d
0x180025c4b  xor     edi, edi
0x180025c4d  lea     rcx, [rsp+38h+hObject]; TokenHandle
0x180025c52  mov     [rsp+38h+lpString], rdi
0x180025c57  mov     [rsp+38h+hObject], rdi
0x180025c5c  call    GetCurrentToken
0x180025c61  mov     ebx, eax
0x180025c63  test    eax, eax
0x180025c65  jz      short loc_180025CA2
0x180025c67  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c6e  cmp     rcx, r14
0x180025c71  jz      loc_180025D5F
0x180025c77  test    byte ptr [rcx+1Ch], 4
0x180025c7b  jz      loc_180025D5F
0x180025c81  cmp     byte ptr [rcx+19h], 2
0x180025c85  jb      loc_180025D5F
0x180025c8b  lea     edx, [rdi+1Eh]
0x180025c8e  mov     r9d, eax
0x180025c91  mov     rcx, [rcx+10h]
0x180025c95  mov     r8, r15
0x180025c98  call    WPP_SF_d
0x180025c9d  jmp     loc_180025D5F
0x180025ca2  mov     rcx, [rsp+38h+hObject]; TokenHandle
0x180025ca7  lea     rdx, [rsp+38h+lpString]
0x180025cac  call    GetSidFromToken
0x180025cb1  mov     ebx, eax
0x180025cb3  test    eax, eax
0x180025cb5  jnz     short loc_180025D2E
0x180025cb7  mov     rdi, [rsp+38h+lpString]
0x180025cbc  mov     rcx, rdi; lpString
0x180025cbf  call    cs:__imp_lstrlenW
0x180025cc6  nop     dword ptr [rax+rax+00h]
0x180025ccb  mov     edx, 9C4h
0x180025cd0  cmp     eax, edx
0x180025cd2  jb      short loc_180025CFB
0x180025cd4  mov     ebx, 25Bh
0x180025cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ce0  cmp     rcx, r14
0x180025ce3  jz      short loc_180025D5F
0x180025ce5  test    byte ptr [rcx+1Ch], 4
0x180025ce9  jz      short loc_180025D5F
0x180025ceb  cmp     byte ptr [rcx+19h], 2
0x180025cef  jb      short loc_180025D5F
0x180025cf1  mov     edx, 1Fh
0x180025cf6  mov     r9d, ebx
0x180025cf9  jmp     short loc_180025C91
0x180025cfb  mov     r8, rdi
0x180025cfe  mov     rcx, rsi
0x180025d01  call    StringCchCopyWrapW
0x180025d06  mov     ebx, eax
0x180025d08  test    eax, eax
0x180025d0a  jz      short loc_180025D5F
0x180025d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d13  cmp     rcx, r14
0x180025d16  jz      short loc_180025D5F
0x180025d18  test    byte ptr [rcx+1Ch], 4
0x180025d1c  jz      short loc_180025D5F
0x180025d1e  cmp     byte ptr [rcx+19h], 2
0x180025d22  jb      short loc_180025D5F
0x180025d24  mov     edx, 20h ; ' '
0x180025d29  jmp     loc_180025C8E
0x180025d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d35  cmp     rcx, r14
0x180025d38  jz      short loc_180025D5A
0x180025d3a  test    byte ptr [rcx+1Ch], 4
0x180025d3e  jz      short loc_180025D5A
0x180025d40  cmp     byte ptr [rcx+19h], 2
0x180025d44  jb      short loc_180025D5A
0x180025d46  mov     rcx, [rcx+10h]
0x180025d4a  mov     edx, 21h ; '!'
0x180025d4f  mov     r9d, eax
0x180025d52  mov     r8, r15
0x180025d55  call    WPP_SF_d
0x180025d5a  mov     rdi, [rsp+38h+lpString]
0x180025d5f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025d65  cmp     ecx, 0FFFFFFFFh
0x180025d68  jz      short loc_180025D85
0x180025d6a  mov     r9d, ebx
0x180025d6d  lea     r8, aGetusersidRetu; "GetUserSid: returning %d "
0x180025d74  mov     edx, 0Ch; dwFlags
0x180025d79  call    cs:__imp_TracePrintfExA
0x180025d80  nop     dword ptr [rax+rax+00h]
0x180025d85  mov     rcx, [rsp+38h+hObject]; hObject
0x180025d8a  test    rcx, rcx
0x180025d8d  jz      short loc_180025D9B
0x180025d8f  call    cs:__imp_CloseHandle
0x180025d96  nop     dword ptr [rax+rax+00h]
0x180025d9b  mov     rcx, rdi
0x180025d9e  call    Free0
0x180025da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180025daa  cmp     rcx, r14
0x180025dad  jz      short loc_180025DCF
0x180025daf  test    byte ptr [rcx+1Ch], 4
0x180025db3  jz      short loc_180025DCF
0x180025db5  cmp     byte ptr [rcx+19h], 6
0x180025db9  jb      short loc_180025DCF
0x180025dbb  mov     rcx, [rcx+10h]
0x180025dbf  mov     edx, 22h ; '"'
0x180025dc4  mov     r9d, ebx
0x180025dc7  mov     r8, r15
0x180025dca  call    WPP_SF_d
0x180025dcf  mov     rsi, [rsp+38h+arg_8]
0x180025dd4  mov     eax, ebx
0x180025dd6  mov     rbx, [rsp+38h+arg_0]
0x180025ddb  add     rsp, 20h
0x180025ddf  pop     r15
0x180025de1  pop     r14
0x180025de3  pop     rdi
0x180025de4  retn
```
