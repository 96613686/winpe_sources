# DfsGetSharePath

- ea: `0x14005858c`
- end: `0x140058644`
- name: `DfsGetSharePath`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x140028098`

## callees

- `0x14005858c`
- `0x140058ce0`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400585ee`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400585ee`
- `ntdll!RtlFreeUnicodeString` at `0x140058612`
- `ntdll!RtlFreeUnicodeString` at `0x140058612`
- `netutils!NetApiBufferFree` at `0x14005862a`
- `netutils!NetApiBufferFree` at `0x14005862a`
- `srvcli!NetShareGetInfo` at `0x1400585ca`
- `srvcli!NetShareGetInfo` at `0x1400585ca`

## pseudocode

```c
DWORD __fastcall DfsGetSharePath(WCHAR *a1, WCHAR *a2, __int64 a3)
{
  int v4; // eax
  DWORD result; // eax
  int v6; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+20h] [rbp-18h] BYREF
  LPBYTE bufptr; // [rsp+40h] [rbp+8h] BYREF

  bufptr = 0;
  NtPathName = 0;
  if ( !a1 || (v4 = 0, !*a1) )
    v4 = 1;
  if ( v4 )
    a1 = 0;
  result = NetShareGetInfo(a1, a2, 0x1F7u, &bufptr);
  if ( !result )
  {
    if ( RtlDosPathNameToNtPathName_U(*((PCWSTR *)bufptr + 5), &NtPathName, 0, 0) == 1 )
    {
      v6 = DfsCreateUnicodeString(a3, &NtPathName);
      RtlFreeUnicodeString(&NtPathName);
    }
    else
    {
      v6 = 8;
    }
    NetApiBufferFree(bufptr);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14005858c  mov     [rsp+arg_8], rbx
0x140058591  push    rdi
0x140058592  sub     rsp, 30h
0x140058596  xor     edi, edi
0x140058598  xorps   xmm0, xmm0
0x14005859b  mov     [rsp+38h+bufptr], rdi
0x1400585a0  mov     rbx, r8
0x1400585a3  movups  xmmword ptr [rsp+38h+NtPathName.Length], xmm0
0x1400585a8  test    rcx, rcx
0x1400585ab  jz      short loc_1400585B4
0x1400585ad  mov     eax, edi
0x1400585af  cmp     [rcx], di
0x1400585b2  jnz     short loc_1400585B9
0x1400585b4  mov     eax, 1
0x1400585b9  test    eax, eax
0x1400585bb  lea     r9, [rsp+38h+bufptr]; bufptr
0x1400585c0  mov     r8d, 1F7h; level
0x1400585c6  cmovnz  rcx, rdi; servername
0x1400585ca  call    cs:__imp_NetShareGetInfo
0x1400585d1  nop     dword ptr [rax+rax+00h]
0x1400585d6  test    eax, eax
0x1400585d8  jnz     short loc_140058638
0x1400585da  mov     rcx, [rsp+38h+bufptr]
0x1400585df  lea     rdx, [rsp+38h+NtPathName]; NtPathName
0x1400585e4  xor     r9d, r9d; DirectoryInfo
0x1400585e7  xor     r8d, r8d; NtFileNamePart
0x1400585ea  mov     rcx, [rcx+28h]; DosPathName
0x1400585ee  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400585f5  nop     dword ptr [rax+rax+00h]
0x1400585fa  cmp     al, 1
0x1400585fc  jnz     short loc_140058620
0x1400585fe  lea     rdx, [rsp+38h+NtPathName]
0x140058603  mov     rcx, rbx
0x140058606  call    DfsCreateUnicodeString
0x14005860b  lea     rcx, [rsp+38h+NtPathName]; UnicodeString
0x140058610  mov     ebx, eax
0x140058612  call    cs:__imp_RtlFreeUnicodeString
0x140058619  nop     dword ptr [rax+rax+00h]
0x14005861e  jmp     short loc_140058625
0x140058620  mov     ebx, 8
0x140058625  mov     rcx, [rsp+38h+bufptr]; Buffer
0x14005862a  call    cs:__imp_NetApiBufferFree
0x140058631  nop     dword ptr [rax+rax+00h]
0x140058636  mov     eax, ebx
0x140058638  mov     rbx, [rsp+38h+arg_8]
0x14005863d  add     rsp, 30h
0x140058641  pop     rdi
0x140058642  retn
```
