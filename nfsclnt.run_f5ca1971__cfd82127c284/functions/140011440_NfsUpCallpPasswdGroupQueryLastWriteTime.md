# NfsUpCallpPasswdGroupQueryLastWriteTime

- ea: `0x140011440`
- end: `0x1400114a5`
- name: `NfsUpCallpPasswdGroupQueryLastWriteTime`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140011614`
- `0x140011968`

## callees

- `0x140011440`
- `0x140018350`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x140011472`
- `KERNEL32!GetFileAttributesExW` at `0x140011472`
- `KERNEL32!GetLastError` at `0x14001147c`
- `KERNEL32!GetLastError` at `0x14001147c`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupQueryLastWriteTime(const WCHAR *a1, _QWORD *a2)
{
  unsigned int v3; // ecx
  __int128 FileInformation; // [rsp+20h] [rbp-38h] BYREF
  __int128 v6; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+40h] [rbp-18h]

  v7 = 0;
  FileInformation = 0;
  v6 = 0;
  if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &FileInformation) )
  {
    v3 = 0;
    *a2 = *(_QWORD *)((char *)&v6 + 4);
  }
  else
  {
    return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x140011440  push    rbx
0x140011442  sub     rsp, 50h
0x140011446  mov     rax, cs:__security_cookie
0x14001144d  xor     rax, rsp
0x140011450  mov     [rsp+58h+var_10], rax
0x140011455  xorps   xmm0, xmm0
0x140011458  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x14001145d  mov     rbx, rdx
0x140011460  xor     eax, eax
0x140011462  xor     edx, edx; fInfoLevelId
0x140011464  mov     [rsp+58h+var_18], eax
0x140011468  movups  [rsp+58h+FileInformation], xmm0
0x14001146d  movups  [rsp+58h+var_28], xmm0
0x140011472  call    cs:__imp_GetFileAttributesExW
0x140011478  test    eax, eax
0x14001147a  jnz     short loc_140011486
0x14001147c  call    cs:__imp_GetLastError
0x140011482  mov     ecx, eax
0x140011484  jmp     short loc_140011490
0x140011486  mov     rax, qword ptr [rsp+58h+var_28+4]
0x14001148b  xor     ecx, ecx
0x14001148d  mov     [rbx], rax
0x140011490  mov     eax, ecx
0x140011492  mov     rcx, [rsp+58h+var_10]
0x140011497  xor     rcx, rsp; StackCookie
0x14001149a  call    __security_check_cookie
0x14001149f  add     rsp, 50h
0x1400114a3  pop     rbx
0x1400114a4  retn
```
