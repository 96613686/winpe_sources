# NtWin32LiveSystemProvider::WriteKernelMinidump(void *,void *,ulong,void * *,ulong,ulong)

- ea: `0x1800267d0`
- end: `0x18002692b`
- name: `?WriteKernelMinidump@NtWin32LiveSystemProvider@@UEAAJPEAX0KPEAPEAXKK@Z`
- size: `347`
- prototype: `int(NtWin32LiveSystemProvider *__hidden this, void *, void *, unsigned int, void **, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800267d0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268d4`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002690b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18002690b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180026830`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180026830`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800268c0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800268c0`

## pseudocode

```c
__int64 __fastcall NtWin32LiveSystemProvider::WriteKernelMinidump(
        NtWin32LiveSystemProvider *this,
        void *a2,
        void *a3,
        int a4,
        void **a5,
        unsigned int a6)
{
  LPVOID v10; // rax
  void *v11; // rdi
  LPVOID v12; // r9
  __int64 (__fastcall *v13)(__int64, __int128 *, __int64, LPVOID, DWORD, DWORD *); // rax
  int v14; // ebx
  unsigned int v15; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-40h] BYREF
  __int128 v18; // [rsp+48h] [rbp-38h] BYREF
  __int128 v19; // [rsp+58h] [rbp-28h]
  __int128 v20; // [rsp+68h] [rbp-18h]
  void **v21; // [rsp+78h] [rbp-8h]
  DWORD nNumberOfBytesToWrite; // [rsp+A0h] [rbp+20h] BYREF

  v21 = 0;
  v18 = 0;
  nNumberOfBytesToWrite = 0;
  v19 = 0;
  v20 = 0;
  if ( !*((_QWORD *)this + 111) )
    return 2147500034LL;
  NumberOfBytesWritten = 0x400000;
  v10 = VirtualAlloc(0, 0x400000u, 0x1000u, 4u);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  v18 = 0;
  DWORD1(v18) = a6;
  v12 = v10;
  v21 = a5;
  v13 = (__int64 (__fastcall *)(__int64, __int128 *, __int64, LPVOID, DWORD, DWORD *))*((_QWORD *)this + 111);
  v20 = 0;
  LODWORD(v18) = 1;
  v19 = 0;
  HIDWORD(v20) = a4;
  v14 = v13(29, &v18, 56, v12, NumberOfBytesWritten, &nNumberOfBytesToWrite);
  if ( v14 >= 0 )
  {
    if ( WriteFile(a2, v11, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      v15 = NumberOfBytesWritten < nNumberOfBytesToWrite ? 0x80070070 : 0;
    }
    else if ( GetLastError() )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v15 = -2147467259;
    }
  }
  else
  {
    v15 = v14 | 0x10000000;
  }
  VirtualFree(v11, 0, 0x8000u);
  return v15;
}

```

## disassembly

```asm
0x1800267d0  mov     [rsp-18h+arg_8], rbx
0x1800267d5  mov     [rsp-18h+arg_10], rsi
0x1800267da  push    rbp
0x1800267db  push    rdi
0x1800267dc  push    r14
0x1800267de  mov     rbp, rsp
0x1800267e1  sub     rsp, 80h
0x1800267e8  xor     eax, eax
0x1800267ea  xorps   xmm0, xmm0
0x1800267ed  mov     r14d, r9d
0x1800267f0  mov     rsi, rdx
0x1800267f3  mov     rbx, rcx
0x1800267f6  mov     [rbp+var_8], rax
0x1800267fa  movups  [rbp+var_38], xmm0
0x1800267fe  mov     [rbp+nNumberOfBytesToWrite], eax
0x180026801  movups  [rbp+var_28], xmm0
0x180026805  movups  [rbp+var_18], xmm0
0x180026809  cmp     [rcx+378h], rax
0x180026810  jnz     short loc_18002681C
0x180026812  mov     eax, 80004002h
0x180026817  jmp     loc_180026913
0x18002681c  xor     ecx, ecx; lpAddress
0x18002681e  mov     edx, 400000h; dwSize
0x180026823  mov     r8d, 1000h; flAllocationType
0x180026829  mov     [rbp+NumberOfBytesWritten], edx
0x18002682c  lea     r9d, [rcx+4]; flProtect
0x180026830  call    cs:__imp_VirtualAlloc
0x180026836  mov     rdi, rax
0x180026839  test    rax, rax
0x18002683c  jnz     short loc_180026848
0x18002683e  mov     eax, 8007000Eh
0x180026843  jmp     loc_180026913
0x180026848  mov     ecx, [rbp+NumberOfBytesWritten]
0x18002684b  lea     rdx, [rbp+var_38]
0x18002684f  mov     eax, [rbp+arg_28]
0x180026852  xorps   xmm0, xmm0
0x180026855  movups  [rbp+var_38], xmm0
0x180026859  mov     dword ptr [rbp+var_38+4], eax
0x18002685c  mov     r8d, 38h ; '8'
0x180026862  mov     rax, [rbp+arg_20]
0x180026866  mov     r9, rdi
0x180026869  mov     [rbp+var_8], rax
0x18002686d  lea     rax, [rbp+nNumberOfBytesToWrite]
0x180026871  mov     [rsp+80h+var_58], rax
0x180026876  mov     rax, [rbx+378h]
0x18002687d  mov     dword ptr [rsp+80h+lpOverlapped], ecx
0x180026881  lea     ecx, [r8-1Bh]
0x180026885  movups  [rbp+var_18], xmm0
0x180026889  mov     dword ptr [rbp+var_38], 1
0x180026890  movups  [rbp+var_28], xmm0
0x180026894  mov     dword ptr [rbp+var_18+0Ch], r14d
0x180026898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002689d  mov     ebx, eax
0x18002689f  test    eax, eax
0x1800268a1  jns     short loc_1800268A9
0x1800268a3  bts     ebx, 1Ch
0x1800268a7  jmp     short loc_180026900
0x1800268a9  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800268ad  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800268b1  mov     rdx, rdi; lpBuffer
0x1800268b4  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x1800268bd  mov     rcx, rsi; hFile
0x1800268c0  call    cs:__imp_WriteFile
0x1800268c6  test    eax, eax
0x1800268c8  jnz     short loc_1800268F2
0x1800268ca  call    cs:__imp_GetLastError
0x1800268d0  test    eax, eax
0x1800268d2  jz      short loc_1800268EB
0x1800268d4  call    cs:__imp_GetLastError
0x1800268da  mov     ebx, eax
0x1800268dc  test    eax, eax
0x1800268de  jle     short loc_180026900
0x1800268e0  movzx   ebx, ax
0x1800268e3  or      ebx, 80070000h
0x1800268e9  jmp     short loc_180026900
0x1800268eb  mov     ebx, 80004005h
0x1800268f0  jmp     short loc_180026900
0x1800268f2  mov     eax, [rbp+nNumberOfBytesToWrite]
0x1800268f5  cmp     [rbp+NumberOfBytesWritten], eax
0x1800268f8  sbb     ebx, ebx
0x1800268fa  and     ebx, 80070070h
0x180026900  xor     edx, edx; dwSize
0x180026902  mov     r8d, 8000h; dwFreeType
0x180026908  mov     rcx, rdi; lpAddress
0x18002690b  call    cs:__imp_VirtualFree
0x180026911  mov     eax, ebx
0x180026913  lea     r11, [rsp+80h+var_s0]
0x18002691b  mov     rbx, [r11+28h]
0x18002691f  mov     rsi, [r11+30h]
0x180026923  mov     rsp, r11
0x180026926  pop     r14
0x180026928  pop     rdi
0x180026929  pop     rbp
0x18002692a  retn
```
