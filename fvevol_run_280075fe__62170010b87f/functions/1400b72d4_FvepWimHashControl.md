# FvepWimHashControl

- ea: `0x1400b72d4`
- end: `0x1400b7739`
- name: `FvepWimHashControl`
- size: `1125`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400644a0`
- `0x1400b71f8`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000a150`
- `0x14000dd8c`
- `0x140022220`
- `0x140095190`
- `0x1400b72d4`
- `0x1400def70`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b747e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b75b8`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b7696`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b747e`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b75b8`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1400b7696`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7435`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7550`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7652`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7435`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7550`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b7652`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b7362`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b74fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b7633`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b7362`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b74fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b7633`

## pseudocode

```c
__int64 __fastcall FvepWimHashControl(_QWORD *a1, const void *a2, int a3)
{
  char v6; // si
  __int64 v7; // rbx
  KIRQL v8; // r14
  __int64 v9; // rdx
  __int64 *v10; // rax
  int updated; // eax
  KIRQL v12; // r14
  int v13; // eax
  KIRQL v14; // al
  __int64 result; // rax
  __int64 v16; // r9
  unsigned __int64 v17; // [rsp+20h] [rbp-40h]
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  int v20; // [rsp+B0h] [rbp+50h] BYREF
  int v21; // [rsp+B8h] [rbp+58h] BYREF

  v20 = a3;
  v21 = 0;
  v19 = 0;
  v6 = 0;
  v18 = 0;
  if ( !memcmp(a2, &WNF_FVE_WIM_HASH_GENERATION_TRIGGER, 8u) )
  {
    v7 = MEMORY[0xFFFFF78000000008];
    if ( v20 == 1 )
    {
      v21 = 0;
      updated = ZwUpdateWnfStateData(&WNF_FVE_WIM_HASH_DELETION_TRIGGER, &v21, 4, 0, 0, 0, 0);
      if ( updated >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          98,
          WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
          (unsigned int)updated);
      }
      v12 = KeAcquireSpinLockRaiseToDpc(a1 + 557);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v7);
      }
      a1[553] = v7;
      KeReleaseSpinLock(a1 + 557, v12);
      v9 = 30;
      v10 = FVE_WIM_HASHING_RESUMED;
    }
    else
    {
      if ( v20 != 2 )
        goto LABEL_40;
      v8 = KeAcquireSpinLockRaiseToDpc(a1 + 557);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v7);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v17 = (v7 - a1[553] + a1[552]) / 0x989680uLL;
          WPP_SF_II(WPP_GLOBAL_Control->AttachedDevice, 102, v17, (v7 - a1[553]) / 0x989680uLL, v17);
        }
      }
      a1[552] += v7 - a1[553];
      a1[553] = 0;
      KeReleaseSpinLock(a1 + 557, v8);
      v9 = 31;
      v10 = FVE_WIM_HASHING_PAUSED;
    }
    goto LABEL_39;
  }
  if ( !memcmp(a2, &WNF_FVE_WIM_HASH_DELETION_TRIGGER, 8u) && a3 == 3 )
  {
    v21 = 2;
    v13 = ZwUpdateWnfStateData(&WNF_FVE_WIM_HASH_GENERATION_TRIGGER, &v21, 4, 0, 0, 0, 0);
    if ( v13 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
        (unsigned int)v13);
    }
    v14 = KeAcquireSpinLockRaiseToDpc(a1 + 557);
    a1[552] = 0;
    a1[553] = 0;
    KeReleaseSpinLock(a1 + 557, v14);
    v9 = 33;
    v10 = FVE_WIM_HASHES_DELETE;
LABEL_39:
    *(_QWORD *)&v18 = v10;
    v6 = 1;
    FveRaiseStatusChangedEvent(a1, v9);
  }
LABEL_40:
  result = ZwUpdateWnfStateData(a2, &v20, 4, 0, 0, 0, 0);
  if ( (int)result >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    if ( v6 )
    {
      LOBYTE(v16) = 1;
      return FveLogEventEx(*a1, &v18, 0, v16);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    return WPP_SF_d(
             WPP_GLOBAL_Control->AttachedDevice,
             105,
             WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
             (unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x1400b72d4  mov     [rsp-38h+arg_0], rbx
0x1400b72d9  mov     [rsp-38h+arg_10], r8d
0x1400b72de  push    rbp
0x1400b72df  push    rsi
0x1400b72e0  push    rdi
0x1400b72e1  push    r12
0x1400b72e3  push    r13
0x1400b72e5  push    r14
0x1400b72e7  push    r15
0x1400b72e9  mov     rbp, rsp
0x1400b72ec  sub     rsp, 60h
0x1400b72f0  xor     r12d, r12d
0x1400b72f3  mov     r15, rdx
0x1400b72f6  mov     ebx, r8d
0x1400b72f9  mov     [rbp+arg_18], r12d
0x1400b72fd  mov     rdi, rcx
0x1400b7300  lea     rdx, WNF_FVE_WIM_HASH_GENERATION_TRIGGER; Buf2
0x1400b7307  xorps   xmm0, xmm0
0x1400b730a  xor     eax, eax
0x1400b730c  lea     r13d, [r12+8]
0x1400b7311  mov     [rbp+var_10], rax
0x1400b7315  mov     r8d, r13d; Size
0x1400b7318  mov     rcx, r15; Buf1
0x1400b731b  mov     sil, r12b
0x1400b731e  movups  [rbp+var_20], xmm0
0x1400b7322  call    memcmp
0x1400b7327  lea     r14, WPP_GLOBAL_Control
0x1400b732e  test    eax, eax
0x1400b7330  jnz     loc_1400B756D
0x1400b7336  mov     rbx, 0FFFFF78000000008h
0x1400b7340  mov     rbx, [rbx]
0x1400b7343  mov     eax, [rbp+arg_10]
0x1400b7346  sub     eax, 1
0x1400b7349  jz      loc_1400B7459
0x1400b734f  cmp     eax, 1
0x1400b7352  jnz     loc_1400B7679
0x1400b7358  lea     rsi, [rdi+1168h]
0x1400b735f  mov     rcx, rsi; SpinLock
0x1400b7362  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b7369  nop     dword ptr [rax+rax+00h]
0x1400b736e  mov     r14b, al
0x1400b7371  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7378  lea     rax, WPP_GLOBAL_Control
0x1400b737f  cmp     rcx, rax
0x1400b7382  jz      loc_1400B741A
0x1400b7388  mov     edx, [rcx+2Ch]
0x1400b738b  test    r13b, dl
0x1400b738e  jz      short loc_1400B73B5
0x1400b7390  cmp     byte ptr [rcx+29h], 4
0x1400b7394  jb      short loc_1400B73B5
0x1400b7396  mov     rcx, [rcx+18h]
0x1400b739a  lea     edx, [r12+65h]
0x1400b739f  mov     r9, rbx
0x1400b73a2  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b73a9  call    WPP_SF_q
0x1400b73ae  lea     rax, WPP_GLOBAL_Control
0x1400b73b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b73bc  cmp     rcx, rax
0x1400b73bf  jz      short loc_1400B741A
0x1400b73c1  mov     eax, [rcx+2Ch]
0x1400b73c4  test    r13b, al
0x1400b73c7  jz      short loc_1400B741A
0x1400b73c9  cmp     byte ptr [rcx+29h], 4
0x1400b73cd  jb      short loc_1400B741A
0x1400b73cf  mov     rdx, [rdi+1140h]
0x1400b73d6  mov     r10, 0D6BF94D5E57A42BDh
0x1400b73e0  mov     rcx, [rcx+18h]
0x1400b73e4  mov     rax, r10
0x1400b73e7  mov     r9, rbx
0x1400b73ea  sub     r9, [rdi+1148h]
0x1400b73f1  add     rdx, r9
0x1400b73f4  mul     rdx
0x1400b73f7  mov     rax, r10
0x1400b73fa  mov     r8, rdx
0x1400b73fd  mul     r9
0x1400b7400  shr     r8, 17h
0x1400b7404  mov     r9, rdx
0x1400b7407  mov     [rsp+60h+var_40], r8
0x1400b740c  shr     r9, 17h
0x1400b7410  mov     edx, 66h ; 'f'
0x1400b7415  call    WPP_SF_II
0x1400b741a  sub     rbx, [rdi+1148h]
0x1400b7421  mov     dl, r14b; NewIrql
0x1400b7424  add     [rdi+1140h], rbx
0x1400b742b  mov     rcx, rsi; SpinLock
0x1400b742e  mov     [rdi+1148h], r12
0x1400b7435  call    cs:__imp_KeReleaseSpinLock
0x1400b743c  nop     dword ptr [rax+rax+00h]
0x1400b7441  mov     edx, 1Fh
0x1400b7446  lea     rax, FVE_WIM_HASHING_PAUSED
0x1400b744d  lea     r14, WPP_GLOBAL_Control
0x1400b7454  jmp     loc_1400B766A
0x1400b7459  xor     r9d, r9d
0x1400b745c  mov     [rsp+60h+var_30], r12d
0x1400b7461  mov     [rsp+60h+var_38], r12d
0x1400b7466  lea     rdx, [rbp+arg_18]
0x1400b746a  lea     rcx, WNF_FVE_WIM_HASH_DELETION_TRIGGER
0x1400b7471  mov     [rbp+arg_18], r12d
0x1400b7475  mov     [rsp+60h+var_40], r12
0x1400b747a  lea     r8d, [r9+4]
0x1400b747e  call    cs:__imp_ZwUpdateWnfStateData
0x1400b7485  nop     dword ptr [rax+rax+00h]
0x1400b748a  test    eax, eax
0x1400b748c  jns     short loc_1400B74C2
0x1400b748e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7495  cmp     rcx, r14
0x1400b7498  jz      short loc_1400B74F1
0x1400b749a  mov     edx, [rcx+2Ch]
0x1400b749d  test    r13b, dl
0x1400b74a0  jz      short loc_1400B74F1
0x1400b74a2  cmp     byte ptr [rcx+29h], 2
0x1400b74a6  jb      short loc_1400B74F1
0x1400b74a8  mov     rcx, [rcx+18h]
0x1400b74ac  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b74b3  mov     edx, 62h ; 'b'
0x1400b74b8  mov     r9d, eax
0x1400b74bb  call    WPP_SF_d
0x1400b74c0  jmp     short loc_1400B74F1
0x1400b74c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b74c9  cmp     rcx, r14
0x1400b74cc  jz      short loc_1400B74F1
0x1400b74ce  mov     eax, [rcx+2Ch]
0x1400b74d1  test    r13b, al
0x1400b74d4  jz      short loc_1400B74F1
0x1400b74d6  cmp     byte ptr [rcx+29h], 4
0x1400b74da  jb      short loc_1400B74F1
0x1400b74dc  mov     rcx, [rcx+18h]
0x1400b74e0  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b74e7  mov     edx, 63h ; 'c'
0x1400b74ec  call    WPP_SF_
0x1400b74f1  lea     rsi, [rdi+1168h]
0x1400b74f8  mov     rcx, rsi; SpinLock
0x1400b74fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b7502  nop     dword ptr [rax+rax+00h]
0x1400b7507  mov     r14b, al
0x1400b750a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7511  lea     rax, WPP_GLOBAL_Control
0x1400b7518  cmp     rcx, rax
0x1400b751b  jz      short loc_1400B7543
0x1400b751d  mov     edx, [rcx+2Ch]
0x1400b7520  test    r13b, dl
0x1400b7523  jz      short loc_1400B7543
0x1400b7525  cmp     byte ptr [rcx+29h], 4
0x1400b7529  jb      short loc_1400B7543
0x1400b752b  mov     rcx, [rcx+18h]
0x1400b752f  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b7536  mov     edx, 64h ; 'd'
0x1400b753b  mov     r9, rbx
0x1400b753e  call    WPP_SF_q
0x1400b7543  mov     dl, r14b; NewIrql
0x1400b7546  mov     [rdi+1148h], rbx
0x1400b754d  mov     rcx, rsi; SpinLock
0x1400b7550  call    cs:__imp_KeReleaseSpinLock
0x1400b7557  nop     dword ptr [rax+rax+00h]
0x1400b755c  mov     edx, 1Eh
0x1400b7561  lea     rax, FVE_WIM_HASHING_RESUMED
0x1400b7568  jmp     loc_1400B744D
0x1400b756d  mov     r8, r13; Size
0x1400b7570  lea     rdx, WNF_FVE_WIM_HASH_DELETION_TRIGGER; Buf2
0x1400b7577  mov     rcx, r15; Buf1
0x1400b757a  call    memcmp
0x1400b757f  test    eax, eax
0x1400b7581  jnz     loc_1400B7679
0x1400b7587  cmp     ebx, 3
0x1400b758a  jnz     loc_1400B7679
0x1400b7590  mov     [rsp+60h+var_30], r12d
0x1400b7595  lea     r8d, [rax+4]
0x1400b7599  mov     [rsp+60h+var_38], r12d
0x1400b759e  lea     rdx, [rbp+arg_18]
0x1400b75a2  xor     r9d, r9d
0x1400b75a5  mov     [rsp+60h+var_40], r12
0x1400b75aa  lea     rcx, WNF_FVE_WIM_HASH_GENERATION_TRIGGER
0x1400b75b1  mov     [rbp+arg_18], 2
0x1400b75b8  call    cs:__imp_ZwUpdateWnfStateData
0x1400b75bf  nop     dword ptr [rax+rax+00h]
0x1400b75c4  test    eax, eax
0x1400b75c6  jns     short loc_1400B75FA
0x1400b75c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b75cf  cmp     rcx, r14
0x1400b75d2  jz      short loc_1400B7629
0x1400b75d4  mov     edx, [rcx+2Ch]
0x1400b75d7  test    r13b, dl
0x1400b75da  jz      short loc_1400B7629
0x1400b75dc  cmp     byte ptr [rcx+29h], 2
0x1400b75e0  jb      short loc_1400B7629
0x1400b75e2  mov     rcx, [rcx+18h]
0x1400b75e6  lea     edx, [rbx+64h]
0x1400b75e9  mov     r9d, eax
0x1400b75ec  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b75f3  call    WPP_SF_d
0x1400b75f8  jmp     short loc_1400B7629
0x1400b75fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7601  cmp     rcx, r14
0x1400b7604  jz      short loc_1400B7629
0x1400b7606  mov     eax, [rcx+2Ch]
0x1400b7609  test    r13b, al
0x1400b760c  jz      short loc_1400B7629
0x1400b760e  cmp     byte ptr [rcx+29h], 4
0x1400b7612  jb      short loc_1400B7629
0x1400b7614  mov     rcx, [rcx+18h]
0x1400b7618  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b761f  mov     edx, 68h ; 'h'
0x1400b7624  call    WPP_SF_
0x1400b7629  lea     rbx, [rdi+1168h]
0x1400b7630  mov     rcx, rbx; SpinLock
0x1400b7633  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b763a  nop     dword ptr [rax+rax+00h]
0x1400b763f  mov     rcx, rbx; SpinLock
0x1400b7642  mov     [rdi+1140h], r12
0x1400b7649  mov     dl, al; NewIrql
0x1400b764b  mov     [rdi+1148h], r12
0x1400b7652  call    cs:__imp_KeReleaseSpinLock
0x1400b7659  nop     dword ptr [rax+rax+00h]
0x1400b765e  mov     edx, 21h ; '!'
0x1400b7663  lea     rax, FVE_WIM_HASHES_DELETE
0x1400b766a  mov     rcx, rdi
0x1400b766d  mov     qword ptr [rbp+var_20], rax
0x1400b7671  mov     sil, 1
0x1400b7674  call    FveRaiseStatusChangedEvent
0x1400b7679  xor     r9d, r9d
0x1400b767c  mov     [rsp+60h+var_30], r12d
0x1400b7681  mov     [rsp+60h+var_38], r12d
0x1400b7686  lea     rdx, [rbp+arg_10]
0x1400b768a  mov     rcx, r15
0x1400b768d  mov     [rsp+60h+var_40], r12
0x1400b7692  lea     r8d, [r9+4]
0x1400b7696  call    cs:__imp_ZwUpdateWnfStateData
0x1400b769d  nop     dword ptr [rax+rax+00h]
0x1400b76a2  test    eax, eax
0x1400b76a4  jns     short loc_1400B76DA
0x1400b76a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b76ad  cmp     rcx, r14
0x1400b76b0  jz      short loc_1400B7720
0x1400b76b2  mov     edx, [rcx+2Ch]
0x1400b76b5  test    r13b, dl
0x1400b76b8  jz      short loc_1400B7720
0x1400b76ba  cmp     byte ptr [rcx+29h], 2
0x1400b76be  jb      short loc_1400B7720
0x1400b76c0  mov     rcx, [rcx+18h]
0x1400b76c4  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b76cb  mov     edx, 69h ; 'i'
0x1400b76d0  mov     r9d, eax
0x1400b76d3  call    WPP_SF_d
0x1400b76d8  jmp     short loc_1400B7720
0x1400b76da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b76e1  cmp     rcx, r14
0x1400b76e4  jz      short loc_1400B7709
0x1400b76e6  mov     eax, [rcx+2Ch]
0x1400b76e9  test    r13b, al
0x1400b76ec  jz      short loc_1400B7709
0x1400b76ee  cmp     byte ptr [rcx+29h], 4
0x1400b76f2  jb      short loc_1400B7709
0x1400b76f4  mov     rcx, [rcx+18h]
0x1400b76f8  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400b76ff  mov     edx, 6Ah ; 'j'
0x1400b7704  call    WPP_SF_
0x1400b7709  test    sil, sil
0x1400b770c  jz      short loc_1400B7720
0x1400b770e  mov     rcx, [rdi]
0x1400b7711  lea     rdx, [rbp+var_20]
0x1400b7715  mov     r9b, 1
0x1400b7718  xor     r8d, r8d
0x1400b771b  call    FveLogEventEx
0x1400b7720  mov     rbx, [rsp+60h+arg_0]
0x1400b7728  add     rsp, 60h
0x1400b772c  pop     r15
0x1400b772e  pop     r14
0x1400b7730  pop     r13
0x1400b7732  pop     r12
0x1400b7734  pop     rdi
0x1400b7735  pop     rsi
0x1400b7736  pop     rbp
0x1400b7737  retn
```
