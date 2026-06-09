# InitializeGuestSid(void)

- ea: `0x180020fe0`
- end: `0x180021485`
- name: `?InitializeGuestSid@@YAXXZ`
- size: `1189`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800288c0`
- `0x180028ab0`

## callees

- `0x180004074`
- `0x1800041ac`
- `0x1800049ac`
- `0x18000b95c`
- `0x18000c39c`
- `0x1800139dc`
- `0x180017430`
- `0x180020fe0`
- `0x18002f0e0`

## import_xrefs

- `NETAPI32!NetUserModalsGet` at `0x180021052`
- `NETAPI32!NetUserModalsGet` at `0x180021052`
- `ADVAPI32!FreeSid` at `0x1800212ed`
- `ADVAPI32!FreeSid` at `0x180021371`
- `ADVAPI32!FreeSid` at `0x1800212ed`
- `ADVAPI32!FreeSid` at `0x180021371`
- `ADVAPI32!CopySid` at `0x1800212d0`
- `ADVAPI32!CopySid` at `0x180021392`
- `ADVAPI32!CopySid` at `0x1800212d0`
- `ADVAPI32!CopySid` at `0x180021392`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180021231`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180021231`
- `ADVAPI32!GetSidSubAuthority` at `0x1800211c4`
- `ADVAPI32!GetSidSubAuthority` at `0x1800211c4`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800211a2`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800211a2`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180021196`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180021196`
- `ADVAPI32!GetLengthSid` at `0x18002142d`
- `ADVAPI32!GetLengthSid` at `0x18002142d`
- `KERNEL32!LeaveCriticalSection` at `0x180021031`
- `KERNEL32!LeaveCriticalSection` at `0x180021125`
- `KERNEL32!LeaveCriticalSection` at `0x180021183`
- `KERNEL32!LeaveCriticalSection` at `0x1800212ad`
- `KERNEL32!LeaveCriticalSection` at `0x180021365`
- `KERNEL32!LeaveCriticalSection` at `0x18002141d`
- `KERNEL32!LeaveCriticalSection` at `0x180021461`
- `KERNEL32!LeaveCriticalSection` at `0x180021031`
- `KERNEL32!LeaveCriticalSection` at `0x180021125`
- `KERNEL32!LeaveCriticalSection` at `0x180021183`
- `KERNEL32!LeaveCriticalSection` at `0x1800212ad`
- `KERNEL32!LeaveCriticalSection` at `0x180021365`
- `KERNEL32!LeaveCriticalSection` at `0x18002141d`
- `KERNEL32!LeaveCriticalSection` at `0x180021461`
- `KERNEL32!GetLastError` at `0x18002123b`
- `KERNEL32!GetLastError` at `0x180021278`
- `KERNEL32!GetLastError` at `0x1800212f3`
- `KERNEL32!GetLastError` at `0x180021330`
- `KERNEL32!GetLastError` at `0x1800213ab`
- `KERNEL32!GetLastError` at `0x1800213e8`
- `KERNEL32!GetLastError` at `0x18002123b`
- `KERNEL32!GetLastError` at `0x180021278`
- `KERNEL32!GetLastError` at `0x1800212f3`
- `KERNEL32!GetLastError` at `0x180021330`
- `KERNEL32!GetLastError` at `0x1800213ab`
- `KERNEL32!GetLastError` at `0x1800213e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void InitializeGuestSid(void)
{
  DWORD v0; // eax
  DWORD v1; // edi
  unsigned int v2; // eax
  void *v3; // r14
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // r15
  UCHAR v5; // di
  UCHAR i; // si
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD LastError; // eax
  DWORD v12; // eax
  DWORD LengthSid; // eax
  char *v14; // rcx
  LPBYTE bufptr; // [rsp+60h] [rbp-29h] BYREF
  __int16 v16; // [rsp+68h] [rbp-21h] BYREF
  PSID pSourceSid[2]; // [rsp+70h] [rbp-19h] BYREF
  DWORD nSubAuthority0[8]; // [rsp+80h] [rbp-9h]

  if ( !dword_180043178 )
  {
    pSourceSid[1] = &stru_180042D98;
    CCriticalSection::Lock((CCriticalSection *)&stru_180042D98);
    if ( dword_180043178 )
    {
      LeaveCriticalSection(&stru_180042D98);
    }
    else
    {
      bufptr = 0;
      v0 = NetUserModalsGet(0, 2u, &bufptr);
      v1 = v0;
      if ( v0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_efe327766876393cacc144e0c735893e_Traceguids, v0);
        v16 = 50;
        LODWORD(pSourceSid[0]) = v1;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v2 = mqwcslen(L"acssctrl/acssinit");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            2,
            2LL * (v2 + 1),
            L"acssctrl/acssinit",
            2,
            &v16,
            4,
            pSourceSid,
            0,
            0);
        }
      }
      else if ( bufptr )
      {
        v3 = (void *)*((_QWORD *)bufptr + 1);
        SidIdentifierAuthority = GetSidIdentifierAuthority(v3);
        v5 = *GetSidSubAuthorityCount(v3);
        if ( v5 >= 8u )
        {
          g_pGuestSid = qword_180042E80;
          if ( CopySid(0x7Cu, qword_180042E80, v3) )
          {
            LengthSid = GetLengthSid(g_pGuestSid);
            v14 = (char *)g_pGuestSid;
            *((_BYTE *)g_pGuestSid + 1) = v5 + 1;
            *(_DWORD *)&v14[LengthSid] = 501;
          }
          else
          {
            g_pGuestSid = 0;
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 32),
                14,
                WPP_efe327766876393cacc144e0c735893e_Traceguids,
                LastError);
            v12 = GetLastError();
            if ( v12 )
              LogMsgNTStatus(v12, (wchar_t *)L"acssctrl/acssinit", 0x36u);
          }
        }
        else
        {
          for ( i = 0; i < v5; ++i )
            nSubAuthority0[i] = *GetSidSubAuthority(v3, i);
          nSubAuthority0[i] = 501;
          pSourceSid[0] = 0;
          if ( AllocateAndInitializeSid(
                 SidIdentifierAuthority,
                 v5 + 1,
                 nSubAuthority0[0],
                 nSubAuthority0[1],
                 nSubAuthority0[2],
                 nSubAuthority0[3],
                 nSubAuthority0[4],
                 nSubAuthority0[5],
                 nSubAuthority0[6],
                 nSubAuthority0[7],
                 pSourceSid) )
          {
            g_pGuestSid = qword_180042E80;
            if ( CopySid(0x80u, qword_180042E80, pSourceSid[0]) )
            {
              FreeSid(pSourceSid[0]);
            }
            else
            {
              g_pGuestSid = 0;
              FreeSid(pSourceSid[0]);
              v9 = GetLastError();
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, WPP_efe327766876393cacc144e0c735893e_Traceguids, v9);
              v10 = GetLastError();
              if ( v10 )
                LogMsgNTStatus(v10, (wchar_t *)L"acssctrl/acssinit", 0x35u);
            }
          }
          else
          {
            v7 = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, WPP_efe327766876393cacc144e0c735893e_Traceguids, v7);
            v8 = GetLastError();
            if ( v8 )
              LogMsgNTStatus(v8, (wchar_t *)L"acssctrl/acssinit", 0x34u);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      {
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          (unsigned int)((_DWORD)bufptr + 11),
          WPP_efe327766876393cacc144e0c735893e_Traceguids);
      }
      dword_180043178 = 1;
      PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(&bufptr);
      LeaveCriticalSection(&stru_180042D98);
    }
  }
}

```

## disassembly

```asm
0x180020fe0  push    rbp
0x180020fe2  push    rsi
0x180020fe3  push    rdi
0x180020fe4  push    r13
0x180020fe6  push    r14
0x180020fe8  push    r15
0x180020fea  lea     rbp, [rsp-2Fh]
0x180020fef  sub     rsp, 0B8h
0x180020ff6  mov     rax, cs:__security_cookie
0x180020ffd  xor     rax, rsp
0x180021000  mov     [rbp+57h+var_40], rax
0x180021004  cmp     cs:dword_180043178, 0
0x18002100b  jnz     loc_180021468
0x180021011  lea     r13, stru_180042D98
0x180021018  mov     [rbp+57h+var_68], r13
0x18002101c  mov     rcx, r13; this
0x18002101f  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180021024  nop
0x180021025  cmp     cs:dword_180043178, 0
0x18002102c  jz      short loc_18002103D
0x18002102e  mov     rcx, r13; lpCriticalSection
0x180021031  call    cs:__imp_LeaveCriticalSection
0x180021037  nop
0x180021038  jmp     loc_180021468
0x18002103d  mov     [rbp+57h+bufptr], 0
0x180021045  lea     r8, [rbp+57h+bufptr]; bufptr
0x180021049  mov     esi, 2
0x18002104e  mov     edx, esi; level
0x180021050  xor     ecx, ecx; servername
0x180021052  call    cs:__imp_NetUserModalsGet
0x180021058  mov     edi, eax
0x18002105a  test    eax, eax
0x18002105c  jz      loc_180021131
0x180021062  lea     rdx, WPP_GLOBAL_Control
0x180021069  mov     rcx, cs:WPP_GLOBAL_Control
0x180021070  cmp     rcx, rdx
0x180021073  jz      short loc_180021097
0x180021075  test    byte ptr [rcx+10Ch], 1
0x18002107c  jz      short loc_180021097
0x18002107e  lea     edx, [rsi+8]
0x180021081  mov     r9d, eax
0x180021084  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x18002108b  mov     rcx, [rcx+100h]
0x180021092  call    WPP_SF_d
0x180021097  mov     eax, 32h ; '2'
0x18002109c  mov     [rbp+57h+var_78], ax
0x1800210a0  mov     dword ptr [rbp+57h+pSourceSid], edi
0x1800210a3  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800210ab  jz      short loc_18002110E
0x1800210ad  lea     rdi, aAcssctrlAcssin; "acssctrl/acssinit"
0x1800210b4  mov     rcx, rdi; wchar_t *
0x1800210b7  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800210bc  lea     r9d, [rax+1]
0x1800210c0  add     r9, r9
0x1800210c3  mov     [rsp+0E0h+pSid], 0
0x1800210cc  mov     qword ptr [rsp+0E0h+nSubAuthority7], 0
0x1800210d5  lea     rax, [rbp+57h+pSourceSid]
0x1800210d9  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x1800210de  mov     qword ptr [rsp+0E0h+nSubAuthority5], 4
0x1800210e7  lea     rax, [rbp+57h+var_78]
0x1800210eb  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x1800210f0  mov     qword ptr [rsp+0E0h+nSubAuthority3], rsi
0x1800210f5  mov     qword ptr [rsp+0E0h+nSubAuthority2], rdi
0x1800210fa  mov     r8d, esi
0x1800210fd  mov     edx, 1
0x180021102  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180021109  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18002110e  mov     cs:dword_180043178, 1
0x180021118  lea     rcx, [rbp+57h+bufptr]
0x18002111c  call    ??1?$PNETBUF@U_DOMAIN_CONTROLLER_INFOW@@@@QEAA@XZ; PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(void)
0x180021121  nop
0x180021122  mov     rcx, r13; lpCriticalSection
0x180021125  call    cs:__imp_LeaveCriticalSection
0x18002112b  nop
0x18002112c  jmp     loc_180021468
0x180021131  mov     rax, [rbp+57h+bufptr]
0x180021135  test    rax, rax
0x180021138  jnz     short loc_18002118F
0x18002113a  lea     rdx, WPP_GLOBAL_Control
0x180021141  mov     rcx, cs:WPP_GLOBAL_Control
0x180021148  cmp     rcx, rdx
0x18002114b  jz      short loc_18002116C
0x18002114d  test    byte ptr [rcx+10Ch], 4
0x180021154  jz      short loc_18002116C
0x180021156  lea     edx, [rax+0Bh]
0x180021159  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180021160  mov     rcx, [rcx+100h]
0x180021167  call    WPP_SF_
0x18002116c  mov     cs:dword_180043178, 1
0x180021176  lea     rcx, [rbp+57h+bufptr]
0x18002117a  call    ??1?$PNETBUF@U_DOMAIN_CONTROLLER_INFOW@@@@QEAA@XZ; PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(void)
0x18002117f  nop
0x180021180  mov     rcx, r13; lpCriticalSection
0x180021183  call    cs:__imp_LeaveCriticalSection
0x180021189  nop
0x18002118a  jmp     loc_180021468
0x18002118f  mov     r14, [rax+8]
0x180021193  mov     rcx, r14; pSid
0x180021196  call    cs:__imp_GetSidIdentifierAuthority
0x18002119c  mov     r15, rax
0x18002119f  mov     rcx, r14; pSid
0x1800211a2  call    cs:__imp_GetSidSubAuthorityCount
0x1800211a8  mov     dil, [rax]
0x1800211ab  cmp     dil, 8
0x1800211af  jnb     loc_18002137C
0x1800211b5  xor     sil, sil
0x1800211b8  test    dil, dil
0x1800211bb  jz      short loc_1800211DC
0x1800211bd  movzx   edx, sil; nSubAuthority
0x1800211c1  mov     rcx, r14; pSid
0x1800211c4  call    cs:__imp_GetSidSubAuthority
0x1800211ca  movzx   ecx, sil
0x1800211ce  mov     eax, [rax]
0x1800211d0  mov     [rbp+rcx*4+57h+nSubAuthority0], eax
0x1800211d4  inc     sil
0x1800211d7  cmp     sil, dil
0x1800211da  jb      short loc_1800211BD
0x1800211dc  movzx   eax, sil
0x1800211e0  mov     [rbp+rax*4+57h+nSubAuthority0], 1F5h
0x1800211e8  mov     [rbp+57h+pSourceSid], 0
0x1800211f0  lea     edx, [rdi+1]; nSubAuthorityCount
0x1800211f3  lea     rax, [rbp+57h+pSourceSid]
0x1800211f7  mov     [rsp+0E0h+pSid], rax; pSid
0x1800211fc  mov     eax, [rbp+57h+var_44]
0x1800211ff  mov     [rsp+0E0h+nSubAuthority7], eax; nSubAuthority7
0x180021203  mov     eax, [rbp+57h+var_48]
0x180021206  mov     [rsp+0E0h+nSubAuthority6], eax; nSubAuthority6
0x18002120a  mov     eax, [rbp+57h+var_4C]
0x18002120d  mov     [rsp+0E0h+nSubAuthority5], eax; nSubAuthority5
0x180021211  mov     eax, [rbp+57h+var_50]
0x180021214  mov     [rsp+0E0h+nSubAuthority4], eax; nSubAuthority4
0x180021218  mov     eax, [rbp+57h+var_54]
0x18002121b  mov     [rsp+0E0h+nSubAuthority3], eax; nSubAuthority3
0x18002121f  mov     eax, [rbp+57h+var_58]
0x180021222  mov     [rsp+0E0h+nSubAuthority2], eax; nSubAuthority2
0x180021226  mov     r9d, [rbp+57h+nSubAuthority1]; nSubAuthority1
0x18002122a  mov     r8d, [rbp+57h+nSubAuthority0]; nSubAuthority0
0x18002122e  mov     rcx, r15; pIdentifierAuthority
0x180021231  call    cs:__imp_AllocateAndInitializeSid
0x180021237  test    eax, eax
0x180021239  jnz     short loc_1800212B9
0x18002123b  call    cs:__imp_GetLastError
0x180021241  lea     rdx, WPP_GLOBAL_Control
0x180021248  mov     rcx, cs:WPP_GLOBAL_Control
0x18002124f  cmp     rcx, rdx
0x180021252  jz      short loc_180021278
0x180021254  test    byte ptr [rcx+10Ch], 1
0x18002125b  jz      short loc_180021278
0x18002125d  mov     edx, 0Ch
0x180021262  mov     r9d, eax
0x180021265  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x18002126c  mov     rcx, [rcx+100h]
0x180021273  call    WPP_SF_d
0x180021278  call    cs:__imp_GetLastError
0x18002127e  test    eax, eax
0x180021280  jz      short loc_180021296
0x180021282  mov     r8d, 34h ; '4'; unsigned __int16
0x180021288  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x18002128f  mov     ecx, eax; int
0x180021291  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180021296  mov     cs:dword_180043178, 1
0x1800212a0  lea     rcx, [rbp+57h+bufptr]
0x1800212a4  call    ??1?$PNETBUF@U_DOMAIN_CONTROLLER_INFOW@@@@QEAA@XZ; PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(void)
0x1800212a9  nop
0x1800212aa  mov     rcx, r13; lpCriticalSection
0x1800212ad  call    cs:__imp_LeaveCriticalSection
0x1800212b3  nop
0x1800212b4  jmp     loc_180021468
0x1800212b9  lea     rdx, qword_180042E80; pDestinationSid
0x1800212c0  mov     cs:?g_pGuestSid@@3PEAXEA, rdx; void * g_pGuestSid
0x1800212c7  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x1800212cb  mov     ecx, 80h; nDestinationSidLength
0x1800212d0  call    cs:__imp_CopySid
0x1800212d6  mov     rcx, [rbp+57h+pSourceSid]; pSid
0x1800212da  test    eax, eax
0x1800212dc  jnz     loc_180021371
0x1800212e2  mov     cs:?g_pGuestSid@@3PEAXEA, 0; void * g_pGuestSid
0x1800212ed  call    cs:__imp_FreeSid
0x1800212f3  call    cs:__imp_GetLastError
0x1800212f9  lea     rdx, WPP_GLOBAL_Control
0x180021300  mov     rcx, cs:WPP_GLOBAL_Control
0x180021307  cmp     rcx, rdx
0x18002130a  jz      short loc_180021330
0x18002130c  test    byte ptr [rcx+10Ch], 1
0x180021313  jz      short loc_180021330
0x180021315  mov     edx, 0Dh
0x18002131a  mov     r9d, eax
0x18002131d  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x180021324  mov     rcx, [rcx+100h]
0x18002132b  call    WPP_SF_d
0x180021330  call    cs:__imp_GetLastError
0x180021336  test    eax, eax
0x180021338  jz      short loc_18002134E
0x18002133a  mov     r8d, 35h ; '5'; unsigned __int16
0x180021340  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x180021347  mov     ecx, eax; int
0x180021349  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18002134e  mov     cs:dword_180043178, 1
0x180021358  lea     rcx, [rbp+57h+bufptr]
0x18002135c  call    ??1?$PNETBUF@U_DOMAIN_CONTROLLER_INFOW@@@@QEAA@XZ; PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(void)
0x180021361  nop
0x180021362  mov     rcx, r13; lpCriticalSection
0x180021365  call    cs:__imp_LeaveCriticalSection
0x18002136b  nop
0x18002136c  jmp     loc_180021468
0x180021371  call    cs:__imp_FreeSid
0x180021377  jmp     loc_18002144A
0x18002137c  lea     rdx, qword_180042E80; pDestinationSid
0x180021383  mov     cs:?g_pGuestSid@@3PEAXEA, rdx; void * g_pGuestSid
0x18002138a  mov     r8, r14; pSourceSid
0x18002138d  mov     ecx, 7Ch ; '|'; nDestinationSidLength
0x180021392  call    cs:__imp_CopySid
0x180021398  test    eax, eax
0x18002139a  jnz     loc_180021426
0x1800213a0  mov     cs:?g_pGuestSid@@3PEAXEA, 0; void * g_pGuestSid
0x1800213ab  call    cs:__imp_GetLastError
0x1800213b1  lea     rdx, WPP_GLOBAL_Control
0x1800213b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213bf  cmp     rcx, rdx
0x1800213c2  jz      short loc_1800213E8
0x1800213c4  test    byte ptr [rcx+10Ch], 1
0x1800213cb  jz      short loc_1800213E8
0x1800213cd  mov     edx, 0Eh
0x1800213d2  mov     r9d, eax
0x1800213d5  lea     r8, WPP_efe327766876393cacc144e0c735893e_Traceguids
0x1800213dc  mov     rcx, [rcx+100h]
0x1800213e3  call    WPP_SF_d
0x1800213e8  call    cs:__imp_GetLastError
0x1800213ee  test    eax, eax
0x1800213f0  jz      short loc_180021406
0x1800213f2  mov     r8d, 36h ; '6'; unsigned __int16
0x1800213f8  lea     rdx, aAcssctrlAcssin; "acssctrl/acssinit"
0x1800213ff  mov     ecx, eax; int
0x180021401  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180021406  mov     cs:dword_180043178, 1
0x180021410  lea     rcx, [rbp+57h+bufptr]
0x180021414  call    ??1?$PNETBUF@U_DOMAIN_CONTROLLER_INFOW@@@@QEAA@XZ; PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(void)
0x180021419  nop
0x18002141a  mov     rcx, r13; lpCriticalSection
0x18002141d  call    cs:__imp_LeaveCriticalSection
0x180021423  nop
0x180021424  jmp     short loc_180021468
0x180021426  mov     rcx, cs:?g_pGuestSid@@3PEAXEA; pSid
0x18002142d  call    cs:__imp_GetLengthSid
0x180021433  inc     dil
0x180021436  mov     rcx, cs:?g_pGuestSid@@3PEAXEA; void * g_pGuestSid
0x18002143d  mov     [rcx+1], dil
0x180021441  mov     eax, eax
0x180021443  mov     dword ptr [rax+rcx], 1F5h
0x18002144a  mov     cs:dword_180043178, 1
0x180021454  lea     rcx, [rbp+57h+bufptr]
0x180021458  call    ??1?$PNETBUF@U_DOMAIN_CONTROLLER_INFOW@@@@QEAA@XZ; PNETBUF<_DOMAIN_CONTROLLER_INFOW>::~PNETBUF<_DOMAIN_CONTROLLER_INFOW>(void)
0x18002145d  nop
0x18002145e  mov     rcx, r13; lpCriticalSection
0x180021461  call    cs:__imp_LeaveCriticalSection
0x180021467  nop
0x180021468  mov     rcx, [rbp+57h+var_40]
0x18002146c  xor     rcx, rsp; StackCookie
0x18002146f  call    __security_check_cookie
0x180021474  add     rsp, 0B8h
0x18002147b  pop     r15
0x18002147d  pop     r14
0x18002147f  pop     r13
0x180021481  pop     rdi
0x180021482  pop     rsi
0x180021483  pop     rbp
0x180021484  retn
```
