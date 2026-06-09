# FwMoneisCreateAppContainerLoopbackRules

- ea: `0x1800bd22c`
- end: `0x1800bd84e`
- name: `FwMoneisCreateAppContainerLoopbackRules`
- size: `1570`
- prototype: `__int64 __fastcall(void *, int, struct _SID *, struct _SID *, __int64, __int64, __int64, int, struct _SID_AND_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cdc50`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x180038c1c`
- `0x18003cfe0`
- `0x1800511b4`
- `0x180054d10`
- `0x180057928`
- `0x18005db50`
- `0x1800729c0`
- `0x180073488`
- `0x1800bca54`
- `0x1800bd22c`
- `0x1800bfa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd710`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd6bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd7b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd7ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd7e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd6bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd7b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd7ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd7e3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bd49e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bd4ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bd5ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bd49e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bd4ee`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800bd5ce`
- `fwbase!FwHResultToWindowsError` at `0x1800bd610`
- `fwbase!FwHResultToWindowsError` at `0x1800bd610`
- `fwbase!FwStringBuild` at `0x1800bd602`
- `fwbase!FwStringBuild` at `0x1800bd602`
- `fwbase!FwFree` at `0x1800bd6a3`
- `fwbase!FwFree` at `0x1800bd75d`
- `fwbase!FwFree` at `0x1800bd6a3`
- `fwbase!FwFree` at `0x1800bd75d`

## pseudocode

```c
__int64 __fastcall FwMoneisCreateAppContainerLoopbackRules(
        void *a1,
        int a2,
        struct _SID *a3,
        struct _SID *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        struct _SID_AND_ATTRIBUTES *a9,
        unsigned int a10)
{
  __int64 v14; // rsi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // r8d
  DWORD IsChildAppContainer; // eax
  __int64 v22; // rcx
  unsigned __int16 *v23; // r14
  unsigned __int16 *v24; // r15
  unsigned int v25; // esi
  struct _SID_AND_ATTRIBUTES *v26; // r12
  LPWSTR v27; // rax
  PSID Sid; // rcx
  unsigned int v29; // eax
  LPWSTR v30; // rax
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+44h] [rbp-BCh] BYREF
  void *v34; // [rsp+48h] [rbp-B8h] BYREF
  void *v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v36; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v37; // [rsp+60h] [rbp-A0h]
  struct _SID_AND_ATTRIBUTES *v38; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v39; // [rsp+70h] [rbp-90h]
  LPWSTR v40; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR v42; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp-70h] BYREF
  char v44[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v45; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v46; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v47; // [rsp+C0h] [rbp-40h]
  int v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  __int16 v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+1C0h] [rbp+C0h]
  __int16 v52; // [rsp+1C4h] [rbp+C4h]
  __int64 v53; // [rsp+1D0h] [rbp+D0h]
  unsigned __int16 *v54; // [rsp+1D8h] [rbp+D8h]
  WCHAR *v55; // [rsp+218h] [rbp+118h]
  LPWSTR v56; // [rsp+220h] [rbp+120h]
  __int16 v57; // [rsp+248h] [rbp+148h]

  v39 = a5;
  v36 = a6;
  v37 = a7;
  v38 = a9;
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 174, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids);
    v14 = WPP_GLOBAL_Control;
  }
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  StringSid = 0;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  memset_0(v44, 0, 0x1F8u);
  v15 = FwMoneisValidateCapabilitySids(a9, a10);
  v16 = v15;
  if ( v15 )
  {
    if ( (_UNKNOWN *)v14 == &WPP_GLOBAL_Control || (*(_BYTE *)(v14 + 28) & 1) == 0 )
      goto LABEL_73;
    v17 = *(_QWORD *)(v14 + 16);
    v18 = 175;
    v19 = v15;
    goto LABEL_8;
  }
  DelaySignaled = 1;
  IsChildAppContainer = FwMoneisIsChildAppContainer(a4, &v32);
  v16 = IsChildAppContainer;
  if ( IsChildAppContainer )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v18 = 176;
LABEL_13:
      v19 = IsChildAppContainer;
LABEL_14:
      v17 = *(_QWORD *)(v22 + 16);
LABEL_8:
      WPP_SF_d(v17, v18, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v19);
LABEL_61:
      v22 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    IsChildAppContainer = FwMoneisValidateAppContainerOperation(a1, a2, v32, a3, a4, &v33);
    v16 = IsChildAppContainer;
    if ( !IsChildAppContainer )
    {
      if ( v33 )
      {
        if ( v32 != 1 )
        {
          IsChildAppContainer = FwMoneisOpenStores(a2, &v34, &v35);
          v16 = IsChildAppContainer;
          if ( IsChildAppContainer )
          {
            v22 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v18 = 180;
              goto LABEL_13;
            }
          }
          else if ( ConvertSidToStringSidW(a3, &StringSid) )
          {
            if ( ConvertSidToStringSidW(a4, &v42) )
            {
              v23 = v36;
              v24 = v37;
              v25 = 0;
              v26 = v38;
              while ( 1 )
              {
                if ( v25 >= a10 )
                {
                  FwMoneisTelemetryEventWriteAppContainerLoopbackRules(v39, v23, v24);
                  goto LABEL_61;
                }
                memset_0(v44, 0, 0x1F8u);
                v45 = 545;
                v57 = 256;
                v50 = 256;
                v27 = v55;
                if ( !a8 )
                  v27 = v42;
                v55 = v27;
                v52 = 1;
                Sid = v26[v25].Sid;
                v46 = v23;
                v47 = v24;
                v54 = v23;
                v56 = StringSid;
                if ( !ConvertSidToStringSidW(Sid, &v40) )
                  break;
                v29 = FwStringBuild(&v41, L"O:LSD:(A;;CC;;;", v40, L")(A;;CC;;;WD)(A;;CC;;;AN)");
                IsChildAppContainer = FwHResultToWindowsError(v29);
                v16 = IsChildAppContainer;
                if ( IsChildAppContainer )
                {
                  v22 = WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    v18 = 184;
                    goto LABEL_13;
                  }
                  goto LABEL_62;
                }
                v53 = v41;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
                {
                  WPP_SF_lSSS(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    185,
                    v20,
                    a8,
                    (__int64)StringSid,
                    (__int64)v42,
                    (__int64)v40);
                }
                v51 = 3;
                v48 = 0x7FFFFFFF;
                v49 = 1;
                IsChildAppContainer = FwMoneisAddRule(v34, v44, 0);
                v16 = IsChildAppContainer;
                if ( IsChildAppContainer )
                {
                  v22 = WPP_GLOBAL_Control;
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                  {
                    v18 = 186;
                    goto LABEL_13;
                  }
                  goto LABEL_62;
                }
                FwFree(v41);
                v41 = 0;
                LocalFree(v40);
                ++v25;
                v40 = 0;
              }
              IsChildAppContainer = GetLastError();
              v16 = IsChildAppContainer;
              v22 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v18 = 183;
                goto LABEL_13;
              }
              goto LABEL_62;
            }
            IsChildAppContainer = GetLastError();
            v16 = IsChildAppContainer;
            v22 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v18 = 182;
              goto LABEL_13;
            }
          }
          else
          {
            IsChildAppContainer = GetLastError();
            v16 = IsChildAppContainer;
            v22 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v18 = 181;
              goto LABEL_13;
            }
          }
          goto LABEL_62;
        }
        v16 = 0;
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_62;
        v18 = 179;
      }
      else
      {
        v16 = 0;
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_62;
        v18 = 178;
      }
      v19 = 0;
      goto LABEL_14;
    }
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v18 = 177;
      goto LABEL_13;
    }
  }
LABEL_62:
  if ( v41 )
  {
    FwFree(v41);
    v22 = WPP_GLOBAL_Control;
  }
  v30 = v40;
  if ( v40 )
  {
    if ( (_UNKNOWN *)v22 != &WPP_GLOBAL_Control && (*(_BYTE *)(v22 + 28) & 4) != 0 )
    {
      WPP_SF_lSSS(*(_QWORD *)(v22 + 16), 187, v20, a8, (__int64)StringSid, (__int64)v42, (__int64)v40);
      v30 = v40;
    }
    LocalFree(v30);
  }
  if ( v42 )
    LocalFree(v42);
  if ( StringSid )
    LocalFree(StringSid);
LABEL_73:
  FwMoneisCloseStores(&v34, &v35);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 188, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x1800bd22c  push    rbp
0x1800bd22e  push    rbx
0x1800bd22f  push    rsi
0x1800bd230  push    rdi
0x1800bd231  push    r12
0x1800bd233  push    r13
0x1800bd235  push    r14
0x1800bd237  push    r15
0x1800bd239  lea     rbp, [rsp-1B8h]
0x1800bd241  sub     rsp, 2B8h
0x1800bd248  mov     rax, cs:__security_cookie
0x1800bd24f  xor     rax, rsp
0x1800bd252  mov     [rbp+1F0h+var_50], rax
0x1800bd259  mov     rax, [rbp+1F0h+arg_20]
0x1800bd260  mov     r14, r9
0x1800bd263  mov     rbx, [rbp+1F0h+arg_40]
0x1800bd26a  mov     r12, r8
0x1800bd26d  mov     [rsp+2F0h+var_280], rax
0x1800bd272  mov     r15d, edx
0x1800bd275  mov     rax, [rbp+1F0h+arg_28]
0x1800bd27c  mov     r13, rcx
0x1800bd27f  mov     [rsp+2F0h+var_298], rax
0x1800bd284  mov     rax, [rbp+1F0h+arg_30]
0x1800bd28b  mov     [rsp+2F0h+var_290], rax
0x1800bd290  mov     [rsp+2F0h+var_288], rbx
0x1800bd295  mov     rsi, cs:WPP_GLOBAL_Control
0x1800bd29c  lea     rax, WPP_GLOBAL_Control
0x1800bd2a3  cmp     rsi, rax
0x1800bd2a6  jz      short loc_1800BD2CA
0x1800bd2a8  test    byte ptr [rsi+1Ch], 8
0x1800bd2ac  jz      short loc_1800BD2CA
0x1800bd2ae  mov     rcx, [rsi+10h]
0x1800bd2b2  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bd2b9  mov     edx, 0AEh
0x1800bd2be  call    WPP_SF_
0x1800bd2c3  mov     rsi, cs:WPP_GLOBAL_Control
0x1800bd2ca  xor     edi, edi
0x1800bd2cc  lea     rcx, [rbp+1F0h+var_250]; void *
0x1800bd2d0  xor     edx, edx; Val
0x1800bd2d2  mov     [rsp+2F0h+var_2B0], edi
0x1800bd2d6  mov     r8d, 1F8h; Size
0x1800bd2dc  mov     [rsp+2F0h+var_2AC], edi
0x1800bd2e0  mov     [rsp+2F0h+var_2A8], rdi
0x1800bd2e5  mov     [rsp+2F0h+var_2A0], rdi
0x1800bd2ea  mov     [rbp+1F0h+StringSid], rdi
0x1800bd2ee  mov     [rbp+1F0h+var_268], rdi
0x1800bd2f2  mov     [rsp+2F0h+var_278], rdi
0x1800bd2f7  mov     [rbp+1F0h+var_270], rdi
0x1800bd2fb  call    memset_0
0x1800bd300  mov     edx, [rbp+1F0h+arg_48]; unsigned int
0x1800bd306  mov     rcx, rbx; struct _SID_AND_ATTRIBUTES *
0x1800bd309  call    ?FwMoneisValidateCapabilitySids@@YAKPEAU_SID_AND_ATTRIBUTES@@K@Z; FwMoneisValidateCapabilitySids(_SID_AND_ATTRIBUTES *,ulong)
0x1800bd30e  mov     ebx, eax
0x1800bd310  test    eax, eax
0x1800bd312  jz      short loc_1800BD350
0x1800bd314  lea     r13, WPP_GLOBAL_Control
0x1800bd31b  cmp     rsi, r13
0x1800bd31e  jz      loc_1800BD7EF
0x1800bd324  mov     edi, 1
0x1800bd329  test    [rsi+1Ch], dil
0x1800bd32d  jz      loc_1800BD7EF
0x1800bd333  mov     rcx, [rsi+10h]
0x1800bd337  mov     edx, 0AFh
0x1800bd33c  mov     r9d, eax
0x1800bd33f  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bd346  call    WPP_SF_d
0x1800bd34b  jmp     loc_1800BD74A
0x1800bd350  mov     edi, 1
0x1800bd355  lea     rdx, [rsp+2F0h+var_2B0]; int *
0x1800bd35a  mov     rcx, r14; struct _SID *
0x1800bd35d  mov     cs:?DelaySignaled@@3KC, edi; ulong volatile DelaySignaled
0x1800bd363  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x1800bd368  mov     ebx, eax
0x1800bd36a  test    eax, eax
0x1800bd36c  jz      short loc_1800BD39D
0x1800bd36e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd375  lea     r13, WPP_GLOBAL_Control
0x1800bd37c  cmp     rcx, r13
0x1800bd37f  jz      loc_1800BD751
0x1800bd385  test    [rcx+1Ch], dil
0x1800bd389  jz      loc_1800BD751
0x1800bd38f  mov     edx, 0B0h
0x1800bd394  mov     r9d, eax
0x1800bd397  mov     rcx, [rcx+10h]
0x1800bd39b  jmp     short loc_1800BD33F
0x1800bd39d  mov     r8d, [rsp+2F0h+var_2B0]; int
0x1800bd3a2  lea     rax, [rsp+2F0h+var_2AC]
0x1800bd3a7  mov     [rsp+2F0h+var_2C8], rax; int *
0x1800bd3ac  mov     r9, r12; struct _SID *
0x1800bd3af  mov     edx, r15d; int
0x1800bd3b2  mov     [rsp+2F0h+var_2D0], r14; struct _SID *
0x1800bd3b7  mov     rcx, r13; void *
0x1800bd3ba  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x1800bd3bf  mov     ebx, eax
0x1800bd3c1  test    eax, eax
0x1800bd3c3  jz      short loc_1800BD3ED
0x1800bd3c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd3cc  lea     r13, WPP_GLOBAL_Control
0x1800bd3d3  cmp     rcx, r13
0x1800bd3d6  jz      loc_1800BD751
0x1800bd3dc  test    [rcx+1Ch], dil
0x1800bd3e0  jz      loc_1800BD751
0x1800bd3e6  mov     edx, 0B1h
0x1800bd3eb  jmp     short loc_1800BD394
0x1800bd3ed  cmp     [rsp+2F0h+var_2AC], 0
0x1800bd3f2  jnz     short loc_1800BD424
0x1800bd3f4  xor     ebx, ebx
0x1800bd3f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd3fd  lea     r13, WPP_GLOBAL_Control
0x1800bd404  cmp     rcx, r13
0x1800bd407  jz      loc_1800BD751
0x1800bd40d  test    [rcx+1Ch], dil
0x1800bd411  jz      loc_1800BD751
0x1800bd417  mov     edx, 0B2h
0x1800bd41c  xor     r9d, r9d
0x1800bd41f  jmp     loc_1800BD397
0x1800bd424  cmp     [rsp+2F0h+var_2B0], edi
0x1800bd428  jnz     short loc_1800BD454
0x1800bd42a  xor     ebx, ebx
0x1800bd42c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd433  lea     r13, WPP_GLOBAL_Control
0x1800bd43a  cmp     rcx, r13
0x1800bd43d  jz      loc_1800BD751
0x1800bd443  test    [rcx+1Ch], dil
0x1800bd447  jz      loc_1800BD751
0x1800bd44d  mov     edx, 0B3h
0x1800bd452  jmp     short loc_1800BD41C
0x1800bd454  lea     r8, [rsp+2F0h+var_2A0]; void **
0x1800bd459  mov     ecx, r15d; int
0x1800bd45c  lea     rdx, [rsp+2F0h+var_2A8]; void **
0x1800bd461  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x1800bd466  mov     ebx, eax
0x1800bd468  test    eax, eax
0x1800bd46a  jz      short loc_1800BD497
0x1800bd46c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd473  lea     r13, WPP_GLOBAL_Control
0x1800bd47a  cmp     rcx, r13
0x1800bd47d  jz      loc_1800BD751
0x1800bd483  test    [rcx+1Ch], dil
0x1800bd487  jz      loc_1800BD751
0x1800bd48d  mov     edx, 0B4h
0x1800bd492  jmp     loc_1800BD394
0x1800bd497  lea     rdx, [rbp+1F0h+StringSid]; StringSid
0x1800bd49b  mov     rcx, r12; Sid
0x1800bd49e  call    cs:__imp_ConvertSidToStringSidW
0x1800bd4a5  nop     dword ptr [rax+rax+00h]
0x1800bd4aa  test    eax, eax
0x1800bd4ac  jnz     short loc_1800BD4E7
0x1800bd4ae  call    cs:__imp_GetLastError
0x1800bd4b5  nop     dword ptr [rax+rax+00h]
0x1800bd4ba  mov     ebx, eax
0x1800bd4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd4c3  lea     r13, WPP_GLOBAL_Control
0x1800bd4ca  cmp     rcx, r13
0x1800bd4cd  jz      loc_1800BD751
0x1800bd4d3  test    [rcx+1Ch], dil
0x1800bd4d7  jz      loc_1800BD751
0x1800bd4dd  mov     edx, 0B5h
0x1800bd4e2  jmp     loc_1800BD394
0x1800bd4e7  lea     rdx, [rbp+1F0h+var_268]; StringSid
0x1800bd4eb  mov     rcx, r14; Sid
0x1800bd4ee  call    cs:__imp_ConvertSidToStringSidW
0x1800bd4f5  nop     dword ptr [rax+rax+00h]
0x1800bd4fa  test    eax, eax
0x1800bd4fc  jnz     short loc_1800BD537
0x1800bd4fe  call    cs:__imp_GetLastError
0x1800bd505  nop     dword ptr [rax+rax+00h]
0x1800bd50a  mov     ebx, eax
0x1800bd50c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd513  lea     r13, WPP_GLOBAL_Control
0x1800bd51a  cmp     rcx, r13
0x1800bd51d  jz      loc_1800BD751
0x1800bd523  test    [rcx+1Ch], dil
0x1800bd527  jz      loc_1800BD751
0x1800bd52d  mov     edx, 0B6h
0x1800bd532  jmp     loc_1800BD394
0x1800bd537  mov     r14, [rsp+2F0h+var_298]
0x1800bd53c  lea     r13, WPP_GLOBAL_Control
0x1800bd543  mov     r15, [rsp+2F0h+var_290]
0x1800bd548  xor     esi, esi
0x1800bd54a  mov     r12, [rsp+2F0h+var_288]
0x1800bd54f  cmp     esi, [rbp+1F0h+arg_48]
0x1800bd555  jnb     loc_1800BD73A
0x1800bd55b  xor     edx, edx; Val
0x1800bd55d  lea     rcx, [rbp+1F0h+var_250]; void *
0x1800bd561  mov     r8d, 1F8h; Size
0x1800bd567  call    memset_0
0x1800bd56c  cmp     [rbp+1F0h+arg_38], 0
0x1800bd573  lea     rdx, [rsp+2F0h+var_278]; StringSid
0x1800bd578  mov     eax, 221h
0x1800bd57d  mov     ecx, esi
0x1800bd57f  mov     [rbp+1F0h+var_248], ax
0x1800bd583  mov     eax, 100h
0x1800bd588  mov     [rbp+1F0h+var_A8], ax
0x1800bd58f  mov     [rbp+1F0h+var_220], ax
0x1800bd593  mov     rax, [rbp+1F0h+var_D8]
0x1800bd59a  cmovz   rax, [rbp+1F0h+var_268]
0x1800bd59f  add     rcx, rcx
0x1800bd5a2  mov     [rbp+1F0h+var_D8], rax
0x1800bd5a9  mov     rax, [rbp+1F0h+StringSid]
0x1800bd5ad  mov     [rbp+1F0h+var_12C], di
0x1800bd5b4  mov     rcx, [r12+rcx*8]; Sid
0x1800bd5b8  mov     [rbp+1F0h+var_238], r14
0x1800bd5bc  mov     [rbp+1F0h+var_230], r15
0x1800bd5c0  mov     [rbp+1F0h+var_118], r14
0x1800bd5c7  mov     [rbp+1F0h+var_D0], rax
0x1800bd5ce  call    cs:__imp_ConvertSidToStringSidW
0x1800bd5d5  nop     dword ptr [rax+rax+00h]
0x1800bd5da  test    eax, eax
0x1800bd5dc  jz      loc_1800BD710
0x1800bd5e2  mov     r8, [rsp+2F0h+var_278]
0x1800bd5e7  lea     r9, aACcWdACcAn; ")(A;;CC;;;WD)(A;;CC;;;AN)"
0x1800bd5ee  lea     rdx, aOLsdACc; "O:LSD:(A;;CC;;;"
0x1800bd5f5  mov     [rsp+2F0h+var_2D0], 0
0x1800bd5fe  lea     rcx, [rbp+1F0h+var_270]
0x1800bd602  call    cs:__imp_FwStringBuild
0x1800bd609  nop     dword ptr [rax+rax+00h]
0x1800bd60e  mov     ecx, eax
0x1800bd610  call    cs:__imp_FwHResultToWindowsError
0x1800bd617  nop     dword ptr [rax+rax+00h]
0x1800bd61c  mov     ebx, eax
0x1800bd61e  test    eax, eax
0x1800bd620  jnz     loc_1800BD6F4
0x1800bd626  mov     rax, [rbp+1F0h+var_270]
0x1800bd62a  mov     [rbp+1F0h+var_120], rax
0x1800bd631  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd638  cmp     rcx, r13
0x1800bd63b  jz      short loc_1800BD674
0x1800bd63d  test    byte ptr [rcx+1Ch], 4
0x1800bd641  jz      short loc_1800BD674
0x1800bd643  mov     rax, [rsp+2F0h+var_278]
0x1800bd648  mov     edx, 0B9h
0x1800bd64d  mov     r9d, [rbp+1F0h+arg_38]
0x1800bd654  mov     rcx, [rcx+10h]
0x1800bd658  mov     [rsp+2F0h+var_2C0], rax
0x1800bd65d  mov     rax, [rbp+1F0h+var_268]
0x1800bd661  mov     [rsp+2F0h+var_2C8], rax
0x1800bd666  mov     rax, [rbp+1F0h+StringSid]
0x1800bd66a  mov     [rsp+2F0h+var_2D0], rax
0x1800bd66f  call    WPP_SF_lSSS
0x1800bd674  mov     rcx, [rsp+2F0h+var_2A8]
0x1800bd679  lea     rdx, [rbp+1F0h+var_250]
0x1800bd67d  xor     r8d, r8d
0x1800bd680  mov     [rbp+1F0h+var_130], 3
0x1800bd68a  mov     [rbp+1F0h+var_228], 7FFFFFFFh
0x1800bd691  mov     [rbp+1F0h+var_224], edi
0x1800bd694  call    ?FwMoneisAddRule@@YAKPEAXPEAU_tag_FW_RULE@@W4customRuleId@@@Z; FwMoneisAddRule(void *,_tag_FW_RULE *,customRuleId)
0x1800bd699  mov     ebx, eax
0x1800bd69b  test    eax, eax
0x1800bd69d  jnz     short loc_1800BD6D8
0x1800bd69f  mov     rcx, [rbp+1F0h+var_270]
0x1800bd6a3  call    cs:__imp_FwFree
0x1800bd6aa  nop     dword ptr [rax+rax+00h]
0x1800bd6af  mov     rcx, [rsp+2F0h+var_278]; hMem
0x1800bd6b4  mov     [rbp+1F0h+var_270], 0
0x1800bd6bc  call    cs:__imp_LocalFree
0x1800bd6c3  nop     dword ptr [rax+rax+00h]
0x1800bd6c8  add     esi, edi
0x1800bd6ca  mov     [rsp+2F0h+var_278], 0
0x1800bd6d3  jmp     loc_1800BD54F
0x1800bd6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd6df  cmp     rcx, r13
0x1800bd6e2  jz      short loc_1800BD751
0x1800bd6e4  test    [rcx+1Ch], dil
0x1800bd6e8  jz      short loc_1800BD751
0x1800bd6ea  mov     edx, 0BAh
0x1800bd6ef  jmp     loc_1800BD394
0x1800bd6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd6fb  cmp     rcx, r13
0x1800bd6fe  jz      short loc_1800BD751
0x1800bd700  test    [rcx+1Ch], dil
0x1800bd704  jz      short loc_1800BD751
0x1800bd706  mov     edx, 0B8h
0x1800bd70b  jmp     loc_1800BD394
0x1800bd710  call    cs:__imp_GetLastError
0x1800bd717  nop     dword ptr [rax+rax+00h]
0x1800bd71c  mov     ebx, eax
0x1800bd71e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd725  cmp     rcx, r13
0x1800bd728  jz      short loc_1800BD751
0x1800bd72a  test    [rcx+1Ch], dil
0x1800bd72e  jz      short loc_1800BD751
0x1800bd730  mov     edx, 0B7h
0x1800bd735  jmp     loc_1800BD394
0x1800bd73a  mov     rcx, [rsp+2F0h+var_280]; unsigned __int16 *
0x1800bd73f  mov     r8, r15; unsigned __int16 *
0x1800bd742  mov     rdx, r14; unsigned __int16 *
0x1800bd745  call    ?FwMoneisTelemetryEventWriteAppContainerLoopbackRules@@YAXPEBG00@Z; FwMoneisTelemetryEventWriteAppContainerLoopbackRules(ushort const *,ushort const *,ushort const *)
0x1800bd74a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd751  mov     rax, [rbp+1F0h+var_270]
0x1800bd755  test    rax, rax
0x1800bd758  jz      short loc_1800BD770
0x1800bd75a  mov     rcx, rax
0x1800bd75d  call    cs:__imp_FwFree
0x1800bd764  nop     dword ptr [rax+rax+00h]
0x1800bd769  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd770  mov     rax, [rsp+2F0h+var_278]
0x1800bd775  test    rax, rax
0x1800bd778  jz      short loc_1800BD7C5
0x1800bd77a  cmp     rcx, r13
  ... truncated ...
```
