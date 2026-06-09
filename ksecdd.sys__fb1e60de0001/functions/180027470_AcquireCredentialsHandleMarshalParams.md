# AcquireCredentialsHandleMarshalParams

- ea: `0x180027470`
- end: `0x18002768b`
- name: `AcquireCredentialsHandleMarshalParams`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002780`
- `0x1800074f4`
- `0x18000f47c`
- `0x1800108a0`
- `0x180027470`

## import_xrefs

- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180027570`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180027570`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180027598`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180027598`
- `ntoskrnl!ZwQueryInformationToken` at `0x1800275eb`
- `ntoskrnl!ZwQueryInformationToken` at `0x1800275eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002764b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002764b`
- `ntoskrnl!ZwClose` at `0x1800275fd`
- `ntoskrnl!ZwClose` at `0x1800275fd`

## pseudocode

```c
__int64 __fastcall AcquireCredentialsHandleMarshalParams(__int64 a1, PVOID *a2, _DWORD *a3)
{
  unsigned __int16 *v3; // rax
  int v5; // r8d
  unsigned __int16 *v8; // rax
  char *v9; // rdi
  __int64 *v11; // rax
  __int64 v12; // rax
  NTSTATUS v13; // esi
  HANDLE Handle; // [rsp+30h] [rbp-39h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-31h] BYREF
  __int128 v16; // [rsp+40h] [rbp-29h] BYREF
  int v17; // [rsp+50h] [rbp-19h]
  int TokenInformation; // [rsp+58h] [rbp-11h] BYREF
  __int128 v19; // [rsp+5Ch] [rbp-Dh]
  __int128 v20; // [rsp+6Ch] [rbp+3h]
  __int128 v21; // [rsp+7Ch] [rbp+13h]
  int v22; // [rsp+8Ch] [rbp+23h]

  v3 = *(unsigned __int16 **)(a1 + 32);
  v5 = 0;
  v17 = 0;
  v16 = 0;
  if ( v3 )
  {
    v5 = *v3;
    v17 = v5;
  }
  v8 = *(unsigned __int16 **)(a1 + 40);
  if ( v8 )
  {
    v5 += *v8;
    v17 = v5;
  }
  if ( *(_QWORD *)(a1 + 72) )
    v17 = *(_DWORD *)(a1 + 64) + v5;
  Handle = 0;
  AsyncSspiMarshaler<KernelAllocator>::Allocate<_AsyncAcquireCredentialsHandleParams>(&v16, &Handle, a3);
  v9 = (char *)Handle;
  if ( !Handle )
    return 3221225626LL;
  *a2 = Handle;
  AsyncSspiMarshaler<KernelAllocator>::CopyString(&v16, v9 + 48, *(_QWORD *)(a1 + 32));
  AsyncSspiMarshaler<KernelAllocator>::CopyString(&v16, v9 + 64, *(_QWORD *)(a1 + 40));
  *((_DWORD *)v9 + 20) = *(_DWORD *)(a1 + 48);
  v11 = *(__int64 **)(a1 + 56);
  if ( v11 )
  {
    v12 = *v11;
    v13 = 0;
  }
  else
  {
    Handle = 0;
    v13 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, 0x200u, &Handle);
    if ( v13 == -1073741700 )
      v13 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &Handle);
    if ( v13 < 0 )
      goto LABEL_23;
    ReturnLength = 0;
    TokenInformation = 0;
    v22 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v13 = ZwQueryInformationToken(Handle, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength);
    ZwClose(Handle);
    if ( v13 < 0 )
    {
LABEL_23:
      if ( *a2 )
      {
        ExFreePoolWithTag(*a2, 0);
        *a2 = 0;
        *a3 = 0;
      }
      return (unsigned int)v13;
    }
    v12 = *(_QWORD *)((char *)&v19 + 4);
  }
  *(_QWORD *)(v9 + 84) = v12;
  if ( *(_QWORD *)(a1 + 72) )
  {
    *((_DWORD *)v9 + 24) = *(_DWORD *)(a1 + 64);
    *((_QWORD *)v9 + 13) = *(_QWORD *)(a1 + 72);
    AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<unsigned char>(
      &v16,
      v9 + 112,
      *(_QWORD *)(a1 + 72),
      *(unsigned int *)(a1 + 64));
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180027470  mov     [rsp-8+arg_18], rbx
0x180027475  push    rbp
0x180027476  push    rsi
0x180027477  push    rdi
0x180027478  push    r14
0x18002747a  push    r15
0x18002747c  lea     rbp, [rsp-37h]
0x180027481  sub     rsp, 0A0h
0x180027488  mov     rax, cs:__security_cookie
0x18002748f  xor     rax, rsp
0x180027492  mov     [rbp+57h+var_30], rax
0x180027496  mov     rax, [rcx+20h]
0x18002749a  mov     r15, r8
0x18002749d  xor     r8d, r8d
0x1800274a0  xorps   xmm0, xmm0
0x1800274a3  mov     [rbp+57h+var_70], r8d
0x1800274a7  mov     r14, rdx
0x1800274aa  mov     rbx, rcx
0x1800274ad  movdqu  [rbp+57h+var_80], xmm0
0x1800274b2  test    rax, rax
0x1800274b5  jz      short loc_1800274BF
0x1800274b7  movzx   r8d, word ptr [rax]
0x1800274bb  mov     [rbp+57h+var_70], r8d
0x1800274bf  mov     rax, [rcx+28h]
0x1800274c3  test    rax, rax
0x1800274c6  jz      short loc_1800274D2
0x1800274c8  movzx   eax, word ptr [rax]
0x1800274cb  add     r8d, eax
0x1800274ce  mov     [rbp+57h+var_70], r8d
0x1800274d2  cmp     qword ptr [rcx+48h], 0
0x1800274d7  jz      short loc_1800274E1
0x1800274d9  add     r8d, [rcx+40h]
0x1800274dd  mov     [rbp+57h+var_70], r8d
0x1800274e1  mov     r8, r15
0x1800274e4  mov     [rbp+57h+Handle], 0
0x1800274ec  lea     rdx, [rbp+57h+Handle]
0x1800274f0  lea     rcx, [rbp+57h+var_80]
0x1800274f4  call    ??$Allocate@U_AsyncAcquireCredentialsHandleParams@@@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAU_AsyncAcquireCredentialsHandleParams@@PEAK@Z; AsyncSspiMarshaler<KernelAllocator>::Allocate<_AsyncAcquireCredentialsHandleParams>(_AsyncAcquireCredentialsHandleParams * *,ulong *)
0x1800274f9  mov     rdi, [rbp+57h+Handle]
0x1800274fd  test    rdi, rdi
0x180027500  jnz     short loc_18002750C
0x180027502  mov     eax, 0C000009Ah
0x180027507  jmp     loc_180027667
0x18002750c  mov     [r14], rdi
0x18002750f  lea     rdx, [rdi+30h]
0x180027513  mov     r8, [rbx+20h]
0x180027517  lea     rcx, [rbp+57h+var_80]
0x18002751b  call    ?CopyString@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAU_UNICODE_STRING@@0@Z; AsyncSspiMarshaler<KernelAllocator>::CopyString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180027520  mov     r8, [rbx+28h]
0x180027524  lea     rdx, [rdi+40h]
0x180027528  lea     rcx, [rbp+57h+var_80]
0x18002752c  call    ?CopyString@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAU_UNICODE_STRING@@0@Z; AsyncSspiMarshaler<KernelAllocator>::CopyString(_UNICODE_STRING *,_UNICODE_STRING *)
0x180027531  mov     eax, [rbx+30h]
0x180027534  mov     [rdi+50h], eax
0x180027537  mov     rax, [rbx+38h]
0x18002753b  test    rax, rax
0x18002753e  jz      short loc_18002754A
0x180027540  mov     rax, [rax]
0x180027543  xor     esi, esi
0x180027545  jmp     loc_180027611
0x18002754a  lea     rax, [rbp+57h+Handle]
0x18002754e  mov     [rbp+57h+Handle], 0
0x180027556  mov     r9d, 200h; HandleAttributes
0x18002755c  mov     [rsp+0C0h+TokenHandle], rax; TokenHandle
0x180027561  mov     r8b, 1; OpenAsSelf
0x180027564  mov     edx, 8; DesiredAccess
0x180027569  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180027570  call    cs:__imp_ZwOpenThreadTokenEx
0x180027577  nop     dword ptr [rax+rax+00h]
0x18002757c  mov     esi, eax
0x18002757e  cmp     eax, 0C000007Ch
0x180027583  jnz     short loc_1800275A6
0x180027585  lea     r9, [rbp+57h+Handle]; TokenHandle
0x180027589  mov     edx, 8; DesiredAccess
0x18002758e  mov     r8d, 200h; HandleAttributes
0x180027594  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180027598  call    cs:__imp_ZwOpenProcessTokenEx
0x18002759f  nop     dword ptr [rax+rax+00h]
0x1800275a4  mov     esi, eax
0x1800275a6  test    esi, esi
0x1800275a8  js      loc_180027641
0x1800275ae  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x1800275b2  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800275b6  xorps   xmm0, xmm0
0x1800275b9  mov     [rbp+57h+ReturnLength], 0
0x1800275c0  xor     eax, eax
0x1800275c2  mov     [rbp+57h+TokenInformation], 0
0x1800275c9  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800275cf  mov     [rbp+57h+var_34], eax
0x1800275d2  lea     rax, [rbp+57h+ReturnLength]
0x1800275d6  movups  [rbp+57h+var_64], xmm0
0x1800275da  mov     [rsp+0C0h+TokenHandle], rax; ReturnLength
0x1800275df  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800275e3  movups  [rbp+57h+var_54], xmm0
0x1800275e7  movups  [rbp+57h+var_44], xmm0
0x1800275eb  call    cs:__imp_ZwQueryInformationToken
0x1800275f2  nop     dword ptr [rax+rax+00h]
0x1800275f7  mov     rcx, [rbp+57h+Handle]; Handle
0x1800275fb  mov     esi, eax
0x1800275fd  call    cs:__imp_ZwClose
0x180027604  nop     dword ptr [rax+rax+00h]
0x180027609  test    esi, esi
0x18002760b  js      short loc_180027641
0x18002760d  mov     rax, qword ptr [rbp+57h+var_64+4]
0x180027611  mov     [rdi+54h], rax
0x180027615  cmp     qword ptr [rbx+48h], 0
0x18002761a  jz      short loc_180027665
0x18002761c  mov     eax, [rbx+40h]
0x18002761f  lea     rdx, [rdi+70h]
0x180027623  mov     [rdi+60h], eax
0x180027626  lea     rcx, [rbp+57h+var_80]
0x18002762a  mov     rax, [rbx+48h]
0x18002762e  mov     [rdi+68h], rax
0x180027632  mov     r9d, [rbx+40h]
0x180027636  mov     r8, [rbx+48h]
0x18002763a  call    ??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z; AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)
0x18002763f  jmp     short loc_180027665
0x180027641  mov     rcx, [r14]; P
0x180027644  test    rcx, rcx
0x180027647  jz      short loc_180027665
0x180027649  xor     edx, edx; Tag
0x18002764b  call    cs:__imp_ExFreePoolWithTag
0x180027652  nop     dword ptr [rax+rax+00h]
0x180027657  mov     qword ptr [r14], 0
0x18002765e  mov     dword ptr [r15], 0
0x180027665  mov     eax, esi
0x180027667  mov     rcx, [rbp+57h+var_30]
0x18002766b  xor     rcx, rsp; StackCookie
0x18002766e  call    __security_check_cookie
0x180027673  mov     rbx, [rsp+0C0h+arg_18]
0x18002767b  add     rsp, 0A0h
0x180027682  pop     r15
0x180027684  pop     r14
0x180027686  pop     rdi
0x180027687  pop     rsi
0x180027688  pop     rbp
0x180027689  retn
```
