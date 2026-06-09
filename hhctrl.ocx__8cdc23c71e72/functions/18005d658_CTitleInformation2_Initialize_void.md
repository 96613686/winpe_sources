# CTitleInformation2::Initialize(void)

- ea: `0x18005d658`
- end: `0x18005d7fc`
- name: `?Initialize@CTitleInformation2@@QEAAJXZ`
- size: `420`
- prototype: `__int64 __fastcall(CTitleInformation2 *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180028718`

## callees

- `0x180001768`
- `0x1800095c8`
- `0x18004f794`
- `0x18005d658`
- `0x180075c90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005d741`
- `KERNEL32!CloseHandle` at `0x18005d741`
- `KERNEL32!CreateFileA` at `0x18005d6c6`
- `KERNEL32!CreateFileA` at `0x18005d6c6`
- `KERNEL32!ReadFile` at `0x18005d71a`
- `KERNEL32!ReadFile` at `0x18005d738`
- `KERNEL32!ReadFile` at `0x18005d71a`
- `KERNEL32!ReadFile` at `0x18005d738`
- `KERNEL32!GetFullPathNameA` at `0x18005d775`
- `KERNEL32!GetFullPathNameA` at `0x18005d775`
- `KERNEL32!SetFilePointer` at `0x18005d6fc`
- `KERNEL32!SetFilePointer` at `0x18005d6fc`

## pseudocode

```c
__int64 __fastcall CTitleInformation2::Initialize(CTitleInformation2 *this)
{
  const CHAR *v2; // rcx
  HANDLE v3; // rax
  __int64 v4; // rbx
  void *v5; // rsi
  __int64 result; // rax
  int v7; // eax
  const CHAR *v8; // rcx
  __int64 v9; // rdx
  _BYTE *v10; // rax
  __int64 v11; // rcx
  char *v12; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  LPSTR FilePart; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  CHAR v18[272]; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  v2 = (const CHAR *)*((_QWORD *)this + 1);
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v3 = CreateFileA(v2, 0x80000000, 1u, &SecurityAttributes, 3u, 0x8000080u, 0);
  v4 = -1;
  v5 = v3;
  if ( v3 == (HANDLE)-1LL )
    return 1;
  Buffer = 0;
  v15 = 0;
  NumberOfBytesRead = 0;
  SetFilePointer(v3, 16, 0, 0);
  ReadFile(v5, &Buffer, 4u, &NumberOfBytesRead, 0);
  ReadFile(v5, &v15, 4u, &NumberOfBytesRead, 0);
  CloseHandle(v5);
  v7 = Buffer;
  v8 = (const CHAR *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 7) = Buffer;
  *((_DWORD *)this + 8) = v7;
  *((_DWORD *)this + 6) = v15;
  FilePart = v18;
  GetFullPathNameA(v8, 0x104u, v18, &FilePart);
  LOBYTE(v9) = 46;
  v10 = (_BYTE *)StrRChr(FilePart, v9);
  v11 = -1;
  *v10 = 0;
  do
    ++v11;
  while ( FilePart[v11] );
  v12 = (char *)operator new[](v11 + 1);
  *((_QWORD *)this + 2) = v12;
  if ( !v12 )
    return 2147942414LL;
  do
    ++v4;
  while ( FilePart[v4] );
  StringCchCopyA(v12, v4 + 1, FilePart);
  result = 0;
  *(_DWORD *)this = 1;
  return result;
}

```

## disassembly

```asm
0x18005d658  mov     [rsp-8+arg_8], rbx
0x18005d65d  mov     [rsp-8+arg_10], rsi
0x18005d662  push    rbp
0x18005d663  push    rdi
0x18005d664  push    r15
0x18005d666  lea     rbp, [rsp-90h]
0x18005d66e  sub     rsp, 190h
0x18005d675  mov     rax, cs:__security_cookie
0x18005d67c  xor     rax, rsp
0x18005d67f  mov     [rbp+0A0h+var_20], rax
0x18005d686  xor     r15d, r15d
0x18005d689  mov     qword ptr [rsp+1A0h+SecurityAttributes.nLength], 18h
0x18005d692  mov     rdi, rcx
0x18005d695  mov     [rsp+1A0h+hTemplateFile], r15; hTemplateFile
0x18005d69a  mov     rcx, [rcx+8]; lpFileName
0x18005d69e  lea     r9, [rsp+1A0h+SecurityAttributes]; lpSecurityAttributes
0x18005d6a3  mov     [rsp+1A0h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18005d6ab  mov     edx, 80000000h; dwDesiredAccess
0x18005d6b0  lea     r8d, [r15+1]; dwShareMode
0x18005d6b4  mov     qword ptr [rsp+1A0h+SecurityAttributes.bInheritHandle], r15
0x18005d6b9  mov     [rsp+1A0h+SecurityAttributes.lpSecurityDescriptor], r15
0x18005d6be  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18005d6c6  call    cs:__imp_CreateFileA
0x18005d6cc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005d6d0  mov     rsi, rax
0x18005d6d3  cmp     rax, rbx
0x18005d6d6  jnz     short loc_18005D6E0
0x18005d6d8  lea     eax, [rbx+2]
0x18005d6db  jmp     loc_18005D7D5
0x18005d6e0  xor     r9d, r9d; dwMoveMethod
0x18005d6e3  mov     [rsp+1A0h+Buffer], r15d
0x18005d6e8  xor     r8d, r8d; lpDistanceToMoveHigh
0x18005d6eb  mov     [rsp+1A0h+var_158], r15d
0x18005d6f0  mov     rcx, rsi; hFile
0x18005d6f3  mov     [rsp+1A0h+NumberOfBytesRead], r15d
0x18005d6f8  lea     edx, [r9+10h]; lDistanceToMove
0x18005d6fc  call    cs:__imp_SetFilePointer
0x18005d702  lea     r9, [rsp+1A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005d707  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r15; lpOverlapped
0x18005d70c  mov     r8d, 4; nNumberOfBytesToRead
0x18005d712  lea     rdx, [rsp+1A0h+Buffer]; lpBuffer
0x18005d717  mov     rcx, rsi; hFile
0x18005d71a  call    cs:__imp_ReadFile
0x18005d720  lea     r9, [rsp+1A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005d725  mov     qword ptr [rsp+1A0h+dwCreationDisposition], r15; lpOverlapped
0x18005d72a  mov     r8d, 4; nNumberOfBytesToRead
0x18005d730  lea     rdx, [rsp+1A0h+var_158]; lpBuffer
0x18005d735  mov     rcx, rsi; hFile
0x18005d738  call    cs:__imp_ReadFile
0x18005d73e  mov     rcx, rsi; hObject
0x18005d741  call    cs:__imp_CloseHandle
0x18005d747  mov     eax, [rsp+1A0h+Buffer]
0x18005d74b  lea     r9, [rsp+1A0h+FilePart]; lpFilePart
0x18005d750  mov     rcx, [rdi+8]; lpFileName
0x18005d754  lea     r8, [rsp+1A0h+var_130]; lpBuffer
0x18005d759  mov     [rdi+1Ch], eax
0x18005d75c  mov     edx, 104h; nBufferLength
0x18005d761  mov     [rdi+20h], eax
0x18005d764  mov     eax, [rsp+1A0h+var_158]
0x18005d768  mov     [rdi+18h], eax
0x18005d76b  lea     rax, [rsp+1A0h+var_130]
0x18005d770  mov     [rsp+1A0h+FilePart], rax
0x18005d775  call    cs:__imp_GetFullPathNameA
0x18005d77b  mov     rcx, [rsp+1A0h+FilePart]
0x18005d780  mov     dl, 2Eh ; '.'
0x18005d782  call    StrRChr
0x18005d787  mov     rcx, rbx
0x18005d78a  mov     [rax], r15b
0x18005d78d  mov     rax, [rsp+1A0h+FilePart]
0x18005d792  inc     rcx
0x18005d795  cmp     [rax+rcx], r15b
0x18005d799  jnz     short loc_18005D792
0x18005d79b  inc     rcx; unsigned __int64
0x18005d79e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005d7a3  mov     [rdi+10h], rax
0x18005d7a7  test    rax, rax
0x18005d7aa  jnz     short loc_18005D7B3
0x18005d7ac  mov     eax, 8007000Eh
0x18005d7b1  jmp     short loc_18005D7D5
0x18005d7b3  mov     r8, [rsp+1A0h+FilePart]; char *
0x18005d7b8  inc     rbx
0x18005d7bb  cmp     [r8+rbx], r15b
0x18005d7bf  jnz     short loc_18005D7B8
0x18005d7c1  lea     rdx, [rbx+1]; unsigned __int64
0x18005d7c5  mov     rcx, rax; char *
0x18005d7c8  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005d7cd  xor     eax, eax
0x18005d7cf  mov     dword ptr [rdi], 1
0x18005d7d5  mov     rcx, [rbp+0A0h+var_20]
0x18005d7dc  xor     rcx, rsp; StackCookie
0x18005d7df  call    __security_check_cookie
0x18005d7e4  lea     r11, [rsp+1A0h+var_10]
0x18005d7ec  mov     rbx, [r11+28h]
0x18005d7f0  mov     rsi, [r11+30h]
0x18005d7f4  mov     rsp, r11
0x18005d7f7  pop     r15
0x18005d7f9  pop     rdi
0x18005d7fa  pop     rbp
0x18005d7fb  retn
```
