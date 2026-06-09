# BaseRegGetKeySecurityOldInternal

- ea: `0x18001ca9c`
- end: `0x18001cc15`
- name: `BaseRegGetKeySecurityOldInternal`
- size: `377`
- prototype: `__int64 __fastcall(HANDLE Handle, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b1e0`

## callees

- `0x18001ca9c`
- `0x18001d28c`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001cb4d`
- `ntdll!RtlNtStatusToDosError` at `0x18001cbae`
- `ntdll!RtlNtStatusToDosError` at `0x18001cb4d`
- `ntdll!RtlNtStatusToDosError` at `0x18001cbae`
- `ntdll!NtQuerySecurityObject` at `0x18001cba2`
- `ntdll!NtQuerySecurityObject` at `0x18001cba2`
- `ntdll!NtClose` at `0x18001cbf4`
- `ntdll!NtClose` at `0x18001cbf4`
- `ntdll!RtlFreeHeap` at `0x18001cbe6`
- `ntdll!RtlFreeHeap` at `0x18001cbe6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001cb03`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001cb03`
- `ntdll!RtlAllocateHeap` at `0x18001cb79`
- `ntdll!RtlAllocateHeap` at `0x18001cb79`

## string_xrefs

- `0x18001caf4`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
ULONG __fastcall BaseRegGetKeySecurityOldInternal(HANDLE Handle, SECURITY_INFORMATION SecurityInformation, __int64 a3)
{
  HANDLE v3; // rsi
  HANDLE v6; // rbx
  HANDLE v7; // r15
  NTSTATUS v8; // eax
  ULONG result; // eax
  PVOID Heap; // r14
  int v11; // ebx
  int v12; // eax
  ULONG v13; // eax
  int LengthNeeded; // [rsp+20h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+50h] [rbp-20h]
  int v18; // [rsp+58h] [rbp-18h]
  int v19; // [rsp+5Ch] [rbp-14h]
  __int128 v20; // [rsp+60h] [rbp-10h]
  ULONG v21; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE v22; // [rsp+B8h] [rbp+48h] BYREF

  v21 = 0;
  v3 = 0;
  DWORD1(v16) = 0;
  v22 = 0;
  v19 = 0;
  v6 = Handle;
  if ( Handle == (HANDLE)-2147483644LL || Handle == (HANDLE)-2147483568LL || (v7 = 0, Handle == (HANDLE)-2147483552LL) )
  {
    DestinationString = 0;
    RtlInitUnicodeStringEx(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
    LODWORD(v16) = 48;
    *((_QWORD *)&v16 + 1) = 0;
    v18 = 64;
    p_DestinationString = &DestinationString;
    v20 = 0;
    v8 = Wow64NtOpenKey(&v22, (SecurityInformation & 8 | 0x10) << 21, &v16, 0, LengthNeeded);
    if ( v8 < 0 )
    {
      result = RtlNtStatusToDosError(v8);
      *(_QWORD *)(a3 + 8) = 0;
      return result;
    }
    v3 = v22;
    v6 = v22;
    v7 = v22;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(a3 + 8));
  if ( Heap )
  {
    v12 = NtQuerySecurityObject(v6, SecurityInformation, Heap, *(_DWORD *)(a3 + 8), &v21);
    if ( v12 >= 0 )
      v13 = MapSDToRpcSD(Heap, a3);
    else
      v13 = RtlNtStatusToDosError(v12);
    v11 = v13;
    if ( v13 )
      *(_QWORD *)(a3 + 8) = v21;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  else
  {
    v11 = 14;
  }
  if ( v7 )
    NtClose(v3);
  return v11;
}

```

## disassembly

```asm
0x18001ca9c  mov     [rsp-28h+arg_8], rbx
0x18001caa1  mov     [rsp-28h+arg_10], rsi
0x18001caa6  push    rbp
0x18001caa7  push    rdi
0x18001caa8  push    r12
0x18001caaa  push    r14
0x18001caac  push    r15
0x18001caae  mov     rbp, rsp
0x18001cab1  sub     rsp, 70h
0x18001cab5  xor     eax, eax
0x18001cab7  mov     [rbp+arg_0], 0
0x18001cabe  xor     esi, esi
0x18001cac0  mov     [rbp+var_2C], eax
0x18001cac3  mov     [rbp+arg_18], rsi
0x18001cac7  mov     rdi, r8
0x18001caca  mov     [rbp+var_14], eax
0x18001cacd  mov     r12d, edx
0x18001cad0  mov     rbx, rcx
0x18001cad3  cmp     rcx, 0FFFFFFFF80000004h
0x18001cada  jz      short loc_18001CAF1
0x18001cadc  cmp     rcx, 0FFFFFFFF80000050h
0x18001cae3  jz      short loc_18001CAF1
0x18001cae5  xor     r15d, r15d
0x18001cae8  cmp     rcx, 0FFFFFFFF80000060h
0x18001caef  jnz     short loc_18001CB66
0x18001caf1  xorps   xmm0, xmm0
0x18001caf4  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18001cafb  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001caff  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001cb03  call    cs:__imp_RtlInitUnicodeStringEx
0x18001cb09  mov     edx, r12d
0x18001cb0c  mov     [rbp+var_30], 30h ; '0'
0x18001cb13  and     edx, 8
0x18001cb16  mov     [rbp+var_28], rsi
0x18001cb1a  or      edx, 10h
0x18001cb1d  mov     [rbp+var_18], 40h ; '@'
0x18001cb24  lea     rax, [rbp+DestinationString]
0x18001cb28  shl     edx, 15h; int
0x18001cb2b  xorps   xmm0, xmm0
0x18001cb2e  mov     [rbp+var_20], rax
0x18001cb32  xor     r9d, r9d; int
0x18001cb35  lea     r8, [rbp+var_30]; int
0x18001cb39  lea     rcx, [rbp+arg_18]; int
0x18001cb3d  movdqu  [rbp+var_10], xmm0
0x18001cb42  call    Wow64NtOpenKey
0x18001cb47  test    eax, eax
0x18001cb49  jns     short loc_18001CB5C
0x18001cb4b  mov     ecx, eax; Status
0x18001cb4d  call    cs:__imp_RtlNtStatusToDosError
0x18001cb53  mov     [rdi+8], rsi
0x18001cb57  jmp     loc_18001CBFC
0x18001cb5c  mov     rsi, [rbp+arg_18]
0x18001cb60  mov     rbx, rsi
0x18001cb63  mov     r15, rsi
0x18001cb66  mov     rcx, gs:60h
0x18001cb6f  xor     edx, edx; Flags
0x18001cb71  mov     r8d, [rdi+8]; Size
0x18001cb75  mov     rcx, [rcx+30h]; HeapHandle
0x18001cb79  call    cs:__imp_RtlAllocateHeap
0x18001cb7f  mov     r14, rax
0x18001cb82  test    rax, rax
0x18001cb85  jnz     short loc_18001CB8C
0x18001cb87  lea     ebx, [rax+0Eh]
0x18001cb8a  jmp     short loc_18001CBEC
0x18001cb8c  mov     r9d, [rdi+8]; Length
0x18001cb90  lea     rax, [rbp+arg_0]
0x18001cb94  mov     r8, r14; SecurityDescriptor
0x18001cb97  mov     qword ptr [rsp+70h+LengthNeeded], rax; LengthNeeded
0x18001cb9c  mov     edx, r12d; SecurityInformation
0x18001cb9f  mov     rcx, rbx; Handle
0x18001cba2  call    cs:__imp_NtQuerySecurityObject
0x18001cba8  test    eax, eax
0x18001cbaa  jns     short loc_18001CBB6
0x18001cbac  mov     ecx, eax; Status
0x18001cbae  call    cs:__imp_RtlNtStatusToDosError
0x18001cbb4  jmp     short loc_18001CBC1
0x18001cbb6  mov     rdx, rdi
0x18001cbb9  mov     rcx, r14; AbsoluteSD
0x18001cbbc  call    MapSDToRpcSD
0x18001cbc1  mov     ebx, eax
0x18001cbc3  test    eax, eax
0x18001cbc5  jz      short loc_18001CBD4
0x18001cbc7  mov     eax, [rbp+arg_0]
0x18001cbca  mov     [rdi+8], eax
0x18001cbcd  mov     dword ptr [rdi+0Ch], 0
0x18001cbd4  mov     rcx, gs:60h
0x18001cbdd  mov     r8, r14; P
0x18001cbe0  xor     edx, edx; Flags
0x18001cbe2  mov     rcx, [rcx+30h]; HeapHandle
0x18001cbe6  call    cs:__imp_RtlFreeHeap
0x18001cbec  test    r15, r15
0x18001cbef  jz      short loc_18001CBFA
0x18001cbf1  mov     rcx, rsi; Handle
0x18001cbf4  call    cs:__imp_NtClose
0x18001cbfa  mov     eax, ebx
0x18001cbfc  lea     r11, [rsp+70h+var_s0]
0x18001cc01  mov     rbx, [r11+38h]
0x18001cc05  mov     rsi, [r11+40h]
0x18001cc09  mov     rsp, r11
0x18001cc0c  pop     r15
0x18001cc0e  pop     r14
0x18001cc10  pop     r12
0x18001cc12  pop     rdi
0x18001cc13  pop     rbp
0x18001cc14  retn
```
