# CCscScope::_TransitionSlowLinkOfflineIfRequired(ushort const *,unsigned __int64,unsigned __int64)

- ea: `0x180010ac8`
- end: `0x180010fdc`
- name: `?_TransitionSlowLinkOfflineIfRequired@CCscScope@@AEAAJPEBG_K1@Z`
- size: `1300`
- prototype: `int(CCscScope *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task`

## callers

- `0x18001a340`

## callees

- `0x18000d640`
- `0x18000f348`
- `0x18000f7f4`
- `0x180010ac8`
- `0x180010fe4`
- `0x18001101c`
- `0x180011070`
- `0x18002d740`
- `0x18002e8f4`
- `0x1800391b8`
- `0x18003c460`
- `0x18003c488`
- `0x18003c4e8`
- `0x18003c560`
- `0x18003c5ec`
- `0x18003cde4`
- `0x18003e928`
- `0x1800464f8`
- `0x18005acc0`
- `0x18005ad54`
- `0x18005ae78`
- `0x18005af88`
- `0x18005fb24`
- `0x180060018`
- `0x180089010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180010b4d`
- `OLEAUT32!__imp_VariantInit` at `0x180010b4d`
- `OLEAUT32!__imp_VariantClear` at `0x180010cde`
- `OLEAUT32!__imp_VariantClear` at `0x180010cde`
- `KERNEL32!lstrcmpiW` at `0x180010b77`
- `KERNEL32!lstrcmpiW` at `0x180010bf9`
- `KERNEL32!lstrcmpiW` at `0x180010b77`
- `KERNEL32!lstrcmpiW` at `0x180010bf9`

## string_xrefs

- `0x180010b65`: `SlowLinkEnabled`
- `0x180010be4`: `SlowLinkEnabled`
- `0x180010c53`: `SlowLinkEnabled`
- `0x180010fa7`: `SlowLinkEnabled`

## pseudocode

```c
__int64 __fastcall CCscScope::_TransitionSlowLinkOfflineIfRequired(
        CCscScope *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v5; // r13
  int v7; // ebx
  unsigned int i; // esi
  int v9; // eax
  int v10; // ecx
  COfflineFilesSetting *v11; // rax
  COfflineFilesSetting *v12; // rax
  COfflineFilesSetting *v13; // rbx
  int v14; // esi
  unsigned int j; // r14d
  LPCWSTR *v16; // r15
  _QWORD *v17; // r14
  void (__fastcall **v18)(_QWORD *, __int64); // rax
  int v19; // esi
  int v20; // ebx
  int v21; // ebx
  unsigned int v22; // ebx
  CCscScope *v23; // rcx
  int v24; // ebx
  unsigned __int16 *v25; // rbx
  int v26; // edx
  CObjectMonitor *v27; // rcx
  __int64 v28; // rdx
  void *v29; // rdx
  const wchar_t *v30; // rax
  unsigned int v32[2]; // [rsp+48h] [rbp-89h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-81h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-79h] BYREF
  _BYTE v35[64]; // [rsp+78h] [rbp-59h] BYREF
  _BYTE v36[112]; // [rsp+B8h] [rbp-19h] BYREF
  CCscScope *v37; // [rsp+138h] [rbp+67h] BYREF
  unsigned __int64 v38; // [rsp+148h] [rbp+77h]

  v38 = a3;
  v37 = this;
  v5 = a3;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
      (_DWORD)a2,
      a4,
      a3);
  v32[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = -2147024773;
  for ( i = 0; i < 0x42; ++i )
  {
    v9 = lstrcmpiW((&off_18008A820)[6 * (int)i], L"SlowLinkEnabled");
    v10 = 0;
    if ( v9 )
      v10 = v7;
    v7 = v10;
  }
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids,
        L"SlowLinkEnabled");
    }
    return 0;
  }
  v11 = (COfflineFilesSetting *)operator new(0x40u);
  if ( !v11 )
    return 0;
  v12 = COfflineFilesSetting::COfflineFilesSetting(v11);
  v13 = v12;
  if ( !v12 )
    return 0;
  if ( *((_QWORD *)v12 + 7) )
  {
    v14 = -2147467259;
  }
  else
  {
    v14 = -2147024773;
    *((_QWORD *)v12 + 7) = 0;
    for ( j = 0; j < 0x42; ++j )
    {
      v16 = (LPCWSTR *)&(&off_18008A820)[6 * (int)j];
      if ( !lstrcmpiW(*v16, L"SlowLinkEnabled") )
      {
        *((_QWORD *)v13 + 7) = v16;
        v14 = 0;
      }
    }
    v5 = v38;
    if ( v14 == -2147024773
      && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids,
        L"SlowLinkEnabled");
      goto LABEL_20;
    }
  }
  if ( v14 >= 0 )
  {
    v17 = (_QWORD *)(((unsigned __int64)v13 + 32) & -(__int64)(v13 != 0));
    goto LABEL_21;
  }
LABEL_20:
  v17 = 0;
  (**(void (__fastcall ***)(COfflineFilesSetting *, __int64))v13)(v13, 1);
LABEL_21:
  if ( v14 >= 0 )
  {
    v18 = (void (__fastcall **)(_QWORD *, __int64))*v17;
    LODWORD(v37) = 0;
    v19 = 0;
    v20 = ((__int64 (__fastcall *)(_QWORD *, VARIANTARG *, CCscScope **))v18[7])(v17, &pvarg, &v37);
    if ( v20 >= 0 )
      v19 = (int)v37;
    (*(void (__fastcall **)(_QWORD *, __int64))*v17)(v17, 1);
    if ( v20 >= 0 )
    {
      v21 = CscVarUtil_ConvertVariantToDWORD(&pvarg, v32);
      VariantClear(&pvarg);
      if ( v21 >= 0 )
      {
        v22 = v32[0];
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
            v32[0],
            v19);
        }
        if ( v22 )
        {
          MAP_NODE::MAP_NODE(v35, 0);
          MAP_NODE::MAP_NODE(v36, 0);
          if ( (int)CSlowLinkConfigInfo::LoadInfo((CSlowLinkConfigInfo *)v35) < 0
            || (v32[0] = 0,
                !CCscScope::_ShouldScopeBeInSlowLink(v23, a2, v5, a4, (struct CSlowLinkConfigInfo *)v35, (int *)v32)) )
          {
LABEL_68:
            MAP_NODE::~MAP_NODE((MAP_NODE *)v36);
            MAP_NODE::~MAP_NODE((MAP_NODE *)v35);
            return 0;
          }
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids);
          }
          CscAgent_SuspendSyncTasks();
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, a2);
          }
          LODWORD(v37) = 0;
          v33 = 0;
          v24 = CscLib_SetItemConnectionStateEx(a2, 2, 3, 0, 0, &v37, &v33);
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids);
          }
          CscAgent_ResumeSyncTasks();
          if ( v24 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
                (_DWORD)a2,
                v24);
            }
            goto LABEL_68;
          }
          v25 = v33;
          if ( (_DWORD)v37 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              v30 = L"<NULL>";
              if ( v33 )
                v30 = v33;
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                65,
                (unsigned int)WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids,
                (_DWORD)a2,
                (__int64)v30);
            }
            if ( v25 )
              CscEvt_PathFailedToTransitionToSlowLinkDueToOpenHandle(a2, v25);
            else
              CscEvt_PathFailedToTransitionToSlowLinkDueToOpenHandleNoFileName(a2);
            goto LABEL_63;
          }
          if ( v32[0] )
          {
            CscEvt_PathTransitionToSlowLinkDueToAlwaysOffline(a2);
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_54;
            }
            v28 = 63;
          }
          else
          {
            CscEvt_PathTransitionToSlowLink(a2, v5, a4);
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_54;
            }
            v28 = 64;
          }
          WPP_SF_S(*((_QWORD *)v27 + 2), v28, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids, a2);
LABEL_54:
          SlowLink_ClearOnlineTransitionRecord(a2, v26);
          SlowLink_RecordOfflineTransition(a2);
LABEL_63:
          if ( v25 )
            CscUtil_HeapFree(v25, v29);
          goto LABEL_68;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010ac8  mov     rax, rsp
0x180010acb  mov     [rax+10h], rbx
0x180010acf  mov     [rax+18h], r8
0x180010ad3  mov     [rax+8], rcx
0x180010ad7  push    rbp
0x180010ad8  push    rsi
0x180010ad9  push    rdi
0x180010ada  push    r12
0x180010adc  push    r13
0x180010ade  push    r14
0x180010ae0  push    r15
0x180010ae2  lea     rbp, [rax-5Fh]
0x180010ae6  sub     rsp, 0F0h
0x180010aed  mov     r12, r9
0x180010af0  mov     r13, r8
0x180010af3  mov     rdi, rdx
0x180010af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180010afd  lea     r14, WPP_GLOBAL_Control
0x180010b04  cmp     rcx, r14
0x180010b07  jz      short loc_180010B34
0x180010b09  test    dword ptr [rcx+1Ch], 400h
0x180010b10  jz      short loc_180010B34
0x180010b12  mov     rcx, [rcx+10h]
0x180010b16  mov     edx, 3Ah ; ':'
0x180010b1b  mov     dword ptr [rsp+120h+var_F8], r8d
0x180010b20  mov     r9, rdi
0x180010b23  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010b2a  mov     dword ptr [rsp+120h+var_100], r12d
0x180010b2f  call    WPP_SF_SdD
0x180010b34  xor     r15d, r15d
0x180010b37  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180010b3b  xorps   xmm0, xmm0
0x180010b3e  mov     [rsp+120h+var_E0], r15d
0x180010b43  xor     eax, eax
0x180010b45  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180010b49  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180010b4d  call    cs:__imp_VariantInit
0x180010b53  mov     ebx, 8007007Bh
0x180010b58  lea     r14, off_18008A820; "AlwaysPinSubFolders"
0x180010b5f  mov     esi, r15d
0x180010b62  movsxd  rax, esi
0x180010b65  lea     rdx, aSlowlinkenable; "SlowLinkEnabled"
0x180010b6c  lea     rcx, [rax+rax*2]
0x180010b70  add     rcx, rcx
0x180010b73  mov     rcx, [r14+rcx*8]; lpString1
0x180010b77  call    cs:__imp_lstrcmpiW
0x180010b7d  test    eax, eax
0x180010b7f  mov     ecx, r15d
0x180010b82  cmovnz  ecx, ebx
0x180010b85  inc     esi
0x180010b87  mov     ebx, ecx
0x180010b89  cmp     esi, 42h ; 'B'
0x180010b8c  jb      short loc_180010B62
0x180010b8e  lea     r14, WPP_GLOBAL_Control
0x180010b95  test    ecx, ecx
0x180010b97  js      loc_180010F86
0x180010b9d  mov     ecx, 40h ; '@'; Size
0x180010ba2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ba7  test    rax, rax
0x180010baa  jz      loc_180010FBF
0x180010bb0  mov     rcx, rax; this
0x180010bb3  call    ??0COfflineFilesSetting@@AEAA@XZ; COfflineFilesSetting::COfflineFilesSetting(void)
0x180010bb8  mov     rbx, rax
0x180010bbb  test    rax, rax
0x180010bbe  jz      loc_180010FBF
0x180010bc4  cmp     [rax+38h], r15
0x180010bc8  jnz     loc_180010E7D
0x180010bce  mov     esi, 8007007Bh
0x180010bd3  mov     [rax+38h], r15
0x180010bd7  mov     r14d, r15d
0x180010bda  lea     r13, off_18008A820; "AlwaysPinSubFolders"
0x180010be1  movsxd  rax, r14d
0x180010be4  lea     rdx, aSlowlinkenable; "SlowLinkEnabled"
0x180010beb  lea     r15, [rax+rax*2]
0x180010bef  shl     r15, 4
0x180010bf3  add     r15, r13
0x180010bf6  mov     rcx, [r15]; lpString1
0x180010bf9  call    cs:__imp_lstrcmpiW
0x180010bff  test    eax, eax
0x180010c01  jnz     short loc_180010C0F
0x180010c03  mov     [rbx+38h], r15
0x180010c07  xor     r15d, r15d
0x180010c0a  mov     esi, r15d
0x180010c0d  jmp     short loc_180010C12
0x180010c0f  xor     r15d, r15d
0x180010c12  inc     r14d
0x180010c15  cmp     r14d, 42h ; 'B'
0x180010c19  jb      short loc_180010BE1
0x180010c1b  mov     r13, [rbp+57h+arg_10]
0x180010c1f  cmp     esi, 8007007Bh
0x180010c25  jnz     loc_180010E82
0x180010c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c32  lea     rax, WPP_GLOBAL_Control
0x180010c39  cmp     rcx, rax
0x180010c3c  jz      loc_180010E82
0x180010c42  test    dword ptr [rcx+1Ch], 10000h
0x180010c49  jz      loc_180010E82
0x180010c4f  mov     rcx, [rcx+10h]
0x180010c53  lea     r9, aSlowlinkenable; "SlowLinkEnabled"
0x180010c5a  mov     edx, 15h
0x180010c5f  lea     r8, WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids
0x180010c66  call    WPP_SF_S
0x180010c6b  mov     rax, [rbx]
0x180010c6e  mov     edx, 1
0x180010c73  mov     rcx, rbx
0x180010c76  mov     r14, r15
0x180010c79  mov     rax, [rax]
0x180010c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c81  test    esi, esi
0x180010c83  js      loc_180010FBF
0x180010c89  mov     rax, [r14]
0x180010c8c  lea     r8, [rbp+57h+arg_0]
0x180010c90  lea     rdx, [rbp+57h+pvarg]
0x180010c94  mov     dword ptr [rbp+57h+arg_0], r15d
0x180010c98  mov     rcx, r14
0x180010c9b  mov     esi, r15d
0x180010c9e  mov     rax, [rax+38h]
0x180010ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ca7  mov     r8, [r14]
0x180010caa  test    eax, eax
0x180010cac  mov     ebx, eax
0x180010cae  mov     edx, 1
0x180010cb3  cmovns  esi, dword ptr [rbp+57h+arg_0]
0x180010cb7  mov     rcx, r14
0x180010cba  mov     rax, [r8]
0x180010cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc2  test    ebx, ebx
0x180010cc4  js      loc_180010FBF
0x180010cca  lea     rdx, [rsp+120h+var_E0]; unsigned int *
0x180010ccf  lea     rcx, [rbp+57h+pvarg]; pvarSrc
0x180010cd3  call    ?CscVarUtil_ConvertVariantToDWORD@@YAJAEBUtagVARIANT@@PEAK@Z; CscVarUtil_ConvertVariantToDWORD(tagVARIANT const &,ulong *)
0x180010cd8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180010cdc  mov     ebx, eax
0x180010cde  call    cs:__imp_VariantClear
0x180010ce4  test    ebx, ebx
0x180010ce6  js      loc_180010FBF
0x180010cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cf3  lea     r14, WPP_GLOBAL_Control
0x180010cfa  mov     ebx, [rsp+120h+var_E0]
0x180010cfe  cmp     rcx, r14
0x180010d01  jz      short loc_180010D28
0x180010d03  test    dword ptr [rcx+1Ch], 400h
0x180010d0a  jz      short loc_180010D28
0x180010d0c  mov     rcx, [rcx+10h]
0x180010d10  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010d17  mov     edx, 3Bh ; ';'
0x180010d1c  mov     dword ptr [rsp+120h+var_100], esi
0x180010d20  mov     r9d, ebx
0x180010d23  call    WPP_SF_dd
0x180010d28  test    ebx, ebx
0x180010d2a  jz      loc_180010FBF
0x180010d30  xor     edx, edx
0x180010d32  lea     rcx, [rbp+57h+var_B0]
0x180010d36  call    ??0MAP_NODE@@QEAA@W4MAP_NODE_TYPE@@@Z; MAP_NODE::MAP_NODE(MAP_NODE_TYPE)
0x180010d3b  xor     edx, edx
0x180010d3d  lea     rcx, [rbp+57h+var_70]
0x180010d41  call    ??0MAP_NODE@@QEAA@W4MAP_NODE_TYPE@@@Z; MAP_NODE::MAP_NODE(MAP_NODE_TYPE)
0x180010d46  lea     rcx, [rbp+57h+var_B0]; this
0x180010d4a  call    ?LoadInfo@CSlowLinkConfigInfo@@QEAAJXZ; CSlowLinkConfigInfo::LoadInfo(void)
0x180010d4f  test    eax, eax
0x180010d51  js      loc_180010F72
0x180010d57  lea     rax, [rsp+120h+var_E0]
0x180010d5c  mov     [rsp+120h+var_E0], r15d
0x180010d61  mov     [rsp+120h+var_F8], rax; int *
0x180010d66  mov     r9, r12; unsigned __int64
0x180010d69  lea     rax, [rbp+57h+var_B0]
0x180010d6d  mov     r8, r13; unsigned __int64
0x180010d70  mov     rdx, rdi; unsigned __int16 *
0x180010d73  mov     [rsp+120h+var_100], rax; struct CSlowLinkConfigInfo *
0x180010d78  call    ?_ShouldScopeBeInSlowLink@CCscScope@@AEAAHPEBG_K1AEAVCSlowLinkConfigInfo@@PEAH@Z; CCscScope::_ShouldScopeBeInSlowLink(ushort const *,unsigned __int64,unsigned __int64,CSlowLinkConfigInfo &,int *)
0x180010d7d  test    eax, eax
0x180010d7f  jz      loc_180010F72
0x180010d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d8c  mov     esi, 400h
0x180010d91  cmp     rcx, r14
0x180010d94  jz      short loc_180010DB0
0x180010d96  test    [rcx+1Ch], esi
0x180010d99  jz      short loc_180010DB0
0x180010d9b  mov     rcx, [rcx+10h]
0x180010d9f  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010da6  mov     edx, 3Ch ; '<'
0x180010dab  call    WPP_SF_
0x180010db0  call    ?CscAgent_SuspendSyncTasks@@YAJXZ; CscAgent_SuspendSyncTasks(void)
0x180010db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dbc  cmp     rcx, r14
0x180010dbf  jz      short loc_180010DDE
0x180010dc1  test    [rcx+1Ch], esi
0x180010dc4  jz      short loc_180010DDE
0x180010dc6  mov     rcx, [rcx+10h]
0x180010dca  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010dd1  mov     edx, 3Dh ; '='
0x180010dd6  mov     r9, rdi
0x180010dd9  call    WPP_SF_S
0x180010dde  xor     r9d, r9d
0x180010de1  mov     dword ptr [rbp+57h+arg_0], r15d
0x180010de5  lea     rax, [rsp+120h+var_D8]
0x180010dea  mov     [rsp+120h+var_D8], r15
0x180010def  mov     [rsp+30h], rax
0x180010df4  mov     rcx, rdi
0x180010df7  lea     rax, [rbp+57h+arg_0]
0x180010dfb  mov     [rsp+120h+var_F8], rax
0x180010e00  lea     edx, [r9+2]
0x180010e04  lea     r8d, [r9+3]
0x180010e08  mov     dword ptr [rsp+120h+var_100], r15d
0x180010e0d  call    ?CscLib_SetItemConnectionStateEx@@YAJPEBGW4_CSC_SCOPE@@W4_CSC_CONNECT_STATE@@HHPEAHPEAPEAG@Z; CscLib_SetItemConnectionStateEx(ushort const *,_CSC_SCOPE,_CSC_CONNECT_STATE,int,int,int *,ushort * *)
0x180010e12  mov     ebx, eax
0x180010e14  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e1b  cmp     rcx, r14
0x180010e1e  jz      short loc_180010E3A
0x180010e20  test    [rcx+1Ch], esi
0x180010e23  jz      short loc_180010E3A
0x180010e25  mov     rcx, [rcx+10h]
0x180010e29  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010e30  mov     edx, 3Eh ; '>'
0x180010e35  call    WPP_SF_
0x180010e3a  call    ?CscAgent_ResumeSyncTasks@@YAJXZ; CscAgent_ResumeSyncTasks(void)
0x180010e3f  test    ebx, ebx
0x180010e41  js      loc_180010F44
0x180010e47  mov     rbx, [rsp+120h+var_D8]
0x180010e4c  cmp     dword ptr [rbp+57h+arg_0], r15d
0x180010e50  jnz     loc_180010EE2
0x180010e56  mov     rcx, rdi; unsigned __int16 *
0x180010e59  cmp     [rsp+120h+var_E0], r15d
0x180010e5e  jz      short loc_180010E9C
0x180010e60  call    ?CscEvt_PathTransitionToSlowLinkDueToAlwaysOffline@@YAKPEBG@Z; CscEvt_PathTransitionToSlowLinkDueToAlwaysOffline(ushort const *)
0x180010e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e6c  cmp     rcx, r14
0x180010e6f  jz      short loc_180010ED0
0x180010e71  test    [rcx+1Ch], esi
0x180010e74  jz      short loc_180010ED0
0x180010e76  mov     edx, 3Fh ; '?'
0x180010e7b  jmp     short loc_180010EBD
0x180010e7d  mov     esi, 80004005h
0x180010e82  test    esi, esi
0x180010e84  js      loc_180010C6B
0x180010e8a  lea     rax, [rbx+20h]
0x180010e8e  neg     rbx
0x180010e91  sbb     r14, r14
0x180010e94  and     r14, rax
0x180010e97  jmp     loc_180010C81
0x180010e9c  mov     r8, r12; unsigned __int64
0x180010e9f  mov     rdx, r13; unsigned __int64
0x180010ea2  call    ?CscEvt_PathTransitionToSlowLink@@YAKPEBG_K1@Z; CscEvt_PathTransitionToSlowLink(ushort const *,unsigned __int64,unsigned __int64)
0x180010ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010eae  cmp     rcx, r14
0x180010eb1  jz      short loc_180010ED0
0x180010eb3  test    [rcx+1Ch], esi
0x180010eb6  jz      short loc_180010ED0
0x180010eb8  mov     edx, 40h ; '@'
0x180010ebd  mov     rcx, [rcx+10h]
0x180010ec1  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010ec8  mov     r9, rdi
0x180010ecb  call    WPP_SF_S
0x180010ed0  mov     rcx, rdi; unsigned __int16 *
0x180010ed3  call    ?SlowLink_ClearOnlineTransitionRecord@@YAJPEBGH@Z; SlowLink_ClearOnlineTransitionRecord(ushort const *,int)
0x180010ed8  mov     rcx, rdi; unsigned __int16 *
0x180010edb  call    ?SlowLink_RecordOfflineTransition@@YAJPEBG@Z; SlowLink_RecordOfflineTransition(ushort const *)
0x180010ee0  jmp     short loc_180010F35
0x180010ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ee9  cmp     rcx, r14
0x180010eec  jz      short loc_180010F1E
0x180010eee  test    [rcx+1Ch], esi
0x180010ef1  jz      short loc_180010F1E
0x180010ef3  mov     rcx, [rcx+10h]
0x180010ef7  lea     rax, aNull_1; "<NULL>"
0x180010efe  test    rbx, rbx
0x180010f01  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010f08  mov     edx, 41h ; 'A'
0x180010f0d  mov     r9, rdi
0x180010f10  cmovnz  rax, rbx
0x180010f14  mov     [rsp+120h+var_100], rax
0x180010f19  call    WPP_SF_SS
0x180010f1e  mov     rcx, rdi; unsigned __int16 *
0x180010f21  test    rbx, rbx
0x180010f24  jz      short loc_180010F30
0x180010f26  mov     rdx, rbx; unsigned __int16 *
0x180010f29  call    ?CscEvt_PathFailedToTransitionToSlowLinkDueToOpenHandle@@YAKPEBG0@Z; CscEvt_PathFailedToTransitionToSlowLinkDueToOpenHandle(ushort const *,ushort const *)
0x180010f2e  jmp     short loc_180010F35
0x180010f30  call    ?CscEvt_PathFailedToTransitionToSlowLinkDueToOpenHandleNoFileName@@YAKPEBG@Z; CscEvt_PathFailedToTransitionToSlowLinkDueToOpenHandleNoFileName(ushort const *)
0x180010f35  test    rbx, rbx
0x180010f38  jz      short loc_180010F72
0x180010f3a  mov     rcx, rbx; lpMem
0x180010f3d  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180010f42  jmp     short loc_180010F72
0x180010f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f4b  cmp     rcx, r14
0x180010f4e  jz      short loc_180010F72
0x180010f50  test    byte ptr [rcx+1Ch], 2
0x180010f54  jz      short loc_180010F72
0x180010f56  mov     rcx, [rcx+10h]
0x180010f5a  lea     r8, WPP_bc65b32e868b3e36b3d994786a01514e_Traceguids
0x180010f61  mov     edx, 42h ; 'B'
0x180010f66  mov     dword ptr [rsp+120h+var_100], ebx
0x180010f6a  mov     r9, rdi
0x180010f6d  call    WPP_SF_Sd
0x180010f72  lea     rcx, [rbp+57h+var_70]; this
0x180010f76  call    ??1MAP_NODE@@QEAA@XZ; MAP_NODE::~MAP_NODE(void)
0x180010f7b  lea     rcx, [rbp+57h+var_B0]; this
0x180010f7f  call    ??1MAP_NODE@@QEAA@XZ; MAP_NODE::~MAP_NODE(void)
0x180010f84  jmp     short loc_180010FBF
  ... truncated ...
```
