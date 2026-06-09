# PcwpGetCounterSetSecurityDescriptor(_UNICODE_STRING const *,ulong,void *,ulong *)

- ea: `0x14000e3e8`
- end: `0x14000e4e1`
- name: `?PcwpGetCounterSetSecurityDescriptor@@YAJPEBU_UNICODE_STRING@@KPEAXPEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, DWORD, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a500`

## callees

- `0x14000cf6c`
- `0x14000dd2c`
- `0x14000e3e8`
- `0x14000ed84`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e467`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000e467`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e450`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e450`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e4b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e4b2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e4a6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000e4a6`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000e492`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000e492`

## pseudocode

```c
__int64 __fastcall PcwpGetCounterSetSecurityDescriptor(
        const struct _UNICODE_STRING *a1,
        DWORD a2,
        void *a3,
        unsigned int *a4)
{
  ACCESS_MASK v6; // edi
  __int64 v7; // rcx
  int v8; // ebx
  PSECURITY_DESCRIPTOR *v10; // rbx
  int v11; // edi
  __int64 v12; // rcx
  struct PCW_SILO_NEUTRAL_COUNTERSET *v13; // [rsp+20h] [rbp-28h] BYREF
  DWORD SecurityInformation; // [rsp+58h] [rbp+10h] BYREF

  SecurityInformation = a2;
  v13 = 0;
  v6 = ((a2 & 0x17) != 0 ? 0x20000 : 0) | 0x1000000;
  if ( (a2 & 8) == 0 )
    v6 = (a2 & 0x17) != 0 ? 0x20000 : 0;
  v8 = PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(&v13);
  if ( v8 >= 0 )
  {
    KeEnterCriticalRegion();
    v10 = (PSECURITY_DESCRIPTOR *)v13;
    ExAcquirePushLockSharedEx((char *)v13 + 88, 0);
    v11 = PcwpAccessCheck(v10, v6);
    if ( v11 >= 0 )
      v11 = SeQuerySecurityDescriptorInfo(&SecurityInformation, a3, a4, v10 + 12);
    ExReleasePushLockSharedEx(v10 + 11, 0);
    KeLeaveCriticalRegion();
    if ( v10 )
      ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v12, v10);
    return (unsigned int)v11;
  }
  else
  {
    if ( v13 )
      ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v7, v13);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x14000e3e8  mov     rax, rsp
0x14000e3eb  mov     [rax+8], rbx
0x14000e3ef  mov     [rax+18h], rbp
0x14000e3f3  mov     [rax+10h], edx
0x14000e3f6  push    rsi
0x14000e3f7  push    rdi
0x14000e3f8  push    r14
0x14000e3fa  sub     rsp, 30h
0x14000e3fe  mov     qword ptr [rax-28h], 0
0x14000e406  mov     rbp, r9
0x14000e409  mov     eax, edx
0x14000e40b  mov     r14, r8
0x14000e40e  and     al, 17h
0x14000e410  neg     al
0x14000e412  sbb     r10d, r10d
0x14000e415  and     r10d, 20000h
0x14000e41c  mov     edi, r10d
0x14000e41f  bts     edi, 18h
0x14000e423  test    dl, 8
0x14000e426  mov     rdx, rcx
0x14000e429  lea     rcx, [rsp+48h+var_28]
0x14000e42e  cmovz   edi, r10d
0x14000e432  call    ?FindOrCreate@PCW_SILO_NEUTRAL_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000e437  mov     ebx, eax
0x14000e439  test    eax, eax
0x14000e43b  jns     short loc_14000E450
0x14000e43d  mov     rdx, [rsp+48h+var_28]
0x14000e442  test    rdx, rdx
0x14000e445  jz      short loc_14000E44C
0x14000e447  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000e44c  mov     eax, ebx
0x14000e44e  jmp     short loc_14000E4CD
0x14000e450  call    cs:__imp_KeEnterCriticalRegion
0x14000e457  nop     dword ptr [rax+rax+00h]
0x14000e45c  mov     rbx, [rsp+48h+var_28]
0x14000e461  xor     edx, edx
0x14000e463  lea     rcx, [rbx+58h]
0x14000e467  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000e46e  nop     dword ptr [rax+rax+00h]
0x14000e473  mov     edx, edi; unsigned int
0x14000e475  mov     rcx, rbx; struct PCW_SILO_NEUTRAL_COUNTERSET *
0x14000e478  call    ?PcwpAccessCheck@@YAJPEBVPCW_SILO_NEUTRAL_COUNTERSET@@K@Z; PcwpAccessCheck(PCW_SILO_NEUTRAL_COUNTERSET const *,ulong)
0x14000e47d  mov     edi, eax
0x14000e47f  test    eax, eax
0x14000e481  js      short loc_14000E4A0
0x14000e483  lea     r9, [rbx+60h]; ObjectsSecurityDescriptor
0x14000e487  mov     r8, rbp; Length
0x14000e48a  mov     rdx, r14; SecurityDescriptor
0x14000e48d  lea     rcx, [rsp+48h+SecurityInformation]; SecurityInformation
0x14000e492  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14000e499  nop     dword ptr [rax+rax+00h]
0x14000e49e  mov     edi, eax
0x14000e4a0  xor     edx, edx
0x14000e4a2  lea     rcx, [rbx+58h]
0x14000e4a6  call    cs:__imp_ExReleasePushLockSharedEx
0x14000e4ad  nop     dword ptr [rax+rax+00h]
0x14000e4b2  call    cs:__imp_KeLeaveCriticalRegion
0x14000e4b9  nop     dword ptr [rax+rax+00h]
0x14000e4be  test    rbx, rbx
0x14000e4c1  jz      short loc_14000E4CB
0x14000e4c3  mov     rdx, rbx
0x14000e4c6  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000e4cb  mov     eax, edi
0x14000e4cd  mov     rbx, [rsp+48h+arg_0]
0x14000e4d2  mov     rbp, [rsp+48h+arg_10]
0x14000e4d7  add     rsp, 30h
0x14000e4db  pop     r14
0x14000e4dd  pop     rdi
0x14000e4de  pop     rsi
0x14000e4df  retn
```
