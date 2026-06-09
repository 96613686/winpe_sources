# NetworkListManager::SetSimulatedProfileInfo(NP_SIMULATED_PROFILE_INFO *,ulong,int)

- ea: `0x1800c5e90`
- end: `0x1800c619c`
- name: `?SetSimulatedProfileInfo@NetworkListManager@@UEAAJPEAUNP_SIMULATED_PROFILE_INFO@@KH@Z`
- size: `780`
- prototype: `__int64 __fastcall(NetworkListManager *this, struct NP_SIMULATED_PROFILE_INFO *, unsigned int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800badd0`
- `0x1800bade0`

## callees

- `0x180009990`
- `0x18000c018`
- `0x18000fab0`
- `0x180010340`
- `0x180015710`
- `0x180026a10`
- `0x1800459ac`
- `0x18004e024`
- `0x1800c5e90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c60b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c60b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c5f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c5f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c6012`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c6012`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800c5fe5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800c5fe5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NetworkListManager::SetSimulatedProfileInfo(
        NetworkListManager *this,
        struct NP_SIMULATED_PROFILE_INFO *a2,
        unsigned int a3,
        int a4)
{
  int v8; // edi
  __int64 v9; // rcx
  struct NP_SIMULATED_PROFILE_INFO *v10; // rax
  unsigned int ClientInformation; // ebx
  PVOID *v12; // rcx
  _OWORD *v14; // r15
  __int64 v15; // rdx
  const WCHAR *v16; // rdx
  _DWORD *v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // edi
  unsigned int v20; // eax
  const char *v21; // r8
  unsigned int v22; // edi
  unsigned int v23; // [rsp+40h] [rbp-68h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-60h] BYREF
  GUID v25; // [rsp+50h] [rbp-58h] BYREF
  int v26; // [rsp+60h] [rbp-48h]

  v23 = 0;
  v8 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
  StandbyMonitor::ProcessClientActivity(18);
  if ( !a2 )
  {
LABEL_8:
    ClientInformation = -2147024809;
LABEL_9:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v9 = 255;
  v10 = a2;
  while ( *(_WORD *)v10 )
  {
    v10 = (struct NP_SIMULATED_PROFILE_INFO *)((char *)v10 + 2);
    if ( !--v9 )
      goto LABEL_8;
  }
  ClientInformation = HrGetClientInformation(&v23, 0, 0);
  if ( (ClientInformation & 0x80000000) != 0 )
    goto LABEL_9;
  v14 = CoTaskMemAlloc(0x20Cu);
  if ( v14 )
  {
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)this + 40);
    v16 = (const WCHAR *)*((_QWORD *)this + 155);
    if ( v16 )
    {
      if ( lstrcmpW((LPCWSTR)a2, v16) )
      {
        v8 = 1;
        v26 = 1;
      }
      v17 = (_DWORD *)*((_QWORD *)this + 155);
      if ( *((_DWORD *)a2 + 128) != v17[128] )
        v26 = v8 | 2;
      CoTaskMemFree(v17);
    }
    else
    {
      v26 = 3;
    }
    *((_QWORD *)this + 155) = v14;
    v18 = 4;
    do
    {
      *v14 = *(_OWORD *)a2;
      v14[1] = *((_OWORD *)a2 + 1);
      v14[2] = *((_OWORD *)a2 + 2);
      v14[3] = *((_OWORD *)a2 + 3);
      v14[4] = *((_OWORD *)a2 + 4);
      v14[5] = *((_OWORD *)a2 + 5);
      v14[6] = *((_OWORD *)a2 + 6);
      v14[7] = *((_OWORD *)a2 + 7);
      v14 += 8;
      a2 = (struct NP_SIMULATED_PROFILE_INFO *)((char *)a2 + 128);
      --v18;
    }
    while ( v18 );
    *(_OWORD *)((char *)v14 - 4) = *(_OWORD *)((char *)a2 - 4);
    v19 = v23;
    *((_DWORD *)this + 312) = v23;
    if ( a3 == -1 && a4 )
      a3 = v19;
    *((_DWORD *)this + 313) = a3;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    if ( a3 != -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, v19, a3);
      v25 = CLSID_NetworkStateChangeEventDataFactory;
      v20 = PubSebEdgeEventValueInternal(WNF_SEB_NETWORK_STATE_CHANGES, a3, &v25);
      v22 = v20;
      if ( v20 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, v20);
        ClientInformation = v22 | 0x10000000;
      }
      StandbyMonitor::ProcessServerWnf(WNF_SEB_NETWORK_STATE_CHANGES, (struct _WNF_STATE_NAME)&stru_18017E0E8, v21);
      goto LABEL_9;
    }
    ClientInformation = -2147023728;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return ClientInformation;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_10;
    v15 = 199;
    goto LABEL_19;
  }
  ClientInformation = -2147024882;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return ClientInformation;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 196;
LABEL_19:
    WPP_SF_(v12[2], v15, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
    goto LABEL_9;
  }
LABEL_10:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(v12[2], 200, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, ClientInformation);
  return ClientInformation;
}

```

## disassembly

```asm
0x1800c5e90  push    rbx
0x1800c5e92  push    rsi
0x1800c5e93  push    rdi
0x1800c5e94  push    r12
0x1800c5e96  push    r13
0x1800c5e98  push    r14
0x1800c5e9a  push    r15
0x1800c5e9c  sub     rsp, 70h
0x1800c5ea0  mov     r12d, r9d
0x1800c5ea3  mov     r14d, r8d
0x1800c5ea6  mov     rsi, rdx
0x1800c5ea9  mov     r13, rcx
0x1800c5eac  xor     r15d, r15d
0x1800c5eaf  mov     [rsp+0A8h+var_68], r15d
0x1800c5eb4  mov     edi, r15d
0x1800c5eb7  mov     [rsp+0A8h+var_48], r15d
0x1800c5ebc  lea     rax, WPP_GLOBAL_Control
0x1800c5ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5eca  cmp     rcx, rax
0x1800c5ecd  jz      short loc_1800C5EEA
0x1800c5ecf  test    byte ptr [rcx+1Ch], 8
0x1800c5ed3  jz      short loc_1800C5EEA
0x1800c5ed5  mov     edx, 0C3h
0x1800c5eda  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c5ee1  mov     rcx, [rcx+10h]
0x1800c5ee5  call    WPP_SF_
0x1800c5eea  mov     ecx, 12h
0x1800c5eef  call    ?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z; StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)
0x1800c5ef4  test    rsi, rsi
0x1800c5ef7  jz      short loc_1800C5F11
0x1800c5ef9  mov     ecx, 0FFh
0x1800c5efe  mov     rax, rsi
0x1800c5f01  cmp     [rax], r15w
0x1800c5f05  jz      short loc_1800C5F5F
0x1800c5f07  add     rax, 2
0x1800c5f0b  sub     rcx, 1
0x1800c5f0f  jnz     short loc_1800C5F01
0x1800c5f11  mov     ebx, 80070057h
0x1800c5f16  lea     rsi, WPP_GLOBAL_Control
0x1800c5f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5f24  cmp     rcx, rsi
0x1800c5f27  jz      short loc_1800C5F47
0x1800c5f29  test    byte ptr [rcx+1Ch], 8
0x1800c5f2d  jz      short loc_1800C5F47
0x1800c5f2f  mov     edx, 0C8h
0x1800c5f34  mov     r9d, ebx
0x1800c5f37  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c5f3e  mov     rcx, [rcx+10h]
0x1800c5f42  call    WPP_SF_d
0x1800c5f47  mov     eax, ebx
0x1800c5f49  jmp     short loc_1800C5F4F
0x1800c5f4b  mov     eax, [rsp+0A8h+var_68]
0x1800c5f4f  add     rsp, 70h
0x1800c5f53  pop     r15
0x1800c5f55  pop     r14
0x1800c5f57  pop     r13
0x1800c5f59  pop     r12
0x1800c5f5b  pop     rdi
0x1800c5f5c  pop     rsi
0x1800c5f5d  pop     rbx
0x1800c5f5e  retn
0x1800c5f5f  xor     r8d, r8d; int *
0x1800c5f62  xor     edx, edx; unsigned int *
0x1800c5f64  lea     rcx, [rsp+0A8h+var_68]; unsigned int *
0x1800c5f69  call    ?HrGetClientInformation@@YAJPEAKPEAIPEAH@Z; HrGetClientInformation(ulong *,uint *,int *)
0x1800c5f6e  mov     ebx, eax
0x1800c5f70  test    eax, eax
0x1800c5f72  js      short loc_1800C5F16
0x1800c5f74  mov     ecx, 20Ch; cb
0x1800c5f79  call    cs:__imp_CoTaskMemAlloc
0x1800c5f7f  mov     r15, rax
0x1800c5f82  test    rax, rax
0x1800c5f85  jnz     short loc_1800C5FC3
0x1800c5f87  mov     ebx, 8007000Eh
0x1800c5f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5f93  lea     rsi, WPP_GLOBAL_Control
0x1800c5f9a  cmp     rcx, rsi
0x1800c5f9d  jz      short loc_1800C5F47
0x1800c5f9f  test    byte ptr [rcx+1Ch], 1
0x1800c5fa3  jz      loc_1800C5F24
0x1800c5fa9  mov     edx, 0C4h
0x1800c5fae  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c5fb5  mov     rcx, [rcx+10h]
0x1800c5fb9  call    WPP_SF_
0x1800c5fbe  jmp     loc_1800C5F1D
0x1800c5fc3  mov     [rsp+0A8h+lpCriticalSection], rdi
0x1800c5fc8  lea     rdx, [r13+28h]
0x1800c5fcc  lea     rcx, [rsp+0A8h+lpCriticalSection]
0x1800c5fd1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800c5fd6  mov     rdx, [r13+4D8h]; lpString2
0x1800c5fdd  test    rdx, rdx
0x1800c5fe0  jz      short loc_1800C601A
0x1800c5fe2  mov     rcx, rsi; lpString1
0x1800c5fe5  call    cs:__imp_lstrcmpW
0x1800c5feb  test    eax, eax
0x1800c5fed  jz      short loc_1800C5FF6
0x1800c5fef  or      edi, 1
0x1800c5ff2  mov     [rsp+0A8h+var_48], edi
0x1800c5ff6  mov     rcx, [r13+4D8h]; pv
0x1800c5ffd  mov     eax, [rcx+200h]
0x1800c6003  cmp     [rsi+200h], eax
0x1800c6009  jz      short loc_1800C6012
0x1800c600b  or      edi, 2
0x1800c600e  mov     [rsp+0A8h+var_48], edi
0x1800c6012  call    cs:__imp_CoTaskMemFree
0x1800c6018  jmp     short loc_1800C6021
0x1800c601a  or      edi, 3
0x1800c601d  mov     [rsp+0A8h+var_48], edi
0x1800c6021  mov     [r13+4D8h], r15
0x1800c6028  mov     eax, 4
0x1800c602d  lea     ecx, [rax+7Ch]
0x1800c6030  movups  xmm0, xmmword ptr [rsi]
0x1800c6033  movups  xmmword ptr [r15], xmm0
0x1800c6037  movups  xmm1, xmmword ptr [rsi+10h]
0x1800c603b  movups  xmmword ptr [r15+10h], xmm1
0x1800c6040  movups  xmm0, xmmword ptr [rsi+20h]
0x1800c6044  movups  xmmword ptr [r15+20h], xmm0
0x1800c6049  movups  xmm1, xmmword ptr [rsi+30h]
0x1800c604d  movups  xmmword ptr [r15+30h], xmm1
0x1800c6052  movups  xmm0, xmmword ptr [rsi+40h]
0x1800c6056  movups  xmmword ptr [r15+40h], xmm0
0x1800c605b  movups  xmm1, xmmword ptr [rsi+50h]
0x1800c605f  movups  xmmword ptr [r15+50h], xmm1
0x1800c6064  movups  xmm0, xmmword ptr [rsi+60h]
0x1800c6068  movups  xmmword ptr [r15+60h], xmm0
0x1800c606d  movups  xmm1, xmmword ptr [rsi+70h]
0x1800c6071  movups  xmmword ptr [r15+70h], xmm1
0x1800c6076  add     r15, rcx
0x1800c6079  add     rsi, rcx
0x1800c607c  sub     rax, 1
0x1800c6080  jnz     short loc_1800C6030
0x1800c6082  movups  xmm0, xmmword ptr [rsi-4]
0x1800c6086  movups  xmmword ptr [r15-4], xmm0
0x1800c608b  mov     edi, [rsp+0A8h+var_68]
0x1800c608f  mov     [r13+4E0h], edi
0x1800c6096  or      esi, 0FFFFFFFFh
0x1800c6099  cmp     r14d, esi
0x1800c609c  jnz     short loc_1800C60A5
0x1800c609e  test    r12d, r12d
0x1800c60a1  cmovnz  r14d, edi
0x1800c60a5  mov     [r13+4E4h], r14d
0x1800c60ac  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x1800c60b1  test    rcx, rcx
0x1800c60b4  jz      short loc_1800C60BC
0x1800c60b6  call    cs:__imp_LeaveCriticalSection
0x1800c60bc  cmp     r14d, esi
0x1800c60bf  jz      loc_1800C616A
0x1800c60c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c60cc  lea     rsi, WPP_GLOBAL_Control
0x1800c60d3  cmp     rcx, rsi
0x1800c60d6  jz      short loc_1800C60FB
0x1800c60d8  test    byte ptr [rcx+1Ch], 8
0x1800c60dc  jz      short loc_1800C60FB
0x1800c60de  mov     edx, 0C5h
0x1800c60e3  mov     [rsp+0A8h+var_88], r14d
0x1800c60e8  mov     r9d, edi
0x1800c60eb  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c60f2  mov     rcx, [rcx+10h]
0x1800c60f6  call    WPP_SF_dd
0x1800c60fb  movups  xmm0, xmmword ptr cs:?CLSID_NetworkStateChangeEventDataFactory@@3U_GUID@@B.Data1; _GUID const CLSID_NetworkStateChangeEventDataFactory ...
0x1800c6102  movdqu  [rsp+0A8h+var_58], xmm0
0x1800c6108  lea     r8, [rsp+0A8h+var_58]
0x1800c610d  mov     edx, r14d
0x1800c6110  mov     rcx, cs:WNF_SEB_NETWORK_STATE_CHANGES
0x1800c6117  call    PubSebEdgeEventValueInternal
0x1800c611c  mov     edi, eax
0x1800c611e  test    eax, eax
0x1800c6120  jz      short loc_1800C6152
0x1800c6122  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6129  cmp     rcx, rsi
0x1800c612c  jz      short loc_1800C614C
0x1800c612e  test    byte ptr [rcx+1Ch], 1
0x1800c6132  jz      short loc_1800C614C
0x1800c6134  mov     edx, 0C6h
0x1800c6139  mov     r9d, eax
0x1800c613c  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800c6143  mov     rcx, [rcx+10h]
0x1800c6147  call    WPP_SF_d
0x1800c614c  mov     ebx, edi
0x1800c614e  bts     ebx, 1Ch
0x1800c6152  lea     rdx, stru_18017E0E8; struct _WNF_STATE_NAME
0x1800c6159  mov     rcx, cs:WNF_SEB_NETWORK_STATE_CHANGES; this
0x1800c6160  call    ?ProcessServerWnf@StandbyMonitor@@YAXU_WNF_STATE_NAME@@PEBD@Z; StandbyMonitor::ProcessServerWnf(_WNF_STATE_NAME,char const *)
0x1800c6165  jmp     loc_1800C5F1D
0x1800c616a  mov     ebx, 80070490h
0x1800c616f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6176  lea     rsi, WPP_GLOBAL_Control
0x1800c617d  cmp     rcx, rsi
0x1800c6180  jz      loc_1800C5F47
0x1800c6186  test    byte ptr [rcx+1Ch], 2
0x1800c618a  jz      loc_1800C5F24
0x1800c6190  mov     edx, 0C7h
0x1800c6195  jmp     loc_1800C5FAE
```
