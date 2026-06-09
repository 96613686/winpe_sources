# RxDereference

- ea: `0x140058f00`
- end: `0x1400591ff`
- name: `RxDereference`
- size: `767`
- prototype: `void __stdcall(PVOID Instance, LOCK_HOLDING_STATE LockHoldingState)`
- caller_count: `37`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140001b70`
- `0x1400027b0`
- `0x140004050`
- `0x140008910`
- `0x140008f60`
- `0x140009ea0`
- `0x14000bf20`
- `0x14000e770`
- `0x140011e30`
- `0x1400228b8`
- `0x140048a00`
- `0x14004cac0`
- `0x14004d498`
- `0x14004dff0`
- `0x14004ec70`
- `0x14004f55c`
- `0x140050910`
- `0x140050d38`
- `0x140052bb0`
- `0x140057a80`
- `0x1400581a0`
- `0x140058540`
- `0x140059910`
- `0x14005a850`
- `0x14005b2b0`
- `0x14005e810`
- `0x14005f400`
- `0x140060560`
- `0x140061d40`
- `0x1400649a0`
- `0x14006c010`
- `0x14006c310`
- `0x14006d920`
- `0x140076760`
- `0x140078460`
- `0x140078fe0`
- `0x14007a310`

## callees

- `0x140010760`
- `0x140014d10`
- `0x140016e20`
- `0x1400228b8`
- `0x1400581a0`
- `0x140058f00`
- `0x140059210`
- `0x1400597e0`
- `0x14006c010`
- `0x14006c310`
- `0x140076760`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140059052`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400591e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059052`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400591e6`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400591cb`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400591cb`
- `ntoskrnl!KeReleaseMutex` at `0x140058f98`
- `ntoskrnl!KeReleaseMutex` at `0x140058f98`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400590d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400590d8`

## pseudocode

```c
void __stdcall RxDereference(PVOID Instance, LOCK_HOLDING_STATE LockHoldingState)
{
  __int64 v2; // r8
  signed __int64 v3; // rsi
  unsigned int v5; // r14d
  char v7; // bp
  int v8; // edi
  bool v9; // zf
  signed __int64 v10; // rax
  BOOLEAN v11; // dl
  __int64 v12; // r9
  __int64 v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  signed __int64 v16; // [rsp+80h] [rbp+8h]

  v3 = *(_QWORD *)Instance;
  v5 = *(unsigned __int16 *)Instance;
  v16 = *(_QWORD *)Instance;
  v7 = 0;
  do
  {
    v8 = 0;
    if ( (unsigned int)(HIDWORD(v3) - 1) > 1 )
      goto LABEL_3;
    if ( LockHoldingState == LHS_ExclusiveLockHeld )
    {
      if ( (_WORD)v5 != 0xEB13 )
      {
        if ( (_WORD)v5 != 0xEB1C && (_WORD)v5 != 0xEC30 || HIDWORD(v3) == 1 )
          v8 = 2;
LABEL_3:
        HIDWORD(v16) = HIDWORD(v3) - 1;
        goto LABEL_4;
      }
    }
    else if ( ((_WORD)v5 == 0xEC30 || (_WORD)v5 == 0xEB1C) && HIDWORD(v3) != 1 )
    {
      goto LABEL_3;
    }
    LOWORD(v16) = v16 | 0x1000;
    v8 = 1;
    if ( !v7 )
    {
      KeWaitForSingleObject(&RxScavengerMutex, Executive, 0, 0, 0);
      v7 = 1;
    }
LABEL_4:
    v10 = _InterlockedCompareExchange64((volatile signed __int64 *)Instance, v16, v3);
    v9 = v3 == v10;
    v3 = v10;
    v16 = v10;
    v11 = 28;
  }
  while ( !v9 );
  if ( v8 == 1 )
    RxpMarkInstanceForScavengedFinalization(Instance);
  if ( v7 )
    KeReleaseMutex(&RxScavengerMutex, 0);
  if ( v8 == 2 )
  {
    v12 = v5;
    switch ( v5 )
    {
      case 0xEB10u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            (unsigned int)WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
            (_DWORD)Instance,
            (__int64)Instance + 144);
        }
        RxOrphanSrvCall(Instance, 3221225662LL, v2, v12);
        v13 = *((_QWORD *)Instance + 11);
        if ( v13 )
        {
          PsDereferenceSiloContext(v13);
          *((_QWORD *)Instance + 11) = 0;
        }
        v14 = (void *)*((_QWORD *)Instance + 10);
        if ( v14 )
        {
          ExFreePoolWithTag(v14, 0);
          *((_QWORD *)Instance + 10) = 0;
        }
        v15 = (void *)*((_QWORD *)Instance + 9);
        if ( v15 )
        {
          ExFreePoolWithTag(v15, 0);
          *((_QWORD *)Instance + 9) = 0;
        }
        RxFreeObject(Instance);
        break;
      case 0xEB1Cu:
        RxFinalizeSrvOpen((PSRV_OPEN)Instance, v11, v2);
        break;
      case 0xEB11u:
        RxFinalizeNetRoot((PNET_ROOT)Instance, v11, v2);
        break;
      case 0xEB12u:
        RxFinalizeVNetRoot((PV_NET_ROOT)Instance, v11, v2);
        break;
      case 0xEB13u:
        RxFinalizeLogicalView(Instance);
        break;
      case 0xEC30u:
        RxFinalizeNetFobx((PFOBX)Instance, v11, v2);
        break;
      default:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v5);
        }
        break;
    }
  }
}

```

## disassembly

```asm
0x140058f00  push    rbx
0x140058f02  push    rbp
0x140058f03  push    rsi
0x140058f04  push    rdi
0x140058f05  push    r12
0x140058f07  push    r13
0x140058f09  push    r14
0x140058f0b  push    r15
0x140058f0d  sub     rsp, 38h
0x140058f11  mov     rsi, [rcx]
0x140058f14  mov     r15d, edx
0x140058f17  movzx   r14d, word ptr [rcx]
0x140058f1b  mov     rbx, rcx
0x140058f1e  mov     [rsp+78h+arg_0], rsi
0x140058f26  xor     bpl, bpl
0x140058f29  mov     edx, 0EB1Ch
0x140058f2e  mov     ecx, 1000h
0x140058f33  mov     r13d, 0EB13h
0x140058f39  mov     r12d, 0EC30h
0x140058f3f  mov     rax, rsi
0x140058f42  xor     edi, edi
0x140058f44  shr     rax, 20h
0x140058f48  dec     eax
0x140058f4a  cmp     eax, 1
0x140058f4d  jbe     short loc_140058FC2
0x140058f4f  mov     dword ptr [rsp+78h+arg_0+4], eax
0x140058f56  mov     rcx, [rsp+78h+arg_0]
0x140058f5e  mov     rax, rsi
0x140058f61  lock cmpxchg [rbx], rcx
0x140058f66  mov     rsi, rax
0x140058f69  mov     [rsp+78h+arg_0], rax
0x140058f71  mov     ecx, 1000h
0x140058f76  mov     edx, 0EB1Ch
0x140058f7b  jnz     short loc_140058F3F
0x140058f7d  cmp     edi, 1
0x140058f80  jnz     short loc_140058F8A
0x140058f82  mov     rcx, rbx; Instance
0x140058f85  call    RxpMarkInstanceForScavengedFinalization
0x140058f8a  test    bpl, bpl
0x140058f8d  jz      short loc_140058FA4
0x140058f8f  xor     edx, edx; Wait
0x140058f91  lea     rcx, RxScavengerMutex; Mutex
0x140058f98  call    cs:__imp_KeReleaseMutex
0x140058f9f  nop     dword ptr [rax+rax+00h]
0x140058fa4  cmp     edi, 2
0x140058fa7  jz      short loc_140058FF2
0x140058fa9  mov     eax, dword ptr [rsp+78h+arg_0+4]
0x140058fb0  add     rsp, 38h
0x140058fb4  pop     r15
0x140058fb6  pop     r14
0x140058fb8  pop     r13
0x140058fba  pop     r12
0x140058fbc  pop     rdi
0x140058fbd  pop     rsi
0x140058fbe  pop     rbp
0x140058fbf  pop     rbx
0x140058fc0  retn
0x140058fc2  cmp     r15d, 2
0x140058fc6  jnz     loc_14005909C
0x140058fcc  cmp     r13w, r14w
0x140058fd0  jz      loc_1400590AA
0x140058fd6  cmp     dx, r14w
0x140058fda  jnz     loc_140059075
0x140058fe0  test    eax, eax
0x140058fe2  jnz     loc_140058F4F
0x140058fe8  mov     edi, 2
0x140058fed  jmp     loc_140058F4F
0x140058ff2  mov     r9d, r14d
0x140058ff5  cmp     r14d, 0EB10h
0x140058ffc  jnz     loc_140059084
0x140059002  mov     rcx, cs:WPP_GLOBAL_Control
0x140059009  lea     rax, WPP_GLOBAL_Control
0x140059010  cmp     rcx, rax
0x140059013  jz      short loc_140059020
0x140059015  mov     eax, [rcx+2Ch]
0x140059018  test    al, al
0x14005901a  js      loc_140059198
0x140059020  mov     edx, 0C00000BEh
0x140059025  mov     rcx, rbx
0x140059028  call    RxOrphanSrvCall
0x14005902d  mov     rcx, [rbx+58h]
0x140059031  test    rcx, rcx
0x140059034  jnz     loc_1400591CB
0x14005903a  mov     rcx, [rbx+50h]; P
0x14005903e  test    rcx, rcx
0x140059041  jnz     loc_1400591E4
0x140059047  mov     rcx, [rbx+48h]; P
0x14005904b  test    rcx, rcx
0x14005904e  jz      short loc_140059066
0x140059050  xor     edx, edx; Tag
0x140059052  call    cs:__imp_ExFreePoolWithTag
0x140059059  nop     dword ptr [rax+rax+00h]
0x14005905e  mov     qword ptr [rbx+48h], 0
0x140059066  mov     rcx, rbx; pObject
0x140059069  call    RxFreeObject
0x14005906e  xor     eax, eax
0x140059070  jmp     loc_140058FB0
0x140059075  cmp     r12w, r14w
0x140059079  jz      loc_140058FE0
0x14005907f  jmp     loc_140058FE8
0x140059084  cmp     r9d, 0EB1Ch
0x14005908b  jnz     short loc_1400590ED
0x14005908d  mov     rcx, rbx; ThisSrvOpen
0x140059090  call    RxFinalizeSrvOpen
0x140059095  xor     eax, eax
0x140059097  jmp     loc_140058FB0
0x14005909c  cmp     r12w, r14w
0x1400590a0  jnz     short loc_14005911D
0x1400590a2  test    eax, eax
0x1400590a4  jnz     loc_140058F4F
0x1400590aa  or      word ptr [rsp+78h+arg_0], cx
0x1400590b2  mov     edi, 1
0x1400590b7  test    bpl, bpl
0x1400590ba  jnz     loc_140058F56
0x1400590c0  xor     r9d, r9d; Alertable
0x1400590c3  mov     [rsp+78h+Timeout], 0; Timeout
0x1400590cc  xor     r8d, r8d; WaitMode
0x1400590cf  lea     rcx, RxScavengerMutex; Object
0x1400590d6  xor     edx, edx; WaitReason
0x1400590d8  call    cs:__imp_KeWaitForSingleObject
0x1400590df  nop     dword ptr [rax+rax+00h]
0x1400590e4  movzx   ebp, dil
0x1400590e8  jmp     loc_140058F56
0x1400590ed  mov     ecx, r9d
0x1400590f0  sub     ecx, 0EB11h
0x1400590f6  jz      short loc_140059129
0x1400590f8  sub     ecx, 1
0x1400590fb  jz      loc_14005918B
0x140059101  sub     ecx, 1
0x140059104  jz      short loc_14005917E
0x140059106  cmp     ecx, 11Dh
0x14005910c  jnz     short loc_140059138
0x14005910e  mov     rcx, rbx; ThisFobx
0x140059111  call    RxFinalizeNetFobx
0x140059116  xor     eax, eax
0x140059118  jmp     loc_140058FB0
0x14005911d  cmp     dx, r14w
0x140059121  jz      loc_1400590A2
0x140059127  jmp     short loc_1400590AA
0x140059129  mov     rcx, rbx; ThisNetRoot
0x14005912c  call    RxFinalizeNetRoot
0x140059131  xor     eax, eax
0x140059133  jmp     loc_140058FB0
0x140059138  mov     rcx, cs:WPP_GLOBAL_Control
0x14005913f  lea     rax, WPP_GLOBAL_Control
0x140059146  cmp     rcx, rax
0x140059149  jz      loc_14005906E
0x14005914f  mov     eax, [rcx+2Ch]
0x140059152  test    al, al
0x140059154  jns     loc_14005906E
0x14005915a  cmp     byte ptr [rcx+29h], 2
0x14005915e  jb      loc_14005906E
0x140059164  mov     rcx, [rcx+18h]
0x140059168  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14005916f  mov     edx, 0Ch
0x140059174  call    WPP_SF_d
0x140059179  jmp     loc_14005906E
0x14005917e  mov     rcx, rbx; pObject
0x140059181  call    RxFinalizeLogicalView
0x140059186  jmp     loc_14005906E
0x14005918b  mov     rcx, rbx; ThisVNetRoot
0x14005918e  call    RxFinalizeVNetRoot
0x140059193  jmp     loc_14005906E
0x140059198  cmp     byte ptr [rcx+29h], 2
0x14005919c  jb      loc_140059020
0x1400591a2  mov     rcx, [rcx+18h]
0x1400591a6  lea     rax, [rbx+90h]
0x1400591ad  mov     edx, 28h ; '('
0x1400591b2  mov     [rsp+78h+Timeout], rax
0x1400591b7  mov     r9, rbx
0x1400591ba  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x1400591c1  call    WPP_SF_qZ
0x1400591c6  jmp     loc_140059020
0x1400591cb  call    cs:__imp_PsDereferenceSiloContext
0x1400591d2  nop     dword ptr [rax+rax+00h]
0x1400591d7  mov     qword ptr [rbx+58h], 0
0x1400591df  jmp     loc_14005903A
0x1400591e4  xor     edx, edx; Tag
0x1400591e6  call    cs:__imp_ExFreePoolWithTag
0x1400591ed  nop     dword ptr [rax+rax+00h]
0x1400591f2  mov     qword ptr [rbx+50h], 0
0x1400591fa  jmp     loc_140059047
```
