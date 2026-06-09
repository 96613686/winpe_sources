# SCCardPresent

- ea: `0x180030ddc`
- end: `0x180030f9e`
- name: `SCCardPresent`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800117e0`

## callees

- `0x1800030d8`
- `0x1800037b4`
- `0x180030ddc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030f6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030f6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030f23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180030f23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030f61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030e61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030f61`
- `ext-ms-win-wlan-scard-l1-1-0!SCardEstablishContext` at `0x180030e24`
- `ext-ms-win-wlan-scard-l1-1-0!SCardEstablishContext` at `0x180030e24`
- `ext-ms-win-wlan-scard-l1-1-0!SCardReleaseContext` at `0x180030f7e`
- `ext-ms-win-wlan-scard-l1-1-0!SCardReleaseContext` at `0x180030f7e`
- `ext-ms-win-wlan-scard-l1-1-0!SCardDisconnect` at `0x180030f56`
- `ext-ms-win-wlan-scard-l1-1-0!SCardDisconnect` at `0x180030f56`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x180030e41`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x180030e95`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x180030e41`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x180030e95`
- `ext-ms-win-wlan-scard-l1-1-0!SCardConnectW` at `0x180030ed5`
- `ext-ms-win-wlan-scard-l1-1-0!SCardConnectW` at `0x180030ed5`

## pseudocode

```c
__int64 __fastcall SCCardPresent(wchar_t **a1)
{
  WCHAR *v2; // rsi
  unsigned int v3; // edi
  DWORD v4; // r15d
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  __int64 v7; // rbx
  const WCHAR *v8; // r14
  __int64 v9; // rax
  HANDLE v10; // rax
  wchar_t *v11; // rax
  HANDLE v12; // rax
  SCARDHANDLE hCard[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcchReaders; // [rsp+88h] [rbp+48h] BYREF
  DWORD pdwActiveProtocol; // [rsp+90h] [rbp+50h] BYREF
  SCARDCONTEXT phContext; // [rsp+98h] [rbp+58h] BYREF

  pcchReaders = 0;
  v2 = 0;
  pdwActiveProtocol = 0;
  phContext = 0;
  hCard[0] = 0;
  if ( !(unsigned __int8)IsSCardEstablishContextPresent() )
    goto LABEL_17;
  v3 = SCardEstablishContext(0, 0, 0, &phContext);
  if ( v3 )
    goto LABEL_18;
  v3 = SCardListReadersW(phContext, 0, 0, &pcchReaders);
  if ( v3 )
    goto LABEL_18;
  if ( pcchReaders <= 2 )
  {
LABEL_17:
    v3 = -2146435049;
    goto LABEL_18;
  }
  v4 = 2 * pcchReaders;
  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v4);
  v2 = v6;
  if ( !v6 )
  {
LABEL_6:
    v3 = -2146435066;
    goto LABEL_18;
  }
  v3 = SCardListReadersW(phContext, 0, v6, &pcchReaders);
  if ( !v3 )
  {
    v7 = -1;
    v8 = v2;
    if ( *v2 )
    {
      while ( 1 )
      {
        v3 = SCardConnectW(phContext, v8, 2u, 3u, hCard, &pdwActiveProtocol);
        if ( !v3 )
          break;
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        v8 += v9 + 1;
        if ( !*v8 )
          goto LABEL_18;
      }
    }
    do
      ++v7;
    while ( v8[v7] );
    pcchReaders = v7 + 1;
    v10 = GetProcessHeap();
    v11 = (wchar_t *)HeapAlloc(v10, 8u, 2 * v4);
    *a1 = v11;
    if ( !v11 )
      goto LABEL_6;
    wcscpy_s(v11, pcchReaders, v8);
  }
LABEL_18:
  if ( hCard[0] )
    SCardDisconnect(hCard[0], 0);
  if ( v2 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v2);
  }
  if ( phContext )
    SCardReleaseContext(phContext);
  return v3;
}

```

## disassembly

```asm
0x180030ddc  mov     [rsp-38h+arg_0], rbx
0x180030de1  push    rbp
0x180030de2  push    rsi
0x180030de3  push    rdi
0x180030de4  push    r12
0x180030de6  push    r13
0x180030de8  push    r14
0x180030dea  push    r15
0x180030dec  mov     rbp, rsp
0x180030def  sub     rsp, 40h
0x180030df3  xor     r13d, r13d
0x180030df6  mov     r12, rcx
0x180030df9  mov     [rbp+pcchReaders], r13d
0x180030dfd  mov     esi, r13d
0x180030e00  mov     [rbp+arg_10], r13d
0x180030e04  mov     [rbp+phContext], r13
0x180030e08  mov     [rbp+hCard], r13
0x180030e0c  call    IsSCardEstablishContextPresent
0x180030e11  test    al, al
0x180030e13  jz      loc_180030F46
0x180030e19  lea     r9, [rbp+phContext]; phContext
0x180030e1d  xor     r8d, r8d; pvReserved2
0x180030e20  xor     edx, edx; pvReserved1
0x180030e22  xor     ecx, ecx; dwScope
0x180030e24  call    cs:__imp_SCardEstablishContext
0x180030e2a  mov     edi, eax
0x180030e2c  test    eax, eax
0x180030e2e  jnz     loc_180030F4B
0x180030e34  mov     rcx, [rbp+phContext]; hContext
0x180030e38  lea     r9, [rbp+pcchReaders]; pcchReaders
0x180030e3c  xor     r8d, r8d; mszReaders
0x180030e3f  xor     edx, edx; mszGroups
0x180030e41  call    cs:__imp_SCardListReadersW
0x180030e47  mov     edi, eax
0x180030e49  test    eax, eax
0x180030e4b  jnz     loc_180030F4B
0x180030e51  mov     eax, [rbp+pcchReaders]
0x180030e54  cmp     eax, 2
0x180030e57  jbe     loc_180030F46
0x180030e5d  lea     r15d, [rax+rax]
0x180030e61  call    cs:__imp_GetProcessHeap
0x180030e67  mov     r8d, r15d; dwBytes
0x180030e6a  lea     edx, [rdi+8]; dwFlags
0x180030e6d  mov     rcx, rax; hHeap
0x180030e70  call    cs:__imp_HeapAlloc
0x180030e76  mov     rsi, rax
0x180030e79  test    rax, rax
0x180030e7c  jnz     short loc_180030E88
0x180030e7e  mov     edi, 80100006h
0x180030e83  jmp     loc_180030F4B
0x180030e88  mov     rcx, [rbp+phContext]; hContext
0x180030e8c  lea     r9, [rbp+pcchReaders]; pcchReaders
0x180030e90  mov     r8, rsi; mszReaders
0x180030e93  xor     edx, edx; mszGroups
0x180030e95  call    cs:__imp_SCardListReadersW
0x180030e9b  mov     edi, eax
0x180030e9d  test    eax, eax
0x180030e9f  jnz     loc_180030F4B
0x180030ea5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030ea9  mov     r14, rsi
0x180030eac  cmp     [rsi], r13w
0x180030eb0  jz      short loc_180030EFE
0x180030eb2  mov     rcx, [rbp+phContext]; hContext
0x180030eb6  lea     rax, [rbp+arg_10]
0x180030eba  mov     [rsp+40h+pdwActiveProtocol], rax; pdwActiveProtocol
0x180030ebf  mov     r9d, 3; dwPreferredProtocols
0x180030ec5  lea     rax, [rbp+hCard]
0x180030ec9  mov     rdx, r14; szReader
0x180030ecc  mov     [rsp+40h+phCard], rax; phCard
0x180030ed1  lea     r8d, [r9-1]; dwShareMode
0x180030ed5  call    cs:__imp_SCardConnectW
0x180030edb  mov     edi, eax
0x180030edd  test    eax, eax
0x180030edf  jz      short loc_180030EFE
0x180030ee1  mov     rax, rbx
0x180030ee4  inc     rax
0x180030ee7  cmp     [r14+rax*2], r13w
0x180030eec  jnz     short loc_180030EE4
0x180030eee  lea     r14, [r14+rax*2]
0x180030ef2  add     r14, 2
0x180030ef6  cmp     [r14], r13w
0x180030efa  jnz     short loc_180030EB2
0x180030efc  jmp     short loc_180030F4B
0x180030efe  inc     rbx
0x180030f01  cmp     [r14+rbx*2], r13w
0x180030f06  jnz     short loc_180030EFE
0x180030f08  lea     eax, [rbx+1]
0x180030f0b  mov     [rbp+pcchReaders], eax
0x180030f0e  lea     ebx, [r15+r15]
0x180030f12  call    cs:__imp_GetProcessHeap
0x180030f18  mov     r8d, ebx; dwBytes
0x180030f1b  mov     edx, 8; dwFlags
0x180030f20  mov     rcx, rax; hHeap
0x180030f23  call    cs:__imp_HeapAlloc
0x180030f29  mov     [r12], rax
0x180030f2d  test    rax, rax
0x180030f30  jz      loc_180030E7E
0x180030f36  mov     edx, [rbp+pcchReaders]; SizeInWords
0x180030f39  mov     r8, r14; Source
0x180030f3c  mov     rcx, rax; Destination
0x180030f3f  call    wcscpy_s
0x180030f44  jmp     short loc_180030F4B
0x180030f46  mov     edi, 80100017h
0x180030f4b  mov     rcx, [rbp+hCard]; hCard
0x180030f4f  test    rcx, rcx
0x180030f52  jz      short loc_180030F5C
0x180030f54  xor     edx, edx; dwDisposition
0x180030f56  call    cs:__imp_SCardDisconnect
0x180030f5c  test    rsi, rsi
0x180030f5f  jz      short loc_180030F75
0x180030f61  call    cs:__imp_GetProcessHeap
0x180030f67  mov     r8, rsi; lpMem
0x180030f6a  xor     edx, edx; dwFlags
0x180030f6c  mov     rcx, rax; hHeap
0x180030f6f  call    cs:__imp_HeapFree
0x180030f75  mov     rcx, [rbp+phContext]; hContext
0x180030f79  test    rcx, rcx
0x180030f7c  jz      short loc_180030F84
0x180030f7e  call    cs:__imp_SCardReleaseContext
0x180030f84  mov     rbx, [rsp+40h+arg_0]
0x180030f8c  mov     eax, edi
0x180030f8e  add     rsp, 40h
0x180030f92  pop     r15
0x180030f94  pop     r14
0x180030f96  pop     r13
0x180030f98  pop     r12
0x180030f9a  pop     rdi
0x180030f9b  pop     rsi
0x180030f9c  pop     rbp
0x180030f9d  retn
```
