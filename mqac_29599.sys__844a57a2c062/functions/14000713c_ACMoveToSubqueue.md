# ACMoveToSubqueue

- ea: `0x14000713c`
- end: `0x14000745a`
- name: `ACMoveToSubqueue`
- size: `798`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140001c04`
- `0x140001c34`
- `0x140003d84`
- `0x14000713c`
- `0x14000968c`
- `0x14001a564`
- `0x140024bb0`
- `0x140024bf0`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140007276`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140007276`
- `ntoskrnl!IoFileObjectType` at `0x14000726a`
- `ntoskrnl!ProbeForRead` at `0x140007206`
- `ntoskrnl!ProbeForRead` at `0x140007206`

## pseudocode

```c
__int64 __fastcall ACMoveToSubqueue(__int64 a1, __int64 a2, void *a3, __int64 *a4)
{
  NTSTATUS v7; // esi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  void *v11; // rcx
  int v12; // r15d
  _QWORD *v13; // rsi
  const struct CQueueBase *v14; // r13
  unsigned int v15; // r14d
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  PVOID Object; // [rsp+30h] [rbp-88h] BYREF
  int v19; // [rsp+38h] [rbp-80h]
  __int64 v20; // [rsp+40h] [rbp-78h]
  __int64 v21; // [rsp+48h] [rbp-70h]
  __int64 v22; // [rsp+50h] [rbp-68h]
  void *v23; // [rsp+58h] [rbp-60h]
  __int128 v24; // [rsp+60h] [rbp-58h] BYREF

  v20 = a2;
  Object = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 213, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a3);
  }
  v7 = CQueueBase::Validate((const struct CQueueBase *)a3);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return (unsigned int)v7;
    }
    v9 = 214;
LABEL_8:
    WPP_SF_d(v8->Queue.ListEntry.Blink, v9, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, (unsigned int)v7);
    return (unsigned int)v7;
  }
  v24 = 0;
  ProbeForRead(a4, 0x24u, 1u);
  v21 = *a4;
  v22 = v21;
  v11 = (void *)a4[3];
  v23 = v11;
  if ( *((_DWORD *)a4 + 8) )
  {
    v24 = *(_OWORD *)(a4 + 1);
    v12 = 1;
    v19 = 1;
  }
  else
  {
    v12 = 0;
    v19 = 0;
  }
  Object = 0;
  v7 = ObReferenceObjectByHandle(v11, 1u, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return (unsigned int)v7;
    }
    v9 = 216;
    goto LABEL_8;
  }
  v13 = Object;
  if ( *((_QWORD *)Object + 1) != a1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 217, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
    }
    return 3221225480LL;
  }
  v14 = (const struct CQueueBase *)*((_QWORD *)Object + 3);
  v15 = CQueueBase::Validate(v14);
  if ( (v15 & 0x80000000) != 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return v15;
    }
    v17 = 218;
LABEL_26:
    WPP_SF_d(v16->Queue.ListEntry.Blink, v17, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v15);
    return v15;
  }
  if ( (*(_DWORD *)(v13[4] + 20LL) & 8) != 0 )
  {
    v15 = (*(__int64 (__fastcall **)(void *, __int64, const struct CQueueBase *, __int64, unsigned __int64))(*(_QWORD *)a3 + 120LL))(
            a3,
            v21,
            v14,
            v20,
            (unsigned __int64)&v24 & -(__int64)(v12 != 0));
    ACpObDereferenceObject(v13);
    if ( (v15 & 0x80000000) == 0 )
      return v15;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return v15;
    }
    v17 = 220;
    goto LABEL_26;
  }
  ACpObDereferenceObject(v13);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      219,
      &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      3221225506LL);
  }
  return 3221225506LL;
}

```

## disassembly

```asm
0x14000713c  push    rbx
0x14000713e  push    rsi
0x14000713f  push    rdi
0x140007140  push    r12
0x140007142  push    r13
0x140007144  push    r14
0x140007146  push    r15
0x140007148  sub     rsp, 80h
0x14000714f  mov     rax, cs:__security_cookie
0x140007156  xor     rax, rsp
0x140007159  mov     [rsp+0B8h+var_48], rax
0x14000715e  mov     r14, r9
0x140007161  mov     r12, r8
0x140007164  mov     [rsp+0B8h+var_78], rdx
0x140007169  mov     r13, rcx
0x14000716c  mov     [rsp+0B8h+var_88], r8
0x140007171  lea     rbx, WPP_GLOBAL_Control
0x140007178  mov     rcx, cs:WPP_GLOBAL_Control
0x14000717f  cmp     rcx, rbx
0x140007182  jz      short loc_1400071A8
0x140007184  mov     eax, [rcx+6Ch]
0x140007187  test    al, 4
0x140007189  jz      short loc_1400071A8
0x14000718b  mov     edx, 0D5h
0x140007190  mov     r9, r8
0x140007193  lea     rdi, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000719a  mov     r8, rdi
0x14000719d  mov     rcx, [rcx+58h]
0x1400071a1  call    WPP_SF_q
0x1400071a6  jmp     short loc_1400071AF
0x1400071a8  lea     rdi, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400071af  mov     rcx, r12; struct CQueueBase *
0x1400071b2  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x1400071b7  mov     esi, eax
0x1400071b9  test    eax, eax
0x1400071bb  jns     short loc_1400071F0
0x1400071bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071c4  cmp     rcx, rbx
0x1400071c7  jz      short loc_1400071E9
0x1400071c9  mov     edx, [rcx+6Ch]
0x1400071cc  mov     ebx, 1
0x1400071d1  test    bl, dl
0x1400071d3  jz      short loc_1400071E9
0x1400071d5  mov     edx, 0D6h
0x1400071da  mov     r9d, esi
0x1400071dd  mov     r8, rdi
0x1400071e0  mov     rcx, [rcx+58h]
0x1400071e4  call    WPP_SF_d
0x1400071e9  mov     eax, esi
0x1400071eb  jmp     loc_140007439
0x1400071f0  xorps   xmm0, xmm0
0x1400071f3  movups  [rsp+0B8h+var_58], xmm0
0x1400071f8  mov     ebx, 1
0x1400071fd  mov     r8d, ebx; Alignment
0x140007200  lea     edx, [rbx+23h]; Length
0x140007203  mov     rcx, r14; Address
0x140007206  call    cs:__imp_ProbeForRead
0x14000720d  nop     dword ptr [rax+rax+00h]
0x140007212  mov     rax, [r14]
0x140007215  mov     [rsp+0B8h+var_70], rax
0x14000721a  mov     [rsp+0B8h+var_68], rax
0x14000721f  mov     rcx, [r14+18h]; Handle
0x140007223  mov     [rsp+0B8h+var_60], rcx
0x140007228  cmp     dword ptr [r14+20h], 0
0x14000722d  jz      short loc_140007243
0x14000722f  movups  xmm0, xmmword ptr [r14+8]
0x140007234  movdqu  [rsp+0B8h+var_58], xmm0
0x14000723a  mov     r15d, ebx
0x14000723d  mov     [rsp+0B8h+var_80], ebx
0x140007241  jmp     short loc_14000724B
0x140007243  xor     r15d, r15d
0x140007246  mov     [rsp+0B8h+var_80], r15d
0x14000724b  mov     [rsp+0B8h+var_88], 0
0x140007254  mov     [rsp+0B8h+HandleInformation], 0; HandleInformation
0x14000725d  lea     rax, [rsp+0B8h+var_88]
0x140007262  mov     [rsp+0B8h+Object], rax; Object
0x140007267  mov     r9b, bl; AccessMode
0x14000726a  mov     r8, cs:__imp_IoFileObjectType
0x140007271  mov     r8, [r8]; ObjectType
0x140007274  mov     edx, ebx; DesiredAccess
0x140007276  call    cs:__imp_ObReferenceObjectByHandle
0x14000727d  nop     dword ptr [rax+rax+00h]
0x140007282  mov     esi, eax
0x140007284  test    eax, eax
0x140007286  jns     short loc_1400072B4
0x140007288  mov     rcx, cs:WPP_GLOBAL_Control
0x14000728f  lea     rax, WPP_GLOBAL_Control
0x140007296  cmp     rcx, rax
0x140007299  jz      loc_1400071E9
0x14000729f  mov     edx, [rcx+6Ch]
0x1400072a2  test    bl, dl
0x1400072a4  jz      loc_1400071E9
0x1400072aa  mov     edx, 0D8h
0x1400072af  jmp     loc_1400071DA
0x1400072b4  mov     rsi, [rsp+0B8h+var_88]
0x1400072b9  cmp     [rsi+8], r13
0x1400072bd  jz      short loc_1400072F4
0x1400072bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072c6  lea     rax, WPP_GLOBAL_Control
0x1400072cd  cmp     rcx, rax
0x1400072d0  jz      short loc_1400072EA
0x1400072d2  mov     eax, [rcx+6Ch]
0x1400072d5  test    bl, al
0x1400072d7  jz      short loc_1400072EA
0x1400072d9  mov     edx, 0D9h
0x1400072de  mov     r8, rdi
0x1400072e1  mov     rcx, [rcx+58h]
0x1400072e5  call    WPP_SF_
0x1400072ea  mov     eax, 0C0000008h
0x1400072ef  jmp     loc_140007439
0x1400072f4  mov     r13, [rsi+18h]
0x1400072f8  mov     rcx, r13; struct CQueueBase *
0x1400072fb  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140007300  mov     r14d, eax
0x140007303  test    eax, eax
0x140007305  jns     short loc_14000733D
0x140007307  mov     rcx, cs:WPP_GLOBAL_Control
0x14000730e  lea     rax, WPP_GLOBAL_Control
0x140007315  cmp     rcx, rax
0x140007318  jz      short loc_140007335
0x14000731a  mov     edx, [rcx+6Ch]
0x14000731d  test    bl, dl
0x14000731f  jz      short loc_140007335
0x140007321  mov     edx, 0DAh
0x140007326  mov     r9d, r14d
0x140007329  mov     r8, rdi
0x14000732c  mov     rcx, [rcx+58h]
0x140007330  call    WPP_SF_d
0x140007335  mov     eax, r14d
0x140007338  jmp     loc_140007439
0x14000733d  mov     rax, [rsi+20h]
0x140007341  mov     edx, [rax+14h]
0x140007344  test    dl, 8
0x140007347  jnz     short loc_14000738C
0x140007349  mov     rcx, rsi; void *
0x14000734c  call    ?ACpObDereferenceObject@@YAXPEAX@Z; ACpObDereferenceObject(void *)
0x140007351  mov     rcx, cs:WPP_GLOBAL_Control
0x140007358  lea     rax, WPP_GLOBAL_Control
0x14000735f  cmp     rcx, rax
0x140007362  jz      short loc_140007382
0x140007364  mov     eax, [rcx+6Ch]
0x140007367  test    bl, al
0x140007369  jz      short loc_140007382
0x14000736b  mov     edx, 0DBh
0x140007370  mov     r9d, 0C0000022h
0x140007376  mov     r8, rdi
0x140007379  mov     rcx, [rcx+58h]
0x14000737d  call    WPP_SF_d
0x140007382  mov     eax, 0C0000022h
0x140007387  jmp     loc_140007439
0x14000738c  mov     rax, [r12]
0x140007390  mov     rax, [rax+78h]
0x140007394  neg     r15d
0x140007397  sbb     r10, r10
0x14000739a  lea     rcx, [rsp+0B8h+var_58]
0x14000739f  and     r10, rcx
0x1400073a2  mov     [rsp+0B8h+Object], r10
0x1400073a7  mov     r9, [rsp+0B8h+var_78]
0x1400073ac  mov     r8, r13
0x1400073af  mov     rdx, [rsp+0B8h+var_70]
0x1400073b4  mov     rcx, r12
0x1400073b7  call    _guard_dispatch_icall
0x1400073bc  mov     r14d, eax
0x1400073bf  mov     rcx, rsi; void *
0x1400073c2  call    ?ACpObDereferenceObject@@YAXPEAX@Z; ACpObDereferenceObject(void *)
0x1400073c7  test    r14d, r14d
0x1400073ca  jns     loc_140007335
0x1400073d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073d7  lea     rax, WPP_GLOBAL_Control
0x1400073de  cmp     rcx, rax
0x1400073e1  jz      loc_140007335
0x1400073e7  mov     edx, [rcx+6Ch]
0x1400073ea  test    bl, dl
0x1400073ec  jz      loc_140007335
0x1400073f2  mov     edx, 0DCh
0x1400073f7  jmp     loc_140007326
0x1400073fc  mov     ebx, eax
0x1400073fe  lea     rax, WPP_GLOBAL_Control
0x140007405  mov     rcx, cs:WPP_GLOBAL_Control
0x14000740c  cmp     rcx, rax
0x14000740f  jz      short loc_140007437
0x140007411  mov     edx, [rcx+6Ch]
0x140007414  test    dl, 1
0x140007417  jz      short loc_140007437
0x140007419  mov     edx, 0D7h
0x14000741e  mov     dword ptr [rsp+0B8h+Object], ebx
0x140007422  mov     r9, [rsp+0B8h+var_88]
0x140007427  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000742e  mov     rcx, [rcx+58h]
0x140007432  call    WPP_SF_qD
0x140007437  mov     eax, ebx
0x140007439  mov     rcx, [rsp+0B8h+var_48]
0x14000743e  xor     rcx, rsp; StackCookie
0x140007441  call    __security_check_cookie
0x140007446  add     rsp, 80h
0x14000744d  pop     r15
0x14000744f  pop     r14
0x140007451  pop     r13
0x140007453  pop     r12
0x140007455  pop     rdi
0x140007456  pop     rsi
0x140007457  pop     rbx
0x140007458  retn
```
