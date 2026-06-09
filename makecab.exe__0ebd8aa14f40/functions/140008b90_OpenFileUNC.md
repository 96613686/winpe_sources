# OpenFileUNC

- ea: `0x140008b90`
- end: `0x140008d19`
- name: `OpenFileUNC`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000873c`

## callees

- `0x140008a78`
- `0x140008b90`
- `0x14000e412`
- `0x14000e450`
- `0x14000e4e0`

## import_xrefs

- `msvcrt!_open_osfhandle` at `0x140008cd5`
- `msvcrt!_open_osfhandle` at `0x140008cd5`
- `KERNEL32!CloseHandle` at `0x140008ce5`
- `KERNEL32!CloseHandle` at `0x140008ce5`
- `KERNEL32!GetLastError` at `0x140008cbe`
- `KERNEL32!GetLastError` at `0x140008cbe`
- `KERNEL32!CreateFileW` at `0x140008cb5`
- `KERNEL32!CreateFileW` at `0x140008cb5`

## pseudocode

```c
__int64 __fastcall OpenFileUNC(const CHAR *a1, int a2)
{
  DWORD v4; // r14d
  unsigned int v5; // ebp
  DWORD v6; // esi
  int v7; // edx
  DWORD dwCreationDisposition; // edi
  int v9; // ecx
  DWORD dwFlagsAndAttributes; // r15d
  unsigned __int64 v11; // rax
  HANDLE FileW; // rdi
  _BYTE v14[560]; // [rsp+40h] [rbp-2268h] BYREF
  WCHAR FileName[4096]; // [rsp+270h] [rbp-2038h] BYREF

  v4 = 4;
  v5 = -1;
  memset_0(v14, 0, sizeof(v14));
  if ( (a2 & 2) != 0 )
  {
    v6 = -1073741824;
  }
  else if ( (a2 & 1) != 0 )
  {
    v6 = 0x40000000;
  }
  else
  {
    v6 = 0x80000000;
    v4 = 5;
  }
  if ( (a2 & 0x10) != 0 )
  {
    v7 = 268435584;
  }
  else
  {
    v7 = 128;
    if ( (a2 & 0x20) != 0 )
      v7 = 134217856;
  }
  if ( (a2 & 0x100) != 0 )
    dwCreationDisposition = 2 - ((a2 & 0x400) != 0);
  else
    dwCreationDisposition = (a2 & 0x200) != 0 ? 5 : 3;
  v9 = v7 | 0x4000000;
  if ( (a2 & 0x40) == 0 )
    v9 = v7;
  dwFlagsAndAttributes = v9 | 0x100;
  if ( (a2 & 0x1000) == 0 )
    dwFlagsAndAttributes = v9;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  if ( v11 < 0x1000 )
  {
    if ( (unsigned int)GetFullPathUNCW(a1, FileName, 256, (__int64)v14) )
    {
      FileW = CreateFileW(FileName, v6, v4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
      GetLastError();
      if ( FileW != (HANDLE)-1LL )
      {
        v5 = _open_osfhandle((intptr_t)FileW, a2 | 0x8080);
        if ( v5 == -1 )
          CloseHandle(FileW);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140008b90  mov     [rsp+arg_10], rbx
0x140008b95  mov     [rsp+arg_18], rbp
0x140008b9a  push    rsi
0x140008b9b  push    rdi
0x140008b9c  push    r12
0x140008b9e  push    r14
0x140008ba0  push    r15
0x140008ba2  mov     eax, 2280h
0x140008ba7  call    _alloca_probe
0x140008bac  sub     rsp, rax
0x140008baf  mov     rax, cs:__security_cookie
0x140008bb6  xor     rax, rsp
0x140008bb9  mov     [rsp+22A8h+var_38], rax
0x140008bc1  mov     ebx, edx
0x140008bc3  mov     r12, rcx
0x140008bc6  xor     edx, edx; Val
0x140008bc8  lea     rcx, [rsp+22A8h+var_2268]; void *
0x140008bcd  mov     r8d, 230h; Size
0x140008bd3  mov     r14d, 4
0x140008bd9  or      ebp, 0FFFFFFFFh
0x140008bdc  call    memset_0
0x140008be1  test    bl, 2
0x140008be4  jz      short loc_140008BED
0x140008be6  mov     esi, 0C0000000h
0x140008beb  jmp     short loc_140008C04
0x140008bed  test    bl, 1
0x140008bf0  jz      short loc_140008BF9
0x140008bf2  mov     esi, 40000000h
0x140008bf7  jmp     short loc_140008C04
0x140008bf9  mov     esi, 80000000h
0x140008bfe  mov     r14d, 5
0x140008c04  test    bl, 10h
0x140008c07  jz      short loc_140008C10
0x140008c09  mov     edx, 10000080h
0x140008c0e  jmp     short loc_140008C20
0x140008c10  test    bl, 20h
0x140008c13  mov     edx, 80h
0x140008c18  mov     eax, 8000080h
0x140008c1d  cmovnz  edx, eax
0x140008c20  mov     r8d, 100h
0x140008c26  mov     eax, ebx
0x140008c28  test    r8d, ebx
0x140008c2b  jz      short loc_140008C3B
0x140008c2d  and     eax, 400h
0x140008c32  neg     eax
0x140008c34  sbb     edi, edi
0x140008c36  add     edi, 2
0x140008c39  jmp     short loc_140008C4A
0x140008c3b  and     eax, 200h
0x140008c40  neg     eax
0x140008c42  sbb     edi, edi
0x140008c44  and     edi, 2
0x140008c47  add     edi, 3
0x140008c4a  mov     ecx, edx
0x140008c4c  bts     ecx, 1Ah
0x140008c50  test    bl, 40h
0x140008c53  cmovz   ecx, edx
0x140008c56  mov     edx, 1000h
0x140008c5b  mov     r15d, ecx
0x140008c5e  or      r15d, r8d
0x140008c61  test    edx, ebx
0x140008c63  cmovz   r15d, ecx
0x140008c67  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008c6b  inc     rax
0x140008c6e  cmp     byte ptr [r12+rax], 0
0x140008c73  jnz     short loc_140008C6B
0x140008c75  cmp     rax, rdx
0x140008c78  jnb     short loc_140008CEB
0x140008c7a  lea     r9, [rsp+22A8h+var_2268]
0x140008c7f  mov     rcx, r12
0x140008c82  lea     rdx, [rsp+22A8h+FileName]
0x140008c8a  call    GetFullPathUNCW
0x140008c8f  test    eax, eax
0x140008c91  jz      short loc_140008CEB
0x140008c93  mov     [rsp+22A8h+hTemplateFile], 0; hTemplateFile
0x140008c9c  lea     rcx, [rsp+22A8h+FileName]; lpFileName
0x140008ca4  mov     [rsp+22A8h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x140008ca9  xor     r9d, r9d; lpSecurityAttributes
0x140008cac  mov     r8d, r14d; dwShareMode
0x140008caf  mov     [rsp+22A8h+dwCreationDisposition], edi; dwCreationDisposition
0x140008cb3  mov     edx, esi; dwDesiredAccess
0x140008cb5  call    cs:__imp_CreateFileW
0x140008cbb  mov     rdi, rax
0x140008cbe  call    cs:__imp_GetLastError
0x140008cc4  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140008cc8  jz      short loc_140008CEB
0x140008cca  or      ebx, 8080h
0x140008cd0  mov     rcx, rdi; OSFileHandle
0x140008cd3  mov     edx, ebx; Flags
0x140008cd5  call    cs:__imp__open_osfhandle
0x140008cdb  mov     ebp, eax
0x140008cdd  cmp     eax, 0FFFFFFFFh
0x140008ce0  jnz     short loc_140008CEB
0x140008ce2  mov     rcx, rdi; hObject
0x140008ce5  call    cs:__imp_CloseHandle
0x140008ceb  mov     eax, ebp
0x140008ced  mov     rcx, [rsp+22A8h+var_38]
0x140008cf5  xor     rcx, rsp; StackCookie
0x140008cf8  call    __security_check_cookie
0x140008cfd  lea     r11, [rsp+22A8h+var_28]
0x140008d05  mov     rbx, [r11+40h]
0x140008d09  mov     rbp, [r11+48h]
0x140008d0d  mov     rsp, r11
0x140008d10  pop     r15
0x140008d12  pop     r14
0x140008d14  pop     r12
0x140008d16  pop     rdi
0x140008d17  pop     rsi
0x140008d18  retn
```
