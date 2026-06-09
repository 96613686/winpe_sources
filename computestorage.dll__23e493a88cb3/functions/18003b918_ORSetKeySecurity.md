# ORSetKeySecurity

- ea: `0x18003b918`
- end: `0x18003babf`
- name: `ORSetKeySecurity`
- size: `423`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003223c`
- `0x1800322e4`
- `0x180033914`

## callees

- `0x180003bb5`
- `0x18003b918`
- `0x18003bac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b972`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ba98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ba98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba2c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003b992`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003b992`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18003ba1c`
- `api-ms-win-security-base-l1-1-0!SetPrivateObjectSecurityEx` at `0x18003ba1c`
- `ntdll!RtlFreeHeap` at `0x18003ba89`
- `ntdll!RtlFreeHeap` at `0x18003ba89`
- `ntdll!RtlAllocateHeap` at `0x18003b9ca`
- `ntdll!RtlAllocateHeap` at `0x18003b9ca`

## pseudocode

```c
__int64 __fastcall ORSetKeySecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3)
{
  __int64 v6; // rsi
  DWORD LastError; // ebx
  __int64 v8; // r15
  PVOID Heap; // rax
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
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v8 + 16));
        ObjectsSecurityDescriptor = Heap;
        if ( Heap )
        {
          memcpy_0(Heap, (const void *)(v8 + 20), *(unsigned int *)(v8 + 16));
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
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ObjectsSecurityDescriptor);
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
0x18003b918  mov     rax, rsp
0x18003b91b  push    rbx
0x18003b91c  push    rbp
0x18003b91d  push    rsi
0x18003b91e  push    rdi
0x18003b91f  push    r12
0x18003b921  push    r13
0x18003b923  push    r14
0x18003b925  push    r15
0x18003b927  sub     rsp, 38h
0x18003b92b  xor     r13d, r13d
0x18003b92e  mov     rbp, r8
0x18003b931  mov     [rax+8], r13
0x18003b935  mov     r12d, edx
0x18003b938  mov     eax, 746Eh
0x18003b93d  mov     rdi, rcx
0x18003b940  cmp     [rcx+1Ch], ax
0x18003b944  jnz     loc_18003BAA6
0x18003b94a  mov     rsi, [rcx+10h]
0x18003b94e  cmp     dword ptr [rsi], 0BEE0BEE0h
0x18003b954  jnz     loc_18003BAA6
0x18003b95a  test    r8, r8
0x18003b95d  jnz     short loc_18003B968
0x18003b95f  lea     ebx, [r8+57h]
0x18003b963  jmp     loc_18003BAAB
0x18003b968  lea     r14, [rsi+88h]
0x18003b96f  mov     rcx, r14; lpCriticalSection
0x18003b972  call    cs:__imp_EnterCriticalSection
0x18003b979  nop     dword ptr [rax+rax+00h]
0x18003b97e  cmp     [rdi+1Eh], r13w
0x18003b983  jz      short loc_18003B98F
0x18003b985  mov     ebx, 3FAh
0x18003b98a  jmp     loc_18003BA68
0x18003b98f  mov     rcx, rbp; pSecurityDescriptor
0x18003b992  call    cs:__imp_IsValidSecurityDescriptor
0x18003b999  nop     dword ptr [rax+rax+00h]
0x18003b99e  test    eax, eax
0x18003b9a0  jnz     short loc_18003B9AC
0x18003b9a2  mov     ebx, 53Ah
0x18003b9a7  jmp     loc_18003BA68
0x18003b9ac  mov     rax, [rdi+60h]
0x18003b9b0  xor     edx, edx; Flags
0x18003b9b2  mov     rcx, gs:60h
0x18003b9bb  mov     ebx, r13d
0x18003b9be  mov     r15, [rax+10h]
0x18003b9c2  mov     rcx, [rcx+30h]; HeapHandle
0x18003b9c6  mov     r8d, [r15+10h]; Size
0x18003b9ca  call    cs:__imp_RtlAllocateHeap
0x18003b9d1  nop     dword ptr [rax+rax+00h]
0x18003b9d6  mov     [rsp+78h+ObjectsSecurityDescriptor], rax
0x18003b9de  test    rax, rax
0x18003b9e1  jz      loc_18003BA68
0x18003b9e7  mov     r8d, [r15+10h]; Size
0x18003b9eb  lea     rdx, [r15+14h]; Src
0x18003b9ef  mov     rcx, rax; void *
0x18003b9f2  call    memcpy_0
0x18003b9f7  lea     rax, CmKeyMapping
0x18003b9fe  mov     [rsp+78h+Token], r13; Token
0x18003ba03  mov     r9d, 8; AutoInheritFlags
0x18003ba09  mov     [rsp+78h+GenericMapping], rax; GenericMapping
0x18003ba0e  lea     r8, [rsp+78h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x18003ba16  mov     rdx, rbp; ModificationDescriptor
0x18003ba19  mov     ecx, r12d; SecurityInformation
0x18003ba1c  call    cs:__imp_SetPrivateObjectSecurityEx
0x18003ba23  nop     dword ptr [rax+rax+00h]
0x18003ba28  test    eax, eax
0x18003ba2a  jnz     short loc_18003BA3E
0x18003ba2c  call    cs:__imp_GetLastError
0x18003ba33  nop     dword ptr [rax+rax+00h]
0x18003ba38  mov     ebx, eax
0x18003ba3a  test    eax, eax
0x18003ba3c  jnz     short loc_18003BA68
0x18003ba3e  mov     rdx, [rsp+78h+ObjectsSecurityDescriptor]
0x18003ba46  mov     rcx, rdi
0x18003ba49  call    OrpAssignKeySecurityToTreeNode
0x18003ba4e  mov     ebx, eax
0x18003ba50  test    eax, eax
0x18003ba52  jnz     short loc_18003BA68
0x18003ba54  inc     qword ptr [rdi+0A8h]
0x18003ba5b  mov     ebx, r13d
0x18003ba5e  mov     dword ptr [rsi+0B4h], 1
0x18003ba68  cmp     [rsp+78h+ObjectsSecurityDescriptor], r13
0x18003ba70  jz      short loc_18003BA95
0x18003ba72  mov     rcx, gs:60h
0x18003ba7b  xor     edx, edx; Flags
0x18003ba7d  mov     r8, [rsp+78h+ObjectsSecurityDescriptor]; P
0x18003ba85  mov     rcx, [rcx+30h]; HeapHandle
0x18003ba89  call    cs:__imp_RtlFreeHeap
0x18003ba90  nop     dword ptr [rax+rax+00h]
0x18003ba95  mov     rcx, r14; lpCriticalSection
0x18003ba98  call    cs:__imp_LeaveCriticalSection
0x18003ba9f  nop     dword ptr [rax+rax+00h]
0x18003baa4  jmp     short loc_18003BAAB
0x18003baa6  mov     ebx, 6
0x18003baab  mov     eax, ebx
0x18003baad  add     rsp, 38h
0x18003bab1  pop     r15
0x18003bab3  pop     r14
0x18003bab5  pop     r13
0x18003bab7  pop     r12
0x18003bab9  pop     rdi
0x18003baba  pop     rsi
0x18003babb  pop     rbp
0x18003babc  pop     rbx
0x18003babd  retn
```
