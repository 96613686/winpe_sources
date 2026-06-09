# KerbAllocateLogonSession(_LUID *,_KERB_LOGON_SESSION * *)

- ea: `0x180005aa0`
- end: `0x180005c81`
- name: `?KerbAllocateLogonSession@@YAJPEAU_LUID@@PEAPEAU_KERB_LOGON_SESSION@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(struct _LUID *, struct _KERB_LOGON_SESSION **)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048cf0`
- `0x180048f6c`
- `0x18008f6b8`

## callees

- `0x180005aa0`
- `0x1800069a0`
- `0x180032964`
- `0x18007108c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b27`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b27`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c4f`
- `ntdll!RtlDeleteCriticalSection` at `0x180005c06`
- `ntdll!RtlDeleteCriticalSection` at `0x180005c16`
- `ntdll!RtlDeleteCriticalSection` at `0x180005c26`
- `ntdll!RtlDeleteCriticalSection` at `0x180005c06`
- `ntdll!RtlDeleteCriticalSection` at `0x180005c16`
- `ntdll!RtlDeleteCriticalSection` at `0x180005c26`
- `ntdll!RtlInitializeCriticalSection` at `0x180005bc2`
- `ntdll!RtlInitializeCriticalSection` at `0x180005bd7`
- `ntdll!RtlInitializeCriticalSection` at `0x180005bf7`
- `ntdll!RtlInitializeCriticalSection` at `0x180005bc2`
- `ntdll!RtlInitializeCriticalSection` at `0x180005bd7`
- `ntdll!RtlInitializeCriticalSection` at `0x180005bf7`

## pseudocode

```c
__int64 __fastcall KerbAllocateLogonSession(struct _LUID *a1, struct _KERB_LOGON_SESSION **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  NTSTATUS v6; // edi
  char v7; // si
  HLOCAL v9; // rax

  if ( KerbGlobalPackageState == 1 )
  {
    v4 = ((__int64 (__fastcall *)(__int64))LsaFunctions->AllocateLsaHeap)(944);
    if ( v4 )
      goto LABEL_3;
  }
  else
  {
    v9 = LocalAlloc(0, 0x3B0u);
    v4 = (__int64)v9;
    if ( v9 )
    {
      memset_0(v9, 0, 0x3B0u);
LABEL_3:
      *(struct _LUID *)(v4 + 64) = *a1;
      *(_BYTE *)(v4 + 936) = 1;
      *(_DWORD *)v4 = 1;
      *(_DWORD *)(v4 + 932) = 0;
      *(_QWORD *)(v4 + 288) = v4 + 280;
      *(_QWORD *)(v4 + 280) = v4 + 280;
      GetSystemTimeAsFileTime((LPFILETIME)(v4 + 296));
      *(_QWORD *)(v4 + 368) = v4 + 360;
      *(_QWORD *)(v4 + 360) = v4 + 360;
      GetSystemTimeAsFileTime((LPFILETIME)(v4 + 376));
      *(_QWORD *)(v4 + 328) = v4 + 320;
      *(_QWORD *)(v4 + 320) = v4 + 320;
      GetSystemTimeAsFileTime((LPFILETIME)(v4 + 336));
      if ( *(_BYTE *)(v4 + 544) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v5);
      memset_0((void *)(v4 + 544), 0, 0x40u);
      *(_QWORD *)(v4 + 560) = v4 + 552;
      *(_QWORD *)(v4 + 552) = v4 + 552;
      *(_BYTE *)(v4 + 544) = 1;
      memset_0((void *)(v4 + 609), 0, 0x5Fu);
      *(_BYTE *)(v4 + 608) = 1;
      *(struct _LUID *)(v4 + 612) = *a1;
      *(_QWORD *)(v4 + 640) = 0;
      *(_QWORD *)(v4 + 656) = v4 + 648;
      *(_QWORD *)(v4 + 648) = v4 + 648;
      *(_QWORD *)(v4 + 848) = v4 + 840;
      *(_QWORD *)(v4 + 840) = v4 + 840;
      v6 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 856));
      if ( v6 >= 0 )
      {
        v7 = 25;
        v6 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 80));
        if ( v6 >= 0 )
        {
          v7 = 27;
          *(_QWORD *)(v4 + 16) = v4 + 8;
          *(_QWORD *)(v4 + 8) = v4 + 8;
          v6 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 24));
          if ( v6 >= 0 )
          {
            *a2 = (struct _KERB_LOGON_SESSION *)v4;
            return (unsigned int)v6;
          }
        }
        RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 856));
        if ( (v7 & 2) != 0 )
          RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 80));
      }
      KerbFree(v4);
      return (unsigned int)v6;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x180005aa0  push    rbx
0x180005aa2  push    rbp
0x180005aa3  push    rsi
0x180005aa4  push    rdi
0x180005aa5  push    r14
0x180005aa7  sub     rsp, 20h
0x180005aab  mov     r14, rdx
0x180005aae  mov     rsi, rcx
0x180005ab1  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180005ab8  jnz     loc_180005C48
0x180005abe  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180005ac5  mov     ecx, 3B0h
0x180005aca  mov     rax, [rax+28h]
0x180005ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad3  mov     rbx, rax
0x180005ad6  test    rax, rax
0x180005ad9  jz      loc_180005C41
0x180005adf  mov     rcx, [rsi]
0x180005ae2  mov     [rbx+40h], rcx
0x180005ae6  mov     byte ptr [rbx+3A8h], 1
0x180005aed  mov     dword ptr [rbx], 1
0x180005af3  mov     dword ptr [rbx+3A4h], 0
0x180005afd  lea     rcx, [rbx+118h]
0x180005b04  mov     [rcx+8], rcx
0x180005b08  mov     [rcx], rcx
0x180005b0b  add     rcx, 10h; lpSystemTimeAsFileTime
0x180005b0f  call    cs:__imp_GetSystemTimeAsFileTime
0x180005b15  lea     rcx, [rbx+168h]
0x180005b1c  mov     [rcx+8], rcx
0x180005b20  mov     [rcx], rcx
0x180005b23  add     rcx, 10h; lpSystemTimeAsFileTime
0x180005b27  call    cs:__imp_GetSystemTimeAsFileTime
0x180005b2d  lea     rcx, [rbx+140h]
0x180005b34  mov     [rcx+8], rcx
0x180005b38  mov     [rcx], rcx
0x180005b3b  add     rcx, 10h; lpSystemTimeAsFileTime
0x180005b3f  call    cs:__imp_GetSystemTimeAsFileTime
0x180005b45  lea     rdi, [rbx+220h]
0x180005b4c  cmp     byte ptr [rdi], 0
0x180005b4f  jnz     loc_180005C72
0x180005b55  xor     edx, edx; Val
0x180005b57  lea     r8d, [rdx+40h]; Size
0x180005b5b  mov     rcx, rdi; void *
0x180005b5e  call    memset_0
0x180005b63  lea     rax, [rdi+8]
0x180005b67  mov     [rax+8], rax
0x180005b6b  mov     [rax], rax
0x180005b6e  mov     byte ptr [rdi], 1
0x180005b71  lea     rcx, [rbx+261h]; void *
0x180005b78  xor     edx, edx; Val
0x180005b7a  lea     r8d, [rdx+5Fh]; Size
0x180005b7e  call    memset_0
0x180005b83  mov     byte ptr [rbx+260h], 1
0x180005b8a  mov     rax, [rsi]
0x180005b8d  mov     [rbx+264h], rax
0x180005b94  mov     qword ptr [rbx+280h], 0
0x180005b9f  lea     rax, [rbx+288h]
0x180005ba6  mov     [rax+8], rax
0x180005baa  mov     [rax], rax
0x180005bad  lea     rax, [rbx+348h]
0x180005bb4  mov     [rax+8], rax
0x180005bb8  mov     [rax], rax
0x180005bbb  lea     rbp, [rax+10h]
0x180005bbf  mov     rcx, rbp; CriticalSection
0x180005bc2  call    cs:__imp_RtlInitializeCriticalSection
0x180005bc8  mov     edi, eax
0x180005bca  test    eax, eax
0x180005bcc  js      short loc_180005C2C
0x180005bce  mov     esi, 19h
0x180005bd3  lea     rcx, [rbx+50h]; CriticalSection
0x180005bd7  call    cs:__imp_RtlInitializeCriticalSection
0x180005bdd  mov     edi, eax
0x180005bdf  test    eax, eax
0x180005be1  js      short loc_180005C03
0x180005be3  mov     esi, 1Bh
0x180005be8  lea     rcx, [rbx+8]
0x180005bec  mov     [rcx+8], rcx
0x180005bf0  mov     [rcx], rcx
0x180005bf3  add     rcx, 10h; CriticalSection
0x180005bf7  call    cs:__imp_RtlInitializeCriticalSection
0x180005bfd  mov     edi, eax
0x180005bff  test    eax, eax
0x180005c01  jns     short loc_180005C7C
0x180005c03  mov     rcx, rbp; CriticalSection
0x180005c06  call    cs:__imp_RtlDeleteCriticalSection
0x180005c0c  test    sil, 2
0x180005c10  jz      short loc_180005C1C
0x180005c12  lea     rcx, [rbx+50h]; CriticalSection
0x180005c16  call    cs:__imp_RtlDeleteCriticalSection
0x180005c1c  test    sil, 4
0x180005c20  jz      short loc_180005C2C
0x180005c22  lea     rcx, [rbx+18h]; CriticalSection
0x180005c26  call    cs:__imp_RtlDeleteCriticalSection
0x180005c2c  mov     rcx, rbx
0x180005c2f  call    KerbFree
0x180005c34  mov     eax, edi
0x180005c36  add     rsp, 20h
0x180005c3a  pop     r14
0x180005c3c  pop     rdi
0x180005c3d  pop     rsi
0x180005c3e  pop     rbp
0x180005c3f  pop     rbx
0x180005c40  retn
0x180005c41  mov     eax, 0C000009Ah
0x180005c46  jmp     short loc_180005C36
0x180005c48  mov     edx, 3B0h; uBytes
0x180005c4d  xor     ecx, ecx; uFlags
0x180005c4f  call    cs:__imp_LocalAlloc
0x180005c55  mov     rbx, rax
0x180005c58  test    rax, rax
0x180005c5b  jz      short loc_180005C41
0x180005c5d  xor     edx, edx; Val
0x180005c5f  mov     r8d, 3B0h; Size
0x180005c65  mov     rcx, rax; void *
0x180005c68  call    memset_0
0x180005c6d  jmp     loc_180005ADF
0x180005c72  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005c77  jmp     loc_180005B55
0x180005c7c  mov     [r14], rbx
0x180005c7f  jmp     short loc_180005C34
```
