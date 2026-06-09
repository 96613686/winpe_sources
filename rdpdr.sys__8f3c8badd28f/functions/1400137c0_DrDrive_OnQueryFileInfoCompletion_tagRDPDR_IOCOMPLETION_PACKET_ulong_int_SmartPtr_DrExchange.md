# DrDrive::OnQueryFileInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x1400137c0`
- end: `0x140013e5d`
- name: `?OnQueryFileInfoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `1693`
- prototype: `__int64(__int64, __int64, unsigned int, _DWORD *, ...)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x1400065c0`
- `0x1400117e0`
- `0x140011870`
- `0x140011a2c`
- `0x1400137c0`
- `0x140023cf0`
- `0x140024020`

## pseudocode

```c
__int64 DrDrive::OnQueryFileInfoCompletion(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, ...)
{
  __int64 v4; // r14
  __int64 v8; // r12
  struct _DEVICE_OBJECT *v9; // rdx
  __int64 v10; // rsi
  unsigned int v11; // ebx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  PDEVICE_OBJECT v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // r15
  __int64 v18; // rbx
  unsigned int v19; // eax
  unsigned int v20; // edx
  va_list v21; // rcx
  RefCount *v22; // rcx
  __int64 v23; // r9
  int v24; // edx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  _DWORD *v27; // rcx
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // [rsp+78h] [rbp+10h] BYREF
  size_t Size; // [rsp+80h] [rbp+18h]
  _DWORD *v35; // [rsp+88h] [rbp+20h]
  RefCount *v36; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v36 = va_arg(va1, RefCount *);
  v35 = a4;
  v4 = (__int64)v36;
  v8 = *(_QWORD *)(*(_QWORD *)v36 + 32LL);
  v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, a3);
    v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
  }
  v10 = *(_QWORD *)(v8 + 48);
  v11 = -1073741434;
  if ( a3 < 0x14 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_98;
    v13 = 118;
LABEL_97:
    WPP_SF_(v12->AttachedDevice, v13, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_98:
    if ( v10 )
      DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_101;
  }
  if ( *(int *)(a2 + 12) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    if ( a3 < 0x15 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_98;
      v13 = 133;
      goto LABEL_97;
    }
    if ( v10 )
    {
      DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(a2 + 12), 0);
LABEL_93:
      *v35 = 1;
      goto LABEL_78;
    }
LABEL_92:
    DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_93;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        120,
        WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
        *(unsigned int *)(a2 + 16),
        *(_DWORD *)(v8 + 40));
      v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    }
  }
  v15 = a3 - 20;
  v16 = *(_DWORD *)(a2 + 16) - *(_DWORD *)(v8 + 40);
  LODWORD(v36) = v16;
  LODWORD(Size) = a3 - 20;
  if ( a3 - 20 > v16 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v15, v16);
    goto LABEL_98;
  }
  v17 = a2 + 20;
  if ( v10 )
  {
    v18 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 64LL);
    v33 = v18;
    if ( v18 )
      RefCount::AddRef((RefCount *)v18);
    if ( WPP_GLOBAL_Control != v9 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
        v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
      }
      if ( WPP_GLOBAL_Control != v9 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          123,
          WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
          *(unsigned int *)(v18 + 24),
          *(_DWORD *)(v10 + 448));
    }
    v19 = Size;
    if ( (unsigned int)Size < (unsigned int)v36 || *(_DWORD *)(v8 + 40) )
    {
      v20 = *(_DWORD *)(a2 + 16);
      if ( *(_DWORD *)(v18 + 28) < v20 )
      {
        if ( !DrFile::AllocateBuffer((DrFile *)v18, v20) )
        {
          v11 = -1073741670;
          DrDevice::CompleteBusyExchange(a1, v4, -1073741670, 0);
          v21 = (va_list)&v33;
          *v35 = 0;
LABEL_84:
          SmartPtr<DrFile>::~SmartPtr<DrFile>(v21);
          goto LABEL_102;
        }
        v19 = Size;
      }
      memmove((void *)(*(_QWORD *)(v18 + 32) + *(unsigned int *)(v8 + 40)), (const void *)(a2 + 20), v19);
      *(_DWORD *)(v8 + 40) += Size;
    }
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v33);
    v15 = Size;
    v16 = (unsigned int)v36;
  }
  if ( v15 != v16 )
  {
    DrDevice::MarkIdle(v14, v4);
    DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
    v11 = 0;
LABEL_101:
    *v35 = 0;
    goto LABEL_102;
  }
  if ( !v10 )
    goto LABEL_92;
  v22 = *(RefCount **)(*(_QWORD *)(v10 + 64) + 64LL);
  v36 = v22;
  if ( v22 )
    RefCount::AddRef(v22);
  v23 = *(unsigned int *)(v10 + 448);
  if ( *(_DWORD *)(v8 + 40) )
    v17 = *((_QWORD *)v22 + 4);
  v24 = *(_DWORD *)(a2 + 16);
  if ( (_DWORD)v23 == 4 )
  {
    if ( v24 != 36 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_83;
      v26 = 125;
      goto LABEL_82;
    }
    if ( *(_DWORD *)(v10 + 472) < 0x28u )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_77;
      v29 = 124;
      goto LABEL_76;
    }
    v31 = *(_QWORD *)(v10 + 456);
    *(_QWORD *)(v31 + 24) = *(_QWORD *)(v17 + 24);
    *(_QWORD *)v31 = *(_QWORD *)v17;
    *(_DWORD *)(v31 + 32) = *(_DWORD *)(v17 + 32);
    *(_QWORD *)(v31 + 8) = *(_QWORD *)(v17 + 8);
    *(_QWORD *)(v31 + 16) = *(_QWORD *)(v17 + 16);
    *(_DWORD *)(v10 + 472) -= 40;
LABEL_69:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        131,
        WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
        v23,
        *(_DWORD *)(a2 + 12));
    DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(a2 + 12), *(_DWORD *)(a2 + 16));
    SmartPtr<DrFile>::~SmartPtr<DrFile>((RefCount **)va);
    goto LABEL_93;
  }
  if ( (_DWORD)v23 == 5 )
  {
    if ( v24 != 22 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_83;
      v26 = 127;
      goto LABEL_82;
    }
    if ( *(_DWORD *)(v10 + 472) < 0x18u )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_77;
      v29 = 126;
      goto LABEL_76;
    }
    v30 = *(_QWORD *)(v10 + 456);
    *(_QWORD *)v30 = *(_QWORD *)v17;
    *(_BYTE *)(v30 + 20) = *(_BYTE *)(v17 + 20);
    *(_BYTE *)(v30 + 21) = *(_BYTE *)(v17 + 21);
    *(_QWORD *)(v30 + 8) = *(_QWORD *)(v17 + 8);
    *(_DWORD *)(v30 + 16) = *(_DWORD *)(v17 + 16);
    *(_DWORD *)(v10 + 472) -= 24;
    goto LABEL_69;
  }
  if ( (_DWORD)v23 != 35 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_83;
    v26 = 130;
LABEL_82:
    WPP_SF_(v25->AttachedDevice, v26, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_83:
    v11 = -1073741434;
    DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    va_copy(v21, va);
    *v35 = 1;
    goto LABEL_84;
  }
  if ( v24 != 8 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_83;
    v26 = 129;
    goto LABEL_82;
  }
  if ( *(_DWORD *)(v10 + 472) >= 8u )
  {
    v27 = *(_DWORD **)(v10 + 456);
    *v27 = *(_DWORD *)v17;
    v27[1] = *(_DWORD *)(v17 + 4);
    *(_DWORD *)(v10 + 472) -= 8;
    goto LABEL_69;
  }
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v29 = 128;
LABEL_76:
    WPP_SF_(v28->AttachedDevice, v29, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
  }
LABEL_77:
  DrDevice::CompleteBusyExchange(a1, v4, -2147483643, 0);
  *v35 = 1;
  SmartPtr<DrFile>::~SmartPtr<DrFile>((RefCount **)va);
LABEL_78:
  v11 = 0;
LABEL_102:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(v4);
  return v11;
}

```

## disassembly

```asm
0x1400137c0  mov     [rsp+arg_18], r9
0x1400137c5  push    rbx
0x1400137c6  push    rbp
0x1400137c7  push    rsi
0x1400137c8  push    r12
0x1400137ca  push    r13
0x1400137cc  push    r14
0x1400137ce  push    r15
0x1400137d0  sub     rsp, 30h
0x1400137d4  mov     r14, [rsp+68h+arg_20]
0x1400137dc  mov     r15d, r8d
0x1400137df  mov     r13, rdx
0x1400137e2  mov     rbp, rcx
0x1400137e5  mov     rax, [r14]
0x1400137e8  mov     r12, [rax+20h]
0x1400137ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137f3  lea     rdx, WPP_GLOBAL_Control
0x1400137fa  cmp     rcx, rdx
0x1400137fd  jz      short loc_140013824
0x1400137ff  cmp     byte ptr [rcx+29h], 5
0x140013803  jb      short loc_140013824
0x140013805  mov     rcx, [rcx+18h]
0x140013809  mov     r9d, r8d
0x14001380c  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013813  mov     edx, 75h ; 'u'
0x140013818  call    WPP_SF_d
0x14001381d  lea     rdx, WPP_GLOBAL_Control
0x140013824  mov     rsi, [r12+30h]
0x140013829  mov     ebx, 0C0000186h
0x14001382e  cmp     r15d, 14h
0x140013832  jnb     short loc_140013858
0x140013834  mov     rcx, cs:WPP_GLOBAL_Control
0x14001383b  cmp     rcx, rdx
0x14001383e  jz      loc_140013E17
0x140013844  cmp     byte ptr [rcx+29h], 2
0x140013848  jb      loc_140013E17
0x14001384e  mov     edx, 76h ; 'v'
0x140013853  jmp     loc_140013E07
0x140013858  cmp     dword ptr [r13+0Ch], 0
0x14001385d  jl      loc_140013D85
0x140013863  mov     rcx, cs:WPP_GLOBAL_Control
0x14001386a  cmp     rcx, rdx
0x14001386d  jz      short loc_1400138CC
0x14001386f  cmp     byte ptr [rcx+29h], 5
0x140013873  jb      short loc_140013891
0x140013875  mov     rcx, [rcx+18h]
0x140013879  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013880  mov     edx, 77h ; 'w'
0x140013885  call    WPP_SF_
0x14001388a  lea     rdx, WPP_GLOBAL_Control
0x140013891  mov     rcx, cs:WPP_GLOBAL_Control
0x140013898  cmp     rcx, rdx
0x14001389b  jz      short loc_1400138CC
0x14001389d  cmp     byte ptr [rcx+29h], 5
0x1400138a1  jb      short loc_1400138CC
0x1400138a3  mov     eax, [r12+28h]
0x1400138a8  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400138af  mov     r9d, [r13+10h]
0x1400138b3  mov     edx, 78h ; 'x'
0x1400138b8  mov     rcx, [rcx+18h]
0x1400138bc  mov     [rsp+68h+var_48], eax
0x1400138c0  call    WPP_SF_dd
0x1400138c5  lea     rdx, WPP_GLOBAL_Control
0x1400138cc  mov     r8d, [r13+10h]
0x1400138d0  lea     eax, [r15-14h]
0x1400138d4  sub     r8d, [r12+28h]
0x1400138d9  mov     dword ptr [rsp+68h+arg_20], r8d
0x1400138e1  mov     dword ptr [rsp+68h+Size], eax
0x1400138e8  cmp     eax, r8d
0x1400138eb  jbe     short loc_140013929
0x1400138ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138f4  cmp     rcx, rdx
0x1400138f7  jz      loc_140013E17
0x1400138fd  cmp     byte ptr [rcx+29h], 2
0x140013901  jb      loc_140013E17
0x140013907  mov     rcx, [rcx+18h]
0x14001390b  mov     edx, 79h ; 'y'
0x140013910  mov     [rsp+68h+var_48], r8d
0x140013915  mov     r9d, eax
0x140013918  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x14001391f  call    WPP_SF_dd
0x140013924  jmp     loc_140013E17
0x140013929  lea     r15, [r13+14h]
0x14001392d  test    rsi, rsi
0x140013930  jz      loc_140013A4F
0x140013936  mov     rbx, [rsi+40h]
0x14001393a  mov     rbx, [rbx+40h]
0x14001393e  mov     [rsp+68h+arg_8], rbx
0x140013943  test    rbx, rbx
0x140013946  jz      short loc_140013950
0x140013948  mov     rcx, rbx; this
0x14001394b  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140013950  mov     rcx, cs:WPP_GLOBAL_Control
0x140013957  cmp     rcx, rdx
0x14001395a  jz      short loc_1400139B3
0x14001395c  cmp     byte ptr [rcx+29h], 5
0x140013960  jb      short loc_14001397E
0x140013962  mov     rcx, [rcx+18h]
0x140013966  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x14001396d  mov     edx, 7Ah ; 'z'
0x140013972  call    WPP_SF_
0x140013977  lea     rdx, WPP_GLOBAL_Control
0x14001397e  mov     rcx, cs:WPP_GLOBAL_Control
0x140013985  cmp     rcx, rdx
0x140013988  jz      short loc_1400139B3
0x14001398a  cmp     byte ptr [rcx+29h], 5
0x14001398e  jb      short loc_1400139B3
0x140013990  mov     eax, [rsi+1C0h]
0x140013996  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x14001399d  mov     r9d, [rbx+18h]
0x1400139a1  mov     edx, 7Bh ; '{'
0x1400139a6  mov     rcx, [rcx+18h]
0x1400139aa  mov     [rsp+68h+var_48], eax
0x1400139ae  call    WPP_SF_dd
0x1400139b3  mov     eax, dword ptr [rsp+68h+Size]
0x1400139ba  cmp     eax, dword ptr [rsp+68h+arg_20]
0x1400139c1  jb      short loc_1400139CB
0x1400139c3  cmp     dword ptr [r12+28h], 0
0x1400139c9  jz      short loc_140013A36
0x1400139cb  mov     edx, [r13+10h]; unsigned int
0x1400139cf  cmp     [rbx+1Ch], edx
0x1400139d2  jnb     short loc_140013A16
0x1400139d4  mov     rcx, rbx; this
0x1400139d7  call    ?AllocateBuffer@DrFile@@QEAAPEAEK@Z; DrFile::AllocateBuffer(ulong)
0x1400139dc  test    rax, rax
0x1400139df  jnz     short loc_140013A0F
0x1400139e1  mov     ebx, 0C000009Ah
0x1400139e6  xor     r9d, r9d
0x1400139e9  mov     r8d, ebx
0x1400139ec  mov     rdx, r14
0x1400139ef  mov     rcx, rbp
0x1400139f2  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400139f7  mov     rax, [rsp+68h+arg_18]
0x1400139ff  lea     rcx, [rsp+68h+arg_8]
0x140013a04  mov     dword ptr [rax], 0
0x140013a0a  jmp     loc_140013D55
0x140013a0f  mov     eax, dword ptr [rsp+68h+Size]
0x140013a16  mov     ecx, [r12+28h]
0x140013a1b  mov     rdx, r15; Src
0x140013a1e  add     rcx, [rbx+20h]; void *
0x140013a22  mov     r8d, eax; Size
0x140013a25  call    memmove
0x140013a2a  mov     eax, dword ptr [rsp+68h+Size]
0x140013a31  add     [r12+28h], eax
0x140013a36  lea     rcx, [rsp+68h+arg_8]
0x140013a3b  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140013a40  mov     eax, dword ptr [rsp+68h+Size]
0x140013a47  mov     r8d, dword ptr [rsp+68h+arg_20]
0x140013a4f  cmp     eax, r8d
0x140013a52  jnz     loc_140013D5F
0x140013a58  test    rsi, rsi
0x140013a5b  jz      loc_140013DD2
0x140013a61  mov     rcx, [rsi+40h]
0x140013a65  mov     rcx, [rcx+40h]; this
0x140013a69  mov     [rsp+68h+arg_20], rcx
0x140013a71  test    rcx, rcx
0x140013a74  jz      short loc_140013A7B
0x140013a76  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140013a7b  cmp     dword ptr [r12+28h], 0
0x140013a81  mov     r9d, [rsi+1C0h]
0x140013a88  jz      short loc_140013A8E
0x140013a8a  mov     r15, [rcx+20h]
0x140013a8e  mov     edx, [r13+10h]
0x140013a92  mov     ecx, r9d
0x140013a95  sub     ecx, 4
0x140013a98  jz      loc_140013BF3
0x140013a9e  sub     ecx, 1
0x140013aa1  jz      loc_140013B59
0x140013aa7  cmp     ecx, 1Eh
0x140013aaa  jz      short loc_140013AD7
0x140013aac  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ab3  lea     rax, WPP_GLOBAL_Control
0x140013aba  cmp     rcx, rax
0x140013abd  jz      loc_140013D29
0x140013ac3  cmp     byte ptr [rcx+29h], 2
0x140013ac7  jb      loc_140013D29
0x140013acd  mov     edx, 82h
0x140013ad2  jmp     loc_140013D19
0x140013ad7  cmp     edx, 8
0x140013ada  jnz     short loc_140013B2E
0x140013adc  cmp     [rsi+1D8h], edx
0x140013ae2  jb      short loc_140013B03
0x140013ae4  mov     eax, [r15]
0x140013ae7  mov     rcx, [rsi+1C8h]
0x140013aee  mov     [rcx], eax
0x140013af0  mov     eax, [r15+4]
0x140013af4  mov     [rcx+4], eax
0x140013af7  add     dword ptr [rsi+1D8h], 0FFFFFFF8h
0x140013afe  jmp     loc_140013C3C
0x140013b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140013b0a  lea     rax, WPP_GLOBAL_Control
0x140013b11  cmp     rcx, rax
0x140013b14  jz      loc_140013CC5
0x140013b1a  cmp     byte ptr [rcx+29h], 2
0x140013b1e  jb      loc_140013CC5
0x140013b24  mov     edx, 80h
0x140013b29  jmp     loc_140013CB5
0x140013b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140013b35  lea     rax, WPP_GLOBAL_Control
0x140013b3c  cmp     rcx, rax
0x140013b3f  jz      loc_140013D29
0x140013b45  cmp     byte ptr [rcx+29h], 2
0x140013b49  jb      loc_140013D29
0x140013b4f  mov     edx, 81h
0x140013b54  jmp     loc_140013D19
0x140013b59  cmp     edx, 16h
0x140013b5c  jnz     short loc_140013BC8
0x140013b5e  cmp     dword ptr [rsi+1D8h], 18h
0x140013b65  jb      short loc_140013B9D
0x140013b67  mov     rax, [r15]
0x140013b6a  mov     rcx, [rsi+1C8h]
0x140013b71  mov     [rcx], rax
0x140013b74  mov     al, [r15+14h]
0x140013b78  mov     [rcx+14h], al
0x140013b7b  mov     al, [r15+15h]
0x140013b7f  mov     [rcx+15h], al
0x140013b82  mov     rax, [r15+8]
0x140013b86  mov     [rcx+8], rax
0x140013b8a  mov     eax, [r15+10h]
0x140013b8e  mov     [rcx+10h], eax
0x140013b91  add     dword ptr [rsi+1D8h], 0FFFFFFE8h
0x140013b98  jmp     loc_140013C3C
0x140013b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ba4  lea     rax, WPP_GLOBAL_Control
0x140013bab  cmp     rcx, rax
0x140013bae  jz      loc_140013CC5
0x140013bb4  cmp     byte ptr [rcx+29h], 2
0x140013bb8  jb      loc_140013CC5
0x140013bbe  mov     edx, 7Eh ; '~'
0x140013bc3  jmp     loc_140013CB5
0x140013bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140013bcf  lea     rax, WPP_GLOBAL_Control
0x140013bd6  cmp     rcx, rax
0x140013bd9  jz      loc_140013D29
0x140013bdf  cmp     byte ptr [rcx+29h], 2
0x140013be3  jb      loc_140013D29
0x140013be9  mov     edx, 7Fh
0x140013bee  jmp     loc_140013D19
0x140013bf3  cmp     edx, 24h ; '$'
0x140013bf6  jnz     loc_140013CFB
0x140013bfc  cmp     dword ptr [rsi+1D8h], 28h ; '('
0x140013c03  jb      loc_140013C97
0x140013c09  mov     rax, [r15+18h]
0x140013c0d  mov     rcx, [rsi+1C8h]
0x140013c14  mov     [rcx+18h], rax
0x140013c18  mov     rax, [r15]
0x140013c1b  mov     [rcx], rax
0x140013c1e  mov     eax, [r15+20h]
0x140013c22  mov     [rcx+20h], eax
0x140013c25  mov     rax, [r15+8]
0x140013c29  mov     [rcx+8], rax
0x140013c2d  mov     rax, [r15+10h]
0x140013c31  mov     [rcx+10h], rax
0x140013c35  add     dword ptr [rsi+1D8h], 0FFFFFFD8h
0x140013c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c43  lea     rax, WPP_GLOBAL_Control
0x140013c4a  cmp     rcx, rax
0x140013c4d  jz      short loc_140013C72
0x140013c4f  cmp     byte ptr [rcx+29h], 5
0x140013c53  jb      short loc_140013C72
0x140013c55  mov     eax, [r13+0Ch]
0x140013c59  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013c60  mov     rcx, [rcx+18h]
0x140013c64  mov     edx, 83h
0x140013c69  mov     [rsp+68h+var_48], eax
0x140013c6d  call    WPP_SF_dd
0x140013c72  mov     r9d, [r13+10h]
0x140013c76  mov     rdx, r14
0x140013c79  mov     r8d, [r13+0Ch]
0x140013c7d  mov     rcx, rbp
0x140013c80  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140013c85  lea     rcx, [rsp+68h+arg_20]
0x140013c8d  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140013c92  jmp     loc_140013DDD
0x140013c97  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c9e  lea     rax, WPP_GLOBAL_Control
0x140013ca5  cmp     rcx, rax
0x140013ca8  jz      short loc_140013CC5
0x140013caa  cmp     byte ptr [rcx+29h], 2
0x140013cae  jb      short loc_140013CC5
0x140013cb0  mov     edx, 7Ch ; '|'
0x140013cb5  mov     rcx, [rcx+18h]
0x140013cb9  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013cc0  call    WPP_SF_
0x140013cc5  xor     r9d, r9d
0x140013cc8  mov     r8d, 80000005h
0x140013cce  mov     rdx, r14
0x140013cd1  mov     rcx, rbp
0x140013cd4  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140013cd9  mov     rax, [rsp+68h+arg_18]
0x140013ce1  lea     rcx, [rsp+68h+arg_20]
0x140013ce9  mov     dword ptr [rax], 1
0x140013cef  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140013cf4  xor     ebx, ebx
0x140013cf6  jmp     loc_140013E42
0x140013cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d02  lea     rax, WPP_GLOBAL_Control
0x140013d09  cmp     rcx, rax
0x140013d0c  jz      short loc_140013D29
0x140013d0e  cmp     byte ptr [rcx+29h], 2
  ... truncated ...
```
