# DrDrive::OnQueryVolumeInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140014360`
- end: `0x140014b39`
- name: `?OnQueryVolumeInfoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `2009`
- prototype: `__int64(__int64, __int64, unsigned int, _DWORD *, ...)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x14000324c`
- `0x1400032c0`
- `0x1400065c0`
- `0x1400117e0`
- `0x140011870`
- `0x140011a2c`
- `0x140014360`
- `0x140023cf0`
- `0x140024020`

## pseudocode

```c
__int64 DrDrive::OnQueryVolumeInfoCompletion(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, ...)
{
  __int64 v4; // r15
  unsigned int v5; // r9d
  __int64 v6; // r8
  unsigned int v8; // ebx
  __int64 v9; // r12
  __int64 v10; // rbp
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // r9d
  _QWORD *v17; // r12
  __int64 v18; // rbx
  unsigned int v19; // edx
  va_list v20; // rcx
  RefCount *v21; // rcx
  __int64 v22; // r9
  unsigned int v23; // edx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  unsigned int *v29; // rbx
  unsigned int v30; // ecx
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rbx
  unsigned int v34; // ecx
  __int64 v36; // [rsp+30h] [rbp-48h]
  _QWORD v37[8]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int Sizea; // [rsp+90h] [rbp+18h]
  unsigned int Sizeb; // [rsp+90h] [rbp+18h]
  RefCount *v43; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v43 = va_arg(va1, RefCount *);
  v4 = (__int64)v43;
  v5 = a3;
  v6 = a2;
  v8 = -1073741434;
  v9 = *(_QWORD *)(*(_QWORD *)v43 + 32LL);
  v36 = v9;
  v10 = *(_QWORD *)(v9 + 48);
  if ( v5 < 0x14 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_118;
    v12 = 95;
LABEL_117:
    WPP_SF_(v11->AttachedDevice, v12, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_118:
    if ( v10 )
      DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_121;
  }
  if ( *(int *)(a2 + 12) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v6 = a2;
      v5 = a3;
    }
    if ( v5 < 0x15 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_118;
      v12 = 115;
      goto LABEL_117;
    }
    if ( v10 )
    {
      DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(v6 + 12), 0);
LABEL_113:
      *a4 = 1;
      goto LABEL_98;
    }
LABEL_112:
    DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_113;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v6 = a2;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        97,
        WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
        *(unsigned int *)(v6 + 16),
        *(_DWORD *)(v9 + 40));
  }
  v14 = a2;
  v15 = a3 - 20;
  Sizea = v15;
  v16 = *(_DWORD *)(a2 + 16) - *(_DWORD *)(v9 + 40);
  LODWORD(v43) = v16;
  if ( v15 > v16 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v15, v16);
    goto LABEL_118;
  }
  v17 = (_QWORD *)(a2 + 20);
  if ( v10 )
  {
    v18 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 64LL);
    v37[0] = v18;
    if ( v18 )
      RefCount::AddRef((RefCount *)v18);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v14 = a2;
      v15 = Sizea;
      v16 = (unsigned int)v43;
    }
    if ( v15 < v16 || *(_DWORD *)(v36 + 40) )
    {
      v19 = *(_DWORD *)(v14 + 16);
      if ( *(_DWORD *)(v18 + 28) < v19 && !DrFile::AllocateBuffer((DrFile *)v18, v19) )
      {
        v8 = -1073741670;
        DrDevice::CompleteBusyExchange(a1, v4, -1073741670, 0);
        v20 = (va_list)v37;
        *a4 = 0;
LABEL_104:
        SmartPtr<DrFile>::~SmartPtr<DrFile>(v20);
        goto LABEL_122;
      }
      memmove((void *)(*(_QWORD *)(v18 + 32) + *(unsigned int *)(v36 + 40)), v17, Sizea);
      *(_DWORD *)(v36 + 40) += Sizea;
    }
    SmartPtr<DrFile>::~SmartPtr<DrFile>(v37);
    v14 = a2;
    v15 = Sizea;
    v16 = (unsigned int)v43;
  }
  if ( v15 != v16 )
  {
    DrDevice::MarkIdle(v13, v4);
    DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
    v8 = 0;
LABEL_121:
    *a4 = 0;
    goto LABEL_122;
  }
  if ( !v10 )
    goto LABEL_112;
  v21 = *(RefCount **)(*(_QWORD *)(v10 + 64) + 64LL);
  v43 = v21;
  if ( v21 )
    RefCount::AddRef(v21);
  v22 = *(unsigned int *)(v10 + 448);
  Sizeb = *(_DWORD *)(v10 + 448);
  if ( *(_DWORD *)(v36 + 40) )
    v17 = (_QWORD *)*((_QWORD *)v21 + 4);
  v23 = *(_DWORD *)(v14 + 16);
  switch ( (_DWORD)v22 )
  {
    case 1:
      if ( v23 < 0x11 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v25 = 103;
        goto LABEL_102;
      }
      if ( *(_DWORD *)(v10 + 472) < 0x12u )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_97;
        v28 = 102;
        goto LABEL_96;
      }
      v33 = *(_QWORD *)(v10 + 456);
      *(_BYTE *)(v33 + 16) = *((_BYTE *)v17 + 16);
      *(_QWORD *)v33 = *v17;
      *(_DWORD *)(v33 + 8) = *((_DWORD *)v17 + 2);
      *(_DWORD *)(v33 + 12) = *((_DWORD *)v17 + 3);
      *(_DWORD *)(v10 + 472) -= 18;
      v34 = *(_DWORD *)(v33 + 12);
      if ( *(_DWORD *)(v10 + 472) < v34 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          goto LABEL_97;
        v28 = 101;
        goto LABEL_96;
      }
      if ( v23 != v34 + 17 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v25 = 100;
        goto LABEL_102;
      }
      memmove((void *)(v33 + 18), (char *)v17 + 17, v34);
      v31 = *(_DWORD *)(v33 + 12);
      goto LABEL_82;
    case 3:
      if ( v23 != 24 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v25 = 105;
        goto LABEL_102;
      }
      if ( *(_DWORD *)(v10 + 472) < 0x18u )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_97;
        v28 = 104;
        goto LABEL_96;
      }
      v32 = *(_QWORD *)(v10 + 456);
      *(_QWORD *)(v32 + 8) = v17[1];
      *(_DWORD *)(v32 + 20) = *((_DWORD *)v17 + 5);
      *(_DWORD *)(v32 + 16) = *((_DWORD *)v17 + 4);
      *(_QWORD *)v32 = *v17;
      *(_DWORD *)(v10 + 472) -= 24;
LABEL_83:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          113,
          WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
          v22,
          *(_DWORD *)(v14 + 12));
      DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(a2 + 12), *(_DWORD *)(a2 + 16));
      SmartPtr<DrFile>::~SmartPtr<DrFile>((RefCount **)va);
      goto LABEL_113;
    case 5:
      if ( v23 < 0xC )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v25 = 111;
        goto LABEL_102;
      }
      if ( *(_DWORD *)(v10 + 472) < 0xCu )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_97;
        v28 = 110;
        goto LABEL_96;
      }
      v29 = *(unsigned int **)(v10 + 456);
      *v29 = *(_DWORD *)v17 & 0xFFFBFFF7;
      v29[1] = *((_DWORD *)v17 + 1);
      v29[2] = *((_DWORD *)v17 + 2);
      *(_DWORD *)(v10 + 472) -= 12;
      v30 = v29[2];
      if ( *(_DWORD *)(v10 + 472) < v30 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_97;
        v28 = 109;
        goto LABEL_96;
      }
      if ( v23 != v30 + 12 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v25 = 108;
        goto LABEL_102;
      }
      memmove(v29 + 3, (char *)v17 + 12, v30);
      v31 = v29[2];
LABEL_82:
      v22 = Sizeb;
      v14 = a2;
      *(_DWORD *)(v10 + 472) -= v31;
      goto LABEL_83;
  }
  if ( (_DWORD)v22 != 7 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_103;
    v25 = 112;
LABEL_102:
    WPP_SF_(v24->AttachedDevice, v25, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_103:
    v8 = -1073741434;
    DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    va_copy(v20, va);
    *a4 = 1;
    goto LABEL_104;
  }
  if ( v23 != 32 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_103;
    v25 = 107;
    goto LABEL_102;
  }
  if ( *(_DWORD *)(v10 + 472) >= 0x20u )
  {
    v26 = *(_QWORD *)(v10 + 456);
    *(_QWORD *)(v26 + 16) = v17[2];
    *(_DWORD *)(v26 + 28) = *((_DWORD *)v17 + 7);
    *(_DWORD *)(v26 + 24) = *((_DWORD *)v17 + 6);
    *(_QWORD *)v26 = *v17;
    *(_QWORD *)(v26 + 8) = v17[1];
    *(_DWORD *)(v10 + 472) -= 32;
    goto LABEL_83;
  }
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v28 = 106;
LABEL_96:
    WPP_SF_(v27->AttachedDevice, v28, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
  }
LABEL_97:
  DrDevice::CompleteBusyExchange(a1, v4, -2147483643, 0);
  *a4 = 1;
  SmartPtr<DrFile>::~SmartPtr<DrFile>((RefCount **)va);
LABEL_98:
  v8 = 0;
LABEL_122:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(v4);
  return v8;
}

```

## disassembly

```asm
0x140014360  mov     [rsp+arg_18], r9
0x140014365  mov     dword ptr [rsp+Size], r8d
0x14001436a  mov     [rsp+arg_8], rdx
0x14001436f  push    rbx
0x140014370  push    rbp
0x140014371  push    rsi
0x140014372  push    rdi
0x140014373  push    r12
0x140014375  push    r13
0x140014377  push    r15
0x140014379  sub     rsp, 40h
0x14001437d  mov     r15, [rsp+78h+arg_20]
0x140014385  mov     r9d, r8d
0x140014388  mov     r8, rdx
0x14001438b  mov     r13, rcx
0x14001438e  mov     ebx, 0C0000186h
0x140014393  mov     rax, [r15]
0x140014396  mov     r12, [rax+20h]
0x14001439a  mov     [rsp+78h+var_48], r12
0x14001439f  mov     rbp, [r12+30h]
0x1400143a4  cmp     r9d, 14h
0x1400143a8  jnb     short loc_1400143DC
0x1400143aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143b1  lea     rdi, WPP_GLOBAL_Control
0x1400143b8  cmp     rcx, rdi
0x1400143bb  jz      loc_140014AF4
0x1400143c1  cmp     byte ptr [rcx+29h], 2
0x1400143c5  jb      loc_140014AF4
0x1400143cb  mov     edx, 5Fh ; '_'
0x1400143d0  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400143d7  jmp     loc_140014AEB
0x1400143dc  cmp     dword ptr [rdx+0Ch], 0
0x1400143e0  jl      loc_140014A53
0x1400143e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143ed  lea     rdi, WPP_GLOBAL_Control
0x1400143f4  lea     rsi, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400143fb  cmp     rcx, rdi
0x1400143fe  jz      short loc_14001444F
0x140014400  cmp     byte ptr [rcx+29h], 5
0x140014404  jb      short loc_14001441F
0x140014406  mov     rcx, [rcx+18h]
0x14001440a  mov     edx, 60h ; '`'
0x14001440f  mov     r8, rsi
0x140014412  call    WPP_SF_
0x140014417  mov     r8, [rsp+78h+arg_8]
0x14001441f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014426  cmp     rcx, rdi
0x140014429  jz      short loc_14001444F
0x14001442b  cmp     byte ptr [rcx+29h], 5
0x14001442f  jb      short loc_14001444F
0x140014431  mov     r9d, [r8+10h]
0x140014435  mov     edx, 61h ; 'a'
0x14001443a  mov     eax, [r12+28h]
0x14001443f  mov     r8, rsi
0x140014442  mov     rcx, [rcx+18h]
0x140014446  mov     [rsp+78h+var_58], eax
0x14001444a  call    WPP_SF_dd
0x14001444f  mov     eax, dword ptr [rsp+78h+Size]
0x140014456  mov     r8, [rsp+78h+arg_8]
0x14001445e  add     eax, 0FFFFFFECh
0x140014461  mov     dword ptr [rsp+78h+Size], eax
0x140014468  mov     r9d, [r8+10h]
0x14001446c  sub     r9d, [r12+28h]
0x140014471  mov     dword ptr [rsp+78h+arg_20], r9d
0x140014479  cmp     eax, r9d
0x14001447c  jbe     short loc_1400144B6
0x14001447e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014485  cmp     rcx, rdi
0x140014488  jz      loc_140014AF4
0x14001448e  cmp     byte ptr [rcx+29h], 2
0x140014492  jb      loc_140014AF4
0x140014498  mov     rcx, [rcx+18h]
0x14001449c  mov     edx, 62h ; 'b'
0x1400144a1  mov     [rsp+78h+var_58], r9d
0x1400144a6  mov     r8, rsi
0x1400144a9  mov     r9d, eax
0x1400144ac  call    WPP_SF_dd
0x1400144b1  jmp     loc_140014AF4
0x1400144b6  lea     r12, [r8+14h]
0x1400144ba  test    rbp, rbp
0x1400144bd  jz      loc_1400145B7
0x1400144c3  mov     rbx, [rbp+40h]
0x1400144c7  mov     rbx, [rbx+40h]
0x1400144cb  mov     [rsp+78h+var_40], rbx
0x1400144d0  test    rbx, rbx
0x1400144d3  jz      short loc_1400144DD
0x1400144d5  mov     rcx, rbx; this
0x1400144d8  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400144dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144e4  cmp     rcx, rdi
0x1400144e7  jz      short loc_140014517
0x1400144e9  cmp     byte ptr [rcx+29h], 5
0x1400144ed  jb      short loc_140014517
0x1400144ef  mov     rcx, [rcx+18h]
0x1400144f3  mov     edx, 63h ; 'c'
0x1400144f8  mov     r8, rsi
0x1400144fb  call    WPP_SF_
0x140014500  mov     r8, [rsp+78h+arg_8]
0x140014508  mov     eax, dword ptr [rsp+78h+Size]
0x14001450f  mov     r9d, dword ptr [rsp+78h+arg_20]
0x140014517  cmp     eax, r9d
0x14001451a  jb      short loc_140014527
0x14001451c  mov     rax, [rsp+78h+var_48]
0x140014521  cmp     dword ptr [rax+28h], 0
0x140014525  jz      short loc_140014596
0x140014527  mov     edx, [r8+10h]; unsigned int
0x14001452b  cmp     [rbx+1Ch], edx
0x14001452e  jnb     short loc_14001456B
0x140014530  mov     rcx, rbx; this
0x140014533  call    ?AllocateBuffer@DrFile@@QEAAPEAEK@Z; DrFile::AllocateBuffer(ulong)
0x140014538  test    rax, rax
0x14001453b  jnz     short loc_14001456B
0x14001453d  mov     ebx, 0C000009Ah
0x140014542  xor     r9d, r9d
0x140014545  mov     r8d, ebx
0x140014548  mov     rdx, r15
0x14001454b  mov     rcx, r13
0x14001454e  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140014553  mov     rax, [rsp+78h+arg_18]
0x14001455b  lea     rcx, [rsp+78h+var_40]
0x140014560  mov     dword ptr [rax], 0
0x140014566  jmp     loc_140014A23
0x14001456b  mov     rax, [rsp+78h+var_48]
0x140014570  mov     rdx, r12; Src
0x140014573  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x14001457b  mov     ecx, [rax+28h]
0x14001457e  add     rcx, [rbx+20h]; void *
0x140014582  call    memmove
0x140014587  mov     rax, [rsp+78h+var_48]
0x14001458c  mov     ecx, dword ptr [rsp+78h+Size]
0x140014593  add     [rax+28h], ecx
0x140014596  lea     rcx, [rsp+78h+var_40]
0x14001459b  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400145a0  mov     r8, [rsp+78h+arg_8]
0x1400145a8  mov     eax, dword ptr [rsp+78h+Size]
0x1400145af  mov     r9d, dword ptr [rsp+78h+arg_20]
0x1400145b7  cmp     eax, r9d
0x1400145ba  jnz     loc_140014A2D
0x1400145c0  test    rbp, rbp
0x1400145c3  jz      loc_140014AB3
0x1400145c9  mov     rcx, [rbp+40h]
0x1400145cd  mov     rcx, [rcx+40h]; this
0x1400145d1  mov     [rsp+78h+arg_20], rcx
0x1400145d9  test    rcx, rcx
0x1400145dc  jz      short loc_1400145E3
0x1400145de  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400145e3  mov     rax, [rsp+78h+var_48]
0x1400145e8  mov     r9d, [rbp+1C0h]
0x1400145ef  mov     dword ptr [rsp+78h+Size], r9d
0x1400145f7  cmp     dword ptr [rax+28h], 0
0x1400145fb  jz      short loc_140014601
0x1400145fd  mov     r12, [rcx+20h]
0x140014601  mov     edx, [r8+10h]
0x140014605  mov     ecx, r9d
0x140014608  sub     ecx, 1
0x14001460b  jz      loc_14001485F
0x140014611  sub     ecx, 2
0x140014614  jz      loc_1400147D7
0x14001461a  sub     ecx, 2
0x14001461d  jz      loc_1400146DD
0x140014623  cmp     ecx, 2
0x140014626  jz      short loc_14001464C
0x140014628  mov     rcx, cs:WPP_GLOBAL_Control
0x14001462f  cmp     rcx, rdi
0x140014632  jz      loc_1400149F7
0x140014638  cmp     byte ptr [rcx+29h], 2
0x14001463c  jb      loc_1400149F7
0x140014642  mov     edx, 70h ; 'p'
0x140014647  jmp     loc_1400149EB
0x14001464c  cmp     edx, 20h ; ' '
0x14001464f  jnz     short loc_1400146B9
0x140014651  cmp     [rbp+1D8h], edx
0x140014657  jb      short loc_140014695
0x140014659  mov     rax, [r12+10h]
0x14001465e  mov     rcx, [rbp+1C8h]
0x140014665  mov     [rcx+10h], rax
0x140014669  mov     eax, [r12+1Ch]
0x14001466e  mov     [rcx+1Ch], eax
0x140014671  mov     eax, [r12+18h]
0x140014676  mov     [rcx+18h], eax
0x140014679  mov     rax, [r12]
0x14001467d  mov     [rcx], rax
0x140014680  mov     rax, [r12+8]
0x140014685  mov     [rcx+8], rax
0x140014689  add     dword ptr [rbp+1D8h], 0FFFFFFE0h
0x140014690  jmp     loc_1400148E6
0x140014695  mov     rcx, cs:WPP_GLOBAL_Control
0x14001469c  cmp     rcx, rdi
0x14001469f  jz      loc_14001499E
0x1400146a5  cmp     byte ptr [rcx+29h], 2
0x1400146a9  jb      loc_14001499E
0x1400146af  mov     edx, 6Ah ; 'j'
0x1400146b4  jmp     loc_140014992
0x1400146b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146c0  cmp     rcx, rdi
0x1400146c3  jz      loc_1400149F7
0x1400146c9  cmp     byte ptr [rcx+29h], 2
0x1400146cd  jb      loc_1400149F7
0x1400146d3  mov     edx, 6Bh ; 'k'
0x1400146d8  jmp     loc_1400149EB
0x1400146dd  cmp     edx, 0Ch
0x1400146e0  jb      loc_1400147B3
0x1400146e6  cmp     dword ptr [rbp+1D8h], 0Ch
0x1400146ed  jb      loc_14001478F
0x1400146f3  mov     rbx, [rbp+1C8h]
0x1400146fa  mov     eax, [r12]
0x1400146fe  and     eax, 0FFFBFFF7h
0x140014703  mov     [rbx], eax
0x140014705  mov     eax, [r12+4]
0x14001470a  mov     [rbx+4], eax
0x14001470d  mov     eax, [r12+8]
0x140014712  mov     [rbx+8], eax
0x140014715  add     dword ptr [rbp+1D8h], 0FFFFFFF4h
0x14001471c  mov     ecx, [rbx+8]
0x14001471f  cmp     [rbp+1D8h], ecx
0x140014725  jb      short loc_14001476B
0x140014727  lea     eax, [rcx+0Ch]
0x14001472a  cmp     edx, eax
0x14001472c  jnz     short loc_140014747
0x14001472e  mov     r8d, ecx; Size
0x140014731  lea     rdx, [r12+0Ch]; Src
0x140014736  lea     rcx, [rbx+0Ch]; void *
0x14001473a  call    memmove
0x14001473f  mov     eax, [rbx+8]
0x140014742  jmp     loc_1400148D0
0x140014747  mov     rcx, cs:WPP_GLOBAL_Control
0x14001474e  cmp     rcx, rdi
0x140014751  jz      loc_1400149F7
0x140014757  cmp     byte ptr [rcx+29h], 2
0x14001475b  jb      loc_1400149F7
0x140014761  mov     edx, 6Ch ; 'l'
0x140014766  jmp     loc_1400149EB
0x14001476b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014772  cmp     rcx, rdi
0x140014775  jz      loc_14001499E
0x14001477b  cmp     byte ptr [rcx+29h], 2
0x14001477f  jb      loc_14001499E
0x140014785  mov     edx, 6Dh ; 'm'
0x14001478a  jmp     loc_140014992
0x14001478f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014796  cmp     rcx, rdi
0x140014799  jz      loc_14001499E
0x14001479f  cmp     byte ptr [rcx+29h], 2
0x1400147a3  jb      loc_14001499E
0x1400147a9  mov     edx, 6Eh ; 'n'
0x1400147ae  jmp     loc_140014992
0x1400147b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147ba  cmp     rcx, rdi
0x1400147bd  jz      loc_1400149F7
0x1400147c3  cmp     byte ptr [rcx+29h], 2
0x1400147c7  jb      loc_1400149F7
0x1400147cd  mov     edx, 6Fh ; 'o'
0x1400147d2  jmp     loc_1400149EB
0x1400147d7  cmp     edx, 18h
0x1400147da  jnz     short loc_14001483B
0x1400147dc  cmp     [rbp+1D8h], edx
0x1400147e2  jb      short loc_140014817
0x1400147e4  mov     rax, [r12+8]
0x1400147e9  mov     rcx, [rbp+1C8h]
0x1400147f0  mov     [rcx+8], rax
0x1400147f4  mov     eax, [r12+14h]
0x1400147f9  mov     [rcx+14h], eax
0x1400147fc  mov     eax, [r12+10h]
0x140014801  mov     [rcx+10h], eax
0x140014804  mov     rax, [r12]
0x140014808  mov     [rcx], rax
0x14001480b  add     dword ptr [rbp+1D8h], 0FFFFFFE8h
0x140014812  jmp     loc_1400148E6
0x140014817  mov     rcx, cs:WPP_GLOBAL_Control
0x14001481e  cmp     rcx, rdi
0x140014821  jz      loc_14001499E
0x140014827  cmp     byte ptr [rcx+29h], 2
0x14001482b  jb      loc_14001499E
0x140014831  mov     edx, 68h ; 'h'
0x140014836  jmp     loc_140014992
0x14001483b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014842  cmp     rcx, rdi
0x140014845  jz      loc_1400149F7
0x14001484b  cmp     byte ptr [rcx+29h], 2
0x14001484f  jb      loc_1400149F7
0x140014855  mov     edx, 69h ; 'i'
0x14001485a  jmp     loc_1400149EB
0x14001485f  cmp     edx, 11h
0x140014862  jb      loc_1400149D4
0x140014868  cmp     dword ptr [rbp+1D8h], 12h
0x14001486f  jb      loc_14001497B
0x140014875  mov     rbx, [rbp+1C8h]
0x14001487c  mov     al, [r12+10h]
0x140014881  mov     [rbx+10h], al
0x140014884  mov     rax, [r12]
0x140014888  mov     [rbx], rax
0x14001488b  mov     eax, [r12+8]
0x140014890  mov     [rbx+8], eax
0x140014893  mov     eax, [r12+0Ch]
0x140014898  mov     [rbx+0Ch], eax
0x14001489b  add     dword ptr [rbp+1D8h], 0FFFFFFEEh
0x1400148a2  mov     ecx, [rbx+0Ch]
0x1400148a5  cmp     [rbp+1D8h], ecx
0x1400148ab  jb      loc_140014962
0x1400148b1  lea     eax, [rcx+11h]
  ... truncated ...
```
