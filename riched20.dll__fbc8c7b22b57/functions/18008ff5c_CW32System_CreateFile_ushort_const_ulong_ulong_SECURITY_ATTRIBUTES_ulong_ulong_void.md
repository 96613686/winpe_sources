# CW32System::CreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18008ff5c`
- end: `0x18009001b`
- name: `?CreateFile@CW32System@@SAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `191`
- prototype: `void *__usercall@<rax>(const unsigned __int16 *@<rcx>, DWORD dwDesiredAccess@<edx>, DWORD dwShareMode@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800432e0`
- `0x180086110`

## callees

- `0x18008f3e4`
- `0x18008ff5c`
- `0x1800903d4`
- `0x180093c00`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18008ffa6`
- `KERNEL32!CreateFileW` at `0x18008ffa6`
- `KERNEL32!CreateFileA` at `0x18008ffe3`
- `KERNEL32!CreateFileA` at `0x18008ffe3`

## pseudocode

```c
HANDLE __fastcall CW32System::CreateFile(
        const unsigned __int16 *a1,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition)
{
  HANDLE FileA; // rbx
  LPCSTR lpFileName[68]; // [rsp+40h] [rbp-248h] BYREF

  if ( CW32System::_dwPlatformId != 1 )
    return CreateFileW(a1, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, 0x110000u, 0);
  CStrIn::CStrIn((CStrIn *)lpFileName, a1, dwShareMode);
  FileA = CreateFileA(lpFileName[0], dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, 0x110000u, 0);
  CConvertStr::Free((CConvertStr *)lpFileName);
  return FileA;
}

```

## disassembly

```asm
0x18008ff5c  push    rbx
0x18008ff5e  push    rsi
0x18008ff5f  push    rdi
0x18008ff60  sub     rsp, 270h
0x18008ff67  mov     rax, cs:__security_cookie
0x18008ff6e  xor     rax, rsp
0x18008ff71  mov     [rsp+288h+var_28], rax
0x18008ff79  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18008ff80  mov     edi, r8d
0x18008ff83  mov     esi, [rsp+288h+arg_20]
0x18008ff8a  mov     ebx, edx
0x18008ff8c  jz      short loc_18008FFB4
0x18008ff8e  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18008ff97  xor     r9d, r9d; lpSecurityAttributes
0x18008ff9a  mov     [rsp+288h+dwFlagsAndAttributes], 110000h; dwFlagsAndAttributes
0x18008ffa2  mov     [rsp+288h+dwCreationDisposition], esi; dwCreationDisposition
0x18008ffa6  call    cs:__imp_CreateFileW
0x18008ffad  nop     dword ptr [rax+rax+00h]
0x18008ffb2  jmp     short loc_18008FFFF
0x18008ffb4  mov     rdx, rcx; unsigned __int16 *
0x18008ffb7  lea     rcx, [rsp+288h+lpFileName]; this
0x18008ffbc  call    ??0CStrIn@@QEAA@PEBGI@Z; CStrIn::CStrIn(ushort const *,uint)
0x18008ffc1  mov     rcx, [rsp+288h+lpFileName]; lpFileName
0x18008ffc6  xor     r9d, r9d; lpSecurityAttributes
0x18008ffc9  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18008ffd2  mov     r8d, edi; dwShareMode
0x18008ffd5  mov     [rsp+288h+dwFlagsAndAttributes], 110000h; dwFlagsAndAttributes
0x18008ffdd  mov     edx, ebx; dwDesiredAccess
0x18008ffdf  mov     [rsp+288h+dwCreationDisposition], esi; dwCreationDisposition
0x18008ffe3  call    cs:__imp_CreateFileA
0x18008ffea  nop     dword ptr [rax+rax+00h]
0x18008ffef  lea     rcx, [rsp+288h+lpFileName]; this
0x18008fff4  mov     rbx, rax
0x18008fff7  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18008fffc  mov     rax, rbx
0x18008ffff  mov     rcx, [rsp+288h+var_28]
0x180090007  xor     rcx, rsp; StackCookie
0x18009000a  call    __security_check_cookie
0x18009000f  add     rsp, 270h
0x180090016  pop     rdi
0x180090017  pop     rsi
0x180090018  pop     rbx
0x180090019  retn
```
