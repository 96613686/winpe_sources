# WimRemoveInterface(ushort const *)

- ea: `0x180011ee4`
- end: `0x1800121f8`
- name: `?WimRemoveInterface@@YAKPEBG@Z`
- size: `788`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180011014`

## callees

- `0x1800025f0`
- `0x18000a718`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000aa58`
- `0x18000c230`
- `0x18000f440`
- `0x18000f47c`
- `0x1800109dc`
- `0x180011ee4`
- `0x180012998`
- `0x180013264`
- `0x1800178cc`
- `0x180024e2c`
- `0x18003a028`

## import_xrefs

- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001216e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18001216e`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180012136`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180012136`

## pseudocode

```c
__int64 __fastcall WimRemoveInterface(const unsigned __int16 *a1)
{
  struct _LIST_ENTRY *v2; // rcx
  unsigned int v3; // ebx
  unsigned int InterfaceEntry; // eax
  _QWORD *v5; // rdi
  _QWORD *v6; // rax
  void **v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8
  struct _LIST_ENTRY *v10; // rcx
  __int64 v11; // rdx
  struct _LAN_INTERFACE_CONTEXT *v13; // [rsp+30h] [rbp-49h] BYREF
  void *lpMem[2]; // [rsp+40h] [rbp-39h] BYREF
  struct _L2_NOTIFICATION_DATA v15; // [rsp+50h] [rbp-29h] BYREF
  struct _GUID v16; // [rsp+80h] [rbp+7h] BYREF

  lpMem[0] = 0;
  v16 = 0;
  v13 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 57, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = DeviceGuidStringToGuid(a1, &v16);
    if ( v3 )
      goto LABEL_45;
    v3 = LockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext);
    if ( v3 )
      goto LABEL_45;
    InterfaceEntry = WimGetInterfaceEntry(&v16, (struct _LAN_INTERFACE_ENTRY **)lpMem);
    v5 = lpMem[0];
    v3 = InterfaceEntry;
    if ( InterfaceEntry )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 59, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, InterfaceEntry);
      }
    }
    else if ( lpMem[0] )
    {
      v6 = *(_QWORD **)lpMem[0];
      if ( *(void **)(*(_QWORD *)lpMem[0] + 8LL) != lpMem[0]
        || (v7 = (void **)*((_QWORD *)lpMem[0] + 1), *v7 != lpMem[0]) )
      {
        __fastfail(3u);
      }
      *v7 = v6;
      v6[1] = v7;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_S(
          WPP_GLOBAL_Control[1].Flink,
          (unsigned int)(LODWORD(lpMem[0]) + 60),
          WPP_41caf6f8117b3ad837214700da2680fc_Traceguids,
          a1);
      }
      v3 = 87;
    }
    UnlockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext);
    if ( v3 )
      goto LABEL_45;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control[1].Flink, 61, v8, &v16);
    }
    *(struct _GUID *)lpMem = v16;
    if ( (int)RemoveInterfaceFromInterfaceStateNameList(WNF_MUR_MEDIA_UI_REQUEST_LAN, (struct _GUID *)lpMem) >= 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 4u
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_42;
      }
      v11 = 63;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_42;
      }
      v11 = 62;
    }
    WPP_SF__guid_(v10[1].Flink, v11, v9, &v16);
LABEL_42:
    if ( !(unsigned int)HtReferenceHandleWithTag(g_hHandleTable, v5[2], 0, 1448036676, 0, &v13) )
    {
      Dot3LogAdapterAddRemoveEvent((unsigned __int16 *)v13 + 12, *((unsigned __int16 **)v13 + 15), 0);
      IntfDeinitContext(v13);
    }
    HtDereferenceHandleWithTag(g_hHandleTable, v5[2], 0, 1);
    Dot3Free(v5);
    v15.NotificationSource = 1;
    *(_OWORD *)&v15.dwDataSize = 0;
    v15.InterfaceGuid = v16;
    v15.NotificationCode = 2;
    NhNotify(0, &v15);
LABEL_45:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_46;
  }
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v2[1].Blink) && (BYTE4(v2[1].Blink) & 1) != 0 )
  {
    WPP_SF_(v2[1].Flink, 58, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 87;
LABEL_46:
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v2[1].Blink) >= 4u && (BYTE4(v2[1].Blink) & 1) != 0 )
    WPP_SF_d(v2[1].Flink, 64, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180011ee4  push    rbp
0x180011ee6  push    rbx
0x180011ee7  push    rsi
0x180011ee8  push    rdi
0x180011ee9  push    r12
0x180011eeb  push    r14
0x180011eed  lea     rbp, [rsp-2Fh]
0x180011ef2  sub     rsp, 0A8h
0x180011ef9  mov     rax, cs:__security_cookie
0x180011f00  xor     rax, rsp
0x180011f03  mov     [rbp+57h+var_40], rax
0x180011f07  xorps   xmm0, xmm0
0x180011f0a  mov     [rbp+57h+lpMem], 0
0x180011f12  movups  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180011f16  mov     rsi, rcx
0x180011f19  mov     [rbp+57h+var_A0], 0
0x180011f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f28  lea     r12, WPP_GLOBAL_Control
0x180011f2f  mov     r14d, 1
0x180011f35  cmp     rcx, r12
0x180011f38  jz      short loc_180011F61
0x180011f3a  cmp     byte ptr [rcx+19h], 4
0x180011f3e  jb      short loc_180011F61
0x180011f40  test    [rcx+1Ch], r14b
0x180011f44  jz      short loc_180011F61
0x180011f46  mov     rcx, [rcx+10h]
0x180011f4a  lea     edx, [r14+38h]
0x180011f4e  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011f55  call    WPP_SF_
0x180011f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f61  test    rsi, rsi
0x180011f64  jnz     short loc_180011F9B
0x180011f66  cmp     rcx, r12
0x180011f69  jz      short loc_180011F91
0x180011f6b  cmp     [rcx+19h], r14b
0x180011f6f  jb      short loc_180011F91
0x180011f71  test    [rcx+1Ch], r14b
0x180011f75  jz      short loc_180011F91
0x180011f77  mov     rcx, [rcx+10h]
0x180011f7b  lea     edx, [rsi+3Ah]
0x180011f7e  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011f85  call    WPP_SF_
0x180011f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f91  mov     ebx, 57h ; 'W'
0x180011f96  jmp     loc_1800121AA
0x180011f9b  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x180011f9f  mov     rcx, rsi; unsigned __int16 *
0x180011fa2  call    ?DeviceGuidStringToGuid@@YAKPEBGPEAU_GUID@@@Z; DeviceGuidStringToGuid(ushort const *,_GUID *)
0x180011fa7  mov     ebx, eax
0x180011fa9  test    eax, eax
0x180011fab  jnz     loc_1800121A3
0x180011fb1  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x180011fb8  call    ?LockLanIntfmgrState@@YAKAEAULAN_INTFMGR_CONTEXT@@@Z; LockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x180011fbd  mov     ebx, eax
0x180011fbf  test    eax, eax
0x180011fc1  jnz     loc_1800121A3
0x180011fc7  lea     rdx, [rbp+57h+lpMem]; struct _LAN_INTERFACE_ENTRY **
0x180011fcb  lea     rcx, [rbp+57h+var_50]; struct _GUID *
0x180011fcf  call    ?WimGetInterfaceEntry@@YAKPEBU_GUID@@PEAPEAU_LAN_INTERFACE_ENTRY@@@Z; WimGetInterfaceEntry(_GUID const *,_LAN_INTERFACE_ENTRY * *)
0x180011fd4  mov     rdi, [rbp+57h+lpMem]
0x180011fd8  mov     ebx, eax
0x180011fda  test    eax, eax
0x180011fdc  jz      short loc_180012014
0x180011fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fe5  cmp     rcx, r12
0x180011fe8  jz      loc_18001206F
0x180011fee  cmp     [rcx+19h], r14b
0x180011ff2  jb      short loc_18001206F
0x180011ff4  test    [rcx+1Ch], r14b
0x180011ff8  jz      short loc_18001206F
0x180011ffa  mov     rcx, [rcx+10h]
0x180011ffe  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180012005  mov     edx, 3Bh ; ';'
0x18001200a  mov     r9d, eax
0x18001200d  call    WPP_SF_d
0x180012012  jmp     short loc_18001206F
0x180012014  test    rdi, rdi
0x180012017  jnz     short loc_18001204E
0x180012019  mov     rcx, cs:WPP_GLOBAL_Control
0x180012020  cmp     rcx, r12
0x180012023  jz      short loc_180012047
0x180012025  cmp     [rcx+19h], r14b
0x180012029  jb      short loc_180012047
0x18001202b  test    [rcx+1Ch], r14b
0x18001202f  jz      short loc_180012047
0x180012031  mov     rcx, [rcx+10h]
0x180012035  lea     edx, [rdi+3Ch]
0x180012038  mov     r9, rsi
0x18001203b  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180012042  call    WPP_SF_S
0x180012047  mov     ebx, 57h ; 'W'
0x18001204c  jmp     short loc_18001206F
0x18001204e  mov     rax, [rdi]
0x180012051  cmp     [rax+8], rdi
0x180012055  jnz     loc_1800121F1
0x18001205b  mov     rdx, [rdi+8]
0x18001205f  cmp     [rdx], rdi
0x180012062  jnz     loc_1800121F1
0x180012068  mov     [rdx], rax
0x18001206b  mov     [rax+8], rdx
0x18001206f  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x180012076  call    ?UnlockLanIntfmgrState@@YAXAEAULAN_INTFMGR_CONTEXT@@@Z; UnlockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x18001207b  test    ebx, ebx
0x18001207d  jnz     loc_1800121A3
0x180012083  mov     rcx, cs:WPP_GLOBAL_Control
0x18001208a  cmp     rcx, r12
0x18001208d  jz      short loc_1800120AB
0x18001208f  cmp     byte ptr [rcx+19h], 4
0x180012093  jb      short loc_1800120AB
0x180012095  test    [rcx+1Ch], r14b
0x180012099  jz      short loc_1800120AB
0x18001209b  mov     rcx, [rcx+10h]
0x18001209f  lea     edx, [rbx+3Dh]
0x1800120a2  lea     r9, [rbp+57h+var_50]
0x1800120a6  call    WPP_SF__guid_
0x1800120ab  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Data1]
0x1800120af  lea     rdx, [rbp+57h+lpMem]; struct _GUID
0x1800120b3  mov     rcx, qword ptr cs:WNF_MUR_MEDIA_UI_REQUEST_LAN.Data; struct _WNF_STATE_NAME
0x1800120ba  movdqa  xmmword ptr [rbp+57h+lpMem], xmm0
0x1800120bf  call    ?RemoveInterfaceFromInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@U_GUID@@@Z; RemoveInterfaceFromInterfaceStateNameList(_WNF_STATE_NAME,_GUID)
0x1800120c4  test    eax, eax
0x1800120c6  jns     short loc_1800120E7
0x1800120c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120cf  cmp     rcx, r12
0x1800120d2  jz      short loc_180012111
0x1800120d4  cmp     [rcx+19h], r14b
0x1800120d8  jb      short loc_180012111
0x1800120da  test    [rcx+1Ch], r14b
0x1800120de  jz      short loc_180012111
0x1800120e0  mov     edx, 3Eh ; '>'
0x1800120e5  jmp     short loc_180012104
0x1800120e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120ee  cmp     rcx, r12
0x1800120f1  jz      short loc_180012111
0x1800120f3  cmp     byte ptr [rcx+19h], 4
0x1800120f7  jb      short loc_180012111
0x1800120f9  test    [rcx+1Ch], r14b
0x1800120fd  jz      short loc_180012111
0x1800120ff  mov     edx, 3Fh ; '?'
0x180012104  mov     rcx, [rcx+10h]
0x180012108  lea     r9, [rbp+57h+var_50]
0x18001210c  call    WPP_SF__guid_
0x180012111  mov     rdx, [rdi+10h]
0x180012115  lea     rax, [rbp+57h+var_A0]
0x180012119  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180012120  mov     r9d, 564F4944h
0x180012126  mov     [rsp+0D0h+var_A8], rax
0x18001212b  xor     r8d, r8d
0x18001212e  mov     [rsp+0D0h+var_B0], 0
0x180012136  call    cs:__imp_HtReferenceHandleWithTag
0x18001213c  test    eax, eax
0x18001213e  jnz     short loc_18001215D
0x180012140  mov     rdx, [rbp+57h+var_A0]
0x180012144  xor     r8d, r8d; int
0x180012147  lea     rcx, [rdx+18h]; unsigned __int16 *
0x18001214b  mov     rdx, [rdx+78h]; unsigned __int16 *
0x18001214f  call    ?Dot3LogAdapterAddRemoveEvent@@YAKPEAG0H@Z; Dot3LogAdapterAddRemoveEvent(ushort *,ushort *,int)
0x180012154  mov     rcx, [rbp+57h+var_A0]; struct _LAN_INTERFACE_CONTEXT *
0x180012158  call    ?IntfDeinitContext@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfDeinitContext(_LAN_INTERFACE_CONTEXT *)
0x18001215d  mov     rdx, [rdi+10h]
0x180012161  mov     r9d, r14d
0x180012164  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18001216b  xor     r8d, r8d
0x18001216e  call    cs:__imp_HtDereferenceHandleWithTag
0x180012174  mov     rcx, rdi; lpMem
0x180012177  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001217c  xorps   xmm0, xmm0
0x18001217f  mov     [rbp+57h+var_80.NotificationSource], r14d
0x180012183  movdqu  xmmword ptr [rbp+57h+var_80.dwDataSize], xmm0
0x180012188  lea     rdx, [rbp+57h+var_80]; struct _L2_NOTIFICATION_DATA *
0x18001218c  xor     ecx, ecx; void *
0x18001218e  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Data1]
0x180012192  movdqu  xmmword ptr [rbp+57h+var_80.InterfaceGuid.Data1], xmm0
0x180012197  mov     [rbp+57h+var_80.NotificationCode], 2
0x18001219e  call    ?NhNotify@@YAKPEAXPEAU_L2_NOTIFICATION_DATA@@@Z; NhNotify(void *,_L2_NOTIFICATION_DATA *)
0x1800121a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121aa  cmp     rcx, r12
0x1800121ad  jz      short loc_1800121D3
0x1800121af  cmp     byte ptr [rcx+19h], 4
0x1800121b3  jb      short loc_1800121D3
0x1800121b5  test    [rcx+1Ch], r14b
0x1800121b9  jz      short loc_1800121D3
0x1800121bb  mov     rcx, [rcx+10h]
0x1800121bf  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x1800121c6  mov     edx, 40h ; '@'
0x1800121cb  mov     r9d, ebx
0x1800121ce  call    WPP_SF_d
0x1800121d3  mov     eax, ebx
0x1800121d5  mov     rcx, [rbp+57h+var_40]
0x1800121d9  xor     rcx, rsp; StackCookie
0x1800121dc  call    __security_check_cookie
0x1800121e1  add     rsp, 0A8h
0x1800121e8  pop     r14
0x1800121ea  pop     r12
0x1800121ec  pop     rdi
0x1800121ed  pop     rsi
0x1800121ee  pop     rbx
0x1800121ef  pop     rbp
0x1800121f0  retn
0x1800121f1  mov     ecx, 3
0x1800121f6  int     29h; Win8: RtlFailFast(ecx)
```
