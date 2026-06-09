# NcaConfigMgrUpdate(void *,void *,void *,void *)

- ea: `0x180006190`
- end: `0x1800063e4`
- name: `?NcaConfigMgrUpdate@@YAXPEAX000@Z`
- size: `596`
- prototype: `void __fastcall(void *, void *, void *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180005770`
- `0x180005d04`
- `0x180006190`
- `0x180006544`
- `0x180006c28`
- `0x18000b7e0`
- `0x180012b6c`
- `0x180016678`
- `0x180019100`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006224`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006224`

## pseudocode

```c
void __fastcall NcaConfigMgrUpdate(void *a1, void *a2, void *a3, void *a4)
{
  PVOID v4; // rcx
  int Policy; // eax
  unsigned int v6; // ebx
  int v7; // edi
  __int128 v8; // xmm4
  __int128 v9; // xmm3
  __int128 v10; // xmm5
  __int128 v11; // xmm6
  __int128 v12; // xmm7
  __int128 v13; // xmm8
  void *v14; // xmm9_8
  __m128i v15; // xmm2
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  PVOID v20; // rcx
  __int128 v21; // [rsp+28h] [rbp-89h] BYREF
  __int128 v22; // [rsp+38h] [rbp-79h]
  __int128 v23; // [rsp+48h] [rbp-69h]
  __int128 v24; // [rsp+58h] [rbp-59h]
  __int128 v25; // [rsp+68h] [rbp-49h]
  __int128 v26; // [rsp+78h] [rbp-39h]
  void *v27; // [rsp+88h] [rbp-29h]

  *(_QWORD *)&v21 = 0;
  memset_0((char *)&v21 + 8, 0, 0x60u);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v4, ConfigUpdateStart, L"Group Policy");
  AcquireSRWLockExclusive(&SRWLock);
  NcaGPTriggerRearm(gNcaConfigMgr);
  Policy = NcaConfigMgrLoadPolicy((struct NCA_POLICY_ *)&v21);
  if ( Policy >= 0 )
  {
    v8 = xmmword_180028BD8;
    v9 = xmmword_180028BC8;
    v10 = xmmword_180028BE8;
    v11 = xmmword_180028BF8;
    v12 = xmmword_180028C08;
    v13 = xmmword_180028C18;
    v14 = qword_180028C28;
    xmmword_180028BD8 = v22;
    xmmword_180028C08 = v25;
    xmmword_180028BE8 = v23;
    xmmword_180028BF8 = v24;
    v15 = _mm_srli_si128((__m128i)v24, 8);
    qword_180028C28 = v27;
    xmmword_180028BC8 = v21;
    xmmword_180028C18 = v26;
    v21 = v9;
    v22 = v8;
    v23 = v10;
    v24 = v11;
    v25 = v12;
    v26 = v13;
    v27 = v14;
    v6 = _mm_cvtsi128_si32(v15);
    v7 = _mm_cvtsi128_si32((__m128i)xmmword_180028BC8);
  }
  else
  {
    v6 = 0;
    v7 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids,
        (unsigned int)Policy);
  }
  NcaExcludeShareLockLeave(0, &SRWLock);
  NcaEvCollProbesRestart();
  NcaDAPEvidenceSnapshotSetGlobalState(20, v6);
  NcaDAPEvidenceSnapshotSetGlobalState(21, v7 != 0);
  NcaConfigMgrPolicyEmpty((struct NCA_POLICY_ *)&v21);
  NcaConfigMgrSendConfigChangedNotification(v17, v16, v18, v19);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v20, ConfigUpdateEnd, L"Group Policy");
}

```

## disassembly

```asm
0x180006190  mov     rax, rsp
0x180006193  push    rbp
0x180006194  push    rbx
0x180006195  push    rdi
0x180006196  push    r15
0x180006198  lea     rbp, [rax-5Fh]
0x18000619c  sub     rsp, 0E8h
0x1800061a3  movaps  xmmword ptr [rax-38h], xmm6
0x1800061a7  lea     rcx, [rsp+100h+var_D8]; void *
0x1800061ac  movaps  xmmword ptr [rax-48h], xmm7
0x1800061b0  xor     edx, edx; Val
0x1800061b2  movaps  xmmword ptr [rax-58h], xmm8
0x1800061b7  movaps  xmmword ptr [rax-68h], xmm9
0x1800061bc  movaps  xmmword ptr [rax-78h], xmm10
0x1800061c1  lea     r8d, [rdx+60h]; Size
0x1800061c5  mov     qword ptr [rsp+100h+var_E8+8], 0
0x1800061ce  call    memset_0
0x1800061d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061da  lea     r15, WPP_GLOBAL_Control
0x1800061e1  cmp     rcx, r15
0x1800061e4  jz      short loc_180006201
0x1800061e6  test    byte ptr [rcx+1Ch], 8
0x1800061ea  jz      short loc_180006201
0x1800061ec  mov     rcx, [rcx+10h]
0x1800061f0  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x1800061f7  mov     edx, 17h
0x1800061fc  call    WPP_SF_
0x180006201  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006208  jz      short loc_18000621D
0x18000620a  lea     r8, aGroupPolicy; "Group Policy"
0x180006211  lea     rdx, ConfigUpdateStart
0x180006218  call    McTemplateU0z_EventWriteTransfer
0x18000621d  lea     rcx, SRWLock; SRWLock
0x180006224  call    cs:__imp_AcquireSRWLockExclusive
0x18000622b  nop     dword ptr [rax+rax+00h]
0x180006230  mov     rcx, cs:?gNcaConfigMgr@@3UNCA_CONFIG_MGR_COMPONENT_@@A; NCA_CONFIG_MGR_COMPONENT_ gNcaConfigMgr
0x180006237  call    NcaGPTriggerRearm
0x18000623c  lea     rcx, [rsp+100h+var_E8+8]; struct NCA_POLICY_ *
0x180006241  call    ?NcaConfigMgrLoadPolicy@@YAJPEAUNCA_POLICY_@@@Z; NcaConfigMgrLoadPolicy(NCA_POLICY_ *)
0x180006246  test    eax, eax
0x180006248  jns     short loc_180006283
0x18000624a  xor     ebx, ebx
0x18000624c  xor     edi, edi
0x18000624e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006255  cmp     rcx, r15
0x180006258  jz      loc_180006337
0x18000625e  test    byte ptr [rcx+1Ch], 1
0x180006262  jz      loc_180006337
0x180006268  mov     rcx, [rcx+10h]
0x18000626c  lea     edx, [rbx+18h]
0x18000626f  mov     r9d, eax
0x180006272  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006279  call    WPP_SF_d
0x18000627e  jmp     loc_180006337
0x180006283  movaps  xmm0, [rbp+57h+var_D0]
0x180006287  movaps  xmm1, [rbp+57h+var_C0]
0x18000628b  movaps  xmm2, [rbp+57h+var_B0]
0x18000628f  movaps  xmm10, [rsp+100h+var_E8+8]
0x180006295  movups  xmm4, cs:xmmword_180028BD8
0x18000629c  movups  xmm3, cs:xmmword_180028BC8
0x1800062a3  movups  xmm5, cs:xmmword_180028BE8
0x1800062aa  movups  xmm6, cs:xmmword_180028BF8
0x1800062b1  movups  xmm7, cs:xmmword_180028C08
0x1800062b8  movups  xmm8, cs:xmmword_180028C18
0x1800062c0  movsd   xmm9, cs:qword_180028C28
0x1800062c9  movups  cs:xmmword_180028BD8, xmm0
0x1800062d0  movaps  xmm0, [rbp+57h+var_A0]
0x1800062d4  movups  cs:xmmword_180028C08, xmm0
0x1800062db  movsd   xmm0, [rbp+57h+var_80]
0x1800062e0  movups  cs:xmmword_180028BE8, xmm1
0x1800062e7  movaps  xmm1, [rbp+57h+var_90]
0x1800062eb  movups  cs:xmmword_180028BF8, xmm2
0x1800062f2  psrldq  xmm2, 8
0x1800062f7  movsd   cs:qword_180028C28, xmm0
0x1800062ff  movups  cs:xmmword_180028BC8, xmm10
0x180006307  movups  cs:xmmword_180028C18, xmm1
0x18000630e  movaps  [rsp+100h+var_E8+8], xmm3
0x180006313  movaps  [rbp+57h+var_D0], xmm4
0x180006317  movaps  [rbp+57h+var_C0], xmm5
0x18000631b  movaps  [rbp+57h+var_B0], xmm6
0x18000631f  movaps  [rbp+57h+var_A0], xmm7
0x180006323  movaps  [rbp+57h+var_90], xmm8
0x180006328  movsd   [rbp+57h+var_80], xmm9
0x18000632e  movd    ebx, xmm2
0x180006332  movd    edi, xmm10
0x180006337  lea     rdx, SRWLock
0x18000633e  xor     ecx, ecx
0x180006340  call    NcaExcludeShareLockLeave
0x180006345  call    NcaEvCollProbesRestart
0x18000634a  mov     edx, ebx
0x18000634c  mov     ecx, 14h
0x180006351  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180006356  xor     edx, edx
0x180006358  mov     ecx, 15h
0x18000635d  test    edi, edi
0x18000635f  setnz   dl
0x180006362  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180006367  lea     rcx, [rsp+100h+var_E8+8]; struct NCA_POLICY_ *
0x18000636c  call    ?NcaConfigMgrPolicyEmpty@@YAXPEAUNCA_POLICY_@@@Z; NcaConfigMgrPolicyEmpty(NCA_POLICY_ *)
0x180006371  call    NcaConfigMgrSendConfigChangedNotification
0x180006376  mov     rcx, cs:WPP_GLOBAL_Control
0x18000637d  cmp     rcx, r15
0x180006380  jz      short loc_18000639D
0x180006382  test    byte ptr [rcx+1Ch], 8
0x180006386  jz      short loc_18000639D
0x180006388  mov     rcx, [rcx+10h]
0x18000638c  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006393  mov     edx, 19h
0x180006398  call    WPP_SF_
0x18000639d  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800063a4  jz      short loc_1800063B9
0x1800063a6  lea     r8, aGroupPolicy; "Group Policy"
0x1800063ad  lea     rdx, ConfigUpdateEnd
0x1800063b4  call    McTemplateU0z_EventWriteTransfer
0x1800063b9  lea     r11, [rsp+100h+var_18]
0x1800063c1  movaps  xmm6, xmmword ptr [r11-18h]
0x1800063c6  movaps  xmm7, xmmword ptr [r11-28h]
0x1800063cb  movaps  xmm8, xmmword ptr [r11-38h]
0x1800063d0  movaps  xmm9, xmmword ptr [r11-48h]
0x1800063d5  movaps  xmm10, xmmword ptr [r11-58h]
0x1800063da  mov     rsp, r11
0x1800063dd  pop     r15
0x1800063df  pop     rdi
0x1800063e0  pop     rbx
0x1800063e1  pop     rbp
0x1800063e2  retn
```
