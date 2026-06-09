# FwMoneisGetAppContainer

- ea: `0x180070e74`
- end: `0x1800711fd`
- name: `FwMoneisGetAppContainer`
- size: `905`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180070d70`

## callees

- `0x18000a710`
- `0x1800511b4`
- `0x180070e74`
- `0x1800729c0`
- `0x180073488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800711c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800711d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800711c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800711d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070f5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070fad`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070f5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180070fad`
- `fwbase!FwHResultToWindowsError` at `0x180071013`
- `fwbase!FwHResultToWindowsError` at `0x18007108d`
- `fwbase!FwHResultToWindowsError` at `0x180071013`
- `fwbase!FwHResultToWindowsError` at `0x18007108d`
- `fwbase!FwStringBuild` at `0x180071005`
- `fwbase!FwStringBuild` at `0x180071005`
- `fwbase!FwAlloc` at `0x18007110a`
- `fwbase!FwAlloc` at `0x18007110a`
- `fwbase!FwCriticalSectionEnter` at `0x18007105b`
- `fwbase!FwCriticalSectionEnter` at `0x18007105b`
- `fwbase!FwCriticalSectionLeave` at `0x1800710db`
- `fwbase!FwCriticalSectionLeave` at `0x1800710f7`
- `fwbase!FwCriticalSectionLeave` at `0x1800710db`
- `fwbase!FwCriticalSectionLeave` at `0x1800710f7`
- `fwbase!FwFree` at `0x1800711ad`
- `fwbase!FwFree` at `0x1800711ad`
- `FWPolicyIOMgr!FwGetRule` at `0x18007107f`
- `FWPolicyIOMgr!FwGetRule` at `0x18007107f`
- `FWPolicyIOMgr!FwFreeRules` at `0x180071198`
- `FWPolicyIOMgr!FwFreeRules` at `0x180071198`

## pseudocode

```c
__int64 __fastcall FwMoneisGetAppContainer(
        void *a1,
        int a2,
        __int64 a3,
        struct _SID *a4,
        struct _SID *Sid,
        __int64 *a6)
{
  unsigned int LastError; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  unsigned int Rule; // eax
  unsigned int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rax
  int v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR v21; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-10h] BYREF

  v18 = 0;
  *a6 = 0;
  StringSid = 0;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  LastError = FwMoneisValidateAppContainerOperation(a1, a2, 0, a4, Sid, &v18);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 130;
LABEL_5:
      v11 = LastError;
LABEL_6:
      WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v11);
    }
  }
  else if ( v18 )
  {
    if ( ConvertSidToStringSidW(a4, &StringSid) )
    {
      if ( ConvertSidToStringSidW(Sid, &v21) )
      {
        v12 = FwStringBuild(&v20, v21, StringSid, 0);
        LastError = FwHResultToWindowsError(v12);
        v8 = LastError;
        if ( LastError )
        {
          v9 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v10 = 134;
            goto LABEL_5;
          }
        }
        else
        {
          FwCriticalSectionEnter((char *)gFwIsolationManager + 24);
          Rule = FwGetRule(*((_QWORD *)gFwIsolationManager + 9), 3, v20, &v19);
          v14 = FwHResultToWindowsError(Rule);
          v8 = v14;
          if ( v14 )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                135,
                WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
                v14);
            }
            FwCriticalSectionLeave((char *)gFwIsolationManager + 24);
          }
          else
          {
            FwCriticalSectionLeave((char *)gFwIsolationManager + 24);
            v15 = FwAlloc(88);
            if ( v15 )
            {
              v16 = v19;
              *(_OWORD *)v15 = *(_OWORD *)(v19 + 24);
              *(_OWORD *)(v15 + 16) = *(_OWORD *)(v16 + 40);
              *(_OWORD *)(v15 + 32) = *(_OWORD *)(v16 + 56);
              *(_OWORD *)(v15 + 48) = *(_OWORD *)(v16 + 72);
              *(_OWORD *)(v15 + 64) = *(_OWORD *)(v16 + 88);
              *(_QWORD *)(v15 + 80) = *(_QWORD *)(v16 + 104);
              memset_0((void *)(v19 + 24), 0, 0x58u);
              *a6 = v15;
            }
            else
            {
              v8 = 14;
              v9 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v10 = 136;
                v11 = 14;
                goto LABEL_6;
              }
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v10 = 133;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v10 = 132;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = 131;
      v11 = 0;
      goto LABEL_6;
    }
  }
  FwFreeRules(v19, 3);
  if ( v20 )
    FwFree(v20);
  if ( v21 )
    LocalFree(v21);
  if ( StringSid )
    LocalFree(StringSid);
  return v8;
}

```

## disassembly

```asm
0x180070e74  push    rbp
0x180070e76  push    rbx
0x180070e77  push    rsi
0x180070e78  push    rdi
0x180070e79  push    r14
0x180070e7b  mov     rbp, rsp
0x180070e7e  sub     rsp, 60h
0x180070e82  mov     rax, cs:__security_cookie
0x180070e89  xor     rax, rsp
0x180070e8c  mov     [rbp+var_8], rax
0x180070e90  mov     r14, [rbp+arg_28]
0x180070e94  lea     rax, [rbp+var_30]
0x180070e98  mov     rsi, [rbp+Sid]
0x180070e9c  xor     r8d, r8d; int
0x180070e9f  mov     [rsp+60h+var_38], rax; int *
0x180070ea4  mov     rdi, r9
0x180070ea7  mov     [rbp+var_30], 0
0x180070eae  mov     qword ptr [r14], 0
0x180070eb5  mov     [rbp+StringSid], 0
0x180070ebd  mov     [rbp+var_18], 0
0x180070ec5  mov     [rbp+var_20], 0
0x180070ecd  mov     [rbp+var_28], 0
0x180070ed5  mov     [rsp+60h+var_40], rsi; struct _SID *
0x180070eda  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x180070edf  mov     ebx, eax
0x180070ee1  test    eax, eax
0x180070ee3  jz      short loc_180070F23
0x180070ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180070eec  lea     rdx, WPP_GLOBAL_Control
0x180070ef3  cmp     rcx, rdx
0x180070ef6  jz      loc_18007118F
0x180070efc  test    byte ptr [rcx+1Ch], 1
0x180070f00  jz      loc_18007118F
0x180070f06  mov     edx, 82h
0x180070f0b  mov     r9d, eax
0x180070f0e  mov     rcx, [rcx+10h]
0x180070f12  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x180070f19  call    WPP_SF_d
0x180070f1e  jmp     loc_18007118F
0x180070f23  cmp     [rbp+var_30], 0
0x180070f27  jnz     short loc_180070F56
0x180070f29  xor     ebx, ebx
0x180070f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180070f32  lea     rdx, WPP_GLOBAL_Control
0x180070f39  cmp     rcx, rdx
0x180070f3c  jz      loc_18007118F
0x180070f42  test    byte ptr [rcx+1Ch], 1
0x180070f46  jz      loc_18007118F
0x180070f4c  mov     edx, 83h
0x180070f51  xor     r9d, r9d
0x180070f54  jmp     short loc_180070F0E
0x180070f56  lea     rdx, [rbp+StringSid]; StringSid
0x180070f5a  mov     rcx, rdi; Sid
0x180070f5d  call    cs:__imp_ConvertSidToStringSidW
0x180070f64  nop     dword ptr [rax+rax+00h]
0x180070f69  test    eax, eax
0x180070f6b  jnz     short loc_180070FA6
0x180070f6d  call    cs:__imp_GetLastError
0x180070f74  nop     dword ptr [rax+rax+00h]
0x180070f79  mov     ebx, eax
0x180070f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180070f82  lea     rdx, WPP_GLOBAL_Control
0x180070f89  cmp     rcx, rdx
0x180070f8c  jz      loc_18007118F
0x180070f92  test    byte ptr [rcx+1Ch], 1
0x180070f96  jz      loc_18007118F
0x180070f9c  mov     edx, 84h
0x180070fa1  jmp     loc_180070F0B
0x180070fa6  lea     rdx, [rbp+var_18]; StringSid
0x180070faa  mov     rcx, rsi; Sid
0x180070fad  call    cs:__imp_ConvertSidToStringSidW
0x180070fb4  nop     dword ptr [rax+rax+00h]
0x180070fb9  test    eax, eax
0x180070fbb  jnz     short loc_180070FF6
0x180070fbd  call    cs:__imp_GetLastError
0x180070fc4  nop     dword ptr [rax+rax+00h]
0x180070fc9  mov     ebx, eax
0x180070fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180070fd2  lea     rdx, WPP_GLOBAL_Control
0x180070fd9  cmp     rcx, rdx
0x180070fdc  jz      loc_18007118F
0x180070fe2  test    byte ptr [rcx+1Ch], 1
0x180070fe6  jz      loc_18007118F
0x180070fec  mov     edx, 85h
0x180070ff1  jmp     loc_180070F0B
0x180070ff6  mov     r8, [rbp+StringSid]
0x180070ffa  lea     rcx, [rbp+var_20]
0x180070ffe  mov     rdx, [rbp+var_18]
0x180071002  xor     r9d, r9d
0x180071005  call    cs:__imp_FwStringBuild
0x18007100c  nop     dword ptr [rax+rax+00h]
0x180071011  mov     ecx, eax
0x180071013  call    cs:__imp_FwHResultToWindowsError
0x18007101a  nop     dword ptr [rax+rax+00h]
0x18007101f  mov     ebx, eax
0x180071021  test    eax, eax
0x180071023  jz      short loc_180071050
0x180071025  mov     rcx, cs:WPP_GLOBAL_Control
0x18007102c  lea     rdx, WPP_GLOBAL_Control
0x180071033  cmp     rcx, rdx
0x180071036  jz      loc_18007118F
0x18007103c  test    byte ptr [rcx+1Ch], 1
0x180071040  jz      loc_18007118F
0x180071046  mov     edx, 86h
0x18007104b  jmp     loc_180070F0B
0x180071050  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x180071057  add     rcx, 18h
0x18007105b  call    cs:__imp_FwCriticalSectionEnter
0x180071062  nop     dword ptr [rax+rax+00h]
0x180071067  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x18007106e  lea     r9, [rbp+var_28]
0x180071072  mov     r8, [rbp+var_20]
0x180071076  mov     edx, 3
0x18007107b  mov     rcx, [rcx+48h]
0x18007107f  call    cs:__imp_FwGetRule
0x180071086  nop     dword ptr [rax+rax+00h]
0x18007108b  mov     ecx, eax
0x18007108d  call    cs:__imp_FwHResultToWindowsError
0x180071094  nop     dword ptr [rax+rax+00h]
0x180071099  mov     ebx, eax
0x18007109b  test    eax, eax
0x18007109d  jz      short loc_1800710EC
0x18007109f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800710a6  lea     rdx, WPP_GLOBAL_Control
0x1800710ad  cmp     rcx, rdx
0x1800710b0  jz      short loc_1800710D0
0x1800710b2  test    byte ptr [rcx+1Ch], 1
0x1800710b6  jz      short loc_1800710D0
0x1800710b8  mov     rcx, [rcx+10h]
0x1800710bc  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800710c3  mov     edx, 87h
0x1800710c8  mov     r9d, eax
0x1800710cb  call    WPP_SF_d
0x1800710d0  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800710d7  add     rcx, 18h
0x1800710db  call    cs:__imp_FwCriticalSectionLeave
0x1800710e2  nop     dword ptr [rax+rax+00h]
0x1800710e7  jmp     loc_18007118F
0x1800710ec  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800710f3  add     rcx, 18h
0x1800710f7  call    cs:__imp_FwCriticalSectionLeave
0x1800710fe  nop     dword ptr [rax+rax+00h]
0x180071103  mov     esi, 58h ; 'X'
0x180071108  mov     ecx, esi
0x18007110a  call    cs:__imp_FwAlloc
0x180071111  nop     dword ptr [rax+rax+00h]
0x180071116  mov     rdi, rax
0x180071119  test    rax, rax
0x18007111c  jnz     short loc_180071145
0x18007111e  lea     ebx, [rsi-4Ah]
0x180071121  mov     rcx, cs:WPP_GLOBAL_Control
0x180071128  lea     rdx, WPP_GLOBAL_Control
0x18007112f  cmp     rcx, rdx
0x180071132  jz      short loc_18007118F
0x180071134  test    byte ptr [rcx+1Ch], 1
0x180071138  jz      short loc_18007118F
0x18007113a  lea     edx, [rsi+30h]
0x18007113d  mov     r9d, ebx
0x180071140  jmp     loc_180070F0E
0x180071145  mov     rax, [rbp+var_28]
0x180071149  mov     r8, rsi; Size
0x18007114c  xor     edx, edx; Val
0x18007114e  movups  xmm0, xmmword ptr [rax+18h]
0x180071152  movups  xmmword ptr [rdi], xmm0
0x180071155  movups  xmm1, xmmword ptr [rax+28h]
0x180071159  movups  xmmword ptr [rdi+10h], xmm1
0x18007115d  movups  xmm0, xmmword ptr [rax+38h]
0x180071161  movups  xmmword ptr [rdi+20h], xmm0
0x180071165  movups  xmm1, xmmword ptr [rax+48h]
0x180071169  movups  xmmword ptr [rdi+30h], xmm1
0x18007116d  movups  xmm0, xmmword ptr [rax+58h]
0x180071171  movups  xmmword ptr [rdi+40h], xmm0
0x180071175  movsd   xmm1, qword ptr [rax+68h]
0x18007117a  movsd   qword ptr [rdi+50h], xmm1
0x18007117f  mov     rcx, [rbp+var_28]
0x180071183  add     rcx, 18h; void *
0x180071187  call    memset_0
0x18007118c  mov     [r14], rdi
0x18007118f  mov     rcx, [rbp+var_28]
0x180071193  mov     edx, 3
0x180071198  call    cs:__imp_FwFreeRules
0x18007119f  nop     dword ptr [rax+rax+00h]
0x1800711a4  mov     rcx, [rbp+var_20]
0x1800711a8  test    rcx, rcx
0x1800711ab  jz      short loc_1800711B9
0x1800711ad  call    cs:__imp_FwFree
0x1800711b4  nop     dword ptr [rax+rax+00h]
0x1800711b9  mov     rcx, [rbp+var_18]; hMem
0x1800711bd  test    rcx, rcx
0x1800711c0  jz      short loc_1800711CE
0x1800711c2  call    cs:__imp_LocalFree
0x1800711c9  nop     dword ptr [rax+rax+00h]
0x1800711ce  mov     rcx, [rbp+StringSid]; hMem
0x1800711d2  test    rcx, rcx
0x1800711d5  jz      short loc_1800711E3
0x1800711d7  call    cs:__imp_LocalFree
0x1800711de  nop     dword ptr [rax+rax+00h]
0x1800711e3  mov     eax, ebx
0x1800711e5  mov     rcx, [rbp+var_8]
0x1800711e9  xor     rcx, rsp; StackCookie
0x1800711ec  call    __security_check_cookie
0x1800711f1  add     rsp, 60h
0x1800711f5  pop     r14
0x1800711f7  pop     rdi
0x1800711f8  pop     rsi
0x1800711f9  pop     rbx
0x1800711fa  pop     rbp
0x1800711fb  retn
```
