# FwMoneisCreateAppContainerLoopbackRules

- ea: `0x1800b653c`
- end: `0x1800b6b09`
- name: `FwMoneisCreateAppContainerLoopbackRules`
- size: `1485`
- prototype: `__int64 __fastcall(void *, int, struct _SID *, struct _SID *, __int64, __int64, __int64, int, struct _SID_AND_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c6780`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18003b4a0`
- `0x18003ca2c`
- `0x180050a6c`
- `0x1800535a8`
- `0x180059270`
- `0x1800620b8`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800b5db0`
- `0x1800b653c`
- `0x1800b8c9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b67b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b67fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b69ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b67b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b67fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b69ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b699c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6a87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6a96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b699c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6a87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6a96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b6aa5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b67ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b67f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b68c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b67ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b67f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b68c6`
- `fwbase!FwHResultToWindowsError` at `0x1800b68fc`
- `fwbase!FwHResultToWindowsError` at `0x1800b68fc`
- `fwbase!FwStringBuild` at `0x1800b68f4`
- `fwbase!FwStringBuild` at `0x1800b68f4`
- `fwbase!FwFree` at `0x1800b6989`
- `fwbase!FwFree` at `0x1800b6a31`
- `fwbase!FwFree` at `0x1800b6989`
- `fwbase!FwFree` at `0x1800b6a31`

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
  unsigned int IsChildAppContainer; // eax
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 169, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids);
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
    v18 = 170;
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
      v18 = 171;
LABEL_13:
      v19 = IsChildAppContainer;
LABEL_14:
      v17 = *(_QWORD *)(v22 + 16);
LABEL_8:
      WPP_SF_d(v17, v18, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v19);
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
              v18 = 175;
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
                    v18 = 179;
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
                    180,
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
                    v18 = 181;
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
                v18 = 178;
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
              v18 = 177;
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
              v18 = 176;
              goto LABEL_13;
            }
          }
          goto LABEL_62;
        }
        v16 = 0;
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_62;
        v18 = 174;
      }
      else
      {
        v16 = 0;
        v22 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_62;
        v18 = 173;
      }
      v19 = 0;
      goto LABEL_14;
    }
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v18 = 172;
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
      WPP_SF_lSSS(*(_QWORD *)(v22 + 16), 182, v20, a8, (__int64)StringSid, (__int64)v42, (__int64)v40);
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
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 183, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x1800b653c  push    rbp
0x1800b653e  push    rbx
0x1800b653f  push    rsi
0x1800b6540  push    rdi
0x1800b6541  push    r12
0x1800b6543  push    r13
0x1800b6545  push    r14
0x1800b6547  push    r15
0x1800b6549  lea     rbp, [rsp-1B8h]
0x1800b6551  sub     rsp, 2B8h
0x1800b6558  mov     rax, cs:__security_cookie
0x1800b655f  xor     rax, rsp
0x1800b6562  mov     [rbp+1F0h+var_50], rax
0x1800b6569  mov     rax, [rbp+1F0h+arg_20]
0x1800b6570  mov     r14, r9
0x1800b6573  mov     rbx, [rbp+1F0h+arg_40]
0x1800b657a  mov     r12, r8
0x1800b657d  mov     [rsp+2F0h+var_280], rax
0x1800b6582  mov     r15d, edx
0x1800b6585  mov     rax, [rbp+1F0h+arg_28]
0x1800b658c  mov     r13, rcx
0x1800b658f  mov     [rsp+2F0h+var_298], rax
0x1800b6594  mov     rax, [rbp+1F0h+arg_30]
0x1800b659b  mov     [rsp+2F0h+var_290], rax
0x1800b65a0  mov     [rsp+2F0h+var_288], rbx
0x1800b65a5  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b65ac  lea     rax, WPP_GLOBAL_Control
0x1800b65b3  cmp     rsi, rax
0x1800b65b6  jz      short loc_1800B65DA
0x1800b65b8  test    byte ptr [rsi+1Ch], 8
0x1800b65bc  jz      short loc_1800B65DA
0x1800b65be  mov     rcx, [rsi+10h]
0x1800b65c2  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b65c9  mov     edx, 0A9h
0x1800b65ce  call    WPP_SF_
0x1800b65d3  mov     rsi, cs:WPP_GLOBAL_Control
0x1800b65da  xor     edi, edi
0x1800b65dc  lea     rcx, [rbp+1F0h+var_250]; void *
0x1800b65e0  xor     edx, edx; Val
0x1800b65e2  mov     [rsp+2F0h+var_2B0], edi
0x1800b65e6  mov     r8d, 1F8h; Size
0x1800b65ec  mov     [rsp+2F0h+var_2AC], edi
0x1800b65f0  mov     [rsp+2F0h+var_2A8], rdi
0x1800b65f5  mov     [rsp+2F0h+var_2A0], rdi
0x1800b65fa  mov     [rbp+1F0h+StringSid], rdi
0x1800b65fe  mov     [rbp+1F0h+var_268], rdi
0x1800b6602  mov     [rsp+2F0h+var_278], rdi
0x1800b6607  mov     [rbp+1F0h+var_270], rdi
0x1800b660b  call    memset_0
0x1800b6610  mov     edx, [rbp+1F0h+arg_48]; unsigned int
0x1800b6616  mov     rcx, rbx; struct _SID_AND_ATTRIBUTES *
0x1800b6619  call    ?FwMoneisValidateCapabilitySids@@YAKPEAU_SID_AND_ATTRIBUTES@@K@Z; FwMoneisValidateCapabilitySids(_SID_AND_ATTRIBUTES *,ulong)
0x1800b661e  mov     ebx, eax
0x1800b6620  test    eax, eax
0x1800b6622  jz      short loc_1800B6660
0x1800b6624  lea     r13, WPP_GLOBAL_Control
0x1800b662b  cmp     rsi, r13
0x1800b662e  jz      loc_1800B6AAB
0x1800b6634  mov     edi, 1
0x1800b6639  test    [rsi+1Ch], dil
0x1800b663d  jz      loc_1800B6AAB
0x1800b6643  mov     rcx, [rsi+10h]
0x1800b6647  mov     edx, 0AAh
0x1800b664c  mov     r9d, eax
0x1800b664f  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b6656  call    WPP_SF_d
0x1800b665b  jmp     loc_1800B6A1E
0x1800b6660  mov     edi, 1
0x1800b6665  lea     rdx, [rsp+2F0h+var_2B0]; int *
0x1800b666a  mov     rcx, r14; struct _SID *
0x1800b666d  mov     cs:?DelaySignaled@@3KC, edi; ulong volatile DelaySignaled
0x1800b6673  call    ?FwMoneisIsChildAppContainer@@YAKPEAU_SID@@PEAH@Z; FwMoneisIsChildAppContainer(_SID *,int *)
0x1800b6678  mov     ebx, eax
0x1800b667a  test    eax, eax
0x1800b667c  jz      short loc_1800B66AD
0x1800b667e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6685  lea     r13, WPP_GLOBAL_Control
0x1800b668c  cmp     rcx, r13
0x1800b668f  jz      loc_1800B6A25
0x1800b6695  test    [rcx+1Ch], dil
0x1800b6699  jz      loc_1800B6A25
0x1800b669f  mov     edx, 0ABh
0x1800b66a4  mov     r9d, eax
0x1800b66a7  mov     rcx, [rcx+10h]
0x1800b66ab  jmp     short loc_1800B664F
0x1800b66ad  mov     r8d, [rsp+2F0h+var_2B0]; int
0x1800b66b2  lea     rax, [rsp+2F0h+var_2AC]
0x1800b66b7  mov     [rsp+2F0h+var_2C8], rax; int *
0x1800b66bc  mov     r9, r12; struct _SID *
0x1800b66bf  mov     edx, r15d; int
0x1800b66c2  mov     [rsp+2F0h+var_2D0], r14; struct _SID *
0x1800b66c7  mov     rcx, r13; void *
0x1800b66ca  call    ?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z; FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)
0x1800b66cf  mov     ebx, eax
0x1800b66d1  test    eax, eax
0x1800b66d3  jz      short loc_1800B66FD
0x1800b66d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b66dc  lea     r13, WPP_GLOBAL_Control
0x1800b66e3  cmp     rcx, r13
0x1800b66e6  jz      loc_1800B6A25
0x1800b66ec  test    [rcx+1Ch], dil
0x1800b66f0  jz      loc_1800B6A25
0x1800b66f6  mov     edx, 0ACh
0x1800b66fb  jmp     short loc_1800B66A4
0x1800b66fd  cmp     [rsp+2F0h+var_2AC], 0
0x1800b6702  jnz     short loc_1800B6734
0x1800b6704  xor     ebx, ebx
0x1800b6706  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b670d  lea     r13, WPP_GLOBAL_Control
0x1800b6714  cmp     rcx, r13
0x1800b6717  jz      loc_1800B6A25
0x1800b671d  test    [rcx+1Ch], dil
0x1800b6721  jz      loc_1800B6A25
0x1800b6727  mov     edx, 0ADh
0x1800b672c  xor     r9d, r9d
0x1800b672f  jmp     loc_1800B66A7
0x1800b6734  cmp     [rsp+2F0h+var_2B0], edi
0x1800b6738  jnz     short loc_1800B6764
0x1800b673a  xor     ebx, ebx
0x1800b673c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6743  lea     r13, WPP_GLOBAL_Control
0x1800b674a  cmp     rcx, r13
0x1800b674d  jz      loc_1800B6A25
0x1800b6753  test    [rcx+1Ch], dil
0x1800b6757  jz      loc_1800B6A25
0x1800b675d  mov     edx, 0AEh
0x1800b6762  jmp     short loc_1800B672C
0x1800b6764  lea     r8, [rsp+2F0h+var_2A0]; void **
0x1800b6769  mov     ecx, r15d; int
0x1800b676c  lea     rdx, [rsp+2F0h+var_2A8]; void **
0x1800b6771  call    ?FwMoneisOpenStores@@YAKHPEAPEAX0@Z; FwMoneisOpenStores(int,void * *,void * *)
0x1800b6776  mov     ebx, eax
0x1800b6778  test    eax, eax
0x1800b677a  jz      short loc_1800B67A7
0x1800b677c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6783  lea     r13, WPP_GLOBAL_Control
0x1800b678a  cmp     rcx, r13
0x1800b678d  jz      loc_1800B6A25
0x1800b6793  test    [rcx+1Ch], dil
0x1800b6797  jz      loc_1800B6A25
0x1800b679d  mov     edx, 0AFh
0x1800b67a2  jmp     loc_1800B66A4
0x1800b67a7  lea     rdx, [rbp+1F0h+StringSid]; StringSid
0x1800b67ab  mov     rcx, r12; Sid
0x1800b67ae  call    cs:__imp_ConvertSidToStringSidW
0x1800b67b4  test    eax, eax
0x1800b67b6  jnz     short loc_1800B67EB
0x1800b67b8  call    cs:__imp_GetLastError
0x1800b67be  mov     ebx, eax
0x1800b67c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b67c7  lea     r13, WPP_GLOBAL_Control
0x1800b67ce  cmp     rcx, r13
0x1800b67d1  jz      loc_1800B6A25
0x1800b67d7  test    [rcx+1Ch], dil
0x1800b67db  jz      loc_1800B6A25
0x1800b67e1  mov     edx, 0B0h
0x1800b67e6  jmp     loc_1800B66A4
0x1800b67eb  lea     rdx, [rbp+1F0h+var_268]; StringSid
0x1800b67ef  mov     rcx, r14; Sid
0x1800b67f2  call    cs:__imp_ConvertSidToStringSidW
0x1800b67f8  test    eax, eax
0x1800b67fa  jnz     short loc_1800B682F
0x1800b67fc  call    cs:__imp_GetLastError
0x1800b6802  mov     ebx, eax
0x1800b6804  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b680b  lea     r13, WPP_GLOBAL_Control
0x1800b6812  cmp     rcx, r13
0x1800b6815  jz      loc_1800B6A25
0x1800b681b  test    [rcx+1Ch], dil
0x1800b681f  jz      loc_1800B6A25
0x1800b6825  mov     edx, 0B1h
0x1800b682a  jmp     loc_1800B66A4
0x1800b682f  mov     r14, [rsp+2F0h+var_298]
0x1800b6834  lea     r13, WPP_GLOBAL_Control
0x1800b683b  mov     r15, [rsp+2F0h+var_290]
0x1800b6840  xor     esi, esi
0x1800b6842  mov     r12, [rsp+2F0h+var_288]
0x1800b6847  cmp     esi, [rbp+1F0h+arg_48]
0x1800b684d  jnb     loc_1800B6A0E
0x1800b6853  xor     edx, edx; Val
0x1800b6855  lea     rcx, [rbp+1F0h+var_250]; void *
0x1800b6859  mov     r8d, 1F8h; Size
0x1800b685f  call    memset_0
0x1800b6864  cmp     [rbp+1F0h+arg_38], 0
0x1800b686b  lea     rdx, [rsp+2F0h+var_278]; StringSid
0x1800b6870  mov     eax, 221h
0x1800b6875  mov     ecx, esi
0x1800b6877  mov     [rbp+1F0h+var_248], ax
0x1800b687b  mov     eax, 100h
0x1800b6880  mov     [rbp+1F0h+var_A8], ax
0x1800b6887  mov     [rbp+1F0h+var_220], ax
0x1800b688b  mov     rax, [rbp+1F0h+var_D8]
0x1800b6892  cmovz   rax, [rbp+1F0h+var_268]
0x1800b6897  add     rcx, rcx
0x1800b689a  mov     [rbp+1F0h+var_D8], rax
0x1800b68a1  mov     rax, [rbp+1F0h+StringSid]
0x1800b68a5  mov     [rbp+1F0h+var_12C], di
0x1800b68ac  mov     rcx, [r12+rcx*8]; Sid
0x1800b68b0  mov     [rbp+1F0h+var_238], r14
0x1800b68b4  mov     [rbp+1F0h+var_230], r15
0x1800b68b8  mov     [rbp+1F0h+var_118], r14
0x1800b68bf  mov     [rbp+1F0h+var_D0], rax
0x1800b68c6  call    cs:__imp_ConvertSidToStringSidW
0x1800b68cc  test    eax, eax
0x1800b68ce  jz      loc_1800B69EA
0x1800b68d4  mov     r8, [rsp+2F0h+var_278]
0x1800b68d9  lea     r9, aACcWdACcAn; ")(A;;CC;;;WD)(A;;CC;;;AN)"
0x1800b68e0  lea     rdx, aOLsdACc; "O:LSD:(A;;CC;;;"
0x1800b68e7  mov     [rsp+2F0h+var_2D0], 0
0x1800b68f0  lea     rcx, [rbp+1F0h+var_270]
0x1800b68f4  call    cs:__imp_FwStringBuild
0x1800b68fa  mov     ecx, eax
0x1800b68fc  call    cs:__imp_FwHResultToWindowsError
0x1800b6902  mov     ebx, eax
0x1800b6904  test    eax, eax
0x1800b6906  jnz     loc_1800B69CE
0x1800b690c  mov     rax, [rbp+1F0h+var_270]
0x1800b6910  mov     [rbp+1F0h+var_120], rax
0x1800b6917  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b691e  cmp     rcx, r13
0x1800b6921  jz      short loc_1800B695A
0x1800b6923  test    byte ptr [rcx+1Ch], 4
0x1800b6927  jz      short loc_1800B695A
0x1800b6929  mov     rax, [rsp+2F0h+var_278]
0x1800b692e  mov     edx, 0B4h
0x1800b6933  mov     r9d, [rbp+1F0h+arg_38]
0x1800b693a  mov     rcx, [rcx+10h]
0x1800b693e  mov     [rsp+2F0h+var_2C0], rax
0x1800b6943  mov     rax, [rbp+1F0h+var_268]
0x1800b6947  mov     [rsp+2F0h+var_2C8], rax
0x1800b694c  mov     rax, [rbp+1F0h+StringSid]
0x1800b6950  mov     [rsp+2F0h+var_2D0], rax
0x1800b6955  call    WPP_SF_lSSS
0x1800b695a  mov     rcx, [rsp+2F0h+var_2A8]
0x1800b695f  lea     rdx, [rbp+1F0h+var_250]
0x1800b6963  xor     r8d, r8d
0x1800b6966  mov     [rbp+1F0h+var_130], 3
0x1800b6970  mov     [rbp+1F0h+var_228], 7FFFFFFFh
0x1800b6977  mov     [rbp+1F0h+var_224], edi
0x1800b697a  call    ?FwMoneisAddRule@@YAKPEAXPEAU_tag_FW_RULE@@W4customRuleId@@@Z; FwMoneisAddRule(void *,_tag_FW_RULE *,customRuleId)
0x1800b697f  mov     ebx, eax
0x1800b6981  test    eax, eax
0x1800b6983  jnz     short loc_1800B69B2
0x1800b6985  mov     rcx, [rbp+1F0h+var_270]
0x1800b6989  call    cs:__imp_FwFree
0x1800b698f  mov     rcx, [rsp+2F0h+var_278]; hMem
0x1800b6994  mov     [rbp+1F0h+var_270], 0
0x1800b699c  call    cs:__imp_LocalFree
0x1800b69a2  add     esi, edi
0x1800b69a4  mov     [rsp+2F0h+var_278], 0
0x1800b69ad  jmp     loc_1800B6847
0x1800b69b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b69b9  cmp     rcx, r13
0x1800b69bc  jz      short loc_1800B6A25
0x1800b69be  test    [rcx+1Ch], dil
0x1800b69c2  jz      short loc_1800B6A25
0x1800b69c4  mov     edx, 0B5h
0x1800b69c9  jmp     loc_1800B66A4
0x1800b69ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b69d5  cmp     rcx, r13
0x1800b69d8  jz      short loc_1800B6A25
0x1800b69da  test    [rcx+1Ch], dil
0x1800b69de  jz      short loc_1800B6A25
0x1800b69e0  mov     edx, 0B3h
0x1800b69e5  jmp     loc_1800B66A4
0x1800b69ea  call    cs:__imp_GetLastError
0x1800b69f0  mov     ebx, eax
0x1800b69f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b69f9  cmp     rcx, r13
0x1800b69fc  jz      short loc_1800B6A25
0x1800b69fe  test    [rcx+1Ch], dil
0x1800b6a02  jz      short loc_1800B6A25
0x1800b6a04  mov     edx, 0B2h
0x1800b6a09  jmp     loc_1800B66A4
0x1800b6a0e  mov     rcx, [rsp+2F0h+var_280]; unsigned __int16 *
0x1800b6a13  mov     r8, r15; unsigned __int16 *
0x1800b6a16  mov     rdx, r14; unsigned __int16 *
0x1800b6a19  call    ?FwMoneisTelemetryEventWriteAppContainerLoopbackRules@@YAXPEBG00@Z; FwMoneisTelemetryEventWriteAppContainerLoopbackRules(ushort const *,ushort const *,ushort const *)
0x1800b6a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6a25  mov     rax, [rbp+1F0h+var_270]
0x1800b6a29  test    rax, rax
0x1800b6a2c  jz      short loc_1800B6A3E
0x1800b6a2e  mov     rcx, rax
0x1800b6a31  call    cs:__imp_FwFree
0x1800b6a37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6a3e  mov     rax, [rsp+2F0h+var_278]
0x1800b6a43  test    rax, rax
0x1800b6a46  jz      short loc_1800B6A8D
0x1800b6a48  cmp     rcx, r13
0x1800b6a4b  jz      short loc_1800B6A84
0x1800b6a4d  test    byte ptr [rcx+1Ch], 4
0x1800b6a51  jz      short loc_1800B6A84
0x1800b6a53  mov     r9d, [rbp+1F0h+arg_38]
0x1800b6a5a  mov     edx, 0B6h
0x1800b6a5f  mov     rcx, [rcx+10h]
0x1800b6a63  mov     [rsp+2F0h+var_2C0], rax
0x1800b6a68  mov     rax, [rbp+1F0h+var_268]
0x1800b6a6c  mov     [rsp+2F0h+var_2C8], rax
0x1800b6a71  mov     rax, [rbp+1F0h+StringSid]
0x1800b6a75  mov     [rsp+2F0h+var_2D0], rax
  ... truncated ...
```
