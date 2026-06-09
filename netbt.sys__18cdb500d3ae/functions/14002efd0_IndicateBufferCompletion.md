# IndicateBufferCompletion

- ea: `0x14002efd0`
- end: `0x14002f16d`
- name: `IndicateBufferCompletion`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140006878`
- `0x140013184`
- `0x140021c1c`
- `0x140027e60`
- `0x14002efd0`
- `0x14002f880`
- `0x140043574`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f00e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002f00e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f11b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002f11b`

## pseudocode

```c
__int64 __fastcall IndicateBufferCompletion(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r12
  int v4; // r15d
  __int64 v5; // r14
  bool v8; // bp
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int *v11; // rsi
  unsigned int v12; // eax
  int v13; // edx
  int v14; // r8d
  _QWORD v16[11]; // [rsp+50h] [rbp-58h] BYREF
  KIRQL NewIrql; // [rsp+B8h] [rbp+10h]
  int v19; // [rsp+C0h] [rbp+18h] BYREF
  int v20; // [rsp+C8h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(a3 + 24);
  v4 = *(_DWORD *)(a2 + 48);
  v5 = *(unsigned int *)(a2 + 56);
  v16[0] = 0;
  v20 = 0;
  v8 = 1;
  v19 = 0;
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 104));
  v11 = (unsigned int *)(a3 + 280);
  if ( (BYTE3(xmmword_140038420) & 8) != 0 )
    WPP_SF_qqqddd(*v11, 23, v10, a3, v3, a2, v4, v5, *v11);
  v12 = *(_DWORD *)(a3 + 284);
  *(_QWORD *)(a3 + 264) += v5;
  *(_QWORD *)(a3 + 216) = 0;
  *(_DWORD *)(a3 + 284) = (unsigned int)v5 < v12 ? v12 - v5 : 0;
  if ( v3 && *(_DWORD *)(a3 + 88) == 7 )
  {
    if ( v4 )
    {
      LOBYTE(v9) = 8;
      OutOfRsrcKillUnderLock(a3, v9);
    }
    else
    {
      *v11 += v5;
      if ( (unsigned int)NbtProcessNewMessageInIndicateBuffer(
                           a1,
                           a3,
                           32,
                           (unsigned int)&v20,
                           *(_QWORD *)(a3 + 232),
                           (__int64)v16,
                           (__int64)&v19) == -1073741802 )
        v8 = (unsigned __int8)NbtQueueDeferredPostIrp((PVOID)a3) == 0;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 104), NewIrql);
  if ( v8 )
    NbtDereferenceLowerConnection(a3, v13, v14, 1106, (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
  *(_QWORD *)(a2 + 8) = 0;
  NbtFreeIrp((PIRP)a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14002efd0  mov     r11, rsp
0x14002efd3  mov     [r11+8], rcx
0x14002efd7  push    rbx
0x14002efd8  push    rbp
0x14002efd9  push    rsi
0x14002efda  push    rdi
0x14002efdb  push    r12
0x14002efdd  push    r13
0x14002efdf  push    r14
0x14002efe1  push    r15
0x14002efe3  sub     rsp, 68h
0x14002efe7  mov     r12, [r8+18h]
0x14002efeb  lea     rcx, [r8+68h]; SpinLock
0x14002efef  mov     r15d, [rdx+30h]
0x14002eff3  xor     eax, eax
0x14002eff5  mov     r14d, [rdx+38h]
0x14002eff9  mov     rbx, r8
0x14002effc  mov     [r11-58h], rax
0x14002f000  mov     rdi, rdx
0x14002f003  mov     [r11+20h], eax
0x14002f007  mov     bpl, 1
0x14002f00a  mov     [r11+18h], eax
0x14002f00e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002f015  nop     dword ptr [rax+rax+00h]
0x14002f01a  mov     [rsp+0A8h+NewIrql], al
0x14002f021  test    byte ptr cs:xmmword_140038420+3, 8
0x14002f028  lea     rsi, [rbx+118h]
0x14002f02f  jz      short loc_14002F058
0x14002f031  mov     ecx, [rsi]
0x14002f033  mov     edx, 17h
0x14002f038  mov     [rsp+0A8h+var_68], ecx
0x14002f03c  mov     r9, rbx
0x14002f03f  mov     [rsp+0A8h+var_70], r14d
0x14002f044  mov     dword ptr [rsp+0A8h+var_78], r15d
0x14002f049  mov     [rsp+0A8h+var_80], rdi
0x14002f04e  mov     [rsp+0A8h+var_88], r12
0x14002f053  call    WPP_SF_qqqddd
0x14002f058  mov     eax, [rbx+11Ch]
0x14002f05e  mov     ecx, eax
0x14002f060  add     [rbx+108h], r14
0x14002f067  sub     ecx, r14d
0x14002f06a  cmp     r14d, eax
0x14002f06d  mov     qword ptr [rbx+0D8h], 0
0x14002f078  sbb     eax, eax
0x14002f07a  and     eax, ecx
0x14002f07c  mov     [rbx+11Ch], eax
0x14002f082  test    r12, r12
0x14002f085  jz      loc_14002F110
0x14002f08b  cmp     dword ptr [rbx+58h], 7
0x14002f08f  jnz     short loc_14002F110
0x14002f091  test    r15d, r15d
0x14002f094  jz      short loc_14002F0A2
0x14002f096  mov     dl, 8
0x14002f098  mov     rcx, rbx
0x14002f09b  call    OutOfRsrcKillUnderLock
0x14002f0a0  jmp     short loc_14002F110
0x14002f0a2  mov     rcx, [rsp+0A8h+arg_0]
0x14002f0aa  lea     rax, [rsp+0A8h+arg_10]
0x14002f0b2  add     [rsi], r14d
0x14002f0b5  lea     r9, [rsp+0A8h+arg_18]
0x14002f0bd  mov     [rsp+0A8h+var_78], rax
0x14002f0c2  mov     r8d, 20h ; ' '
0x14002f0c8  lea     rax, [rsp+0A8h+var_58]
0x14002f0cd  mov     rdx, rbx
0x14002f0d0  mov     [rsp+0A8h+var_80], rax
0x14002f0d5  mov     rax, [rbx+0E8h]
0x14002f0dc  mov     [rsp+0A8h+var_88], rax
0x14002f0e1  call    NbtProcessNewMessageInIndicateBuffer
0x14002f0e6  cmp     eax, 0C0000016h
0x14002f0eb  jnz     short loc_14002F110
0x14002f0ed  mov     r9d, [rsp+0A8h+arg_10]
0x14002f0f5  mov     rdx, r12
0x14002f0f8  mov     r8, [rsp+0A8h+var_58]
0x14002f0fd  mov     rcx, rbx; Context
0x14002f100  call    NbtQueueDeferredPostIrp
0x14002f105  xor     edx, edx
0x14002f107  movzx   ebp, bpl
0x14002f10b  test    al, al
0x14002f10d  cmovnz  ebp, edx
0x14002f110  mov     dl, [rsp+0A8h+NewIrql]; NewIrql
0x14002f117  lea     rcx, [rbx+68h]; SpinLock
0x14002f11b  call    cs:__imp_KeReleaseSpinLock
0x14002f122  nop     dword ptr [rax+rax+00h]
0x14002f127  test    bpl, bpl
0x14002f12a  jz      short loc_14002F146
0x14002f12c  lea     rcx, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x14002f133  mov     r9d, 452h
0x14002f139  mov     [rsp+0A8h+var_88], rcx
0x14002f13e  mov     rcx, rbx
0x14002f141  call    NbtDereferenceLowerConnection
0x14002f146  mov     rcx, rdi; Irp
0x14002f149  mov     qword ptr [rdi+8], 0
0x14002f151  call    NbtFreeIrp
0x14002f156  mov     eax, 0C0000016h
0x14002f15b  add     rsp, 68h
0x14002f15f  pop     r15
0x14002f161  pop     r14
0x14002f163  pop     r13
0x14002f165  pop     r12
0x14002f167  pop     rdi
0x14002f168  pop     rsi
0x14002f169  pop     rbp
0x14002f16a  pop     rbx
0x14002f16b  retn
```
