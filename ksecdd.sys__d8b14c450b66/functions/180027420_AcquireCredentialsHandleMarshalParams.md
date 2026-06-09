# AcquireCredentialsHandleMarshalParams

- ea: `0x180027420`
- end: `0x18002763b`
- name: `AcquireCredentialsHandleMarshalParams`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002780`
- `0x1800074f4`
- `0x18000f414`
- `0x180010840`
- `0x180027420`

## import_xrefs

- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180027520`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x180027520`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180027548`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x180027548`
- `ntoskrnl!ZwQueryInformationToken` at `0x18002759b`
- `ntoskrnl!ZwQueryInformationToken` at `0x18002759b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800275fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800275fb`
- `ntoskrnl!ZwClose` at `0x1800275ad`
- `ntoskrnl!ZwClose` at `0x1800275ad`

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
  AsyncSspiMarshaler<KernelAllocator>::Allocate<_AsyncAcquireCredentialsHandleParams>((__int64)&v16, &Handle, a3);
  v9 = (char *)Handle;
  if ( !Handle )
    return 3221225626LL;
  *a2 = Handle;
  AsyncSspiMarshaler<KernelAllocator>::CopyString((__int64)&v16, (__int64)(v9 + 48), *(unsigned __int16 **)(a1 + 32));
  AsyncSspiMarshaler<KernelAllocator>::CopyString((__int64)&v16, (__int64)(v9 + 64), *(unsigned __int16 **)(a1 + 40));
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
      (__int64)&v16,
      (_QWORD *)v9 + 14,
      *(const void **)(a1 + 72),
      *(_DWORD *)(a1 + 64));
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180027420  mov     [rsp-8+arg_18], rbx
0x180027425  push    rbp
0x180027426  push    rsi
0x180027427  push    rdi
0x180027428  push    r14
0x18002742a  push    r15
0x18002742c  lea     rbp, [rsp-37h]
0x180027431  sub     rsp, 0A0h
0x180027438  mov     rax, cs:__security_cookie
0x18002743f  xor     rax, rsp
0x180027442  mov     [rbp+57h+var_30], rax
0x180027446  mov     rax, [rcx+20h]
0x18002744a  mov     r15, r8
0x18002744d  xor     r8d, r8d
0x180027450  xorps   xmm0, xmm0
0x180027453  mov     [rbp+57h+var_70], r8d
0x180027457  mov     r14, rdx
0x18002745a  mov     rbx, rcx
0x18002745d  movdqu  [rbp+57h+var_80], xmm0
0x180027462  test    rax, rax
0x180027465  jz      short loc_18002746F
0x180027467  movzx   r8d, word ptr [rax]
0x18002746b  mov     [rbp+57h+var_70], r8d
0x18002746f  mov     rax, [rcx+28h]
0x180027473  test    rax, rax
0x180027476  jz      short loc_180027482
0x180027478  movzx   eax, word ptr [rax]
0x18002747b  add     r8d, eax
0x18002747e  mov     [rbp+57h+var_70], r8d
0x180027482  cmp     qword ptr [rcx+48h], 0
0x180027487  jz      short loc_180027491
0x180027489  add     r8d, [rcx+40h]
0x18002748d  mov     [rbp+57h+var_70], r8d
0x180027491  mov     r8, r15
0x180027494  mov     [rbp+57h+Handle], 0
0x18002749c  lea     rdx, [rbp+57h+Handle]
0x1800274a0  lea     rcx, [rbp+57h+var_80]
0x1800274a4  call    ??$Allocate@U_AsyncAcquireCredentialsHandleParams@@@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAU_AsyncAcquireCredentialsHandleParams@@PEAK@Z; AsyncSspiMarshaler<KernelAllocator>::Allocate<_AsyncAcquireCredentialsHandleParams>(_AsyncAcquireCredentialsHandleParams * *,ulong *)
0x1800274a9  mov     rdi, [rbp+57h+Handle]
0x1800274ad  test    rdi, rdi
0x1800274b0  jnz     short loc_1800274BC
0x1800274b2  mov     eax, 0C000009Ah
0x1800274b7  jmp     loc_180027617
0x1800274bc  mov     [r14], rdi
0x1800274bf  lea     rdx, [rdi+30h]
0x1800274c3  mov     r8, [rbx+20h]
0x1800274c7  lea     rcx, [rbp+57h+var_80]
0x1800274cb  call    ?CopyString@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAU_UNICODE_STRING@@0@Z; AsyncSspiMarshaler<KernelAllocator>::CopyString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800274d0  mov     r8, [rbx+28h]
0x1800274d4  lea     rdx, [rdi+40h]
0x1800274d8  lea     rcx, [rbp+57h+var_80]
0x1800274dc  call    ?CopyString@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAU_UNICODE_STRING@@0@Z; AsyncSspiMarshaler<KernelAllocator>::CopyString(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800274e1  mov     eax, [rbx+30h]
0x1800274e4  mov     [rdi+50h], eax
0x1800274e7  mov     rax, [rbx+38h]
0x1800274eb  test    rax, rax
0x1800274ee  jz      short loc_1800274FA
0x1800274f0  mov     rax, [rax]
0x1800274f3  xor     esi, esi
0x1800274f5  jmp     loc_1800275C1
0x1800274fa  lea     rax, [rbp+57h+Handle]
0x1800274fe  mov     [rbp+57h+Handle], 0
0x180027506  mov     r9d, 200h; HandleAttributes
0x18002750c  mov     [rsp+0C0h+TokenHandle], rax; TokenHandle
0x180027511  mov     r8b, 1; OpenAsSelf
0x180027514  mov     edx, 8; DesiredAccess
0x180027519  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180027520  call    cs:__imp_ZwOpenThreadTokenEx
0x180027527  nop     dword ptr [rax+rax+00h]
0x18002752c  mov     esi, eax
0x18002752e  cmp     eax, 0C000007Ch
0x180027533  jnz     short loc_180027556
0x180027535  lea     r9, [rbp+57h+Handle]; TokenHandle
0x180027539  mov     edx, 8; DesiredAccess
0x18002753e  mov     r8d, 200h; HandleAttributes
0x180027544  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180027548  call    cs:__imp_ZwOpenProcessTokenEx
0x18002754f  nop     dword ptr [rax+rax+00h]
0x180027554  mov     esi, eax
0x180027556  test    esi, esi
0x180027558  js      loc_1800275F1
0x18002755e  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x180027562  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180027566  xorps   xmm0, xmm0
0x180027569  mov     [rbp+57h+ReturnLength], 0
0x180027570  xor     eax, eax
0x180027572  mov     [rbp+57h+TokenInformation], 0
0x180027579  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002757f  mov     [rbp+57h+var_34], eax
0x180027582  lea     rax, [rbp+57h+ReturnLength]
0x180027586  movups  [rbp+57h+var_64], xmm0
0x18002758a  mov     [rsp+0C0h+TokenHandle], rax; ReturnLength
0x18002758f  lea     edx, [r9-2Eh]; TokenInformationClass
0x180027593  movups  [rbp+57h+var_54], xmm0
0x180027597  movups  [rbp+57h+var_44], xmm0
0x18002759b  call    cs:__imp_ZwQueryInformationToken
0x1800275a2  nop     dword ptr [rax+rax+00h]
0x1800275a7  mov     rcx, [rbp+57h+Handle]; Handle
0x1800275ab  mov     esi, eax
0x1800275ad  call    cs:__imp_ZwClose
0x1800275b4  nop     dword ptr [rax+rax+00h]
0x1800275b9  test    esi, esi
0x1800275bb  js      short loc_1800275F1
0x1800275bd  mov     rax, qword ptr [rbp+57h+var_64+4]
0x1800275c1  mov     [rdi+54h], rax
0x1800275c5  cmp     qword ptr [rbx+48h], 0
0x1800275ca  jz      short loc_180027615
0x1800275cc  mov     eax, [rbx+40h]
0x1800275cf  lea     rdx, [rdi+70h]
0x1800275d3  mov     [rdi+60h], eax
0x1800275d6  lea     rcx, [rbp+57h+var_80]
0x1800275da  mov     rax, [rbx+48h]
0x1800275de  mov     [rdi+68h], rax
0x1800275e2  mov     r9d, [rbx+40h]
0x1800275e6  mov     r8, [rbx+48h]
0x1800275ea  call    ??$CopyBuffer@E@?$AsyncSspiMarshaler@UKernelAllocator@@@@QEAAJPEAPEAEPEAEK@Z; AsyncSspiMarshaler<KernelAllocator>::CopyBuffer<uchar>(uchar * *,uchar *,ulong)
0x1800275ef  jmp     short loc_180027615
0x1800275f1  mov     rcx, [r14]; P
0x1800275f4  test    rcx, rcx
0x1800275f7  jz      short loc_180027615
0x1800275f9  xor     edx, edx; Tag
0x1800275fb  call    cs:__imp_ExFreePoolWithTag
0x180027602  nop     dword ptr [rax+rax+00h]
0x180027607  mov     qword ptr [r14], 0
0x18002760e  mov     dword ptr [r15], 0
0x180027615  mov     eax, esi
0x180027617  mov     rcx, [rbp+57h+var_30]
0x18002761b  xor     rcx, rsp; StackCookie
0x18002761e  call    __security_check_cookie
0x180027623  mov     rbx, [rsp+0C0h+arg_18]
0x18002762b  add     rsp, 0A0h
0x180027632  pop     r15
0x180027634  pop     r14
0x180027636  pop     rdi
0x180027637  pop     rsi
0x180027638  pop     rbp
0x180027639  retn
```
