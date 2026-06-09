# RemoveConnectionPort

- ea: `0x180047954`
- end: `0x180048088`
- name: `RemoveConnectionPort`
- size: `1844`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800210e0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000bf74`
- `0x18000c37c`
- `0x18000c424`
- `0x180034114`
- `0x18003e864`
- `0x180040ddc`
- `0x18004236c`
- `0x180043958`
- `0x180047954`
- `0x18004917c`
- `0x18004a7cc`
- `0x18004c1f0`
- `0x18004c26c`
- `0x18004c33c`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047f78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047f9e`
- `rtutils!RouterLogEventA` at `0x180047ddd`
- `rtutils!RouterLogEventA` at `0x180047ddd`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180047ca5`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180047ca5`

## pseudocode

```c
double __fastcall RemoveConnectionPort(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // bl
  struct _LIST_ENTRY *v7; // rcx
  double result; // xmm0_8
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rbx
  __int64 UserData; // rax
  __int64 v16; // rax
  const char *v17; // rdx
  char *v18; // rcx
  char *v19; // rax
  void *v20; // rdx
  struct _LIST_ENTRY *v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rdx
  struct _LIST_ENTRY *v27; // rcx
  __int64 v28; // rax
  unsigned int v29; // eax
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h]
  char v35[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v36; // [rsp+B0h] [rbp-50h]
  char pszDest[80]; // [rsp+C0h] [rbp-40h] BYREF
  char v38[288]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR Name[264]; // [rsp+230h] [rbp+130h] BYREF

  v4 = a3;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(a4) = a3;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 234, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a4);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(v7[1].Blink) & 0x2000) != 0 && BYTE1(v7[1].Blink) >= 2u )
      {
        result = WPP_SF_(v7[1].Flink, 235, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v7[1].Blink) & 0x2000) != 0
        && BYTE1(v7[1].Blink) >= 6u )
      {
        v9 = 236;
        return WPP_SF_(v7[1].Flink, v9, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      }
    }
    return result;
  }
  v10 = *(_DWORD *)(a2 + 68);
  if ( v10 )
  {
    v11 = (unsigned int)(v10 - 1);
    *(_DWORD *)(a2 + 68) = v11;
    v7 = WPP_GLOBAL_Control;
  }
  else
  {
    v11 = 0;
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
    && BYTE1(v7[1].Blink) >= 5u )
  {
    WPP_SF_qcqd(v7[1].Flink, v11, a3, *(_QWORD *)a1, v4 != 0, a2, v11);
    v7 = WPP_GLOBAL_Control;
  }
  v12 = *(_QWORD *)(a2 + 56);
  if ( v12 )
  {
    v13 = *(_DWORD *)(a1 + 1096);
    if ( v13 < *(_DWORD *)(a2 + 64) )
    {
      *(_QWORD *)(v12 + 8LL * (v13 - 1)) = 0;
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( *(_DWORD *)(a2 + 68) )
  {
    v28 = *(_QWORD *)(a1 + 1048);
    if ( v28 && *(_DWORD *)(v28 + 24) )
    {
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v7[1].Blink) & 0x2000) != 0
        && BYTE1(v7[1].Blink) >= 5u )
      {
        WPP_SF_sq(
          v7[1].Flink,
          244,
          (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
          a1 + 8,
          *(_QWORD *)(a1 + 1048));
      }
      SignalNotifiers(*(_QWORD *)(a2 + 48), 8, 0);
      EnterCriticalSection(&g_csConnectionNotifierList);
      SignalNotifiers(pConnectionNotifierList, 8, 0);
      LeaveCriticalSection(&g_csConnectionNotifierList);
      *(_DWORD *)g_RasEvent = 0x4000;
      v29 = DwSendNotificationInternal(a2, g_RasEvent);
      if ( v29 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_89;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 245, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v29);
      }
      v7 = WPP_GLOBAL_Control;
    }
  }
  else if ( !*(_DWORD *)(a2 + 88) || *(_DWORD *)(a1 + 1072) )
  {
    SignalNotifiers(*(_QWORD *)(a2 + 48), 2, 0);
    EnterCriticalSection(&g_csConnectionNotifierList);
    SignalNotifiers(pConnectionNotifierList, 2, 0);
    LeaveCriticalSection(&g_csConnectionNotifierList);
    if ( !*(_DWORD *)(a1 + 1072) || !hRasClientEventLogHandle )
      goto LABEL_54;
    v14 = 273;
    memset_0(v38, 0, 0x111u);
    memset_0(pszDest, 0, sizeof(pszDest));
    UserData = GetUserData(a2 + 32, 10);
    if ( UserData && *(_DWORD *)(UserData + 20) <= 0x10u )
    {
      StringCchPrintfA(
        pszDest,
        0x50u,
        "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
        *(_DWORD *)(UserData + 24),
        *(unsigned __int16 *)(UserData + 28),
        *(unsigned __int16 *)(UserData + 30),
        *(unsigned __int8 *)(UserData + 32),
        *(unsigned __int8 *)(UserData + 33),
        *(unsigned __int8 *)(UserData + 34),
        *(unsigned __int8 *)(UserData + 35),
        *(unsigned __int8 *)(UserData + 36),
        *(unsigned __int8 *)(UserData + 37),
        *(unsigned __int8 *)(UserData + 38),
        *(unsigned __int8 *)(UserData + 39));
      v14 = 273;
    }
    if ( (unsigned int)IsSystemOwnedConnection(a2) )
    {
      v16 = 2147483646;
      v17 = "SYSTEM";
      v18 = v38;
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v16;
        --v14;
      }
      while ( v14 );
      v19 = v18 - 1;
      if ( v14 )
        v19 = v18;
      *v19 = 0;
    }
    else
    {
      memset_0(Name, 0, 0x202u);
      v20 = *(void **)(a2 + 96);
      result = 0.0;
      cchName = 257;
      cchReferencedDomainName = 16;
      peUse = 0;
      *(_OWORD *)ReferencedDomainName = 0;
      v34 = 0;
      if ( LookupAccountSidW(0, v20, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        StringCchPrintfA(v38, 0x111u, "%S\\%S", ReferencedDomainName, Name);
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
LABEL_47:
          v22 = *(int *)(a1 + 1324);
          if ( (unsigned int)v22 <= 9 )
          {
            v23 = HIDWORD(rdrMapping[2 * v22]);
            if ( v23 )
            {
              result = 0.0;
              *(_QWORD *)ReferencedDomainName = pszDest;
              *(_QWORD *)&ReferencedDomainName[4] = v38;
              *(_QWORD *)&v34 = a2 + 445;
              *((_QWORD *)&v34 + 1) = v35;
              *(_OWORD *)v35 = 0;
              v36 = 0;
              if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v21[1].Blink) & 0x2000) != 0
                && BYTE1(v21[1].Blink) >= 5u )
              {
                WPP_SF_sd(
                  v21[1].Flink,
                  240,
                  (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
                  rdrMapping[2 * v22 + 1],
                  v23);
              }
              StringCchPrintfA(v35, 0x20u, "%d", HIDWORD(rdrMapping[2 * *(int *)(a1 + 1324)]));
              RouterLogEventA(hRasClientEventLogHandle, 4u, 0x4F02u, 4u, (LPSTR *)ReferencedDomainName, 0);
            }
          }
LABEL_54:
          v24 = SendSensNotification(8, *(_QWORD *)(a2 + 16));
          if ( v24 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_60:
              if ( *(_DWORD *)(a1 + 1360) == 3 && (*(_BYTE *)(a1 + 1224) & 0x20) != 0 )
                goto LABEL_75;
              *(_DWORD *)g_RasEvent = 128;
              v25 = DwSendNotificationInternal(a2, g_RasEvent);
              if ( v25 )
              {
                v27 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                {
LABEL_72:
                  *(_DWORD *)(a2 + 120) = *(_DWORD *)(a1 + 1072);
                  if ( !*(_DWORD *)(a2 + 164) )
                  {
                    result = FreeConnection((char *)a2);
                    *(_QWORD *)(a1 + 1064) = 0;
                  }
                  v7 = WPP_GLOBAL_Control;
                  a2 = 0;
LABEL_75:
                  if ( !a2 )
                    goto LABEL_94;
                  goto LABEL_89;
                }
                if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
                {
LABEL_68:
                  if ( v27 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v27[1].Blink) & 0x2000) != 0
                    && BYTE1(v27[1].Blink) >= 5u )
                  {
                    WPP_SF_qqddd(
                      v27[1].Flink,
                      v26,
                      a3,
                      *(_QWORD *)(a2 + 16),
                      a2,
                      *(_DWORD *)(a1 + 1072),
                      *(_DWORD *)(a1 + 1360),
                      *(_DWORD *)(a1 + 1224) & 0x20);
                  }
                  goto LABEL_72;
                }
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 242, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v25);
              }
              v27 = WPP_GLOBAL_Control;
              goto LABEL_68;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 241, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v24);
          }
          v7 = WPP_GLOBAL_Control;
          goto LABEL_60;
        }
        result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 239, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      }
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
LABEL_89:
  if ( !*(_DWORD *)(a2 + 68)
    && v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x2000) != 0
    && BYTE1(v7[1].Blink) >= 5u )
  {
    WPP_SF_qdd(v7[1].Flink, 246, a3, *(_QWORD *)(a2 + 16), 0, *(_DWORD *)(a2 + 88));
  }
LABEL_94:
  *(_QWORD *)(a1 + 1048) = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v9 = 247;
    return WPP_SF_(v7[1].Flink, v9, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180047954  mov     [rsp-8+arg_18], rbx
0x180047959  push    rbp
0x18004795a  push    rsi
0x18004795b  push    rdi
0x18004795c  push    r12
0x18004795e  push    r13
0x180047960  push    r14
0x180047962  push    r15
0x180047964  lea     rbp, [rsp-350h]
0x18004796c  sub     rsp, 450h
0x180047973  mov     rax, cs:__security_cookie
0x18004797a  xor     rax, rsp
0x18004797d  mov     [rbp+380h+var_40], rax
0x180047984  mov     bl, r8b
0x180047987  mov     r13, rdx
0x18004798a  mov     r12, rcx
0x18004798d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047994  lea     r14, WPP_GLOBAL_Control
0x18004799b  lea     r15, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800479a2  mov     esi, 2000h
0x1800479a7  cmp     rcx, r14
0x1800479aa  jz      short loc_1800479D2
0x1800479ac  test    [rcx+1Ch], esi
0x1800479af  jz      short loc_1800479D2
0x1800479b1  cmp     byte ptr [rcx+19h], 6
0x1800479b5  jb      short loc_1800479D2
0x1800479b7  mov     rcx, [rcx+10h]
0x1800479bb  mov     edx, 0EAh
0x1800479c0  mov     r9b, bl
0x1800479c3  mov     r8, r15
0x1800479c6  call    WPP_SF_c
0x1800479cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800479d2  xor     edi, edi
0x1800479d4  test    r13, r13
0x1800479d7  jnz     short loc_180047A2B
0x1800479d9  cmp     rcx, r14
0x1800479dc  jz      loc_18004805D
0x1800479e2  test    [rcx+1Ch], esi
0x1800479e5  jz      short loc_180047A05
0x1800479e7  cmp     byte ptr [rcx+19h], 2
0x1800479eb  jb      short loc_180047A05
0x1800479ed  mov     rcx, [rcx+10h]
0x1800479f1  mov     edx, 0EBh
0x1800479f6  mov     r8, r15
0x1800479f9  call    WPP_SF_
0x1800479fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a05  cmp     rcx, r14
0x180047a08  jz      loc_18004805D
0x180047a0e  test    [rcx+1Ch], esi
0x180047a11  jz      loc_18004805D
0x180047a17  cmp     byte ptr [rcx+19h], 6
0x180047a1b  jb      loc_18004805D
0x180047a21  mov     edx, 0ECh
0x180047a26  jmp     loc_180048051
0x180047a2b  mov     edx, [r13+44h]
0x180047a2f  test    edx, edx
0x180047a31  jz      short loc_180047A42
0x180047a33  dec     edx
0x180047a35  mov     [r13+44h], edx
0x180047a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a40  jmp     short loc_180047A44
0x180047a42  mov     edx, edi
0x180047a44  cmp     rcx, r14
0x180047a47  jz      short loc_180047A7A
0x180047a49  test    [rcx+1Ch], esi
0x180047a4c  jz      short loc_180047A7A
0x180047a4e  cmp     byte ptr [rcx+19h], 5
0x180047a52  jb      short loc_180047A7A
0x180047a54  mov     r9, [r12]
0x180047a58  test    bl, bl
0x180047a5a  mov     rcx, [rcx+10h]
0x180047a5e  mov     dword ptr [rsp+480h+peUse], edx
0x180047a62  setnz   al
0x180047a65  mov     [rsp+480h+cchReferencedDomainName], r13
0x180047a6a  mov     byte ptr [rsp+480h+ReferencedDomainName], al
0x180047a6e  call    WPP_SF_qcqd
0x180047a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a7a  mov     rdx, [r13+38h]
0x180047a7e  test    rdx, rdx
0x180047a81  jz      short loc_180047A9E
0x180047a83  mov     eax, [r12+448h]
0x180047a8b  cmp     eax, [r13+40h]
0x180047a8f  jnb     short loc_180047A9E
0x180047a91  dec     eax
0x180047a93  mov     [rdx+rax*8], rdi
0x180047a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a9e  cmp     [r13+44h], edi
0x180047aa2  jnz     loc_180047F1C
0x180047aa8  cmp     [r13+58h], edi
0x180047aac  jz      short loc_180047ABC
0x180047aae  cmp     [r12+430h], edi
0x180047ab6  jz      loc_180047FF9
0x180047abc  mov     rcx, [r13+30h]
0x180047ac0  xor     r8d, r8d
0x180047ac3  lea     edx, [r8+2]
0x180047ac7  call    SignalNotifiers
0x180047acc  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x180047ad3  call    cs:__imp_EnterCriticalSection
0x180047ada  nop     dword ptr [rax+rax+00h]
0x180047adf  mov     rcx, cs:pConnectionNotifierList
0x180047ae6  xor     r8d, r8d
0x180047ae9  lea     edx, [r8+2]
0x180047aed  call    SignalNotifiers
0x180047af2  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x180047af9  call    cs:__imp_LeaveCriticalSection
0x180047b00  nop     dword ptr [rax+rax+00h]
0x180047b05  cmp     [r12+430h], edi
0x180047b0d  jz      loc_180047DE9
0x180047b13  cmp     cs:hRasClientEventLogHandle, rdi
0x180047b1a  jz      loc_180047DE9
0x180047b20  mov     ebx, 111h
0x180047b25  lea     rcx, [rbp+380h+var_370]; void *
0x180047b29  mov     r8d, ebx; Size
0x180047b2c  xor     edx, edx; Val
0x180047b2e  call    memset_0
0x180047b33  xor     edx, edx; Val
0x180047b35  lea     rcx, [rbp+380h+pszDest]; void *
0x180047b39  lea     r8d, [rdx+50h]; Size
0x180047b3d  call    memset_0
0x180047b42  lea     rcx, [r13+20h]
0x180047b46  mov     edx, 0Ah
0x180047b4b  call    GetUserData
0x180047b50  mov     r9, rax
0x180047b53  test    rax, rax
0x180047b56  jz      loc_180047BF5
0x180047b5c  cmp     dword ptr [rax+14h], 10h
0x180047b60  ja      loc_180047BF5
0x180047b66  movzx   ecx, byte ptr [rax+27h]
0x180047b6a  mov     edx, 50h ; 'P'; cchDest
0x180047b6f  movzx   r8d, byte ptr [rax+26h]
0x180047b74  movzx   r10d, byte ptr [rax+25h]
0x180047b79  movzx   r11d, byte ptr [rax+24h]
0x180047b7e  movzx   ebx, byte ptr [rax+23h]
0x180047b82  movzx   edi, byte ptr [r9+21h]
0x180047b87  movzx   esi, byte ptr [r9+20h]
0x180047b8c  movzx   r14d, word ptr [r9+1Eh]
0x180047b91  movzx   r15d, word ptr [r9+1Ch]
0x180047b96  movzx   eax, byte ptr [rax+22h]
0x180047b9a  mov     r9d, [r9+18h]
0x180047b9e  mov     [rsp+480h+var_418], ecx
0x180047ba2  lea     rcx, [rbp+380h+pszDest]; pszDest
0x180047ba6  mov     [rsp+480h+var_420], r8d
0x180047bab  lea     r8, a08x04x04x02x02_1; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x180047bb2  mov     [rsp+480h+var_428], r10d
0x180047bb7  mov     [rsp+480h+var_430], r11d
0x180047bbc  mov     [rsp+480h+var_438], ebx
0x180047bc0  mov     [rsp+480h+var_440], eax
0x180047bc4  mov     [rsp+480h+var_448], edi
0x180047bc8  mov     dword ptr [rsp+480h+peUse], esi
0x180047bcc  mov     dword ptr [rsp+480h+cchReferencedDomainName], r14d
0x180047bd1  mov     dword ptr [rsp+480h+ReferencedDomainName], r15d
0x180047bd6  call    StringCchPrintfA
0x180047bdb  xor     edi, edi
0x180047bdd  lea     r14, WPP_GLOBAL_Control
0x180047be4  mov     ebx, 111h
0x180047be9  lea     r15, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180047bf0  mov     esi, 2000h
0x180047bf5  mov     rcx, r13
0x180047bf8  call    IsSystemOwnedConnection
0x180047bfd  test    eax, eax
0x180047bff  jz      short loc_180047C43
0x180047c01  mov     eax, 7FFFFFFEh
0x180047c06  lea     rdx, aSystem; "SYSTEM"
0x180047c0d  lea     rcx, [rbp+380h+var_370]
0x180047c11  test    rax, rax
0x180047c14  jz      short loc_180047C30
0x180047c16  mov     r8b, [rdx]
0x180047c19  test    r8b, r8b
0x180047c1c  jz      short loc_180047C30
0x180047c1e  mov     [rcx], r8b
0x180047c21  inc     rdx
0x180047c24  inc     rcx
0x180047c27  dec     rax
0x180047c2a  sub     rbx, 1
0x180047c2e  jnz     short loc_180047C11
0x180047c30  test    rbx, rbx
0x180047c33  lea     rax, [rcx-1]
0x180047c37  cmovnz  rax, rcx
0x180047c3b  mov     [rax], dil
0x180047c3e  jmp     loc_180047D02
0x180047c43  xor     edx, edx; Val
0x180047c45  lea     rcx, [rbp+380h+Name]; void *
0x180047c4c  mov     r8d, 202h; Size
0x180047c52  call    memset_0
0x180047c57  mov     rdx, [r13+60h]; Sid
0x180047c5b  lea     rax, [rsp+480h+var_410]
0x180047c60  mov     [rsp+480h+peUse], rax; peUse
0x180047c65  lea     r9, [rsp+480h+cchName]; cchName
0x180047c6a  xorps   xmm0, xmm0
0x180047c6d  mov     [rsp+480h+cchName], 101h
0x180047c75  lea     rax, [rsp+480h+var_40C]
0x180047c7a  mov     [rsp+480h+var_40C], 10h
0x180047c82  mov     [rsp+480h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180047c87  lea     r8, [rbp+380h+Name]; Name
0x180047c8e  lea     rax, [rbp+380h+var_400]
0x180047c92  mov     [rsp+480h+var_410], edi
0x180047c96  xor     ecx, ecx; lpSystemName
0x180047c98  mov     [rsp+480h+ReferencedDomainName], rax; ReferencedDomainName
0x180047c9d  movups  xmmword ptr [rbp+380h+var_400], xmm0
0x180047ca1  movups  [rbp+380h+var_3F0], xmm0
0x180047ca5  call    cs:__imp_LookupAccountSidW
0x180047cac  nop     dword ptr [rax+rax+00h]
0x180047cb1  test    eax, eax
0x180047cb3  jnz     short loc_180047CDF
0x180047cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180047cbc  cmp     rcx, r14
0x180047cbf  jz      short loc_180047D09
0x180047cc1  test    [rcx+1Ch], esi
0x180047cc4  jz      short loc_180047D09
0x180047cc6  cmp     byte ptr [rcx+19h], 2
0x180047cca  jb      short loc_180047D09
0x180047ccc  mov     rcx, [rcx+10h]
0x180047cd0  mov     edx, 0EFh
0x180047cd5  mov     r8, r15
0x180047cd8  call    WPP_SF_
0x180047cdd  jmp     short loc_180047D02
0x180047cdf  lea     rax, [rbp+380h+Name]
0x180047ce6  mov     rdx, rbx; cchDest
0x180047ce9  lea     r9, [rbp+380h+var_400]
0x180047ced  mov     [rsp+480h+ReferencedDomainName], rax
0x180047cf2  lea     r8, aSS; "%S\\%S"
0x180047cf9  lea     rcx, [rbp+380h+var_370]; pszDest
0x180047cfd  call    StringCchPrintfA
0x180047d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180047d09  movsxd  rax, dword ptr [r12+52Ch]
0x180047d11  test    eax, eax
0x180047d13  js      loc_180047DE9
0x180047d19  cmp     eax, 0Ah
0x180047d1c  jnb     loc_180047DE9
0x180047d22  mov     r9, rax
0x180047d25  lea     rbx, rdrMapping
0x180047d2c  add     r9, r9
0x180047d2f  mov     r8d, [rbx+r9*8+4]
0x180047d34  test    r8d, r8d
0x180047d37  jz      loc_180047DE9
0x180047d3d  lea     rax, [rbp+380h+pszDest]
0x180047d41  xorps   xmm0, xmm0
0x180047d44  mov     qword ptr [rbp+380h+var_400], rax
0x180047d48  lea     rax, [rbp+380h+var_370]
0x180047d4c  mov     qword ptr [rbp+380h+var_400+8], rax
0x180047d50  lea     rax, [r13+1BDh]
0x180047d57  mov     qword ptr [rbp+380h+var_3F0], rax
0x180047d5b  lea     rax, [rbp+380h+var_3E0]
0x180047d5f  mov     qword ptr [rbp+380h+var_3F0+8], rax
0x180047d63  movups  xmmword ptr [rbp+380h+var_3E0], xmm0
0x180047d67  movups  [rbp+380h+var_3D0], xmm0
0x180047d6b  cmp     rcx, r14
0x180047d6e  jz      short loc_180047D96
0x180047d70  test    [rcx+1Ch], esi
0x180047d73  jz      short loc_180047D96
0x180047d75  cmp     byte ptr [rcx+19h], 5
0x180047d79  jb      short loc_180047D96
0x180047d7b  mov     r9, [rbx+r9*8+8]
0x180047d80  mov     edx, 0F0h
0x180047d85  mov     rcx, [rcx+10h]
0x180047d89  mov     dword ptr [rsp+480h+ReferencedDomainName], r8d
0x180047d8e  mov     r8, r15
0x180047d91  call    WPP_SF_sd
0x180047d96  movsxd  r9, dword ptr [r12+52Ch]
0x180047d9e  lea     r8, aD_0; "%d"
0x180047da5  add     r9, r9
0x180047da8  lea     rcx, [rbp+380h+var_3E0]; pszDest
0x180047dac  mov     edx, 20h ; ' '; cchDest
0x180047db1  mov     r9d, [rbx+r9*8+4]
0x180047db6  call    StringCchPrintfA
0x180047dbb  mov     rcx, cs:hRasClientEventLogHandle; hLogHandle
0x180047dc2  lea     rax, [rbp+380h+var_400]
0x180047dc6  mov     edx, 4; dwEventType
0x180047dcb  mov     dword ptr [rsp+480h+cchReferencedDomainName], edi; dwErrorCode
0x180047dcf  mov     r9d, edx; dwSubStringCount
0x180047dd2  mov     [rsp+480h+ReferencedDomainName], rax; plpszSubStringArray
0x180047dd7  mov     r8d, 4F02h; dwMessageId
0x180047ddd  call    cs:__imp_RouterLogEventA
0x180047de4  nop     dword ptr [rax+rax+00h]
0x180047de9  mov     rdx, [r13+10h]
0x180047ded  mov     ecx, 8
0x180047df2  call    SendSensNotification
0x180047df7  test    eax, eax
0x180047df9  jz      short loc_180047E26
0x180047dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e02  cmp     rcx, r14
0x180047e05  jz      short loc_180047E2D
0x180047e07  test    [rcx+1Ch], esi
0x180047e0a  jz      short loc_180047E2D
0x180047e0c  cmp     byte ptr [rcx+19h], 2
0x180047e10  jb      short loc_180047E2D
0x180047e12  mov     rcx, [rcx+10h]
0x180047e16  mov     edx, 0F1h
0x180047e1b  mov     r9d, eax
0x180047e1e  mov     r8, r15
0x180047e21  call    WPP_SF_d
0x180047e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e2d  cmp     dword ptr [r12+550h], 3
0x180047e36  jnz     short loc_180047E47
0x180047e38  test    byte ptr [r12+4C8h], 20h
0x180047e41  jnz     loc_180047F0E
0x180047e47  lea     rdx, g_RasEvent
0x180047e4e  mov     cs:g_RasEvent, 80h
0x180047e58  mov     rcx, r13
0x180047e5b  call    DwSendNotificationInternal
  ... truncated ...
```
