# AslEnvGetSysNativeDirPathForGuestBuf

- ea: `0x1407369c8`
- end: `0x140736af7`
- name: `AslEnvGetSysNativeDirPathForGuestBuf`
- size: `303`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PWSTR pszDest@<rcx>, size_t cchDest@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140824840`

## callees

- `0x1402dc448`
- `0x1406d9d70`
- `0x1406f4880`
- `0x1407369c8`
- `0x1408270c8`
- `0x1408273c4`
- `0x14097d158`
- `0x140afe014`

## string_xrefs

- `0x140736a9b`: `RtlStringCchCopyW failed [%x]`
- `0x140736a43`: `AslPathToSystemPathBuf failed [%x]`
- `0x140736a76`: `AslPathCombine failed [%x]`
- `0x140736aa8`: `AslEnvGetSysNativeDirPathForGuestBuf`

## pseudocode

```c
__int64 __fastcall AslEnvGetSysNativeDirPathForGuestBuf(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        _WORD *a3,
        __int16 a4,
        _WORD *a5)
{
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  int v12; // r8d
  NTSTATUS v14; // [rsp+20h] [rbp-C8h]
  wchar_t pszSrc[64]; // [rsp+30h] [rbp-B8h] BYREF

  memset_0(pszSrc, 0, sizeof(pszSrc));
  *pszDest = 0;
  if ( a5 && *a5 != a4 )
  {
    v9 = AslPathToSystemPathBuf(pszSrc, 0x40u, L"\\SysNative");
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = "AslPathToSystemPathBuf failed [%x]";
      v12 = 1847;
LABEL_11:
      v14 = v9;
      AslLogCallPrintf(1, (unsigned int)"AslEnvGetSysNativeDirPathForGuestBuf", v12, (_DWORD)v11, v14);
      return v10;
    }
    if ( a3 && *a3 )
    {
      v9 = AslPathCombine(pszSrc, a3, pszDest, cchDest);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "AslPathCombine failed [%x]";
        v12 = 1857;
        goto LABEL_11;
      }
    }
    else
    {
      v9 = RtlStringCchCopyW(pszDest, cchDest, pszSrc);
      v10 = v9;
      if ( v9 < 0 )
      {
        v11 = "RtlStringCchCopyW failed [%x]";
        v12 = 1865;
        goto LABEL_11;
      }
    }
    return v10;
  }
  return AslEnvGetSystem32DirPathBuf(pszDest, cchDest, (__int64)a5);
}

```

## disassembly

```asm
0x1407369c8  push    rbx
0x1407369ca  push    rbp
0x1407369cb  push    rsi
0x1407369cc  push    rdi
0x1407369cd  push    r14
0x1407369cf  sub     rsp, 0C0h
0x1407369d6  mov     rax, cs:__security_cookie
0x1407369dd  xor     rax, rsp
0x1407369e0  mov     [rsp+0E8h+var_38], rax
0x1407369e8  mov     rdi, r8
0x1407369eb  mov     rbp, rdx
0x1407369ee  mov     rsi, rcx
0x1407369f1  xor     edx, edx; Val
0x1407369f3  mov     r8d, 80h; Size
0x1407369f9  lea     rcx, [rsp+0E8h+pszSrc]; void *
0x1407369fe  movzx   ebx, r9w
0x140736a02  call    memset_0
0x140736a07  mov     rax, [rsp+0E8h+arg_20]
0x140736a0f  xor     r14d, r14d
0x140736a12  mov     [rsi], r14w
0x140736a16  test    rax, rax
0x140736a19  jz      loc_140736AC1
0x140736a1f  cmp     [rax], bx
0x140736a22  jz      loc_140736AC1
0x140736a28  lea     r8, aSysnative; "\\SysNative"
0x140736a2f  lea     edx, [r14+40h]; cchDest
0x140736a33  lea     rcx, [rsp+0E8h+pszSrc]; pszDest
0x140736a38  call    AslPathToSystemPathBuf
0x140736a3d  mov     ebx, eax
0x140736a3f  test    eax, eax
0x140736a41  jns     short loc_140736A52
0x140736a43  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x140736a4a  mov     r8d, 737h
0x140736a50  jmp     short loc_140736AA8
0x140736a52  test    rdi, rdi
0x140736a55  jz      short loc_140736A85
0x140736a57  cmp     [rdi], r14w
0x140736a5b  jz      short loc_140736A85
0x140736a5d  mov     r9, rbp
0x140736a60  lea     rcx, [rsp+0E8h+pszSrc]
0x140736a65  mov     r8, rsi
0x140736a68  mov     rdx, rdi
0x140736a6b  call    AslPathCombine
0x140736a70  mov     ebx, eax
0x140736a72  test    eax, eax
0x140736a74  jns     short loc_140736ABD
0x140736a76  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140736a7d  mov     r8d, 741h
0x140736a83  jmp     short loc_140736AA8
0x140736a85  lea     r8, [rsp+0E8h+pszSrc]; pszSrc
0x140736a8a  mov     rdx, rbp; cchDest
0x140736a8d  mov     rcx, rsi; pszDest
0x140736a90  call    RtlStringCchCopyW
0x140736a95  mov     ebx, eax
0x140736a97  test    eax, eax
0x140736a99  jns     short loc_140736ABD
0x140736a9b  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140736aa2  mov     r8d, 749h
0x140736aa8  lea     rdx, aAslenvgetsysna; "AslEnvGetSysNativeDirPathForGuestBuf"
0x140736aaf  mov     [rsp+0E8h+var_C8], eax
0x140736ab3  mov     ecx, 1
0x140736ab8  call    AslLogCallPrintf
0x140736abd  mov     eax, ebx
0x140736abf  jmp     short loc_140736AD8
0x140736ac1  movzx   r9d, bx
0x140736ac5  mov     qword ptr [rsp+0E8h+var_C8], rax; __int64
0x140736aca  mov     r8, rdi
0x140736acd  mov     rdx, rbp; cchDest
0x140736ad0  mov     rcx, rsi; pszDest
0x140736ad3  call    AslEnvGetSystem32DirPathBuf
0x140736ad8  mov     rcx, [rsp+0E8h+var_38]
0x140736ae0  xor     rcx, rsp; StackCookie
0x140736ae3  call    __security_check_cookie
0x140736ae8  add     rsp, 0C0h
0x140736aef  pop     r14
0x140736af1  pop     rdi
0x140736af2  pop     rsi
0x140736af3  pop     rbp
0x140736af4  pop     rbx
0x140736af5  retn
```
