# IntfInitContext(void *)

- ea: `0x180018d4c`
- end: `0x18001946e`
- name: `?IntfInitContext@@YAKPEAX@Z`
- size: `1826`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f4a0`

## callees

- `0x1800025f0`
- `0x1800030fc`
- `0x18000a7ec`
- `0x18000a9c0`
- `0x18000aa58`
- `0x18000c230`
- `0x18000c4d4`
- `0x18000c85c`
- `0x1800177b4`
- `0x180017a00`
- `0x180018d4c`
- `0x180019474`
- `0x180019690`
- `0x18001a930`
- `0x18001bca0`
- `0x18001bd7c`
- `0x18001bf24`
- `0x1800224ac`
- `0x1800226b8`
- `0x180022834`
- `0x180022a6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019423`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019423`
- `dot3msm!Dot3MsmInitAdapter` at `0x18001906a`
- `dot3msm!Dot3MsmInitAdapter` at `0x18001906a`
- `dot3msm!Dot3MsmDeInitAdapter` at `0x180018f25`
- `dot3msm!Dot3MsmDeInitAdapter` at `0x180018f25`
- `dot3msm!Dot3MsmCreateDefaultProfile` at `0x180019334`
- `dot3msm!Dot3MsmCreateDefaultProfile` at `0x180019334`
- `dot3msm!Dot3MsmFreeProfile` at `0x180018f3e`
- `dot3msm!Dot3MsmFreeProfile` at `0x180018f3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f58`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180018f7b`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180018f7b`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180018def`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800191d9`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180018def`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800191d9`

## pseudocode

```c
__int64 __fastcall IntfInitContext(void *a1)
{
  int v2; // r15d
  unsigned int v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  __int64 *ToastHelper; // rax
  struct _LAN_INTERFACE_CONTEXT *v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx
  _QWORD *v11; // rax
  unsigned int inited; // eax
  __int64 v13; // rdx
  unsigned int Profile; // eax
  __int64 v15; // rdx
  struct _LAN_INTERFACE_CONTEXT *v16; // r8
  unsigned int v17; // eax
  struct _LIST_ENTRY *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdi
  _DWORD *v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // r8
  _DWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  void *v29; // rax
  unsigned int v30; // ecx
  struct _PM_PROFILE *v31; // rsi
  struct _LAN_INTERFACE_CONTEXT *v32; // [rsp+40h] [rbp-39h] BYREF
  __int64 v33; // [rsp+48h] [rbp-31h] BYREF
  struct _PM_PROFILE *v34; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v35[8]; // [rsp+58h] [rbp-21h] BYREF
  std::_Ref_count_base *v36; // [rsp+60h] [rbp-19h]
  __int128 v37; // [rsp+68h] [rbp-11h] BYREF
  __int64 v38; // [rsp+78h] [rbp-1h]

  v32 = 0;
  v38 = 0;
  v37 = 0;
  v2 = 0;
  v33 = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 45, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
  }
  v3 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1448036676, 0, 1, &v32);
  if ( v3 )
    goto LABEL_22;
  if ( !v32 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 46, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    v3 = 87;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 47, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, *((_QWORD *)v32 + 15));
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v32 + 128));
  v2 = 1;
  ToastHelper = (__int64 *)MakeToastHelper(v35, (char *)v32 + 8);
  v6 = v32;
  v7 = *ToastHelper;
  v8 = ToastHelper[1];
  *ToastHelper = 0;
  ToastHelper[1] = 0;
  *((_QWORD *)v6 + 59) = v7;
  v9 = (std::_Ref_count_base *)*((_QWORD *)v6 + 60);
  *((_QWORD *)v6 + 60) = v8;
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  if ( !*((_QWORD *)v32 + 59) )
    goto LABEL_21;
  *((_QWORD *)v32 + 41) = 0;
  v11 = (_QWORD *)((char *)v32 + 392);
  *((_QWORD *)v32 + 50) = (char *)v32 + 392;
  *v11 = v11;
  *((_DWORD *)v32 + 106) = 0;
  *((_DWORD *)v32 + 107) = 0;
  *((_QWORD *)v32 + 54) = 0;
  *((_QWORD *)v32 + 55) = 0;
  *((_DWORD *)v32 + 112) = 0;
  *((_QWORD *)v32 + 57) = 0;
  *((_DWORD *)v32 + 116) = 2;
  v37 = *(_OWORD *)((char *)v32 + 8);
  v38 = *((_QWORD *)v32 + 15);
  inited = Dot3MsmInitAdapter(a1, &v37, (char *)v32 + 328);
  v3 = inited;
  if ( inited )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v13 = 48;
    goto LABEL_43;
  }
  if ( !g_bDisableAuthentication )
  {
    Profile = IntfLoadProfile(v32);
    v3 = Profile;
    if ( Profile )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 49, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, Profile);
        v4 = WPP_GLOBAL_Control;
      }
      if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) == 0 )
        goto LABEL_23;
      McTemplateU0qqqjz_EtwEventWriteTransfer(
        (_DWORD)v32 + 8,
        (unsigned int)LoadProfileFailed,
        v3,
        625,
        0,
        (__int64)v32 + 8,
        *((_QWORD *)v32 + 15));
      goto LABEL_22;
    }
  }
  inited = IntfInitTimers(v32);
  v3 = inited;
  if ( inited )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v13 = 50;
    goto LABEL_43;
  }
  v3 = AceInitStateMachine((char *)v32 + 176, v15, *(_QWORD *)v32);
  if ( v3 )
    goto LABEL_22;
  IntfDefaultParameters(v32);
  IntfReadFromRegistry(v32);
  HtReferenceHandleWithTag(g_hHandleTable, a1, 1448036676, 1229870150, 0, &v32);
  v16 = v32;
  if ( *((_DWORD *)v32 + 43) )
  {
    AceStartStateMachine((struct _LAN_INTERFACE_CONTEXT *)((char *)v32 + 176));
    *((_DWORD *)v32 + 42) = 0;
    AceInsertTrigger((char *)v32 + 176, 1u, 0, 0, 1);
    v16 = v32;
  }
  v17 = PmEnumProfiles(
          (struct _GUID *)((char *)v16 + 8),
          (unsigned int (*)(struct _PM_PROFILE *, unsigned int, void *))ProfileCallBackIntf,
          v16);
  v3 = v17;
  if ( v17 )
  {
    if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 0x10) != 0 )
      McTemplateU0qqqjz_EtwEventWriteTransfer(
        (_DWORD)v32 + 8,
        (unsigned int)NoProfileFound,
        v17,
        680,
        0,
        (__int64)v32 + 8,
        *((_QWORD *)v32 + 15));
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_77;
    }
    v19 = 51;
    v20 = v3;
    goto LABEL_76;
  }
  v21 = *((_QWORD *)v32 + 37);
  if ( v21 )
  {
    v34 = (struct _PM_PROFILE *)*((_QWORD *)v32 + 37);
    v22 = *(_DWORD **)(v21 + 552);
    if ( v22 )
      goto LABEL_91;
    goto LABEL_77;
  }
  if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 0x10) != 0 )
    McTemplateU0qqqjz_EtwEventWriteTransfer(
      (_DWORD)v32 + 8,
      (unsigned int)NoProfileFound,
      0,
      694,
      0,
      (__int64)v32 + 8,
      *((_QWORD *)v32 + 15));
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v19 = 52;
    v20 = 0;
LABEL_76:
    WPP_SF_d(v18[1].Flink, v19, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v20);
  }
LABEL_77:
  inited = Dot3MsmCreateDefaultProfile(&v33);
  v3 = inited;
  if ( inited )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v13 = 53;
    goto LABEL_43;
  }
  v25 = Dot3Alloc(0x20u, v23, v24);
  v22 = v25;
  if ( !v25 )
    goto LABEL_21;
  *v25 = 0;
  v28 = v33;
  *(_OWORD *)(v22 + 2) = *(_OWORD *)v33;
  *((_QWORD *)v22 + 3) = *(_QWORD *)(v28 + 16);
  v29 = Dot3Alloc(*(unsigned int *)(v33 + 8), v26, v27);
  *((_QWORD *)v22 + 3) = v29;
  if ( !v29 )
    goto LABEL_21;
  memcpy_0(v29, *(const void **)(v33 + 16), *(unsigned int *)(v33 + 8));
  inited = PmAllocateEmptyProfile(v30, &v34);
  v3 = inited;
  if ( inited )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v13 = 54;
LABEL_43:
    WPP_SF_d(v4[1].Flink, v13, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, inited);
    goto LABEL_22;
  }
  v31 = v34;
  if ( !v34 )
  {
LABEL_21:
    v3 = 14;
LABEL_22:
    v4 = WPP_GLOBAL_Control;
LABEL_23:
    if ( !v32 )
      goto LABEL_27;
    IntfDeinitTimers(v32);
    AceDeinitStateMachine((struct _LAN_INTERFACE_CONTEXT *)((char *)v32 + 176));
    if ( *((_QWORD *)v32 + 41) )
      Dot3MsmDeInitAdapter();
    goto LABEL_26;
  }
  _o_wcscpy_s((char *)v34 + 24, 256, L"DEFAULT");
  *((_QWORD *)v31 + 69) = v22;
  *((_QWORD *)v32 + 37) = v31;
  *((_DWORD *)v32 + 76) = 5;
LABEL_91:
  if ( !g_bDisableAuthentication )
  {
LABEL_26:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v22[2] = 0;
  v4 = WPP_GLOBAL_Control;
LABEL_27:
  if ( v33 )
  {
    Dot3MsmFreeProfile(v33);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v2 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v32 + 128));
    v4 = WPP_GLOBAL_Control;
  }
  if ( v32 )
  {
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 55, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180018d4c  push    rbp
0x180018d4e  push    rbx
0x180018d4f  push    rsi
0x180018d50  push    rdi
0x180018d51  push    r12
0x180018d53  push    r13
0x180018d55  push    r14
0x180018d57  push    r15
0x180018d59  lea     rbp, [rsp-1Fh]
0x180018d5e  sub     rsp, 98h
0x180018d65  mov     rax, cs:__security_cookie
0x180018d6c  xor     rax, rsp
0x180018d6f  mov     [rbp+57h+var_50], rax
0x180018d73  xor     r12d, r12d
0x180018d76  xorps   xmm0, xmm0
0x180018d79  xor     eax, eax
0x180018d7b  mov     [rbp+57h+var_90], r12
0x180018d7f  mov     [rbp+57h+var_58], rax
0x180018d83  mov     r14, rcx
0x180018d86  movups  [rbp+57h+var_68], xmm0
0x180018d8a  mov     r15d, r12d
0x180018d8d  mov     [rbp+57h+var_88], r12
0x180018d91  mov     [rbp+57h+var_80], r12
0x180018d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d9c  lea     rsi, WPP_GLOBAL_Control
0x180018da3  lea     r13d, [r12+1]
0x180018da8  cmp     rcx, rsi
0x180018dab  jz      short loc_180018DCC
0x180018dad  cmp     byte ptr [rcx+19h], 4
0x180018db1  jb      short loc_180018DCC
0x180018db3  test    [rcx+1Ch], r13b
0x180018db7  jz      short loc_180018DCC
0x180018db9  mov     rcx, [rcx+10h]
0x180018dbd  lea     edx, [rax+2Dh]
0x180018dc0  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180018dc7  call    WPP_SF_
0x180018dcc  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180018dd3  lea     rax, [rbp+57h+var_90]
0x180018dd7  mov     [rsp+0D0h+var_A8], rax
0x180018ddc  mov     edi, 564F4944h
0x180018de1  mov     r8d, edi
0x180018de4  mov     [rsp+0D0h+var_B0], r13d
0x180018de9  xor     r9d, r9d
0x180018dec  mov     rdx, r14
0x180018def  call    cs:__imp_HtReferenceHandleWithTag
0x180018df5  mov     ebx, eax
0x180018df7  test    eax, eax
0x180018df9  jnz     loc_180018EED
0x180018dff  cmp     [rbp+57h+var_90], r12
0x180018e03  jnz     short loc_180018E41
0x180018e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e0c  cmp     rcx, rsi
0x180018e0f  jz      short loc_180018E37
0x180018e11  cmp     [rcx+19h], r13b
0x180018e15  jb      short loc_180018E37
0x180018e17  test    [rcx+1Ch], r13b
0x180018e1b  jz      short loc_180018E37
0x180018e1d  mov     rcx, [rcx+10h]
0x180018e21  lea     edx, [rax+2Eh]
0x180018e24  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180018e2b  call    WPP_SF_
0x180018e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e37  mov     ebx, 57h ; 'W'
0x180018e3c  jmp     loc_180018EF4
0x180018e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e48  cmp     rcx, rsi
0x180018e4b  jz      short loc_180018E76
0x180018e4d  cmp     byte ptr [rcx+19h], 4
0x180018e51  jb      short loc_180018E76
0x180018e53  test    [rcx+1Ch], r13b
0x180018e57  jz      short loc_180018E76
0x180018e59  mov     r9, [rbp+57h+var_90]
0x180018e5d  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180018e64  mov     rcx, [rcx+10h]
0x180018e68  mov     edx, 2Fh ; '/'
0x180018e6d  mov     r9, [r9+78h]
0x180018e71  call    WPP_SF_S
0x180018e76  mov     rcx, [rbp+57h+var_90]
0x180018e7a  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180018e7e  call    cs:__imp_EnterCriticalSection
0x180018e84  mov     rdx, [rbp+57h+var_90]
0x180018e88  lea     rcx, [rbp+57h+var_78]
0x180018e8c  add     rdx, 8
0x180018e90  mov     r15d, r13d
0x180018e93  call    _MakeToastHelper
0x180018e98  mov     r8, [rbp+57h+var_90]
0x180018e9c  mov     rcx, [rax]
0x180018e9f  mov     rdx, [rax+8]
0x180018ea3  mov     [rax], r12
0x180018ea6  mov     [rax+8], r12
0x180018eaa  mov     [r8+1D8h], rcx
0x180018eb1  mov     rcx, [r8+1E0h]; this
0x180018eb8  mov     [r8+1E0h], rdx
0x180018ebf  test    rcx, rcx
0x180018ec2  jz      short loc_180018EC9
0x180018ec4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018ec9  mov     rcx, [rbp+57h+var_70]; this
0x180018ecd  test    rcx, rcx
0x180018ed0  jz      short loc_180018ED7
0x180018ed2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018ed7  mov     rax, [rbp+57h+var_90]
0x180018edb  cmp     [rax+1D8h], r12
0x180018ee2  jnz     loc_180018FDA
0x180018ee8  mov     ebx, 0Eh
0x180018eed  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ef4  mov     rax, [rbp+57h+var_90]
0x180018ef8  test    rax, rax
0x180018efb  jz      short loc_180018F32
0x180018efd  mov     rcx, rax; struct _LAN_INTERFACE_CONTEXT *
0x180018f00  call    ?IntfDeinitTimers@@YAXPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfDeinitTimers(_LAN_INTERFACE_CONTEXT *)
0x180018f05  mov     rcx, [rbp+57h+var_90]
0x180018f09  add     rcx, 0B0h; struct _ACE_STATE_MACHINE *
0x180018f10  call    ?AceDeinitStateMachine@@YAKPEAU_ACE_STATE_MACHINE@@@Z; AceDeinitStateMachine(_ACE_STATE_MACHINE *)
0x180018f15  mov     rax, [rbp+57h+var_90]
0x180018f19  mov     rcx, [rax+148h]
0x180018f20  test    rcx, rcx
0x180018f23  jz      short loc_180018F2B
0x180018f25  call    cs:__imp_Dot3MsmDeInitAdapter
0x180018f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f32  mov     rax, [rbp+57h+var_88]
0x180018f36  test    rax, rax
0x180018f39  jz      short loc_180018F4B
0x180018f3b  mov     rcx, rax
0x180018f3e  call    cs:__imp_Dot3MsmFreeProfile
0x180018f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f4b  test    r15d, r15d
0x180018f4e  jz      short loc_180018F65
0x180018f50  mov     rcx, [rbp+57h+var_90]
0x180018f54  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x180018f58  call    cs:__imp_LeaveCriticalSection
0x180018f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f65  cmp     [rbp+57h+var_90], r12
0x180018f69  jz      short loc_180018F88
0x180018f6b  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180018f72  mov     r9d, r13d
0x180018f75  xor     r8d, r8d
0x180018f78  mov     rdx, r14
0x180018f7b  call    cs:__imp_HtDereferenceHandleWithTag
0x180018f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f88  lea     rax, WPP_GLOBAL_Control
0x180018f8f  cmp     rcx, rax
0x180018f92  jz      short loc_180018FB8
0x180018f94  cmp     byte ptr [rcx+19h], 4
0x180018f98  jb      short loc_180018FB8
0x180018f9a  test    [rcx+1Ch], r13b
0x180018f9e  jz      short loc_180018FB8
0x180018fa0  mov     rcx, [rcx+10h]
0x180018fa4  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180018fab  mov     edx, 37h ; '7'
0x180018fb0  mov     r9d, ebx
0x180018fb3  call    WPP_SF_d
0x180018fb8  mov     eax, ebx
0x180018fba  mov     rcx, [rbp+57h+var_50]
0x180018fbe  xor     rcx, rsp; StackCookie
0x180018fc1  call    __security_check_cookie
0x180018fc6  add     rsp, 98h
0x180018fcd  pop     r15
0x180018fcf  pop     r14
0x180018fd1  pop     r13
0x180018fd3  pop     r12
0x180018fd5  pop     rdi
0x180018fd6  pop     rsi
0x180018fd7  pop     rbx
0x180018fd8  pop     rbp
0x180018fd9  retn
0x180018fda  mov     rax, [rbp+57h+var_90]
0x180018fde  lea     rdx, [rbp+57h+var_68]
0x180018fe2  mov     rcx, r14
0x180018fe5  mov     [rax+148h], r12
0x180018fec  mov     rax, [rbp+57h+var_90]
0x180018ff0  add     rax, 188h
0x180018ff6  mov     [rax+8], rax
0x180018ffa  mov     [rax], rax
0x180018ffd  mov     rax, [rbp+57h+var_90]
0x180019001  mov     [rax+1A8h], r12d
0x180019008  mov     rax, [rbp+57h+var_90]
0x18001900c  mov     [rax+1ACh], r12d
0x180019013  mov     rax, [rbp+57h+var_90]
0x180019017  mov     [rax+1B0h], r12
0x18001901e  mov     rax, [rbp+57h+var_90]
0x180019022  mov     [rax+1B8h], r12
0x180019029  mov     rax, [rbp+57h+var_90]
0x18001902d  mov     [rax+1C0h], r12d
0x180019034  mov     rax, [rbp+57h+var_90]
0x180019038  mov     [rax+1C8h], r12
0x18001903f  mov     rax, [rbp+57h+var_90]
0x180019043  mov     dword ptr [rax+1D0h], 2
0x18001904d  mov     r8, [rbp+57h+var_90]
0x180019051  movups  xmm0, xmmword ptr [r8+8]
0x180019056  movdqu  [rbp+57h+var_68], xmm0
0x18001905b  mov     rax, [r8+78h]
0x18001905f  add     r8, 148h
0x180019066  mov     [rbp+57h+var_58], rax
0x18001906a  call    cs:__imp_Dot3MsmInitAdapter
0x180019070  mov     ebx, eax
0x180019072  test    eax, eax
0x180019074  jz      short loc_1800190B7
0x180019076  mov     rcx, cs:WPP_GLOBAL_Control
0x18001907d  cmp     rcx, rsi
0x180019080  jz      loc_180018EF4
0x180019086  cmp     [rcx+19h], r13b
0x18001908a  jb      loc_180018EF4
0x180019090  test    [rcx+1Ch], r13b
0x180019094  jz      loc_180018EF4
0x18001909a  mov     edx, 30h ; '0'
0x18001909f  mov     rcx, [rcx+10h]
0x1800190a3  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x1800190aa  mov     r9d, eax
0x1800190ad  call    WPP_SF_d
0x1800190b2  jmp     loc_180018EED
0x1800190b7  cmp     cs:?g_bDisableAuthentication@@3HA, r12d; int g_bDisableAuthentication
0x1800190be  jnz     loc_18001914C
0x1800190c4  mov     rcx, [rbp+57h+var_90]; struct _LAN_INTERFACE_CONTEXT *
0x1800190c8  call    ?IntfLoadProfile@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfLoadProfile(_LAN_INTERFACE_CONTEXT *)
0x1800190cd  mov     ebx, eax
0x1800190cf  test    eax, eax
0x1800190d1  jz      short loc_18001914C
0x1800190d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190da  cmp     rcx, rsi
0x1800190dd  jz      short loc_18001910A
0x1800190df  cmp     [rcx+19h], r13b
0x1800190e3  jb      short loc_18001910A
0x1800190e5  test    [rcx+1Ch], r13b
0x1800190e9  jz      short loc_18001910A
0x1800190eb  mov     rcx, [rcx+10h]
0x1800190ef  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x1800190f6  mov     edx, 31h ; '1'
0x1800190fb  mov     r9d, eax
0x1800190fe  call    WPP_SF_d
0x180019103  mov     rcx, cs:WPP_GLOBAL_Control
0x18001910a  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x180019111  jz      loc_180018EF4
0x180019117  mov     rax, [rbp+57h+var_90]
0x18001911b  lea     rdx, LoadProfileFailed
0x180019122  mov     r9d, 271h
0x180019128  mov     r8d, ebx
0x18001912b  lea     rcx, [rax+8]
0x18001912f  mov     rax, [rax+78h]
0x180019133  mov     [rsp+0D0h+var_A0], rax
0x180019138  mov     [rsp+0D0h+var_A8], rcx
0x18001913d  mov     [rsp+0D0h+var_B0], r12d
0x180019142  call    McTemplateU0qqqjz_EtwEventWriteTransfer
0x180019147  jmp     loc_180018EED
0x18001914c  mov     rcx, [rbp+57h+var_90]; struct _LAN_INTERFACE_CONTEXT *
0x180019150  call    ?IntfInitTimers@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfInitTimers(_LAN_INTERFACE_CONTEXT *)
0x180019155  mov     ebx, eax
0x180019157  test    eax, eax
0x180019159  jz      short loc_180019189
0x18001915b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019162  cmp     rcx, rsi
0x180019165  jz      loc_180018EF4
0x18001916b  cmp     [rcx+19h], r13b
0x18001916f  jb      loc_180018EF4
0x180019175  test    [rcx+1Ch], r13b
0x180019179  jz      loc_180018EF4
0x18001917f  mov     edx, 32h ; '2'
0x180019184  jmp     loc_18001909F
0x180019189  mov     r8, [rbp+57h+var_90]
0x18001918d  lea     rcx, [r8+0B0h]
0x180019194  mov     r8, [r8]
0x180019197  call    ?AceInitStateMachine@@YAKPEAU_ACE_STATE_MACHINE@@W4_ACE_STATE_MACHINE_TYPE@@PEAX@Z; AceInitStateMachine(_ACE_STATE_MACHINE *,_ACE_STATE_MACHINE_TYPE,void *)
0x18001919c  mov     ebx, eax
0x18001919e  test    eax, eax
0x1800191a0  jnz     loc_180018EED
0x1800191a6  mov     rcx, [rbp+57h+var_90]; struct _LAN_INTERFACE_CONTEXT *
0x1800191aa  call    ?IntfDefaultParameters@@YAXPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfDefaultParameters(_LAN_INTERFACE_CONTEXT *)
0x1800191af  mov     rcx, [rbp+57h+var_90]; struct _LAN_INTERFACE_CONTEXT *
0x1800191b3  call    ?IntfReadFromRegistry@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfReadFromRegistry(_LAN_INTERFACE_CONTEXT *)
0x1800191b8  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800191bf  lea     rax, [rbp+57h+var_90]
0x1800191c3  mov     [rsp+0D0h+var_A8], rax
0x1800191c8  mov     r9d, 494E5446h
0x1800191ce  mov     r8d, edi
0x1800191d1  mov     [rsp+0D0h+var_B0], r12d
0x1800191d6  mov     rdx, r14
0x1800191d9  call    cs:__imp_HtReferenceHandleWithTag
0x1800191df  mov     r8, [rbp+57h+var_90]
0x1800191e3  cmp     [r8+0ACh], r12d
0x1800191ea  jz      short loc_180019225
0x1800191ec  lea     rcx, [r8+0B0h]; struct _ACE_STATE_MACHINE *
0x1800191f3  call    ?AceStartStateMachine@@YAKPEAU_ACE_STATE_MACHINE@@@Z; AceStartStateMachine(_ACE_STATE_MACHINE *)
0x1800191f8  mov     rax, [rbp+57h+var_90]
0x1800191fc  xor     r9d, r9d; unsigned int
0x1800191ff  xor     r8d, r8d; void *
0x180019202  mov     [rsp+0D0h+var_B0], r13d; int
0x180019207  mov     edx, r13d; unsigned int
0x18001920a  mov     [rax+0A8h], r12d
0x180019211  mov     rcx, [rbp+57h+var_90]
0x180019215  add     rcx, 0B0h; Context
0x18001921c  call    ?AceInsertTrigger@@YAKPEAU_ACE_STATE_MACHINE@@KPEAXKH@Z; AceInsertTrigger(_ACE_STATE_MACHINE *,ulong,void *,ulong,int)
0x180019221  mov     r8, [rbp+57h+var_90]; void *
0x180019225  lea     rcx, [r8+8]; struct _GUID *
0x180019229  lea     rdx, ?ProfileCallBackIntf@@YAKPEAU_PM_PROFILE@@KPEAX@Z; unsigned int (*)(struct _PM_PROFILE *, unsigned int, void *)
0x180019230  call    ?PmEnumProfiles@@YAKPEAU_GUID@@P6AKPEAU_PM_PROFILE@@KPEAX@Z2@Z; PmEnumProfiles(_GUID *,ulong (*)(_PM_PROFILE *,ulong,void *),void *)
0x180019235  mov     ebx, eax
0x180019237  test    eax, eax
0x180019239  jz      short loc_1800192A2
0x18001923b  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 10h
0x180019242  jz      short loc_180019274
0x180019244  mov     rax, [rbp+57h+var_90]
  ... truncated ...
```
