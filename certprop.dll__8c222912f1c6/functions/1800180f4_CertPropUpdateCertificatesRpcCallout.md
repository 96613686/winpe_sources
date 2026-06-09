# CertPropUpdateCertificatesRpcCallout

- ea: `0x1800180f4`
- end: `0x1800185cf`
- name: `CertPropUpdateCertificatesRpcCallout`
- size: `1243`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180023c10`

## callees

- `0x180004600`
- `0x1800062e0`
- `0x18000cda0`
- `0x18000d220`
- `0x180010b54`
- `0x180016090`
- `0x1800180f4`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001813e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001814e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001853b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001813e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001814e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001853b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001854b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001855e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001854b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001855e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018200`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018200`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183d4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001843e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001843e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001844f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001844f`

## pseudocode

```c
__int64 __fastcall CertPropUpdateCertificatesRpcCallout(int a1, __int64 a2)
{
  unsigned __int16 *v4; // rsi
  int v5; // r14d
  __int64 v6; // rcx
  STRSAFE_LPSTR v7; // rcx
  char *i; // rbx
  int v9; // r12d
  DWORD LastError; // edi
  __int64 v11; // rcx
  int v12; // r9d
  int v13; // eax
  int v14; // ecx
  int v15; // ecx
  DWORD v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // eax
  unsigned __int16 *v23; // rax
  int v24; // edx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  DWORD v30; // [rsp+30h] [rbp-D0h] BYREF
  int v31; // [rsp+34h] [rbp-CCh] BYREF
  int v32; // [rsp+38h] [rbp-C8h] BYREF
  int v33; // [rsp+3Ch] [rbp-C4h] BYREF
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+44h] [rbp-BCh] BYREF
  int v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+4Ch] [rbp-B4h] BYREF
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  GUID ActivityId; // [rsp+58h] [rbp-A8h] BYREF
  GUID v40; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v41[32]; // [rsp+80h] [rbp-80h] BYREF
  int *v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h]
  _QWORD v44[2]; // [rsp+B0h] [rbp-50h] BYREF
  DWORD *v45; // [rsp+C0h] [rbp-40h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  int *v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  int *v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  int *v51; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+F8h] [rbp-8h]
  int *v53; // [rsp+100h] [rbp+0h]
  __int64 v54; // [rsp+108h] [rbp+8h]
  DWORD *v55; // [rsp+110h] [rbp+10h]
  __int64 v56; // [rsp+118h] [rbp+18h]
  int *v57; // [rsp+120h] [rbp+20h]
  __int64 v58; // [rsp+128h] [rbp+28h]
  char v59[32]; // [rsp+130h] [rbp+30h] BYREF

  v4 = 0;
  v5 = 0;
  ActivityId = 0;
  v40 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v40);
  if ( (unsigned int)dword_180031008 > 5 && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
    tlgWriteTransfer_EventWriteTransfer(v6, byte_1800295E9, &v40, &ActivityId, 2, v59);
  WppTraceIndent(v6, 2);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids, WPP_pszIndent);
  }
  if ( g_fEnableCertProp )
  {
    EnterCriticalSection(&g_csSessionList);
    v9 = 1;
    for ( i = (char *)g_pSessionList; ; i = *(char **)i )
    {
      if ( !i )
      {
        LastError = 1365;
        goto LABEL_15;
      }
      if ( a1 == *((_DWORD *)i + 2) )
        break;
    }
    if ( (unsigned int)dword_180031008 > 5 )
    {
      if ( i == (char *)-24LL )
        v14 = 0;
      else
        v14 = *((_DWORD *)i + 70);
      v37 = v14;
      v42 = &v37;
      v43 = 4;
      if ( i == (char *)-24LL )
        v15 = 0;
      else
        v15 = *((_DWORD *)i + 6);
      v38 = v15;
      v44[0] = &v38;
      v44[1] = 4;
      if ( i == (char *)-24LL )
        v16 = 0;
      else
        v16 = *((_DWORD *)i + 7);
      v30 = v16;
      v45 = &v30;
      v46 = 4;
      if ( i == (char *)-24LL )
        v17 = 0;
      else
        v17 = *((_DWORD *)i + 8);
      v31 = v17;
      v47 = &v31;
      v48 = 4;
      if ( i == (char *)-24LL )
        v18 = 0;
      else
        v18 = *((_DWORD *)i + 9);
      v32 = v18;
      v49 = &v32;
      v50 = 4;
      if ( i == (char *)-24LL )
        v19 = 0;
      else
        v19 = *((_DWORD *)i + 10);
      v33 = v19;
      v51 = &v33;
      v52 = 4;
      if ( i == (char *)-24LL )
        v20 = 0;
      else
        v20 = *((_DWORD *)i + 11);
      v34 = v20;
      v53 = &v34;
      v54 = 4;
      if ( i == (char *)-24LL )
        v21 = 0;
      else
        v21 = *((_DWORD *)i + 16);
      v35 = v21;
      v55 = (DWORD *)&v35;
      v56 = 4;
      if ( i == (char *)-24LL )
        v22 = 0;
      else
        v22 = *((_DWORD *)i + 12);
      v36 = v22;
      v58 = 4;
      v57 = &v36;
      tlgWriteTransfer_EventWriteTransfer(&v35, byte_180029A53, &v40, &ActivityId, 11, v41);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(i + 72));
    v5 = 1;
    if ( *((_DWORD *)i + 8) )
    {
      v4 = (unsigned __int16 *)*((_QWORD *)i + 17);
      LastError = 0;
      while ( v4 )
      {
        v23 = *(unsigned __int16 **)v4;
        do
        {
          v7 = (STRSAFE_LPSTR)*(unsigned __int16 *)((char *)v23 + a2 - *(_QWORD *)v4);
          v24 = *v23 - (_DWORD)v7;
          if ( v24 )
            break;
          ++v23;
        }
        while ( (_DWORD)v7 );
        if ( !v24 )
        {
          ReaderMonitorUpdateCerts(i + 24, v4);
          if ( !SetEvent(*((HANDLE *)i + 14)) )
            LastError = GetLastError();
          break;
        }
        v4 = (unsigned __int16 *)*((_QWORD *)v4 + 30);
      }
    }
    else
    {
      LastError = -2146435071;
    }
  }
  else
  {
    i = 0;
    v9 = 0;
    LastError = 1058;
  }
LABEL_15:
  if ( (unsigned int)dword_180031008 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
  {
    v36 = a1;
    v42 = &v36;
    v43 = 4;
    tlgCreate1Sz_wchar_t(v44, a2);
    if ( v4 )
      v13 = *((_DWORD *)v4 + 54);
    else
      v13 = v12;
    v35 = v13;
    v45 = (DWORD *)&v35;
    v46 = 4;
    if ( v4 )
      v25 = *((_DWORD *)v4 + 55);
    else
      v25 = v12;
    v34 = v25;
    v47 = &v34;
    v48 = 4;
    if ( v4 )
      v26 = *((_DWORD *)v4 + 56);
    else
      v26 = 1;
    v33 = v26;
    v49 = &v33;
    v50 = 4;
    if ( v4 )
      v27 = *((_DWORD *)v4 + 57);
    else
      v27 = 1;
    v32 = v27;
    v52 = 4;
    v51 = &v32;
    v31 = g_fEnableCertProp;
    v53 = &v31;
    v55 = &v30;
    v54 = 4;
    v30 = LastError;
    v56 = 4;
    tlgWriteTransfer_EventWriteTransfer(v11, byte_18002993B, &v40, &ActivityId, 10, v41);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( v5 == 1 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(i + 72));
  if ( v9 == 1 )
    LeaveCriticalSection(&g_csSessionList);
  WppTraceIndent(v28, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800180f4  push    rbp
0x1800180f6  push    rbx
0x1800180f7  push    rsi
0x1800180f8  push    rdi
0x1800180f9  push    r12
0x1800180fb  push    r13
0x1800180fd  push    r14
0x1800180ff  push    r15
0x180018101  lea     rbp, [rsp-68h]
0x180018106  sub     rsp, 168h
0x18001810d  mov     rax, cs:__security_cookie
0x180018114  xor     rax, rsp
0x180018117  mov     [rbp+0A0h+var_50], rax
0x18001811b  mov     r13, rdx
0x18001811e  mov     r15d, ecx
0x180018121  xorps   xmm0, xmm0
0x180018124  lea     rdx, [rsp+1A0h+ActivityId]; ActivityId
0x180018129  xorps   xmm1, xmm1
0x18001812c  xor     esi, esi
0x18001812e  xor     r14d, r14d
0x180018131  movups  xmmword ptr [rsp+1A0h+ActivityId.Data1], xmm0
0x180018136  lea     ecx, [rsi+5]; ControlCode
0x180018139  movups  xmmword ptr [rsp+1A0h+var_138.Data1], xmm1
0x18001813e  call    cs:__imp_EventActivityIdControl
0x180018144  lea     ebx, [rsi+1]
0x180018147  mov     ecx, ebx; ControlCode
0x180018149  lea     rdx, [rsp+1A0h+var_138]; ActivityId
0x18001814e  call    cs:__imp_EventActivityIdControl
0x180018154  mov     eax, cs:dword_180031008
0x18001815a  cmp     eax, 5
0x18001815d  jbe     short loc_180018199
0x18001815f  mov     rdx, 200000000000h
0x180018169  call    _tlgKeywordOn
0x18001816e  test    al, al
0x180018170  jz      short loc_180018199
0x180018172  lea     rax, [rbp+0A0h+var_70]
0x180018176  mov     [rsp+1A0h+var_178], rax
0x18001817b  lea     r9, [rsp+1A0h+ActivityId]
0x180018180  lea     r8, [rsp+1A0h+var_138]
0x180018185  mov     [rsp+1A0h+var_180], 2
0x18001818d  lea     rdx, byte_1800295E9
0x180018194  call    _tlgWriteTransfer_EventWriteTransfer
0x180018199  mov     edx, 2
0x18001819e  call    WppTraceIndent
0x1800181a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181aa  lea     rax, WPP_GLOBAL_Control
0x1800181b1  mov     edi, 4
0x1800181b6  cmp     rcx, rax
0x1800181b9  jz      short loc_1800181E0
0x1800181bb  test    [rcx+1Ch], bl
0x1800181be  jz      short loc_1800181E0
0x1800181c0  cmp     [rcx+19h], dil
0x1800181c4  jb      short loc_1800181E0
0x1800181c6  mov     r9, cs:WPP_pszIndent
0x1800181cd  lea     edx, [rdi+49h]
0x1800181d0  mov     rcx, [rcx+10h]
0x1800181d4  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800181db  call    WPP_SF_s
0x1800181e0  xor     r9d, r9d
0x1800181e3  cmp     cs:g_fEnableCertProp, r9d
0x1800181ea  jnz     short loc_1800181F9
0x1800181ec  mov     ebx, r9d
0x1800181ef  mov     r12d, r9d
0x1800181f2  mov     edi, 422h
0x1800181f7  jmp     short loc_180018228
0x1800181f9  lea     rcx, g_csSessionList; lpCriticalSection
0x180018200  call    cs:__imp_EnterCriticalSection
0x180018206  mov     r12d, ebx
0x180018209  xor     r9d, r9d
0x18001820c  mov     rbx, cs:g_pSessionList
0x180018213  jmp     short loc_18001821E
0x180018215  cmp     r15d, [rbx+8]
0x180018219  jz      short loc_180018286
0x18001821b  mov     rbx, [rbx]
0x18001821e  test    rbx, rbx
0x180018221  jnz     short loc_180018215
0x180018223  mov     edi, 555h
0x180018228  mov     eax, cs:dword_180031008
0x18001822e  cmp     eax, 5
0x180018231  jbe     loc_18001852B
0x180018237  mov     rdx, 200000000000h
0x180018241  call    _tlgKeywordOn
0x180018246  test    al, al
0x180018248  jz      loc_18001852B
0x18001824e  lea     rax, [rsp+1A0h+var_158]
0x180018253  mov     [rsp+1A0h+var_158], r15d
0x180018258  mov     r15d, 4
0x18001825e  mov     [rbp+0A0h+var_100], rax
0x180018262  mov     rdx, r13
0x180018265  mov     [rbp+0A0h+var_F8], r15
0x180018269  lea     rcx, [rbp+0A0h+var_F0]
0x18001826d  call    _tlgCreate1Sz_wchar_t
0x180018272  test    rsi, rsi
0x180018275  jz      loc_18001845F
0x18001827b  mov     eax, [rsi+0D8h]
0x180018281  jmp     loc_180018462
0x180018286  mov     eax, cs:dword_180031008
0x18001828c  cmp     eax, 5
0x18001828f  jbe     loc_1800183D0
0x180018295  lea     rax, [rbx+18h]
0x180018299  test    rax, rax
0x18001829c  jz      short loc_1800182A6
0x18001829e  mov     ecx, [rbx+118h]
0x1800182a4  jmp     short loc_1800182A9
0x1800182a6  mov     ecx, r9d
0x1800182a9  mov     [rsp+1A0h+var_154], ecx
0x1800182ad  lea     rcx, [rsp+1A0h+var_154]
0x1800182b2  mov     [rbp+0A0h+var_100], rcx
0x1800182b6  mov     [rbp+0A0h+var_F8], rdi
0x1800182ba  test    rax, rax
0x1800182bd  jz      short loc_1800182C3
0x1800182bf  mov     ecx, [rax]
0x1800182c1  jmp     short loc_1800182C6
0x1800182c3  mov     ecx, r9d
0x1800182c6  mov     [rsp+1A0h+var_150], ecx
0x1800182ca  lea     rcx, [rsp+1A0h+var_150]
0x1800182cf  mov     [rbp+0A0h+var_F0], rcx
0x1800182d3  mov     [rbp+0A0h+var_E8], rdi
0x1800182d7  test    rax, rax
0x1800182da  jz      short loc_1800182E1
0x1800182dc  mov     ecx, [rbx+1Ch]
0x1800182df  jmp     short loc_1800182E4
0x1800182e1  mov     ecx, r9d
0x1800182e4  mov     [rsp+1A0h+var_170], ecx
0x1800182e8  lea     rcx, [rsp+1A0h+var_170]
0x1800182ed  mov     [rbp+0A0h+var_E0], rcx
0x1800182f1  mov     [rbp+0A0h+var_D8], rdi
0x1800182f5  test    rax, rax
0x1800182f8  jz      short loc_1800182FF
0x1800182fa  mov     ecx, [rbx+20h]
0x1800182fd  jmp     short loc_180018302
0x1800182ff  mov     ecx, r9d
0x180018302  mov     [rsp+1A0h+var_16C], ecx
0x180018306  lea     rcx, [rsp+1A0h+var_16C]
0x18001830b  mov     [rbp+0A0h+var_D0], rcx
0x18001830f  mov     [rbp+0A0h+var_C8], rdi
0x180018313  test    rax, rax
0x180018316  jz      short loc_18001831D
0x180018318  mov     ecx, [rbx+24h]
0x18001831b  jmp     short loc_180018320
0x18001831d  mov     ecx, r9d
0x180018320  mov     [rsp+1A0h+var_168], ecx
0x180018324  lea     rcx, [rsp+1A0h+var_168]
0x180018329  mov     [rbp+0A0h+var_C0], rcx
0x18001832d  mov     [rbp+0A0h+var_B8], rdi
0x180018331  test    rax, rax
0x180018334  jz      short loc_18001833B
0x180018336  mov     ecx, [rbx+28h]
0x180018339  jmp     short loc_18001833E
0x18001833b  mov     ecx, r9d
0x18001833e  mov     [rsp+1A0h+var_164], ecx
0x180018342  lea     rcx, [rsp+1A0h+var_164]
0x180018347  mov     [rbp+0A0h+var_B0], rcx
0x18001834b  mov     [rbp+0A0h+var_A8], rdi
0x18001834f  test    rax, rax
0x180018352  jz      short loc_180018359
0x180018354  mov     ecx, [rbx+2Ch]
0x180018357  jmp     short loc_18001835C
0x180018359  mov     ecx, r9d
0x18001835c  mov     [rsp+1A0h+var_160], ecx
0x180018360  lea     rcx, [rsp+1A0h+var_160]
0x180018365  mov     [rbp+0A0h+var_A0], rcx
0x180018369  mov     [rbp+0A0h+var_98], rdi
0x18001836d  test    rax, rax
0x180018370  jz      short loc_180018377
0x180018372  mov     ecx, [rbx+40h]
0x180018375  jmp     short loc_18001837A
0x180018377  mov     ecx, r9d
0x18001837a  mov     [rsp+1A0h+var_15C], ecx
0x18001837e  lea     rcx, [rsp+1A0h+var_15C]
0x180018383  mov     [rbp+0A0h+var_90], rcx
0x180018387  mov     [rbp+0A0h+var_88], rdi
0x18001838b  test    rax, rax
0x18001838e  jz      short loc_180018395
0x180018390  mov     eax, [rbx+30h]
0x180018393  jmp     short loc_180018398
0x180018395  mov     eax, r9d
0x180018398  mov     [rsp+1A0h+var_158], eax
0x18001839c  lea     r9, [rsp+1A0h+ActivityId]
0x1800183a1  lea     rax, [rsp+1A0h+var_158]
0x1800183a6  mov     [rbp+0A0h+var_78], rdi
0x1800183aa  mov     [rbp+0A0h+var_80], rax
0x1800183ae  lea     r8, [rsp+1A0h+var_138]
0x1800183b3  lea     rax, [rbp+0A0h+var_120]
0x1800183b7  mov     [rsp+1A0h+var_178], rax
0x1800183bc  lea     rdx, byte_180029A53
0x1800183c3  mov     [rsp+1A0h+var_180], 0Bh
0x1800183cb  call    _tlgWriteTransfer_EventWriteTransfer
0x1800183d0  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800183d4  call    cs:__imp_EnterCriticalSection
0x1800183da  xor     r9d, r9d
0x1800183dd  mov     r14d, r12d
0x1800183e0  cmp     [rbx+20h], r9d
0x1800183e4  jnz     short loc_1800183F0
0x1800183e6  mov     edi, 80100001h
0x1800183eb  jmp     loc_180018228
0x1800183f0  mov     rsi, [rbx+88h]
0x1800183f7  mov     edi, r9d
0x1800183fa  jmp     short loc_180018424
0x1800183fc  mov     rax, [rsi]
0x1800183ff  mov     r8, r13
0x180018402  sub     r8, rax
0x180018405  movzx   edx, word ptr [rax]
0x180018408  movzx   ecx, word ptr [rax+r8]
0x18001840d  sub     edx, ecx
0x18001840f  jnz     short loc_180018419
0x180018411  add     rax, 2
0x180018415  test    ecx, ecx
0x180018417  jnz     short loc_180018405
0x180018419  test    edx, edx
0x18001841b  jz      short loc_18001842E
0x18001841d  mov     rsi, [rsi+0F0h]
0x180018424  test    rsi, rsi
0x180018427  jnz     short loc_1800183FC
0x180018429  jmp     loc_180018228
0x18001842e  lea     rcx, [rbx+18h]
0x180018432  mov     rdx, rsi
0x180018435  call    ReaderMonitorUpdateCerts
0x18001843a  mov     rcx, [rbx+70h]; hEvent
0x18001843e  call    cs:__imp_SetEvent
0x180018444  xor     r9d, r9d
0x180018447  test    eax, eax
0x180018449  jnz     loc_180018228
0x18001844f  call    cs:__imp_GetLastError
0x180018455  mov     edi, eax
0x180018457  xor     r9d, r9d
0x18001845a  jmp     loc_180018228
0x18001845f  mov     eax, r9d
0x180018462  mov     [rsp+1A0h+var_15C], eax
0x180018466  lea     rax, [rsp+1A0h+var_15C]
0x18001846b  mov     [rbp+0A0h+var_E0], rax
0x18001846f  mov     [rbp+0A0h+var_D8], r15
0x180018473  test    rsi, rsi
0x180018476  jz      short loc_180018480
0x180018478  mov     eax, [rsi+0DCh]
0x18001847e  jmp     short loc_180018483
0x180018480  mov     eax, r9d
0x180018483  mov     [rsp+1A0h+var_160], eax
0x180018487  lea     rax, [rsp+1A0h+var_160]
0x18001848c  mov     [rbp+0A0h+var_D0], rax
0x180018490  mov     [rbp+0A0h+var_C8], r15
0x180018494  test    rsi, rsi
0x180018497  jz      short loc_1800184A1
0x180018499  mov     eax, [rsi+0E0h]
0x18001849f  jmp     short loc_1800184A6
0x1800184a1  mov     eax, 1
0x1800184a6  mov     [rsp+1A0h+var_164], eax
0x1800184aa  lea     rax, [rsp+1A0h+var_164]
0x1800184af  mov     [rbp+0A0h+var_C0], rax
0x1800184b3  mov     [rbp+0A0h+var_B8], r15
0x1800184b7  test    rsi, rsi
0x1800184ba  jz      short loc_1800184C4
0x1800184bc  mov     eax, [rsi+0E4h]
0x1800184c2  jmp     short loc_1800184C9
0x1800184c4  mov     eax, 1
0x1800184c9  mov     [rsp+1A0h+var_168], eax
0x1800184cd  lea     r9, [rsp+1A0h+ActivityId]
0x1800184d2  lea     rax, [rsp+1A0h+var_168]
0x1800184d7  mov     [rbp+0A0h+var_A8], r15
0x1800184db  mov     [rbp+0A0h+var_B0], rax
0x1800184df  lea     r8, [rsp+1A0h+var_138]
0x1800184e4  mov     eax, cs:g_fEnableCertProp
0x1800184ea  lea     rdx, byte_18002993B
0x1800184f1  mov     [rsp+1A0h+var_16C], eax
0x1800184f5  lea     rax, [rsp+1A0h+var_16C]
0x1800184fa  mov     [rbp+0A0h+var_A0], rax
0x1800184fe  lea     rax, [rsp+1A0h+var_170]
0x180018503  mov     [rbp+0A0h+var_90], rax
0x180018507  lea     rax, [rbp+0A0h+var_120]
0x18001850b  mov     [rsp+1A0h+var_178], rax
0x180018510  mov     [rsp+1A0h+var_180], 0Ah
0x180018518  mov     [rbp+0A0h+var_98], r15
0x18001851c  mov     [rsp+1A0h+var_170], edi
0x180018520  mov     [rbp+0A0h+var_88], r15
0x180018524  call    _tlgWriteTransfer_EventWriteTransfer
0x180018529  jmp     short loc_180018531
0x18001852b  mov     r15d, 4
0x180018531  lea     rdx, [rsp+1A0h+ActivityId]; ActivityId
0x180018536  mov     ecx, 2; ControlCode
0x18001853b  call    cs:__imp_EventActivityIdControl
0x180018541  cmp     r14d, 1
0x180018545  jnz     short loc_180018551
0x180018547  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001854b  call    cs:__imp_LeaveCriticalSection
0x180018551  cmp     r12d, 1
0x180018555  jnz     short loc_180018564
0x180018557  lea     rcx, g_csSessionList; lpCriticalSection
0x18001855e  call    cs:__imp_LeaveCriticalSection
0x180018564  mov     edx, 2
0x180018569  call    WppTraceIndent
0x18001856e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018575  lea     rax, WPP_GLOBAL_Control
0x18001857c  cmp     rcx, rax
0x18001857f  jz      short loc_1800185AD
0x180018581  test    byte ptr [rcx+1Ch], 1
0x180018585  jz      short loc_1800185AD
0x180018587  cmp     [rcx+19h], r15b
0x18001858b  jb      short loc_1800185AD
0x18001858d  mov     r9, cs:WPP_pszIndent
0x180018594  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
  ... truncated ...
```
