# TLSDBIssueTemporaryLicense

- ea: `0x180033af4`
- end: `0x180033f3b`
- name: `TLSDBIssueTemporaryLicense`
- size: `1095`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a028`
- `0x18002c4e8`

## callees

- `0x180005665`
- `0x18000cff0`
- `0x180022910`
- `0x180030a20`
- `0x180033968`
- `0x180033af4`
- `0x180035408`
- `0x1800662a0`
- `0x18007e438`
- `0x1800a0fb0`
- `0x1800a1070`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180033e50`
- `msvcrt!wcscpy_s` at `0x180033e6c`
- `msvcrt!wcscpy_s` at `0x180033e8f`
- `msvcrt!wcscpy_s` at `0x180033e50`
- `msvcrt!wcscpy_s` at `0x180033e6c`
- `msvcrt!wcscpy_s` at `0x180033e8f`
- `msvcrt!time` at `0x180033bff`
- `msvcrt!time` at `0x180033bff`
- `KERNEL32!CompareFileTime` at `0x180033d78`
- `KERNEL32!CompareFileTime` at `0x180033d78`
- `KERNEL32!SetLastError` at `0x180033bbd`
- `KERNEL32!SetLastError` at `0x180033bbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TLSDBIssueTemporaryLicense(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v7; // r14d
  CRdlsDBManager *v8; // rcx
  unsigned int v9; // r12d
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rdi
  const FILETIME *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // r8
  int *v16; // rax
  __int64 v17; // rcx
  void *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h]
  __int128 v21; // [rsp+40h] [rbp-C0h]
  struct _EVENT_DESCRIPTOR v22; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h]
  __int128 v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[4]; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+94h] [rbp-6Ch]
  int v28; // [rsp+98h] [rbp-68h]
  int v29; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 v30[32]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v31[256]; // [rsp+E8h] [rbp-18h] BYREF
  int v32; // [rsp+2E8h] [rbp+1E8h]
  int v33; // [rsp+2ECh] [rbp+1ECh]
  char v34; // [rsp+2F0h] [rbp+1F0h]
  int v35; // [rsp+2F4h] [rbp+1F4h]
  int v36; // [rsp+2F8h] [rbp+1F8h]
  int v37; // [rsp+2FCh] [rbp+1FCh]
  int v38; // [rsp+300h] [rbp+200h]
  int v39; // [rsp+304h] [rbp+204h]
  int v40; // [rsp+308h] [rbp+208h]
  _BYTE v41[4]; // [rsp+320h] [rbp+220h] BYREF
  int v42; // [rsp+324h] [rbp+224h]
  __int64 v43; // [rsp+328h] [rbp+228h]
  int v44; // [rsp+334h] [rbp+234h]
  char v45; // [rsp+344h] [rbp+244h]
  __int64 v46; // [rsp+348h] [rbp+248h]
  int v47; // [rsp+350h] [rbp+250h]
  char v48; // [rsp+B54h] [rbp+A54h]
  wchar_t Source[256]; // [rsp+B56h] [rbp+A56h] BYREF
  wchar_t v50[525]; // [rsp+D56h] [rbp+C56h] BYREF

  *(_QWORD *)&v22.Id = a1;
  memset_0(v26, 0, 0x288u);
  v7 = 0;
  v43 = 0;
  v46 = 0;
  v47 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v19 = 0;
  v9 = TLSDBGetTemporaryLicense(a1, a2, v41);
  if ( v9 )
    goto LABEL_21;
  if ( (v48 & 0xF) != 4 && (v45 & 0xF) != 5 )
  {
    v9 = 4096;
    SetLastError(0x1000u);
    goto LABEL_21;
  }
  LODWORD(v20) = CRdlsDBManager::GetNextLicenseId(v8);
  HIDWORD(v20) = v42;
  v27 = v20;
  v28 = v42;
  v29 = v44;
  v35 = 1;
  v32 = time(0);
  v33 = v32 + 86400 * *(_DWORD *)&g_GracePeriod;
  v34 = 1;
  StringCchCopyW(v30, 0x10u, (const unsigned __int16 *)(a2 + 84));
  StringCchCopyW(v31, 0x100u, (const unsigned __int16 *)(a2 + 118));
  v36 = *(_DWORD *)(a2 + 48);
  v37 = *(_DWORD *)(a2 + 52);
  v38 = *(_DWORD *)(a2 + 56);
  v39 = *(_DWORD *)(a2 + 60);
  v40 = *(_DWORD *)(a2 + 64);
  *(_QWORD *)&v21 = 10000000 * (v32 + 0x2B6109100LL);
  *((_QWORD *)&v21 + 1) = 10000000 * (v33 + 0x2B6109100LL);
  *(_QWORD *)&v23 = *(_QWORD *)(a2 + 704);
  DWORD2(v23) = 4;
  HIDWORD(v23) = v42;
  LODWORD(v24) = v44;
  v10 = v20;
  *((_QWORD *)&v24 + 1) = v20;
  v11 = v21;
  v25 = v21;
  v12 = *((_QWORD *)&v21 + 1);
  v9 = CTLSPolicy::PMLicenseRequest(*(CTLSPolicy **)a2, *(void **)(a2 + 8), 6u, &v23, &v19, 1);
  if ( v9 )
    goto LABEL_21;
  v13 = (const FILETIME *)v19;
  if ( v19 )
  {
    if ( *((_QWORD *)v19 + 1) )
    {
      if ( *(_DWORD *)v19 )
        goto LABEL_12;
    }
    else if ( !*(_DWORD *)v19 )
    {
LABEL_12:
      if ( CompareFileTime(v13 + 2, v13 + 3) > 0 )
      {
        v14 = *(_QWORD *)a2 + 600LL;
        v15 = *(_QWORD *)a2 + 88LL;
        v9 = -939524081;
        v22 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
        TLSLogEvent(&v22, 0xC800000F, v15, v14);
        goto LABEL_21;
      }
      v11 = *((_QWORD *)v19 + 2);
      v12 = *((_QWORD *)v19 + 3);
      goto LABEL_15;
    }
    *(_DWORD *)v19 = 0;
    *((_QWORD *)v19 + 1) = 0;
    v13 = (const FILETIME *)v19;
    goto LABEL_12;
  }
LABEL_15:
  v9 = TLSDBLicenseAdd(*(_QWORD *)&v22.Id, v26);
  *(_QWORD *)(a5 + 2664) = 0;
  *(_DWORD *)a5 = 1;
  *(_QWORD *)(a5 + 8) = v10;
  *(_DWORD *)(a5 + 16) = v42;
  *(_DWORD *)(a5 + 20) = v20;
  *(_DWORD *)(a5 + 24) = v44;
  *(_OWORD *)(a5 + 32) = *(_OWORD *)(a2 + 48);
  *(_DWORD *)(a5 + 48) = *(_DWORD *)(a2 + 64);
  *(_DWORD *)(a5 + 68) = 1;
  *(_QWORD *)(a5 + 52) = v11;
  *(_QWORD *)(a5 + 60) = v12;
  *(_DWORD *)(a5 + 72) = v50[257] | (v50[256] << 16);
  wcscpy_s((wchar_t *)(a5 + 76), 0x100u, Source);
  wcscpy_s((wchar_t *)(a5 + 588), 0x100u, v50);
  wcscpy_s((wchar_t *)(a5 + 1100), 0x100u, **(const wchar_t ***)(*(_QWORD *)(a2 + 696) + 8LL));
  StringCchCopyW((unsigned __int16 *)(a5 + 1612), 0x100u, (const unsigned __int16 *)(a2 + 118));
  StringCchCopyW((unsigned __int16 *)(a5 + 2124), 0x10u, (const unsigned __int16 *)(a2 + 84));
  *(_DWORD *)(a5 + 2636) = *(_DWORD *)(a2 + 40);
  *(_DWORD *)(a5 + 2640) = *(_DWORD *)(a2 + 44);
  v16 = (int *)v19;
  if ( v19 )
    v17 = *((_QWORD *)v19 + 1);
  else
    v17 = 0;
  *(_QWORD *)(a5 + 2648) = v17;
  if ( v16 )
    v7 = *v16;
  *(_DWORD *)(a5 + 2656) = v7;
LABEL_21:
  __LicensePack::~__LicensePack((__LicensePack *)v41);
  return v9;
}

```

## disassembly

```asm
0x180033af4  mov     [rsp-8+arg_10], rbx
0x180033af9  push    rbp
0x180033afa  push    rsi
0x180033afb  push    rdi
0x180033afc  push    r12
0x180033afe  push    r13
0x180033b00  push    r14
0x180033b02  push    r15
0x180033b04  lea     rbp, [rsp-1080h]
0x180033b0c  mov     eax, 1180h
0x180033b11  call    _alloca_probe
0x180033b16  sub     rsp, rax
0x180033b19  mov     rax, cs:__security_cookie
0x180033b20  xor     rax, rsp
0x180033b23  mov     [rbp+10B0h+var_40], rax
0x180033b2a  mov     r13, rdx
0x180033b2d  mov     rbx, rcx
0x180033b30  mov     qword ptr [rsp+11B0h+var_1160.Id], rcx
0x180033b35  mov     r15, [rbp+10B0h+arg_20]
0x180033b3c  xor     edx, edx; Val
0x180033b3e  mov     r8d, 288h; Size
0x180033b44  lea     rcx, [rbp+10B0h+var_1120]; void *
0x180033b48  call    memset_0
0x180033b4d  xor     r14d, r14d
0x180033b50  mov     [rbp+10B0h+var_E88], r14
0x180033b57  mov     [rbp+10B0h+var_E68], r14
0x180033b5e  mov     [rbp+10B0h+var_E60], r14d
0x180033b65  xorps   xmm0, xmm0
0x180033b68  movups  [rsp+11B0h+var_1150], xmm0
0x180033b6d  movups  [rsp+11B0h+var_1140], xmm0
0x180033b72  movups  [rbp+10B0h+var_1130], xmm0
0x180033b76  mov     [rsp+11B0h+var_1180], r14
0x180033b7b  lea     r8, [rbp+10B0h+var_E90]
0x180033b82  mov     rdx, r13
0x180033b85  mov     rcx, rbx
0x180033b88  call    TLSDBGetTemporaryLicense
0x180033b8d  mov     r12d, eax
0x180033b90  test    eax, eax
0x180033b92  jnz     loc_180033F01
0x180033b98  mov     al, [rbp+10B0h+var_65C]
0x180033b9e  and     al, 0Fh
0x180033ba0  cmp     al, 4
0x180033ba2  jz      short loc_180033BCE
0x180033ba4  movzx   eax, [rbp+10B0h+var_E6C]
0x180033bab  and     eax, 0FFFFFF0Fh
0x180033bb0  cmp     al, 5
0x180033bb2  jz      short loc_180033BCE
0x180033bb4  mov     r12d, 1000h
0x180033bba  mov     ecx, r12d; dwErrCode
0x180033bbd  call    cs:__imp_SetLastError
0x180033bc4  nop     dword ptr [rax+rax+00h]
0x180033bc9  jmp     loc_180033F01
0x180033bce  call    ?GetNextLicenseId@CRdlsDBManager@@QEAAKXZ; CRdlsDBManager::GetNextLicenseId(void)
0x180033bd3  mov     dword ptr [rsp+11B0h+var_1178], eax
0x180033bd7  mov     ecx, [rbp+10B0h+var_E8C]
0x180033bdd  mov     dword ptr [rsp+11B0h+var_1178+4], ecx
0x180033be1  mov     [rbp+10B0h+var_111C], eax
0x180033be4  mov     [rbp+10B0h+var_1118], ecx
0x180033be7  mov     ecx, [rbp+10B0h+var_E7C]
0x180033bed  mov     [rbp+10B0h+var_1114], ecx
0x180033bf0  mov     r12d, 1
0x180033bf6  mov     [rbp+10B0h+var_EBC], r12d
0x180033bfd  xor     ecx, ecx; Time
0x180033bff  call    cs:__imp_time
0x180033c06  nop     dword ptr [rax+rax+00h]
0x180033c0b  mov     [rbp+10B0h+var_EC8], eax
0x180033c11  imul    ecx, cs:?g_GracePeriod@@3KA, 15180h; ulong g_GracePeriod
0x180033c1b  add     ecx, eax
0x180033c1d  mov     [rbp+10B0h+var_EC4], ecx
0x180033c23  mov     [rbp+10B0h+var_EC0], r12b
0x180033c2a  lea     r8, [r13+54h]; unsigned __int16 *
0x180033c2e  lea     edx, [r12+0Fh]; unsigned __int64
0x180033c33  lea     rcx, [rbp+10B0h+var_1108]; unsigned __int16 *
0x180033c37  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c3c  lea     r8, [r13+76h]; unsigned __int16 *
0x180033c40  mov     edx, 100h; unsigned __int64
0x180033c45  lea     rcx, [rbp+10B0h+var_10C8]; unsigned __int16 *
0x180033c49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c4e  mov     eax, [r13+30h]
0x180033c52  mov     [rbp+10B0h+var_EB8], eax
0x180033c58  mov     eax, [r13+34h]
0x180033c5c  mov     [rbp+10B0h+var_EB4], eax
0x180033c62  mov     eax, [r13+38h]
0x180033c66  mov     [rbp+10B0h+var_EB0], eax
0x180033c6c  mov     eax, [r13+3Ch]
0x180033c70  mov     [rbp+10B0h+var_EAC], eax
0x180033c76  mov     eax, [r13+40h]
0x180033c7a  mov     [rbp+10B0h+var_EA8], eax
0x180033c80  mov     eax, [rbp+10B0h+var_EC8]
0x180033c86  movsxd  rcx, eax
0x180033c89  mov     rdx, 2B6109100h
0x180033c93  add     rcx, rdx
0x180033c96  imul    rax, rcx, 989680h
0x180033c9d  mov     rcx, rax
0x180033ca0  shr     rcx, 20h
0x180033ca4  mov     dword ptr [rsp+11B0h+var_1170+4], ecx
0x180033ca8  mov     dword ptr [rsp+11B0h+var_1170], eax
0x180033cac  mov     eax, [rbp+10B0h+var_EC4]
0x180033cb2  movsxd  rcx, eax
0x180033cb5  add     rcx, rdx
0x180033cb8  imul    rax, rcx, 989680h
0x180033cbf  mov     rcx, rax
0x180033cc2  shr     rcx, 20h
0x180033cc6  mov     dword ptr [rsp+11B0h+var_1168+4], ecx
0x180033cca  mov     dword ptr [rsp+11B0h+var_1168], eax
0x180033cce  mov     rax, [r13+2C0h]
0x180033cd5  mov     qword ptr [rsp+11B0h+var_1150], rax
0x180033cda  mov     dword ptr [rsp+11B0h+var_1150+8], 4
0x180033ce2  mov     eax, [rbp+10B0h+var_E8C]
0x180033ce8  mov     dword ptr [rsp+11B0h+var_1150+0Ch], eax
0x180033cec  mov     eax, [rbp+10B0h+var_E7C]
0x180033cf2  mov     dword ptr [rsp+11B0h+var_1140], eax
0x180033cf6  mov     rsi, [rsp+11B0h+var_1178]
0x180033cfb  mov     qword ptr [rsp+11B0h+var_1140+8], rsi
0x180033d00  mov     rbx, [rsp+11B0h+var_1170]
0x180033d05  mov     qword ptr [rbp+10B0h+var_1130], rbx
0x180033d09  mov     rdi, [rsp+11B0h+var_1168]
0x180033d0e  mov     qword ptr [rbp+10B0h+var_1130+8], rdi
0x180033d12  mov     [rsp+11B0h+var_1188], r12d; int
0x180033d17  lea     rax, [rsp+11B0h+var_1180]
0x180033d1c  mov     [rsp+11B0h+var_1190], rax; void **
0x180033d21  lea     r9, [rsp+11B0h+var_1150]; void *
0x180033d26  lea     r8d, [r12+5]; unsigned int
0x180033d2b  mov     rdx, [r13+8]; void *
0x180033d2f  mov     rcx, [r13+0]; this
0x180033d33  call    ?PMLicenseRequest@CTLSPolicy@@QEAAKPEAXKQEAXPEAPEAXH@Z; CTLSPolicy::PMLicenseRequest(void *,ulong,void * const,void * *,int)
0x180033d38  mov     r12d, eax
0x180033d3b  test    eax, eax
0x180033d3d  jnz     loc_180033F01
0x180033d43  mov     rcx, [rsp+11B0h+var_1180]
0x180033d48  test    rcx, rcx
0x180033d4b  jz      short loc_180033DC9
0x180033d4d  cmp     [rcx+8], r14
0x180033d51  jz      short loc_180033D5A
0x180033d53  cmp     [rcx], r14d
0x180033d56  jz      short loc_180033D5F
0x180033d58  jmp     short loc_180033D70
0x180033d5a  cmp     [rcx], r14d
0x180033d5d  jz      short loc_180033D70
0x180033d5f  mov     [rcx], r14d
0x180033d62  mov     rax, [rsp+11B0h+var_1180]
0x180033d67  mov     [rax+8], r14
0x180033d6b  mov     rcx, [rsp+11B0h+var_1180]
0x180033d70  lea     rdx, [rcx+18h]; lpFileTime2
0x180033d74  add     rcx, 10h; lpFileTime1
0x180033d78  call    cs:__imp_CompareFileTime
0x180033d7f  nop     dword ptr [rax+rax+00h]
0x180033d84  test    eax, eax
0x180033d86  jle     short loc_180033DBC
0x180033d88  mov     rax, [r13+0]
0x180033d8c  lea     r9, [rax+258h]
0x180033d93  lea     r8, [rax+58h]
0x180033d97  mov     r12d, 0C800000Fh
0x180033d9d  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x180033da4  movdqu  xmmword ptr [rsp+11B0h+var_1160.Id], xmm0
0x180033daa  mov     edx, r12d; unsigned int
0x180033dad  lea     rcx, [rsp+11B0h+var_1160]; struct _EVENT_DESCRIPTOR
0x180033db2  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180033db7  jmp     loc_180033F01
0x180033dbc  mov     rdi, [rsp+11B0h+var_1180]
0x180033dc1  mov     rbx, [rdi+10h]
0x180033dc5  mov     rdi, [rdi+18h]
0x180033dc9  lea     rdx, [rbp+10B0h+var_1120]
0x180033dcd  mov     rcx, qword ptr [rsp+11B0h+var_1160.Id]
0x180033dd2  call    TLSDBLicenseAdd
0x180033dd7  mov     r12d, eax
0x180033dda  mov     [r15+0A68h], r14
0x180033de1  mov     ecx, 1
0x180033de6  mov     [r15], ecx
0x180033de9  mov     [r15+8], rsi
0x180033ded  mov     eax, [rbp+10B0h+var_E8C]
0x180033df3  mov     [r15+10h], eax
0x180033df7  mov     eax, dword ptr [rsp+11B0h+var_1178]
0x180033dfb  mov     [r15+14h], eax
0x180033dff  mov     eax, [rbp+10B0h+var_E7C]
0x180033e05  mov     [r15+18h], eax
0x180033e09  movups  xmm0, xmmword ptr [r13+30h]
0x180033e0e  movups  xmmword ptr [r15+20h], xmm0
0x180033e13  mov     eax, [r13+40h]
0x180033e17  mov     [r15+30h], eax
0x180033e1b  mov     [r15+44h], ecx
0x180033e1f  mov     [r15+34h], rbx
0x180033e23  mov     [r15+3Ch], rdi
0x180033e27  movzx   ecx, [rbp+10B0h+var_25A]
0x180033e2e  shl     ecx, 10h
0x180033e31  movzx   eax, [rbp+10B0h+var_258]
0x180033e38  or      ecx, eax
0x180033e3a  mov     [r15+48h], ecx
0x180033e3e  lea     rcx, [r15+4Ch]; Destination
0x180033e42  lea     r8, [rbp+10B0h+Source]; Source
0x180033e49  mov     ebx, 100h
0x180033e4e  mov     edx, ebx; SizeInWords
0x180033e50  call    cs:__imp_wcscpy_s
0x180033e57  nop     dword ptr [rax+rax+00h]
0x180033e5c  lea     rcx, [r15+24Ch]; Destination
0x180033e63  lea     r8, [rbp+10B0h+var_45A]; Source
0x180033e6a  mov     edx, ebx; SizeInWords
0x180033e6c  call    cs:__imp_wcscpy_s
0x180033e73  nop     dword ptr [rax+rax+00h]
0x180033e78  mov     rax, [r13+2B8h]
0x180033e7f  mov     r8, [rax+8]
0x180033e83  lea     rcx, [r15+44Ch]; Destination
0x180033e8a  mov     r8, [r8]; Source
0x180033e8d  mov     edx, ebx; SizeInWords
0x180033e8f  call    cs:__imp_wcscpy_s
0x180033e96  nop     dword ptr [rax+rax+00h]
0x180033e9b  lea     rcx, [r15+64Ch]; unsigned __int16 *
0x180033ea2  lea     r8, [r13+76h]; unsigned __int16 *
0x180033ea6  mov     edx, ebx; unsigned __int64
0x180033ea8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ead  lea     rcx, [r15+84Ch]; unsigned __int16 *
0x180033eb4  lea     r8, [r13+54h]; unsigned __int16 *
0x180033eb8  mov     edx, 10h; unsigned __int64
0x180033ebd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ec2  mov     r11d, [r13+28h]
0x180033ec6  mov     [r15+0A4Ch], r11d
0x180033ecd  mov     eax, [r13+2Ch]
0x180033ed1  mov     [r15+0A50h], eax
0x180033ed8  mov     rax, [rsp+11B0h+var_1180]
0x180033edd  test    rax, rax
0x180033ee0  jz      short loc_180033EE8
0x180033ee2  mov     rcx, [rax+8]
0x180033ee6  jmp     short loc_180033EEB
0x180033ee8  mov     rcx, r14
0x180033eeb  mov     [r15+0A58h], rcx
0x180033ef2  test    rax, rax
0x180033ef5  jz      short loc_180033EFA
0x180033ef7  mov     r14d, [rax]
0x180033efa  mov     [r15+0A60h], r14d
0x180033f01  lea     rcx, [rbp+10B0h+var_E90]; this
0x180033f08  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x180033f0d  mov     eax, r12d
0x180033f10  mov     rcx, [rbp+10B0h+var_40]
0x180033f17  xor     rcx, rsp; StackCookie
0x180033f1a  call    __security_check_cookie
0x180033f1f  mov     rbx, [rsp+11B0h+arg_10]
0x180033f27  add     rsp, 1180h
0x180033f2e  pop     r15
0x180033f30  pop     r14
0x180033f32  pop     r13
0x180033f34  pop     r12
0x180033f36  pop     rdi
0x180033f37  pop     rsi
0x180033f38  pop     rbp
0x180033f39  retn
```
