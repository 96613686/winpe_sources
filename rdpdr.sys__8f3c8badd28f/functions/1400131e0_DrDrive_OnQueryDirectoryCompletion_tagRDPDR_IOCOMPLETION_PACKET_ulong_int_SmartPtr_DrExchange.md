# DrDrive::OnQueryDirectoryCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x1400131e0`
- end: `0x1400137b1`
- name: `?OnQueryDirectoryCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `1489`
- prototype: `__int64(__int64, __int64, unsigned int, _DWORD *, ...)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x140003398`
- `0x14000353c`
- `0x1400065c0`
- `0x1400117e0`
- `0x140011870`
- `0x140011a2c`
- `0x14001285c`
- `0x140012a3c`
- `0x140012bf4`
- `0x140012db0`
- `0x1400131e0`
- `0x1400168f0`
- `0x140016b1c`
- `0x140023cf0`
- `0x140024020`

## pseudocode

```c
__int64 DrDrive::OnQueryDirectoryCompletion(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, ...)
{
  __int64 v4; // r14
  __int64 v8; // rax
  struct _DEVICE_OBJECT *v9; // r9
  struct _RX_CONTEXT *v10; // r13
  unsigned int v11; // esi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // eax
  int v15; // r10d
  unsigned __int8 *v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rsi
  unsigned int v19; // edx
  __int64 v20; // rbx
  enum _FILE_INFORMATION_CLASS Flags; // r12d
  unsigned int v22; // esi
  struct tagRDPDR_QUERYDIR_CACHE_ENTRY *CurrentQueryDirCacheEntry; // rax
  DrDrive *v24; // rcx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // r9d
  int v28; // r8d
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // edi
  unsigned int v33; // r13d
  __int64 v34; // rdx
  __int64 v35; // rcx
  int v37; // [rsp+50h] [rbp-20h]
  __int64 v38; // [rsp+58h] [rbp-18h]
  unsigned __int8 *v39; // [rsp+60h] [rbp-10h]
  __int64 v40; // [rsp+68h] [rbp-8h] BYREF
  int v42; // [rsp+C0h] [rbp+50h] BYREF
  _DWORD *v43; // [rsp+C8h] [rbp+58h]
  __int64 v44; // [rsp+D0h] [rbp+60h] BYREF
  va_list va; // [rsp+D0h] [rbp+60h]
  va_list va1; // [rsp+D8h] [rbp+68h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v44 = va_arg(va1, _QWORD);
  v43 = a4;
  v4 = v44;
  v8 = *(_QWORD *)(*(_QWORD *)v44 + 32LL);
  v38 = v8;
  v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, a3);
    v8 = v38;
    v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
  }
  v10 = *(struct _RX_CONTEXT **)(v8 + 48);
  v11 = -1073741434;
  if ( a3 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_86:
    if ( v10 )
      DrDevice::CompleteBusyExchange(a1, v4, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, v4);
    goto LABEL_89;
  }
  if ( *(int *)(a2 + 12) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    if ( a3 < 0x15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      goto LABEL_86;
    }
    v34 = v4;
    v35 = a1;
    if ( v10 )
    {
      DrDevice::CompleteBusyExchange(a1, v4, *(_DWORD *)(a2 + 12), 0);
      goto LABEL_75;
    }
LABEL_74:
    DrDevice::DiscardBusyExchange(v35, v34);
LABEL_75:
    v11 = 0;
    *v43 = 1;
    goto LABEL_90;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
      v8 = v38;
      v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        82,
        WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
        *(unsigned int *)(a2 + 16),
        *(_DWORD *)(v8 + 40));
      v9 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    }
  }
  v13 = (unsigned int)(*(_DWORD *)(a2 + 16) - *(_DWORD *)(v38 + 40));
  v14 = a3 - 20;
  LODWORD(v44) = v13;
  v42 = a3 - 20;
  if ( a3 - 20 > (unsigned int)v13 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_83886b54412a34bbe371408c37660ab5_Traceguids, v14, v13);
    goto LABEL_86;
  }
  v15 = *(_DWORD *)(a2 + 12);
  v16 = (unsigned __int8 *)(a2 + 20);
  v39 = (unsigned __int8 *)(a2 + 20);
  v37 = v15;
  if ( !v10 )
  {
    v18 = v38;
    goto LABEL_35;
  }
  v17 = *(_QWORD *)&v10->pFobx->OffsetOfNextEaToReturn;
  v40 = v17;
  if ( v17 )
    RefCount::AddRef((RefCount *)v17);
  if ( WPP_GLOBAL_Control != v9 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    v14 = v42;
    LODWORD(v13) = v44;
  }
  v18 = v38;
  if ( v14 >= (unsigned int)v13 && !*(_DWORD *)(v38 + 40) )
  {
LABEL_33:
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v40);
    v14 = v42;
    v16 = (unsigned __int8 *)(a2 + 20);
    v13 = (unsigned int)v44;
    v15 = v37;
LABEL_35:
    if ( v14 != (_DWORD)v13 )
    {
      DrDevice::MarkIdle(v12, v4);
      DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
      v11 = 0;
LABEL_89:
      *v43 = 0;
      goto LABEL_90;
    }
    if ( v10 )
    {
      v20 = *(_QWORD *)&v10->pFobx->OffsetOfNextEaToReturn;
      v40 = v20;
      if ( v20 )
        RefCount::AddRef((RefCount *)v20);
      Flags = v10->LowIoContext.ParamsFor.Locks.Flags;
      v42 = -1073741823;
      LODWORD(v44) = 0;
      if ( *(_DWORD *)(v18 + 40) )
      {
        v16 = *(unsigned __int8 **)(v20 + 32);
        v39 = v16;
      }
      v22 = *(_DWORD *)(a2 + 16);
      if ( *(_DWORD *)(v20 + 48) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_DDd(
            WPP_GLOBAL_Control->AttachedDevice,
            v16,
            v13,
            *(unsigned int *)(v20 + 24),
            Flags,
            *(_DWORD *)(a2 + 16));
          v16 = v39;
        }
        if ( !(unsigned int)DrFile::PopulateQueryDirectoryCache((DrFile *)v20, v16, v22, Flags) )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_56;
          v26 = 87;
          goto LABEL_55;
        }
        CurrentQueryDirCacheEntry = DrFile::GetCurrentQueryDirCacheEntry((DrFile *)v20, Flags);
        if ( !CurrentQueryDirCacheEntry )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_56;
          v26 = 86;
          goto LABEL_55;
        }
        v16 = (unsigned __int8 *)CurrentQueryDirCacheEntry + 8;
        v15 = *((_DWORD *)CurrentQueryDirCacheEntry + 1);
        v22 = *(_DWORD *)CurrentQueryDirCacheEntry - 8;
        v37 = v15;
      }
      if ( Flags == FileDirectoryInformation )
      {
        v29 = DrDrive::OnFileDirectoryInformation(
                (DrDrive *)(unsigned int)(Flags - 1),
                v10,
                v15,
                v16,
                v22,
                &v42,
                (unsigned int *)va);
      }
      else if ( Flags == FileFullDirectoryInformation )
      {
        v29 = DrDrive::OnFileFullDirectoryInformation(
                (DrDrive *)(unsigned int)(Flags - 2),
                v10,
                v15,
                v16,
                v22,
                &v42,
                (unsigned int *)va);
      }
      else
      {
        v24 = (DrDrive *)(unsigned int)(Flags - 3);
        if ( Flags == FileBothDirectoryInformation )
        {
          v29 = DrDrive::OnFileBothDirectoryInformation(v24, v10, v15, v16, v22, &v42, (unsigned int *)va);
        }
        else
        {
          if ( Flags != FileNamesInformation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_56;
            v26 = 88;
LABEL_55:
            WPP_SF_(v25->AttachedDevice, v26, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_56:
            v11 = -1073741434;
            v27 = 0;
            v28 = -1073741434;
LABEL_57:
            DrDevice::CompleteBusyExchange(a1, v4, v28, v27);
            *v43 = 1;
            goto LABEL_58;
          }
          v29 = DrDrive::OnFileNamesInformation(v24, v10, v15, v16, v22, &v42, (unsigned int *)va);
        }
      }
      v11 = v29;
      v32 = v42;
      v33 = v44;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_DDDDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v30,
          v31,
          *(unsigned int *)(v20 + 24),
          Flags,
          v29,
          v37,
          v42,
          v44);
      v27 = v33;
      v28 = v32;
      goto LABEL_57;
    }
    v34 = v4;
    v35 = a1;
    goto LABEL_74;
  }
  v19 = *(_DWORD *)(a2 + 16);
  if ( *(_DWORD *)(v17 + 28) >= v19 )
  {
LABEL_32:
    memmove((void *)(*(_QWORD *)(v17 + 32) + *(unsigned int *)(v38 + 40)), (const void *)(a2 + 20), v14);
    *(_DWORD *)(v38 + 40) += v42;
    goto LABEL_33;
  }
  if ( DrFile::AllocateBuffer((DrFile *)v17, v19) )
  {
    v14 = v42;
    goto LABEL_32;
  }
  v11 = -1073741670;
  DrDevice::CompleteBusyExchange(a1, v4, -1073741670, 0);
  *v43 = 0;
LABEL_58:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v40);
LABEL_90:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(v4);
  return v11;
}

```

## disassembly

```asm
0x1400131e0  mov     [rsp-38h+arg_0], rbx
0x1400131e5  mov     [rsp-38h+arg_18], r9
0x1400131ea  mov     [rsp-38h+arg_8], rdx
0x1400131ef  push    rbp
0x1400131f0  push    rsi
0x1400131f1  push    rdi
0x1400131f2  push    r12
0x1400131f4  push    r13
0x1400131f6  push    r14
0x1400131f8  push    r15
0x1400131fa  mov     rbp, rsp
0x1400131fd  sub     rsp, 70h
0x140013201  mov     r14, [rbp+arg_20]
0x140013205  mov     ebx, r8d
0x140013208  mov     r12, rdx
0x14001320b  mov     r15, rcx
0x14001320e  mov     rax, [r14]
0x140013211  mov     rax, [rax+20h]
0x140013215  mov     [rbp+var_18], rax
0x140013219  mov     rcx, cs:WPP_GLOBAL_Control
0x140013220  lea     r9, WPP_GLOBAL_Control
0x140013227  cmp     rcx, r9
0x14001322a  jz      short loc_140013255
0x14001322c  cmp     byte ptr [rcx+29h], 5
0x140013230  jb      short loc_140013255
0x140013232  mov     rcx, [rcx+18h]
0x140013236  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x14001323d  mov     edx, 4Fh ; 'O'
0x140013242  mov     r9d, ebx
0x140013245  call    WPP_SF_d
0x14001324a  mov     rax, [rbp+var_18]
0x14001324e  lea     r9, WPP_GLOBAL_Control
0x140013255  mov     r13, [rax+30h]
0x140013259  mov     esi, 0C0000186h
0x14001325e  cmp     ebx, 14h
0x140013261  jnb     short loc_140013291
0x140013263  mov     rcx, cs:WPP_GLOBAL_Control
0x14001326a  cmp     rcx, r9
0x14001326d  jz      short loc_14001328A
0x14001326f  cmp     byte ptr [rcx+29h], 2
0x140013273  jb      short loc_14001328A
0x140013275  mov     rcx, [rcx+18h]
0x140013279  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013280  mov     edx, 50h ; 'P'
0x140013285  call    WPP_SF_
0x14001328a  xor     edi, edi
0x14001328c  jmp     loc_14001376B
0x140013291  xor     edi, edi
0x140013293  cmp     [r12+0Ch], edi
0x140013298  jl      loc_1400136F4
0x14001329e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132a5  cmp     rcx, r9
0x1400132a8  jz      short loc_140013308
0x1400132aa  cmp     byte ptr [rcx+29h], 5
0x1400132ae  jb      short loc_1400132CE
0x1400132b0  mov     rcx, [rcx+18h]
0x1400132b4  lea     edx, [rdi+51h]
0x1400132b7  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400132be  call    WPP_SF_
0x1400132c3  mov     rax, [rbp+var_18]
0x1400132c7  lea     r9, WPP_GLOBAL_Control
0x1400132ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132d5  cmp     rcx, r9
0x1400132d8  jz      short loc_140013308
0x1400132da  cmp     byte ptr [rcx+29h], 5
0x1400132de  jb      short loc_140013308
0x1400132e0  mov     eax, [rax+28h]
0x1400132e3  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400132ea  mov     r9d, [r12+10h]
0x1400132ef  mov     edx, 52h ; 'R'
0x1400132f4  mov     rcx, [rcx+18h]
0x1400132f8  mov     [rsp+70h+var_50], eax
0x1400132fc  call    WPP_SF_dd
0x140013301  lea     r9, WPP_GLOBAL_Control
0x140013308  mov     rax, [rbp+var_18]
0x14001330c  mov     r8d, [r12+10h]
0x140013311  sub     r8d, [rax+28h]
0x140013315  lea     eax, [rbx-14h]
0x140013318  mov     dword ptr [rbp+arg_20], r8d
0x14001331c  mov     [rbp+arg_10], eax
0x14001331f  cmp     eax, r8d
0x140013322  jbe     short loc_140013360
0x140013324  mov     rcx, cs:WPP_GLOBAL_Control
0x14001332b  cmp     rcx, r9
0x14001332e  jz      loc_14001376B
0x140013334  cmp     byte ptr [rcx+29h], 2
0x140013338  jb      loc_14001376B
0x14001333e  mov     rcx, [rcx+18h]
0x140013342  mov     edx, 53h ; 'S'
0x140013347  mov     [rsp+70h+var_50], r8d
0x14001334c  mov     r9d, eax
0x14001334f  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013356  call    WPP_SF_dd
0x14001335b  jmp     loc_14001376B
0x140013360  mov     r10d, [r12+0Ch]
0x140013365  lea     rdx, [r12+14h]
0x14001336a  mov     [rbp+var_10], rdx
0x14001336e  mov     [rbp+var_20], r10d
0x140013372  test    r13, r13
0x140013375  jz      loc_14001343F
0x14001337b  mov     rbx, [r13+40h]
0x14001337f  mov     rbx, [rbx+40h]
0x140013383  mov     [rbp+var_8], rbx
0x140013387  test    rbx, rbx
0x14001338a  jz      short loc_140013394
0x14001338c  mov     rcx, rbx; this
0x14001338f  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140013394  mov     rcx, cs:WPP_GLOBAL_Control
0x14001339b  cmp     rcx, r9
0x14001339e  jz      short loc_1400133C2
0x1400133a0  cmp     byte ptr [rcx+29h], 5
0x1400133a4  jb      short loc_1400133C2
0x1400133a6  mov     rcx, [rcx+18h]
0x1400133aa  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400133b1  mov     edx, 54h ; 'T'
0x1400133b6  call    WPP_SF_
0x1400133bb  mov     eax, [rbp+arg_10]
0x1400133be  mov     r8d, dword ptr [rbp+arg_20]
0x1400133c2  mov     rsi, [rbp+var_18]
0x1400133c6  cmp     eax, r8d
0x1400133c9  jb      short loc_1400133D0
0x1400133cb  cmp     [rsi+28h], edi
0x1400133ce  jz      short loc_140013425
0x1400133d0  mov     edx, [r12+10h]; unsigned int
0x1400133d5  cmp     [rbx+1Ch], edx
0x1400133d8  jnb     short loc_14001340B
0x1400133da  mov     rcx, rbx; this
0x1400133dd  call    ?AllocateBuffer@DrFile@@QEAAPEAEK@Z; DrFile::AllocateBuffer(ulong)
0x1400133e2  test    rax, rax
0x1400133e5  jnz     short loc_140013408
0x1400133e7  mov     esi, 0C000009Ah
0x1400133ec  xor     r9d, r9d
0x1400133ef  mov     r8d, esi
0x1400133f2  mov     rdx, r14
0x1400133f5  mov     rcx, r15
0x1400133f8  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400133fd  mov     rax, [rbp+arg_18]
0x140013401  mov     [rax], edi
0x140013403  jmp     loc_14001357B
0x140013408  mov     eax, [rbp+arg_10]
0x14001340b  mov     ecx, [rsi+28h]
0x14001340e  lea     rdx, [r12+14h]; Src
0x140013413  add     rcx, [rbx+20h]; void *
0x140013417  mov     r8d, eax; Size
0x14001341a  call    memmove
0x14001341f  mov     eax, [rbp+arg_10]
0x140013422  add     [rsi+28h], eax
0x140013425  lea     rcx, [rbp+var_8]
0x140013429  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001342e  mov     eax, [rbp+arg_10]
0x140013431  mov     rdx, [rbp+var_10]
0x140013435  mov     r8d, dword ptr [rbp+arg_20]
0x140013439  mov     r10d, [rbp+var_20]
0x14001343d  jmp     short loc_140013443
0x14001343f  mov     rsi, [rbp+var_18]
0x140013443  cmp     eax, r8d
0x140013446  jnz     loc_1400136CE
0x14001344c  test    r13, r13
0x14001344f  jz      loc_1400136B2
0x140013455  mov     rbx, [r13+40h]
0x140013459  mov     rbx, [rbx+40h]
0x14001345d  mov     [rbp+var_8], rbx
0x140013461  test    rbx, rbx
0x140013464  jz      short loc_14001346E
0x140013466  mov     rcx, rbx; this
0x140013469  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001346e  mov     r12d, [r13+1C0h]
0x140013475  mov     [rbp+arg_10], 0C0000001h
0x14001347c  mov     dword ptr [rbp+arg_20], edi
0x14001347f  cmp     [rsi+28h], edi
0x140013482  jz      short loc_14001348C
0x140013484  mov     rdx, [rbx+20h]
0x140013488  mov     [rbp+var_10], rdx
0x14001348c  mov     rsi, [rbp+arg_8]
0x140013490  mov     esi, [rsi+10h]
0x140013493  cmp     [rbx+30h], edi
0x140013496  jz      short loc_140013506
0x140013498  mov     rcx, cs:WPP_GLOBAL_Control
0x14001349f  lea     rax, WPP_GLOBAL_Control
0x1400134a6  cmp     rcx, rax
0x1400134a9  jz      short loc_1400134CB
0x1400134ab  cmp     byte ptr [rcx+29h], 5
0x1400134af  jb      short loc_1400134CB
0x1400134b1  mov     r9d, [rbx+18h]
0x1400134b5  mov     rcx, [rcx+18h]
0x1400134b9  mov     dword ptr [rsp+70h+var_48], esi
0x1400134bd  mov     [rsp+70h+var_50], r12d
0x1400134c2  call    WPP_SF_DDd
0x1400134c7  mov     rdx, [rbp+var_10]; unsigned __int8 *
0x1400134cb  mov     r9d, r12d; enum _FILE_INFORMATION_CLASS
0x1400134ce  mov     r8d, esi; unsigned int
0x1400134d1  mov     rcx, rbx; this
0x1400134d4  call    ?PopulateQueryDirectoryCache@DrFile@@QEAAHPEAEKW4_FILE_INFORMATION_CLASS@@@Z; DrFile::PopulateQueryDirectoryCache(uchar *,ulong,_FILE_INFORMATION_CLASS)
0x1400134d9  test    eax, eax
0x1400134db  jz      loc_1400135A9
0x1400134e1  mov     edx, r12d; enum _FILE_INFORMATION_CLASS
0x1400134e4  mov     rcx, rbx; this
0x1400134e7  call    ?GetCurrentQueryDirCacheEntry@DrFile@@QEAAPEAUtagRDPDR_QUERYDIR_CACHE_ENTRY@@W4_FILE_INFORMATION_CLASS@@@Z; DrFile::GetCurrentQueryDirCacheEntry(_FILE_INFORMATION_CLASS)
0x1400134ec  test    rax, rax
0x1400134ef  jz      loc_140013589
0x1400134f5  mov     esi, [rax]
0x1400134f7  lea     rdx, [rax+8]
0x1400134fb  mov     r10d, [rax+4]
0x1400134ff  sub     esi, 8
0x140013502  mov     [rbp+var_20], r10d
0x140013506  mov     ecx, r12d
0x140013509  sub     ecx, 1; this
0x14001350c  jz      loc_14001363B
0x140013512  sub     ecx, 1; this
0x140013515  jz      loc_140013615
0x14001351b  sub     ecx, 1; this
0x14001351e  jz      loc_1400135EF
0x140013524  cmp     ecx, 9
0x140013527  jz      loc_1400135C9
0x14001352d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013534  lea     rax, WPP_GLOBAL_Control
0x14001353b  cmp     rcx, rax
0x14001353e  jz      short loc_14001355B
0x140013540  cmp     byte ptr [rcx+29h], 2
0x140013544  jb      short loc_14001355B
0x140013546  mov     edx, 58h ; 'X'
0x14001354b  mov     rcx, [rcx+18h]
0x14001354f  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013556  call    WPP_SF_
0x14001355b  mov     esi, 0C0000186h
0x140013560  xor     r9d, r9d
0x140013563  mov     r8d, esi
0x140013566  mov     rdx, r14
0x140013569  mov     rcx, r15
0x14001356c  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140013571  mov     rax, [rbp+arg_18]
0x140013575  mov     dword ptr [rax], 1
0x14001357b  lea     rcx, [rbp+var_8]
0x14001357f  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140013584  jmp     loc_14001378E
0x140013589  mov     rcx, cs:WPP_GLOBAL_Control
0x140013590  lea     rax, WPP_GLOBAL_Control
0x140013597  cmp     rcx, rax
0x14001359a  jz      short loc_14001355B
0x14001359c  cmp     byte ptr [rcx+29h], 2
0x1400135a0  jb      short loc_14001355B
0x1400135a2  mov     edx, 56h ; 'V'
0x1400135a7  jmp     short loc_14001354B
0x1400135a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135b0  lea     rax, WPP_GLOBAL_Control
0x1400135b7  cmp     rcx, rax
0x1400135ba  jz      short loc_14001355B
0x1400135bc  cmp     byte ptr [rcx+29h], 2
0x1400135c0  jb      short loc_14001355B
0x1400135c2  mov     edx, 57h ; 'W'
0x1400135c7  jmp     short loc_14001354B
0x1400135c9  lea     rax, [rbp+arg_20]
0x1400135cd  mov     r9, rdx; unsigned __int8 *
0x1400135d0  mov     [rsp+70h+var_40], rax; unsigned int *
0x1400135d5  mov     r8d, r10d; int
0x1400135d8  lea     rax, [rbp+arg_10]
0x1400135dc  mov     rdx, r13; struct _RX_CONTEXT *
0x1400135df  mov     [rsp+70h+var_48], rax; int *
0x1400135e4  mov     [rsp+70h+var_50], esi; unsigned int
0x1400135e8  call    ?OnFileNamesInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileNamesInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x1400135ed  jmp     short loc_14001365F
0x1400135ef  lea     rax, [rbp+arg_20]
0x1400135f3  mov     r9, rdx; unsigned __int8 *
0x1400135f6  mov     [rsp+70h+var_40], rax; unsigned int *
0x1400135fb  mov     r8d, r10d; int
0x1400135fe  lea     rax, [rbp+arg_10]
0x140013602  mov     rdx, r13; struct _RX_CONTEXT *
0x140013605  mov     [rsp+70h+var_48], rax; int *
0x14001360a  mov     [rsp+70h+var_50], esi; unsigned int
0x14001360e  call    ?OnFileBothDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileBothDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x140013613  jmp     short loc_14001365F
0x140013615  lea     rax, [rbp+arg_20]
0x140013619  mov     r9, rdx; unsigned __int8 *
0x14001361c  mov     [rsp+70h+var_40], rax; unsigned int *
0x140013621  mov     r8d, r10d; int
0x140013624  lea     rax, [rbp+arg_10]
0x140013628  mov     rdx, r13; struct _RX_CONTEXT *
0x14001362b  mov     [rsp+70h+var_48], rax; int *
0x140013630  mov     [rsp+70h+var_50], esi; unsigned int
0x140013634  call    ?OnFileFullDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileFullDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x140013639  jmp     short loc_14001365F
0x14001363b  lea     rax, [rbp+arg_20]
0x14001363f  mov     r9, rdx; unsigned __int8 *
0x140013642  mov     [rsp+70h+var_40], rax; unsigned int *
0x140013647  mov     r8d, r10d; int
0x14001364a  lea     rax, [rbp+arg_10]
0x14001364e  mov     rdx, r13; struct _RX_CONTEXT *
0x140013651  mov     [rsp+70h+var_48], rax; int *
0x140013656  mov     [rsp+70h+var_50], esi; unsigned int
0x14001365a  call    ?OnFileDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z; DrDrive::OnFileDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)
0x14001365f  mov     esi, eax
0x140013661  mov     rcx, cs:WPP_GLOBAL_Control
0x140013668  lea     rax, WPP_GLOBAL_Control
0x14001366f  mov     edi, [rbp+arg_10]
0x140013672  mov     r13d, dword ptr [rbp+arg_20]
0x140013676  cmp     rcx, rax
0x140013679  jz      short loc_1400136A7
0x14001367b  cmp     byte ptr [rcx+29h], 5
0x14001367f  jb      short loc_1400136A7
0x140013681  mov     eax, [rbp+var_20]
  ... truncated ...
```
