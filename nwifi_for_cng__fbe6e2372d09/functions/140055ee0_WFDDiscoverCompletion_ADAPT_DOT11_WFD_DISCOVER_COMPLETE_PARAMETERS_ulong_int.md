# WFDDiscoverCompletion(_ADAPT *,_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *,ulong,int)

- ea: `0x140055ee0`
- end: `0x140056255`
- name: `?WFDDiscoverCompletion@@YAXPEAU_ADAPT@@PEAU_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS@@KH@Z`
- size: `885`
- prototype: `void __fastcall(struct _ADAPT *, struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003deb0`
- `0x140055628`
- `0x140056310`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x140030244`
- `0x140055138`
- `0x140055d60`
- `0x140055ee0`
- `0x140056b98`
- `0x140056c44`
- `0x14009bbb0`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056212`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140056212`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056223`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056223`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005619f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005619f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140056131`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140056131`

## pseudocode

```c
void __fastcall WFDDiscoverCompletion(struct _ADAPT *a1, struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *a2, int a3)
{
  unsigned int v3; // r13d
  struct _DOT11_WFD_DEVICE_ENTRY *v4; // r12
  DOT11_WIFI_SCAN_MODULE *p_ScanModule; // r15
  unsigned int v6; // r14d
  int v8; // edx
  unsigned int v9; // edi
  unsigned int v10; // r8d
  __int64 v11; // r9
  __int64 v12; // r9
  int v13; // r8d
  KIRQL v14; // al
  struct DOT11_WIFI_SCAN_REQUEST *pOutstandingInNic; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdx
  int v18; // [rsp+40h] [rbp-68h]
  __int128 v20; // [rsp+50h] [rbp-58h] BYREF

  v3 = 0;
  v4 = 0;
  p_ScanModule = &a1->ScanModule;
  v6 = a3;
  v18 = 1;
  v20 = 0;
  if ( !a2 || (a3 = 24, v6 < 0x18) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_sqD(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, a3, (unsigned int)"PTSTATUS", (char)a2, v6);
    }
    goto LABEL_37;
  }
  v8 = *(unsigned __int8 *)a2;
  if ( (_BYTE)v8 != 0x80 || *((_WORD *)a2 + 1) < 0x18u || !*((_BYTE *)a2 + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_sDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        (_DWORD)WPP_GLOBAL_Control,
        (unsigned int)"PTSTATUS",
        v8,
        *((_WORD *)a2 + 1),
        *((_BYTE *)a2 + 1));
    }
LABEL_37:
    v9 = -1073676267;
    goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      24,
      (unsigned int)WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids,
      (unsigned int)"PTSTATUS",
      *((_DWORD *)a2 + 1));
  }
  v9 = *((_DWORD *)a2 + 1);
  if ( !v9 )
  {
    v10 = *((_DWORD *)a2 + 3);
    if ( v10 > 0x80 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v10, 128);
      }
      v18 = 0;
LABEL_17:
      v3 = *((_DWORD *)a2 + 5);
      v4 = (struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *)((char *)a2 + *((unsigned int *)a2 + 4));
      goto LABEL_38;
    }
    v11 = *((unsigned int *)a2 + 2);
    if ( (_DWORD)v11 != v10
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v11, v10);
    }
    v12 = *((unsigned int *)a2 + 4);
    v13 = *((_DWORD *)a2 + 5);
    if ( v13 + (int)v12 <= v6 )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v12, v13, v6);
    }
    v9 = -1073741811;
  }
LABEL_38:
  v14 = KeAcquireSpinLockRaiseToDpc(&p_ScanModule->Lock.SpinLock);
  pOutstandingInNic = p_ScanModule->pOutstandingInNic;
  p_ScanModule->Lock.OldIrql = v14;
  p_ScanModule->pOutstandingInNic = 0;
  if ( !v9 )
  {
    v9 = WFDCacheSetDiscoveredDevices(v4, v3, p_ScanModule);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer)
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v9);
      }
    }
  }
  KeReleaseSpinLock(&p_ScanModule->Lock.SpinLock, p_ScanModule->Lock.OldIrql);
  if ( pOutstandingInNic )
  {
    v16 = 0;
    *(_QWORD *)&v20 = 1048960;
    v17 = 261;
    if ( !v9 )
      v16 = v3;
    DWORD2(v20) = v16;
    if ( v18 )
      v17 = v9;
    (*((void (__fastcall **)(struct _ADAPT *, __int64, __int128 *, _QWORD, _QWORD, _QWORD))pOutstandingInNic + 3))(
      a1,
      v17,
      &v20,
      *((_QWORD *)pOutstandingInNic + 4),
      *((_QWORD *)pOutstandingInNic + 5),
      *((_QWORD *)pOutstandingInNic + 6));
    _InterlockedDecrement((volatile signed __int32 *)&p_ScanModule->uNumOutstandingScannings);
    if ( *((_QWORD *)pOutstandingInNic - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)pOutstandingInNic - 2), (char *)pOutstandingInNic - 16);
    else
      ExFreePoolWithTag((char *)pOutstandingInNic - 16, *((_DWORD *)pOutstandingInNic - 2));
  }
}

```

## disassembly

```asm
0x140055ee0  mov     [rsp+arg_10], rbx
0x140055ee5  push    rbp
0x140055ee6  push    rsi
0x140055ee7  push    rdi
0x140055ee8  push    r12
0x140055eea  push    r13
0x140055eec  push    r14
0x140055eee  push    r15
0x140055ef0  sub     rsp, 70h
0x140055ef4  mov     rax, cs:__security_cookie
0x140055efb  xor     rax, rsp
0x140055efe  mov     [rsp+0A8h+var_48], rax
0x140055f03  xor     r13d, r13d
0x140055f06  mov     [rsp+0A8h+var_60], rcx
0x140055f0b  xor     r12d, r12d
0x140055f0e  lea     r15, [rcx+88h]
0x140055f15  xorps   xmm0, xmm0
0x140055f18  mov     r14d, r8d
0x140055f1b  mov     rbx, rdx
0x140055f1e  lea     eax, [r13+1]
0x140055f22  mov     [rsp+0A8h+var_68], eax
0x140055f26  movups  [rsp+0A8h+var_58], xmm0
0x140055f2b  test    rdx, rdx
0x140055f2e  jz      loc_1400560E9
0x140055f34  lea     r8d, [r13+18h]
0x140055f38  cmp     r14d, r8d
0x140055f3b  jb      loc_1400560E9
0x140055f41  movzx   edx, byte ptr [rdx]
0x140055f44  cmp     dl, 80h
0x140055f47  jnz     loc_14005609C
0x140055f4d  cmp     [rbx+2], r8w
0x140055f52  jb      loc_14005609C
0x140055f58  cmp     [rbx+1], al
0x140055f5b  jb      loc_14005609C
0x140055f61  mov     rcx, cs:WPP_GLOBAL_Control
0x140055f68  lea     rbp, WPP_GLOBAL_Control
0x140055f6f  lea     esi, [rax+0Fh]
0x140055f72  cmp     rcx, rbp
0x140055f75  jz      short loc_140055FA6
0x140055f77  cmp     byte ptr [rcx+29h], 3
0x140055f7b  jb      short loc_140055FA6
0x140055f7d  mov     eax, [rcx+2Ch]
0x140055f80  test    sil, al
0x140055f83  jz      short loc_140055FA6
0x140055f85  mov     eax, [rbx+4]
0x140055f88  lea     r9, aPtstatus; "PTSTATUS"
0x140055f8f  mov     rcx, [rcx+18h]
0x140055f93  mov     edx, r8d
0x140055f96  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140055f9d  mov     dword ptr [rsp+0A8h+var_88], eax
0x140055fa1  call    WPP_SF_sd
0x140055fa6  mov     edi, [rbx+4]
0x140055fa9  test    edi, edi
0x140055fab  jnz     loc_14005612D
0x140055fb1  mov     r8d, [rbx+0Ch]
0x140055fb5  cmp     r8d, 80h
0x140055fbc  jbe     short loc_14005600B
0x140055fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140055fc5  cmp     rcx, rbp
0x140055fc8  jz      short loc_140055FF6
0x140055fca  cmp     byte ptr [rcx+29h], 2
0x140055fce  jb      short loc_140055FF6
0x140055fd0  mov     eax, [rcx+2Ch]
0x140055fd3  test    sil, al
0x140055fd6  jz      short loc_140055FF6
0x140055fd8  mov     rcx, [rcx+18h]
0x140055fdc  lea     edx, [rdi+19h]
0x140055fdf  mov     r9d, r8d
0x140055fe2  mov     dword ptr [rsp+0A8h+var_88], 80h
0x140055fea  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140055ff1  call    WPP_SF_Dd
0x140055ff6  mov     [rsp+0A8h+var_68], r12d
0x140055ffb  mov     r12d, [rbx+10h]
0x140055fff  mov     r13d, [rbx+14h]
0x140056003  add     r12, rbx
0x140056006  jmp     loc_14005612D
0x14005600b  mov     r9d, [rbx+8]
0x14005600f  cmp     r9d, r8d
0x140056012  jz      short loc_140056048
0x140056014  mov     rcx, cs:WPP_GLOBAL_Control
0x14005601b  cmp     rcx, rbp
0x14005601e  jz      short loc_140056048
0x140056020  cmp     byte ptr [rcx+29h], 2
0x140056024  jb      short loc_140056048
0x140056026  mov     eax, [rcx+2Ch]
0x140056029  test    sil, al
0x14005602c  jz      short loc_140056048
0x14005602e  mov     rcx, [rcx+18h]
0x140056032  mov     edx, 1Ah
0x140056037  mov     dword ptr [rsp+0A8h+var_88], r8d
0x14005603c  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140056043  call    WPP_SF_Dd
0x140056048  mov     r9d, [rbx+10h]
0x14005604c  mov     r8d, [rbx+14h]
0x140056050  lea     eax, [r8+r9]
0x140056054  cmp     eax, r14d
0x140056057  jbe     short loc_140055FFB
0x140056059  mov     rcx, cs:WPP_GLOBAL_Control
0x140056060  cmp     rcx, rbp
0x140056063  jz      short loc_140056092
0x140056065  cmp     byte ptr [rcx+29h], 1
0x140056069  jb      short loc_140056092
0x14005606b  mov     eax, [rcx+2Ch]
0x14005606e  test    sil, al
0x140056071  jz      short loc_140056092
0x140056073  mov     rcx, [rcx+18h]
0x140056077  mov     edx, 1Bh
0x14005607c  mov     dword ptr [rsp+0A8h+var_80], r14d
0x140056081  mov     dword ptr [rsp+0A8h+var_88], r8d
0x140056086  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005608d  call    WPP_SF_lll
0x140056092  mov     edi, 0C000000Dh
0x140056097  jmp     loc_14005612D
0x14005609c  mov     r8, cs:WPP_GLOBAL_Control
0x1400560a3  lea     rbp, WPP_GLOBAL_Control
0x1400560aa  mov     esi, 10h
0x1400560af  cmp     r8, rbp
0x1400560b2  jz      short loc_140056128
0x1400560b4  cmp     [r8+29h], al
0x1400560b8  jb      short loc_140056128
0x1400560ba  mov     eax, [r8+2Ch]
0x1400560be  test    sil, al
0x1400560c1  jz      short loc_140056128
0x1400560c3  movzx   ecx, word ptr [rbx+2]
0x1400560c7  lea     r9, aPtstatus; "PTSTATUS"
0x1400560ce  movzx   eax, byte ptr [rbx+1]
0x1400560d2  mov     [rsp+0A8h+var_78], eax
0x1400560d6  mov     dword ptr [rsp+0A8h+var_80], ecx
0x1400560da  mov     rcx, [r8+18h]
0x1400560de  mov     dword ptr [rsp+0A8h+var_88], edx
0x1400560e2  call    WPP_SF_sDDD
0x1400560e7  jmp     short loc_140056128
0x1400560e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400560f0  lea     rbp, WPP_GLOBAL_Control
0x1400560f7  mov     esi, 10h
0x1400560fc  cmp     rcx, rbp
0x1400560ff  jz      short loc_140056128
0x140056101  cmp     [rcx+29h], al
0x140056104  jb      short loc_140056128
0x140056106  mov     eax, [rcx+2Ch]
0x140056109  test    sil, al
0x14005610c  jz      short loc_140056128
0x14005610e  mov     rcx, [rcx+18h]
0x140056112  lea     r9, aPtstatus; "PTSTATUS"
0x140056119  mov     dword ptr [rsp+0A8h+var_80], r14d
0x14005611e  mov     [rsp+0A8h+var_88], rbx
0x140056123  call    WPP_SF_sqD
0x140056128  mov     edi, 0C0010015h
0x14005612d  lea     rcx, [r15+8]; SpinLock
0x140056131  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140056138  nop     dword ptr [rax+rax+00h]
0x14005613d  mov     rbx, [r15+20h]
0x140056141  mov     [r15+10h], al
0x140056145  mov     qword ptr [r15+20h], 0
0x14005614d  test    edi, edi
0x14005614f  jnz     short loc_140056197
0x140056151  mov     r8, r15; struct DOT11_WIFI_SCAN_MODULE *
0x140056154  mov     edx, r13d; Size
0x140056157  mov     rcx, r12; Src
0x14005615a  call    ?WFDCacheSetDiscoveredDevices@@YAHPEAU_DOT11_WFD_DEVICE_ENTRY@@KPEAUDOT11_WIFI_SCAN_MODULE@@@Z; WFDCacheSetDiscoveredDevices(_DOT11_WFD_DEVICE_ENTRY *,ulong,DOT11_WIFI_SCAN_MODULE *)
0x14005615f  mov     edi, eax
0x140056161  test    eax, eax
0x140056163  jz      short loc_140056197
0x140056165  mov     rax, cs:WPP_GLOBAL_Control
0x14005616c  cmp     rax, rbp
0x14005616f  jz      short loc_140056197
0x140056171  cmp     byte ptr [rax+29h], 1
0x140056175  jb      short loc_140056197
0x140056177  mov     ecx, [rax+2Ch]
0x14005617a  test    sil, cl
0x14005617d  jz      short loc_140056197
0x14005617f  mov     rcx, [rax+18h]
0x140056183  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005618a  mov     edx, 1Ch
0x14005618f  mov     r9d, edi
0x140056192  call    WPP_SF_d
0x140056197  mov     dl, [r15+10h]; NewIrql
0x14005619b  lea     rcx, [r15+8]; SpinLock
0x14005619f  call    cs:__imp_KeReleaseSpinLock
0x1400561a6  nop     dword ptr [rax+rax+00h]
0x1400561ab  test    rbx, rbx
0x1400561ae  jz      short loc_14005622F
0x1400561b0  mov     rcx, [rsp+0A8h+var_60]
0x1400561b5  xor     eax, eax
0x1400561b7  mov     qword ptr [rsp+0A8h+var_58], 100180h
0x1400561c0  test    edi, edi
0x1400561c2  mov     edx, 105h
0x1400561c7  cmovz   eax, r13d
0x1400561cb  cmp     [rsp+0A8h+var_68], 0
0x1400561d0  mov     dword ptr [rsp+0A8h+var_58+8], eax
0x1400561d4  mov     r8, [rbx+30h]
0x1400561d8  cmovnz  edx, edi
0x1400561db  mov     r10, [rbx+28h]
0x1400561df  mov     r9, [rbx+20h]
0x1400561e3  mov     rax, [rbx+18h]
0x1400561e7  mov     [rsp+0A8h+var_80], r8
0x1400561ec  lea     r8, [rsp+0A8h+var_58]
0x1400561f1  mov     [rsp+0A8h+var_88], r10
0x1400561f6  call    _guard_dispatch_icall
0x1400561fb  lock dec dword ptr [r15+18h]
0x140056200  lea     rcx, [rbx-10h]; P
0x140056204  mov     rax, [rcx]
0x140056207  test    rax, rax
0x14005620a  jz      short loc_140056220
0x14005620c  mov     rdx, rcx; Entry
0x14005620f  mov     rcx, rax; Lookaside
0x140056212  call    cs:__imp_ExFreeToNPagedLookasideList
0x140056219  nop     dword ptr [rax+rax+00h]
0x14005621e  jmp     short loc_14005622F
0x140056220  mov     edx, [rcx+8]; Tag
0x140056223  call    cs:__imp_ExFreePoolWithTag
0x14005622a  nop     dword ptr [rax+rax+00h]
0x14005622f  mov     rcx, [rsp+0A8h+var_48]
0x140056234  xor     rcx, rsp; StackCookie
0x140056237  call    __security_check_cookie
0x14005623c  mov     rbx, [rsp+0A8h+arg_10]
0x140056244  add     rsp, 70h
0x140056248  pop     r15
0x14005624a  pop     r14
0x14005624c  pop     r13
0x14005624e  pop     r12
0x140056250  pop     rdi
0x140056251  pop     rsi
0x140056252  pop     rbp
0x140056253  retn
```
