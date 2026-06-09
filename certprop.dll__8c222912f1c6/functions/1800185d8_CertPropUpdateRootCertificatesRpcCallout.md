# CertPropUpdateRootCertificatesRpcCallout

- ea: `0x1800185d8`
- end: `0x18001889d`
- name: `CertPropUpdateRootCertificatesRpcCallout`
- size: `709`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180023e20`

## callees

- `0x180004600`
- `0x18000cda0`
- `0x1800103f0`
- `0x180010b54`
- `0x180016090`
- `0x1800185d8`
- `0x180018b58`
- `0x180018bb4`
- `0x180021154`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018622`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018632`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001880c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018622`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018632`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001880c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001881c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001882f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001881c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001882f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018709`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018709`

## pseudocode

```c
__int64 __fastcall CertPropUpdateRootCertificatesRpcCallout(int a1)
{
  int v2; // r15d
  int v3; // r12d
  __int64 v4; // rcx
  STRSAFE_LPSTR v5; // rcx
  char *v6; // rbx
  int v7; // r14d
  unsigned int updated; // edi
  __int64 i; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v13; // [rsp+30h] [rbp-A9h] BYREF
  int v14; // [rsp+34h] [rbp-A5h] BYREF
  int v15; // [rsp+38h] [rbp-A1h] BYREF
  unsigned int v16; // [rsp+3Ch] [rbp-9Dh] BYREF
  GUID ActivityId; // [rsp+40h] [rbp-99h] BYREF
  GUID v18; // [rsp+50h] [rbp-89h] BYREF
  char v19[32]; // [rsp+60h] [rbp-79h] BYREF
  int *v20; // [rsp+80h] [rbp-59h]
  __int64 v21; // [rsp+88h] [rbp-51h]
  int *v22; // [rsp+90h] [rbp-49h]
  __int64 v23; // [rsp+98h] [rbp-41h]
  int *v24; // [rsp+A0h] [rbp-39h]
  __int64 v25; // [rsp+A8h] [rbp-31h]
  unsigned int *v26; // [rsp+B0h] [rbp-29h]
  __int64 v27; // [rsp+B8h] [rbp-21h]
  char v28[32]; // [rsp+C0h] [rbp-19h] BYREF

  v2 = 0;
  v3 = 0;
  ActivityId = 0;
  v18 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v18);
  if ( (unsigned int)dword_180031008 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
    tlgWriteTransfer_EventWriteTransfer(v4, byte_180029A1D, &v18, &ActivityId, 2, v28);
  WppTraceIndent(v4, 2);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
  }
  if ( g_fEnableRootCertProp )
  {
    EnterCriticalSection(&g_csSessionList);
    v6 = (char *)g_pSessionList;
    v7 = 1;
    if ( !g_pSessionList )
      goto LABEL_20;
    do
    {
      if ( a1 == *((_DWORD *)v6 + 2) )
        break;
      v6 = *(char **)v6;
    }
    while ( v6 );
    if ( v6 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 72));
      v2 = 1;
      if ( *((_DWORD *)v6 + 7) )
      {
        for ( i = *((_QWORD *)v6 + 17); i; i = *(_QWORD *)(i + 240) )
        {
          ReaderMonitorUpdateRootCerts(v6 + 24, i);
          v3 += *(_DWORD *)(i + 220);
        }
        updated = CertPropUpdateRootCertificates(v6);
      }
      else
      {
        updated = -2146435071;
      }
    }
    else
    {
LABEL_20:
      updated = 1365;
    }
  }
  else
  {
    v6 = 0;
    v7 = 0;
    updated = 1058;
  }
  if ( (unsigned int)dword_180031008 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
  {
    v13 = a1;
    v20 = &v13;
    v14 = g_fEnableRootCertProp;
    v21 = 4;
    v22 = &v14;
    v24 = &v15;
    v26 = &v16;
    v23 = 4;
    v15 = v3;
    v25 = 4;
    v16 = updated;
    v27 = 4;
    tlgWriteTransfer_EventWriteTransfer(v10, byte_18002961B, &v18, &ActivityId, 6, v19);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( v2 == 1 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 72));
  if ( v7 == 1 )
    LeaveCriticalSection(&g_csSessionList);
  WppTraceIndent(v11, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      updated);
  }
  return updated;
}

```

## disassembly

```asm
0x1800185d8  push    rbp
0x1800185da  push    rbx
0x1800185db  push    rsi
0x1800185dc  push    rdi
0x1800185dd  push    r12
0x1800185df  push    r13
0x1800185e1  push    r14
0x1800185e3  push    r15
0x1800185e5  lea     rbp, [rsp-1Fh]
0x1800185ea  sub     rsp, 0F8h
0x1800185f1  mov     rax, cs:__security_cookie
0x1800185f8  xor     rax, rsp
0x1800185fb  mov     [rbp+57h+var_50], rax
0x1800185ff  xor     esi, esi
0x180018601  lea     rdx, [rsp+130h+ActivityId]; ActivityId
0x180018606  mov     r13d, ecx
0x180018609  xorps   xmm0, xmm0
0x18001860c  xorps   xmm1, xmm1
0x18001860f  mov     r15d, esi
0x180018612  mov     r12d, esi
0x180018615  lea     ecx, [rsi+5]; ControlCode
0x180018618  movups  xmmword ptr [rsp+130h+ActivityId.Data1], xmm0
0x18001861d  movups  xmmword ptr [rsp+130h+var_E0.Data1], xmm1
0x180018622  call    cs:__imp_EventActivityIdControl
0x180018628  lea     edi, [rsi+1]
0x18001862b  mov     ecx, edi; ControlCode
0x18001862d  lea     rdx, [rsp+130h+var_E0]; ActivityId
0x180018632  call    cs:__imp_EventActivityIdControl
0x180018638  mov     eax, cs:dword_180031008
0x18001863e  lea     ebx, [rsi+2]
0x180018641  cmp     eax, 5
0x180018644  jbe     short loc_18001867C
0x180018646  mov     rdx, 200000000000h
0x180018650  call    _tlgKeywordOn
0x180018655  test    al, al
0x180018657  jz      short loc_18001867C
0x180018659  lea     rax, [rbp+57h+var_70]
0x18001865d  mov     [rsp+130h+var_108], rax
0x180018662  lea     r9, [rsp+130h+ActivityId]
0x180018667  lea     r8, [rsp+130h+var_E0]
0x18001866c  mov     [rsp+130h+var_110], ebx
0x180018670  lea     rdx, byte_180029A1D
0x180018677  call    _tlgWriteTransfer_EventWriteTransfer
0x18001867c  mov     edx, ebx
0x18001867e  call    WppTraceIndent
0x180018683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001868a  lea     rax, WPP_GLOBAL_Control
0x180018691  cmp     rcx, rax
0x180018694  jz      short loc_1800186BE
0x180018696  test    [rcx+1Ch], dil
0x18001869a  jz      short loc_1800186BE
0x18001869c  cmp     byte ptr [rcx+19h], 4
0x1800186a0  jb      short loc_1800186BE
0x1800186a2  mov     r9, cs:WPP_pszIndent
0x1800186a9  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800186b0  mov     rcx, [rcx+10h]
0x1800186b4  mov     edx, 10h
0x1800186b9  call    WPP_SF_s
0x1800186be  cmp     cs:g_fEnableRootCertProp, esi
0x1800186c4  jnz     short loc_1800186D6
0x1800186c6  mov     rbx, rsi
0x1800186c9  mov     r14d, esi
0x1800186cc  mov     edi, 422h
0x1800186d1  jmp     loc_180018757
0x1800186d6  lea     rcx, g_csSessionList; lpCriticalSection
0x1800186dd  call    cs:__imp_EnterCriticalSection
0x1800186e3  mov     rbx, cs:g_pSessionList
0x1800186ea  mov     r14d, edi
0x1800186ed  test    rbx, rbx
0x1800186f0  jz      short loc_180018752
0x1800186f2  cmp     r13d, [rbx+8]
0x1800186f6  jz      short loc_180018700
0x1800186f8  mov     rbx, [rbx]
0x1800186fb  test    rbx, rbx
0x1800186fe  jnz     short loc_1800186F2
0x180018700  test    rbx, rbx
0x180018703  jz      short loc_180018752
0x180018705  lea     rcx, [rbx+48h]; lpCriticalSection
0x180018709  call    cs:__imp_EnterCriticalSection
0x18001870f  mov     r15d, edi
0x180018712  cmp     [rbx+1Ch], esi
0x180018715  jnz     short loc_18001871E
0x180018717  mov     edi, 80100001h
0x18001871c  jmp     short loc_180018757
0x18001871e  mov     rdi, [rbx+88h]
0x180018725  jmp     short loc_180018741
0x180018727  mov     rdx, rdi
0x18001872a  lea     rcx, [rbx+18h]
0x18001872e  call    ReaderMonitorUpdateRootCerts
0x180018733  add     r12d, [rdi+0DCh]
0x18001873a  mov     rdi, [rdi+0F0h]
0x180018741  test    rdi, rdi
0x180018744  jnz     short loc_180018727
0x180018746  mov     rcx, rbx
0x180018749  call    CertPropUpdateRootCertificates
0x18001874e  mov     edi, eax
0x180018750  jmp     short loc_180018757
0x180018752  mov     edi, 555h
0x180018757  mov     eax, cs:dword_180031008
0x18001875d  cmp     eax, 5
0x180018760  jbe     loc_180018800
0x180018766  mov     rdx, 200000000000h
0x180018770  call    _tlgKeywordOn
0x180018775  test    al, al
0x180018777  jz      loc_180018800
0x18001877d  lea     rax, [rsp+130h+var_100]
0x180018782  mov     [rsp+130h+var_100], r13d
0x180018787  mov     [rbp+57h+var_B0], rax
0x18001878b  lea     r9, [rsp+130h+ActivityId]
0x180018790  mov     eax, cs:g_fEnableRootCertProp
0x180018796  lea     r8, [rsp+130h+var_E0]
0x18001879b  mov     [rsp+130h+var_FC], eax
0x18001879f  lea     rdx, byte_18002961B
0x1800187a6  lea     rax, [rsp+130h+var_FC]
0x1800187ab  mov     [rbp+57h+var_A8], 4
0x1800187b3  mov     [rbp+57h+var_A0], rax
0x1800187b7  lea     rax, [rsp+130h+var_F8]
0x1800187bc  mov     [rbp+57h+var_90], rax
0x1800187c0  lea     rax, [rsp+130h+var_F4]
0x1800187c5  mov     [rbp+57h+var_80], rax
0x1800187c9  lea     rax, [rbp+57h+var_D0]
0x1800187cd  mov     [rsp+130h+var_108], rax
0x1800187d2  mov     [rsp+130h+var_110], 6
0x1800187da  mov     [rbp+57h+var_98], 4
0x1800187e2  mov     [rsp+130h+var_F8], r12d
0x1800187e7  mov     [rbp+57h+var_88], 4
0x1800187ef  mov     [rsp+130h+var_F4], edi
0x1800187f3  mov     [rbp+57h+var_78], 4
0x1800187fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180018800  mov     esi, 2
0x180018805  lea     rdx, [rsp+130h+ActivityId]; ActivityId
0x18001880a  mov     ecx, esi; ControlCode
0x18001880c  call    cs:__imp_EventActivityIdControl
0x180018812  cmp     r15d, 1
0x180018816  jnz     short loc_180018822
0x180018818  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001881c  call    cs:__imp_LeaveCriticalSection
0x180018822  cmp     r14d, 1
0x180018826  jnz     short loc_180018835
0x180018828  lea     rcx, g_csSessionList; lpCriticalSection
0x18001882f  call    cs:__imp_LeaveCriticalSection
0x180018835  mov     edx, esi
0x180018837  call    WppTraceIndent
0x18001883c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018843  lea     rax, WPP_GLOBAL_Control
0x18001884a  cmp     rcx, rax
0x18001884d  jz      short loc_18001887B
0x18001884f  test    byte ptr [rcx+1Ch], 1
0x180018853  jz      short loc_18001887B
0x180018855  cmp     byte ptr [rcx+19h], 4
0x180018859  jb      short loc_18001887B
0x18001885b  mov     r9, cs:WPP_pszIndent
0x180018862  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180018869  mov     rcx, [rcx+10h]
0x18001886d  mov     edx, 11h
0x180018872  mov     [rsp+130h+var_110], edi
0x180018876  call    WPP_SF_sD
0x18001887b  mov     eax, edi
0x18001887d  mov     rcx, [rbp+57h+var_50]
0x180018881  xor     rcx, rsp; StackCookie
0x180018884  call    __security_check_cookie
0x180018889  add     rsp, 0F8h
0x180018890  pop     r15
0x180018892  pop     r14
0x180018894  pop     r13
0x180018896  pop     r12
0x180018898  pop     rdi
0x180018899  pop     rsi
0x18001889a  pop     rbx
0x18001889b  pop     rbp
0x18001889c  retn
```
