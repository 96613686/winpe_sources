# HidpDestroyFileExtension

- ea: `0x18000e880`
- end: `0x18000eb9e`
- name: `HidpDestroyFileExtension`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000621c`

## callees

- `0x18000e880`
- `0x18000ebb0`
- `0x1800127d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18000ea73`
- `ntoskrnl!IofCompleteRequest` at `0x18000ea73`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e9cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e9e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ea92`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e9cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e9e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ea92`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000e8f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000e98d`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000e8f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000e98d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000e89e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000e91f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000e89e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000e91f`

## pseudocode

```c
void __fastcall HidpDestroyFileExtension(__int64 a1, __int64 a2)
{
  KIRQL v4; // al
  _QWORD *v5; // rcx
  _QWORD *v6; // rdi
  KIRQL v7; // bp
  __int64 v8; // rdx
  __int64 v9; // r15
  __int64 v10; // rbp
  KIRQL v11; // r10
  _QWORD **v12; // rcx
  __int64 Irp; // r8
  _QWORD *v14; // rdx
  _QWORD *v15; // rax
  int v16; // r8d
  __int64 *v17; // rax
  void *v18; // rcx
  __int64 *v19; // rcx
  __int64 **v20; // rdx
  IRP *v21; // rdi
  __int64 v22; // rax
  __int64 **v23; // rcx
  __int64 v24; // [rsp+60h] [rbp-68h]
  __int64 *v25; // [rsp+70h] [rbp-58h] BYREF
  __int64 **v26; // [rsp+78h] [rbp-50h]

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 72));
  v5 = *(_QWORD **)(a2 + 40);
  v6 = (_QWORD *)(a2 + 40);
  v7 = v4;
  if ( v5 != (_QWORD *)(a2 + 40) )
  {
    if ( (_QWORD *)v5[1] != v6 )
      goto LABEL_30;
    v8 = *v5;
    if ( *(_QWORD **)(*v5 + 8LL) != v5 )
      goto LABEL_30;
    *v6 = v8;
    *(_QWORD *)(v8 + 8) = v6;
    v5[1] = v5;
    *v5 = v5;
    --*(_DWORD *)(a2 + 88);
    for ( ; v5; --*(_DWORD *)(a2 + 88) )
    {
      ExFreePoolWithTag(v5, 0);
      v5 = (_QWORD *)*v6;
      if ( (_QWORD *)*v6 == v6 )
        break;
      if ( (_QWORD *)v5[1] != v6 )
        goto LABEL_30;
      v22 = *v5;
      if ( *(_QWORD **)(*v5 + 8LL) != v5 )
        goto LABEL_30;
      *v6 = v22;
      *(_QWORD *)(v22 + 8) = v6;
      v5[1] = v5;
      *v5 = v5;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 72), v7);
  v9 = *(_QWORD *)(a2 + 8);
  v10 = *(_QWORD *)(a2 + 16);
  v26 = &v25;
  v25 = (__int64 *)&v25;
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 72));
  v12 = (_QWORD **)(a2 + 24);
LABEL_6:
  Irp = 0;
  do
  {
    v14 = *v12;
    if ( *v12 == v12 )
      break;
    if ( (_QWORD **)v14[1] != v12 )
      goto LABEL_30;
    v15 = (_QWORD *)*v14;
    if ( *(_QWORD **)(*v14 + 8LL) != v14 )
      goto LABEL_30;
    *v12 = v15;
    Irp = (__int64)(v14 - 21);
    v15[1] = v12;
    if ( !_InterlockedExchange64(v14 - 8, 0) )
    {
      v14[1] = v14;
      *v14 = v14;
      goto LABEL_6;
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
  }
  while ( v14 == (_QWORD *)168 );
  if ( Irp )
  {
    while ( 1 )
    {
      v23 = v26;
      if ( *v26 != (__int64 *)&v25 )
        break;
      *(_QWORD *)(Irp + 176) = v26;
      *(_QWORD *)(Irp + 168) = &v25;
      *v23 = (__int64 *)(Irp + 168);
      v26 = (__int64 **)(Irp + 168);
      Irp = DequeueInterruptReadIrp(a1, a2);
      if ( !Irp )
        goto LABEL_13;
    }
LABEL_30:
    __fastfail(3u);
  }
LABEL_13:
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 72), v11);
  while ( 1 )
  {
    v17 = v25;
    if ( v25 == (__int64 *)&v25 )
      break;
    if ( (__int64 **)v25[1] != &v25 )
      goto LABEL_30;
    v19 = (__int64 *)*v25;
    if ( *(__int64 **)(*v25 + 8) != v25 )
      goto LABEL_30;
    v25 = (__int64 *)*v25;
    v20 = &v25;
    v21 = (IRP *)(v17 - 21);
    v19[1] = (__int64)&v25;
    *((_DWORD *)v17 - 30) = -1073741667;
    LOBYTE(v20) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v24) = -1073741667;
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v20,
        v16,
        *(_QWORD *)(v9 + 672),
        4,
        5,
        11,
        (__int64)WPP_d3422704dcd235ea7c23ca0d62a7cccc_Traceguids,
        *(_QWORD *)(*(_QWORD *)(v10 + 64) + 32LL),
        *(_DWORD *)(v10 + 8),
        *(_QWORD *)(v10 + 48),
        (_BYTE)v17 + 88,
        v24);
    }
    IofCompleteRequest(v21, 0);
  }
  v18 = *(void **)(a2 + 152);
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0);
    *(_QWORD *)(a2 + 152) = 0;
  }
  ExFreePoolWithTag((PVOID)a2, 0);
}

```

## disassembly

```asm
0x18000e880  push    rbx
0x18000e882  push    rbp
0x18000e883  push    rsi
0x18000e884  push    rdi
0x18000e885  push    r12
0x18000e887  push    r13
0x18000e889  push    r14
0x18000e88b  push    r15
0x18000e88d  sub     rsp, 88h
0x18000e894  mov     r14, rcx
0x18000e897  mov     rbx, rdx
0x18000e89a  lea     rcx, [rdx+48h]; SpinLock
0x18000e89e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000e8a5  nop     dword ptr [rax+rax+00h]
0x18000e8aa  mov     rcx, [rbx+28h]; P
0x18000e8ae  lea     rdi, [rbx+28h]
0x18000e8b2  movzx   ebp, al
0x18000e8b5  cmp     rcx, rdi
0x18000e8b8  jz      short loc_18000E8EB
0x18000e8ba  cmp     [rcx+8], rdi
0x18000e8be  jnz     loc_18000EAD5
0x18000e8c4  mov     rdx, [rcx]
0x18000e8c7  cmp     [rdx+8], rcx
0x18000e8cb  jnz     loc_18000EAD5
0x18000e8d1  mov     [rdi], rdx
0x18000e8d4  mov     [rdx+8], rdi
0x18000e8d8  mov     [rcx+8], rcx
0x18000e8dc  mov     [rcx], rcx
0x18000e8df  dec     dword ptr [rbx+58h]
0x18000e8e2  test    rcx, rcx
0x18000e8e5  jnz     loc_18000EA90
0x18000e8eb  movzx   edx, bpl; NewIrql
0x18000e8ef  lea     rcx, [rbx+48h]; SpinLock
0x18000e8f3  call    cs:__imp_KeReleaseSpinLock
0x18000e8fa  nop     dword ptr [rax+rax+00h]
0x18000e8ff  mov     r15, [rbx+8]
0x18000e903  lea     rax, [rsp+0C8h+var_58]
0x18000e908  mov     rbp, [rbx+10h]
0x18000e90c  lea     rcx, [rbx+48h]; SpinLock
0x18000e910  mov     [rsp+0C8h+var_50], rax
0x18000e915  lea     rax, [rsp+0C8h+var_58]
0x18000e91a  mov     [rsp+0C8h+var_58], rax
0x18000e91f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000e926  nop     dword ptr [rax+rax+00h]
0x18000e92b  movzx   r10d, al
0x18000e92f  lea     rcx, [rbx+18h]
0x18000e933  xor     r8d, r8d
0x18000e936  mov     rdx, [rcx]
0x18000e939  cmp     rdx, rcx
0x18000e93c  jz      short loc_18000E97C
0x18000e93e  cmp     [rdx+8], rcx
0x18000e942  jnz     loc_18000EAD5
0x18000e948  mov     rax, [rdx]
0x18000e94b  cmp     [rax+8], rdx
0x18000e94f  jnz     loc_18000EAD5
0x18000e955  mov     [rcx], rax
0x18000e958  lea     r8, [rdx-0A8h]
0x18000e95f  mov     [rax+8], rcx
0x18000e963  xor     eax, eax
0x18000e965  xchg    rax, [r8+68h]
0x18000e969  test    rax, rax
0x18000e96c  jz      loc_18000EB1E
0x18000e972  lock dec dword ptr [r14+10h]
0x18000e977  test    r8, r8
0x18000e97a  jz      short loc_18000E936
0x18000e97c  test    r8, r8
0x18000e97f  jnz     loc_18000EADC
0x18000e985  movzx   edx, r10b; NewIrql
0x18000e989  lea     rcx, [rbx+48h]; SpinLock
0x18000e98d  call    cs:__imp_KeReleaseSpinLock
0x18000e994  nop     dword ptr [rax+rax+00h]
0x18000e999  lea     r14, WPP_GLOBAL_Control
0x18000e9a0  lea     rsi, WPP_RECORDER_INITIALIZED
0x18000e9a7  lea     r13, WPP_d3422704dcd235ea7c23ca0d62a7cccc_Traceguids
0x18000e9ae  mov     rax, [rsp+0C8h+var_58]
0x18000e9b3  lea     rcx, [rsp+0C8h+var_58]
0x18000e9b8  cmp     rax, rcx
0x18000e9bb  jnz     short loc_18000EA08
0x18000e9bd  mov     rcx, [rbx+98h]; P
0x18000e9c4  test    rcx, rcx
0x18000e9c7  jz      short loc_18000E9E2
0x18000e9c9  xor     edx, edx; Tag
0x18000e9cb  call    cs:__imp_ExFreePoolWithTag
0x18000e9d2  nop     dword ptr [rax+rax+00h]
0x18000e9d7  mov     qword ptr [rbx+98h], 0
0x18000e9e2  xor     edx, edx; Tag
0x18000e9e4  mov     rcx, rbx; P
0x18000e9e7  call    cs:__imp_ExFreePoolWithTag
0x18000e9ee  nop     dword ptr [rax+rax+00h]
0x18000e9f3  add     rsp, 88h
0x18000e9fa  pop     r15
0x18000e9fc  pop     r14
0x18000e9fe  pop     r13
0x18000ea00  pop     r12
0x18000ea02  pop     rdi
0x18000ea03  pop     rsi
0x18000ea04  pop     rbp
0x18000ea05  pop     rbx
0x18000ea06  retn
0x18000ea08  lea     rcx, [rsp+0C8h+var_58]
0x18000ea0d  cmp     [rax+8], rcx
0x18000ea11  jnz     loc_18000EAD5
0x18000ea17  mov     rcx, [rax]
0x18000ea1a  cmp     [rcx+8], rax
0x18000ea1e  jnz     loc_18000EAD5
0x18000ea24  mov     [rsp+0C8h+var_58], rcx
0x18000ea29  lea     rdx, [rsp+0C8h+var_58]
0x18000ea2e  lea     rdi, [rax-0A8h]
0x18000ea35  mov     [rcx+8], rdx
0x18000ea39  mov     dword ptr [rdi+30h], 0C000009Dh
0x18000ea40  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea47  cmp     rcx, r14
0x18000ea4a  jnz     loc_18000EB2A
0x18000ea50  xor     dl, dl
0x18000ea52  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18000ea59  setnz   r8b
0x18000ea5d  test    dl, dl
0x18000ea5f  jnz     loc_18000EB46
0x18000ea65  test    r8b, r8b
0x18000ea68  jnz     loc_18000EB46
0x18000ea6e  xor     edx, edx; PriorityBoost
0x18000ea70  mov     rcx, rdi; Irp
0x18000ea73  call    cs:__imp_IofCompleteRequest
0x18000ea7a  nop     dword ptr [rax+rax+00h]
0x18000ea7f  jmp     loc_18000E9AE
0x18000ea90  xor     edx, edx; Tag
0x18000ea92  call    cs:__imp_ExFreePoolWithTag
0x18000ea99  nop     dword ptr [rax+rax+00h]
0x18000ea9e  mov     rcx, [rdi]
0x18000eaa1  cmp     rcx, rdi
0x18000eaa4  jz      loc_18000E8EB
0x18000eaaa  cmp     [rcx+8], rdi
0x18000eaae  jnz     short loc_18000EAD5
0x18000eab0  mov     rax, [rcx]
0x18000eab3  cmp     [rax+8], rcx
0x18000eab7  jnz     short loc_18000EAD5
0x18000eab9  mov     [rdi], rax
0x18000eabc  mov     [rax+8], rdi
0x18000eac0  mov     [rcx+8], rcx
0x18000eac4  mov     [rcx], rcx
0x18000eac7  dec     dword ptr [rbx+58h]
0x18000eaca  test    rcx, rcx
0x18000eacd  jz      loc_18000E8EB
0x18000ead3  jmp     short loc_18000EA90
0x18000ead5  mov     ecx, 3
0x18000eada  int     29h; Win8: RtlFailFast(ecx)
0x18000eadc  mov     rcx, [rsp+0C8h+var_50]
0x18000eae1  lea     rax, [rsp+0C8h+var_58]
0x18000eae6  cmp     [rcx], rax
0x18000eae9  jnz     short loc_18000EAD5
0x18000eaeb  lea     rax, [r8+0A8h]
0x18000eaf2  mov     [rax+8], rcx
0x18000eaf6  lea     rdx, [rsp+0C8h+var_58]
0x18000eafb  mov     [rax], rdx
0x18000eafe  mov     rdx, rbx
0x18000eb01  mov     [rcx], rax
0x18000eb04  mov     rcx, r14
0x18000eb07  mov     [rsp+0C8h+var_50], rax
0x18000eb0c  call    DequeueInterruptReadIrp
0x18000eb11  mov     r8, rax
0x18000eb14  test    rax, rax
0x18000eb17  jnz     short loc_18000EADC
0x18000eb19  jmp     loc_18000E985
0x18000eb1e  mov     [rdx+8], rdx
0x18000eb22  mov     [rdx], rdx
0x18000eb25  jmp     loc_18000E933
0x18000eb2a  mov     eax, [rcx+2Ch]
0x18000eb2d  test    al, 10h
0x18000eb2f  jz      loc_18000EA50
0x18000eb35  cmp     byte ptr [rcx+29h], 4
0x18000eb39  jb      loc_18000EA50
0x18000eb3f  mov     dl, 1
0x18000eb41  jmp     loc_18000EA52
0x18000eb46  mov     rax, [rbp+30h]
0x18000eb4a  mov     r9, [rbp+40h]
0x18000eb4e  mov     rcx, [rcx+18h]
0x18000eb52  mov     [rsp+0C8h+var_68], 0C000009Dh
0x18000eb5a  mov     [rsp+0C8h+var_70], rdi
0x18000eb5f  mov     [rsp+0C8h+var_78], rax
0x18000eb64  mov     eax, [rbp+8]
0x18000eb67  mov     [rsp+0C8h+var_80], eax
0x18000eb6b  mov     rax, [r9+20h]
0x18000eb6f  mov     r9, [r15+2A0h]
0x18000eb76  mov     [rsp+0C8h+var_88], rax
0x18000eb7b  mov     [rsp+0C8h+var_90], r13
0x18000eb80  mov     [rsp+0C8h+var_98], 0Bh
0x18000eb87  mov     [rsp+0C8h+var_A0], 5
0x18000eb8f  mov     [rsp+0C8h+var_A8], 4
0x18000eb94  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x18000eb99  jmp     loc_18000EA6E
```
