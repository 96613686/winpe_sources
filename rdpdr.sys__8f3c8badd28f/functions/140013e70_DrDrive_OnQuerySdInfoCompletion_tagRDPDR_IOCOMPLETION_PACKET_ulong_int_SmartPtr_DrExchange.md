# DrDrive::OnQuerySdInfoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140013e70`
- end: `0x140014355`
- name: `?OnQuerySdInfoCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `1253`
- prototype: `__int64(__int64, __int64, unsigned int, _DWORD *, ...)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x14000324c`
- `0x1400032c0`
- `0x1400065c0`
- `0x1400117e0`
- `0x140011870`
- `0x140011a2c`
- `0x140013e70`
- `0x140023cf0`
- `0x140024020`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140014127`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140014127`

## pseudocode

```c
__int64 DrDrive::OnQuerySdInfoCompletion(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, ...)
{
  __int64 v4; // rsi
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  __int64 v9; // r14
  PDEVICE_OBJECT v10; // rcx
  _DWORD *v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  void *v14; // r9
  __int64 v15; // rbx
  unsigned int v16; // edx
  va_list v17; // rcx
  RefCount *v18; // rcx
  ULONG v19; // eax
  __int64 v20; // rbx
  __int64 v22; // [rsp+30h] [rbp-48h] BYREF
  void *Src; // [rsp+38h] [rbp-40h]
  _DWORD *v24; // [rsp+88h] [rbp+10h]
  void *v25; // [rsp+88h] [rbp+10h]
  unsigned int v26; // [rsp+90h] [rbp+18h]
  unsigned int v27; // [rsp+90h] [rbp+18h]
  int v28; // [rsp+90h] [rbp+18h]
  RefCount *v30; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v30 = va_arg(va1, RefCount *);
  v26 = a3;
  v4 = (__int64)v30;
  v7 = -1073741434;
  v8 = *(_DWORD **)(*(_QWORD *)v30 + 32LL);
  v24 = v8;
  v9 = *((_QWORD *)v8 + 6);
  if ( a3 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_62:
    if ( v9 )
      DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_65;
  }
  if ( *(int *)(a2 + 12) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      a3 = v26;
    }
    if ( a3 < 0x15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      goto LABEL_62;
    }
    if ( v9 )
    {
      DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(a2 + 12), 0);
      goto LABEL_58;
    }
LABEL_57:
    DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_58;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v8 = v24;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        137,
        WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
        *(unsigned int *)(a2 + 16),
        v8[10]);
  }
  v11 = v24;
  v12 = v26 - 20;
  v27 = v12;
  v13 = *(_DWORD *)(a2 + 16) - v24[10];
  LODWORD(v30) = v13;
  if ( v12 > v13 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v12, v13);
    goto LABEL_62;
  }
  v14 = (void *)(a2 + 20);
  Src = (void *)(a2 + 20);
  if ( v9 )
  {
    v15 = *(_QWORD *)(*(_QWORD *)(v9 + 64) + 64LL);
    v22 = v15;
    if ( v15 )
      RefCount::AddRef((RefCount *)v15);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v11 = v24;
      v12 = v27;
      v13 = (unsigned int)v30;
    }
    if ( v12 < v13 || v11[10] )
    {
      v16 = *(_DWORD *)(a2 + 16);
      if ( *(_DWORD *)(v15 + 28) < v16 )
      {
        if ( !DrFile::AllocateBuffer((DrFile *)v15, v16) )
        {
          v7 = -1073741670;
          DrDevice::CompleteBusyExchange(a1, v4, -1073741670, 0);
          v17 = (va_list)&v22;
          *a4 = 0;
LABEL_49:
          SmartPtr<DrFile>::~SmartPtr<DrFile>(v17);
          goto LABEL_66;
        }
        v12 = v27;
      }
      memmove((void *)(*(_QWORD *)(v15 + 32) + (unsigned int)v24[10]), (const void *)(a2 + 20), v12);
      v24[10] += v27;
    }
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v22);
    v11 = v24;
    v14 = (void *)(a2 + 20);
    v12 = v27;
    v13 = (unsigned int)v30;
  }
  if ( v12 != v13 )
  {
    DrDevice::MarkIdle(v10, v4);
    DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
    v7 = 0;
LABEL_65:
    *a4 = 0;
    goto LABEL_66;
  }
  if ( !v9 )
    goto LABEL_57;
  v18 = *(RefCount **)(*(_QWORD *)(v9 + 64) + 64LL);
  v30 = v18;
  if ( v18 )
    RefCount::AddRef(v18);
  v28 = *(_DWORD *)(a2 + 16);
  v25 = *(void **)(v9 + 456);
  if ( v11[10] )
  {
    v14 = (void *)*((_QWORD *)v18 + 4);
    Src = v14;
  }
  v19 = RtlLengthSecurityDescriptor(v14);
  v20 = v19;
  if ( v28 != v19 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    v7 = -1073741434;
    DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    va_copy(v17, va);
    *a4 = 1;
    goto LABEL_49;
  }
  if ( *(_DWORD *)(v9 + 472) < v19 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    *(_QWORD *)(v9 + 184) = v20;
    *(_DWORD *)(v9 + 176) = -2147483643;
    DrDevice::CompleteBusyExchange(a1, v4, -2147483643, v20);
    *a4 = 1;
    SmartPtr<DrFile>::~SmartPtr<DrFile>((RefCount **)va);
    goto LABEL_44;
  }
  memmove(v25, Src, v19);
  *(_DWORD *)(v9 + 472) -= v20;
  DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(a2 + 12), *(_DWORD *)(a2 + 16));
  SmartPtr<DrFile>::~SmartPtr<DrFile>((RefCount **)va);
LABEL_58:
  *a4 = 1;
LABEL_44:
  v7 = 0;
LABEL_66:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(v4);
  return v7;
}

```

## disassembly

```asm
0x140013e70  mov     [rsp+arg_0], rbx
0x140013e75  mov     [rsp+arg_18], r9
0x140013e7a  mov     [rsp+arg_10], r8d
0x140013e7f  push    rbp
0x140013e80  push    rsi
0x140013e81  push    rdi
0x140013e82  push    r12
0x140013e84  push    r13
0x140013e86  push    r14
0x140013e88  push    r15
0x140013e8a  sub     rsp, 40h
0x140013e8e  mov     rsi, [rsp+78h+arg_20]
0x140013e96  mov     r13, rdx
0x140013e99  mov     rbp, rcx
0x140013e9c  mov     ebx, 0C0000186h
0x140013ea1  mov     rax, [rsi]
0x140013ea4  mov     rax, [rax+20h]
0x140013ea8  mov     [rsp+78h+arg_8], rax
0x140013eb0  mov     r14, [rax+30h]
0x140013eb4  cmp     r8d, 14h
0x140013eb8  jnb     short loc_140013EEF
0x140013eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ec1  lea     r15, WPP_GLOBAL_Control
0x140013ec8  cmp     rcx, r15
0x140013ecb  jz      short loc_140013EE8
0x140013ecd  cmp     byte ptr [rcx+29h], 2
0x140013ed1  jb      short loc_140013EE8
0x140013ed3  mov     rcx, [rcx+18h]
0x140013ed7  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013ede  mov     edx, 87h
0x140013ee3  call    WPP_SF_
0x140013ee8  xor     edi, edi
0x140013eea  jmp     loc_14001430B
0x140013eef  xor     edi, edi
0x140013ef1  cmp     [rdx+0Ch], edi
0x140013ef4  jl      loc_140014272
0x140013efa  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f01  lea     r15, WPP_GLOBAL_Control
0x140013f08  lea     r12, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013f0f  cmp     rcx, r15
0x140013f12  jz      short loc_140013F61
0x140013f14  cmp     byte ptr [rcx+29h], 5
0x140013f18  jb      short loc_140013F33
0x140013f1a  mov     rcx, [rcx+18h]
0x140013f1e  mov     edx, 88h
0x140013f23  mov     r8, r12
0x140013f26  call    WPP_SF_
0x140013f2b  mov     rax, [rsp+78h+arg_8]
0x140013f33  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f3a  cmp     rcx, r15
0x140013f3d  jz      short loc_140013F61
0x140013f3f  cmp     byte ptr [rcx+29h], 5
0x140013f43  jb      short loc_140013F61
0x140013f45  mov     eax, [rax+28h]
0x140013f48  mov     edx, 89h
0x140013f4d  mov     r9d, [r13+10h]
0x140013f51  mov     r8, r12
0x140013f54  mov     rcx, [rcx+18h]
0x140013f58  mov     [rsp+78h+var_58], eax
0x140013f5c  call    WPP_SF_dd
0x140013f61  mov     eax, [rsp+78h+arg_10]
0x140013f68  mov     rdx, [rsp+78h+arg_8]
0x140013f70  add     eax, 0FFFFFFECh
0x140013f73  mov     r8d, [r13+10h]
0x140013f77  mov     [rsp+78h+arg_10], eax
0x140013f7e  sub     r8d, [rdx+28h]
0x140013f82  mov     dword ptr [rsp+78h+arg_20], r8d
0x140013f8a  cmp     eax, r8d
0x140013f8d  jbe     short loc_140013FC7
0x140013f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f96  cmp     rcx, r15
0x140013f99  jz      loc_14001430B
0x140013f9f  cmp     byte ptr [rcx+29h], 2
0x140013fa3  jb      loc_14001430B
0x140013fa9  mov     rcx, [rcx+18h]
0x140013fad  mov     edx, 8Ah
0x140013fb2  mov     [rsp+78h+var_58], r8d
0x140013fb7  mov     r9d, eax
0x140013fba  mov     r8, r12
0x140013fbd  call    WPP_SF_dd
0x140013fc2  jmp     loc_14001430B
0x140013fc7  lea     r9, [r13+14h]
0x140013fcb  mov     [rsp+78h+Src], r9
0x140013fd0  test    r14, r14
0x140013fd3  jz      loc_1400140D0
0x140013fd9  mov     rbx, [r14+40h]
0x140013fdd  mov     rbx, [rbx+40h]
0x140013fe1  mov     [rsp+78h+var_48], rbx
0x140013fe6  test    rbx, rbx
0x140013fe9  jz      short loc_140013FF3
0x140013feb  mov     rcx, rbx; this
0x140013fee  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140013ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ffa  cmp     rcx, r15
0x140013ffd  jz      short loc_14001402D
0x140013fff  cmp     byte ptr [rcx+29h], 5
0x140014003  jb      short loc_14001402D
0x140014005  mov     rcx, [rcx+18h]
0x140014009  mov     edx, 8Bh
0x14001400e  mov     r8, r12
0x140014011  call    WPP_SF_
0x140014016  mov     rdx, [rsp+78h+arg_8]
0x14001401e  mov     eax, [rsp+78h+arg_10]
0x140014025  mov     r8d, dword ptr [rsp+78h+arg_20]
0x14001402d  cmp     eax, r8d
0x140014030  jb      short loc_140014037
0x140014032  cmp     [rdx+28h], edi
0x140014035  jz      short loc_1400140AB
0x140014037  mov     edx, [r13+10h]; unsigned int
0x14001403b  cmp     [rbx+1Ch], edx
0x14001403e  jnb     short loc_14001407E
0x140014040  mov     rcx, rbx; this
0x140014043  call    ?AllocateBuffer@DrFile@@QEAAPEAEK@Z; DrFile::AllocateBuffer(ulong)
0x140014048  test    rax, rax
0x14001404b  jnz     short loc_140014077
0x14001404d  mov     ebx, 0C000009Ah
0x140014052  xor     r9d, r9d
0x140014055  mov     r8d, ebx
0x140014058  mov     rdx, rsi
0x14001405b  mov     rcx, rbp
0x14001405e  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140014063  mov     rax, [rsp+78h+arg_18]
0x14001406b  lea     rcx, [rsp+78h+var_48]
0x140014070  mov     [rax], edi
0x140014072  jmp     loc_140014242
0x140014077  mov     eax, [rsp+78h+arg_10]
0x14001407e  mov     r8d, eax; Size
0x140014081  lea     rdx, [r13+14h]; Src
0x140014085  mov     rax, [rsp+78h+arg_8]
0x14001408d  mov     ecx, [rax+28h]
0x140014090  add     rcx, [rbx+20h]; void *
0x140014094  call    memmove
0x140014099  mov     rax, [rsp+78h+arg_8]
0x1400140a1  mov     ecx, [rsp+78h+arg_10]
0x1400140a8  add     [rax+28h], ecx
0x1400140ab  lea     rcx, [rsp+78h+var_48]
0x1400140b0  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400140b5  mov     rdx, [rsp+78h+arg_8]
0x1400140bd  lea     r9, [r13+14h]
0x1400140c1  mov     eax, [rsp+78h+arg_10]
0x1400140c8  mov     r8d, dword ptr [rsp+78h+arg_20]
0x1400140d0  cmp     eax, r8d
0x1400140d3  jnz     loc_14001424C
0x1400140d9  test    r14, r14
0x1400140dc  jz      loc_1400142CA
0x1400140e2  mov     rcx, [r14+40h]
0x1400140e6  mov     rcx, [rcx+40h]; this
0x1400140ea  mov     [rsp+78h+arg_20], rcx
0x1400140f2  test    rcx, rcx
0x1400140f5  jz      short loc_1400140FC
0x1400140f7  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400140fc  mov     eax, [r13+10h]
0x140014100  mov     [rsp+78h+arg_10], eax
0x140014107  mov     rax, [r14+1C8h]
0x14001410e  mov     [rsp+78h+arg_8], rax
0x140014116  cmp     [rdx+28h], edi
0x140014119  jz      short loc_140014124
0x14001411b  mov     r9, [rcx+20h]
0x14001411f  mov     [rsp+78h+Src], r9
0x140014124  mov     rcx, r9; SecurityDescriptor
0x140014127  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001412e  nop     dword ptr [rax+rax+00h]
0x140014133  mov     ebx, eax
0x140014135  cmp     [rsp+78h+arg_10], eax
0x14001413c  jnz     loc_1400141F3
0x140014142  cmp     [r14+1D8h], ebx
0x140014149  jb      short loc_14001418C
0x14001414b  mov     rdx, [rsp+78h+Src]; Src
0x140014150  mov     r8d, ebx; Size
0x140014153  mov     rcx, [rsp+78h+arg_8]; void *
0x14001415b  call    memmove
0x140014160  sub     [r14+1D8h], ebx
0x140014167  mov     rdx, rsi
0x14001416a  mov     r9d, [r13+10h]
0x14001416e  mov     rcx, rbp
0x140014171  mov     r8d, [r13+0Ch]
0x140014175  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x14001417a  lea     rcx, [rsp+78h+arg_20]
0x140014182  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014187  jmp     loc_1400142D5
0x14001418c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014193  cmp     rcx, r15
0x140014196  jz      short loc_1400141AF
0x140014198  cmp     byte ptr [rcx+29h], 2
0x14001419c  jb      short loc_1400141AF
0x14001419e  mov     rcx, [rcx+18h]
0x1400141a2  mov     edx, 8Ch
0x1400141a7  mov     r8, r12
0x1400141aa  call    WPP_SF_
0x1400141af  mov     r8d, 80000005h
0x1400141b5  mov     [r14+0B8h], rbx
0x1400141bc  mov     r9d, ebx
0x1400141bf  mov     [r14+0B0h], r8d
0x1400141c6  mov     rdx, rsi
0x1400141c9  mov     rcx, rbp
0x1400141cc  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400141d1  mov     rax, [rsp+78h+arg_18]
0x1400141d9  lea     rcx, [rsp+78h+arg_20]
0x1400141e1  mov     dword ptr [rax], 1
0x1400141e7  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400141ec  mov     ebx, edi
0x1400141ee  jmp     loc_140014332
0x1400141f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141fa  cmp     rcx, r15
0x1400141fd  jz      short loc_140014216
0x1400141ff  cmp     byte ptr [rcx+29h], 2
0x140014203  jb      short loc_140014216
0x140014205  mov     rcx, [rcx+18h]
0x140014209  mov     edx, 8Dh
0x14001420e  mov     r8, r12
0x140014211  call    WPP_SF_
0x140014216  mov     ebx, 0C0000186h
0x14001421b  xor     r9d, r9d
0x14001421e  mov     r8d, ebx
0x140014221  mov     rdx, rsi
0x140014224  mov     rcx, rbp
0x140014227  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x14001422c  mov     rax, [rsp+78h+arg_18]
0x140014234  lea     rcx, [rsp+78h+arg_20]
0x14001423c  mov     dword ptr [rax], 1
0x140014242  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140014247  jmp     loc_140014332
0x14001424c  mov     rdx, rsi
0x14001424f  call    ?MarkIdle@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::MarkIdle(SmartPtr<DrExchange> &)
0x140014254  mov     rcx, [rbp+20h]
0x140014258  xor     r8d, r8d; unsigned int
0x14001425b  mov     rcx, [rcx+2E0h]; this
0x140014262  lea     edx, [r8+14h]; unsigned int
0x140014266  call    ?ReadMore@DrSession@@QEAAHKK@Z; DrSession::ReadMore(ulong,ulong)
0x14001426b  mov     ebx, edi
0x14001426d  jmp     loc_140014328
0x140014272  mov     rcx, cs:WPP_GLOBAL_Control
0x140014279  lea     r15, WPP_GLOBAL_Control
0x140014280  lea     r12, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140014287  cmp     rcx, r15
0x14001428a  jz      short loc_1400142AB
0x14001428c  cmp     byte ptr [rcx+29h], 5
0x140014290  jb      short loc_1400142AB
0x140014292  mov     rcx, [rcx+18h]
0x140014296  mov     edx, 8Eh
0x14001429b  mov     r8, r12
0x14001429e  call    WPP_SF_
0x1400142a3  mov     r8d, [rsp+78h+arg_10]
0x1400142ab  cmp     r8d, 15h
0x1400142af  jb      short loc_1400142E8
0x1400142b1  test    r14, r14
0x1400142b4  jz      short loc_1400142CA
0x1400142b6  mov     r8d, [r13+0Ch]
0x1400142ba  xor     r9d, r9d
0x1400142bd  mov     rdx, rsi
0x1400142c0  mov     rcx, rbp
0x1400142c3  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400142c8  jmp     short loc_1400142D5
0x1400142ca  mov     rdx, rsi
0x1400142cd  mov     rcx, rbp
0x1400142d0  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x1400142d5  mov     rax, [rsp+78h+arg_18]
0x1400142dd  mov     dword ptr [rax], 1
0x1400142e3  jmp     loc_1400141EC
0x1400142e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142ef  cmp     rcx, r15
0x1400142f2  jz      short loc_14001430B
0x1400142f4  cmp     byte ptr [rcx+29h], 2
0x1400142f8  jb      short loc_14001430B
0x1400142fa  mov     rcx, [rcx+18h]
0x1400142fe  mov     edx, 8Fh
0x140014303  mov     r8, r12
0x140014306  call    WPP_SF_
0x14001430b  mov     rdx, rsi
0x14001430e  mov     rcx, rbp
0x140014311  test    r14, r14
0x140014314  jz      short loc_140014323
0x140014316  xor     r9d, r9d
0x140014319  mov     r8d, ebx
0x14001431c  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140014321  jmp     short loc_140014328
0x140014323  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140014328  mov     rax, [rsp+78h+arg_18]
0x140014330  mov     [rax], edi
0x140014332  mov     rcx, rsi
0x140014335  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001433a  mov     eax, ebx
0x14001433c  mov     rbx, [rsp+78h+arg_0]
0x140014344  add     rsp, 40h
0x140014348  pop     r15
0x14001434a  pop     r14
0x14001434c  pop     r13
0x14001434e  pop     r12
0x140014350  pop     rdi
0x140014351  pop     rsi
0x140014352  pop     rbp
0x140014353  retn
```
