# DeleteOneFileCB(void *,HINTPROCINFO *,void *,int *)

- ea: `0x180012e80`
- end: `0x180012f22`
- name: `?DeleteOneFileCB@@YAJPEAXPEAUHINTPROCINFO@@0PEAH@Z`
- size: `162`
- prototype: `__int64 __fastcall(HINTERNET hConnect, struct HINTPROCINFO *, void *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180002240`
- `0x180012e80`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180012ed0`
- `SHLWAPI!__imp_SHUnicodeToAnsiCP` at `0x180012ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012eea`
- `WININET!FtpDeleteFileA` at `0x180012ee0`
- `WININET!FtpDeleteFileA` at `0x180012ee0`

## pseudocode

```c
__int64 __fastcall DeleteOneFileCB(HINTERNET hConnect, struct HINTPROCINFO *a2, _QWORD *a3, int *a4)
{
  __int64 v5; // rax
  unsigned int v6; // ebx
  signed int LastError; // eax
  CHAR szFileName[272]; // [rsp+20h] [rbp-128h] BYREF

  v5 = *(_QWORD *)(*(_QWORD *)a2 + 16LL);
  if ( v5 )
    LODWORD(v5) = *(_DWORD *)(v5 + 196);
  SHUnicodeToAnsiCP((_DWORD)v5 != 0 ? 0xFDE9 : 0, a3[2], szFileName, 260);
  v6 = 0;
  if ( !FtpDeleteFileA(hConnect, szFileName) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x180012e80  mov     [rsp+arg_8], rbx
0x180012e85  push    rdi
0x180012e86  sub     rsp, 140h
0x180012e8d  mov     rax, cs:__security_cookie
0x180012e94  xor     rax, rsp
0x180012e97  mov     [rsp+148h+var_18], rax
0x180012e9f  mov     rax, [rdx]
0x180012ea2  mov     r10, r8
0x180012ea5  mov     rdi, rcx
0x180012ea8  mov     rax, [rax+10h]
0x180012eac  test    rax, rax
0x180012eaf  jz      short loc_180012EB7
0x180012eb1  mov     eax, [rax+0C4h]
0x180012eb7  mov     rdx, [r10+10h]
0x180012ebb  lea     r8, [rsp+148h+szFileName]
0x180012ec0  neg     eax
0x180012ec2  mov     r9d, 104h
0x180012ec8  sbb     ecx, ecx
0x180012eca  and     ecx, 0FDE9h
0x180012ed0  call    cs:__imp_SHUnicodeToAnsiCP
0x180012ed6  lea     rdx, [rsp+148h+szFileName]; lpszFileName
0x180012edb  mov     rcx, rdi; hConnect
0x180012ede  xor     ebx, ebx
0x180012ee0  call    cs:__imp_FtpDeleteFileA
0x180012ee6  test    eax, eax
0x180012ee8  jnz     short loc_180012EFF
0x180012eea  call    cs:__imp_GetLastError
0x180012ef0  mov     ebx, eax
0x180012ef2  test    eax, eax
0x180012ef4  jle     short loc_180012EFF
0x180012ef6  movzx   ebx, ax
0x180012ef9  or      ebx, 80070000h
0x180012eff  mov     eax, ebx
0x180012f01  mov     rcx, [rsp+148h+var_18]
0x180012f09  xor     rcx, rsp; StackCookie
0x180012f0c  call    __security_check_cookie
0x180012f11  mov     rbx, [rsp+148h+arg_8]
0x180012f19  add     rsp, 140h
0x180012f20  pop     rdi
0x180012f21  retn
```
