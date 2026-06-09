# CreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)

- ea: `0x140050ae0`
- end: `0x140050cde`
- name: `?CreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(HINSTANCE hModule, const unsigned __int16 *, const unsigned __int16 *, struct IStream **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14004225c`
- `0x140051164`

## callees

- `0x1400038e6`
- `0x140050ae0`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x140050ca6`
- `KERNEL32!GlobalUnlock` at `0x140050ca6`
- `KERNEL32!GlobalLock` at `0x140050c28`
- `KERNEL32!GlobalLock` at `0x140050c28`
- `KERNEL32!FindResourceW` at `0x140050afd`
- `KERNEL32!FindResourceW` at `0x140050afd`
- `KERNEL32!LoadResource` at `0x140050b4a`
- `KERNEL32!LoadResource` at `0x140050b4a`
- `KERNEL32!GlobalFree` at `0x140050cbe`
- `KERNEL32!GlobalFree` at `0x140050cbe`
- `KERNEL32!GlobalAlloc` at `0x140050bea`
- `KERNEL32!GlobalAlloc` at `0x140050bea`
- `KERNEL32!LockResource` at `0x140050b89`
- `KERNEL32!LockResource` at `0x140050b89`
- `KERNEL32!FreeResource` at `0x140050c92`
- `KERNEL32!FreeResource` at `0x140050c92`
- `KERNEL32!SizeofResource` at `0x140050bad`
- `KERNEL32!SizeofResource` at `0x140050bad`
- `KERNEL32!GetLastError` at `0x140050b1f`
- `KERNEL32!GetLastError` at `0x140050b66`
- `KERNEL32!GetLastError` at `0x140050bbf`
- `KERNEL32!GetLastError` at `0x140050c06`
- `KERNEL32!GetLastError` at `0x140050c44`
- `KERNEL32!GetLastError` at `0x140050b1f`
- `KERNEL32!GetLastError` at `0x140050b66`
- `KERNEL32!GetLastError` at `0x140050bbf`
- `KERNEL32!GetLastError` at `0x140050c06`
- `KERNEL32!GetLastError` at `0x140050c44`
- `ole32!CreateStreamOnHGlobal` at `0x140050c7c`
- `ole32!CreateStreamOnHGlobal` at `0x140050c7c`

## pseudocode

```c
__int64 __fastcall CreateStreamFromResource(
        HINSTANCE hModule,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IStream **a4)
{
  HRSRC ResourceW; // r15
  signed int LastError; // eax
  int StreamOnHGlobal; // ebx
  HGLOBAL v9; // rdi
  void *v10; // r14
  HGLOBAL Resource; // rsi
  signed int v12; // eax
  const void *v13; // r12
  DWORD v14; // eax
  SIZE_T v15; // rbp
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax

  ResourceW = FindResourceW(hModule, a2, (LPCWSTR)0x17);
  if ( (((unsigned __int64)ResourceW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_5;
  LastError = GetLastError();
  StreamOnHGlobal = LastError;
  if ( LastError > 0 )
    StreamOnHGlobal = (unsigned __int16)LastError | 0x80070000;
  if ( StreamOnHGlobal >= 0 )
  {
LABEL_5:
    v9 = 0;
    v10 = 0;
    Resource = LoadResource(hModule, ResourceW);
    if ( (((unsigned __int64)Resource + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_9;
    v12 = GetLastError();
    StreamOnHGlobal = v12;
    if ( v12 > 0 )
      StreamOnHGlobal = (unsigned __int16)v12 | 0x80070000;
    if ( StreamOnHGlobal >= 0 )
    {
LABEL_9:
      v13 = LockResource(Resource);
      if ( v13 )
      {
        v14 = SizeofResource(hModule, ResourceW);
        v15 = v14;
        if ( v14 )
          goto LABEL_15;
        v16 = GetLastError();
        StreamOnHGlobal = v16;
        if ( v16 > 0 )
          StreamOnHGlobal = (unsigned __int16)v16 | 0x80070000;
        if ( StreamOnHGlobal >= 0 )
        {
LABEL_15:
          v9 = GlobalAlloc(2u, v15);
          if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
            goto LABEL_19;
          v17 = GetLastError();
          StreamOnHGlobal = v17;
          if ( v17 > 0 )
            StreamOnHGlobal = (unsigned __int16)v17 | 0x80070000;
          if ( StreamOnHGlobal >= 0 )
          {
LABEL_19:
            v10 = GlobalLock(v9);
            if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
              goto LABEL_23;
            v18 = GetLastError();
            StreamOnHGlobal = v18;
            if ( v18 > 0 )
              StreamOnHGlobal = (unsigned __int16)v18 | 0x80070000;
            if ( StreamOnHGlobal >= 0 )
            {
LABEL_23:
              memcpy_0(v10, v13, v15);
              StreamOnHGlobal = CreateStreamOnHGlobal(v9, 1, a4);
            }
          }
        }
      }
      else
      {
        StreamOnHGlobal = -2147467259;
      }
    }
    if ( Resource )
      FreeResource(Resource);
    if ( v10 )
      GlobalUnlock(v9);
    if ( StreamOnHGlobal < 0 && v9 )
      GlobalFree(v9);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x140050ae0  push    rbx
0x140050ae2  push    rbp
0x140050ae3  push    rsi
0x140050ae4  push    rdi
0x140050ae5  push    r12
0x140050ae7  push    r13
0x140050ae9  push    r14
0x140050aeb  push    r15
0x140050aed  sub     rsp, 28h
0x140050af1  mov     r8d, 17h; lpType
0x140050af7  mov     r13, r9
0x140050afa  mov     rbp, rcx
0x140050afd  call    cs:__imp_FindResourceW
0x140050b04  nop     dword ptr [rax+rax+00h]
0x140050b09  mov     r15, rax
0x140050b0c  mov     r12d, 80070000h
0x140050b12  lea     rdx, [rax+1]
0x140050b16  test    rdx, 0FFFFFFFFFFFFFFFEh
0x140050b1d  jnz     short loc_140050B3F
0x140050b1f  call    cs:__imp_GetLastError
0x140050b26  nop     dword ptr [rax+rax+00h]
0x140050b2b  mov     ebx, eax
0x140050b2d  test    eax, eax
0x140050b2f  jle     short loc_140050B37
0x140050b31  movzx   ebx, ax
0x140050b34  or      ebx, r12d
0x140050b37  test    ebx, ebx
0x140050b39  js      loc_140050CCA
0x140050b3f  mov     rdx, r15; hResInfo
0x140050b42  mov     rcx, rbp; hModule
0x140050b45  xor     edi, edi
0x140050b47  xor     r14d, r14d
0x140050b4a  call    cs:__imp_LoadResource
0x140050b51  nop     dword ptr [rax+rax+00h]
0x140050b56  mov     rsi, rax
0x140050b59  lea     rcx, [rax+1]
0x140050b5d  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140050b64  jnz     short loc_140050B86
0x140050b66  call    cs:__imp_GetLastError
0x140050b6d  nop     dword ptr [rax+rax+00h]
0x140050b72  mov     ebx, eax
0x140050b74  test    eax, eax
0x140050b76  jle     short loc_140050B7E
0x140050b78  movzx   ebx, ax
0x140050b7b  or      ebx, r12d
0x140050b7e  test    ebx, ebx
0x140050b80  js      loc_140050C8A
0x140050b86  mov     rcx, rsi; hResData
0x140050b89  call    cs:__imp_LockResource
0x140050b90  nop     dword ptr [rax+rax+00h]
0x140050b95  mov     r12, rax
0x140050b98  test    rax, rax
0x140050b9b  jnz     short loc_140050BA7
0x140050b9d  mov     ebx, 80004005h
0x140050ba2  jmp     loc_140050C8A
0x140050ba7  mov     rdx, r15; hResInfo
0x140050baa  mov     rcx, rbp; hModule
0x140050bad  call    cs:__imp_SizeofResource
0x140050bb4  nop     dword ptr [rax+rax+00h]
0x140050bb9  mov     ebp, eax
0x140050bbb  test    eax, eax
0x140050bbd  jnz     short loc_140050BE2
0x140050bbf  call    cs:__imp_GetLastError
0x140050bc6  nop     dword ptr [rax+rax+00h]
0x140050bcb  mov     ebx, eax
0x140050bcd  test    eax, eax
0x140050bcf  jle     short loc_140050BDA
0x140050bd1  movzx   ebx, ax
0x140050bd4  or      ebx, 80070000h
0x140050bda  test    ebx, ebx
0x140050bdc  js      loc_140050C8A
0x140050be2  mov     rdx, rbp; dwBytes
0x140050be5  mov     ecx, 2; uFlags
0x140050bea  call    cs:__imp_GlobalAlloc
0x140050bf1  nop     dword ptr [rax+rax+00h]
0x140050bf6  mov     rdi, rax
0x140050bf9  lea     rcx, [rax+1]
0x140050bfd  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140050c04  jnz     short loc_140050C25
0x140050c06  call    cs:__imp_GetLastError
0x140050c0d  nop     dword ptr [rax+rax+00h]
0x140050c12  mov     ebx, eax
0x140050c14  test    eax, eax
0x140050c16  jle     short loc_140050C21
0x140050c18  movzx   ebx, ax
0x140050c1b  or      ebx, 80070000h
0x140050c21  test    ebx, ebx
0x140050c23  js      short loc_140050C8A
0x140050c25  mov     rcx, rdi; hMem
0x140050c28  call    cs:__imp_GlobalLock
0x140050c2f  nop     dword ptr [rax+rax+00h]
0x140050c34  mov     r14, rax
0x140050c37  lea     rcx, [rax+1]
0x140050c3b  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140050c42  jnz     short loc_140050C63
0x140050c44  call    cs:__imp_GetLastError
0x140050c4b  nop     dword ptr [rax+rax+00h]
0x140050c50  mov     ebx, eax
0x140050c52  test    eax, eax
0x140050c54  jle     short loc_140050C5F
0x140050c56  movzx   ebx, ax
0x140050c59  or      ebx, 80070000h
0x140050c5f  test    ebx, ebx
0x140050c61  js      short loc_140050C8A
0x140050c63  mov     r8, rbp; Size
0x140050c66  mov     rdx, r12; Src
0x140050c69  mov     rcx, r14; void *
0x140050c6c  call    memcpy_0
0x140050c71  mov     r8, r13; ppstm
0x140050c74  mov     edx, 1; fDeleteOnRelease
0x140050c79  mov     rcx, rdi; hGlobal
0x140050c7c  call    cs:__imp_CreateStreamOnHGlobal
0x140050c83  nop     dword ptr [rax+rax+00h]
0x140050c88  mov     ebx, eax
0x140050c8a  test    rsi, rsi
0x140050c8d  jz      short loc_140050C9E
0x140050c8f  mov     rcx, rsi; hResData
0x140050c92  call    cs:__imp_FreeResource
0x140050c99  nop     dword ptr [rax+rax+00h]
0x140050c9e  test    r14, r14
0x140050ca1  jz      short loc_140050CB2
0x140050ca3  mov     rcx, rdi; hMem
0x140050ca6  call    cs:__imp_GlobalUnlock
0x140050cad  nop     dword ptr [rax+rax+00h]
0x140050cb2  test    ebx, ebx
0x140050cb4  jns     short loc_140050CCA
0x140050cb6  test    rdi, rdi
0x140050cb9  jz      short loc_140050CCA
0x140050cbb  mov     rcx, rdi; hMem
0x140050cbe  call    cs:__imp_GlobalFree
0x140050cc5  nop     dword ptr [rax+rax+00h]
0x140050cca  mov     eax, ebx
0x140050ccc  add     rsp, 28h
0x140050cd0  pop     r15
0x140050cd2  pop     r14
0x140050cd4  pop     r13
0x140050cd6  pop     r12
0x140050cd8  pop     rdi
0x140050cd9  pop     rsi
0x140050cda  pop     rbp
0x140050cdb  pop     rbx
0x140050cdc  retn
```
