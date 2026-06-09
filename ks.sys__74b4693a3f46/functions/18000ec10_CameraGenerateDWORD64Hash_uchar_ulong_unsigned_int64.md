# CameraGenerateDWORD64Hash(uchar *,ulong,unsigned __int64 *)

- ea: `0x18000ec10`
- end: `0x18000ec8a`
- name: `?CameraGenerateDWORD64Hash@@YAJPEAEKPEA_K@Z`
- size: `122`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004fa1c`
- `0x180064208`

## callees

- `0x18000d2e8`
- `0x18000ec10`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x18000ec40`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x18000ec40`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x18000ec72`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x18000ec72`

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
0x18000ec10  push    rbx
0x18000ec12  push    rbp
0x18000ec13  push    rsi
0x18000ec14  push    rdi
0x18000ec15  sub     rsp, 28h
0x18000ec19  mov     rdi, r8
0x18000ec1c  mov     [rsp+48h+phAlgorithm], 0
0x18000ec25  mov     esi, edx
0x18000ec27  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000ec2e  mov     rbp, rcx
0x18000ec31  lea     rdx, pszAlgId; "SHA256"
0x18000ec38  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x18000ec3d  xor     r9d, r9d; dwFlags
0x18000ec40  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ec47  nop     dword ptr [rax+rax+00h]
0x18000ec4c  mov     ebx, eax
0x18000ec4e  test    eax, eax
0x18000ec50  js      short loc_18000EC66
0x18000ec52  mov     r8, [rsp+48h+phAlgorithm]; hObject
0x18000ec57  mov     r9, rdi; unsigned __int64 *
0x18000ec5a  mov     edx, esi; cbInput
0x18000ec5c  mov     rcx, rbp; pbInput
0x18000ec5f  call    ?CameraGenerateDWORD64HashWithHandle@@YAJPEAEKPEAXPEA_K@Z; CameraGenerateDWORD64HashWithHandle(uchar *,ulong,void *,unsigned __int64 *)
0x18000ec64  mov     ebx, eax
0x18000ec66  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x18000ec6b  test    rcx, rcx
0x18000ec6e  jz      short loc_18000EC7E
0x18000ec70  xor     edx, edx; dwFlags
0x18000ec72  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000ec79  nop     dword ptr [rax+rax+00h]
0x18000ec7e  mov     eax, ebx
0x18000ec80  add     rsp, 28h
0x18000ec84  pop     rdi
0x18000ec85  pop     rsi
0x18000ec86  pop     rbp
0x18000ec87  pop     rbx
0x18000ec88  retn
```
