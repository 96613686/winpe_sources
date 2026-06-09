# CEventUrl::Invoke(void)

- ea: `0x180010b0c`
- end: `0x180010bc2`
- name: `?Invoke@CEventUrl@@QEBAXXZ`
- size: `182`
- prototype: `void __fastcall(CEventUrl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000af00`

## callees

- `0x180010b0c`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x180010b59`
- `KERNEL32!GetWindowsDirectoryW` at `0x180010b59`
- `SHELL32!ShellExecuteW` at `0x180010ba3`
- `SHELL32!ShellExecuteW` at `0x180010ba3`

## pseudocode

```c
void __fastcall CEventUrl::Invoke(CEventUrl *this)
{
  WCHAR *lpDirectory; // rax
  const WCHAR *v3; // r9
  WCHAR *v4; // r8
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  lpDirectory = 0;
  if ( *((_QWORD *)this + 126) )
  {
    if ( *((_DWORD *)this + 257) )
    {
      memset_0(Buffer, 0, 0x20Au);
      GetWindowsDirectoryW(Buffer, 0x104u);
      v3 = (const WCHAR *)((char *)this + 1032);
      if ( *((_QWORD *)this + 132) >= 8u )
        v3 = *(const WCHAR **)v3;
      lpDirectory = Buffer;
      v4 = &g_wszRedirectionProgram;
    }
    else
    {
      v4 = (WCHAR *)((char *)this + 992);
      if ( *((_QWORD *)this + 127) >= 8u )
        v4 = *(WCHAR **)v4;
      v3 = 0;
    }
    ShellExecuteW(0, 0, v4, v3, lpDirectory, 1);
  }
}

```

## disassembly

```asm
0x180010b0c  push    rbx
0x180010b0e  sub     rsp, 250h
0x180010b15  mov     rax, cs:__security_cookie
0x180010b1c  xor     rax, rsp
0x180010b1f  mov     [rsp+258h+var_18], rax
0x180010b27  xor     eax, eax
0x180010b29  mov     rbx, rcx
0x180010b2c  cmp     [rcx+3F0h], rax
0x180010b33  jz      short loc_180010BA9
0x180010b35  cmp     [rcx+404h], eax
0x180010b3b  jz      short loc_180010B7E
0x180010b3d  xor     edx, edx; Val
0x180010b3f  lea     rcx, [rsp+258h+Buffer]; void *
0x180010b44  mov     r8d, 20Ah; Size
0x180010b4a  call    memset_0
0x180010b4f  mov     edx, 104h; uSize
0x180010b54  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180010b59  call    cs:__imp_GetWindowsDirectoryW
0x180010b5f  lea     r9, [rbx+408h]
0x180010b66  cmp     qword ptr [r9+18h], 8
0x180010b6b  jb      short loc_180010B70
0x180010b6d  mov     r9, [r9]
0x180010b70  lea     rax, [rsp+258h+Buffer]
0x180010b75  lea     r8, ?g_wszRedirectionProgram@@3PAGA; ushort near * g_wszRedirectionProgram
0x180010b7c  jmp     short loc_180010B92
0x180010b7e  lea     r8, [rcx+3E0h]
0x180010b85  cmp     qword ptr [r8+18h], 8
0x180010b8a  jb      short loc_180010B8F
0x180010b8c  mov     r8, [r8]; lpFile
0x180010b8f  xor     r9d, r9d; lpParameters
0x180010b92  mov     [rsp+258h+nShowCmd], 1; nShowCmd
0x180010b9a  xor     edx, edx; lpOperation
0x180010b9c  xor     ecx, ecx; hwnd
0x180010b9e  mov     [rsp+258h+lpDirectory], rax; lpDirectory
0x180010ba3  call    cs:__imp_ShellExecuteW
0x180010ba9  mov     rcx, [rsp+258h+var_18]
0x180010bb1  xor     rcx, rsp; StackCookie
0x180010bb4  call    __security_check_cookie
0x180010bb9  add     rsp, 250h
0x180010bc0  pop     rbx
0x180010bc1  retn
```
