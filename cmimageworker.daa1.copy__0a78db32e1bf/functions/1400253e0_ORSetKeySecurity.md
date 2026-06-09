# ORSetKeySecurity

- ea: `0x1400253e0`
- end: `0x140025579`
- name: `ORSetKeySecurity`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400229c8`

## callees

- `0x140002d5a`
- `0x140002d66`
- `0x1400253e0`
- `0x140025580`
- `0x14002e8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002543a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002543a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400254ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400254ed`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x14002545a`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x14002545a`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1400254dd`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x1400254dd`

## pseudocode

```c
__int64 __fastcall ORSetKeySecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3)
{
  __int64 v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // r15
  PVOID Heap_0; // rax
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+80h] [rbp+8h] BYREF

  ObjectsSecurityDescriptor = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 && (v6 = *(_QWORD *)(a1 + 16), *(_DWORD *)v6 == -1092567328) )
  {
    if ( a3 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 136));
      if ( *(_WORD *)(a1 + 30) )
      {
        LastError = 1018;
      }
      else if ( IsValidSecurityDescriptor(a3) )
      {
        LastError = 0;
        v8 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 16LL);
        Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v8 + 16));
        ObjectsSecurityDescriptor = Heap_0;
        if ( Heap_0 )
        {
          memcpy_0(Heap_0, (const void *)(v8 + 20), *(unsigned int *)(v8 + 16));
          if ( SetPrivateObjectSecurityEx(a2, a3, &ObjectsSecurityDescriptor, 8u, &CmKeyMapping, 0)
            || (LastError = GetLastError()) == 0 )
          {
            LastError = OrpAssignKeySecurityToTreeNode(a1, ObjectsSecurityDescriptor);
            if ( !LastError )
            {
              ++*(_QWORD *)(a1 + 168);
              LastError = 0;
              *(_DWORD *)(v6 + 180) = 1;
            }
          }
        }
      }
      else
      {
        LastError = 1338;
      }
      if ( ObjectsSecurityDescriptor )
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, ObjectsSecurityDescriptor);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 136));
    }
    else
    {
      return 87;
    }
  }
  else
  {
    return 6;
  }
  return LastError;
}

```

## disassembly

```asm
0x1400253e0  mov     rax, rsp
0x1400253e3  push    rbx
0x1400253e4  push    rbp
0x1400253e5  push    rsi
0x1400253e6  push    rdi
0x1400253e7  push    r12
0x1400253e9  push    r13
0x1400253eb  push    r14
0x1400253ed  push    r15
0x1400253ef  sub     rsp, 38h
0x1400253f3  xor     r13d, r13d
0x1400253f6  mov     rbp, r8
0x1400253f9  mov     [rax+8], r13
0x1400253fd  mov     r12d, edx
0x140025400  mov     eax, 746Eh
0x140025405  mov     rdi, rcx
0x140025408  cmp     [rcx+1Ch], ax
0x14002540c  jnz     loc_140025560
0x140025412  mov     rsi, [rcx+10h]
0x140025416  cmp     dword ptr [rsi], 0BEE0BEE0h
0x14002541c  jnz     loc_140025560
0x140025422  test    r8, r8
0x140025425  jnz     short loc_140025430
0x140025427  lea     ebx, [r8+57h]
0x14002542b  jmp     loc_140025565
0x140025430  lea     r14, [rsi+88h]
0x140025437  mov     rcx, r14; lpCriticalSection
0x14002543a  call    cs:__imp_EnterCriticalSection
0x140025441  nop     dword ptr [rax+rax+00h]
0x140025446  cmp     [rdi+1Eh], r13w
0x14002544b  jz      short loc_140025457
0x14002544d  mov     ebx, 3FAh
0x140025452  jmp     loc_140025529
0x140025457  mov     rcx, rbp; pSecurityDescriptor
0x14002545a  call    cs:__imp_IsValidSecurityDescriptor
0x140025461  nop     dword ptr [rax+rax+00h]
0x140025466  test    eax, eax
0x140025468  jnz     short loc_140025474
0x14002546a  mov     ebx, 53Ah
0x14002546f  jmp     loc_140025529
0x140025474  mov     rax, [rdi+60h]
0x140025478  xor     edx, edx; Flags
0x14002547a  mov     rcx, gs:60h
0x140025483  mov     ebx, r13d
0x140025486  mov     r15, [rax+10h]
0x14002548a  mov     rcx, [rcx+30h]; HeapHandle
0x14002548e  mov     r8d, [r15+10h]; Size
0x140025492  call    RtlAllocateHeap_0
0x140025497  mov     [rsp+78h+ObjectsSecurityDescriptor], rax
0x14002549f  test    rax, rax
0x1400254a2  jz      loc_140025529
0x1400254a8  mov     r8d, [r15+10h]; Size
0x1400254ac  lea     rdx, [r15+14h]; Src
0x1400254b0  mov     rcx, rax; void *
0x1400254b3  call    memcpy_0
0x1400254b8  lea     rax, CmKeyMapping
0x1400254bf  mov     [rsp+78h+Token], r13; Token
0x1400254c4  mov     r9d, 8; AutoInheritFlags
0x1400254ca  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x1400254cf  lea     r8, [rsp+78h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1400254d7  mov     rdx, rbp; ModificationDescriptor
0x1400254da  mov     ecx, r12d; SecurityInformation
0x1400254dd  call    cs:__imp_SetPrivateObjectSecurityEx
0x1400254e4  nop     dword ptr [rax+rax+00h]
0x1400254e9  test    eax, eax
0x1400254eb  jnz     short loc_1400254FF
0x1400254ed  call    cs:__imp_GetLastError
0x1400254f4  nop     dword ptr [rax+rax+00h]
0x1400254f9  mov     ebx, eax
0x1400254fb  test    eax, eax
0x1400254fd  jnz     short loc_140025529
0x1400254ff  mov     rdx, [rsp+78h+ObjectsSecurityDescriptor]
0x140025507  mov     rcx, rdi
0x14002550a  call    OrpAssignKeySecurityToTreeNode
0x14002550f  mov     ebx, eax
0x140025511  test    eax, eax
0x140025513  jnz     short loc_140025529
0x140025515  inc     qword ptr [rdi+0A8h]
0x14002551c  mov     ebx, r13d
0x14002551f  mov     dword ptr [rsi+0B4h], 1
0x140025529  cmp     [rsp+78h+ObjectsSecurityDescriptor], r13
0x140025531  jz      short loc_14002554F
0x140025533  mov     rcx, gs:60h
0x14002553c  xor     edx, edx; Flags
0x14002553e  mov     r8, [rsp+78h+ObjectsSecurityDescriptor]; P
0x140025546  mov     rcx, [rcx+30h]; HeapHandle
0x14002554a  call    RtlFreeHeap_0
0x14002554f  mov     rcx, r14; lpCriticalSection
0x140025552  call    cs:__imp_LeaveCriticalSection
0x140025559  nop     dword ptr [rax+rax+00h]
0x14002555e  jmp     short loc_140025565
0x140025560  mov     ebx, 6
0x140025565  mov     eax, ebx
0x140025567  add     rsp, 38h
0x14002556b  pop     r15
0x14002556d  pop     r14
0x14002556f  pop     r13
0x140025571  pop     r12
0x140025573  pop     rdi
0x140025574  pop     rsi
0x140025575  pop     rbp
0x140025576  pop     rbx
0x140025577  retn
```
