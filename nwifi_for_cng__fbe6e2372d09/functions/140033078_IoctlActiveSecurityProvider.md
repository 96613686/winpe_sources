# IoctlActiveSecurityProvider

- ea: `0x140033078`
- end: `0x14003336c`
- name: `IoctlActiveSecurityProvider`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140033a14`

## callees

- `0x14000a81c`
- `0x14000d21c`
- `0x1400207e8`
- `0x14002f498`
- `0x140033078`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x140033135`
- `NDIS!NdisAcquireRWLockWrite` at `0x140033135`
- `NDIS!NdisReleaseRWLock` at `0x1400332d8`
- `NDIS!NdisReleaseRWLock` at `0x14003333d`
- `NDIS!NdisReleaseRWLock` at `0x1400332d8`
- `NDIS!NdisReleaseRWLock` at `0x14003333d`
- `NDIS!NdisAcquireRWLockRead` at `0x1400332fe`
- `NDIS!NdisAcquireRWLockRead` at `0x1400332fe`

## pseudocode

```c
__int64 __fastcall IoctlActiveSecurityProvider(__int64 a1, int *a2, unsigned int a3, int *a4)
{
  __int64 v4; // rdi
  int v5; // esi
  unsigned int v9; // r9d
  __int64 v10; // rdi
  int v11; // r12d
  unsigned int v12; // ebx
  unsigned int v13; // r14d
  int v14; // edx
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // ecx
  int v20; // ecx
  unsigned int v21; // r14d
  int v22; // ecx
  __int64 v23; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 24);
  v5 = 0;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( !v4 )
    return 3221225488LL;
  v9 = *a4;
  v10 = *(_QWORD *)(v4 + 16);
  v11 = 0;
  *a4 = 0;
  if ( a3 >= 4 )
  {
    v12 = 0;
    if ( !*a2 )
    {
      if ( v9 >= 4 )
      {
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v10 + 144), &LockState, 0);
        v23 = *(_QWORD *)(v10 + 5888);
        if ( v23 )
        {
          if ( v23 == *(_QWORD *)(v10 + 5880) )
            v5 = 2;
          else
            LOBYTE(v5) = v23 == *(_QWORD *)(v10 + 5872);
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 144), &LockState);
        *a2 = v5;
        v11 = 4;
        goto LABEL_43;
      }
      goto LABEL_4;
    }
    if ( *a2 != 1 )
      goto LABEL_7;
    if ( !*(_DWORD *)(v10 + 5616) )
    {
      v12 = -1073741436;
      goto LABEL_43;
    }
    if ( a3 - 4 < 4 )
    {
LABEL_7:
      v12 = -1073741811;
      goto LABEL_43;
    }
    if ( *(_QWORD *)(v10 + 5872) != a1 )
    {
      v12 = -1073741790;
      goto LABEL_43;
    }
    v13 = a2[1];
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v10 + 144), &LockState, 0);
    switch ( v13 & 0x7FFFFFFF )
    {
      case 0u:
        *(_QWORD *)(v10 + 5888) = 0;
        v20 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids);
        if ( (byte_1400B2802 & 0x40) != 0 )
          McTemplateK0pju_EtwWriteTransfer(v20, v14, v10 + 4920, v10, v10 + 4920, 0);
        goto LABEL_32;
      case 1u:
        v18 = *(_QWORD *)(v10 + 5872);
        if ( v18 )
        {
          *(_QWORD *)(v10 + 5888) = v18;
          v19 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids);
          if ( (byte_1400B2802 & 0x40) != 0 )
            McTemplateK0pju_EtwWriteTransfer(v19, v14, v10 + 4920, v10, v10 + 4920, 1);
          goto LABEL_32;
        }
        break;
      case 2u:
        v16 = *(_QWORD *)(v10 + 5880);
        if ( v16 )
        {
          *(_QWORD *)(v10 + 5888) = v16;
          v17 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids);
          if ( (byte_1400B2802 & 0x40) != 0 )
            McTemplateK0pju_EtwWriteTransfer(v17, v14, v10 + 4920, v10, v10 + 4920, 2);
LABEL_32:
          v21 = *(_DWORD *)(v10 + 5896) & 0xFFFFFFFE | (v13 >> 31);
          *(_DWORD *)(v10 + 5896) = v21;
          v22 = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            LOBYTE(v15) = v21 & 1;
            WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids, v15);
          }
          if ( (byte_1400B2802 & 0x40) != 0 )
            McTemplateK0pjq_EtwWriteTransfer(
              v22,
              (unsigned int)IHVSerializationStatus,
              v10 + 4920,
              v10,
              v10 + 4920,
              -(*(_BYTE *)(v10 + 5896) & 1));
          goto LABEL_36;
        }
        break;
      default:
        v12 = -1073741811;
LABEL_36:
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + 144), &LockState);
        goto LABEL_43;
    }
    v12 = -1073741772;
    goto LABEL_36;
  }
LABEL_4:
  v12 = -1073741789;
LABEL_43:
  *a4 = v11;
  return v12;
}

```

## disassembly

```asm
0x140033078  mov     [rsp+arg_8], rbx
0x14003307d  mov     [rsp+arg_10], rbp
0x140033082  push    rsi
0x140033083  push    rdi
0x140033084  push    r12
0x140033086  push    r14
0x140033088  push    r15
0x14003308a  sub     rsp, 30h
0x14003308e  mov     rdi, [rcx+18h]
0x140033092  xor     esi, esi
0x140033094  xor     eax, eax
0x140033096  mov     [rsp+58h+LockState.OldIrql], sil
0x14003309b  mov     word ptr [rsp+58h+LockState.LockState], ax
0x1400330a0  mov     r14, rdx
0x1400330a3  mov     r15, r9
0x1400330a6  mov     rdx, rcx
0x1400330a9  test    rdi, rdi
0x1400330ac  jnz     short loc_1400330B8
0x1400330ae  mov     eax, 0C0000010h
0x1400330b3  jmp     loc_140033354
0x1400330b8  mov     r9d, [r9]
0x1400330bb  mov     ebp, 4
0x1400330c0  mov     rdi, [rdi+10h]
0x1400330c4  mov     r12d, esi
0x1400330c7  mov     [r15], esi
0x1400330ca  cmp     r8d, ebp
0x1400330cd  jnb     short loc_1400330D9
0x1400330cf  mov     ebx, 0C0000023h
0x1400330d4  jmp     loc_14003334F
0x1400330d9  mov     ecx, [r14]
0x1400330dc  mov     ebx, esi
0x1400330de  test    ecx, ecx
0x1400330e0  jz      loc_1400332E6
0x1400330e6  cmp     ecx, 1
0x1400330e9  jz      short loc_1400330F5
0x1400330eb  mov     ebx, 0C000000Dh
0x1400330f0  jmp     loc_14003334F
0x1400330f5  cmp     [rdi+15F0h], esi
0x1400330fb  jnz     short loc_140033107
0x1400330fd  mov     ebx, 0C0000184h
0x140033102  jmp     loc_14003334F
0x140033107  lea     eax, [r8-4]
0x14003310b  cmp     eax, ebp
0x14003310d  jb      short loc_1400330EB
0x14003310f  cmp     [rdi+16F0h], rdx
0x140033116  jz      short loc_140033122
0x140033118  mov     ebx, 0C0000022h
0x14003311d  jmp     loc_14003334F
0x140033122  mov     rcx, [rdi+90h]; Lock
0x140033129  lea     rdx, [rsp+58h+LockState]; LockState
0x14003312e  mov     r14d, [r14+4]
0x140033132  xor     r8d, r8d; Flags
0x140033135  call    cs:__imp_NdisAcquireRWLockWrite
0x14003313c  nop     dword ptr [rax+rax+00h]
0x140033141  mov     eax, r14d
0x140033144  and     eax, 7FFFFFFFh
0x140033149  jz      loc_14003320A
0x14003314f  sub     eax, 1
0x140033152  jz      short loc_1400331BF
0x140033154  cmp     eax, 1
0x140033157  jz      short loc_140033163
0x140033159  mov     ebx, 0C000000Dh
0x14003315e  jmp     loc_1400332CC
0x140033163  mov     rax, [rdi+16F8h]
0x14003316a  test    rax, rax
0x14003316d  jz      short loc_1400331B5
0x14003316f  mov     [rdi+1700h], rax
0x140033176  mov     rcx, cs:WPP_GLOBAL_Control
0x14003317d  lea     rbp, WPP_GLOBAL_Control
0x140033184  cmp     rcx, rbp
0x140033187  jz      short loc_14003319E
0x140033189  mov     rcx, [rcx+18h]
0x14003318d  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140033194  mov     edx, 0Eh
0x140033199  call    WPP_SF_
0x14003319e  test    cs:byte_1400B2802, 40h
0x1400331a5  jz      loc_14003325B
0x1400331ab  mov     byte ptr [rsp+58h+var_30], 2
0x1400331b0  jmp     loc_140033247
0x1400331b5  mov     ebx, 0C0000034h
0x1400331ba  jmp     loc_1400332CC
0x1400331bf  mov     rax, [rdi+16F0h]
0x1400331c6  test    rax, rax
0x1400331c9  jz      short loc_1400331B5
0x1400331cb  mov     [rdi+1700h], rax
0x1400331d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331d9  lea     rbp, WPP_GLOBAL_Control
0x1400331e0  cmp     rcx, rbp
0x1400331e3  jz      short loc_1400331FA
0x1400331e5  mov     rcx, [rcx+18h]
0x1400331e9  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x1400331f0  mov     edx, 0Dh
0x1400331f5  call    WPP_SF_
0x1400331fa  test    cs:byte_1400B2802, 40h
0x140033201  jz      short loc_14003325B
0x140033203  mov     byte ptr [rsp+58h+var_30], 1
0x140033208  jmp     short loc_140033247
0x14003320a  mov     [rdi+1700h], rsi
0x140033211  mov     rcx, cs:WPP_GLOBAL_Control
0x140033218  lea     rbp, WPP_GLOBAL_Control
0x14003321f  cmp     rcx, rbp
0x140033222  jz      short loc_140033239
0x140033224  mov     rcx, [rcx+18h]
0x140033228  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x14003322f  mov     edx, 0Ch
0x140033234  call    WPP_SF_
0x140033239  test    cs:byte_1400B2802, 40h
0x140033240  jz      short loc_14003325B
0x140033242  mov     byte ptr [rsp+58h+var_30], sil
0x140033247  lea     r8, [rdi+1338h]
0x14003324e  mov     r9, rdi
0x140033251  mov     [rsp+58h+var_38], r8
0x140033256  call    McTemplateK0pju_EtwWriteTransfer
0x14003325b  mov     eax, [rdi+1708h]
0x140033261  and     eax, 0FFFFFFFEh
0x140033264  shr     r14d, 1Fh
0x140033268  or      r14d, eax
0x14003326b  mov     [rdi+1708h], r14d
0x140033272  mov     rcx, cs:WPP_GLOBAL_Control
0x140033279  cmp     rcx, rbp
0x14003327c  jz      short loc_14003329A
0x14003327e  mov     rcx, [rcx+18h]
0x140033282  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140033289  and     r14d, 1
0x14003328d  mov     edx, 0Fh
0x140033292  mov     r9b, r14b
0x140033295  call    WPP_SF_c
0x14003329a  test    cs:byte_1400B2802, 40h
0x1400332a1  jz      short loc_1400332CC
0x1400332a3  mov     eax, [rdi+1708h]
0x1400332a9  lea     r8, [rdi+1338h]
0x1400332b0  shr     eax, 1
0x1400332b2  lea     rdx, IHVSerializationStatus
0x1400332b9  mov     r9, rdi
0x1400332bc  sbb     eax, eax
0x1400332be  mov     [rsp+58h+var_30], eax
0x1400332c2  mov     [rsp+58h+var_38], r8
0x1400332c7  call    McTemplateK0pjq_EtwWriteTransfer
0x1400332cc  mov     rcx, [rdi+90h]; Lock
0x1400332d3  lea     rdx, [rsp+58h+LockState]; LockState
0x1400332d8  call    cs:__imp_NdisReleaseRWLock
0x1400332df  nop     dword ptr [rax+rax+00h]
0x1400332e4  jmp     short loc_14003334F
0x1400332e6  cmp     r9d, ebp
0x1400332e9  jb      loc_1400330CF
0x1400332ef  mov     rcx, [rdi+90h]; Lock
0x1400332f6  lea     rdx, [rsp+58h+LockState]; LockState
0x1400332fb  xor     r8d, r8d; Flags
0x1400332fe  call    cs:__imp_NdisAcquireRWLockRead
0x140033305  nop     dword ptr [rax+rax+00h]
0x14003330a  mov     rax, [rdi+1700h]
0x140033311  test    rax, rax
0x140033314  jz      short loc_140033331
0x140033316  cmp     rax, [rdi+16F8h]
0x14003331d  jnz     short loc_140033326
0x14003331f  mov     esi, 2
0x140033324  jmp     short loc_140033331
0x140033326  cmp     rax, [rdi+16F0h]
0x14003332d  setz    sil
0x140033331  mov     rcx, [rdi+90h]; Lock
0x140033338  lea     rdx, [rsp+58h+LockState]; LockState
0x14003333d  call    cs:__imp_NdisReleaseRWLock
0x140033344  nop     dword ptr [rax+rax+00h]
0x140033349  mov     [r14], esi
0x14003334c  mov     r12d, ebp
0x14003334f  mov     [r15], r12d
0x140033352  mov     eax, ebx
0x140033354  mov     rbx, [rsp+58h+arg_8]
0x140033359  mov     rbp, [rsp+58h+arg_10]
0x14003335e  add     rsp, 30h
0x140033362  pop     r15
0x140033364  pop     r14
0x140033366  pop     r12
0x140033368  pop     rdi
0x140033369  pop     rsi
0x14003336a  retn
```
