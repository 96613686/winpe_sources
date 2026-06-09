# CFveApiEnum::EnumNextDevType(void)

- ea: `0x180005960`
- end: `0x180005c57`
- name: `?EnumNextDevType@CFveApiEnum@@AEAAJXZ`
- size: `759`
- prototype: `__int64 __fastcall(CFveApiEnum *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180005f74`

## callees

- `0x180005410`
- `0x180005960`
- `0x18000ba30`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180005b37`
- `ntdll!RtlCompareMemory` at `0x180005b37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800059c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800059c9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180005a16`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180005abd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180005a16`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180005abd`

## pseudocode

```c
__int64 __fastcall CFveApiEnum::EnumNextDevType(CFveApiEnum *this)
{
  int v2; // edi
  unsigned int *v3; // r14
  int v4; // r15d
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int LastHresultError; // ebx
  SIZE_T v8; // r8
  unsigned int v9; // r13d
  unsigned int v10; // ecx
  unsigned int *v11; // r12
  SIZE_T v12; // r8
  __int64 v13; // rax
  void *v14; // rcx
  unsigned int v16; // [rsp+44h] [rbp-64h]
  DWORD OutBuffer; // [rsp+68h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+6Ch] [rbp-3Ch] BYREF

  v2 = 0;
  v3 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  v4 = 3;
  FileW = (HANDLE)*((_QWORD *)this + 12);
  if ( FileW == (HANDLE)-1LL )
  {
    FileW = CreateFileW(L"\\\\.\\BitLocker", 0, 3u, 0, 3u, 0, 0);
    *((_QWORD *)this + 12) = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_33;
  }
  if ( DeviceIoControl(FileW, 0x4C4210CCu, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
  {
    LastHresultError = -2147024809;
    goto LABEL_36;
  }
  LastError = GetLastError();
  LastHresultError = LastError;
  if ( LastError > 0 )
    LastHresultError = (unsigned __int16)LastError | 0x80070000;
  if ( LastHresultError >= 0 )
    LastHresultError = -2147418113;
  if ( LastHresultError == -2147024662 )
  {
    LastHresultError = 0;
    v8 = OutBuffer;
    if ( !OutBuffer )
      v8 = 1;
    v3 = (unsigned int *)HeapAlloc(CFveApiBase::_ProcessHeap, 0, v8);
    if ( !v3 )
    {
      LastHresultError = -2147024882;
      goto LABEL_36;
    }
    if ( DeviceIoControl(*((HANDLE *)this + 12), 0x4C4210CCu, 0, 0, v3, OutBuffer, &BytesReturned, 0) )
    {
      v9 = 8;
      v10 = 0;
      v11 = v3 + 2;
      while ( 1 )
      {
        v16 = v10;
        if ( v10 >= v3[1] || v9 >= *v3 )
          break;
        while ( v2 < 3 )
        {
          v12 = qword_18013B928[v2];
          if ( v11[3] + 2LL == v12
            && RtlCompareMemory((char *)v11 + v11[2], off_18012CDE0[v2], v12) == qword_18013B928[v2] )
          {
            break;
          }
          ++v2;
        }
        if ( v2 && v2 < 3 && (v2 > *((_DWORD *)this + 20) || *((_DWORD *)this + 20) == 3) && v2 < v4 )
          v4 = v2;
        v13 = *v11;
        v9 += v13;
        v10 = v16 + 1;
        v11 = (unsigned int *)((char *)v11 + v13);
        v2 = 0;
      }
      if ( v4 == 3 )
      {
        *((_DWORD *)this + 20) = 3;
        LastHresultError = -2147024878;
      }
      else
      {
        *((_DWORD *)this + 20) = v4;
        *((_DWORD *)this + 21) = -1;
        v14 = (void *)*((_QWORD *)this + 11);
        if ( v14 != (void *)-1LL )
        {
          CloseHandle(v14);
          *((_QWORD *)this + 11) = -1;
        }
      }
      goto LABEL_36;
    }
LABEL_33:
    LastHresultError = GetLastHresultError();
  }
LABEL_36:
  if ( v3 && !HeapFree(CFveApiBase::_ProcessHeap, 0, v3) )
    GetLastHresultError();
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x180005960  mov     r11, rsp
0x180005963  mov     [r11+10h], rbx
0x180005967  mov     [r11+18h], rsi
0x18000596b  push    rdi
0x18000596c  push    r12
0x18000596e  push    r13
0x180005970  push    r14
0x180005972  push    r15
0x180005974  sub     rsp, 80h
0x18000597b  mov     rax, cs:__security_cookie
0x180005982  xor     rax, rsp
0x180005985  mov     [rsp+0A8h+var_38], rax
0x18000598a  mov     rsi, rcx
0x18000598d  xor     edi, edi
0x18000598f  mov     r14d, edi
0x180005992  mov     [r11-58h], rdi
0x180005996  mov     [rsp+0A8h+OutBuffer], edi
0x18000599a  mov     [rsp+0A8h+BytesReturned], edi
0x18000599e  lea     ecx, [rdi+3]
0x1800059a1  mov     r15d, ecx
0x1800059a4  mov     rax, [rsi+60h]
0x1800059a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800059ac  jnz     short loc_1800059E3
0x1800059ae  mov     [r11-78h], rdi
0x1800059b2  mov     [rsp+0A8h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800059b6  mov     [rsp+0A8h+dwCreationDisposition], ecx; dwCreationDisposition
0x1800059ba  xor     r9d, r9d; lpSecurityAttributes
0x1800059bd  mov     r8d, ecx; dwShareMode
0x1800059c0  xor     edx, edx; dwDesiredAccess
0x1800059c2  lea     rcx, FileName; "\\\\.\\BitLocker"
0x1800059c9  call    cs:__imp_CreateFileW
0x1800059d0  nop     dword ptr [rax+rax+00h]
0x1800059d5  mov     [rsi+60h], rax
0x1800059d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800059dd  jz      loc_180005BED
0x1800059e3  mov     [rsp+0A8h+lpOverlapped], rdi; lpOverlapped
0x1800059e8  lea     rcx, [rsp+0A8h+BytesReturned]
0x1800059ed  mov     [rsp+0A8h+lpBytesReturned], rcx; lpBytesReturned
0x1800059f2  mov     [rsp+0A8h+dwFlagsAndAttributes], 4; nOutBufferSize
0x1800059fa  lea     rcx, [rsp+0A8h+OutBuffer]
0x1800059ff  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rcx; lpOutBuffer
0x180005a04  xor     r9d, r9d; nInBufferSize
0x180005a07  xor     r8d, r8d; lpInBuffer
0x180005a0a  mov     r12d, 4C4210CCh
0x180005a10  mov     edx, r12d; dwIoControlCode
0x180005a13  mov     rcx, rax; hDevice
0x180005a16  call    cs:__imp_DeviceIoControl
0x180005a1d  nop     dword ptr [rax+rax+00h]
0x180005a22  test    eax, eax
0x180005a24  jnz     loc_180005BF6
0x180005a2a  call    cs:__imp_GetLastError
0x180005a31  nop     dword ptr [rax+rax+00h]
0x180005a36  mov     ebx, eax
0x180005a38  test    eax, eax
0x180005a3a  jle     short loc_180005A45
0x180005a3c  movzx   ebx, ax
0x180005a3f  or      ebx, 80070000h
0x180005a45  mov     eax, 8000FFFFh
0x180005a4a  test    ebx, ebx
0x180005a4c  cmovns  ebx, eax
0x180005a4f  cmp     ebx, 800700EAh
0x180005a55  jnz     loc_180005C02
0x180005a5b  mov     ebx, edi
0x180005a5d  mov     r8d, [rsp+0A8h+OutBuffer]
0x180005a62  mov     eax, 1
0x180005a67  test    r8, r8
0x180005a6a  cmovz   r8d, eax; dwBytes
0x180005a6e  xor     edx, edx; dwFlags
0x180005a70  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180005a77  call    cs:__imp_HeapAlloc
0x180005a7e  nop     dword ptr [rax+rax+00h]
0x180005a83  mov     r14, rax
0x180005a86  mov     [rsp+0A8h+var_58], rax
0x180005a8b  test    rax, rax
0x180005a8e  jz      loc_180005BFD
0x180005a94  mov     [rsp+0A8h+lpOverlapped], rdi; lpOverlapped
0x180005a99  lea     rax, [rsp+0A8h+BytesReturned]
0x180005a9e  mov     [rsp+0A8h+lpBytesReturned], rax; lpBytesReturned
0x180005aa3  mov     eax, [rsp+0A8h+OutBuffer]
0x180005aa7  mov     [rsp+0A8h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180005aab  mov     qword ptr [rsp+0A8h+dwCreationDisposition], r14; lpOutBuffer
0x180005ab0  xor     r9d, r9d; nInBufferSize
0x180005ab3  xor     r8d, r8d; lpInBuffer
0x180005ab6  mov     edx, r12d; dwIoControlCode
0x180005ab9  mov     rcx, [rsi+60h]; hDevice
0x180005abd  call    cs:__imp_DeviceIoControl
0x180005ac4  nop     dword ptr [rax+rax+00h]
0x180005ac9  test    eax, eax
0x180005acb  jz      loc_180005BED
0x180005ad1  mov     r13d, 8
0x180005ad7  mov     [rsp+0A8h+var_60], r13d
0x180005adc  mov     ecx, edi
0x180005ade  lea     r12, [r14+8]
0x180005ae2  lea     r9, __ImageBase
0x180005ae9  mov     [rsp+0A8h+var_64], ecx
0x180005aed  mov     [rsp+0A8h+var_48], r12
0x180005af2  cmp     ecx, [r14+4]
0x180005af6  jnb     loc_180005BA4
0x180005afc  cmp     r13d, [r14]
0x180005aff  jnb     loc_180005BA4
0x180005b05  mov     [rsp+0A8h+var_68], edi
0x180005b09  cmp     edi, 3
0x180005b0c  jge     short loc_180005B57
0x180005b0e  movsxd  rdx, edi
0x180005b11  mov     r8, ds:rva qword_18013B928[r9+rdx*8]; Length
0x180005b19  mov     eax, [r12+0Ch]
0x180005b1e  add     rax, 2
0x180005b22  cmp     rax, r8
0x180005b25  jnz     short loc_180005B9D
0x180005b27  mov     ecx, [r12+8]
0x180005b2c  add     rcx, r12; Source1
0x180005b2f  mov     rdx, ds:rva off_18012CDE0[r9+rdx*8]; Source2
0x180005b37  call    cs:__imp_RtlCompareMemory
0x180005b3e  nop     dword ptr [rax+rax+00h]
0x180005b43  movsxd  rcx, edi
0x180005b46  lea     r9, __ImageBase
0x180005b4d  cmp     rax, ds:rva qword_18013B928[r9+rcx*8]
0x180005b55  jnz     short loc_180005B9D
0x180005b57  test    edi, edi
0x180005b59  jz      loc_180005BEB
0x180005b5f  cmp     edi, 3
0x180005b62  jge     loc_180005BEB
0x180005b68  cmp     edi, [rsi+50h]
0x180005b6b  jle     short loc_180005BD5
0x180005b6d  cmp     edi, r15d
0x180005b70  cmovl   r15d, edi
0x180005b74  mov     [rsp+0A8h+var_50], r15d
0x180005b79  mov     [rsp+0A8h+var_68], 3
0x180005b81  mov     eax, [r12]
0x180005b85  add     r13d, eax
0x180005b88  mov     [rsp+0A8h+var_60], r13d
0x180005b8d  mov     ecx, [rsp+0A8h+var_64]
0x180005b91  inc     ecx
0x180005b93  add     r12, rax
0x180005b96  xor     edi, edi
0x180005b98  jmp     loc_180005AE9
0x180005b9d  inc     edi
0x180005b9f  jmp     loc_180005B05
0x180005ba4  cmp     r15d, 3
0x180005ba8  jz      short loc_180005BDD
0x180005baa  mov     [rsi+50h], r15d
0x180005bae  mov     dword ptr [rsi+54h], 0FFFFFFFFh
0x180005bb5  mov     rcx, [rsi+58h]; hObject
0x180005bb9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005bbd  jz      short loc_180005C02
0x180005bbf  call    cs:__imp_CloseHandle
0x180005bc6  nop     dword ptr [rax+rax+00h]
0x180005bcb  mov     qword ptr [rsi+58h], 0FFFFFFFFFFFFFFFFh
0x180005bd3  jmp     short loc_180005C02
0x180005bd5  cmp     dword ptr [rsi+50h], 3
0x180005bd9  jnz     short loc_180005B79
0x180005bdb  jmp     short loc_180005B6D
0x180005bdd  mov     dword ptr [rsi+50h], 3
0x180005be4  mov     ebx, 80070012h
0x180005be9  jmp     short loc_180005C02
0x180005beb  jmp     short loc_180005B81
0x180005bed  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180005bf2  mov     ebx, eax
0x180005bf4  jmp     short loc_180005C02
0x180005bf6  mov     ebx, 80070057h
0x180005bfb  jmp     short loc_180005C02
0x180005bfd  mov     ebx, 8007000Eh
0x180005c02  test    r14, r14
0x180005c05  jz      short loc_180005C23
0x180005c07  mov     r8, r14; lpMem
0x180005c0a  xor     edx, edx; dwFlags
0x180005c0c  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180005c13  call    cs:__imp_HeapFree
0x180005c1a  nop     dword ptr [rax+rax+00h]
0x180005c1f  test    eax, eax
0x180005c21  jz      short loc_180005C50
0x180005c23  mov     eax, ebx
0x180005c25  mov     rcx, [rsp+0A8h+var_38]
0x180005c2a  xor     rcx, rsp; StackCookie
0x180005c2d  call    __security_check_cookie
0x180005c32  lea     r11, [rsp+0A8h+var_28]
0x180005c3a  mov     rbx, [r11+38h]
0x180005c3e  mov     rsi, [r11+40h]
0x180005c42  mov     rsp, r11
0x180005c45  pop     r15
0x180005c47  pop     r14
0x180005c49  pop     r13
0x180005c4b  pop     r12
0x180005c4d  pop     rdi
0x180005c4e  retn
0x180005c50  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180005c55  jmp     short loc_180005C23
0x18011f23b  push    rbp
0x18011f23d  sub     rsp, 40h
0x18011f241  mov     rbp, rdx
0x18011f244  mov     rcx, [rbp+50h]; lpMem
0x18011f248  test    rcx, rcx
0x18011f24b  jz      short loc_18011F25A
0x18011f24d  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011f252  mov     qword ptr [rbp+50h], 0
0x18011f25a  add     rsp, 40h
0x18011f25e  pop     rbp
0x18011f25f  retn
```
