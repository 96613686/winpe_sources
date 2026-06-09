# NbtDereferenceAddress

- ea: `0x140004038`
- end: `0x1400043c0`
- name: `NbtDereferenceAddress`
- size: `904`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1400021d0`
- `0x140002740`
- `0x140002cb0`
- `0x1400031bc`
- `0x140003d04`
- `0x140004cb0`
- `0x14000508c`
- `0x140010c90`
- `0x1400226d0`

## callees

- `0x140004038`
- `0x140006900`
- `0x1400079a8`
- `0x140007ed8`
- `0x140007ff8`
- `0x140008110`
- `0x1400089c8`
- `0x14000d310`
- `0x14000da94`
- `0x14001b964`
- `0x14001f6dc`
- `0x140030f80`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004074`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000408a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000431f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004074`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000408a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000431f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004100`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400041bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004248`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400042fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400040bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004100`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400041bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004248`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400042fe`

## pseudocode

```c
__int64 __fastcall NbtDereferenceAddress(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  KIRQL v5; // bp
  KIRQL v6; // al
  KIRQL v7; // r8
  __int64 v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // esi
  __int64 v14; // r9
  void *v15; // rcx
  int v16; // ecx
  __int64 DeviceFromNameAddr; // rsi
  __int64 v18; // rbx
  int v19; // r8d
  int v20; // ebx
  __int64 v21; // rsi

  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      a1,
      80,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) - 1,
      a3,
      a4);
  v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v7 = v6;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
  {
    v9 = *(_QWORD *)a1;
    if ( *(_QWORD *)(*(_QWORD *)a1 + 8LL) != a1 || (v10 = *(_QWORD **)(a1 + 8), *v10 != a1) )
      __fastfail(3u);
    *v10 = v9;
    *(_QWORD *)(v9 + 8) = v10;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v7);
    v11 = *(_QWORD *)(a1 + 40);
    if ( v11 )
    {
      *(_QWORD *)(v11 + 120) = 0;
      v12 = *(_QWORD *)(a1 + 40);
      v13 = *(_DWORD *)(v12 + 72);
      *(_DWORD *)(v12 + 72) = v13 & 0xFFFFFF0F;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 72LL) |= 0x40u;
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 96LL) |= *(_QWORD *)(*(_QWORD *)(a1 + 40) + 80LL);
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 80LL) = 0;
      NbtCheckNameAddrTimer(*(_QWORD *)(a1 + 40));
      v14 = *(_QWORD *)(a1 + 40);
      v15 = *(void **)(v14 + 112);
      if ( v15 )
      {
        *(_QWORD *)(v14 + 112) = 0;
        StopTimer(v15);
      }
      if ( (v13 & 0x41) == 0 && *(_BYTE *)(*(_QWORD *)(a1 + 40) + 164LL) != 42 )
      {
        DeviceFromNameAddr = GetAndRefNextDeviceFromNameAddr();
        if ( DeviceFromNameAddr )
        {
          v18 = *(_QWORD *)(a1 + 40);
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              v16,
              12,
              (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
              v18,
              *(_DWORD *)(v18 + 20),
              *(_DWORD *)(v18 + 20) + 1,
              126,
              (__int64)"minio\\netbt\\sys\\name.c");
          NbtReferenceName(v18, 4);
          KeReleaseSpinLock(&SpinLock, v5);
          v20 = ReleaseNameOnNet(
                  *(_QWORD *)(a1 + 40),
                  (_DWORD)Str2,
                  v19,
                  (unsigned __int16)NodeType,
                  DeviceFromNameAddr);
          v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
          NBT_DEREFERENCE_DEVICE(DeviceFromNameAddr, 9);
          if ( v20 < 0 )
            NbtDereferenceName(*(PVOID *)(a1 + 40), 4, 1, 142, (__int64)"minio\\netbt\\sys\\name.c");
        }
      }
      v21 = *(_QWORD *)(a1 + 40);
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *(_DWORD *)(v21 + 20),
          81,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          v21,
          *(_DWORD *)(v21 + 20),
          *(_DWORD *)(v21 + 20) - 1,
          146,
          (__int64)"minio\\netbt\\sys\\name.c");
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 + 20), 0xFFFFFFFF) == 1 )
      {
        NbtUnlinkNameFromHashTable((__int64 *)v21);
        NbtFreeNameAddr((PVOID)v21);
      }
      else
      {
        NbtCheckNameAddrTimer(v21);
      }
    }
    KeReleaseSpinLock(&SpinLock, v5);
    NTQueueToWorkerThread(a1 + 64, (__int64)DelayedFreeAddrObj, 0, a1, 0, 0, 0, 10);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v6);
    KeReleaseSpinLock(&SpinLock, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x140004038  mov     rax, rsp
0x14000403b  push    rbx
0x14000403c  push    rbp
0x14000403d  push    rsi
0x14000403e  push    rdi
0x14000403f  push    r13
0x140004041  push    r15
0x140004043  sub     rsp, 58h
0x140004047  mov     r10d, r8d
0x14000404a  mov     qword ptr [rax+8], 0
0x140004052  mov     rdi, rcx
0x140004055  mov     qword ptr [rax-48h], 0
0x14000405d  test    byte ptr cs:xmmword_140038420+9, 40h
0x140004064  jnz     loc_140004299
0x14000406a  lea     r15, SpinLock
0x140004071  mov     rcx, r15; SpinLock
0x140004074  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000407b  nop     dword ptr [rax+rax+00h]
0x140004080  lea     rbx, [rdi+38h]
0x140004084  mov     bpl, al
0x140004087  mov     rcx, rbx; SpinLock
0x14000408a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004091  nop     dword ptr [rax+rax+00h]
0x140004096  mov     r8b, al
0x140004099  or      edx, 0FFFFFFFFh
0x14000409c  lock xadd [rdi+14h], edx
0x1400040a1  cmp     edx, 1
0x1400040a4  jz      short loc_1400040D9
0x1400040a6  mov     dl, al; NewIrql
0x1400040a8  mov     rcx, rbx; SpinLock
0x1400040ab  call    cs:__imp_KeReleaseSpinLock
0x1400040b2  nop     dword ptr [rax+rax+00h]
0x1400040b7  mov     dl, bpl; NewIrql
0x1400040ba  mov     rcx, r15; SpinLock
0x1400040bd  call    cs:__imp_KeReleaseSpinLock
0x1400040c4  nop     dword ptr [rax+rax+00h]
0x1400040c9  xor     eax, eax
0x1400040cb  add     rsp, 58h
0x1400040cf  pop     r15
0x1400040d1  pop     r13
0x1400040d3  pop     rdi
0x1400040d4  pop     rsi
0x1400040d5  pop     rbp
0x1400040d6  pop     rbx
0x1400040d7  retn
0x1400040d9  mov     rax, [rdi]
0x1400040dc  cmp     [rax+8], rdi
0x1400040e0  jnz     loc_140004292
0x1400040e6  mov     rcx, [rdi+8]
0x1400040ea  cmp     [rcx], rdi
0x1400040ed  jnz     loc_140004292
0x1400040f3  mov     [rcx], rax
0x1400040f6  mov     dl, r8b; NewIrql
0x1400040f9  mov     [rax+8], rcx
0x1400040fd  mov     rcx, rbx; SpinLock
0x140004100  call    cs:__imp_KeReleaseSpinLock
0x140004107  nop     dword ptr [rax+rax+00h]
0x14000410c  mov     rax, [rdi+28h]
0x140004110  test    rax, rax
0x140004113  jz      loc_140004242
0x140004119  mov     qword ptr [rax+78h], 0
0x140004121  mov     rcx, [rdi+28h]
0x140004125  mov     esi, [rcx+48h]
0x140004128  mov     eax, esi
0x14000412a  and     eax, 0FFFFFF0Fh
0x14000412f  mov     [rcx+48h], eax
0x140004132  mov     rax, [rdi+28h]
0x140004136  or      dword ptr [rax+48h], 40h
0x14000413a  mov     rcx, [rdi+28h]
0x14000413e  mov     rax, [rcx+50h]
0x140004142  or      [rcx+60h], rax
0x140004146  mov     rax, [rdi+28h]
0x14000414a  mov     qword ptr [rax+50h], 0
0x140004152  mov     rcx, [rdi+28h]
0x140004156  call    NbtCheckNameAddrTimer
0x14000415b  mov     r9, [rdi+28h]
0x14000415f  mov     rcx, [r9+70h]; Entry
0x140004163  test    rcx, rcx
0x140004166  jnz     loc_1400042CD
0x14000416c  lea     r13, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140004173  test    sil, 41h
0x140004177  jnz     loc_140004214
0x14000417d  mov     rcx, [rdi+28h]
0x140004181  cmp     byte ptr [rcx+0A4h], 2Ah ; '*'
0x140004188  jz      loc_140004214
0x14000418e  call    GetAndRefNextDeviceFromNameAddr
0x140004193  mov     rsi, rax
0x140004196  test    rax, rax
0x140004199  jz      short loc_140004214
0x14000419b  mov     rbx, [rdi+28h]
0x14000419f  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400041a6  jnz     loc_140004333
0x1400041ac  mov     edx, 4
0x1400041b1  mov     rcx, rbx
0x1400041b4  call    NbtReferenceName
0x1400041b9  mov     dl, bpl; NewIrql
0x1400041bc  mov     rcx, r15; SpinLock
0x1400041bf  call    cs:__imp_KeReleaseSpinLock
0x1400041c6  nop     dword ptr [rax+rax+00h]
0x1400041cb  movzx   r9d, cs:NodeType
0x1400041d3  mov     rdx, cs:Str2
0x1400041da  mov     rcx, [rdi+28h]
0x1400041de  mov     [rsp+88h+var_68], rsi
0x1400041e3  call    ReleaseNameOnNet
0x1400041e8  mov     rcx, r15; SpinLock
0x1400041eb  mov     ebx, eax
0x1400041ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400041f4  nop     dword ptr [rax+rax+00h]
0x1400041f9  mov     r8b, 1
0x1400041fc  mov     edx, 9
0x140004201  mov     rcx, rsi
0x140004204  mov     bpl, al
0x140004207  call    NBT_DEREFERENCE_DEVICE
0x14000420c  test    ebx, ebx
0x14000420e  js      loc_14000436B
0x140004214  mov     rsi, [rdi+28h]
0x140004218  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000421f  jnz     loc_14000438C
0x140004225  or      eax, 0FFFFFFFFh
0x140004228  lock xadd [rsi+14h], eax
0x14000422d  mov     rcx, rsi
0x140004230  cmp     eax, 1
0x140004233  jnz     short loc_14000428B
0x140004235  call    NbtUnlinkNameFromHashTable
0x14000423a  mov     rcx, rsi; P
0x14000423d  call    NbtFreeNameAddr
0x140004242  mov     dl, bpl; NewIrql
0x140004245  mov     rcx, r15; SpinLock
0x140004248  call    cs:__imp_KeReleaseSpinLock
0x14000424f  nop     dword ptr [rax+rax+00h]
0x140004254  mov     byte ptr [rsp+88h+var_50], 0Ah
0x140004259  lea     rcx, [rdi+40h]
0x14000425d  mov     byte ptr [rsp+88h+var_58], 0
0x140004262  lea     rdx, DelayedFreeAddrObj
0x140004269  mov     [rsp+88h+var_60], 0
0x140004272  mov     r9, rdi
0x140004275  xor     r8d, r8d
0x140004278  mov     [rsp+88h+var_68], 0
0x140004281  call    NTQueueToWorkerThread
0x140004286  jmp     loc_1400040C9
0x14000428b  call    NbtCheckNameAddrTimer
0x140004290  jmp     short loc_140004242
0x140004292  mov     ecx, 3
0x140004297  int     29h; Win8: RtlFailFast(ecx)
0x140004299  mov     r8d, [rcx+14h]
0x14000429d  mov     edx, 50h ; 'P'
0x1400042a2  mov     [rsp+88h+var_50], r9
0x1400042a7  mov     r9, rdi
0x1400042aa  mov     [rsp+88h+var_58], r10d
0x1400042af  lea     eax, [r8-1]
0x1400042b3  mov     dword ptr [rsp+88h+var_60], eax
0x1400042b7  mov     dword ptr [rsp+88h+var_68], r8d
0x1400042bc  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x1400042c3  call    WPP_SF_qddds
0x1400042c8  jmp     loc_14000406A
0x1400042cd  lea     r8, [rsp+88h+var_48]
0x1400042d2  mov     qword ptr [r9+70h], 0
0x1400042da  lea     rdx, [rsp+88h+arg_0]
0x1400042e2  call    StopTimer
0x1400042e7  mov     rbx, [rsp+88h+arg_0]
0x1400042ef  test    rbx, rbx
0x1400042f2  jz      loc_14000416C
0x1400042f8  mov     dl, bpl; NewIrql
0x1400042fb  mov     rcx, r15; SpinLock
0x1400042fe  call    cs:__imp_KeReleaseSpinLock
0x140004305  nop     dword ptr [rax+rax+00h]
0x14000430a  mov     rcx, [rsp+88h+var_48]
0x14000430f  mov     edx, 102h
0x140004314  mov     rax, rbx
0x140004317  call    _guard_dispatch_icall
0x14000431c  mov     rcx, r15; SpinLock
0x14000431f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004326  nop     dword ptr [rax+rax+00h]
0x14000432b  mov     bpl, al
0x14000432e  jmp     loc_14000416C
0x140004333  mov     r9d, [rbx+14h]
0x140004337  mov     edx, 0Ch
0x14000433c  mov     [rsp+88h+var_50], r13
0x140004341  mov     [rsp+88h+var_58], 2E7Eh
0x140004349  lea     r8d, [r9+1]
0x14000434d  mov     dword ptr [rsp+88h+var_60], r8d
0x140004352  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x140004359  mov     dword ptr [rsp+88h+var_68], r9d
0x14000435e  mov     r9, rbx
0x140004361  call    WPP_SF_qddds
0x140004366  jmp     loc_1400041AC
0x14000436b  mov     rcx, [rdi+28h]; P
0x14000436f  mov     r9d, 2E8Eh
0x140004375  mov     r8b, 1
0x140004378  mov     [rsp+88h+var_68], r13; __int64
0x14000437d  mov     edx, 4
0x140004382  call    NbtDereferenceName
0x140004387  jmp     loc_140004214
0x14000438c  mov     ecx, [rsi+14h]
0x14000438f  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140004396  mov     [rsp+88h+var_50], r13
0x14000439b  mov     edx, 51h ; 'Q'
0x1400043a0  mov     [rsp+88h+var_58], 2E92h
0x1400043a8  mov     r9, rsi
0x1400043ab  lea     eax, [rcx-1]
0x1400043ae  mov     dword ptr [rsp+88h+var_60], eax
0x1400043b2  mov     dword ptr [rsp+88h+var_68], ecx
0x1400043b6  call    WPP_SF_qddds
0x1400043bb  jmp     loc_140004225
```
