# GetAddressByNameA

- ea: `0x18002c410`
- end: `0x18002c652`
- name: `GetAddressByNameA`
- size: `578`
- prototype: `INT __stdcall(DWORD dwNameSpace, LPGUID lpServiceType, LPSTR lpServiceName, LPINT lpiProtocols, DWORD dwResolution, LPSERVICE_ASYNC_INFO lpServiceAsyncInfo, LPVOID lpCsaddrBuffer, LPDWORD lpdwBufferLength, LPSTR lpAliasBuffer, LPDWORD lpdwAliasBufferLength)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002c410`
- `0x18002c660`
- `0x180053010`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18002c5b5`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18002c5b5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002c474`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002c474`
- `ntdll!RtlNtStatusToDosError` at `0x18002c486`
- `ntdll!RtlNtStatusToDosError` at `0x18002c486`
- `ntdll!RtlInitAnsiString` at `0x18002c45d`
- `ntdll!RtlInitAnsiString` at `0x18002c45d`
- `ntdll!RtlFreeUnicodeString` at `0x18002c4ed`
- `ntdll!RtlFreeUnicodeString` at `0x18002c605`
- `ntdll!RtlFreeUnicodeString` at `0x18002c4ed`
- `ntdll!RtlFreeUnicodeString` at `0x18002c605`
- `ntdll!RtlInitUnicodeString` at `0x18002c591`
- `ntdll!RtlInitUnicodeString` at `0x18002c591`
- `ntdll!RtlFreeHeap` at `0x18002c625`
- `ntdll!RtlFreeHeap` at `0x18002c625`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c494`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c4fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c494`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c4fe`

## pseudocode

```c
INT __stdcall GetAddressByNameA(
        DWORD dwNameSpace,
        LPGUID lpServiceType,
        LPSTR lpServiceName,
        LPINT lpiProtocols,
        DWORD dwResolution,
        LPSERVICE_ASYNC_INFO lpServiceAsyncInfo,
        LPVOID lpCsaddrBuffer,
        LPDWORD lpdwBufferLength,
        LPSTR lpAliasBuffer,
        LPDWORD lpdwAliasBufferLength)
{
  WCHAR *v10; // rsi
  int v14; // eax
  DWORD v15; // eax
  WCHAR *Buffer; // rdi
  USHORT *v18; // r12
  int AddressByNameW; // r13d
  const WCHAR *v20; // r14
  CHAR *i; // rdi
  __int64 v22; // rax
  __int64 v23; // rax
  struct _STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-20h] BYREF
  UNICODE_STRING SourceString; // [rsp+70h] [rbp-10h] BYREF
  DWORD dwAliasBufferLength; // [rsp+C0h] [rbp+40h] BYREF

  v10 = 0;
  dwAliasBufferLength = 0;
  DestinationString = 0;
  SourceString = 0;
  UnicodeString = 0;
  if ( lpServiceName )
  {
    RtlInitAnsiString(&DestinationString, lpServiceName);
    v14 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
    if ( v14 < 0 )
    {
      v15 = RtlNtStatusToDosError(v14);
      SetLastError(v15);
      return -1;
    }
    Buffer = UnicodeString.Buffer;
  }
  else
  {
    Buffer = 0;
  }
  v18 = (USHORT *)lpdwAliasBufferLength;
  if ( lpAliasBuffer )
  {
    dwAliasBufferLength = 2 * *lpdwAliasBufferLength;
    v10 = (WCHAR *)((__int64 (__fastcall *)(HANDLE, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0);
    if ( !v10 )
    {
      if ( lpServiceName )
        RtlFreeUnicodeString(&UnicodeString);
      SetLastError(8u);
      return 0;
    }
  }
  else
  {
    dwAliasBufferLength = 0;
  }
  AddressByNameW = GetAddressByNameW(
                     dwNameSpace,
                     lpServiceType,
                     Buffer,
                     lpiProtocols,
                     dwResolution,
                     lpServiceAsyncInfo,
                     lpCsaddrBuffer,
                     lpdwBufferLength,
                     v10,
                     &dwAliasBufferLength);
  if ( AddressByNameW > 0 && lpAliasBuffer )
  {
    v20 = v10;
    for ( i = lpAliasBuffer; *v20; v20 += v23 + 1 )
    {
      if ( i - lpAliasBuffer >= (unsigned __int64)(unsigned int)(*(_DWORD *)v18 - 1) )
        break;
      RtlInitUnicodeString(&SourceString, v20);
      DestinationString.MaximumLength = *v18;
      DestinationString.Buffer = i;
      RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
      v22 = -1;
      do
        ++v22;
      while ( i[v22] );
      i += v22 + 1;
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
    }
    *i = 0;
    *(_DWORD *)v18 = dwAliasBufferLength >> 1;
  }
  if ( lpServiceName )
    RtlFreeUnicodeString(&UnicodeString);
  if ( lpAliasBuffer )
    RtlFreeHeap(SockPrivateHeap, 0, v10);
  return AddressByNameW;
}

```

## disassembly

```asm
0x18002c410  mov     [rsp-28h+arg_8], rsi
0x18002c415  mov     [rsp-28h+arg_18], rdi
0x18002c41a  mov     [rsp-28h+dwNameSpace], ecx
0x18002c41e  push    rbp
0x18002c41f  push    r12
0x18002c421  push    r13
0x18002c423  push    r14
0x18002c425  push    r15
0x18002c427  mov     rbp, rsp
0x18002c42a  sub     rsp, 80h
0x18002c431  xor     esi, esi
0x18002c433  xorps   xmm0, xmm0
0x18002c436  mov     [rbp+dwAliasBufferLength], esi
0x18002c439  xorps   xmm1, xmm1
0x18002c43c  mov     r14, r9
0x18002c43f  mov     r15, r8
0x18002c442  mov     r13, rdx
0x18002c445  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002c449  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x18002c44d  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18002c451  test    r8, r8
0x18002c454  jz      short loc_18002C4AE
0x18002c456  mov     rdx, r8; SourceString
0x18002c459  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c45d  call    cs:__imp_RtlInitAnsiString
0x18002c464  nop     dword ptr [rax+rax+00h]
0x18002c469  mov     r8b, 1; AllocateDestinationString
0x18002c46c  lea     rdx, [rbp+DestinationString]; SourceString
0x18002c470  lea     rcx, [rbp+UnicodeString]; DestinationString
0x18002c474  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18002c47b  nop     dword ptr [rax+rax+00h]
0x18002c480  test    eax, eax
0x18002c482  jns     short loc_18002C4A8
0x18002c484  mov     ecx, eax; Status
0x18002c486  call    cs:__imp_RtlNtStatusToDosError
0x18002c48d  nop     dword ptr [rax+rax+00h]
0x18002c492  mov     ecx, eax; dwErrCode
0x18002c494  call    cs:__imp_SetLastError
0x18002c49b  nop     dword ptr [rax+rax+00h]
0x18002c4a0  or      eax, 0FFFFFFFFh
0x18002c4a3  jmp     loc_18002C634
0x18002c4a8  mov     rdi, [rbp+UnicodeString.Buffer]
0x18002c4ac  jmp     short loc_18002C4B1
0x18002c4ae  mov     rdi, rsi
0x18002c4b1  mov     r12, [rbp+lpdwAliasBufferLength]
0x18002c4b5  cmp     [rbp+lpAliasBuffer], rsi
0x18002c4b9  jz      short loc_18002C511
0x18002c4bb  mov     eax, [r12]
0x18002c4bf  xor     edx, edx
0x18002c4c1  mov     rcx, cs:SockPrivateHeap
0x18002c4c8  lea     r8d, [rax+rax]
0x18002c4cc  mov     rax, cs:SockAllocateHeapRoutine
0x18002c4d3  mov     [rbp+dwAliasBufferLength], r8d
0x18002c4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4dc  mov     rsi, rax
0x18002c4df  test    rax, rax
0x18002c4e2  jnz     short loc_18002C514
0x18002c4e4  test    r15, r15
0x18002c4e7  jz      short loc_18002C4F9
0x18002c4e9  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002c4ed  call    cs:__imp_RtlFreeUnicodeString
0x18002c4f4  nop     dword ptr [rax+rax+00h]
0x18002c4f9  mov     ecx, 8; dwErrCode
0x18002c4fe  call    cs:__imp_SetLastError
0x18002c505  nop     dword ptr [rax+rax+00h]
0x18002c50a  xor     eax, eax
0x18002c50c  jmp     loc_18002C634
0x18002c511  mov     [rbp+dwAliasBufferLength], esi
0x18002c514  mov     ecx, [rbp+dwNameSpace]; dwNameSpace
0x18002c517  lea     rax, [rbp+dwAliasBufferLength]
0x18002c51b  mov     [rsp+80h+var_38], rax; lpdwAliasBufferLength
0x18002c520  mov     r9, r14; lpiProtocols
0x18002c523  mov     rax, [rbp+lpdwBufferLength]
0x18002c527  mov     r8, rdi; lpServiceName
0x18002c52a  mov     [rsp+80h+var_40], rsi; lpAliasBuffer
0x18002c52f  mov     rdx, r13; lpServiceType
0x18002c532  mov     [rsp+80h+var_48], rax; lpdwBufferLength
0x18002c537  mov     rax, [rbp+lpCsaddrBuffer]
0x18002c53b  mov     [rsp+80h+var_50], rax; lpCsaddrBuffer
0x18002c540  mov     rax, [rbp+lpServiceAsyncInfo]
0x18002c544  mov     [rsp+80h+var_58], rax; lpServiceAsyncInfo
0x18002c549  mov     eax, [rbp+dwResolution]
0x18002c54c  mov     [rsp+80h+var_60], eax; dwResolution
0x18002c550  call    GetAddressByNameW
0x18002c555  xor     edx, edx
0x18002c557  mov     r13d, eax
0x18002c55a  test    eax, eax
0x18002c55c  jle     loc_18002C5FC
0x18002c562  cmp     [rbp+lpAliasBuffer], rdx
0x18002c566  jz      loc_18002C5FC
0x18002c56c  mov     r14, rsi
0x18002c56f  mov     rdi, [rbp+lpAliasBuffer]
0x18002c573  cmp     [rsi], dx
0x18002c576  jz      short loc_18002C5F1
0x18002c578  mov     ecx, [r12]
0x18002c57c  mov     rax, rdi
0x18002c57f  sub     rax, [rbp+lpAliasBuffer]
0x18002c583  dec     ecx
0x18002c585  cmp     rax, rcx
0x18002c588  jnb     short loc_18002C5F1
0x18002c58a  mov     rdx, r14; SourceString
0x18002c58d  lea     rcx, [rbp+SourceString]; DestinationString
0x18002c591  call    cs:__imp_RtlInitUnicodeString
0x18002c598  nop     dword ptr [rax+rax+00h]
0x18002c59d  movzx   eax, word ptr [r12]
0x18002c5a2  lea     rdx, [rbp+SourceString]; SourceString
0x18002c5a6  xor     r8d, r8d; AllocateDestinationString
0x18002c5a9  mov     [rbp+DestinationString.MaximumLength], ax
0x18002c5ad  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c5b1  mov     [rbp+DestinationString.Buffer], rdi
0x18002c5b5  call    cs:__imp_RtlUnicodeStringToAnsiString
0x18002c5bc  nop     dword ptr [rax+rax+00h]
0x18002c5c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c5c5  xor     edx, edx
0x18002c5c7  inc     rax
0x18002c5ca  cmp     [rdi+rax], dl
0x18002c5cd  jnz     short loc_18002C5C7
0x18002c5cf  inc     rax
0x18002c5d2  add     rdi, rax
0x18002c5d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c5d9  inc     rax
0x18002c5dc  cmp     [r14+rax*2], dx
0x18002c5e1  jnz     short loc_18002C5D9
0x18002c5e3  lea     r14, [r14+rax*2]
0x18002c5e7  add     r14, 2
0x18002c5eb  cmp     [r14], dx
0x18002c5ef  jnz     short loc_18002C578
0x18002c5f1  mov     [rdi], dl
0x18002c5f3  mov     eax, [rbp+dwAliasBufferLength]
0x18002c5f6  shr     eax, 1
0x18002c5f8  mov     [r12], eax
0x18002c5fc  test    r15, r15
0x18002c5ff  jz      short loc_18002C613
0x18002c601  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18002c605  call    cs:__imp_RtlFreeUnicodeString
0x18002c60c  nop     dword ptr [rax+rax+00h]
0x18002c611  xor     edx, edx
0x18002c613  cmp     [rbp+lpAliasBuffer], rdx
0x18002c617  jz      short loc_18002C631
0x18002c619  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002c620  mov     r8, rsi; P
0x18002c623  xor     edx, edx; Flags
0x18002c625  call    cs:__imp_RtlFreeHeap
0x18002c62c  nop     dword ptr [rax+rax+00h]
0x18002c631  mov     eax, r13d
0x18002c634  lea     r11, [rsp+80h+var_s0]
0x18002c63c  mov     rsi, [r11+38h]
0x18002c640  mov     rdi, [r11+48h]
0x18002c644  mov     rsp, r11
0x18002c647  pop     r15
0x18002c649  pop     r14
0x18002c64b  pop     r13
0x18002c64d  pop     r12
0x18002c64f  pop     rbp
0x18002c650  retn
```
