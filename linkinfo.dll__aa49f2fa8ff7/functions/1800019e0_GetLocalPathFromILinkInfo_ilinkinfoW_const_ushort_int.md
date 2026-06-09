# GetLocalPathFromILinkInfo(_ilinkinfoW const *,ushort *,int)

- ea: `0x1800019e0`
- end: `0x180001acc`
- name: `?GetLocalPathFromILinkInfo@@YAXPEBU_ilinkinfoW@@PEAGH@Z`
- size: `236`
- prototype: `void __fastcall(const CHAR *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001840`
- `0x180004eb0`

## callees

- `0x1800019e0`
- `0x180001ae0`
- `0x180001bd0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001a39`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001a73`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001a39`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001a73`

## pseudocode

```c
void __fastcall GetLocalPathFromILinkInfo(const CHAR *a1, unsigned __int16 *a2)
{
  WCHAR *v4; // rsi
  unsigned __int16 *v5; // rbp
  WCHAR WideCharStr[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR lpWideCharStr[264]; // [rsp+240h] [rbp-238h] BYREF

  if ( *((_DWORD *)a1 + 1) == 28 )
  {
    v4 = WideCharStr;
    MultiByteToWideChar(0, 0, &a1[*((unsigned int *)a1 + 4)], -1, WideCharStr, 260);
    v5 = lpWideCharStr;
    MultiByteToWideChar(0, 0, &a1[*((unsigned int *)a1 + 6)], -1, lpWideCharStr, 260);
  }
  else
  {
    v4 = (WCHAR *)&a1[*((unsigned int *)a1 + 7)];
    v5 = (unsigned __int16 *)&a1[*((unsigned int *)a1 + 8)];
  }
  StringCchCopyW(a2, 0x104u, v4);
  CatPath(a2, v5);
}

```

## disassembly

```asm
0x1800019e0  mov     [rsp+arg_10], rbx
0x1800019e5  push    rbp
0x1800019e6  push    rsi
0x1800019e7  push    rdi
0x1800019e8  sub     rsp, 460h
0x1800019ef  mov     rax, cs:__security_cookie
0x1800019f6  xor     rax, rsp
0x1800019f9  mov     [rsp+478h+var_28], rax
0x180001a01  cmp     dword ptr [rcx+4], 1Ch
0x180001a05  mov     rdi, rdx
0x180001a08  mov     rbx, rcx
0x180001a0b  jnz     loc_180001ABE
0x180001a11  mov     r8d, [rcx+10h]
0x180001a15  lea     rax, [rsp+478h+WideCharStr]
0x180001a1a  add     r8, rcx; lpMultiByteStr
0x180001a1d  mov     [rsp+478h+cchWideChar], 104h; cchWideChar
0x180001a25  xor     ecx, ecx; CodePage
0x180001a27  mov     [rsp+478h+lpWideCharStr], rax; lpWideCharStr
0x180001a2c  xor     edx, edx; dwFlags
0x180001a2e  lea     rsi, [rsp+478h+WideCharStr]
0x180001a33  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180001a39  call    cs:__imp_MultiByteToWideChar
0x180001a40  nop     dword ptr [rax+rax+00h]
0x180001a45  mov     r8d, [rbx+18h]
0x180001a49  lea     rax, [rsp+478h+var_238]
0x180001a51  add     r8, rbx; lpMultiByteStr
0x180001a54  mov     [rsp+478h+cchWideChar], 104h; cchWideChar
0x180001a5c  xor     edx, edx; dwFlags
0x180001a5e  mov     [rsp+478h+lpWideCharStr], rax; lpWideCharStr
0x180001a63  xor     ecx, ecx; CodePage
0x180001a65  lea     rbp, [rsp+478h+var_238]
0x180001a6d  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180001a73  call    cs:__imp_MultiByteToWideChar
0x180001a7a  nop     dword ptr [rax+rax+00h]
0x180001a7f  mov     r8, rsi; unsigned __int16 *
0x180001a82  mov     edx, 104h; unsigned __int64
0x180001a87  mov     rcx, rdi; unsigned __int16 *
0x180001a8a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001a8f  mov     rdx, rbp; unsigned __int16 *
0x180001a92  mov     rcx, rdi; unsigned __int16 *
0x180001a95  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x180001a9a  mov     rcx, [rsp+478h+var_28]
0x180001aa2  xor     rcx, rsp; StackCookie
0x180001aa5  call    __security_check_cookie
0x180001aaa  mov     rbx, [rsp+478h+arg_10]
0x180001ab2  add     rsp, 460h
0x180001ab9  pop     rdi
0x180001aba  pop     rsi
0x180001abb  pop     rbp
0x180001abc  retn
0x180001abe  mov     esi, [rcx+1Ch]
0x180001ac1  mov     ebp, [rcx+20h]
0x180001ac4  add     rsi, rbx
0x180001ac7  add     rbp, rbx
0x180001aca  jmp     short loc_180001A7F
```
