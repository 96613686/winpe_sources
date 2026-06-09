# DeleteRemoteDatabaseEntry

- ea: `0x14000b5e8`
- end: `0x14000ba8b`
- name: `DeleteRemoteDatabaseEntry`
- size: `1187`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000a96c`
- `0x14000ecbc`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x14000a550`
- `0x14000b5e8`
- `0x14000bb40`
- `0x140012df0`
- `0x1400135a0`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x14000b8b6`
- `ntoskrnl!ZwReadFile` at `0x14000b8b6`
- `ntoskrnl!ZwWriteFile` at `0x14000ba44`
- `ntoskrnl!ZwWriteFile` at `0x14000ba44`
- `ntoskrnl!KeReleaseMutex` at `0x14000b64c`
- `ntoskrnl!KeReleaseMutex` at `0x14000b70d`
- `ntoskrnl!KeReleaseMutex` at `0x14000b76a`
- `ntoskrnl!KeReleaseMutex` at `0x14000b7bb`
- `ntoskrnl!KeReleaseMutex` at `0x14000b64c`
- `ntoskrnl!KeReleaseMutex` at `0x14000b70d`
- `ntoskrnl!KeReleaseMutex` at `0x14000b76a`
- `ntoskrnl!KeReleaseMutex` at `0x14000b7bb`
- `ntoskrnl!ExAllocatePool2` at `0x14000b82a`
- `ntoskrnl!ExAllocatePool2` at `0x14000b82a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b900`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b916`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b900`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b916`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b6ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b936`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b6ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b936`

## pseudocode

```c
__int64 __fastcall DeleteRemoteDatabaseEntry(__int64 a1, void *a2, unsigned int a3)
{
  __int64 v3; // rbx
  union _LARGE_INTEGER v6; // rsi
  struct _KMUTANT *v7; // r12
  unsigned int RemoteDatabaseSize; // edi
  __int64 v9; // r8
  NTSTATUS v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int RemoteDatabaseEntry; // eax
  _DWORD *v17; // r13
  __int64 v18; // r8
  ULONG Length; // edi
  __int64 v20; // r8
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  PVOID v24; // rsi
  int v25; // eax
  __int64 v26; // r8
  unsigned int v27; // esi
  __int64 v29; // r8
  __int64 v30; // [rsp+50h] [rbp-30h]
  __int64 v31; // [rsp+58h] [rbp-28h]
  __int64 v32; // [rsp+60h] [rbp-20h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-18h] BYREF
  PVOID P; // [rsp+C0h] [rbp+40h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+D8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a1 + 152);
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  v6.QuadPart = a3;
  v7 = (struct _KMUTANT *)(v3 + 56);
  v31 = *(_QWORD *)(v3 + 336);
  v30 = *(_QWORD *)(a1 + 176);
  P = 0;
  v32 = v3;
  KeReleaseMutex((PRKMUTEX)(v3 + 56), 0);
  RemoteDatabaseSize = GetRemoteDatabaseSize(a2);
  if ( !RemoteDatabaseSize )
  {
    v10 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 56, v9, 3221225485LL);
    goto LABEL_38;
  }
  KeWaitForSingleObject((PVOID)(v3 + 56), Executive, 0, 0, 0);
  v11 = VerifyEpoch(v3, v31, v30);
  v10 = v11;
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_10;
    v14 = 57;
    v15 = (unsigned int)v11;
LABEL_9:
    WPP_SF_L(v13->AttachedDevice, v14, v12, v15);
LABEL_10:
    KeReleaseMutex(v7, 0);
    goto LABEL_38;
  }
  RemoteDatabaseEntry = GetRemoteDatabaseEntry(a1, a2, v6.LowPart, (unsigned __int16 **)&P);
  v17 = P;
  v10 = RemoteDatabaseEntry;
  if ( RemoteDatabaseEntry < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 58, v12, (unsigned int)RemoteDatabaseEntry);
    KeReleaseMutex(v7, 0);
    goto LABEL_36;
  }
  if ( !P )
  {
    v10 = -1073741811;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_10;
    v14 = (unsigned int)((_DWORD)P + 59);
    v15 = 3221225485LL;
    goto LABEL_9;
  }
  KeReleaseMutex(v7, 0);
  if ( *v17 + v6.LowPart >= RemoteDatabaseSize )
  {
    v10 = TruncateRemoteDatabase(a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 60, v18, (unsigned int)v10);
    goto LABEL_36;
  }
  Length = RemoteDatabaseSize - *v17 - v6.LowPart;
  P = (PVOID)ExAllocatePool2(258, Length, 1098149453);
  if ( !P )
  {
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61);
    goto LABEL_36;
  }
  ByteOffset.QuadPart = v6.LowPart + *v17;
  v10 = ZwReadFile(a2, 0, 0, 0, &IoStatusBlock, P, Length, &ByteOffset, 0);
  if ( v10 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_34;
    v22 = 62;
    goto LABEL_32;
  }
  if ( IoStatusBlock.Information < Length )
  {
    v10 = -1073741811;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_34;
    v22 = 63;
    v23 = 3221225485LL;
    goto LABEL_33;
  }
  v10 = TruncateRemoteDatabase(a2);
  if ( v10 >= 0 )
  {
    ByteOffset = v6;
    v24 = P;
    v10 = ZwWriteFile(a2, 0, 0, 0, &IoStatusBlock, P, Length, &ByteOffset, 0);
    if ( v10 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 65, v29, (unsigned int)v10);
    }
    goto LABEL_35;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v22 = 64;
LABEL_32:
    v23 = (unsigned int)v10;
LABEL_33:
    WPP_SF_L(v21->AttachedDevice, v22, v20, v23);
  }
LABEL_34:
  v24 = P;
LABEL_35:
  ExFreePoolWithTag(v24, 0);
LABEL_36:
  if ( v17 )
    ExFreePoolWithTag(v17, 0);
LABEL_38:
  KeWaitForSingleObject(v7, Executive, 0, 0, 0);
  v25 = VerifyEpoch(v32, v31, v30);
  v27 = v25;
  if ( v25 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 66, v26, (unsigned int)v25);
    if ( v10 >= 0 )
      return v27;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b5e8  mov     [rsp-38h+arg_8], rbx
0x14000b5ed  push    rbp
0x14000b5ee  push    rsi
0x14000b5ef  push    rdi
0x14000b5f0  push    r12
0x14000b5f2  push    r13
0x14000b5f4  push    r14
0x14000b5f6  push    r15
0x14000b5f8  mov     rbp, rsp
0x14000b5fb  sub     rsp, 80h
0x14000b602  mov     rbx, [rcx+98h]
0x14000b609  xorps   xmm0, xmm0
0x14000b60c  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000b610  mov     qword ptr [rbp+arg_18], 0
0x14000b618  mov     r14, rdx
0x14000b61b  mov     r15, rcx
0x14000b61e  mov     esi, r8d
0x14000b621  mov     rax, [rbx+150h]
0x14000b628  lea     r12, [rbx+38h]
0x14000b62c  mov     [rbp+var_28], rax
0x14000b630  xor     edx, edx; Wait
0x14000b632  mov     rax, [rcx+0B0h]
0x14000b639  mov     rcx, r12; Mutex
0x14000b63c  mov     [rbp+var_30], rax
0x14000b640  mov     [rbp+P], 0
0x14000b648  mov     [rbp+var_20], rbx
0x14000b64c  call    cs:__imp_KeReleaseMutex
0x14000b653  nop     dword ptr [rax+rax+00h]
0x14000b658  mov     rcx, r14
0x14000b65b  call    GetRemoteDatabaseSize
0x14000b660  mov     edi, eax
0x14000b662  test    eax, eax
0x14000b664  jnz     short loc_14000B6A6
0x14000b666  mov     ebx, 0C000000Dh
0x14000b66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b672  lea     rdi, WPP_GLOBAL_Control
0x14000b679  cmp     rcx, rdi
0x14000b67c  jz      loc_14000B922
0x14000b682  mov     eax, [rcx+2Ch]
0x14000b685  test    al, 1
0x14000b687  jz      loc_14000B922
0x14000b68d  mov     rcx, [rcx+18h]
0x14000b691  mov     edx, 38h ; '8'
0x14000b696  mov     r9d, 0C000000Dh
0x14000b69c  call    WPP_SF_L
0x14000b6a1  jmp     loc_14000B922
0x14000b6a6  xor     r9d, r9d; Alertable
0x14000b6a9  mov     [rsp+80h+Timeout], 0; Timeout
0x14000b6b2  xor     r8d, r8d; WaitMode
0x14000b6b5  xor     edx, edx; WaitReason
0x14000b6b7  mov     rcx, r12; Object
0x14000b6ba  call    cs:__imp_KeWaitForSingleObject
0x14000b6c1  nop     dword ptr [rax+rax+00h]
0x14000b6c6  mov     r8, [rbp+var_30]
0x14000b6ca  mov     rcx, rbx
0x14000b6cd  mov     rdx, [rbp+var_28]
0x14000b6d1  call    VerifyEpoch
0x14000b6d6  mov     ebx, eax
0x14000b6d8  test    eax, eax
0x14000b6da  jns     short loc_14000B71E
0x14000b6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b6e3  lea     rdi, WPP_GLOBAL_Control
0x14000b6ea  cmp     rcx, rdi
0x14000b6ed  jz      short loc_14000B708
0x14000b6ef  mov     edx, [rcx+2Ch]
0x14000b6f2  test    dl, 1
0x14000b6f5  jz      short loc_14000B708
0x14000b6f7  mov     edx, 39h ; '9'
0x14000b6fc  mov     r9d, eax
0x14000b6ff  mov     rcx, [rcx+18h]
0x14000b703  call    WPP_SF_L
0x14000b708  xor     edx, edx; Wait
0x14000b70a  mov     rcx, r12; Mutex
0x14000b70d  call    cs:__imp_KeReleaseMutex
0x14000b714  nop     dword ptr [rax+rax+00h]
0x14000b719  jmp     loc_14000B922
0x14000b71e  lea     r9, [rbp+P]
0x14000b722  mov     r8d, esi
0x14000b725  mov     rdx, r14
0x14000b728  mov     rcx, r15
0x14000b72b  call    GetRemoteDatabaseEntry
0x14000b730  mov     r13, [rbp+P]
0x14000b734  mov     ebx, eax
0x14000b736  test    eax, eax
0x14000b738  jns     short loc_14000B77B
0x14000b73a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b741  lea     rdi, WPP_GLOBAL_Control
0x14000b748  cmp     rcx, rdi
0x14000b74b  jz      short loc_14000B765
0x14000b74d  mov     eax, [rcx+2Ch]
0x14000b750  test    al, 1
0x14000b752  jz      short loc_14000B765
0x14000b754  mov     rcx, [rcx+18h]
0x14000b758  mov     edx, 3Ah ; ':'
0x14000b75d  mov     r9d, ebx
0x14000b760  call    WPP_SF_L
0x14000b765  xor     edx, edx; Wait
0x14000b767  mov     rcx, r12; Mutex
0x14000b76a  call    cs:__imp_KeReleaseMutex
0x14000b771  nop     dword ptr [rax+rax+00h]
0x14000b776  jmp     loc_14000B90C
0x14000b77b  test    r13, r13
0x14000b77e  jnz     short loc_14000B7B6
0x14000b780  mov     ebx, 0C000000Dh
0x14000b785  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b78c  lea     rdi, WPP_GLOBAL_Control
0x14000b793  cmp     rcx, rdi
0x14000b796  jz      loc_14000B708
0x14000b79c  mov     eax, [rcx+2Ch]
0x14000b79f  test    al, 1
0x14000b7a1  jz      loc_14000B708
0x14000b7a7  lea     edx, [r13+3Bh]
0x14000b7ab  mov     r9d, 0C000000Dh
0x14000b7b1  jmp     loc_14000B6FF
0x14000b7b6  xor     edx, edx; Wait
0x14000b7b8  mov     rcx, r12; Mutex
0x14000b7bb  call    cs:__imp_KeReleaseMutex
0x14000b7c2  nop     dword ptr [rax+rax+00h]
0x14000b7c7  mov     ecx, [r13+0]
0x14000b7cb  lea     eax, [rcx+rsi]
0x14000b7ce  cmp     eax, edi
0x14000b7d0  jb      short loc_14000B816
0x14000b7d2  mov     edx, esi
0x14000b7d4  mov     rcx, r14; FileHandle
0x14000b7d7  call    TruncateRemoteDatabase
0x14000b7dc  mov     ebx, eax
0x14000b7de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b7e5  lea     rdi, WPP_GLOBAL_Control
0x14000b7ec  cmp     rcx, rdi
0x14000b7ef  jz      loc_14000B90C
0x14000b7f5  mov     eax, [rcx+2Ch]
0x14000b7f8  test    al, 1
0x14000b7fa  jz      loc_14000B90C
0x14000b800  mov     rcx, [rcx+18h]
0x14000b804  mov     edx, 3Ch ; '<'
0x14000b809  mov     r9d, ebx
0x14000b80c  call    WPP_SF_L
0x14000b811  jmp     loc_14000B90C
0x14000b816  sub     edi, ecx
0x14000b818  mov     r8d, 41746E4Dh
0x14000b81e  sub     edi, esi
0x14000b820  mov     ecx, 102h
0x14000b825  mov     edx, edi
0x14000b827  mov     r15d, edi
0x14000b82a  call    cs:__imp_ExAllocatePool2
0x14000b831  nop     dword ptr [rax+rax+00h]
0x14000b836  mov     [rbp+P], rax
0x14000b83a  mov     rcx, rax
0x14000b83d  test    rax, rax
0x14000b840  jnz     short loc_14000B87C
0x14000b842  mov     ebx, 0C000009Ah
0x14000b847  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b84e  lea     rdi, WPP_GLOBAL_Control
0x14000b855  cmp     rcx, rdi
0x14000b858  jz      loc_14000B90C
0x14000b85e  mov     eax, [rcx+2Ch]
0x14000b861  test    al, 4
0x14000b863  jz      loc_14000B90C
0x14000b869  mov     rcx, [rcx+18h]
0x14000b86d  mov     edx, 3Dh ; '='
0x14000b872  call    WPP_SF_
0x14000b877  jmp     loc_14000B90C
0x14000b87c  mov     eax, [r13+0]
0x14000b880  xor     r9d, r9d; ApcContext
0x14000b883  add     eax, esi
0x14000b885  mov     [rsp+80h+Key], 0; Key
0x14000b88e  mov     qword ptr [rbp+arg_18], rax
0x14000b892  xor     r8d, r8d; ApcRoutine
0x14000b895  lea     rax, [rbp+arg_18]
0x14000b899  xor     edx, edx; Event
0x14000b89b  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x14000b8a0  lea     rax, [rbp+IoStatusBlock]
0x14000b8a4  mov     [rsp+80h+Length], r15d; Length
0x14000b8a9  mov     [rsp+80h+Buffer], rcx; Buffer
0x14000b8ae  mov     rcx, r14; FileHandle
0x14000b8b1  mov     [rsp+80h+Timeout], rax; IoStatusBlock
0x14000b8b6  call    cs:__imp_ZwReadFile
0x14000b8bd  nop     dword ptr [rax+rax+00h]
0x14000b8c2  lea     rdi, WPP_GLOBAL_Control
0x14000b8c9  mov     ebx, eax
0x14000b8cb  test    eax, eax
0x14000b8cd  jns     loc_14000B9A1
0x14000b8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b8da  cmp     rcx, rdi
0x14000b8dd  jz      short loc_14000B8F7
0x14000b8df  mov     eax, [rcx+2Ch]
0x14000b8e2  test    al, 1
0x14000b8e4  jz      short loc_14000B8F7
0x14000b8e6  mov     edx, 3Eh ; '>'
0x14000b8eb  mov     r9d, ebx
0x14000b8ee  mov     rcx, [rcx+18h]
0x14000b8f2  call    WPP_SF_L
0x14000b8f7  mov     rsi, [rbp+P]
0x14000b8fb  xor     edx, edx; Tag
0x14000b8fd  mov     rcx, rsi; P
0x14000b900  call    cs:__imp_ExFreePoolWithTag
0x14000b907  nop     dword ptr [rax+rax+00h]
0x14000b90c  test    r13, r13
0x14000b90f  jz      short loc_14000B922
0x14000b911  xor     edx, edx; Tag
0x14000b913  mov     rcx, r13; P
0x14000b916  call    cs:__imp_ExFreePoolWithTag
0x14000b91d  nop     dword ptr [rax+rax+00h]
0x14000b922  xor     r9d, r9d; Alertable
0x14000b925  mov     [rsp+80h+Timeout], 0; Timeout
0x14000b92e  xor     r8d, r8d; WaitMode
0x14000b931  xor     edx, edx; WaitReason
0x14000b933  mov     rcx, r12; Object
0x14000b936  call    cs:__imp_KeWaitForSingleObject
0x14000b93d  nop     dword ptr [rax+rax+00h]
0x14000b942  mov     r8, [rbp+var_30]
0x14000b946  mov     rdx, [rbp+var_28]
0x14000b94a  mov     rcx, [rbp+var_20]
0x14000b94e  call    VerifyEpoch
0x14000b953  mov     esi, eax
0x14000b955  test    eax, eax
0x14000b957  jns     short loc_14000B983
0x14000b959  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b960  cmp     rcx, rdi
0x14000b963  jz      short loc_14000B97E
0x14000b965  mov     edx, [rcx+2Ch]
0x14000b968  test    dl, 1
0x14000b96b  jz      short loc_14000B97E
0x14000b96d  mov     rcx, [rcx+18h]
0x14000b971  mov     edx, 42h ; 'B'
0x14000b976  mov     r9d, eax
0x14000b979  call    WPP_SF_L
0x14000b97e  test    ebx, ebx
0x14000b980  cmovns  ebx, esi
0x14000b983  mov     eax, ebx
0x14000b985  mov     rbx, [rsp+80h+arg_8]
0x14000b98d  add     rsp, 80h
0x14000b994  pop     r15
0x14000b996  pop     r14
0x14000b998  pop     r13
0x14000b99a  pop     r12
0x14000b99c  pop     rdi
0x14000b99d  pop     rsi
0x14000b99e  pop     rbp
0x14000b99f  retn
0x14000b9a1  cmp     [rbp+IoStatusBlock.Information], r15
0x14000b9a5  jnb     short loc_14000B9D7
0x14000b9a7  mov     ebx, 0C000000Dh
0x14000b9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9b3  cmp     rcx, rdi
0x14000b9b6  jz      loc_14000B8F7
0x14000b9bc  mov     eax, [rcx+2Ch]
0x14000b9bf  test    al, 1
0x14000b9c1  jz      loc_14000B8F7
0x14000b9c7  mov     edx, 3Fh ; '?'
0x14000b9cc  mov     r9d, 0C000000Dh
0x14000b9d2  jmp     loc_14000B8EE
0x14000b9d7  mov     edx, esi
0x14000b9d9  mov     rcx, r14; FileHandle
0x14000b9dc  call    TruncateRemoteDatabase
0x14000b9e1  mov     ebx, eax
0x14000b9e3  test    eax, eax
0x14000b9e5  jns     short loc_14000BA0C
0x14000b9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b9ee  cmp     rcx, rdi
0x14000b9f1  jz      loc_14000B8F7
0x14000b9f7  mov     eax, [rcx+2Ch]
0x14000b9fa  test    al, 1
0x14000b9fc  jz      loc_14000B8F7
0x14000ba02  mov     edx, 40h ; '@'
0x14000ba07  jmp     loc_14000B8EB
0x14000ba0c  mov     [rsp+80h+Key], 0; Key
0x14000ba15  lea     rax, [rbp+arg_18]
0x14000ba19  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x14000ba1e  xor     r9d, r9d; ApcContext
0x14000ba21  mov     qword ptr [rbp+arg_18], rsi
0x14000ba25  lea     rax, [rbp+IoStatusBlock]
0x14000ba29  mov     rsi, [rbp+P]
0x14000ba2d  xor     r8d, r8d; ApcRoutine
0x14000ba30  mov     [rsp+80h+Length], r15d; Length
0x14000ba35  xor     edx, edx; Event
0x14000ba37  mov     [rsp+80h+Buffer], rsi; Buffer
0x14000ba3c  mov     rcx, r14; FileHandle
0x14000ba3f  mov     [rsp+80h+Timeout], rax; IoStatusBlock
0x14000ba44  call    cs:__imp_ZwWriteFile
0x14000ba4b  nop     dword ptr [rax+rax+00h]
0x14000ba50  mov     ebx, eax
0x14000ba52  test    eax, eax
0x14000ba54  jns     loc_14000B8FB
0x14000ba5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ba61  cmp     rcx, rdi
0x14000ba64  jz      loc_14000B8FB
0x14000ba6a  mov     eax, [rcx+2Ch]
0x14000ba6d  test    al, 1
0x14000ba6f  jz      loc_14000B8FB
0x14000ba75  mov     rcx, [rcx+18h]
0x14000ba79  mov     edx, 41h ; 'A'
0x14000ba7e  mov     r9d, ebx
0x14000ba81  call    WPP_SF_L
0x14000ba86  jmp     loc_14000B8FB
```
