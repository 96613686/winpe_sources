# WFDDiscoverCompletion(_ADAPT *,_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *,ulong,int)

- ea: `0x1400546c0`
- end: `0x140054a35`
- name: `?WFDDiscoverCompletion@@YAXPEAU_ADAPT@@PEAU_DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS@@KH@Z`
- size: `885`
- prototype: `void __fastcall(struct _ADAPT *, struct _DOT11_WFD_DISCOVER_COMPLETE_PARAMETERS *, unsigned int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003dc90`
- `0x140053e08`
- `0x140054af0`

## callees

- `0x140020dc0`
- `0x140020f20`
- `0x14002ffb4`
- `0x140053918`
- `0x140054540`
- `0x1400546c0`
- `0x140055378`
- `0x140055424`
- `0x14009a3d0`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400549f2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400549f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054a03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054a03`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005497f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005497f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140054911`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140054911`

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
  __int64 v15; // r9
  struct DOT11_WIFI_SCAN_REQUEST *pOutstandingInNic; // rbx
  unsigned int v17; // eax
  __int64 v18; // rdx
  int v19; // [rsp+40h] [rbp-68h]
  __int128 v21; // [rsp+50h] [rbp-58h] BYREF

  v3 = 0;
  v4 = 0;
  p_ScanModule = &a1->ScanModule;
  v6 = a3;
  v19 = 1;
  v21 = 0;
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
      v19 = 0;
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
    v9 = WFDCacheSetDiscoveredDevices(v4, v3, p_ScanModule, v15);
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
    v17 = 0;
    *(_QWORD *)&v21 = 1048960;
    v18 = 261;
    if ( !v9 )
      v17 = v3;
    DWORD2(v21) = v17;
    if ( v19 )
      v18 = v9;
    (*((void (__fastcall **)(struct _ADAPT *, __int64, __int128 *, _QWORD, _QWORD, _QWORD))pOutstandingInNic + 3))(
      a1,
      v18,
      &v21,
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
0x1400546c0  mov     [rsp+arg_10], rbx
0x1400546c5  push    rbp
0x1400546c6  push    rsi
0x1400546c7  push    rdi
0x1400546c8  push    r12
0x1400546ca  push    r13
0x1400546cc  push    r14
0x1400546ce  push    r15
0x1400546d0  sub     rsp, 70h
0x1400546d4  mov     rax, cs:__security_cookie
0x1400546db  xor     rax, rsp
0x1400546de  mov     [rsp+0A8h+var_48], rax
0x1400546e3  xor     r13d, r13d
0x1400546e6  mov     [rsp+0A8h+var_60], rcx
0x1400546eb  xor     r12d, r12d
0x1400546ee  lea     r15, [rcx+88h]
0x1400546f5  xorps   xmm0, xmm0
0x1400546f8  mov     r14d, r8d
0x1400546fb  mov     rbx, rdx
0x1400546fe  lea     eax, [r13+1]
0x140054702  mov     [rsp+0A8h+var_68], eax
0x140054706  movups  [rsp+0A8h+var_58], xmm0
0x14005470b  test    rdx, rdx
0x14005470e  jz      loc_1400548C9
0x140054714  lea     r8d, [r13+18h]
0x140054718  cmp     r14d, r8d
0x14005471b  jb      loc_1400548C9
0x140054721  movzx   edx, byte ptr [rdx]
0x140054724  cmp     dl, 80h
0x140054727  jnz     loc_14005487C
0x14005472d  cmp     [rbx+2], r8w
0x140054732  jb      loc_14005487C
0x140054738  cmp     [rbx+1], al
0x14005473b  jb      loc_14005487C
0x140054741  mov     rcx, cs:WPP_GLOBAL_Control
0x140054748  lea     rbp, WPP_GLOBAL_Control
0x14005474f  lea     esi, [rax+0Fh]
0x140054752  cmp     rcx, rbp
0x140054755  jz      short loc_140054786
0x140054757  cmp     byte ptr [rcx+29h], 3
0x14005475b  jb      short loc_140054786
0x14005475d  mov     eax, [rcx+2Ch]
0x140054760  test    sil, al
0x140054763  jz      short loc_140054786
0x140054765  mov     eax, [rbx+4]
0x140054768  lea     r9, aPtstatus; "PTSTATUS"
0x14005476f  mov     rcx, [rcx+18h]
0x140054773  mov     edx, r8d
0x140054776  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005477d  mov     dword ptr [rsp+0A8h+var_88], eax
0x140054781  call    WPP_SF_sd
0x140054786  mov     edi, [rbx+4]
0x140054789  test    edi, edi
0x14005478b  jnz     loc_14005490D
0x140054791  mov     r8d, [rbx+0Ch]
0x140054795  cmp     r8d, 80h
0x14005479c  jbe     short loc_1400547EB
0x14005479e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400547a5  cmp     rcx, rbp
0x1400547a8  jz      short loc_1400547D6
0x1400547aa  cmp     byte ptr [rcx+29h], 2
0x1400547ae  jb      short loc_1400547D6
0x1400547b0  mov     eax, [rcx+2Ch]
0x1400547b3  test    sil, al
0x1400547b6  jz      short loc_1400547D6
0x1400547b8  mov     rcx, [rcx+18h]
0x1400547bc  lea     edx, [rdi+19h]
0x1400547bf  mov     r9d, r8d
0x1400547c2  mov     dword ptr [rsp+0A8h+var_88], 80h
0x1400547ca  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x1400547d1  call    WPP_SF_Dd
0x1400547d6  mov     [rsp+0A8h+var_68], r12d
0x1400547db  mov     r12d, [rbx+10h]
0x1400547df  mov     r13d, [rbx+14h]
0x1400547e3  add     r12, rbx
0x1400547e6  jmp     loc_14005490D
0x1400547eb  mov     r9d, [rbx+8]
0x1400547ef  cmp     r9d, r8d
0x1400547f2  jz      short loc_140054828
0x1400547f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400547fb  cmp     rcx, rbp
0x1400547fe  jz      short loc_140054828
0x140054800  cmp     byte ptr [rcx+29h], 2
0x140054804  jb      short loc_140054828
0x140054806  mov     eax, [rcx+2Ch]
0x140054809  test    sil, al
0x14005480c  jz      short loc_140054828
0x14005480e  mov     rcx, [rcx+18h]
0x140054812  mov     edx, 1Ah
0x140054817  mov     dword ptr [rsp+0A8h+var_88], r8d
0x14005481c  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140054823  call    WPP_SF_Dd
0x140054828  mov     r9d, [rbx+10h]
0x14005482c  mov     r8d, [rbx+14h]
0x140054830  lea     eax, [r8+r9]
0x140054834  cmp     eax, r14d
0x140054837  jbe     short loc_1400547DB
0x140054839  mov     rcx, cs:WPP_GLOBAL_Control
0x140054840  cmp     rcx, rbp
0x140054843  jz      short loc_140054872
0x140054845  cmp     byte ptr [rcx+29h], 1
0x140054849  jb      short loc_140054872
0x14005484b  mov     eax, [rcx+2Ch]
0x14005484e  test    sil, al
0x140054851  jz      short loc_140054872
0x140054853  mov     rcx, [rcx+18h]
0x140054857  mov     edx, 1Bh
0x14005485c  mov     dword ptr [rsp+0A8h+var_80], r14d
0x140054861  mov     dword ptr [rsp+0A8h+var_88], r8d
0x140054866  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005486d  call    WPP_SF_lll
0x140054872  mov     edi, 0C000000Dh
0x140054877  jmp     loc_14005490D
0x14005487c  mov     r8, cs:WPP_GLOBAL_Control
0x140054883  lea     rbp, WPP_GLOBAL_Control
0x14005488a  mov     esi, 10h
0x14005488f  cmp     r8, rbp
0x140054892  jz      short loc_140054908
0x140054894  cmp     [r8+29h], al
0x140054898  jb      short loc_140054908
0x14005489a  mov     eax, [r8+2Ch]
0x14005489e  test    sil, al
0x1400548a1  jz      short loc_140054908
0x1400548a3  movzx   ecx, word ptr [rbx+2]
0x1400548a7  lea     r9, aPtstatus; "PTSTATUS"
0x1400548ae  movzx   eax, byte ptr [rbx+1]
0x1400548b2  mov     [rsp+0A8h+var_78], eax
0x1400548b6  mov     dword ptr [rsp+0A8h+var_80], ecx
0x1400548ba  mov     rcx, [r8+18h]
0x1400548be  mov     dword ptr [rsp+0A8h+var_88], edx
0x1400548c2  call    WPP_SF_sDDD
0x1400548c7  jmp     short loc_140054908
0x1400548c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400548d0  lea     rbp, WPP_GLOBAL_Control
0x1400548d7  mov     esi, 10h
0x1400548dc  cmp     rcx, rbp
0x1400548df  jz      short loc_140054908
0x1400548e1  cmp     [rcx+29h], al
0x1400548e4  jb      short loc_140054908
0x1400548e6  mov     eax, [rcx+2Ch]
0x1400548e9  test    sil, al
0x1400548ec  jz      short loc_140054908
0x1400548ee  mov     rcx, [rcx+18h]
0x1400548f2  lea     r9, aPtstatus; "PTSTATUS"
0x1400548f9  mov     dword ptr [rsp+0A8h+var_80], r14d
0x1400548fe  mov     [rsp+0A8h+var_88], rbx
0x140054903  call    WPP_SF_sqD
0x140054908  mov     edi, 0C0010015h
0x14005490d  lea     rcx, [r15+8]; SpinLock
0x140054911  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140054918  nop     dword ptr [rax+rax+00h]
0x14005491d  mov     rbx, [r15+20h]
0x140054921  mov     [r15+10h], al
0x140054925  mov     qword ptr [r15+20h], 0
0x14005492d  test    edi, edi
0x14005492f  jnz     short loc_140054977
0x140054931  mov     r8, r15; struct DOT11_WIFI_SCAN_MODULE *
0x140054934  mov     edx, r13d; Size
0x140054937  mov     rcx, r12; Src
0x14005493a  call    ?WFDCacheSetDiscoveredDevices@@YAHPEAU_DOT11_WFD_DEVICE_ENTRY@@KPEAUDOT11_WIFI_SCAN_MODULE@@@Z; WFDCacheSetDiscoveredDevices(_DOT11_WFD_DEVICE_ENTRY *,ulong,DOT11_WIFI_SCAN_MODULE *)
0x14005493f  mov     edi, eax
0x140054941  test    eax, eax
0x140054943  jz      short loc_140054977
0x140054945  mov     rax, cs:WPP_GLOBAL_Control
0x14005494c  cmp     rax, rbp
0x14005494f  jz      short loc_140054977
0x140054951  cmp     byte ptr [rax+29h], 1
0x140054955  jb      short loc_140054977
0x140054957  mov     ecx, [rax+2Ch]
0x14005495a  test    sil, cl
0x14005495d  jz      short loc_140054977
0x14005495f  mov     rcx, [rax+18h]
0x140054963  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x14005496a  mov     edx, 1Ch
0x14005496f  mov     r9d, edi
0x140054972  call    WPP_SF_d
0x140054977  mov     dl, [r15+10h]; NewIrql
0x14005497b  lea     rcx, [r15+8]; SpinLock
0x14005497f  call    cs:__imp_KeReleaseSpinLock
0x140054986  nop     dword ptr [rax+rax+00h]
0x14005498b  test    rbx, rbx
0x14005498e  jz      short loc_140054A0F
0x140054990  mov     rcx, [rsp+0A8h+var_60]
0x140054995  xor     eax, eax
0x140054997  mov     qword ptr [rsp+0A8h+var_58], 100180h
0x1400549a0  test    edi, edi
0x1400549a2  mov     edx, 105h
0x1400549a7  cmovz   eax, r13d
0x1400549ab  cmp     [rsp+0A8h+var_68], 0
0x1400549b0  mov     dword ptr [rsp+0A8h+var_58+8], eax
0x1400549b4  mov     r8, [rbx+30h]
0x1400549b8  cmovnz  edx, edi
0x1400549bb  mov     r10, [rbx+28h]
0x1400549bf  mov     r9, [rbx+20h]
0x1400549c3  mov     rax, [rbx+18h]
0x1400549c7  mov     [rsp+0A8h+var_80], r8
0x1400549cc  lea     r8, [rsp+0A8h+var_58]
0x1400549d1  mov     [rsp+0A8h+var_88], r10
0x1400549d6  call    _guard_dispatch_icall
0x1400549db  lock dec dword ptr [r15+18h]
0x1400549e0  lea     rcx, [rbx-10h]; P
0x1400549e4  mov     rax, [rcx]
0x1400549e7  test    rax, rax
0x1400549ea  jz      short loc_140054A00
0x1400549ec  mov     rdx, rcx; Entry
0x1400549ef  mov     rcx, rax; Lookaside
0x1400549f2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400549f9  nop     dword ptr [rax+rax+00h]
0x1400549fe  jmp     short loc_140054A0F
0x140054a00  mov     edx, [rcx+8]; Tag
0x140054a03  call    cs:__imp_ExFreePoolWithTag
0x140054a0a  nop     dword ptr [rax+rax+00h]
0x140054a0f  mov     rcx, [rsp+0A8h+var_48]
0x140054a14  xor     rcx, rsp; StackCookie
0x140054a17  call    __security_check_cookie
0x140054a1c  mov     rbx, [rsp+0A8h+arg_10]
0x140054a24  add     rsp, 70h
0x140054a28  pop     r15
0x140054a2a  pop     r14
0x140054a2c  pop     r13
0x140054a2e  pop     r12
0x140054a30  pop     rdi
0x140054a31  pop     rsi
0x140054a32  pop     rbp
0x140054a33  retn
```
