# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x180044afc`
- end: `0x180044e8e`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `914`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180041410`

## callees

- `0x1800026d0`
- `0x180002710`
- `0x180002ae0`
- `0x180041370`
- `0x180044620`
- `0x180044afc`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180044b76`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180044b76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044d33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044dbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044d33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044d1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044da9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044d1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044c3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044c3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044b52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044de0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044e5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044b52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044c2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044de0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044e5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044baf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044c6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044baf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044c6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044bf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044ca7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044bf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044ca7`
- `DMCmnUtils!UnicodeToMB` at `0x180044cf5`
- `DMCmnUtils!UnicodeToMB` at `0x180044cf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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

  byte_180070F10 = 0;
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
        v13 = &byte_180070F10;
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
    v18 = v17 ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v17) : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v18,
      _InterlockedExchangeAdd64(v18 + 17, 0),
      &byte_180070F10);
    if ( v18 )
      operator delete((void *)v18);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180044afc  mov     [rsp-8+arg_0], rbx
0x180044b01  mov     [rsp-8+arg_8], rdi
0x180044b06  push    rbp
0x180044b07  lea     rbp, [rsp-0E0h]
0x180044b0f  sub     rsp, 1E0h
0x180044b16  mov     rax, cs:__security_cookie
0x180044b1d  xor     rax, rsp
0x180044b20  mov     [rbp+0E0h+var_10], rax
0x180044b27  mov     [rsp+1E0h+hKey], 0
0x180044b30  mov     cs:byte_180070F10, 0
0x180044b37  mov     rdi, [rsp+1E0h+hKey]
0x180044b3c  test    rdi, rdi
0x180044b3f  jz      short loc_180044B6D
0x180044b41  call    cs:__imp_GetLastError
0x180044b48  nop     dword ptr [rax+rax+00h]
0x180044b4d  mov     ebx, eax
0x180044b4f  mov     rcx, rdi; hKey
0x180044b52  call    cs:__imp_RegCloseKey
0x180044b59  nop     dword ptr [rax+rax+00h]
0x180044b5e  mov     ecx, ebx; dwErrCode
0x180044b60  call    cs:__imp_SetLastError
0x180044b67  nop     dword ptr [rax+rax+00h]
0x180044b6c  nop
0x180044b6d  mov     [rsp+1E0h+hKey], 0
0x180044b76  call    cs:__imp_RtlIsStateSeparationEnabled
0x180044b7d  nop     dword ptr [rax+rax+00h]
0x180044b82  neg     al
0x180044b84  sbb     rdx, rdx
0x180044b87  and     edx, 8
0x180044b8a  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x180044b91  lea     rax, [rsp+1E0h+hKey]
0x180044b96  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180044b9b  mov     r9d, 20019h; samDesired
0x180044ba1  xor     r8d, r8d; ulOptions
0x180044ba4  mov     rdx, [rdx+rcx]; lpSubKey
0x180044ba8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044baf  call    cs:__imp_RegOpenKeyExW
0x180044bb6  nop     dword ptr [rax+rax+00h]
0x180044bbb  mov     ebx, eax
0x180044bbd  test    eax, eax
0x180044bbf  jnz     loc_180044DEF
0x180044bc5  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x180044bcd  lea     rax, [rsp+1E0h+cbData]
0x180044bd2  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180044bd7  lea     rax, [rsp+1E0h+Data]
0x180044bdc  mov     [rsp+1E0h+phkResult], rax; lpData
0x180044be1  xor     r9d, r9d; lpType
0x180044be4  xor     r8d, r8d; lpReserved
0x180044be7  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x180044bee  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180044bf3  call    cs:__imp_RegQueryValueExW
0x180044bfa  nop     dword ptr [rax+rax+00h]
0x180044bff  mov     ebx, eax
0x180044c01  test    eax, eax
0x180044c03  jnz     loc_180044DEF
0x180044c09  mov     [rsp+1E0h+var_1A8], 0
0x180044c12  mov     rdi, [rsp+1E0h+var_1A8]
0x180044c17  test    rdi, rdi
0x180044c1a  jz      short loc_180044C48
0x180044c1c  call    cs:__imp_GetLastError
0x180044c23  nop     dword ptr [rax+rax+00h]
0x180044c28  mov     ebx, eax
0x180044c2a  mov     rcx, rdi; hKey
0x180044c2d  call    cs:__imp_RegCloseKey
0x180044c34  nop     dword ptr [rax+rax+00h]
0x180044c39  mov     ecx, ebx; dwErrCode
0x180044c3b  call    cs:__imp_SetLastError
0x180044c42  nop     dword ptr [rax+rax+00h]
0x180044c47  nop
0x180044c48  mov     [rsp+1E0h+var_1A8], 0
0x180044c51  lea     rax, [rsp+1E0h+var_1A8]
0x180044c56  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180044c5b  mov     r9d, 20019h; samDesired
0x180044c61  xor     r8d, r8d; ulOptions
0x180044c64  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x180044c69  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180044c6e  call    cs:__imp_RegOpenKeyExW
0x180044c75  nop     dword ptr [rax+rax+00h]
0x180044c7a  mov     [rsp+1E0h+var_19C], 102h
0x180044c82  lea     rax, [rsp+1E0h+var_19C]
0x180044c87  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180044c8c  lea     rax, [rbp+0E0h+var_120]
0x180044c90  mov     [rsp+1E0h+phkResult], rax; lpData
0x180044c95  xor     r9d, r9d; lpType
0x180044c98  xor     r8d, r8d; lpReserved
0x180044c9b  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x180044ca2  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x180044ca7  call    cs:__imp_RegQueryValueExW
0x180044cae  nop     dword ptr [rax+rax+00h]
0x180044cb3  mov     ebx, eax
0x180044cb5  test    eax, eax
0x180044cb7  jnz     loc_180044DCB
0x180044cbd  mov     [rsp+1E0h+lpMem], 0
0x180044cc6  mov     [rsp+1E0h+var_198], eax
0x180044cca  lea     rax, [rsp+1E0h+lpMem]
0x180044ccf  mov     [rsp+1E0h+var_188], rax
0x180044cd4  mov     [rsp+1E0h+var_180], 0
0x180044cdd  mov     [rsp+1E0h+var_178], 1
0x180044ce2  lea     r9, [rsp+1E0h+var_198]
0x180044ce7  lea     r8, [rsp+1E0h+var_180]
0x180044cec  mov     edx, 0FDE9h
0x180044cf1  lea     rcx, [rbp+0E0h+var_120]
0x180044cf5  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180044cfc  nop     dword ptr [rax+rax+00h]
0x180044d01  mov     ebx, eax
0x180044d03  cmp     [rsp+1E0h+var_178], 0
0x180044d08  jz      short loc_180044D3F
0x180044d0a  mov     rdx, [rsp+1E0h+var_188]
0x180044d0f  mov     rdi, [rdx]
0x180044d12  mov     rcx, [rsp+1E0h+var_180]
0x180044d17  mov     [rdx], rcx
0x180044d1a  test    rdi, rdi
0x180044d1d  jz      short loc_180044D3F
0x180044d1f  call    cs:__imp_GetProcessHeap
0x180044d26  nop     dword ptr [rax+rax+00h]
0x180044d2b  mov     rcx, rax; hHeap
0x180044d2e  mov     r8, rdi; lpMem
0x180044d31  xor     edx, edx; dwFlags
0x180044d33  call    cs:__imp_HeapFree
0x180044d3a  nop     dword ptr [rax+rax+00h]
0x180044d3f  mov     rdi, [rsp+1E0h+lpMem]
0x180044d44  test    ebx, ebx
0x180044d46  js      short loc_180044D9B
0x180044d48  test    rdi, rdi
0x180044d4b  jz      short loc_180044D9B
0x180044d4d  mov     eax, 7FFFFFFEh
0x180044d52  mov     r8, rdi
0x180044d55  mov     ecx, 81h
0x180044d5a  lea     rdx, byte_180070F10
0x180044d61  test    rax, rax
0x180044d64  jz      short loc_180044D80
0x180044d66  mov     r9b, [r8]
0x180044d69  test    r9b, r9b
0x180044d6c  jz      short loc_180044D80
0x180044d6e  inc     r8
0x180044d71  mov     [rdx], r9b
0x180044d74  inc     rdx
0x180044d77  dec     rax
0x180044d7a  sub     rcx, 1
0x180044d7e  jnz     short loc_180044D61
0x180044d80  lea     rax, [rdx-1]
0x180044d84  test    rcx, rcx
0x180044d87  cmovnz  rax, rdx
0x180044d8b  mov     byte ptr [rax], 0
0x180044d8e  neg     rcx
0x180044d91  sbb     ebx, ebx
0x180044d93  not     ebx
0x180044d95  and     ebx, 8007007Ah
0x180044d9b  mov     [rsp+1E0h+lpMem], 0
0x180044da4  test    rdi, rdi
0x180044da7  jz      short loc_180044DD6
0x180044da9  call    cs:__imp_GetProcessHeap
0x180044db0  nop     dword ptr [rax+rax+00h]
0x180044db5  mov     rcx, rax; hHeap
0x180044db8  mov     r8, rdi; lpMem
0x180044dbb  xor     edx, edx; dwFlags
0x180044dbd  call    cs:__imp_HeapFree
0x180044dc4  nop     dword ptr [rax+rax+00h]
0x180044dc9  jmp     short loc_180044DD6
0x180044dcb  jle     short loc_180044DD6
0x180044dcd  movzx   ebx, ax
0x180044dd0  or      ebx, 80070000h
0x180044dd6  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x180044ddb  test    rcx, rcx
0x180044dde  jz      short loc_180044DED
0x180044de0  call    cs:__imp_RegCloseKey
0x180044de7  nop     dword ptr [rax+rax+00h]
0x180044dec  nop
0x180044ded  jmp     short loc_180044DFA
0x180044def  jle     short loc_180044DFA
0x180044df1  movzx   ebx, ax
0x180044df4  or      ebx, 80070000h
0x180044dfa  test    ebx, ebx
0x180044dfc  jns     short loc_180044E50
0x180044dfe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044e05  mov     edi, 90h
0x180044e0a  mov     ecx, edi; unsigned __int64
0x180044e0c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044e11  test    rax, rax
0x180044e14  jz      short loc_180044E23
0x180044e16  mov     rcx, rax
0x180044e19  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180044e1e  mov     rbx, rax
0x180044e21  jmp     short loc_180044E25
0x180044e23  xor     ebx, ebx
0x180044e25  xor     edx, edx
0x180044e27  lock xadd [rbx+88h], rdx; unsigned __int64
0x180044e30  lea     r8, byte_180070F10; char *
0x180044e37  mov     rcx, rbx; this
0x180044e3a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180044e3f  test    rbx, rbx
0x180044e42  jz      short loc_180044E50
0x180044e44  mov     rdx, rdi
0x180044e47  mov     rcx, rbx; Block
0x180044e4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044e4f  nop
0x180044e50  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180044e55  test    rcx, rcx
0x180044e58  jz      short loc_180044E67
0x180044e5a  call    cs:__imp_RegCloseKey
0x180044e61  nop     dword ptr [rax+rax+00h]
0x180044e66  nop
0x180044e67  xor     eax, eax
0x180044e69  mov     rcx, [rbp+0E0h+var_10]
0x180044e70  xor     rcx, rsp; StackCookie
0x180044e73  call    __security_check_cookie
0x180044e78  lea     r11, [rsp+1E0h+var_s0]
0x180044e80  mov     rbx, [r11+10h]
0x180044e84  mov     rdi, [r11+18h]
0x180044e88  mov     rsp, r11
0x180044e8b  pop     rbp
0x180044e8c  retn
```
