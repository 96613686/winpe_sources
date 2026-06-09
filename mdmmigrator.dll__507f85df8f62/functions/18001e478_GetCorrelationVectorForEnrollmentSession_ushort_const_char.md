# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x18001e478`
- end: `0x18001e796`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `798`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001dce8`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x18000360c`
- `0x18001dc54`
- `0x18001e38c`
- `0x18001e478`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e6d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e653`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e6d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e661`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e6df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e661`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e574`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e4d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e4d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e587`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e57f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e57f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e769`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e513`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e5b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e513`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e5b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e551`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e5e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e551`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e5e7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e4e0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e4e0`
- `DMCmnUtils!UnicodeToMB` at `0x18001e62f`
- `DMCmnUtils!UnicodeToMB` at `0x18001e62f`

## pseudocode

```c
__int64 __fastcall GetCorrelationVectorForEnrollmentSession(const unsigned __int16 *a1, char *a2)
{
  char IsStateSeparationEnabled; // al
  LSTATUS v3; // eax
  signed int v4; // ebx
  bool v5; // cc
  LSTATUS v6; // eax
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  void *v9; // rdi
  __int64 v10; // rax
  char *v11; // r8
  __int64 v12; // rcx
  char *v13; // rdx
  char v14; // r9
  char *v15; // rax
  HANDLE v16; // rax
  void *v17; // rax
  char *v18; // r8
  volatile signed __int64 *v19; // rbx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpcbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v25; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *p_lpMem; // [rsp+58h] [rbp-A8h]
  char *v28; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v31[136]; // [rsp+C0h] [rbp-40h] BYREF

  byte_18002B850 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3
    || (cbData = 78,
        v3 = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, &cbData),
        v4 = v3,
        v5 = v3 <= 0,
        v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    phkResult = 0;
    RegOpenKeyExW(hKey, Data, 0, 0x20019u, &phkResult);
    lpcbData = 258;
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v31, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      lpMem = 0;
      v25 = 0;
      p_lpMem = &lpMem;
      v28 = 0;
      v29 = 1;
      v4 = UnicodeToMB(v31, 0xFDE9u, &v28, &v25);
      if ( v29 )
      {
        v7 = *p_lpMem;
        *p_lpMem = v28;
        if ( v7 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
        }
      }
      v9 = lpMem;
      if ( v4 >= 0 && lpMem )
      {
        v10 = 2147483646;
        v11 = (char *)lpMem;
        v12 = 129;
        v13 = &byte_18002B850;
        do
        {
          if ( !v10 )
            break;
          v14 = *v11;
          if ( !*v11 )
            break;
          ++v11;
          *v13++ = v14;
          --v10;
          --v12;
        }
        while ( v12 );
        v15 = v13 - 1;
        if ( v12 )
          v15 = v13;
        *v15 = 0;
        v4 = v12 == 0 ? 0x8007007A : 0;
      }
      lpMem = 0;
      if ( v9 )
      {
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v9);
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( v4 < 0 )
  {
    v17 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v17
        ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v17)
        : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v19,
      _InterlockedExchangeAdd64(v19 + 17, 0),
      v18);
    if ( v19 )
      operator delete((void *)v19, (const struct std::nothrow_t *)0x90);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001e478  mov     [rsp-8+arg_0], rbx
0x18001e47d  mov     [rsp-8+arg_8], rdi
0x18001e482  push    rbp
0x18001e483  lea     rbp, [rsp-0E0h]
0x18001e48b  sub     rsp, 1E0h
0x18001e492  mov     rax, cs:__security_cookie
0x18001e499  xor     rax, rsp
0x18001e49c  mov     [rbp+0E0h+var_10], rax
0x18001e4a3  mov     [rsp+1E0h+hKey], 0
0x18001e4ac  mov     cs:byte_18002B850, 0
0x18001e4b3  mov     rdi, [rsp+1E0h+hKey]
0x18001e4b8  test    rdi, rdi
0x18001e4bb  jz      short loc_18001E4D7
0x18001e4bd  call    cs:__imp_GetLastError
0x18001e4c3  mov     ebx, eax
0x18001e4c5  mov     rcx, rdi; hKey
0x18001e4c8  call    cs:__imp_RegCloseKey
0x18001e4ce  mov     ecx, ebx; dwErrCode
0x18001e4d0  call    cs:__imp_SetLastError
0x18001e4d6  nop
0x18001e4d7  mov     [rsp+1E0h+hKey], 0
0x18001e4e0  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001e4e6  neg     al
0x18001e4e8  sbb     rdx, rdx
0x18001e4eb  and     edx, 8
0x18001e4ee  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x18001e4f5  lea     rax, [rsp+1E0h+hKey]
0x18001e4fa  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001e4ff  mov     r9d, 20019h; samDesired
0x18001e505  xor     r8d, r8d; ulOptions
0x18001e508  mov     rdx, [rdx+rcx]; lpSubKey
0x18001e50c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e513  call    cs:__imp_RegOpenKeyExW
0x18001e519  mov     ebx, eax
0x18001e51b  test    eax, eax
0x18001e51d  jnz     loc_18001E705
0x18001e523  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x18001e52b  lea     rax, [rsp+1E0h+cbData]
0x18001e530  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18001e535  lea     rax, [rsp+1E0h+Data]
0x18001e53a  mov     [rsp+1E0h+phkResult], rax; lpData
0x18001e53f  xor     r9d, r9d; lpType
0x18001e542  xor     r8d, r8d; lpReserved
0x18001e545  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18001e54c  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001e551  call    cs:__imp_RegQueryValueExW
0x18001e557  mov     ebx, eax
0x18001e559  test    eax, eax
0x18001e55b  jnz     loc_18001E705
0x18001e561  mov     [rsp+1E0h+var_1A8], 0
0x18001e56a  mov     rdi, [rsp+1E0h+var_1A8]
0x18001e56f  test    rdi, rdi
0x18001e572  jz      short loc_18001E58E
0x18001e574  call    cs:__imp_GetLastError
0x18001e57a  mov     ebx, eax
0x18001e57c  mov     rcx, rdi; hKey
0x18001e57f  call    cs:__imp_RegCloseKey
0x18001e585  mov     ecx, ebx; dwErrCode
0x18001e587  call    cs:__imp_SetLastError
0x18001e58d  nop
0x18001e58e  mov     [rsp+1E0h+var_1A8], 0
0x18001e597  lea     rax, [rsp+1E0h+var_1A8]
0x18001e59c  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001e5a1  mov     r9d, 20019h; samDesired
0x18001e5a7  xor     r8d, r8d; ulOptions
0x18001e5aa  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x18001e5af  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001e5b4  call    cs:__imp_RegOpenKeyExW
0x18001e5ba  mov     [rsp+1E0h+var_19C], 102h
0x18001e5c2  lea     rax, [rsp+1E0h+var_19C]
0x18001e5c7  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18001e5cc  lea     rax, [rbp+0E0h+var_120]
0x18001e5d0  mov     [rsp+1E0h+phkResult], rax; lpData
0x18001e5d5  xor     r9d, r9d; lpType
0x18001e5d8  xor     r8d, r8d; lpReserved
0x18001e5db  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x18001e5e2  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x18001e5e7  call    cs:__imp_RegQueryValueExW
0x18001e5ed  mov     ebx, eax
0x18001e5ef  test    eax, eax
0x18001e5f1  jnz     loc_18001E6E7
0x18001e5f7  mov     [rsp+1E0h+lpMem], 0
0x18001e600  mov     [rsp+1E0h+var_198], eax
0x18001e604  lea     rax, [rsp+1E0h+lpMem]
0x18001e609  mov     [rsp+1E0h+var_188], rax
0x18001e60e  mov     [rsp+1E0h+var_180], 0
0x18001e617  mov     [rsp+1E0h+var_178], 1
0x18001e61c  lea     r9, [rsp+1E0h+var_198]
0x18001e621  lea     r8, [rsp+1E0h+var_180]
0x18001e626  mov     edx, 0FDE9h
0x18001e62b  lea     rcx, [rbp+0E0h+var_120]
0x18001e62f  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x18001e635  mov     ebx, eax
0x18001e637  cmp     [rsp+1E0h+var_178], 0
0x18001e63c  jz      short loc_18001E667
0x18001e63e  mov     rdx, [rsp+1E0h+var_188]
0x18001e643  mov     rdi, [rdx]
0x18001e646  mov     rcx, [rsp+1E0h+var_180]
0x18001e64b  mov     [rdx], rcx
0x18001e64e  test    rdi, rdi
0x18001e651  jz      short loc_18001E667
0x18001e653  call    cs:__imp_GetProcessHeap
0x18001e659  mov     rcx, rax; hHeap
0x18001e65c  mov     r8, rdi; lpMem
0x18001e65f  xor     edx, edx; dwFlags
0x18001e661  call    cs:__imp_HeapFree
0x18001e667  mov     rdi, [rsp+1E0h+lpMem]
0x18001e66c  test    ebx, ebx
0x18001e66e  js      short loc_18001E6C3
0x18001e670  test    rdi, rdi
0x18001e673  jz      short loc_18001E6C3
0x18001e675  mov     eax, 7FFFFFFEh
0x18001e67a  mov     r8, rdi
0x18001e67d  mov     ecx, 81h
0x18001e682  lea     rdx, byte_18002B850
0x18001e689  test    rax, rax
0x18001e68c  jz      short loc_18001E6A8
0x18001e68e  mov     r9b, [r8]
0x18001e691  test    r9b, r9b
0x18001e694  jz      short loc_18001E6A8
0x18001e696  inc     r8
0x18001e699  mov     [rdx], r9b
0x18001e69c  inc     rdx
0x18001e69f  dec     rax
0x18001e6a2  sub     rcx, 1
0x18001e6a6  jnz     short loc_18001E689
0x18001e6a8  lea     rax, [rdx-1]
0x18001e6ac  test    rcx, rcx
0x18001e6af  cmovnz  rax, rdx
0x18001e6b3  mov     byte ptr [rax], 0
0x18001e6b6  neg     rcx
0x18001e6b9  sbb     ebx, ebx
0x18001e6bb  not     ebx
0x18001e6bd  and     ebx, 8007007Ah
0x18001e6c3  mov     [rsp+1E0h+lpMem], 0
0x18001e6cc  test    rdi, rdi
0x18001e6cf  jz      short loc_18001E6F2
0x18001e6d1  call    cs:__imp_GetProcessHeap
0x18001e6d7  mov     rcx, rax; hHeap
0x18001e6da  mov     r8, rdi; lpMem
0x18001e6dd  xor     edx, edx; dwFlags
0x18001e6df  call    cs:__imp_HeapFree
0x18001e6e5  jmp     short loc_18001E6F2
0x18001e6e7  jle     short loc_18001E6F2
0x18001e6e9  movzx   ebx, ax
0x18001e6ec  or      ebx, 80070000h
0x18001e6f2  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x18001e6f7  test    rcx, rcx
0x18001e6fa  jz      short loc_18001E703
0x18001e6fc  call    cs:__imp_RegCloseKey
0x18001e702  nop
0x18001e703  jmp     short loc_18001E710
0x18001e705  jle     short loc_18001E710
0x18001e707  movzx   ebx, ax
0x18001e70a  or      ebx, 80070000h
0x18001e710  test    ebx, ebx
0x18001e712  jns     short loc_18001E75F
0x18001e714  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e71b  mov     edi, 90h
0x18001e720  mov     ecx, edi; unsigned __int64
0x18001e722  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e727  test    rax, rax
0x18001e72a  jz      short loc_18001E739
0x18001e72c  mov     rcx, rax
0x18001e72f  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18001e734  mov     rbx, rax
0x18001e737  jmp     short loc_18001E73B
0x18001e739  xor     ebx, ebx
0x18001e73b  xor     edx, edx
0x18001e73d  lock xadd [rbx+88h], rdx; unsigned __int64
0x18001e746  mov     rcx, rbx; this
0x18001e749  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001e74e  test    rbx, rbx
0x18001e751  jz      short loc_18001E75F
0x18001e753  mov     rdx, rdi; struct std::nothrow_t *
0x18001e756  mov     rcx, rbx; void *
0x18001e759  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e75e  nop
0x18001e75f  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001e764  test    rcx, rcx
0x18001e767  jz      short loc_18001E770
0x18001e769  call    cs:__imp_RegCloseKey
0x18001e76f  nop
0x18001e770  xor     eax, eax
0x18001e772  mov     rcx, [rbp+0E0h+var_10]
0x18001e779  xor     rcx, rsp; StackCookie
0x18001e77c  call    __security_check_cookie
0x18001e781  lea     r11, [rsp+1E0h+var_s0]
0x18001e789  mov     rbx, [r11+10h]
0x18001e78d  mov     rdi, [r11+18h]
0x18001e791  mov     rsp, r11
0x18001e794  pop     rbp
0x18001e795  retn
```
