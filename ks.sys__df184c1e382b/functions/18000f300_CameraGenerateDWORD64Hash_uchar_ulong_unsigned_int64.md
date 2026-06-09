# CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)

- ea: `0x18000f300`
- end: `0x18000f37a`
- name: `?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z`
- size: `122`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004fbbc`
- `0x1800643a8`

## callees

- `0x18000d2e8`
- `0x18000f300`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x18000f330`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x18000f330`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x18000f362`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x18000f362`

## pseudocode

```c
__int64 __fastcall CameraGenerateDWORD64Hash(PUCHAR pbInput, ULONG cbInput, unsigned __int64 *a3)
{
  NTSTATUS DWORD64HashWithHandle; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp+20h] BYREF

  phAlgorithm = 0;
  DWORD64HashWithHandle = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( DWORD64HashWithHandle >= 0 )
    DWORD64HashWithHandle = CameraGenerateDWORD64HashWithHandle(pbInput, cbInput, phAlgorithm, a3);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)DWORD64HashWithHandle;
}

```

## disassembly

```asm
0x18000f300  push    rbx
0x18000f302  push    rbp
0x18000f303  push    rsi
0x18000f304  push    rdi
0x18000f305  sub     rsp, 28h
0x18000f309  mov     rdi, r8
0x18000f30c  mov     [rsp+48h+phAlgorithm], 0
0x18000f315  mov     esi, edx
0x18000f317  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000f31e  mov     rbp, rcx
0x18000f321  lea     rdx, pszAlgId; "SHA256"
0x18000f328  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x18000f32d  xor     r9d, r9d; dwFlags
0x18000f330  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000f337  nop     dword ptr [rax+rax+00h]
0x18000f33c  mov     ebx, eax
0x18000f33e  test    eax, eax
0x18000f340  js      short loc_18000F356
0x18000f342  mov     r8, [rsp+48h+phAlgorithm]; hObject
0x18000f347  mov     r9, rdi; unsigned __int64 *
0x18000f34a  mov     edx, esi; cbInput
0x18000f34c  mov     rcx, rbp; pbInput
0x18000f34f  call    ?CameraGenerateDWORD64HashWithHandle@@YAJPEAEKPEAXPEA_K@Z; CameraGenerateDWORD64HashWithHandle(uchar *,ulong,void *,unsigned __int64 *)
0x18000f354  mov     ebx, eax
0x18000f356  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x18000f35b  test    rcx, rcx
0x18000f35e  jz      short loc_18000F36E
0x18000f360  xor     edx, edx; dwFlags
0x18000f362  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000f369  nop     dword ptr [rax+rax+00h]
0x18000f36e  mov     eax, ebx
0x18000f370  add     rsp, 28h
0x18000f374  pop     rdi
0x18000f375  pop     rsi
0x18000f376  pop     rbp
0x18000f377  pop     rbx
0x18000f378  retn
```
