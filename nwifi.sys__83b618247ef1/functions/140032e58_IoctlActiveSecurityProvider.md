# IoctlActiveSecurityProvider

- ea: `0x140032e58`
- end: `0x14003314c`
- name: `IoctlActiveSecurityProvider`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400337f4`

## callees

- `0x14000a82c`
- `0x14000d22c`
- `0x1400207e8`
- `0x14002f208`
- `0x140032e58`

## import_xrefs

- `NDIS!NdisAcquireRWLockWrite` at `0x140032f15`
- `NDIS!NdisAcquireRWLockWrite` at `0x140032f15`
- `NDIS!NdisReleaseRWLock` at `0x1400330b8`
- `NDIS!NdisReleaseRWLock` at `0x14003311d`
- `NDIS!NdisReleaseRWLock` at `0x1400330b8`
- `NDIS!NdisReleaseRWLock` at `0x14003311d`
- `NDIS!NdisAcquireRWLockRead` at `0x1400330de`
- `NDIS!NdisAcquireRWLockRead` at `0x1400330de`

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
  __int64 v24; // [rsp+28h] [rbp-30h]
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
        if ( (byte_1400AF802 & 0x40) != 0 )
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
          if ( (byte_1400AF802 & 0x40) != 0 )
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
          if ( (byte_1400AF802 & 0x40) != 0 )
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
          if ( (byte_1400AF802 & 0x40) != 0 )
          {
            LODWORD(v24) = -(*(_DWORD *)(v10 + 5896) & 1);
            McTemplateK0pjq_EtwWriteTransfer(
              v22,
              (unsigned int)IHVSerializationStatus,
              v10 + 4920,
              v10,
              v10 + 4920,
              v24);
          }
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
0x140032e58  mov     [rsp+arg_8], rbx
0x140032e5d  mov     [rsp+arg_10], rbp
0x140032e62  push    rsi
0x140032e63  push    rdi
0x140032e64  push    r12
0x140032e66  push    r14
0x140032e68  push    r15
0x140032e6a  sub     rsp, 30h
0x140032e6e  mov     rdi, [rcx+18h]
0x140032e72  xor     esi, esi
0x140032e74  xor     eax, eax
0x140032e76  mov     [rsp+58h+LockState.OldIrql], sil
0x140032e7b  mov     word ptr [rsp+58h+LockState.LockState], ax
0x140032e80  mov     r14, rdx
0x140032e83  mov     r15, r9
0x140032e86  mov     rdx, rcx
0x140032e89  test    rdi, rdi
0x140032e8c  jnz     short loc_140032E98
0x140032e8e  mov     eax, 0C0000010h
0x140032e93  jmp     loc_140033134
0x140032e98  mov     r9d, [r9]
0x140032e9b  mov     ebp, 4
0x140032ea0  mov     rdi, [rdi+10h]
0x140032ea4  mov     r12d, esi
0x140032ea7  mov     [r15], esi
0x140032eaa  cmp     r8d, ebp
0x140032ead  jnb     short loc_140032EB9
0x140032eaf  mov     ebx, 0C0000023h
0x140032eb4  jmp     loc_14003312F
0x140032eb9  mov     ecx, [r14]
0x140032ebc  mov     ebx, esi
0x140032ebe  test    ecx, ecx
0x140032ec0  jz      loc_1400330C6
0x140032ec6  cmp     ecx, 1
0x140032ec9  jz      short loc_140032ED5
0x140032ecb  mov     ebx, 0C000000Dh
0x140032ed0  jmp     loc_14003312F
0x140032ed5  cmp     [rdi+15F0h], esi
0x140032edb  jnz     short loc_140032EE7
0x140032edd  mov     ebx, 0C0000184h
0x140032ee2  jmp     loc_14003312F
0x140032ee7  lea     eax, [r8-4]
0x140032eeb  cmp     eax, ebp
0x140032eed  jb      short loc_140032ECB
0x140032eef  cmp     [rdi+16F0h], rdx
0x140032ef6  jz      short loc_140032F02
0x140032ef8  mov     ebx, 0C0000022h
0x140032efd  jmp     loc_14003312F
0x140032f02  mov     rcx, [rdi+90h]; Lock
0x140032f09  lea     rdx, [rsp+58h+LockState]; LockState
0x140032f0e  mov     r14d, [r14+4]
0x140032f12  xor     r8d, r8d; Flags
0x140032f15  call    cs:__imp_NdisAcquireRWLockWrite
0x140032f1c  nop     dword ptr [rax+rax+00h]
0x140032f21  mov     eax, r14d
0x140032f24  and     eax, 7FFFFFFFh
0x140032f29  jz      loc_140032FEA
0x140032f2f  sub     eax, 1
0x140032f32  jz      short loc_140032F9F
0x140032f34  cmp     eax, 1
0x140032f37  jz      short loc_140032F43
0x140032f39  mov     ebx, 0C000000Dh
0x140032f3e  jmp     loc_1400330AC
0x140032f43  mov     rax, [rdi+16F8h]
0x140032f4a  test    rax, rax
0x140032f4d  jz      short loc_140032F95
0x140032f4f  mov     [rdi+1700h], rax
0x140032f56  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f5d  lea     rbp, WPP_GLOBAL_Control
0x140032f64  cmp     rcx, rbp
0x140032f67  jz      short loc_140032F7E
0x140032f69  mov     rcx, [rcx+18h]
0x140032f6d  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140032f74  mov     edx, 0Eh
0x140032f79  call    WPP_SF_
0x140032f7e  test    cs:byte_1400AF802, 40h
0x140032f85  jz      loc_14003303B
0x140032f8b  mov     byte ptr [rsp+58h+var_30], 2
0x140032f90  jmp     loc_140033027
0x140032f95  mov     ebx, 0C0000034h
0x140032f9a  jmp     loc_1400330AC
0x140032f9f  mov     rax, [rdi+16F0h]
0x140032fa6  test    rax, rax
0x140032fa9  jz      short loc_140032F95
0x140032fab  mov     [rdi+1700h], rax
0x140032fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140032fb9  lea     rbp, WPP_GLOBAL_Control
0x140032fc0  cmp     rcx, rbp
0x140032fc3  jz      short loc_140032FDA
0x140032fc5  mov     rcx, [rcx+18h]
0x140032fc9  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140032fd0  mov     edx, 0Dh
0x140032fd5  call    WPP_SF_
0x140032fda  test    cs:byte_1400AF802, 40h
0x140032fe1  jz      short loc_14003303B
0x140032fe3  mov     byte ptr [rsp+58h+var_30], 1
0x140032fe8  jmp     short loc_140033027
0x140032fea  mov     [rdi+1700h], rsi
0x140032ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ff8  lea     rbp, WPP_GLOBAL_Control
0x140032fff  cmp     rcx, rbp
0x140033002  jz      short loc_140033019
0x140033004  mov     rcx, [rcx+18h]
0x140033008  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x14003300f  mov     edx, 0Ch
0x140033014  call    WPP_SF_
0x140033019  test    cs:byte_1400AF802, 40h
0x140033020  jz      short loc_14003303B
0x140033022  mov     byte ptr [rsp+58h+var_30], sil
0x140033027  lea     r8, [rdi+1338h]
0x14003302e  mov     r9, rdi
0x140033031  mov     [rsp+58h+var_38], r8
0x140033036  call    McTemplateK0pju_EtwWriteTransfer
0x14003303b  mov     eax, [rdi+1708h]
0x140033041  and     eax, 0FFFFFFFEh
0x140033044  shr     r14d, 1Fh
0x140033048  or      r14d, eax
0x14003304b  mov     [rdi+1708h], r14d
0x140033052  mov     rcx, cs:WPP_GLOBAL_Control
0x140033059  cmp     rcx, rbp
0x14003305c  jz      short loc_14003307A
0x14003305e  mov     rcx, [rcx+18h]
0x140033062  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140033069  and     r14d, 1
0x14003306d  mov     edx, 0Fh
0x140033072  mov     r9b, r14b
0x140033075  call    WPP_SF_c
0x14003307a  test    cs:byte_1400AF802, 40h
0x140033081  jz      short loc_1400330AC
0x140033083  mov     eax, [rdi+1708h]
0x140033089  lea     r8, [rdi+1338h]
0x140033090  shr     eax, 1
0x140033092  lea     rdx, IHVSerializationStatus
0x140033099  mov     r9, rdi
0x14003309c  sbb     eax, eax
0x14003309e  mov     dword ptr [rsp+58h+var_30], eax
0x1400330a2  mov     [rsp+58h+var_38], r8
0x1400330a7  call    McTemplateK0pjq_EtwWriteTransfer
0x1400330ac  mov     rcx, [rdi+90h]; Lock
0x1400330b3  lea     rdx, [rsp+58h+LockState]; LockState
0x1400330b8  call    cs:__imp_NdisReleaseRWLock
0x1400330bf  nop     dword ptr [rax+rax+00h]
0x1400330c4  jmp     short loc_14003312F
0x1400330c6  cmp     r9d, ebp
0x1400330c9  jb      loc_140032EAF
0x1400330cf  mov     rcx, [rdi+90h]; Lock
0x1400330d6  lea     rdx, [rsp+58h+LockState]; LockState
0x1400330db  xor     r8d, r8d; Flags
0x1400330de  call    cs:__imp_NdisAcquireRWLockRead
0x1400330e5  nop     dword ptr [rax+rax+00h]
0x1400330ea  mov     rax, [rdi+1700h]
0x1400330f1  test    rax, rax
0x1400330f4  jz      short loc_140033111
0x1400330f6  cmp     rax, [rdi+16F8h]
0x1400330fd  jnz     short loc_140033106
0x1400330ff  mov     esi, 2
0x140033104  jmp     short loc_140033111
0x140033106  cmp     rax, [rdi+16F0h]
0x14003310d  setz    sil
0x140033111  mov     rcx, [rdi+90h]; Lock
0x140033118  lea     rdx, [rsp+58h+LockState]; LockState
0x14003311d  call    cs:__imp_NdisReleaseRWLock
0x140033124  nop     dword ptr [rax+rax+00h]
0x140033129  mov     [r14], esi
0x14003312c  mov     r12d, ebp
0x14003312f  mov     [r15], r12d
0x140033132  mov     eax, ebx
0x140033134  mov     rbx, [rsp+58h+arg_8]
0x140033139  mov     rbp, [rsp+58h+arg_10]
0x14003313e  add     rsp, 30h
0x140033142  pop     r15
0x140033144  pop     r14
0x140033146  pop     r12
0x140033148  pop     rdi
0x140033149  pop     rsi
0x14003314a  retn
```
