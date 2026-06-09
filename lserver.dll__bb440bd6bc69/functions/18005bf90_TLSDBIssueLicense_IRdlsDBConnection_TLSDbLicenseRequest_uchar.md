# TLSDBIssueLicense(IRdlsDBConnection *,__TLSDbLicenseRequest *,uchar)

- ea: `0x18005bf90`
- end: `0x18005c264`
- name: `?TLSDBIssueLicense@@YAKPEAVIRdlsDBConnection@@PEAU__TLSDbLicenseRequest@@E@Z`
- size: `724`
- prototype: `unsigned int __fastcall(struct IRdlsDBConnection *, struct __TLSDbLicenseRequest *, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005cd14`

## callees

- `0x180005665`
- `0x18000cff0`
- `0x180022910`
- `0x180030a20`
- `0x180035408`
- `0x18005be20`
- `0x18005bf90`
- `0x1800662a0`
- `0x18007e438`
- `0x1800a0fb0`
- `0x1800a1070`

## import_xrefs

- `msvcrt!time` at `0x18005c093`
- `msvcrt!time` at `0x18005c093`
- `KERNEL32!CompareFileTime` at `0x18005c1df`
- `KERNEL32!CompareFileTime` at `0x18005c1df`
- `KERNEL32!SetLastError` at `0x18005c040`
- `KERNEL32!SetLastError` at `0x18005c040`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TLSDBIssueLicense(
        struct IRdlsDBConnection *a1,
        struct __TLSDbLicenseRequest *a2,
        unsigned __int8 a3)
{
  int v3; // r15d
  unsigned int v6; // ebx
  unsigned int v7; // r13d
  CRdlsDBManager *v8; // rcx
  unsigned int v9; // esi
  int v10; // edi
  int v11; // ebx
  const FILETIME *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  void *v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  struct _EVENT_DESCRIPTOR v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v21; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+80h] [rbp-80h]
  _BYTE v23[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v24; // [rsp+94h] [rbp-6Ch]
  __int64 v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+A4h] [rbp-5Ch]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  int v28; // [rsp+C0h] [rbp-40h]
  unsigned __int8 v29; // [rsp+8C4h] [rbp+7C4h]
  _BYTE v30[4]; // [rsp+EE0h] [rbp+DE0h] BYREF
  int v31; // [rsp+EE4h] [rbp+DE4h]
  unsigned int v32; // [rsp+EE8h] [rbp+DE8h]
  int v33; // [rsp+EECh] [rbp+DECh]
  unsigned __int16 v34[32]; // [rsp+EF8h] [rbp+DF8h] BYREF
  unsigned __int16 v35[256]; // [rsp+F38h] [rbp+E38h] BYREF
  int v36; // [rsp+1138h] [rbp+1038h]
  int v37; // [rsp+113Ch] [rbp+103Ch]
  char v38; // [rsp+1140h] [rbp+1040h]
  int v39; // [rsp+1144h] [rbp+1044h]
  __int64 v40; // [rsp+1148h] [rbp+1048h]
  __int64 v41; // [rsp+1150h] [rbp+1050h]
  int v42; // [rsp+1158h] [rbp+1058h]

  v3 = a3;
  memset_0(v30, 0, 0x288u);
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v16 = 0;
  v6 = TLSDBGetLicense(a1, a2, (struct __LicensePack *)v23, v3);
  if ( !v6 )
  {
    v7 = v29;
    v8 = (CRdlsDBManager *)(v29 & 0xF);
    if ( (_DWORD)v8 != v3 )
    {
      v6 = 4096;
      SetLastError(0x1000u);
      goto LABEL_16;
    }
    LODWORD(v17) = CRdlsDBManager::GetNextLicenseId(v8);
    v9 = v24;
    HIDWORD(v17) = v24;
    v31 = v17;
    v32 = v24;
    v10 = v26;
    v33 = v26;
    v39 = 1;
    v11 = *(_DWORD *)&g_dwReissueLeasePU;
    if ( (_BYTE)v3 == 7 )
      v11 = *(_DWORD *)&g_dwLeasePUFailed;
    v36 = time(0);
    v37 = v11 + v36;
    v38 = 2;
    StringCchCopyW(v34, 0x10u, (const unsigned __int16 *)a2 + 42);
    StringCchCopyW(v35, 0x100u, (const unsigned __int16 *)a2 + 59);
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v18 = 10000000 * (v36 + 0x2B6109100LL);
    *(_QWORD *)&v19.Id = 10000000 * (v37 + 0x2B6109100LL);
    *(_QWORD *)&v20 = *((_QWORD *)a2 + 88);
    *((_QWORD *)&v20 + 1) = __PAIR64__(v9, v7);
    LODWORD(v21) = v10;
    *((_QWORD *)&v21 + 1) = v17;
    *(_QWORD *)&v22 = v18;
    *((_QWORD *)&v22 + 1) = *(_QWORD *)&v19.Id;
    v6 = CTLSPolicy::PMLicenseRequest(*(CTLSPolicy **)a2, *((void **)a2 + 1), 6u, &v20, &v16, 1);
    if ( !v6 )
    {
      v12 = (const FILETIME *)v16;
      if ( !v16 )
        goto LABEL_15;
      if ( *((_QWORD *)v16 + 1) )
      {
        if ( *(_DWORD *)v16 )
        {
LABEL_13:
          if ( CompareFileTime(v12 + 2, v12 + 3) > 0 )
          {
            v13 = *(_QWORD *)a2 + 600LL;
            v14 = *(_QWORD *)a2 + 88LL;
            v6 = -939524081;
            v19 = (struct _EVENT_DESCRIPTOR)TLS_E_GENERATECLIENTELICENSE;
            TLSLogEvent(&v19, 0xC800000F, v14, v13);
            goto LABEL_16;
          }
LABEL_15:
          v6 = TLSDBLicenseAdd(a1, v30);
          goto LABEL_16;
        }
      }
      else if ( !*(_DWORD *)v16 )
      {
        goto LABEL_13;
      }
      *(_DWORD *)v16 = 0;
      *((_QWORD *)v16 + 1) = 0;
      v12 = (const FILETIME *)v16;
      goto LABEL_13;
    }
  }
LABEL_16:
  __LicensePack::~__LicensePack((__LicensePack *)v23);
  return v6;
}

```

## disassembly

```asm
0x18005bf90  mov     [rsp-8+arg_18], rbx
0x18005bf95  push    rbp
0x18005bf96  push    rsi
0x18005bf97  push    rdi
0x18005bf98  push    r12
0x18005bf9a  push    r13
0x18005bf9c  push    r14
0x18005bf9e  push    r15
0x18005bfa0  lea     rbp, [rsp-1080h]
0x18005bfa8  mov     eax, 1180h
0x18005bfad  call    _alloca_probe
0x18005bfb2  sub     rsp, rax
0x18005bfb5  mov     rax, cs:__security_cookie
0x18005bfbc  xor     rax, rsp
0x18005bfbf  mov     [rbp+10B0h+var_40], rax
0x18005bfc6  movzx   r15d, r8b
0x18005bfca  mov     r14, rdx
0x18005bfcd  mov     r12, rcx
0x18005bfd0  xor     edx, edx; Val
0x18005bfd2  mov     r8d, 288h; Size
0x18005bfd8  lea     rcx, [rbp+10B0h+var_2D0]; void *
0x18005bfdf  call    memset_0
0x18005bfe4  xor     edi, edi
0x18005bfe6  mov     [rbp+10B0h+var_1118], rdi
0x18005bfea  mov     [rbp+10B0h+var_10F8], rdi
0x18005bfee  mov     [rbp+10B0h+var_10F0], edi
0x18005bff1  xorps   xmm0, xmm0
0x18005bff4  movups  [rsp+11B0h+var_1150], xmm0
0x18005bff9  movups  [rsp+11B0h+var_1140], xmm0
0x18005bffe  movups  [rbp+10B0h+var_1130], xmm0
0x18005c002  mov     [rsp+11B0h+var_1180], rdi
0x18005c007  mov     r9b, r15b; unsigned __int8
0x18005c00a  lea     r8, [rbp+10B0h+var_1120]; struct __LicensePack *
0x18005c00e  mov     rdx, r14; struct __TLSDbLicenseRequest *
0x18005c011  mov     rcx, r12; struct IRdlsDBConnection *
0x18005c014  call    ?TLSDBGetLicense@@YAKPEAVIRdlsDBConnection@@PEAU__TLSDbLicenseRequest@@PEAU__LicensePack@@E@Z; TLSDBGetLicense(IRdlsDBConnection *,__TLSDbLicenseRequest *,__LicensePack *,uchar)
0x18005c019  mov     ebx, eax
0x18005c01b  test    eax, eax
0x18005c01d  jnz     loc_18005C22E
0x18005c023  movzx   r13d, [rbp+10B0h+var_8EC]
0x18005c02b  mov     ecx, r13d
0x18005c02e  and     ecx, 0FFFFFF0Fh; this
0x18005c034  cmp     ecx, r15d
0x18005c037  jz      short loc_18005C051
0x18005c039  mov     ebx, 1000h
0x18005c03e  mov     ecx, ebx; dwErrCode
0x18005c040  call    cs:__imp_SetLastError
0x18005c047  nop     dword ptr [rax+rax+00h]
0x18005c04c  jmp     loc_18005C22E
0x18005c051  call    ?GetNextLicenseId@CRdlsDBManager@@QEAAKXZ; CRdlsDBManager::GetNextLicenseId(void)
0x18005c056  mov     dword ptr [rsp+11B0h+var_1178], eax
0x18005c05a  mov     esi, [rbp+10B0h+var_111C]
0x18005c05d  mov     dword ptr [rsp+11B0h+var_1178+4], esi
0x18005c061  mov     [rbp+10B0h+var_2CC], eax
0x18005c067  mov     [rbp+10B0h+var_2C8], esi
0x18005c06d  mov     edi, [rbp+10B0h+var_110C]
0x18005c070  mov     [rbp+10B0h+var_2C4], edi
0x18005c076  mov     [rbp+10B0h+var_6C], 1
0x18005c080  mov     ebx, cs:?g_dwReissueLeasePU@@3KA; ulong g_dwReissueLeasePU
0x18005c086  cmp     r15b, 7
0x18005c08a  cmovz   ebx, cs:?g_dwLeasePUFailed@@3KA; ulong g_dwLeasePUFailed
0x18005c091  xor     ecx, ecx; Time
0x18005c093  call    cs:__imp_time
0x18005c09a  nop     dword ptr [rax+rax+00h]
0x18005c09f  mov     [rbp+10B0h+var_78], eax
0x18005c0a5  add     eax, ebx
0x18005c0a7  mov     [rbp+10B0h+var_74], eax
0x18005c0ad  mov     [rbp+10B0h+var_70], 2
0x18005c0b4  lea     r8, [r14+54h]; unsigned __int16 *
0x18005c0b8  mov     edx, 10h; unsigned __int64
0x18005c0bd  lea     rcx, [rbp+10B0h+var_2B8]; unsigned __int16 *
0x18005c0c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005c0c9  lea     r8, [r14+76h]; unsigned __int16 *
0x18005c0cd  mov     edx, 100h; unsigned __int64
0x18005c0d2  lea     rcx, [rbp+10B0h+var_278]; unsigned __int16 *
0x18005c0d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005c0de  xor     r15d, r15d
0x18005c0e1  mov     [rbp+10B0h+var_68], r15
0x18005c0e8  mov     [rbp+10B0h+var_60], r15
0x18005c0ef  mov     [rbp+10B0h+var_58], r15d
0x18005c0f6  mov     eax, [rbp+10B0h+var_78]
0x18005c0fc  movsxd  rcx, eax
0x18005c0ff  mov     rdx, 2B6109100h
0x18005c109  add     rcx, rdx
0x18005c10c  imul    rax, rcx, 989680h
0x18005c113  mov     rcx, rax
0x18005c116  shr     rcx, 20h
0x18005c11a  mov     dword ptr [rsp+11B0h+var_1170+4], ecx
0x18005c11e  mov     dword ptr [rsp+11B0h+var_1170], eax
0x18005c122  mov     eax, [rbp+10B0h+var_74]
0x18005c128  movsxd  rcx, eax
0x18005c12b  add     rcx, rdx
0x18005c12e  imul    rax, rcx, 989680h
0x18005c135  mov     rcx, rax
0x18005c138  shr     rcx, 20h
0x18005c13c  mov     dword ptr [rsp+11B0h+var_1160.Level], ecx
0x18005c140  mov     dword ptr [rsp+11B0h+var_1160.Id], eax
0x18005c144  mov     rax, [r14+2C0h]
0x18005c14b  mov     qword ptr [rsp+11B0h+var_1150], rax
0x18005c150  mov     dword ptr [rsp+11B0h+var_1150+8], r13d
0x18005c155  mov     dword ptr [rsp+11B0h+var_1150+0Ch], esi
0x18005c159  mov     dword ptr [rsp+11B0h+var_1140], edi
0x18005c15d  mov     rax, [rsp+11B0h+var_1178]
0x18005c162  mov     qword ptr [rsp+11B0h+var_1140+8], rax
0x18005c167  mov     rax, [rsp+11B0h+var_1170]
0x18005c16c  mov     qword ptr [rbp+10B0h+var_1130], rax
0x18005c170  mov     rax, qword ptr [rsp+11B0h+var_1160.Id]
0x18005c175  mov     qword ptr [rbp+10B0h+var_1130+8], rax
0x18005c179  mov     [rsp+11B0h+var_1188], 1; int
0x18005c181  lea     rax, [rsp+11B0h+var_1180]
0x18005c186  mov     [rsp+11B0h+var_1190], rax; void **
0x18005c18b  lea     r9, [rsp+11B0h+var_1150]; void *
0x18005c190  lea     r8d, [r15+6]; unsigned int
0x18005c194  mov     rdx, [r14+8]; void *
0x18005c198  mov     rcx, [r14]; this
0x18005c19b  call    ?PMLicenseRequest@CTLSPolicy@@QEAAKPEAXKQEAXPEAPEAXH@Z; CTLSPolicy::PMLicenseRequest(void *,ulong,void * const,void * *,int)
0x18005c1a0  mov     ebx, eax
0x18005c1a2  test    eax, eax
0x18005c1a4  jnz     loc_18005C22E
0x18005c1aa  mov     rcx, [rsp+11B0h+var_1180]
0x18005c1af  test    rcx, rcx
0x18005c1b2  jz      short loc_18005C21D
0x18005c1b4  cmp     [rcx+8], r15
0x18005c1b8  jz      short loc_18005C1C1
0x18005c1ba  cmp     [rcx], r15d
0x18005c1bd  jz      short loc_18005C1C6
0x18005c1bf  jmp     short loc_18005C1D7
0x18005c1c1  cmp     [rcx], r15d
0x18005c1c4  jz      short loc_18005C1D7
0x18005c1c6  mov     [rcx], r15d
0x18005c1c9  mov     rax, [rsp+11B0h+var_1180]
0x18005c1ce  mov     [rax+8], r15
0x18005c1d2  mov     rcx, [rsp+11B0h+var_1180]
0x18005c1d7  lea     rdx, [rcx+18h]; lpFileTime2
0x18005c1db  add     rcx, 10h; lpFileTime1
0x18005c1df  call    cs:__imp_CompareFileTime
0x18005c1e6  nop     dword ptr [rax+rax+00h]
0x18005c1eb  test    eax, eax
0x18005c1ed  jle     short loc_18005C21D
0x18005c1ef  mov     rax, [r14]
0x18005c1f2  lea     r9, [rax+258h]
0x18005c1f9  lea     r8, [rax+58h]
0x18005c1fd  mov     ebx, 0C800000Fh
0x18005c202  movups  xmm0, cs:TLS_E_GENERATECLIENTELICENSE
0x18005c209  movdqu  xmmword ptr [rsp+11B0h+var_1160.Id], xmm0
0x18005c20f  mov     edx, ebx; unsigned int
0x18005c211  lea     rcx, [rsp+11B0h+var_1160]; struct _EVENT_DESCRIPTOR
0x18005c216  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x18005c21b  jmp     short loc_18005C22E
0x18005c21d  lea     rdx, [rbp+10B0h+var_2D0]
0x18005c224  mov     rcx, r12
0x18005c227  call    TLSDBLicenseAdd
0x18005c22c  mov     ebx, eax
0x18005c22e  lea     rcx, [rbp+10B0h+var_1120]; this
0x18005c232  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x18005c237  mov     eax, ebx
0x18005c239  mov     rcx, [rbp+10B0h+var_40]
0x18005c240  xor     rcx, rsp; StackCookie
0x18005c243  call    __security_check_cookie
0x18005c248  mov     rbx, [rsp+11B0h+arg_18]
0x18005c250  add     rsp, 1180h
0x18005c257  pop     r15
0x18005c259  pop     r14
0x18005c25b  pop     r13
0x18005c25d  pop     r12
0x18005c25f  pop     rdi
0x18005c260  pop     rsi
0x18005c261  pop     rbp
0x18005c262  retn
```
