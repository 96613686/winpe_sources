# CscFinalizeLogicalView

- ea: `0x1400759d0`
- end: `0x140075b03`
- name: `CscFinalizeLogicalView`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000a634`
- `0x140016a04`
- `0x14001b710`
- `0x1400759d0`
- `0x140075f70`
- `0x140076898`
- `0x140076a38`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140075ac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ae4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ae4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140075a47`
- `ntoskrnl!ExDeleteResourceLite` at `0x140075a47`

## pseudocode

```c
__int64 __fastcall CscFinalizeLogicalView(__int64 a1)
{
  __int64 v1; // rbx
  signed __int64 v3; // rdi
  void *v4; // rcx
  signed __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, a1);
  CscFlushLViewWasPreviouslyOffline(a1);
  CscOfflineLviewCacheFinalizeForLogicalPath((PERESOURCE)(CscDevExtn + 384));
  if ( v1 )
  {
    ExDeleteResourceLite((PERESOURCE)(v1 + 128));
    v3 = _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(a1 + 48) + 40LL), 0, 0);
    v6 = v3;
    if ( v3 )
    {
      CscStoreDereferenceEntry(&v6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v3, 0, 0);
    }
    CscNotifyUninitializeSync(v1);
    v4 = *(void **)(v1 + 232);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0);
      *(_QWORD *)(v1 + 232) = 0;
    }
    ExFreePoolWithTag((PVOID)v1, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1400759d0  mov     [rsp+arg_8], rbx
0x1400759d5  mov     [rsp+arg_10], rbp
0x1400759da  push    rdi
0x1400759db  sub     rsp, 30h
0x1400759df  mov     rbx, [rcx+30h]
0x1400759e3  mov     rdi, rcx
0x1400759e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400759ed  lea     rbp, WPP_GLOBAL_Control
0x1400759f4  cmp     rcx, rbp
0x1400759f7  jz      short loc_140075A18
0x1400759f9  mov     eax, [rcx+2Ch]
0x1400759fc  test    al, 40h
0x1400759fe  jz      short loc_140075A18
0x140075a00  mov     rcx, [rcx+18h]
0x140075a04  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075a0b  mov     edx, 30h ; '0'
0x140075a10  mov     r9, rdi
0x140075a13  call    WPP_SF_q
0x140075a18  mov     rcx, rdi
0x140075a1b  call    CscFlushLViewWasPreviouslyOffline
0x140075a20  mov     rcx, cs:CscDevExtn
0x140075a27  mov     rdx, [rdi+38h]
0x140075a2b  add     rcx, 180h; Resource
0x140075a32  call    CscOfflineLviewCacheFinalizeForLogicalPath
0x140075a37  test    rbx, rbx
0x140075a3a  jz      loc_140075AF0
0x140075a40  lea     rcx, [rbx+80h]; Resource
0x140075a47  call    cs:__imp_ExDeleteResourceLite
0x140075a4e  nop     dword ptr [rax+rax+00h]
0x140075a53  mov     rdx, [rdi+30h]
0x140075a57  xor     ecx, ecx
0x140075a59  xor     eax, eax
0x140075a5b  lock cmpxchg [rdx+28h], rcx
0x140075a61  mov     rdi, rax
0x140075a64  mov     [rsp+38h+arg_0], rax
0x140075a69  jz      short loc_140075AB2
0x140075a6b  lea     rcx, [rsp+38h+arg_0]
0x140075a70  call    CscStoreDereferenceEntry
0x140075a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140075a7c  cmp     rcx, rbp
0x140075a7f  jz      short loc_140075AB2
0x140075a81  mov     eax, [rcx+2Ch]
0x140075a84  test    al, 40h
0x140075a86  jz      short loc_140075AB2
0x140075a88  mov     rcx, [rcx+18h]
0x140075a8c  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075a93  mov     edx, 31h ; '1'
0x140075a98  mov     [rsp+38h+var_10], 0
0x140075aa1  mov     r9, rdi
0x140075aa4  mov     [rsp+38h+var_18], 0
0x140075aad  call    WPP_SF_qqq
0x140075ab2  mov     rcx, rbx
0x140075ab5  call    CscNotifyUninitializeSync
0x140075aba  mov     rcx, [rbx+0E8h]; P
0x140075ac1  test    rcx, rcx
0x140075ac4  jz      short loc_140075ADF
0x140075ac6  xor     edx, edx; Tag
0x140075ac8  call    cs:__imp_ExFreePoolWithTag
0x140075acf  nop     dword ptr [rax+rax+00h]
0x140075ad4  mov     qword ptr [rbx+0E8h], 0
0x140075adf  xor     edx, edx; Tag
0x140075ae1  mov     rcx, rbx; P
0x140075ae4  call    cs:__imp_ExFreePoolWithTag
0x140075aeb  nop     dword ptr [rax+rax+00h]
0x140075af0  mov     rbx, [rsp+38h+arg_8]
0x140075af5  xor     eax, eax
0x140075af7  mov     rbp, [rsp+38h+arg_10]
0x140075afc  add     rsp, 30h
0x140075b00  pop     rdi
0x140075b01  retn
```
