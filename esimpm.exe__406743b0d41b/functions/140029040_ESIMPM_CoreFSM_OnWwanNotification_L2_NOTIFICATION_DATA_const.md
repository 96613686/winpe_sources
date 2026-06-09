# ESIMPM::CoreFSM::OnWwanNotification(_L2_NOTIFICATION_DATA const *)

- ea: `0x140029040`
- end: `0x1400296ac`
- name: `?OnWwanNotification@CoreFSM@ESIMPM@@QEAAXPEBU_L2_NOTIFICATION_DATA@@@Z`
- size: `1644`
- prototype: `void __fastcall(ESIMPM::CoreFSM *__hidden this, const struct _L2_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140024900`

## callees

- `0x140002f84`
- `0x140003244`
- `0x140003b04`
- `0x140003b1c`
- `0x140014f64`
- `0x14001a9b4`
- `0x140020620`
- `0x140023158`
- `0x1400238d8`
- `0x14002564c`
- `0x140026a10`
- `0x140029040`
- `0x14002a448`
- `0x14002a854`
- `0x14002e734`
- `0x14002ea68`
- `0x14003211c`
- `0x140032434`

## string_xrefs

- `0x140029221`: ` A different SIM (IMSI %s ICCID %s) becomes ready. Expecting %s`
- `0x14002924c`: ` SIM ready for iccid %s, imsi%s`
- `0x1400295a5`: ` DataServiceState %d`
- `0x140029687`: ` ConnectionIStreamUpdated state %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ESIMPM::CoreFSM::OnWwanNotification(
        ESIMPM::CoreFSM *this,
        const struct _L2_NOTIFICATION_DATA *a2,
        __int64 a3)
{
  unsigned int *pData; // rbx
  DWORD dwDataSize; // ecx
  DWORD NotificationCode; // r9d
  int v8; // esi
  unsigned int v9; // edx
  bool v10; // cf
  char **v11; // rsi
  char *v12; // rcx
  _WORD *v13; // r15
  _WORD *v14; // rbp
  __int64 v15; // r8
  unsigned __int64 v16; // rdx
  char *v17; // r14
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned int EFHPLMNs; // eax
  _WORD *v21; // r9
  char **v22; // rcx
  unsigned __int64 v23; // rdx
  char *v24; // rsi
  __int64 v25; // rbx
  _QWORD *v26; // rax
  __int64 v27; // rax
  void *v28; // rbx
  unsigned int v29; // edx
  unsigned int v30; // eax
  int v31; // r9d
  const struct _GUID *v32; // rdx
  int v33; // eax
  unsigned int v34; // esi
  unsigned int v35; // ecx
  unsigned int v36; // ebx
  __int64 v37; // [rsp+20h] [rbp-78h]
  __int64 v38; // [rsp+20h] [rbp-78h]
  _QWORD v39[11]; // [rsp+40h] [rbp-58h] BYREF
  void *v40; // [rsp+A8h] [rbp+10h]

  pData = (unsigned int *)a2->pData;
  dwDataSize = a2->dwDataSize;
  NotificationCode = a2->NotificationCode;
  v8 = 14;
  v9 = 12;
  if ( NotificationCode > 0x1C )
  {
    switch ( NotificationCode )
    {
      case '1':
        if ( !pData || dwDataSize < 0x5F0 )
          goto LABEL_11;
        goto LABEL_35;
      case '_':
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 8;
        break;
      case '`':
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 0xC;
        break;
      case 'n':
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 0x24;
        break;
      case 'w':
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 0x18;
        break;
      default:
        goto LABEL_24;
    }
  }
  else
  {
    switch ( NotificationCode )
    {
      case 0x1Cu:
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 0x10;
        break;
      case 2u:
      case 3u:
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 4;
        break;
      case 6u:
      case 7u:
        if ( !pData )
          goto LABEL_11;
        v10 = dwDataSize < 0xD0;
        break;
      case 0x12u:
        if ( !pData )
        {
LABEL_11:
          ESIMPM::Log::Error(
            "ESIMPM::WwanHelper::s_ValidateNotifData",
            0,
            L"invalid notification: code %d size %d pData %p");
          return;
        }
        v10 = dwDataSize < 0x5C;
        break;
      default:
LABEL_24:
        ESIMPM::Log::Verbose("ESIMPM::WwanHelper::s_ValidateNotifData", 0, L" ignored notif code %d");
        return;
    }
  }
  if ( v10 )
    goto LABEL_11;
LABEL_35:
  if ( NotificationCode > 0x1C )
  {
    if ( NotificationCode == 49 )
    {
      v36 = pData[3];
      ESIMPM::Log::Info(
        "ESIMPM::CoreFSM::OnWwanNotification",
        (const struct _GUID *)((char *)this + 184),
        L" ConnectionIStreamUpdated state %d",
        v36);
      if ( v36 != 1 )
        v8 = 17;
      v9 = v8;
      goto LABEL_60;
    }
    if ( NotificationCode != 95 )
    {
      if ( NotificationCode == 96 )
      {
        ESIMPM::Log::Info(
          "ESIMPM::CoreFSM::OnWwanNotification",
          (const struct _GUID *)((char *)this + 184),
          L" EventTypeMultiSIMSlotMapping status 0x%x reqId 0x%x uiccSlotID %d (m_ReqIdSwitchSlot 0x%x current activeSlot %d)",
          *pData,
          pData[1],
          pData[2],
          *((_DWORD *)this + 90),
          *((_DWORD *)this + 53));
        return;
      }
      if ( NotificationCode == 110 )
      {
        ESIMPM::Log::Info(
          "ESIMPM::CoreFSM::OnWwanNotification",
          (const struct _GUID *)((char *)this + 184),
          L" DataServiceState %d",
          pData[1]);
        return;
      }
      v31 = *((_DWORD *)this + 92);
      if ( pData[1] )
      {
        if ( *pData != v31 )
          return;
        ESIMPM::Log::Error(
          "ESIMPM::CoreFSM::OnWwanNotification",
          (wchar_t *)this + 92,
          L"hplmns received request id %d, failed with 0x%x");
        *((_DWORD *)this + 92) = 0;
        *((_DWORD *)this + 130) = pData[1];
        v9 = 27;
      }
      else
      {
        v32 = (const struct _GUID *)((char *)this + 184);
        if ( *pData != v31 )
        {
          ESIMPM::Log::Verbose(
            "ESIMPM::CoreFSM::OnWwanNotification",
            v32,
            L"hplmns received request id %d, expecting request id %d, ignore",
            *pData,
            *((_DWORD *)this + 92));
          return;
        }
        ESIMPM::Log::Info("ESIMPM::CoreFSM::OnWwanNotification", v32, L"hplmns received request id %d");
        *((_DWORD *)this + 92) = 0;
        ESIMPM::LpaHelper::SetHPLMNs(
          (char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128,
          (char *)this + 528,
          pData + 6,
          pData[8] + 16);
        v9 = 26;
      }
      goto LABEL_60;
    }
    v33 = *((_DWORD *)this + 52);
    if ( *pData == v33 )
    {
      v34 = 0;
      if ( v33 )
      {
        do
        {
          v35 = pData[v34 + 1];
          *((_DWORD *)this + v34 + 54) = v35;
          LODWORD(v37) = v35;
          ESIMPM::Log::Info(
            "ESIMPM::CoreFSM::OnWwanNotification",
            (const struct _GUID *)((char *)this + 184),
            L" EventTypeMultiSIMInfo Idx %d SlotState %d",
            v34++,
            v37);
        }
        while ( v34 < *((_DWORD *)this + 52) );
      }
    }
    else
    {
      ESIMPM::Log::Error(
        "ESIMPM::CoreFSM::OnWwanNotification",
        (wchar_t *)this + 92,
        L" MsmEventTypeMultiSIMInfo unmatched num slot %d vs known one %d");
    }
  }
  else
  {
    if ( NotificationCode == 28 )
    {
      ESIMPM::Log::Info(
        "ESIMPM::CoreFSM::OnWwanNotification",
        (const struct _GUID *)((char *)this + 184),
        L" EventTypeRadioState: current radio state sw %d hw %d client requested radio state %d (m_swRadioState %d)",
        pData[3],
        pData[2],
        pData[1],
        *((_DWORD *)this + 86));
      v30 = pData[3];
      if ( *((_DWORD *)this + 86) == v30 )
        return;
      *((_DWORD *)this + 86) = v30;
      v9 = 7;
      goto LABEL_60;
    }
    if ( NotificationCode != 2 )
    {
      switch ( NotificationCode )
      {
        case 3u:
          v9 = 9;
          break;
        case 6u:
          *((_BYTE *)this + 340) = 1;
          v21 = pData + 3;
          v22 = (char **)((char *)this + 448);
          v23 = -1;
          do
            ++v23;
          while ( v21[v23] );
          if ( v23 > *((_QWORD *)this + 59) )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
              v22,
              v23,
              a3,
              v21);
          }
          else
          {
            if ( *((_QWORD *)this + 59) <= 7u )
              v24 = (char *)this + 448;
            else
              v24 = *v22;
            *((_QWORD *)this + 58) = v23;
            v25 = 2 * v23;
            memmove_0(v24, v21, 2 * v23);
            *(_WORD *)&v24[v25] = 0;
          }
          v9 = 11;
          break;
        case 7u:
          *((_BYTE *)this + 340) = 0;
          break;
        default:
          if ( *pData != 1 )
          {
            ESIMPM::Log::Verbose(
              "ESIMPM::CoreFSM::OnWwanNotification",
              (const struct _GUID *)((char *)this + 184),
              L" SIM state %d");
            return;
          }
          v11 = (char **)((char *)this + 376);
          v12 = (char *)this + 376;
          if ( *((_QWORD *)this + 50) > 7u )
            v12 = *v11;
          v13 = pData + 2;
          if ( memcmp_0(v12, pData + 2, 2LL * *((_QWORD *)this + 49)) )
          {
            if ( *((_QWORD *)this + 50) > 7u )
              v11 = (char **)*v11;
            ESIMPM::Log::Warning(
              "ESIMPM::CoreFSM::OnWwanNotification",
              (const struct _GUID *)((char *)this + 184),
              L" A different SIM (IMSI %s ICCID %s) becomes ready. Expecting %s",
              pData + 2,
              pData + 10,
              v11);
            return;
          }
          v14 = pData + 10;
          ESIMPM::Log::Info(
            "ESIMPM::CoreFSM::OnWwanNotification",
            (const struct _GUID *)((char *)this + 184),
            L" SIM ready for iccid %s, imsi%s",
            pData + 10,
            pData + 2);
          v16 = -1;
          do
            ++v16;
          while ( v14[v16] );
          if ( v16 > *((_QWORD *)this + 69) )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
              (char *)this + 528,
              v16,
              v15,
              pData + 10);
          }
          else
          {
            if ( *((_QWORD *)this + 69) <= 7u )
              v17 = (char *)this + 528;
            else
              v17 = (char *)*((_QWORD *)this + 66);
            *((_QWORD *)this + 68) = v16;
            v18 = 2 * v16;
            memmove_0(v17, v14, 2 * v16);
            *(_WORD *)&v17[v18] = 0;
          }
          ESIMPM::CoreFSM::TruncateTailingF(v19, (char *)this + 528);
          ESIMPM::LpaHelper::SetIMSI((__int64)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 128, (const wchar_t *)this + 264, v13);
          if ( !*((_DWORD *)this + 92) )
          {
            EFHPLMNs = ESIMPM::WwanHelper::SendQueryEFHPLMNs(
                         (ESIMPM::EsimPoMgr *)((char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 8),
                         &a2->InterfaceGuid,
                         (unsigned int *)this + 92);
            LODWORD(v38) = *((_DWORD *)this + 92);
            ESIMPM::Log::Info(
              "ESIMPM::CoreFSM::OnWwanNotification",
              (const struct _GUID *)((char *)this + 184),
              L"query hplmns 0x%x, request id %d",
              EFHPLMNs,
              v38);
          }
          v9 = 24;
          break;
      }
LABEL_60:
      ESIMPM::CoreFSM::fsmEventHandler((unsigned int *)this, v9);
      return;
    }
    v39[1] = 0;
    v26 = operator new(0x30u);
    *v26 = v26;
    v26[1] = v26;
    v39[0] = v26;
    if ( (unsigned int)ESIMPM::WwanHelper::QueryVisibleProviders(
                         (char *)ESIMPM::EsimPoMgr::m_s_EsimPoMgr + 8,
                         &a2->InterfaceGuid,
                         v39) )
    {
      v29 = 9;
    }
    else
    {
      v40 = operator new(0x10u);
      v27 = std::list<std::wstring>::list<std::wstring>(v40, v39);
      v28 = (void *)*((_QWORD *)this + 39);
      *((_QWORD *)this + 39) = v27;
      if ( v28 )
      {
        std::list<std::wstring>::~list<std::wstring>(v28);
        operator delete(v28);
      }
      v29 = 8;
    }
    ESIMPM::CoreFSM::fsmEventHandler((unsigned int *)this, v29);
    std::list<std::wstring>::~list<std::wstring>(v39);
  }
}

```

## disassembly

```asm
0x140029040  push    rbx
0x140029042  push    rbp
0x140029043  push    rsi
0x140029044  push    rdi
0x140029045  push    r12
0x140029047  push    r13
0x140029049  push    r14
0x14002904b  push    r15
0x14002904d  sub     rsp, 58h
0x140029051  mov     r13, rdx
0x140029054  mov     rdi, rcx
0x140029057  xor     r14d, r14d
0x14002905a  mov     rbx, [rdx+20h]
0x14002905e  mov     ecx, [rdx+18h]
0x140029061  mov     r9d, [rdx+4]
0x140029065  lea     esi, [r14+0Eh]
0x140029069  lea     ebp, [rsi-5]
0x14002906c  lea     r15d, [r14+10h]
0x140029070  lea     edx, [rsi-2]
0x140029073  cmp     r9d, 1Ch
0x140029077  ja      short loc_1400290F5
0x140029079  jz      short loc_1400290EB
0x14002907b  mov     eax, r9d
0x14002907e  sub     eax, 2
0x140029081  jz      short loc_1400290E1
0x140029083  sub     eax, 1
0x140029086  jz      short loc_1400290E1
0x140029088  sub     eax, 3
0x14002908b  jz      short loc_1400290D4
0x14002908d  sub     eax, 1
0x140029090  jz      short loc_1400290D4
0x140029092  cmp     eax, 0Bh
0x140029095  jnz     short loc_14002910F
0x140029097  test    rbx, rbx
0x14002909a  jz      short loc_1400290A5
0x14002909c  cmp     ecx, 5Ch ; '\'
0x14002909f  jnb     loc_14002917C
0x1400290a5  mov     [rsp+98h+var_70], rbx
0x1400290aa  mov     dword ptr [rsp+98h+var_78], ecx
0x1400290ae  lea     r8, aInvalidNotific; "invalid notification: code %d size %d p"...
0x1400290b5  xor     edx, edx; struct _GUID *
0x1400290b7  lea     rcx, aEsimpmWwanhelp_4; "ESIMPM::WwanHelper::s_ValidateNotifData"
0x1400290be  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400290c3  add     rsp, 58h
0x1400290c7  pop     r15
0x1400290c9  pop     r14
0x1400290cb  pop     r13
0x1400290cd  pop     r12
0x1400290cf  pop     rdi
0x1400290d0  pop     rsi
0x1400290d1  pop     rbp
0x1400290d2  pop     rbx
0x1400290d3  retn
0x1400290d4  test    rbx, rbx
0x1400290d7  jz      short loc_1400290A5
0x1400290d9  cmp     ecx, 0D0h
0x1400290df  jmp     short loc_14002909F
0x1400290e1  test    rbx, rbx
0x1400290e4  jz      short loc_1400290A5
0x1400290e6  cmp     ecx, 4
0x1400290e9  jmp     short loc_14002909F
0x1400290eb  test    rbx, rbx
0x1400290ee  jz      short loc_1400290A5
0x1400290f0  cmp     ecx, r15d
0x1400290f3  jmp     short loc_14002909F
0x1400290f5  mov     eax, r9d
0x1400290f8  sub     eax, 31h ; '1'
0x1400290fb  jz      short loc_140029167
0x1400290fd  sub     eax, 2Eh ; '.'
0x140029100  jz      short loc_140029156
0x140029102  sub     eax, 1
0x140029105  jz      short loc_140029146
0x140029107  sub     eax, esi
0x140029109  jz      short loc_140029135
0x14002910b  cmp     eax, ebp
0x14002910d  jz      short loc_140029124
0x14002910f  lea     r8, aIgnoredNotifCo; " ignored notif code %d"
0x140029116  xor     edx, edx
0x140029118  lea     rcx, aEsimpmWwanhelp_4; "ESIMPM::WwanHelper::s_ValidateNotifData"
0x14002911f  jmp     loc_1400294CD
0x140029124  test    rbx, rbx
0x140029127  jz      loc_1400290A5
0x14002912d  cmp     ecx, 18h
0x140029130  jmp     loc_14002909F
0x140029135  test    rbx, rbx
0x140029138  jz      loc_1400290A5
0x14002913e  cmp     ecx, 24h ; '$'
0x140029141  jmp     loc_14002909F
0x140029146  test    rbx, rbx
0x140029149  jz      loc_1400290A5
0x14002914f  cmp     ecx, edx
0x140029151  jmp     loc_14002909F
0x140029156  test    rbx, rbx
0x140029159  jz      loc_1400290A5
0x14002915f  cmp     ecx, 8
0x140029162  jmp     loc_14002909F
0x140029167  test    rbx, rbx
0x14002916a  jz      loc_1400290A5
0x140029170  cmp     ecx, 5F0h
0x140029176  jb      loc_1400290A5
0x14002917c  cmp     r9d, 1Ch
0x140029180  ja      loc_14002948E
0x140029186  jz      loc_140029439
0x14002918c  mov     eax, r9d
0x14002918f  sub     eax, 2
0x140029192  jz      loc_140029397
0x140029198  sub     eax, 1
0x14002919b  jz      loc_140029393
0x1400291a1  sub     eax, 3
0x1400291a4  jz      loc_140029335
0x1400291aa  sub     eax, 1
0x1400291ad  jz      loc_14002932C
0x1400291b3  cmp     eax, 0Bh
0x1400291b6  jnz     loc_1400294B8
0x1400291bc  mov     r9d, [rbx]
0x1400291bf  cmp     r9d, 1
0x1400291c3  jz      short loc_1400291D1
0x1400291c5  lea     r8, aSimStateD; " SIM state %d"
0x1400291cc  jmp     loc_1400294BF
0x1400291d1  lea     rsi, [rdi+178h]
0x1400291d8  mov     rcx, rsi
0x1400291db  cmp     qword ptr [rsi+18h], 7
0x1400291e0  jbe     short loc_1400291E5
0x1400291e2  mov     rcx, [rsi]; Buf1
0x1400291e5  lea     r15, [rbx+8]
0x1400291e9  mov     r8, [rdi+188h]
0x1400291f0  add     r8, r8; Size
0x1400291f3  mov     rdx, r15; Buf2
0x1400291f6  call    memcmp_0
0x1400291fb  test    eax, eax
0x1400291fd  jz      short loc_140029239
0x1400291ff  cmp     qword ptr [rsi+18h], 7
0x140029204  jbe     short loc_140029209
0x140029206  mov     rsi, [rsi]
0x140029209  lea     rax, [rbx+28h]
0x14002920d  lea     rdx, [rdi+0B8h]; struct _GUID *
0x140029214  mov     [rsp+98h+var_70], rsi
0x140029219  mov     [rsp+98h+var_78], rax
0x14002921e  mov     r9, r15
0x140029221  lea     r8, aADifferentSimI; " A different SIM (IMSI %s ICCID %s) bec"...
0x140029228  lea     rcx, aEsimpmCorefsmO; "ESIMPM::CoreFSM::OnWwanNotification"
0x14002922f  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x140029234  jmp     loc_1400290C3
0x140029239  lea     rbp, [rbx+28h]
0x14002923d  lea     r12, [rdi+0B8h]
0x140029244  mov     [rsp+98h+var_78], r15
0x140029249  mov     r9, rbp
0x14002924c  lea     r8, aSimReadyForIcc; " SIM ready for iccid %s, imsi%s"
0x140029253  mov     rdx, r12; struct _GUID *
0x140029256  lea     rcx, aEsimpmCorefsmO; "ESIMPM::CoreFSM::OnWwanNotification"
0x14002925d  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140029262  lea     rsi, [rdi+210h]
0x140029269  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002926d  inc     rdx
0x140029270  cmp     [rbp+rdx*2+0], r14w
0x140029276  jnz     short loc_14002926D
0x140029278  cmp     rdx, [rsi+18h]
0x14002927c  ja      short loc_1400292AF
0x14002927e  cmp     qword ptr [rsi+18h], 7
0x140029283  jbe     short loc_14002928A
0x140029285  mov     r14, [rsi]
0x140029288  jmp     short loc_14002928D
0x14002928a  mov     r14, rsi
0x14002928d  mov     [rsi+10h], rdx
0x140029291  lea     rbx, [rdx+rdx]
0x140029295  mov     r8, rbx; Size
0x140029298  mov     rdx, rbp; Src
0x14002929b  mov     rcx, r14; void *
0x14002929e  call    memmove_0
0x1400292a3  xor     eax, eax
0x1400292a5  mov     [r14+rbx], ax
0x1400292aa  xor     r14d, r14d
0x1400292ad  jmp     short loc_1400292BA
0x1400292af  mov     r9, rbp
0x1400292b2  mov     rcx, rsi
0x1400292b5  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x1400292ba  mov     rdx, rsi
0x1400292bd  call    ?TruncateTailingF@CoreFSM@ESIMPM@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ESIMPM::CoreFSM::TruncateTailingF(std::wstring &)
0x1400292c2  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400292c9  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400292cd  mov     r8, r15
0x1400292d0  mov     rdx, rsi
0x1400292d3  call    ?SetIMSI@LpaHelper@ESIMPM@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; ESIMPM::LpaHelper::SetIMSI(std::wstring const &,ushort const * const)
0x1400292d8  lea     rbx, [rdi+170h]
0x1400292df  cmp     [rbx], r14d
0x1400292e2  jnz     short loc_14002931A
0x1400292e4  lea     rdx, [r13+8]; struct _GUID *
0x1400292e8  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400292ef  add     rcx, 8; this
0x1400292f3  mov     r8, rbx; unsigned int *
0x1400292f6  call    ?SendQueryEFHPLMNs@WwanHelper@ESIMPM@@QEAAKAEBU_GUID@@PEAK@Z; ESIMPM::WwanHelper::SendQueryEFHPLMNs(_GUID const &,ulong *)
0x1400292fb  mov     ecx, [rbx]
0x1400292fd  mov     dword ptr [rsp+98h+var_78], ecx
0x140029301  mov     r9d, eax
0x140029304  lea     r8, aQueryHplmns0xX; "query hplmns 0x%x, request id %d"
0x14002930b  mov     rdx, r12; struct _GUID *
0x14002930e  lea     rcx, aEsimpmCorefsmO; "ESIMPM::CoreFSM::OnWwanNotification"
0x140029315  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002931a  mov     edx, 18h
0x14002931f  mov     rcx, rdi
0x140029322  call    ?fsmEventHandler@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler(ESIMPM::CoreFSM::_CoreFSMEvent)
0x140029327  jmp     loc_1400290C3
0x14002932c  mov     [rdi+154h], r14b
0x140029333  jmp     short loc_14002931F
0x140029335  mov     byte ptr [rdi+154h], 1
0x14002933c  lea     r9, [rbx+0Ch]
0x140029340  lea     rcx, [rdi+1C0h]
0x140029347  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002934b  inc     rdx
0x14002934e  cmp     [r9+rdx*2], r14w
0x140029353  jnz     short loc_14002934B
0x140029355  cmp     rdx, [rcx+18h]
0x140029359  ja      short loc_140029387
0x14002935b  cmp     qword ptr [rcx+18h], 7
0x140029360  jbe     short loc_140029367
0x140029362  mov     rsi, [rcx]
0x140029365  jmp     short loc_14002936A
0x140029367  mov     rsi, rcx
0x14002936a  mov     [rcx+10h], rdx
0x14002936e  lea     rbx, [rdx+rdx]
0x140029372  mov     r8, rbx; Size
0x140029375  mov     rdx, r9; Src
0x140029378  mov     rcx, rsi; void *
0x14002937b  call    memmove_0
0x140029380  mov     [rsi+rbx], r14w
0x140029385  jmp     short loc_14002938C
0x140029387  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x14002938c  mov     edx, 0Bh
0x140029391  jmp     short loc_14002931F
0x140029393  mov     edx, ebp
0x140029395  jmp     short loc_14002931F
0x140029397  mov     [rsp+98h+var_58], r14
0x14002939c  mov     [rsp+98h+var_50], r14
0x1400293a1  mov     ecx, 30h ; '0'; Size
0x1400293a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400293ab  mov     [rax], rax
0x1400293ae  mov     [rax+8], rax
0x1400293b2  mov     [rsp+98h+var_58], rax
0x1400293b7  lea     rdx, [r13+8]
0x1400293bb  mov     rcx, cs:?m_s_EsimPoMgr@EsimPoMgr@ESIMPM@@0V?$unique_ptr@VEsimPoMgr@ESIMPM@@U?$default_delete@VEsimPoMgr@ESIMPM@@@std@@@std@@A; std::unique_ptr<ESIMPM::EsimPoMgr> ESIMPM::EsimPoMgr::m_s_EsimPoMgr
0x1400293c2  add     rcx, 8
0x1400293c6  lea     r8, [rsp+98h+var_58]
0x1400293cb  call    ?QueryVisibleProviders@WwanHelper@ESIMPM@@QEAAKAEBU_GUID@@AEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ESIMPM::WwanHelper::QueryVisibleProviders(_GUID const &,std::list<std::wstring> &)
0x1400293d0  test    eax, eax
0x1400293d2  jnz     short loc_14002941F
0x1400293d4  mov     rcx, r15; Size
0x1400293d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400293dc  mov     [rsp+98h+arg_8], rax
0x1400293e4  lea     rdx, [rsp+98h+var_58]
0x1400293e9  mov     rcx, rax
0x1400293ec  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::list<std::wstring>::list<std::wstring>(std::list<std::wstring> const &)
0x1400293f1  nop
0x1400293f2  mov     rbx, [rdi+138h]
0x1400293f9  mov     [rdi+138h], rax
0x140029400  test    rbx, rbx
0x140029403  jz      short loc_140029418
0x140029405  mov     rcx, rbx
0x140029408  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x14002940d  mov     rdx, r15
0x140029410  mov     rcx, rbx; Block
0x140029413  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140029418  mov     edx, 8
0x14002941d  jmp     short loc_140029421
0x14002941f  mov     edx, ebp
0x140029421  mov     rcx, rdi
0x140029424  call    ?fsmEventHandler@CoreFSM@ESIMPM@@AEAAXW4_CoreFSMEvent@12@@Z; ESIMPM::CoreFSM::fsmEventHandler(ESIMPM::CoreFSM::_CoreFSMEvent)
0x140029429  nop
0x14002942a  lea     rcx, [rsp+98h+var_58]
0x14002942f  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x140029434  jmp     loc_1400290C3
0x140029439  lea     rdx, [rdi+0B8h]; struct _GUID *
0x140029440  mov     eax, [rdi+158h]
0x140029446  mov     [rsp+98h+var_68], eax
0x14002944a  mov     eax, [rbx+4]
0x14002944d  mov     dword ptr [rsp+98h+var_70], eax
0x140029451  mov     eax, [rbx+8]
0x140029454  mov     dword ptr [rsp+98h+var_78], eax
0x140029458  mov     r9d, [rbx+0Ch]
0x14002945c  lea     r8, aEventtyperadio; " EventTypeRadioState: current radio sta"...
0x140029463  lea     rcx, aEsimpmCorefsmO; "ESIMPM::CoreFSM::OnWwanNotification"
0x14002946a  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x14002946f  mov     eax, [rbx+0Ch]
0x140029472  cmp     [rdi+158h], eax
0x140029478  jz      loc_1400290C3
0x14002947e  mov     [rdi+158h], eax
0x140029484  mov     edx, 7
0x140029489  jmp     loc_14002931F
0x14002948e  mov     eax, r9d
0x140029491  sub     eax, 31h ; '1'
0x140029494  jz      loc_14002967A
0x14002949a  sub     eax, 2Eh ; '.'
0x14002949d  jz      loc_140029601
0x1400294a3  sub     eax, 1
0x1400294a6  jz      loc_1400295BD
0x1400294ac  sub     eax, esi
0x1400294ae  jz      loc_14002959A
0x1400294b4  cmp     eax, ebp
0x1400294b6  jz      short loc_1400294D7
0x1400294b8  lea     r8, aIgnoredNotifCo; " ignored notif code %d"
0x1400294bf  lea     rdx, [rdi+0B8h]; struct _GUID *
  ... truncated ...
```
