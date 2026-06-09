# MinCryptHashMemory

- ea: `0x180063444`
- end: `0x1800634e3`
- name: `MinCryptHashMemory`
- size: `159`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180062ed4`
- `0x180063008`
- `0x180063a30`

## callees

- `0x180063444`
- `0x18010cb94`
- `0x18010d3d4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800634cd`
- `ntdll!RtlNtStatusToDosError` at `0x1800634cd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800634c5`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800634c5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063492`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063492`

## pseudocode

```c
ULONG __fastcall MinCryptHashMemory(
        unsigned int a1,
        unsigned int a2,
        struct _HASHLIB_BLOB *a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  const WCHAR *v8; // rax
  NTSTATUS v10; // eax
  NTSTATUS v11; // ecx
  int v12; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp-18h] BYREF

  v8 = CapiAlgIdToCngAlgId(a1);
  if ( v8 )
  {
    phAlgorithm = 0;
    v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, v8, L"Microsoft Primitive Provider", 0);
    if ( v10 >= 0 )
    {
      v12 = HashComputeMemoryHashMultiple(phAlgorithm, a2, a3, a4, a5);
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      v11 = v12;
    }
    else
    {
      v11 = v10;
    }
    return RtlNtStatusToDosError(v11);
  }
  else
  {
    *a5 = 0;
    return -2146893816;
  }
}

```

## disassembly

```asm
0x180063444  mov     [rsp+arg_0], rbx
0x180063449  mov     [rsp+arg_8], rsi
0x18006344e  push    rdi
0x18006344f  sub     rsp, 40h
0x180063453  mov     rbx, r9
0x180063456  mov     rdi, r8
0x180063459  mov     esi, edx
0x18006345b  call    ?CapiAlgIdToCngAlgId@@YAPEBGI@Z; CapiAlgIdToCngAlgId(uint)
0x180063460  test    rax, rax
0x180063463  jnz     short loc_180063477
0x180063465  mov     rax, [rsp+48h+arg_20]
0x18006346a  mov     dword ptr [rax], 0
0x180063470  mov     eax, 80090008h
0x180063475  jmp     short loc_1800634D3
0x180063477  xor     r9d, r9d; dwFlags
0x18006347a  mov     [rsp+48h+phAlgorithm], 0
0x180063483  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18006348a  mov     rdx, rax; pszAlgId
0x18006348d  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x180063492  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180063498  test    eax, eax
0x18006349a  jns     short loc_1800634A0
0x18006349c  mov     ecx, eax
0x18006349e  jmp     short loc_1800634CD
0x1800634a0  mov     rax, [rsp+48h+arg_20]
0x1800634a5  mov     r9, rbx; unsigned __int8 *
0x1800634a8  mov     rcx, [rsp+48h+phAlgorithm]; void *
0x1800634ad  mov     r8, rdi; struct _HASHLIB_BLOB *
0x1800634b0  mov     edx, esi; unsigned int
0x1800634b2  mov     [rsp+48h+var_28], rax; unsigned int *
0x1800634b7  call    ?HashComputeMemoryHashMultiple@@YAJPEAXKPEAU_HASHLIB_BLOB@@PEAEPEAK@Z; HashComputeMemoryHashMultiple(void *,ulong,_HASHLIB_BLOB *,uchar *,ulong *)
0x1800634bc  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x1800634c1  xor     edx, edx; dwFlags
0x1800634c3  mov     ebx, eax
0x1800634c5  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800634cb  mov     ecx, ebx; Status
0x1800634cd  call    cs:__imp_RtlNtStatusToDosError
0x1800634d3  mov     rbx, [rsp+48h+arg_0]
0x1800634d8  mov     rsi, [rsp+48h+arg_8]
0x1800634dd  add     rsp, 40h
0x1800634e1  pop     rdi
0x1800634e2  retn
```
