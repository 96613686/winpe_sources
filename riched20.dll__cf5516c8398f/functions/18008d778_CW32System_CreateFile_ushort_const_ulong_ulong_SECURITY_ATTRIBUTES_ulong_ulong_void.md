# CW32System::CreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18008d778`
- end: `0x18008d82a`
- name: `?CreateFile@CW32System@@SAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `178`
- prototype: `void *__usercall@<rax>(const unsigned __int16 *@<rcx>, DWORD dwDesiredAccess@<edx>, DWORD dwShareMode@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180042260`
- `0x180083b80`

## callees

- `0x18008cc4c`
- `0x18008d778`
- `0x18008dbbc`
- `0x180091140`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18008d7c2`
- `KERNEL32!CreateFileW` at `0x18008d7c2`
- `KERNEL32!CreateFileA` at `0x18008d7f9`
- `KERNEL32!CreateFileA` at `0x18008d7f9`

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
0x18008d778  push    rbx
0x18008d77a  push    rsi
0x18008d77b  push    rdi
0x18008d77c  sub     rsp, 270h
0x18008d783  mov     rax, cs:__security_cookie
0x18008d78a  xor     rax, rsp
0x18008d78d  mov     [rsp+288h+var_28], rax
0x18008d795  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18008d79c  mov     edi, r8d
0x18008d79f  mov     esi, [rsp+288h+arg_20]
0x18008d7a6  mov     ebx, edx
0x18008d7a8  jz      short loc_18008D7CA
0x18008d7aa  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18008d7b3  xor     r9d, r9d; lpSecurityAttributes
0x18008d7b6  mov     [rsp+288h+dwFlagsAndAttributes], 110000h; dwFlagsAndAttributes
0x18008d7be  mov     [rsp+288h+dwCreationDisposition], esi; dwCreationDisposition
0x18008d7c2  call    cs:__imp_CreateFileW
0x18008d7c8  jmp     short loc_18008D80F
0x18008d7ca  mov     rdx, rcx; unsigned __int16 *
0x18008d7cd  lea     rcx, [rsp+288h+lpFileName]; this
0x18008d7d2  call    ??0CStrIn@@QEAA@PEBGI@Z; CStrIn::CStrIn(ushort const *,uint)
0x18008d7d7  mov     rcx, [rsp+288h+lpFileName]; lpFileName
0x18008d7dc  xor     r9d, r9d; lpSecurityAttributes
0x18008d7df  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x18008d7e8  mov     r8d, edi; dwShareMode
0x18008d7eb  mov     [rsp+288h+dwFlagsAndAttributes], 110000h; dwFlagsAndAttributes
0x18008d7f3  mov     edx, ebx; dwDesiredAccess
0x18008d7f5  mov     [rsp+288h+dwCreationDisposition], esi; dwCreationDisposition
0x18008d7f9  call    cs:__imp_CreateFileA
0x18008d7ff  lea     rcx, [rsp+288h+lpFileName]; this
0x18008d804  mov     rbx, rax
0x18008d807  call    ?Free@CConvertStr@@IEAAXXZ; CConvertStr::Free(void)
0x18008d80c  mov     rax, rbx
0x18008d80f  mov     rcx, [rsp+288h+var_28]
0x18008d817  xor     rcx, rsp; StackCookie
0x18008d81a  call    __security_check_cookie
0x18008d81f  add     rsp, 270h
0x18008d826  pop     rdi
0x18008d827  pop     rsi
0x18008d828  pop     rbx
0x18008d829  retn
```
