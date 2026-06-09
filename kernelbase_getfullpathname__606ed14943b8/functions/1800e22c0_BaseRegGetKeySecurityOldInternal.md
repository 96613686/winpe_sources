# BaseRegGetKeySecurityOldInternal

- ea: `0x1800e22c0`
- end: `0x1800e2479`
- name: `BaseRegGetKeySecurityOldInternal`
- size: `441`
- prototype: `__int64 __fastcall(HANDLE Handle, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e1f30`

## callees

- `0x18005f8a0`
- `0x1800e22c0`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x1800e2361`
- `ntdll!NtQuerySecurityObject` at `0x1800e2361`
- `ntdll!RtlNtStatusToDosError` at `0x1800e23ec`
- `ntdll!RtlNtStatusToDosError` at `0x1801a0ebb`
- `ntdll!RtlNtStatusToDosError` at `0x1800e23ec`
- `ntdll!RtlNtStatusToDosError` at `0x1801a0ebb`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801a0e66`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801a0e66`
- `ntdll!NtClose` at `0x1800e246b`
- `ntdll!NtClose` at `0x1800e246b`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800e2374`
- `ntdll!RtlValidSecurityDescriptor` at `0x1800e2374`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800e238b`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800e238b`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800e23de`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800e23de`
- `ntdll!RtlFreeHeap` at `0x1800e241d`
- `ntdll!RtlFreeHeap` at `0x1800e241d`
- `ntdll!RtlAllocateHeap` at `0x1800e2334`
- `ntdll!RtlAllocateHeap` at `0x1800e23b7`
- `ntdll!RtlAllocateHeap` at `0x1800e2334`
- `ntdll!RtlAllocateHeap` at `0x1800e23b7`

## string_xrefs

- `0x1801a0e57`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
ULONG __fastcall BaseRegGetKeySecurityOldInternal(HANDLE Handle, SECURITY_INFORMATION SecurityInformation, __int64 a3)
{
  void *v3; // rsi
  HANDLE v6; // rbx
  ULONG *v7; // r14
  PVOID Heap; // r15
  int SelfRelativeSD; // eax
  ULONG v10; // ebx
  PVOID v11; // rax
  ULONG v12; // ebx
  ULONG result; // eax
  NTSTATUS v14; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v16[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+50h] [rbp-20h]
  int v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+5Ch] [rbp-14h]
  __int128 v21; // [rsp+60h] [rbp-10h]
  ULONG LengthNeeded; // [rsp+A0h] [rbp+30h] BYREF
  void *v23; // [rsp+B8h] [rbp+48h] BYREF

  LengthNeeded = 0;
  v3 = 0;
  v16[1] = 0;
  v23 = 0;
  v20 = 0;
  v6 = Handle;
  if ( Handle == (HANDLE)-2147483644LL || Handle == (HANDLE)-2147483568LL || Handle == (HANDLE)-2147483552LL )
  {
    DestinationString = 0;
    RtlInitUnicodeStringEx(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
    v16[0] = 48;
    v17 = 0;
    v19 = 64;
    p_DestinationString = &DestinationString;
    v21 = 0;
    v14 = Wow64NtOpenKey((unsigned int)&v23, (SecurityInformation & 8 | 0x10) << 21, (unsigned int)v16, 0, 0);
    if ( v14 < 0 )
    {
      result = RtlNtStatusToDosError(v14);
      *(_QWORD *)(a3 + 8) = 0;
      return result;
    }
    v3 = v23;
    v6 = v23;
  }
  v7 = (ULONG *)(a3 + 8);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(a3 + 8));
  if ( Heap )
  {
    SelfRelativeSD = NtQuerySecurityObject(v6, SecurityInformation, Heap, *v7, &LengthNeeded);
    if ( SelfRelativeSD < 0 )
    {
LABEL_11:
      v12 = RtlNtStatusToDosError(SelfRelativeSD);
LABEL_12:
      if ( v12 )
      {
        *v7 = LengthNeeded;
        *(_DWORD *)(a3 + 12) = 0;
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      goto LABEL_15;
    }
    if ( !RtlValidSecurityDescriptor(Heap) )
    {
      v12 = 87;
      goto LABEL_12;
    }
    v10 = RtlLengthSecurityDescriptor(Heap);
    v11 = *(PVOID *)a3;
    if ( *(_QWORD *)a3 )
    {
      if ( *v7 >= v10 )
        goto LABEL_10;
    }
    else
    {
      v11 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      *(_QWORD *)a3 = v11;
      if ( v11 )
      {
        *v7 = v10;
LABEL_10:
        *(_DWORD *)(a3 + 12) = v10;
        SelfRelativeSD = RtlMakeSelfRelativeSD(Heap, v11, (PULONG)(a3 + 8));
        goto LABEL_11;
      }
    }
    v12 = 14;
    goto LABEL_12;
  }
  v12 = 14;
LABEL_15:
  if ( v3 )
    NtClose(v3);
  return v12;
}

```

## disassembly

```asm
0x1800e22c0  mov     [rsp-28h+arg_8], rbx
0x1800e22c5  mov     [rsp-28h+arg_10], rsi
0x1800e22ca  push    rbp
0x1800e22cb  push    rdi
0x1800e22cc  push    r12
0x1800e22ce  push    r14
0x1800e22d0  push    r15
0x1800e22d2  mov     rbp, rsp
0x1800e22d5  sub     rsp, 70h
0x1800e22d9  xor     eax, eax
0x1800e22db  mov     [rbp+arg_0], 0
0x1800e22e2  xor     esi, esi
0x1800e22e4  mov     [rbp+var_2C], eax
0x1800e22e7  mov     [rbp+arg_18], rsi
0x1800e22eb  mov     rdi, r8
0x1800e22ee  mov     [rbp+var_14], eax
0x1800e22f1  mov     r12d, edx
0x1800e22f4  mov     rbx, rcx
0x1800e22f7  cmp     rcx, 0FFFFFFFF80000004h
0x1800e22fe  jz      loc_1801A0E54
0x1800e2304  cmp     rcx, 0FFFFFFFF80000050h
0x1800e230b  jz      loc_1801A0E54
0x1800e2311  cmp     rcx, 0FFFFFFFF80000060h
0x1800e2318  jz      loc_1801A0E54
0x1800e231e  mov     rcx, gs:60h
0x1800e2327  lea     r14, [rdi+8]
0x1800e232b  mov     r8d, [r14]; Size
0x1800e232e  xor     edx, edx; Flags
0x1800e2330  mov     rcx, [rcx+30h]; HeapHandle
0x1800e2334  call    cs:__imp_RtlAllocateHeap
0x1800e233b  nop     dword ptr [rax+rax+00h]
0x1800e2340  mov     r15, rax
0x1800e2343  test    rax, rax
0x1800e2346  jz      loc_1800E2461
0x1800e234c  mov     r9d, [r14]; Length
0x1800e234f  lea     rax, [rbp+arg_0]
0x1800e2353  mov     r8, r15; SecurityDescriptor
0x1800e2356  mov     [rsp+70h+LengthNeeded], rax; LengthNeeded
0x1800e235b  mov     edx, r12d; SecurityInformation
0x1800e235e  mov     rcx, rbx; Handle
0x1800e2361  call    cs:__imp_NtQuerySecurityObject
0x1800e2368  nop     dword ptr [rax+rax+00h]
0x1800e236d  test    eax, eax
0x1800e236f  js      short loc_1800E23EA
0x1800e2371  mov     rcx, r15; SecurityDescriptor
0x1800e2374  call    cs:__imp_RtlValidSecurityDescriptor
0x1800e237b  nop     dword ptr [rax+rax+00h]
0x1800e2380  test    al, al
0x1800e2382  jz      loc_1800E244A
0x1800e2388  mov     rcx, r15; SecurityDescriptor
0x1800e238b  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800e2392  nop     dword ptr [rax+rax+00h]
0x1800e2397  mov     ebx, eax
0x1800e2399  mov     rax, [rdi]
0x1800e239c  test    rax, rax
0x1800e239f  jnz     loc_1800E2451
0x1800e23a5  mov     rcx, gs:60h
0x1800e23ae  mov     r8d, ebx; Size
0x1800e23b1  xor     edx, edx; Flags
0x1800e23b3  mov     rcx, [rcx+30h]; HeapHandle
0x1800e23b7  call    cs:__imp_RtlAllocateHeap
0x1800e23be  nop     dword ptr [rax+rax+00h]
0x1800e23c3  mov     [rdi], rax
0x1800e23c6  test    rax, rax
0x1800e23c9  jz      loc_1800E245A
0x1800e23cf  mov     [r14], ebx
0x1800e23d2  mov     r8, r14; BufferLength
0x1800e23d5  mov     [rdi+0Ch], ebx
0x1800e23d8  mov     rdx, rax; SelfRelativeSD
0x1800e23db  mov     rcx, r15; AbsoluteSD
0x1800e23de  call    cs:__imp_RtlMakeSelfRelativeSD
0x1800e23e5  nop     dword ptr [rax+rax+00h]
0x1800e23ea  mov     ecx, eax; Status
0x1800e23ec  call    cs:__imp_RtlNtStatusToDosError
0x1800e23f3  nop     dword ptr [rax+rax+00h]
0x1800e23f8  mov     ebx, eax
0x1800e23fa  test    ebx, ebx
0x1800e23fc  jz      short loc_1800E240B
0x1800e23fe  mov     eax, [rbp+arg_0]
0x1800e2401  mov     [r14], eax
0x1800e2404  mov     dword ptr [rdi+0Ch], 0
0x1800e240b  mov     rcx, gs:60h
0x1800e2414  mov     r8, r15; P
0x1800e2417  xor     edx, edx; Flags
0x1800e2419  mov     rcx, [rcx+30h]; HeapHandle
0x1800e241d  call    cs:__imp_RtlFreeHeap
0x1800e2424  nop     dword ptr [rax+rax+00h]
0x1800e2429  test    rsi, rsi
0x1800e242c  jnz     short loc_1800E2468
0x1800e242e  mov     eax, ebx
0x1800e2430  lea     r11, [rsp+70h+var_s0]
0x1800e2435  mov     rbx, [r11+38h]
0x1800e2439  mov     rsi, [r11+40h]
0x1800e243d  mov     rsp, r11
0x1800e2440  pop     r15
0x1800e2442  pop     r14
0x1800e2444  pop     r12
0x1800e2446  pop     rdi
0x1800e2447  pop     rbp
0x1800e2448  retn
0x1800e244a  mov     ebx, 57h ; 'W'
0x1800e244f  jmp     short loc_1800E23FA
0x1800e2451  cmp     [r14], ebx
0x1800e2454  jnb     loc_1800E23D2
0x1800e245a  mov     ebx, 0Eh
0x1800e245f  jmp     short loc_1800E23FA
0x1800e2461  mov     ebx, 0Eh
0x1800e2466  jmp     short loc_1800E2429
0x1800e2468  mov     rcx, rsi; Handle
0x1800e246b  call    cs:__imp_NtClose
0x1800e2472  nop     dword ptr [rax+rax+00h]
0x1800e2477  jmp     short loc_1800E242E
0x1801a0e54  xorps   xmm0, xmm0
0x1801a0e57  lea     rdx, aRegistryMachin_34; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1801a0e5e  lea     rcx, [rbp+DestinationString]; DestinationString
0x1801a0e62  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1801a0e66  call    cs:__imp_RtlInitUnicodeStringEx
0x1801a0e6d  nop     dword ptr [rax+rax+00h]
0x1801a0e72  mov     edx, r12d
0x1801a0e75  mov     [rbp+var_30], 30h ; '0'
0x1801a0e7c  and     edx, 8
0x1801a0e7f  mov     [rbp+var_28], rsi
0x1801a0e83  or      edx, 10h
0x1801a0e86  mov     [rbp+var_18], 40h ; '@'
0x1801a0e8d  lea     rax, [rbp+DestinationString]
0x1801a0e91  shl     edx, 15h
0x1801a0e94  xorps   xmm0, xmm0
0x1801a0e97  mov     [rbp+var_20], rax
0x1801a0e9b  xor     r9d, r9d
0x1801a0e9e  mov     [rsp+70h+LengthNeeded], rsi
0x1801a0ea3  lea     r8, [rbp+var_30]
0x1801a0ea7  lea     rcx, [rbp+arg_18]
0x1801a0eab  movdqu  [rbp+var_10], xmm0
0x1801a0eb0  call    Wow64NtOpenKey
0x1801a0eb5  test    eax, eax
0x1801a0eb7  jns     short loc_1801A0ED0
0x1801a0eb9  mov     ecx, eax; Status
0x1801a0ebb  call    cs:__imp_RtlNtStatusToDosError
0x1801a0ec2  nop     dword ptr [rax+rax+00h]
0x1801a0ec7  mov     [rdi+8], rsi
0x1801a0ecb  jmp     loc_1800E2430
0x1801a0ed0  mov     rsi, [rbp+arg_18]
0x1801a0ed4  mov     rbx, rsi
0x1801a0ed7  jmp     loc_1800E231E
```
