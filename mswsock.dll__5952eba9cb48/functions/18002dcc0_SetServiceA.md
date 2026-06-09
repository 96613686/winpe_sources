# SetServiceA

- ea: `0x18002dcc0`
- end: `0x18002dee7`
- name: `SetServiceA`
- size: `551`
- prototype: `INT __stdcall(DWORD dwNameSpace, DWORD dwOperation, DWORD dwFlags, LPSERVICE_INFOA lpServiceInfo, LPSERVICE_ASYNC_INFO lpServiceAsyncInfo, LPDWORD lpdwStatusFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002cffc`
- `0x18002dcc0`
- `0x18002df24`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002de40`
- `ntdll!RtlFreeHeap` at `0x18002de5e`
- `ntdll!RtlFreeHeap` at `0x18002de7b`
- `ntdll!RtlFreeHeap` at `0x18002de98`
- `ntdll!RtlFreeHeap` at `0x18002deb0`
- `ntdll!RtlFreeHeap` at `0x18002de40`
- `ntdll!RtlFreeHeap` at `0x18002de5e`
- `ntdll!RtlFreeHeap` at `0x18002de7b`
- `ntdll!RtlFreeHeap` at `0x18002de98`
- `ntdll!RtlFreeHeap` at `0x18002deb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dd08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dec2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dd08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002dec2`

## pseudocode

```c
INT __stdcall SetServiceA(
        DWORD dwNameSpace,
        DWORD dwOperation,
        DWORD dwFlags,
        LPSERVICE_INFOA lpServiceInfo,
        LPSERVICE_ASYNC_INFO lpServiceAsyncInfo,
        LPDWORD lpdwStatusFlags)
{
  INT v8; // r14d
  __m128i *HeapRoutine; // r12
  DWORD UnicodeString; // ebx

  if ( lpServiceInfo )
  {
    v8 = 0;
    HeapRoutine = (__m128i *)SockAllocateHeapRoutine(SockPrivateHeap, 0, 80);
    if ( HeapRoutine )
    {
      UnicodeString = AllocateUnicodeString(lpServiceInfo->lpServiceName);
      if ( !UnicodeString )
      {
        UnicodeString = AllocateUnicodeString(lpServiceInfo->lpComment);
        if ( !UnicodeString )
        {
          UnicodeString = AllocateUnicodeString(lpServiceInfo->lpLocale);
          if ( !UnicodeString )
          {
            UnicodeString = AllocateUnicodeString(lpServiceInfo->lpMachineName);
            if ( !UnicodeString )
            {
              HeapRoutine->m128i_i64[0] = (__int64)lpServiceInfo->lpServiceType;
              HeapRoutine[1].m128i_i64[0] = 0;
              HeapRoutine->m128i_i64[1] = 0;
              HeapRoutine[1].m128i_i64[1] = 0;
              HeapRoutine[2].m128i_i32[0] = lpServiceInfo->dwDisplayHint;
              HeapRoutine[2].m128i_i32[1] = lpServiceInfo->dwVersion;
              HeapRoutine[2].m128i_i32[2] = lpServiceInfo->dwTime;
              HeapRoutine[3].m128i_i64[0] = 0;
              HeapRoutine[3].m128i_i64[1] = (__int64)lpServiceInfo->lpServiceAddress;
              HeapRoutine[4].m128i_i32[0] = lpServiceInfo->ServiceSpecificInfo.cbSize;
              HeapRoutine[4].m128i_i64[1] = (__int64)lpServiceInfo->ServiceSpecificInfo.pBlobData;
              v8 = SetServiceWorker(
                     dwNameSpace,
                     dwOperation,
                     dwFlags,
                     HeapRoutine,
                     (__int64)lpServiceAsyncInfo,
                     0,
                     lpdwStatusFlags);
            }
          }
        }
      }
      RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
      if ( UnicodeString )
      {
        SetLastError(UnicodeString);
        return -1;
      }
    }
    return v8;
  }
  else
  {
    SetLastError(0x57u);
    return -1;
  }
}

```

## disassembly

```asm
0x18002dcc0  mov     [rsp-40h+arg_10], r8d
0x18002dcc5  mov     [rsp-40h+arg_8], edx
0x18002dcc9  mov     [rsp-40h+arg_0], ecx
0x18002dccd  push    rbp
0x18002dcce  push    rbx
0x18002dccf  push    rsi
0x18002dcd0  push    rdi
0x18002dcd1  push    r12
0x18002dcd3  push    r13
0x18002dcd5  push    r14
0x18002dcd7  push    r15
0x18002dcd9  mov     rbp, rsp
0x18002dcdc  sub     rsp, 68h
0x18002dce0  xor     esi, esi
0x18002dce2  mov     [rbp+P], 0
0x18002dcea  xor     r15d, r15d
0x18002dced  mov     [rbp+var_20], 0
0x18002dcf5  mov     [rbp+arg_18], rsi
0x18002dcf9  mov     rdi, r9
0x18002dcfc  mov     [rbp+var_28], r15
0x18002dd00  test    r9, r9
0x18002dd03  jnz     short loc_18002DD1C
0x18002dd05  lea     ecx, [rsi+57h]; dwErrCode
0x18002dd08  call    cs:__imp_SetLastError
0x18002dd0f  nop     dword ptr [rax+rax+00h]
0x18002dd14  or      eax, 0FFFFFFFFh
0x18002dd17  jmp     loc_18002DED5
0x18002dd1c  mov     rcx, cs:SockPrivateHeap
0x18002dd23  xor     r14d, r14d
0x18002dd26  mov     rax, cs:SockAllocateHeapRoutine
0x18002dd2d  xor     edx, edx
0x18002dd2f  lea     r8d, [r14+50h]
0x18002dd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd38  mov     r12, rax
0x18002dd3b  test    rax, rax
0x18002dd3e  jz      loc_18002DED2
0x18002dd44  mov     rcx, [rdi+8]; lpMultiByteStr
0x18002dd48  lea     rdx, [rbp+P]
0x18002dd4c  call    AllocateUnicodeString
0x18002dd51  mov     r13, [rbp+P]
0x18002dd55  mov     ebx, eax
0x18002dd57  test    eax, eax
0x18002dd59  jnz     loc_18002DE2F
0x18002dd5f  mov     rcx, [rdi+10h]; lpMultiByteStr
0x18002dd63  lea     rdx, [rbp+var_20]
0x18002dd67  call    AllocateUnicodeString
0x18002dd6c  mov     ebx, eax
0x18002dd6e  test    eax, eax
0x18002dd70  jnz     loc_18002DE2F
0x18002dd76  mov     rcx, [rdi+18h]; lpMultiByteStr
0x18002dd7a  lea     rdx, [rbp+arg_18]
0x18002dd7e  call    AllocateUnicodeString
0x18002dd83  mov     ebx, eax
0x18002dd85  test    eax, eax
0x18002dd87  jnz     loc_18002DE2B
0x18002dd8d  mov     rcx, [rdi+30h]; lpMultiByteStr
0x18002dd91  lea     rdx, [rbp+var_28]
0x18002dd95  call    AllocateUnicodeString
0x18002dd9a  mov     rsi, [rbp+arg_18]
0x18002dd9e  mov     ebx, eax
0x18002dda0  mov     r15, [rbp+var_28]
0x18002dda4  test    eax, eax
0x18002dda6  jnz     loc_18002DE2F
0x18002ddac  mov     rax, [rdi]
0x18002ddaf  mov     r9, r12
0x18002ddb2  mov     r8d, [rbp+arg_10]
0x18002ddb6  mov     edx, [rbp+arg_8]
0x18002ddb9  mov     ecx, [rbp+arg_0]
0x18002ddbc  mov     [r12], rax
0x18002ddc0  mov     rax, [rbp+var_20]
0x18002ddc4  mov     [r12+10h], rax
0x18002ddc9  mov     [r12+8], r13
0x18002ddce  mov     [r12+18h], rsi
0x18002ddd3  mov     eax, [rdi+20h]
0x18002ddd6  mov     [r12+20h], eax
0x18002dddb  mov     eax, [rdi+24h]
0x18002ddde  mov     [r12+24h], eax
0x18002dde3  mov     eax, [rdi+28h]
0x18002dde6  mov     [r12+28h], eax
0x18002ddeb  mov     [r12+30h], r15
0x18002ddf0  mov     rax, [rdi+38h]
0x18002ddf4  mov     [r12+38h], rax
0x18002ddf9  mov     eax, [rdi+40h]
0x18002ddfc  mov     [r12+40h], eax
0x18002de01  mov     rax, [rdi+48h]
0x18002de05  mov     [r12+48h], rax
0x18002de0a  mov     rax, [rbp+lpdwStatusFlags]
0x18002de0e  mov     [rsp+68h+var_38], rax
0x18002de13  mov     rax, [rbp+lpServiceAsyncInfo]
0x18002de17  mov     [rsp+68h+var_40], r14d
0x18002de1c  mov     [rsp+68h+var_48], rax
0x18002de21  call    SetServiceWorker
0x18002de26  mov     r14d, eax
0x18002de29  jmp     short loc_18002DE2F
0x18002de2b  mov     rsi, [rbp+arg_18]
0x18002de2f  test    r13, r13
0x18002de32  jz      short loc_18002DE4C
0x18002de34  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002de3b  mov     r8, r13; P
0x18002de3e  xor     edx, edx; Flags
0x18002de40  call    cs:__imp_RtlFreeHeap
0x18002de47  nop     dword ptr [rax+rax+00h]
0x18002de4c  mov     r8, [rbp+var_20]; P
0x18002de50  test    r8, r8
0x18002de53  jz      short loc_18002DE6A
0x18002de55  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002de5c  xor     edx, edx; Flags
0x18002de5e  call    cs:__imp_RtlFreeHeap
0x18002de65  nop     dword ptr [rax+rax+00h]
0x18002de6a  test    rsi, rsi
0x18002de6d  jz      short loc_18002DE87
0x18002de6f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002de76  mov     r8, rsi; P
0x18002de79  xor     edx, edx; Flags
0x18002de7b  call    cs:__imp_RtlFreeHeap
0x18002de82  nop     dword ptr [rax+rax+00h]
0x18002de87  test    r15, r15
0x18002de8a  jz      short loc_18002DEA4
0x18002de8c  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002de93  mov     r8, r15; P
0x18002de96  xor     edx, edx; Flags
0x18002de98  call    cs:__imp_RtlFreeHeap
0x18002de9f  nop     dword ptr [rax+rax+00h]
0x18002dea4  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002deab  mov     r8, r12; P
0x18002deae  xor     edx, edx; Flags
0x18002deb0  call    cs:__imp_RtlFreeHeap
0x18002deb7  nop     dword ptr [rax+rax+00h]
0x18002debc  test    ebx, ebx
0x18002debe  jz      short loc_18002DED2
0x18002dec0  mov     ecx, ebx; dwErrCode
0x18002dec2  call    cs:__imp_SetLastError
0x18002dec9  nop     dword ptr [rax+rax+00h]
0x18002dece  or      r14d, 0FFFFFFFFh
0x18002ded2  mov     eax, r14d
0x18002ded5  add     rsp, 68h
0x18002ded9  pop     r15
0x18002dedb  pop     r14
0x18002dedd  pop     r13
0x18002dedf  pop     r12
0x18002dee1  pop     rdi
0x18002dee2  pop     rsi
0x18002dee3  pop     rbx
0x18002dee4  pop     rbp
0x18002dee5  retn
```
