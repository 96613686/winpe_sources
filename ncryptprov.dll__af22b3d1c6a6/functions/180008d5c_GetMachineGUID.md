# GetMachineGUID

- ea: `0x180008d5c`
- end: `0x180009052`
- name: `GetMachineGUID`
- size: `758`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007298`
- `0x180008840`
- `0x18005283c`

## callees

- `0x180008120`
- `0x180008574`
- `0x180008d5c`
- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180008e60`
- `ntdll!RtlNtStatusToDosError` at `0x180008e60`
- `ntdll!RtlFreeHeap` at `0x180008e52`
- `ntdll!RtlFreeHeap` at `0x180008e52`
- `ntdll!NtQueryValueKey` at `0x180008e1f`
- `ntdll!NtQueryValueKey` at `0x180008e1f`
- `ntdll!NtClose` at `0x180008ebb`
- `ntdll!NtClose` at `0x180008ebb`
- `ntdll!RtlInitUnicodeString` at `0x180008dbe`
- `ntdll!RtlInitUnicodeString` at `0x180008dbe`
- `ntdll!RtlAllocateHeap` at `0x180008de2`
- `ntdll!RtlAllocateHeap` at `0x180008de2`

## string_xrefs

- `0x180008fc6`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180008ff3`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000902a`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180008f0d`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`
- `0x180008f70`: `onecore\ds\security\cryptoapi\ncrypt\common\registry.c`

## pseudocode

```c
__int64 __fastcall GetMachineGUID(__int64 *a1, __int64 a2)
{
  ULONG v2; // edi
  unsigned int v4; // eax
  int Value; // ebx
  HANDLE v6; // rbx
  PVOID Heap; // rax
  int v8; // edx
  int v9; // r8d
  void *v10; // r14
  int v11; // edx
  int v12; // ebx
  int v13; // r8d
  __int64 v14; // rdi
  int v15; // r8d
  int v16; // edx
  int v17; // r8d
  __int64 v19; // r9
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  ULONG Length; // [rsp+80h] [rbp+30h] BYREF
  __int64 v22; // [rsp+88h] [rbp+38h] BYREF
  HANDLE KeyHandle; // [rsp+90h] [rbp+40h] BYREF

  v2 = 16;
  KeyHandle = 0;
  LODWORD(v22) = 16;
  *a1 = 0;
  v4 = MSCryptOpenHKLMKey((__int64)a1, a2, &KeyHandle);
  Value = v4;
  if ( v4 == 2 )
    goto LABEL_11;
  if ( v4 )
  {
    v19 = 3143;
LABEL_34:
    DebugTraceError(v4, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v19);
    goto LABEL_12;
  }
  v6 = KeyHandle;
  Length = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"MachineGuid");
  Length = 28;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1Cu);
  v10 = Heap;
  if ( Heap )
  {
    v12 = NtQueryValueKey(v6, &DestinationString, KeyValuePartialInformation, Heap, Length, &Length);
    if ( v12 >= 0 || v12 == -2147483643 || v12 == -1073741789 )
    {
      v2 = Length - 12;
      LODWORD(v22) = Length - 12;
      v12 = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        v13,
        (unsigned int)"Status",
        v12,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
        45);
    }
  }
  else
  {
    v12 = -1073741801;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        v9,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\registry.c",
        2);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  v4 = RtlNtStatusToDosError(v12);
  Value = v4;
  if ( v4 == 2 )
    goto LABEL_11;
  if ( v4 )
  {
    v19 = 3157;
    goto LABEL_34;
  }
  v14 = SafeAllocaAllocateFromHeap(v2);
  if ( v14 )
  {
    Value = MSCryptQueryValue(KeyHandle, (__int64)&v22);
    if ( !Value )
    {
      *a1 = v14;
LABEL_11:
      Value = 0;
      goto LABEL_12;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v17,
        (unsigned int)"dwReturn",
        Value,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        102);
    MSCryptFree(v14);
  }
  else
  {
    Value = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        8,
        v15,
        (unsigned int)"dwReturn",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        93);
  }
LABEL_12:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( Value > 0 )
    return (unsigned __int16)Value | 0x80070000;
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180008d5c  mov     [rsp-28h+arg_18], rbx
0x180008d61  push    rbp
0x180008d62  push    rsi
0x180008d63  push    rdi
0x180008d64  push    r13
0x180008d66  push    r14
0x180008d68  mov     rbp, rsp
0x180008d6b  sub     rsp, 50h
0x180008d6f  mov     edi, 10h
0x180008d74  mov     [rbp+KeyHandle], 0
0x180008d7c  lea     r8, [rbp+KeyHandle]
0x180008d80  mov     dword ptr [rbp+arg_8], edi
0x180008d83  mov     rsi, rcx
0x180008d86  mov     qword ptr [rcx], 0
0x180008d8d  call    MSCryptOpenHKLMKey
0x180008d92  mov     ebx, eax
0x180008d94  cmp     eax, 2
0x180008d97  jz      loc_180008EB0
0x180008d9d  test    eax, eax
0x180008d9f  jnz     loc_18000901C
0x180008da5  mov     rbx, [rbp+KeyHandle]
0x180008da9  lea     rdx, SourceString; "MachineGuid"
0x180008db0  xorps   xmm0, xmm0
0x180008db3  mov     [rbp+arg_0], eax
0x180008db6  lea     rcx, [rbp+DestinationString]; DestinationString
0x180008dba  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180008dbe  call    cs:__imp_RtlInitUnicodeString
0x180008dc5  nop     dword ptr [rax+rax+00h]
0x180008dca  lea     r8d, [rdi+0Ch]; Size
0x180008dce  mov     [rbp+arg_0], r8d
0x180008dd2  lea     edx, [rdi-8]; Flags
0x180008dd5  mov     rcx, gs:60h
0x180008dde  mov     rcx, [rcx+30h]; HeapHandle
0x180008de2  call    cs:__imp_RtlAllocateHeap
0x180008de9  nop     dword ptr [rax+rax+00h]
0x180008dee  lea     r13, WPP_GLOBAL_Control
0x180008df5  mov     r14, rax
0x180008df8  test    rax, rax
0x180008dfb  jz      loc_180008EE6
0x180008e01  lea     rax, [rbp+arg_0]
0x180008e05  mov     r9, r14; KeyValueInformation
0x180008e08  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180008e0d  lea     r8d, [rdi-0Eh]; KeyValueInformationClass
0x180008e11  mov     eax, [rbp+arg_0]
0x180008e14  lea     rdx, [rbp+DestinationString]; ValueName
0x180008e18  mov     rcx, rbx; KeyHandle
0x180008e1b  mov     [rsp+50h+Length], eax; Length
0x180008e1f  call    cs:__imp_NtQueryValueKey
0x180008e26  nop     dword ptr [rax+rax+00h]
0x180008e2b  mov     ebx, eax
0x180008e2d  test    eax, eax
0x180008e2f  js      loc_180008F36
0x180008e35  mov     edi, [rbp+arg_0]
0x180008e38  add     edi, 0FFFFFFF4h
0x180008e3b  mov     dword ptr [rbp+arg_8], edi
0x180008e3e  xor     ebx, ebx
0x180008e40  mov     rcx, gs:60h
0x180008e49  mov     r8, r14; P
0x180008e4c  xor     edx, edx; Flags
0x180008e4e  mov     rcx, [rcx+30h]; HeapHandle
0x180008e52  call    cs:__imp_RtlFreeHeap
0x180008e59  nop     dword ptr [rax+rax+00h]
0x180008e5e  mov     ecx, ebx; Status
0x180008e60  call    cs:__imp_RtlNtStatusToDosError
0x180008e67  nop     dword ptr [rax+rax+00h]
0x180008e6c  mov     ebx, eax
0x180008e6e  cmp     eax, 2
0x180008e71  jz      short loc_180008EB0
0x180008e73  test    eax, eax
0x180008e75  jnz     loc_180009024
0x180008e7b  mov     ecx, edi
0x180008e7d  call    SafeAllocaAllocateFromHeap
0x180008e82  mov     rdi, rax
0x180008e85  test    rax, rax
0x180008e88  jz      loc_180008FA1
0x180008e8e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180008e92  lea     rax, [rbp+arg_8]
0x180008e96  mov     r9, rdi
0x180008e99  mov     qword ptr [rsp+50h+Length], rax; __int64
0x180008e9e  call    MSCryptQueryValue
0x180008ea3  mov     ebx, eax
0x180008ea5  test    eax, eax
0x180008ea7  jnz     loc_180008F82
0x180008ead  mov     [rsi], rdi
0x180008eb0  xor     ebx, ebx
0x180008eb2  mov     rcx, [rbp+KeyHandle]; Handle
0x180008eb6  test    rcx, rcx
0x180008eb9  jz      short loc_180008EC7
0x180008ebb  call    cs:__imp_NtClose
0x180008ec2  nop     dword ptr [rax+rax+00h]
0x180008ec7  test    ebx, ebx
0x180008ec9  jg      loc_180009044
0x180008ecf  mov     eax, ebx
0x180008ed1  mov     rbx, [rsp+50h+arg_18]
0x180008ed9  add     rsp, 50h
0x180008edd  pop     r14
0x180008edf  pop     r13
0x180008ee1  pop     rdi
0x180008ee2  pop     rsi
0x180008ee3  pop     rbp
0x180008ee4  retn
0x180008ee6  mov     ebx, 0C0000017h
0x180008eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ef2  cmp     rcx, r13
0x180008ef5  jz      loc_180008E40
0x180008efb  test    byte ptr [rcx+1Ch], 1
0x180008eff  jz      loc_180008E40
0x180008f05  mov     [rsp+50h+var_20], 102h
0x180008f0d  lea     rax, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008f14  mov     [rsp+50h+ResultLength], rax
0x180008f19  mov     [rsp+50h+Length], 0C0000017h
0x180008f21  mov     rcx, [rcx+10h]
0x180008f25  lea     r9, aStatus; "Status"
0x180008f2c  call    WPP_SF_sDsd
0x180008f31  jmp     loc_180008E40
0x180008f36  cmp     ebx, 80000005h
0x180008f3c  jz      loc_180008E35
0x180008f42  cmp     ebx, 0C0000023h
0x180008f48  jz      loc_180008E35
0x180008f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f55  cmp     rcx, r13
0x180008f58  jz      loc_180008E40
0x180008f5e  test    byte ptr [rcx+1Ch], 1
0x180008f62  jz      loc_180008E40
0x180008f68  mov     [rsp+50h+var_20], 12Dh
0x180008f70  lea     rax, aOnecoreDsSecur_40; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008f77  mov     [rsp+50h+ResultLength], rax
0x180008f7c  mov     [rsp+50h+Length], ebx
0x180008f80  jmp     short loc_180008F21
0x180008f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f89  cmp     rcx, r13
0x180008f8c  jz      short loc_180008F94
0x180008f8e  test    byte ptr [rcx+1Ch], 1
0x180008f92  jnz     short loc_180008FEF
0x180008f94  mov     rcx, rdi
0x180008f97  call    MSCryptFree
0x180008f9c  jmp     loc_180008EB2
0x180008fa1  mov     edx, 8
0x180008fa6  mov     ebx, edx
0x180008fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008faf  cmp     rcx, r13
0x180008fb2  jz      loc_180008EB2
0x180008fb8  test    byte ptr [rcx+1Ch], 1
0x180008fbc  jz      loc_180008EB2
0x180008fc2  mov     rcx, [rcx+10h]
0x180008fc6  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008fcd  mov     [rsp+50h+var_20], 0C5Dh
0x180008fd5  lea     r9, aDwreturn; "dwReturn"
0x180008fdc  mov     [rsp+50h+ResultLength], rax
0x180008fe1  mov     [rsp+50h+Length], edx
0x180008fe5  call    WPP_SF_sDsd
0x180008fea  jmp     loc_180008EB2
0x180008fef  mov     rcx, [rcx+10h]
0x180008ff3  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008ffa  mov     [rsp+50h+var_20], 0C66h
0x180009002  lea     r9, aDwreturn; "dwReturn"
0x180009009  mov     [rsp+50h+ResultLength], rax
0x18000900e  mov     [rsp+50h+Length], ebx
0x180009012  call    WPP_SF_sDsd
0x180009017  jmp     loc_180008F94
0x18000901c  mov     r9d, 0C47h
0x180009022  jmp     short loc_18000902A
0x180009024  mov     r9d, 0C55h
0x18000902a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009031  mov     ecx, eax
0x180009033  lea     rdx, aDwreturn; "dwReturn"
0x18000903a  call    DebugTraceError
0x18000903f  jmp     loc_180008EB2
0x180009044  movzx   ebx, bx
0x180009047  or      ebx, 80070000h
0x18000904d  jmp     loc_180008ECF
```
