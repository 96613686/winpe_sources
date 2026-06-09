# PptpInitialize

- ea: `0x140014fd8`
- end: `0x140015266`
- name: `PptpInitialize`
- size: `654`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140006810`
- `0x140016980`

## callees

- `0x140003e08`
- `0x140003e38`
- `0x1400073a0`
- `0x1400076d0`
- `0x140014fd8`
- `0x14001d1a0`
- `0x14001d3ac`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001506d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400150b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400151db`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015205`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001506d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400150b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400151db`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015205`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015052`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015052`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151ea`

## pseudocode

```c
__int64 __fastcall PptpInitialize(__int64 a1)
{
  KIRQL v2; // al
  bool v3; // zf
  KSPIN_LOCK *v4; // rcx
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  KIRQL v7; // al
  KIRQL v8; // al
  _WORD v10[2]; // [rsp+30h] [rbp-30h] BYREF
  int v11; // [rsp+34h] [rbp-2Ch]
  int v12; // [rsp+38h] [rbp-28h]
  int v13; // [rsp+3Ch] [rbp-24h]
  __int128 *v14; // [rsp+40h] [rbp-20h]
  __int128 v15; // [rsp+48h] [rbp-18h] BYREF

  v10[1] = 0;
  v13 = 0;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x65u,
      (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v3 = *(_QWORD *)(a1 + 64) == 0;
  v4 = (KSPIN_LOCK *)(a1 + 8);
  *(_BYTE *)(a1 + 16) = v2;
  if ( v3 )
  {
    KeReleaseSpinLock(v4, v2);
    if ( !*(_QWORD *)(a1 + 64) )
    {
      v11 = 47;
      v10[0] = 3;
      v14 = &v15;
      v12 = 4;
      LODWORD(v15) = 2;
      v5 = (_QWORD *)WskCreateAndIntializeSockContext();
      v6 = v5;
      if ( v5 )
      {
        v5[3] = 0;
        v5[2] = CallReceiveDatagramCallback;
        v5[1] = a1;
        v5[8] = CallpSendComplete;
        v5[9] = a1 + 112;
        v5[6] = CtlLogWskLibActivity;
        if ( (unsigned int)WskCreateSocket((__int64)v10, 0, 4, (__int64)v5, 0x20u) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x68u,
              (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids,
              0);
          }
          WskDestroySockContext(v6);
        }
        else
        {
          v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
          *(_QWORD *)(a1 + 64) = v6;
          *(_BYTE *)(a1 + 16) = v7;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v7);
          v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
          Pptpv4Initialized = 1;
          *(_BYTE *)(a1 + 16) = v8;
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v8);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return 0;
        if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu) && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_d(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x67u,
            (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids,
            0);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x6Bu,
        (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids,
        0);
    }
  }
  else
  {
    KeReleaseSpinLock(v4, v2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xBu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x66u,
        (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140014fd8  mov     [rsp-28h+arg_8], rbx
0x140014fdd  mov     [rsp-28h+arg_10], rsi
0x140014fe2  push    rbp
0x140014fe3  push    rdi
0x140014fe4  push    r12
0x140014fe6  push    r13
0x140014fe8  push    r14
0x140014fea  mov     rbp, rsp
0x140014fed  sub     rsp, 60h
0x140014ff1  mov     rax, cs:__security_cookie
0x140014ff8  xor     rax, rsp
0x140014ffb  mov     [rbp+var_8], rax
0x140014fff  xor     eax, eax
0x140015001  xorps   xmm0, xmm0
0x140015004  mov     [rbp+var_2E], ax
0x140015008  mov     rbx, rcx
0x14001500b  mov     [rbp+var_24], eax
0x14001500e  movups  [rbp+var_18], xmm0
0x140015012  mov     rcx, cs:WPP_GLOBAL_Control
0x140015019  lea     r13, WPP_GLOBAL_Control
0x140015020  lea     esi, [rax+2]
0x140015023  lea     r12, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x14001502a  cmp     rcx, r13
0x14001502d  jz      short loc_14001504B
0x14001502f  bt      dword ptr [rcx+2Ch], 0Bh
0x140015034  jnb     short loc_14001504B
0x140015036  cmp     [rcx+29h], sil
0x14001503a  jb      short loc_14001504B
0x14001503c  mov     rcx, [rcx+18h]
0x140015040  lea     edx, [rax+65h]
0x140015043  mov     r8, r12
0x140015046  call    WPP_SF_
0x14001504b  lea     rdi, [rbx+8]
0x14001504f  mov     rcx, rdi; SpinLock
0x140015052  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015059  nop     dword ptr [rax+rax+00h]
0x14001505e  cmp     qword ptr [rbx+40h], 0
0x140015063  mov     rcx, rdi; SpinLock
0x140015066  mov     [rbx+10h], al
0x140015069  mov     dl, al; NewIrql
0x14001506b  jz      short loc_1400150B4
0x14001506d  call    cs:__imp_KeReleaseSpinLock
0x140015074  nop     dword ptr [rax+rax+00h]
0x140015079  mov     rcx, cs:WPP_GLOBAL_Control
0x140015080  cmp     rcx, r13
0x140015083  jz      loc_14001523E
0x140015089  bt      dword ptr [rcx+2Ch], 0Bh
0x14001508e  jnb     loc_14001523E
0x140015094  cmp     [rcx+29h], sil
0x140015098  jb      loc_14001523E
0x14001509e  mov     rcx, [rcx+18h]
0x1400150a2  mov     edx, 66h ; 'f'
0x1400150a7  mov     r8, r12
0x1400150aa  call    WPP_SF_
0x1400150af  jmp     loc_14001523E
0x1400150b4  call    cs:__imp_KeReleaseSpinLock
0x1400150bb  nop     dword ptr [rax+rax+00h]
0x1400150c0  cmp     qword ptr [rbx+40h], 0
0x1400150c5  jnz     loc_140015211
0x1400150cb  mov     eax, 3
0x1400150d0  mov     [rbp+var_2C], 2Fh ; '/'
0x1400150d7  mov     [rbp+var_30], ax
0x1400150db  lea     rax, [rbp+var_18]
0x1400150df  mov     [rbp+var_20], rax
0x1400150e3  mov     [rbp+var_28], 4
0x1400150ea  mov     dword ptr [rbp+var_18], esi
0x1400150ed  call    WskCreateAndIntializeSockContext
0x1400150f2  mov     rsi, rax
0x1400150f5  test    rax, rax
0x1400150f8  jnz     short loc_140015136
0x1400150fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140015101  cmp     rcx, r13
0x140015104  jz      loc_14001523E
0x14001510a  bt      dword ptr [rcx+2Ch], 0Bh
0x14001510f  jnb     loc_140015211
0x140015115  cmp     byte ptr [rcx+29h], 1
0x140015119  jb      loc_140015211
0x14001511f  mov     rcx, [rcx+18h]
0x140015123  lea     edx, [rax+67h]
0x140015126  xor     r9d, r9d
0x140015129  mov     r8, r12
0x14001512c  call    WPP_SF_d
0x140015131  jmp     loc_140015211
0x140015136  lea     rax, CallReceiveDatagramCallback
0x14001513d  mov     qword ptr [rsi+18h], 0
0x140015145  mov     [rsi+10h], rax
0x140015149  lea     rcx, [rbp+var_30]
0x14001514d  lea     rax, CallpSendComplete
0x140015154  mov     [rsi+8], rbx
0x140015158  mov     [rsi+40h], rax
0x14001515c  xor     edx, edx
0x14001515e  lea     rax, [rbx+70h]
0x140015162  mov     [rsp+60h+var_40], 20h ; ' '
0x14001516a  mov     [rsi+48h], rax
0x14001516e  mov     r9, rsi
0x140015171  lea     rax, CtlLogWskLibActivity
0x140015178  lea     r8d, [rdx+4]
0x14001517c  mov     [rsi+30h], rax
0x140015180  call    WskCreateSocket
0x140015185  test    eax, eax
0x140015187  jz      short loc_1400151C0
0x140015189  mov     rcx, cs:WPP_GLOBAL_Control
0x140015190  cmp     rcx, r13
0x140015193  jz      short loc_1400151B6
0x140015195  bt      dword ptr [rcx+2Ch], 0Bh
0x14001519a  jnb     short loc_1400151B6
0x14001519c  cmp     byte ptr [rcx+29h], 1
0x1400151a0  jb      short loc_1400151B6
0x1400151a2  mov     rcx, [rcx+18h]
0x1400151a6  mov     edx, 68h ; 'h'
0x1400151ab  xor     r9d, r9d
0x1400151ae  mov     r8, r12
0x1400151b1  call    WPP_SF_d
0x1400151b6  mov     rcx, rsi
0x1400151b9  call    WskDestroySockContext
0x1400151be  jmp     short loc_140015211
0x1400151c0  mov     rcx, rdi; SpinLock
0x1400151c3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400151ca  nop     dword ptr [rax+rax+00h]
0x1400151cf  mov     rcx, rdi; SpinLock
0x1400151d2  mov     [rbx+40h], rsi
0x1400151d6  mov     dl, al; NewIrql
0x1400151d8  mov     [rbx+10h], al
0x1400151db  call    cs:__imp_KeReleaseSpinLock
0x1400151e2  nop     dword ptr [rax+rax+00h]
0x1400151e7  mov     rcx, rdi; SpinLock
0x1400151ea  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400151f1  nop     dword ptr [rax+rax+00h]
0x1400151f6  mov     rcx, rdi; SpinLock
0x1400151f9  mov     cs:Pptpv4Initialized, 1
0x140015200  mov     dl, al; NewIrql
0x140015202  mov     [rbx+10h], al
0x140015205  call    cs:__imp_KeReleaseSpinLock
0x14001520c  nop     dword ptr [rax+rax+00h]
0x140015211  mov     rcx, cs:WPP_GLOBAL_Control
0x140015218  cmp     rcx, r13
0x14001521b  jz      short loc_14001523E
0x14001521d  bt      dword ptr [rcx+2Ch], 0Bh
0x140015222  jnb     short loc_14001523E
0x140015224  cmp     byte ptr [rcx+29h], 1
0x140015228  jb      short loc_14001523E
0x14001522a  mov     rcx, [rcx+18h]
0x14001522e  mov     edx, 6Bh ; 'k'
0x140015233  xor     r9d, r9d
0x140015236  mov     r8, r12
0x140015239  call    WPP_SF_d
0x14001523e  xor     eax, eax
0x140015240  mov     rcx, [rbp+var_8]
0x140015244  xor     rcx, rsp; StackCookie
0x140015247  call    __security_check_cookie
0x14001524c  lea     r11, [rsp+60h+var_s0]
0x140015251  mov     rbx, [r11+38h]
0x140015255  mov     rsi, [r11+40h]
0x140015259  mov     rsp, r11
0x14001525c  pop     r14
0x14001525e  pop     r13
0x140015260  pop     r12
0x140015262  pop     rdi
0x140015263  pop     rbp
0x140015264  retn
```
