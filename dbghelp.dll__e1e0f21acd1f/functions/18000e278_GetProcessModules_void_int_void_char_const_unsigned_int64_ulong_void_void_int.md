# GetProcessModules(void *,int (*)(void *,char const *,unsigned __int64,ulong,void *),void *,int)

- ea: `0x18000e278`
- end: `0x18000e36f`
- name: `?GetProcessModules@@YAKPEAXP6AH0PEBD_KK0@Z0H@Z`
- size: `247`
- prototype: `unsigned int __fastcall(DWORD dwProcessId, int (*)(void *, const char *, unsigned __int64, unsigned int, void *), void *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d670`
- `0x18000e220`
- `0x1801a4be0`
- `0x1801a4c40`
- `0x1801a4ca0`
- `0x1801a7e60`

## callees

- `0x18000d920`
- `0x18000e278`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e307`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18000e2e1`
- `ntdll!RtlQueryProcessDebugInformation` at `0x18000e2e1`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18000e299`
- `ntdll!RtlCreateQueryDebugBuffer` at `0x18000e299`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18000e2ff`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18000e356`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18000e2ff`
- `ntdll!RtlDestroyQueryDebugBuffer` at `0x18000e356`

## pseudocode

```c
__int64 __fastcall GetProcessModules(
        __int64 dwProcessId,
        int (*a2)(void *, const char *, unsigned __int64, unsigned int, void *),
        void *a3,
        int a4)
{
  PRTL_DEBUG_INFORMATION QueryDebugBuffer; // rbx
  ULONG PID; // r14d
  int v11; // ebp
  ULONG v12; // esi
  unsigned int ProcessDebugInformation; // edi
  _DWORD *p_NumberOfHeaps; // rcx
  unsigned int i; // edi

  QueryDebugBuffer = RtlCreateQueryDebugBuffer(0, 0);
  if ( !QueryDebugBuffer )
    return 8;
  PID = GetPID(dwProcessId, a4);
  v11 = 3;
  if ( !PID )
    PID = dwProcessId;
  v12 = ((unsigned int)dword_1802AF9CC >> 7) & 0x40 | 0x80000001;
  do
  {
    ProcessDebugInformation = RtlQueryProcessDebugInformation(PID, v12, QueryDebugBuffer);
    if ( ProcessDebugInformation != -1073741820 )
      break;
  }
  while ( v11-- );
  if ( ProcessDebugInformation )
  {
    RtlDestroyQueryDebugBuffer(QueryDebugBuffer);
    SetLastError(ProcessDebugInformation);
    return ProcessDebugInformation;
  }
  else
  {
    p_NumberOfHeaps = &QueryDebugBuffer->Heaps->NumberOfHeaps;
    for ( i = 0; i < *p_NumberOfHeaps; ++i )
    {
      if ( !((unsigned int (__fastcall *)(__int64, _DWORD *, _QWORD, _QWORD, void *))a2)(
              dwProcessId,
              &p_NumberOfHeaps[74 * i + 12],
              *(_QWORD *)&p_NumberOfHeaps[74 * i + 6],
              (unsigned int)p_NumberOfHeaps[74 * i + 8],
              a3) )
        break;
      p_NumberOfHeaps = &QueryDebugBuffer->Heaps->NumberOfHeaps;
    }
    RtlDestroyQueryDebugBuffer(QueryDebugBuffer);
    return 0;
  }
}

```

## disassembly

```asm
0x18000e278  push    rbx
0x18000e27a  push    rbp
0x18000e27b  push    rsi
0x18000e27c  push    rdi
0x18000e27d  push    r12
0x18000e27f  push    r13
0x18000e281  push    r14
0x18000e283  push    r15
0x18000e285  sub     rsp, 38h
0x18000e289  mov     r13, rdx
0x18000e28c  mov     r15, rcx
0x18000e28f  xor     edx, edx; EventPair
0x18000e291  xor     ecx, ecx; Size
0x18000e293  mov     edi, r9d
0x18000e296  mov     r12, r8
0x18000e299  call    cs:__imp_RtlCreateQueryDebugBuffer
0x18000e29f  mov     rbx, rax
0x18000e2a2  test    rax, rax
0x18000e2a5  jnz     short loc_18000E2AF
0x18000e2a7  lea     eax, [rbx+8]
0x18000e2aa  jmp     loc_18000E35E
0x18000e2af  mov     edx, edi; int
0x18000e2b1  mov     rcx, r15; dwProcessId
0x18000e2b4  call    ?GetPID@@YAKPEAXH@Z; GetPID(void *,int)
0x18000e2b9  mov     esi, cs:dword_1802AF9CC
0x18000e2bf  test    eax, eax
0x18000e2c1  mov     r14d, eax
0x18000e2c4  mov     ebp, 3
0x18000e2c9  cmovz   r14, r15
0x18000e2cd  shr     esi, 7
0x18000e2d0  and     esi, 40h
0x18000e2d3  or      esi, 80000001h
0x18000e2d9  mov     r8, rbx; DebugBuffer
0x18000e2dc  mov     edx, esi; DebugInfoClassMask
0x18000e2de  mov     rcx, r14; ProcessId
0x18000e2e1  call    cs:__imp_RtlQueryProcessDebugInformation
0x18000e2e7  mov     edi, eax
0x18000e2e9  cmp     eax, 0C0000004h
0x18000e2ee  jnz     short loc_18000E2F8
0x18000e2f0  mov     ecx, ebp
0x18000e2f2  dec     ebp
0x18000e2f4  test    ecx, ecx
0x18000e2f6  jnz     short loc_18000E2D9
0x18000e2f8  test    edi, edi
0x18000e2fa  jz      short loc_18000E311
0x18000e2fc  mov     rcx, rbx; DebugBuffer
0x18000e2ff  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18000e305  mov     ecx, edi; dwErrCode
0x18000e307  call    cs:__imp_SetLastError
0x18000e30d  mov     eax, edi
0x18000e30f  jmp     short loc_18000E35E
0x18000e311  mov     rcx, [rbx+60h]
0x18000e315  xor     edi, edi
0x18000e317  cmp     [rcx], edi
0x18000e319  jbe     short loc_18000E353
0x18000e31b  lea     rdx, [rcx+30h]
0x18000e31f  mov     eax, edi
0x18000e321  imul    r8, rax, 128h
0x18000e328  mov     rax, r13
0x18000e32b  mov     [rsp+78h+var_58], r12
0x18000e330  add     rdx, r8
0x18000e333  mov     r9d, [r8+rcx+20h]
0x18000e338  mov     r8, [r8+rcx+18h]
0x18000e33d  mov     rcx, r15
0x18000e340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e345  test    eax, eax
0x18000e347  jz      short loc_18000E353
0x18000e349  mov     rcx, [rbx+60h]
0x18000e34d  inc     edi
0x18000e34f  cmp     edi, [rcx]
0x18000e351  jb      short loc_18000E31B
0x18000e353  mov     rcx, rbx; DebugBuffer
0x18000e356  call    cs:__imp_RtlDestroyQueryDebugBuffer
0x18000e35c  xor     eax, eax
0x18000e35e  add     rsp, 38h
0x18000e362  pop     r15
0x18000e364  pop     r14
0x18000e366  pop     r13
0x18000e368  pop     r12
0x18000e36a  pop     rdi
0x18000e36b  pop     rsi
0x18000e36c  pop     rbp
0x18000e36d  pop     rbx
0x18000e36e  retn
```
