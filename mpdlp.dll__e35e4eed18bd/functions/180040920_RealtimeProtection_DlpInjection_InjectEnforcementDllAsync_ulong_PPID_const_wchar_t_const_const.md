# RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(ulong,PPID const &,wchar_t const * const)

- ea: `0x180040920`
- end: `0x180040cd7`
- name: `?InjectEnforcementDllAsync@DlpInjection@RealtimeProtection@@YAJKAEBUPPID@@QEB_W@Z`
- size: `951`
- prototype: `int(RealtimeProtection::DlpInjection *__hidden this, unsigned int, const struct PPID *, const wchar_t *const)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a630`
- `0x18018d9f0`
- `0x18020c1dc`

## callees

- `0x180040290`
- `0x180040920`
- `0x180040cd8`
- `0x180040d60`
- `0x1800410ec`
- `0x180046d10`
- `0x180080030`
- `0x1800809d0`
- `0x180088cb4`
- `0x1800890e0`
- `0x180089510`
- `0x1800ab660`
- `0x18010cb40`
- `0x18010ce44`
- `0x18023a310`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x1800409ca`
- `MpClient!MpConfigGetValue` at `0x1800409ca`
- `MpClient!MpConfigClose` at `0x180040a22`
- `MpClient!MpConfigClose` at `0x180040aa4`
- `MpClient!MpConfigClose` at `0x180040b1b`
- `MpClient!MpConfigClose` at `0x180040bf7`
- `MpClient!MpConfigClose` at `0x180040c5d`
- `MpClient!MpConfigClose` at `0x180040a22`
- `MpClient!MpConfigClose` at `0x180040aa4`
- `MpClient!MpConfigClose` at `0x180040b1b`
- `MpClient!MpConfigClose` at `0x180040bf7`
- `MpClient!MpConfigClose` at `0x180040c5d`
- `MpClient!MpConfigOpen` at `0x180040983`
- `MpClient!MpConfigOpen` at `0x180040983`

## string_xrefs

- `0x18004097c`: `Miscellaneous Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(
        RealtimeProtection::DlpInjection *this,
        const struct PPID *a2,
        const struct PPID *a3,
        const wchar_t *const a4)
{
  unsigned int v6; // r13d
  int v7; // eax
  unsigned int v8; // esi
  int v9; // esi
  int Value; // r14d
  PVOID *v11; // rcx
  int IsValidTargetForMpDetoursInjectionFromEngine; // eax
  unsigned int v14; // esi
  void *v15; // rbx
  RealtimeProtection::DlpPlugin *v16; // rcx
  struct RealtimeProtection::CPluginWorkItemQueue *PluginWorkItemQueue; // rax
  volatile signed __int32 *v18; // rax
  CommonUtil::CRefObject *v19; // rbx
  bool *v20; // [rsp+20h] [rbp-78h]
  wchar_t v21[8]; // [rsp+30h] [rbp-68h] BYREF
  bool v22[4]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v23; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-48h] BYREF
  void *v25; // [rsp+58h] [rbp-40h] BYREF

  v6 = (unsigned int)this;
  if ( (unsigned int)RealtimeProtection::DlpPlugin::IsPluginInitialized(this) )
  {
    if ( (unsigned int)RealtimeProtection::DlpPlugin::IsKillbitActive(0x2000000000000000LL) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids);
      return 0;
    }
    else
    {
      v23 = 0;
      v7 = MpConfigOpen(L"Miscellaneous Configuration", &v23);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids,
            (unsigned int)v7);
        if ( v23 )
          MpConfigClose();
        return v8;
      }
      else
      {
        v9 = 0;
        v24 = 0;
        *(_DWORD *)v22 = 0;
        LODWORD(v25) = 4;
        Value = MpConfigGetValue(v23, L"DisableInjection", &v24, &v25, v22, 0, *(_DWORD *)v21);
        if ( Value >= 0 )
        {
          if ( v24 > 1 )
          {
            Value = -2147023267;
          }
          else if ( (_DWORD)v25 )
          {
            v9 = *(_DWORD *)v22;
          }
          else
          {
            *(_DWORD *)v22 = 0;
          }
        }
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids,
            (unsigned int)Value,
            v9);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( Value || v9 != 1 )
        {
          LOBYTE(v21[0]) = 1;
          IsValidTargetForMpDetoursInjectionFromEngine = RealtimeProtection::DlpInjection::GetIsValidTargetForMpDetoursInjectionFromEngine(
                                                           (RealtimeProtection::DlpInjection *)v6,
                                                           (unsigned int)a2,
                                                           a3,
                                                           v21,
                                                           v20);
          v14 = IsValidTargetForMpDetoursInjectionFromEngine;
          if ( IsValidTargetForMpDetoursInjectionFromEngine < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids,
                (unsigned int)IsValidTargetForMpDetoursInjectionFromEngine);
            if ( v23 )
              MpConfigClose();
            return v14;
          }
          else if ( LOBYTE(v21[0]) )
          {
            v15 = operator new(0x78u);
            v25 = v15;
            memset(v15, 0, 0x78u);
            PluginWorkItemQueue = RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(v16);
            v18 = (volatile signed __int32 *)RealtimeProtection::CDlpInjectEnforcementDllWorkItem::CDlpInjectEnforcementDllWorkItem(
                                               (RealtimeProtection::CDlpInjectEnforcementDllWorkItem *)v15,
                                               PluginWorkItemQueue,
                                               a2,
                                               (const wchar_t *)a3);
            v19 = (CommonUtil::CRefObject *)v18;
            if ( v18 )
              _InterlockedIncrement(v18 + 2);
            RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(v18, 5);
            if ( v19 )
              CommonUtil::CRefObject::Release(v19);
            if ( v23 )
              MpConfigClose();
            return 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids, a3);
            if ( v23 )
              MpConfigClose();
            return 0;
          }
        }
        else
        {
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
            WPP_SF_(v11[2], 30, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids);
          if ( v23 )
            MpConfigClose();
          return 0;
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180040920  mov     [rsp+arg_18], rbx
0x180040925  push    rsi
0x180040926  push    r12
0x180040928  push    r13
0x18004092a  push    r14
0x18004092c  push    r15
0x18004092e  sub     rsp, 70h
0x180040932  mov     rax, cs:__security_cookie
0x180040939  xor     rax, rsp
0x18004093c  mov     [rsp+98h+var_38], rax
0x180040941  mov     r15, r8
0x180040944  mov     r12, rdx
0x180040947  mov     r13d, ecx
0x18004094a  call    ?IsPluginInitialized@DlpPlugin@RealtimeProtection@@YAHXZ; RealtimeProtection::DlpPlugin::IsPluginInitialized(void)
0x18004094f  test    eax, eax
0x180040951  jz      loc_180040B51
0x180040957  mov     rcx, 2000000000000000h
0x180040961  call    ?IsKillbitActive@DlpPlugin@RealtimeProtection@@YAHW4FeatureKillbit@@@Z; RealtimeProtection::DlpPlugin::IsKillbitActive(FeatureKillbit)
0x180040966  test    eax, eax
0x180040968  jnz     loc_180040B86
0x18004096e  mov     [rsp+98h+var_50], 0
0x180040977  lea     rdx, [rsp+98h+var_50]
0x18004097c  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x180040983  call    cs:__imp_MpConfigOpen
0x180040989  mov     esi, eax
0x18004098b  test    eax, eax
0x18004098d  js      loc_180040BBB
0x180040993  xor     esi, esi
0x180040995  mov     [rsp+98h+var_48], esi
0x180040999  mov     dword ptr [rsp+98h+var_58], esi
0x18004099d  mov     dword ptr [rsp+98h+var_40], 4
0x1800409a5  mov     [rsp+98h+var_70], rsi
0x1800409aa  lea     rax, [rsp+98h+var_58]
0x1800409af  mov     [rsp+98h+var_78], rax; bool *
0x1800409b4  lea     r9, [rsp+98h+var_40]
0x1800409b9  lea     r8, [rsp+98h+var_48]
0x1800409be  lea     rdx, aDisableinjecti; "DisableInjection"
0x1800409c5  mov     rcx, [rsp+98h+var_50]
0x1800409ca  call    cs:__imp_MpConfigGetValue
0x1800409d0  mov     r14d, eax
0x1800409d3  test    eax, eax
0x1800409d5  js      short loc_1800409E8
0x1800409d7  cmp     [rsp+98h+var_48], 1
0x1800409dc  ja      short loc_180040A53
0x1800409de  cmp     dword ptr [rsp+98h+var_40], esi
0x1800409e2  jnz     short loc_180040A4D
0x1800409e4  mov     dword ptr [rsp+98h+var_58], esi
0x1800409e8  lea     rbx, WPP_GLOBAL_Control
0x1800409ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800409f6  cmp     rcx, rbx
0x1800409f9  jz      short loc_180040A05
0x1800409fb  test    byte ptr [rcx+1Ch], 4
0x1800409ff  jnz     loc_180040B29
0x180040a05  test    r14d, r14d
0x180040a08  jnz     short loc_180040A5B
0x180040a0a  cmp     esi, 1
0x180040a0d  jnz     short loc_180040A5B
0x180040a0f  cmp     rcx, rbx
0x180040a12  jnz     loc_180040C04
0x180040a18  mov     rcx, [rsp+98h+var_50]
0x180040a1d  test    rcx, rcx
0x180040a20  jz      short loc_180040A28
0x180040a22  call    cs:__imp_MpConfigClose
0x180040a28  xor     eax, eax
0x180040a2a  mov     rcx, [rsp+98h+var_38]
0x180040a2f  xor     rcx, rsp; StackCookie
0x180040a32  call    __security_check_cookie
0x180040a37  mov     rbx, [rsp+98h+arg_18]
0x180040a3f  add     rsp, 70h
0x180040a43  pop     r15
0x180040a45  pop     r14
0x180040a47  pop     r13
0x180040a49  pop     r12
0x180040a4b  pop     rsi
0x180040a4c  retn
0x180040a4d  mov     esi, dword ptr [rsp+98h+var_58]
0x180040a51  jmp     short loc_1800409E8
0x180040a53  mov     r14d, 8007065Dh
0x180040a59  jmp     short loc_1800409E8
0x180040a5b  mov     byte ptr [rsp+98h+var_68], 1
0x180040a60  lea     r9, [rsp+98h+var_68]; wchar_t *
0x180040a65  mov     r8, r15; struct PPID *
0x180040a68  mov     rdx, r12; unsigned int
0x180040a6b  mov     ecx, r13d; this
0x180040a6e  call    ?GetIsValidTargetForMpDetoursInjectionFromEngine@DlpInjection@RealtimeProtection@@YAJKAEBUPPID@@PEB_WPEA_N@Z; RealtimeProtection::DlpInjection::GetIsValidTargetForMpDetoursInjectionFromEngine(ulong,PPID const &,wchar_t const *,bool *)
0x180040a73  mov     esi, eax
0x180040a75  test    eax, eax
0x180040a77  js      loc_180040C28
0x180040a7d  cmp     byte ptr [rsp+98h+var_68], 0
0x180040a82  jnz     short loc_180040AB1
0x180040a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a8b  cmp     rcx, rbx
0x180040a8e  jz      short loc_180040A9A
0x180040a90  test    byte ptr [rcx+1Ch], 2
0x180040a94  jnz     loc_180040C6A
0x180040a9a  mov     rcx, [rsp+98h+var_50]
0x180040a9f  test    rcx, rcx
0x180040aa2  jz      short loc_180040AAA
0x180040aa4  call    cs:__imp_MpConfigClose
0x180040aaa  xor     eax, eax
0x180040aac  jmp     loc_180040A2A
0x180040ab1  mov     esi, 78h ; 'x'
0x180040ab6  mov     ecx, esi; Size
0x180040ab8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040abd  mov     rbx, rax
0x180040ac0  mov     [rsp+98h+var_40], rax
0x180040ac5  mov     r8d, esi; Size
0x180040ac8  xor     edx, edx; Val
0x180040aca  mov     rcx, rax; void *
0x180040acd  call    memset
0x180040ad2  call    ?GetPluginWorkItemQueue@DlpPlugin@RealtimeProtection@@YAPEAVCPluginWorkItemQueue@2@XZ; RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(void)
0x180040ad7  mov     r9, r15; wchar_t *
0x180040ada  mov     r8, r12; struct PPID *
0x180040add  mov     rdx, rax; struct RealtimeProtection::CPluginWorkItemQueue *
0x180040ae0  mov     rcx, rbx; this
0x180040ae3  call    ??0CDlpInjectEnforcementDllWorkItem@RealtimeProtection@@QEAA@PEAVCPluginWorkItemQueue@1@AEBUPPID@@PEB_W@Z; RealtimeProtection::CDlpInjectEnforcementDllWorkItem::CDlpInjectEnforcementDllWorkItem(RealtimeProtection::CPluginWorkItemQueue *,PPID const &,wchar_t const *)
0x180040ae8  mov     rbx, rax
0x180040aeb  test    rax, rax
0x180040aee  jz      short loc_180040AF4
0x180040af0  lock inc dword ptr [rax+8]
0x180040af4  mov     edx, 5
0x180040af9  mov     rcx, rbx
0x180040afc  call    ?PrioritizedDispatchJob@CMpPluginWorkItemBase@RealtimeProtection@@UEAAXW4tagMP_THREAD_POOL_PRIORITY@@@Z; RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(tagMP_THREAD_POOL_PRIORITY)
0x180040b01  xor     esi, esi
0x180040b03  test    rbx, rbx
0x180040b06  jz      short loc_180040B11
0x180040b08  mov     rcx, rbx; this
0x180040b0b  call    ?Release@CRefObject@CommonUtil@@QEBAJXZ; CommonUtil::CRefObject::Release(void)
0x180040b10  nop
0x180040b11  mov     rcx, [rsp+98h+var_50]
0x180040b16  test    rcx, rcx
0x180040b19  jz      short loc_180040B22
0x180040b1b  call    cs:__imp_MpConfigClose
0x180040b21  nop
0x180040b22  mov     eax, esi
0x180040b24  jmp     loc_180040A2A
0x180040b29  mov     edx, 1Dh
0x180040b2e  mov     dword ptr [rsp+98h+var_78], esi
0x180040b32  mov     r9d, r14d
0x180040b35  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040b3c  mov     rcx, [rcx+10h]
0x180040b40  call    WPP_SF_Dd
0x180040b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b4c  jmp     loc_180040A05
0x180040b51  lea     rbx, WPP_GLOBAL_Control
0x180040b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b5f  cmp     rcx, rbx
0x180040b62  jz      short loc_180040B7F
0x180040b64  test    byte ptr [rcx+1Ch], 2
0x180040b68  jz      short loc_180040B7F
0x180040b6a  mov     edx, 1Ah
0x180040b6f  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040b76  mov     rcx, [rcx+10h]
0x180040b7a  call    WPP_SF_
0x180040b7f  xor     eax, eax
0x180040b81  jmp     loc_180040A2A
0x180040b86  lea     rbx, WPP_GLOBAL_Control
0x180040b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b94  cmp     rcx, rbx
0x180040b97  jz      short loc_180040BB4
0x180040b99  test    byte ptr [rcx+1Ch], 2
0x180040b9d  jz      short loc_180040BB4
0x180040b9f  mov     edx, 1Bh
0x180040ba4  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040bab  mov     rcx, [rcx+10h]
0x180040baf  call    WPP_SF_
0x180040bb4  xor     eax, eax
0x180040bb6  jmp     loc_180040A2A
0x180040bbb  lea     rbx, WPP_GLOBAL_Control
0x180040bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180040bc9  cmp     rcx, rbx
0x180040bcc  jz      short loc_180040BED
0x180040bce  test    byte ptr [rcx+1Ch], 1
0x180040bd2  jz      short loc_180040BED
0x180040bd4  mov     edx, 1Ch
0x180040bd9  mov     r9d, esi
0x180040bdc  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040be3  mov     rcx, [rcx+10h]
0x180040be7  call    WPP_SF_d
0x180040bec  nop
0x180040bed  mov     rcx, [rsp+98h+var_50]
0x180040bf2  test    rcx, rcx
0x180040bf5  jz      short loc_180040BFD
0x180040bf7  call    cs:__imp_MpConfigClose
0x180040bfd  mov     eax, esi
0x180040bff  jmp     loc_180040A2A
0x180040c04  test    byte ptr [rcx+1Ch], 2
0x180040c08  jz      loc_180040A18
0x180040c0e  mov     edx, 1Eh
0x180040c13  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040c1a  mov     rcx, [rcx+10h]
0x180040c1e  call    WPP_SF_
0x180040c23  jmp     loc_180040A18
0x180040c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c2f  cmp     rcx, rbx
0x180040c32  jz      short loc_180040C53
0x180040c34  test    byte ptr [rcx+1Ch], 1
0x180040c38  jz      short loc_180040C53
0x180040c3a  mov     edx, 1Fh
0x180040c3f  mov     r9d, esi
0x180040c42  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040c49  mov     rcx, [rcx+10h]
0x180040c4d  call    WPP_SF_d
0x180040c52  nop
0x180040c53  mov     rcx, [rsp+98h+var_50]
0x180040c58  test    rcx, rcx
0x180040c5b  jz      short loc_180040C63
0x180040c5d  call    cs:__imp_MpConfigClose
0x180040c63  mov     eax, esi
0x180040c65  jmp     loc_180040A2A
0x180040c6a  mov     edx, 20h ; ' '
0x180040c6f  mov     r9, r15
0x180040c72  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040c79  mov     rcx, [rcx+10h]
0x180040c7d  call    WPP_SF_S
0x180040c82  jmp     loc_180040A9A
0x180040c87  mov     esi, dword ptr [rsp+98h+var_58]
0x180040c8b  test    esi, esi
0x180040c8d  jns     loc_180040B22
0x180040c93  jmp     short loc_180040C99
0x180040c95  mov     esi, dword ptr [rsp+98h+var_58]
0x180040c99  lea     rbx, WPP_GLOBAL_Control
0x180040ca0  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ca7  cmp     rcx, rbx
0x180040caa  jz      loc_180040B22
0x180040cb0  test    byte ptr [rcx+1Ch], 1
0x180040cb4  jz      loc_180040B22
0x180040cba  mov     edx, 21h ; '!'
0x180040cbf  mov     r9d, esi
0x180040cc2  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x180040cc9  mov     rcx, [rcx+10h]
0x180040ccd  call    WPP_SF_d
0x180040cd2  jmp     loc_180040B22
```
