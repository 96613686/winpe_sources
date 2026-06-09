# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x180025058`
- end: `0x18002537d`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `805`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800245fc`

## callees

- `0x1800039f0`
- `0x180003a14`
- `0x180006090`
- `0x18001c244`
- `0x18001c7a0`
- `0x180025058`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025241`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800252bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025241`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800252bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025233`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025233`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800250b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800250b0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002509d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002509d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800250a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002515f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800252dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025350`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800250a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002515f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800252dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025350`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025131`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800251c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025131`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800251c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800250f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025194`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800250f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025194`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800250c0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800250c0`
- `DMCmnUtils!UnicodeToMB` at `0x18002520f`
- `DMCmnUtils!UnicodeToMB` at `0x18002520f`

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
  volatile signed __int64 *v18; // rbx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpcbData; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v24; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *p_lpMem; // [rsp+58h] [rbp-A8h]
  char *v27; // [rsp+60h] [rbp-A0h] BYREF
  char v28; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v30[136]; // [rsp+C0h] [rbp-40h] BYREF

  byte_180051170 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(LPCWSTR *)((char *)&`DMGetKnownRegPath'::`2'::Paths + (IsStateSeparationEnabled != 0 ? 8 : 0)),
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
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v30, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      lpMem = 0;
      v24 = 0;
      p_lpMem = &lpMem;
      v27 = 0;
      v28 = 1;
      v4 = UnicodeToMB(v30, 0xFDE9u, &v27, &v24);
      if ( v28 )
      {
        v7 = *p_lpMem;
        *p_lpMem = v27;
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
        v13 = &byte_180051170;
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
    v18 = v17
        ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v17)
        : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v18,
      _InterlockedExchangeAdd64(v18 + 17, 0),
      &byte_180051170);
    if ( v18 )
      operator delete((void *)v18, (const struct std::nothrow_t *)0x90);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180025058  mov     [rsp-8+arg_0], rbx
0x18002505d  mov     [rsp-8+arg_8], rdi
0x180025062  push    rbp
0x180025063  lea     rbp, [rsp-0E0h]
0x18002506b  sub     rsp, 1E0h
0x180025072  mov     rax, cs:__security_cookie
0x180025079  xor     rax, rsp
0x18002507c  mov     [rbp+0E0h+var_10], rax
0x180025083  mov     [rsp+1E0h+hKey], 0
0x18002508c  mov     cs:byte_180051170, 0
0x180025093  mov     rdi, [rsp+1E0h+hKey]
0x180025098  test    rdi, rdi
0x18002509b  jz      short loc_1800250B7
0x18002509d  call    cs:__imp_GetLastError
0x1800250a3  mov     ebx, eax
0x1800250a5  mov     rcx, rdi; hKey
0x1800250a8  call    cs:__imp_RegCloseKey
0x1800250ae  mov     ecx, ebx; dwErrCode
0x1800250b0  call    cs:__imp_SetLastError
0x1800250b6  nop
0x1800250b7  mov     [rsp+1E0h+hKey], 0
0x1800250c0  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800250c6  neg     al
0x1800250c8  sbb     rdx, rdx
0x1800250cb  and     edx, 8
0x1800250ce  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x1800250d5  lea     rax, [rsp+1E0h+hKey]
0x1800250da  mov     [rsp+1E0h+phkResult], rax; phkResult
0x1800250df  mov     r9d, 20019h; samDesired
0x1800250e5  xor     r8d, r8d; ulOptions
0x1800250e8  mov     rdx, [rdx+rcx]; lpSubKey
0x1800250ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800250f3  call    cs:__imp_RegOpenKeyExW
0x1800250f9  mov     ebx, eax
0x1800250fb  test    eax, eax
0x1800250fd  jnz     loc_1800252E5
0x180025103  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x18002510b  lea     rax, [rsp+1E0h+cbData]
0x180025110  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180025115  lea     rax, [rsp+1E0h+Data]
0x18002511a  mov     [rsp+1E0h+phkResult], rax; lpData
0x18002511f  xor     r9d, r9d; lpType
0x180025122  xor     r8d, r8d; lpReserved
0x180025125  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18002512c  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180025131  call    cs:__imp_RegQueryValueExW
0x180025137  mov     ebx, eax
0x180025139  test    eax, eax
0x18002513b  jnz     loc_1800252E5
0x180025141  mov     [rsp+1E0h+var_1A8], 0
0x18002514a  mov     rdi, [rsp+1E0h+var_1A8]
0x18002514f  test    rdi, rdi
0x180025152  jz      short loc_18002516E
0x180025154  call    cs:__imp_GetLastError
0x18002515a  mov     ebx, eax
0x18002515c  mov     rcx, rdi; hKey
0x18002515f  call    cs:__imp_RegCloseKey
0x180025165  mov     ecx, ebx; dwErrCode
0x180025167  call    cs:__imp_SetLastError
0x18002516d  nop
0x18002516e  mov     [rsp+1E0h+var_1A8], 0
0x180025177  lea     rax, [rsp+1E0h+var_1A8]
0x18002517c  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180025181  mov     r9d, 20019h; samDesired
0x180025187  xor     r8d, r8d; ulOptions
0x18002518a  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x18002518f  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180025194  call    cs:__imp_RegOpenKeyExW
0x18002519a  mov     [rsp+1E0h+var_19C], 102h
0x1800251a2  lea     rax, [rsp+1E0h+var_19C]
0x1800251a7  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800251ac  lea     rax, [rbp+0E0h+var_120]
0x1800251b0  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800251b5  xor     r9d, r9d; lpType
0x1800251b8  xor     r8d, r8d; lpReserved
0x1800251bb  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x1800251c2  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x1800251c7  call    cs:__imp_RegQueryValueExW
0x1800251cd  mov     ebx, eax
0x1800251cf  test    eax, eax
0x1800251d1  jnz     loc_1800252C7
0x1800251d7  mov     [rsp+1E0h+lpMem], 0
0x1800251e0  mov     [rsp+1E0h+var_198], eax
0x1800251e4  lea     rax, [rsp+1E0h+lpMem]
0x1800251e9  mov     [rsp+1E0h+var_188], rax
0x1800251ee  mov     [rsp+1E0h+var_180], 0
0x1800251f7  mov     [rsp+1E0h+var_178], 1
0x1800251fc  lea     r9, [rsp+1E0h+var_198]
0x180025201  lea     r8, [rsp+1E0h+var_180]
0x180025206  mov     edx, 0FDE9h
0x18002520b  lea     rcx, [rbp+0E0h+var_120]
0x18002520f  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180025215  mov     ebx, eax
0x180025217  cmp     [rsp+1E0h+var_178], 0
0x18002521c  jz      short loc_180025247
0x18002521e  mov     rdx, [rsp+1E0h+var_188]
0x180025223  mov     rdi, [rdx]
0x180025226  mov     rcx, [rsp+1E0h+var_180]
0x18002522b  mov     [rdx], rcx
0x18002522e  test    rdi, rdi
0x180025231  jz      short loc_180025247
0x180025233  call    cs:__imp_GetProcessHeap
0x180025239  mov     rcx, rax; hHeap
0x18002523c  mov     r8, rdi; lpMem
0x18002523f  xor     edx, edx; dwFlags
0x180025241  call    cs:__imp_HeapFree
0x180025247  mov     rdi, [rsp+1E0h+lpMem]
0x18002524c  test    ebx, ebx
0x18002524e  js      short loc_1800252A3
0x180025250  test    rdi, rdi
0x180025253  jz      short loc_1800252A3
0x180025255  mov     eax, 7FFFFFFEh
0x18002525a  mov     r8, rdi
0x18002525d  mov     ecx, 81h
0x180025262  lea     rdx, byte_180051170
0x180025269  test    rax, rax
0x18002526c  jz      short loc_180025288
0x18002526e  mov     r9b, [r8]
0x180025271  test    r9b, r9b
0x180025274  jz      short loc_180025288
0x180025276  inc     r8
0x180025279  mov     [rdx], r9b
0x18002527c  inc     rdx
0x18002527f  dec     rax
0x180025282  sub     rcx, 1
0x180025286  jnz     short loc_180025269
0x180025288  lea     rax, [rdx-1]
0x18002528c  test    rcx, rcx
0x18002528f  cmovnz  rax, rdx
0x180025293  mov     byte ptr [rax], 0
0x180025296  neg     rcx
0x180025299  sbb     ebx, ebx
0x18002529b  not     ebx
0x18002529d  and     ebx, 8007007Ah
0x1800252a3  mov     [rsp+1E0h+lpMem], 0
0x1800252ac  test    rdi, rdi
0x1800252af  jz      short loc_1800252D2
0x1800252b1  call    cs:__imp_GetProcessHeap
0x1800252b7  mov     rcx, rax; hHeap
0x1800252ba  mov     r8, rdi; lpMem
0x1800252bd  xor     edx, edx; dwFlags
0x1800252bf  call    cs:__imp_HeapFree
0x1800252c5  jmp     short loc_1800252D2
0x1800252c7  jle     short loc_1800252D2
0x1800252c9  movzx   ebx, ax
0x1800252cc  or      ebx, 80070000h
0x1800252d2  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x1800252d7  test    rcx, rcx
0x1800252da  jz      short loc_1800252E3
0x1800252dc  call    cs:__imp_RegCloseKey
0x1800252e2  nop
0x1800252e3  jmp     short loc_1800252F0
0x1800252e5  jle     short loc_1800252F0
0x1800252e7  movzx   ebx, ax
0x1800252ea  or      ebx, 80070000h
0x1800252f0  test    ebx, ebx
0x1800252f2  jns     short loc_180025346
0x1800252f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800252fb  mov     edi, 90h
0x180025300  mov     ecx, edi; unsigned __int64
0x180025302  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025307  test    rax, rax
0x18002530a  jz      short loc_180025319
0x18002530c  mov     rcx, rax
0x18002530f  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180025314  mov     rbx, rax
0x180025317  jmp     short loc_18002531B
0x180025319  xor     ebx, ebx
0x18002531b  xor     edx, edx
0x18002531d  lock xadd [rbx+88h], rdx; unsigned __int64
0x180025326  lea     r8, byte_180051170; char *
0x18002532d  mov     rcx, rbx; this
0x180025330  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180025335  test    rbx, rbx
0x180025338  jz      short loc_180025346
0x18002533a  mov     rdx, rdi; struct std::nothrow_t *
0x18002533d  mov     rcx, rbx; void *
0x180025340  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180025345  nop
0x180025346  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18002534b  test    rcx, rcx
0x18002534e  jz      short loc_180025357
0x180025350  call    cs:__imp_RegCloseKey
0x180025356  nop
0x180025357  xor     eax, eax
0x180025359  mov     rcx, [rbp+0E0h+var_10]
0x180025360  xor     rcx, rsp; StackCookie
0x180025363  call    __security_check_cookie
0x180025368  lea     r11, [rsp+1E0h+var_s0]
0x180025370  mov     rbx, [r11+10h]
0x180025374  mov     rdi, [r11+18h]
0x180025378  mov     rsp, r11
0x18002537b  pop     rbp
0x18002537c  retn
```
