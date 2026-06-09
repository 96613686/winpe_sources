# ReplaceAllInserts(_EVENTLOGRECORD *,CLogInfo *,ushort *,CSafeReg *,CSafeReg *,CSafeReg *,PSK,ushort * *)

- ea: `0x18000eb2c`
- end: `0x18000f094`
- name: `?ReplaceAllInserts@@YAXPEAU_EVENTLOGRECORD@@PEAVCLogInfo@@PEAGPEAVCSafeReg@@33W4PSK@@PEAPEAG@Z`
- size: `1384`
- prototype: `void __fastcall(struct _EVENTLOGRECORD *, __int64, unsigned __int16 *, __int64, const void *, __int64, char, const wchar_t **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d814`

## callees

- `0x180001750`
- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x180007014`
- `0x18000c5c0`
- `0x18000c684`
- `0x18000dfdc`
- `0x18000e208`
- `0x18000eb2c`
- `0x18000f09c`
- `0x18000f4b4`
- `0x18000f564`
- `0x18001f960`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcschr` at `0x18000ebfa`
- `msvcrt!wcschr` at `0x18000ec77`
- `msvcrt!wcschr` at `0x18000eda3`
- `msvcrt!wcschr` at `0x18000eeb2`
- `msvcrt!wcschr` at `0x18000ebfa`
- `msvcrt!wcschr` at `0x18000ec77`
- `msvcrt!wcschr` at `0x18000eda3`
- `msvcrt!wcschr` at `0x18000eeb2`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18000ef05`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18000ef05`
- `KERNEL32!LocalFree` at `0x18000ef8c`
- `KERNEL32!LocalFree` at `0x18000f04d`
- `KERNEL32!LocalFree` at `0x18000ef8c`
- `KERNEL32!LocalFree` at `0x18000f04d`
- `KERNEL32!LocalAlloc` at `0x18000ec36`
- `KERNEL32!LocalAlloc` at `0x18000ec36`

## pseudocode

```c
void __fastcall ReplaceAllInserts(
        struct _EVENTLOGRECORD *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        const void *a5,
        __int64 a6,
        char a7,
        const wchar_t **a8)
{
  struct _EVENTLOGRECORD *v8; // r14
  const unsigned __int16 **v9; // r12
  int v10; // r13d
  int v11; // edi
  unsigned __int16 *v12; // r15
  unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ecx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbx
  wchar_t *v18; // rax
  wchar_t *v19; // rbx
  unsigned __int16 *v20; // rsi
  __int64 v21; // rbx
  const wchar_t *v22; // rcx
  wchar_t *v23; // rax
  wchar_t *v24; // r14
  __int64 ComputerNameAsString; // rax
  __int64 v26; // rdx
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  wchar_t *v29; // rax
  wchar_t *v30; // r15
  const WCHAR *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 MappedSID; // rax
  __int64 v36; // rdx
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  unsigned __int16 *v40; // rbx
  unsigned __int16 *v41; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v43; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v44; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _EVENTLOGRECORD *v45; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v46; // [rsp+68h] [rbp-98h]
  PSID Sid; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v48; // [rsp+78h] [rbp-88h]
  struct CLogInfo *v49; // [rsp+80h] [rbp-80h]
  _DWORD v50[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  LPCVOID v53[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v55[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v57[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v59; // [rsp+E8h] [rbp-18h]
  LPCWSTR StringSid[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v61[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v62[32]; // [rsp+130h] [rbp+30h] BYREF

  v48 = a3;
  v49 = (struct CLogInfo *)a2;
  v8 = a1;
  v45 = a1;
  v9 = a8;
  v10 = 0;
  v11 = 0;
  v12 = (unsigned __int16 *)((a2 + 32) & -(__int64)(*(_WORD *)(a2 + 32) != 0));
  v46 = v12;
  if ( (*(_BYTE *)(a2 + 24) & 1) != 0 )
  {
    v13 = &g_wszAuxMessageSource;
    if ( !g_wszAuxMessageSource )
      v13 = v12;
    v12 = v13;
    v46 = v13;
  }
  v41 = 0;
  v56 = 0;
  v54 = 0;
  v52 = 0;
  v55[0] = 0;
  v55[1] = a4;
  v53[0] = (LPCVOID)0x100000000LL;
  v53[1] = a5;
  v50[0] = 0;
  v50[1] = 2;
  v51 = a6;
  if ( wcschr(*a8, 0x25u) )
  {
    v14 = -1;
    do
      ++v14;
    while ( (*v9)[v14] );
    v15 = v14 + 1;
    v44 = v15 >> 1;
    v43 = v15 + (v15 >> 1);
    v16 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * v43);
    v17 = v16;
    v41 = v16;
    if ( v16 )
    {
      StringCchCopyW(v16, v43, *v9);
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              if ( !v17 || !*v17 || (v18 = wcschr(v17, 0x25u), v19 = v18, (v42 = v18) == 0) )
              {
LABEL_64:
                v40 = v41;
                if ( v41 )
                {
                  LocalFree((HLOCAL)*v9);
                  *v9 = v40;
                }
                goto LABEL_66;
              }
              v20 = v18 + 1;
              if ( (unsigned __int16)(v18[1] - 48) <= 9u )
              {
                ReplaceStringInsert(&v41, v8);
                goto LABEL_15;
              }
              if ( *v20 != 37 )
                break;
              if ( (unsigned __int16)(v18[2] - 48) > 9u )
              {
                if ( v18[2] == 37 && (unsigned __int16)(v18[3] - 48) <= 9u )
                {
                  v21 = (char *)v18 - (char *)v41;
                  v42 = v18 + 2;
                  if ( ReplaceStringInsert(&v41, v8) >= 0 )
                  {
                    v17 = &v41[(int)(v21 >> 1)];
                    if ( (unsigned int)++v10 >= 0x64 )
                      goto LABEL_64;
                  }
                  else
                  {
                    v17 = v42;
                  }
                }
                else
                {
                  v17 = v18 + 1;
                }
              }
              else
              {
                ReplaceParameterInsert(
                  &v41,
                  v8,
                  v49,
                  v48,
                  (struct SParamModule *)v55,
                  v53,
                  (struct SParamModule *)v50,
                  (enum PSK *)&a7);
LABEL_15:
                if ( (unsigned int)++v10 >= 0x64 )
                  goto LABEL_64;
                v17 = v42;
              }
            }
            if ( *v20 == 123 )
              break;
            v17 = v18 + 1;
          }
          v22 = v18 + 2;
          if ( v18[2] == 83 )
            break;
          v23 = wcschr(v22, 0x7Du);
          v24 = v23;
          if ( v23 )
          {
            std::wstring::wstring(StringSid, v20, v23 - v19);
            if ( v12 )
            {
              ComputerNameAsString = std::wstring::wstring(v61, v12);
              v11 |= 1u;
            }
            else
            {
              ComputerNameAsString = GetComputerNameAsString(v62);
              v11 |= 2u;
            }
            GetMappedGUID(v57, ComputerNameAsString, StringSid);
            if ( (v11 & 2) != 0 )
            {
              v11 &= ~2u;
              LOBYTE(v26) = 1;
              std::wstring::_Tidy(v62, v26, 0);
            }
            if ( (v11 & 1) != 0 )
            {
              v11 &= ~1u;
              LOBYTE(v26) = 1;
              std::wstring::_Tidy(v61, v26, 0);
            }
            if ( v58 )
            {
              v27 = (const unsigned __int16 *)v57;
              if ( v59 >= 8 )
                v27 = v57[0];
              if ( ReplaceSubStr(v27, &v41, &v42, v24 + 1, &v43, &v44) < 0 )
                goto LABEL_63;
              v17 = v42;
            }
            else
            {
              v17 = v24;
            }
            LOBYTE(v26) = 1;
            std::wstring::_Tidy(v57, v26, 0);
            LOBYTE(v28) = 1;
            std::wstring::_Tidy(StringSid, v28, 0);
          }
          else
          {
            v17 = v20;
          }
LABEL_52:
          v8 = v45;
        }
        v29 = wcschr(v22, 0x7Du);
        v30 = v29;
        if ( !v29 )
          break;
        std::wstring::wstring(StringSid, v19 + 2, v29 - v19 - 2);
        std::wstring::wstring(v57);
        Sid = 0;
        v31 = (const WCHAR *)StringSid;
        if ( StringSid[3] >= (LPCWSTR)8 )
          v31 = StringSid[0];
        if ( !ConvertStringSidToSidW(v31, &Sid) )
        {
          v17 = v30;
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v57, v32, 0);
          LOBYTE(v33) = 1;
          std::wstring::_Tidy(StringSid, v33, 0);
          goto LABEL_51;
        }
        v34 = -1;
        v8 = v45;
        do
          ++v34;
        while ( *((_WORD *)&v45[1].Length + v34) );
        MappedSID = GetMappedSID(v61, (unsigned __int16 *)&v45[1].Length + v34 + 1, v46, Sid);
        std::wstring::operator=(v57, MappedSID);
        LOBYTE(v36) = 1;
        std::wstring::_Tidy(v61, v36, 0);
        LocalFree(Sid);
        Sid = 0;
        if ( v58 )
        {
          v37 = (const unsigned __int16 *)v57;
          if ( v59 >= 8 )
            v37 = v57[0];
          if ( ReplaceSubStr(v37, &v41, &v42, v30 + 1, &v43, &v44) < 0 )
          {
LABEL_63:
            LOBYTE(v26) = 1;
            std::wstring::_Tidy(v57, v26, 0);
            LOBYTE(v39) = 1;
            std::wstring::_Tidy(StringSid, v39, 0);
            goto LABEL_64;
          }
          v17 = v42;
        }
        else
        {
          v17 = v30;
        }
        LOBYTE(v26) = 1;
        std::wstring::_Tidy(v57, v26, 0);
        LOBYTE(v38) = 1;
        std::wstring::_Tidy(StringSid, v38, 0);
        v12 = v46;
      }
      v17 = v20;
LABEL_51:
      v12 = v46;
      goto LABEL_52;
    }
  }
LABEL_66:
  CSafeCacheHandle::~CSafeCacheHandle((CSafeCacheHandle *)&v52);
  CSafeCacheHandle::~CSafeCacheHandle((CSafeCacheHandle *)&v54);
  CSafeCacheHandle::~CSafeCacheHandle((CSafeCacheHandle *)&v56);
}

```

## disassembly

```asm
0x18000eb2c  push    rbp
0x18000eb2e  push    rbx
0x18000eb2f  push    rsi
0x18000eb30  push    rdi
0x18000eb31  push    r12
0x18000eb33  push    r13
0x18000eb35  push    r14
0x18000eb37  push    r15
0x18000eb39  lea     rbp, [rsp-68h]
0x18000eb3e  sub     rsp, 168h
0x18000eb45  mov     rax, cs:__security_cookie
0x18000eb4c  xor     rax, rsp
0x18000eb4f  mov     [rbp+0A0h+var_50], rax
0x18000eb53  mov     [rsp+1A0h+var_128], r8
0x18000eb58  mov     [rbp+0A0h+var_120], rdx
0x18000eb5c  mov     r14, rcx
0x18000eb5f  mov     [rsp+1A0h+var_140], rcx
0x18000eb64  mov     r10, [rbp+0A0h+arg_20]
0x18000eb6b  mov     r11, [rbp+0A0h+arg_28]
0x18000eb72  mov     r12, [rbp+0A0h+arg_38]
0x18000eb79  xor     r13d, r13d
0x18000eb7c  mov     edi, r13d
0x18000eb7f  mov     [rsp+1A0h+var_160], r13d
0x18000eb84  lea     rcx, [rdx+20h]
0x18000eb88  movzx   eax, word ptr [rcx]
0x18000eb8b  neg     ax
0x18000eb8e  sbb     r15, r15
0x18000eb91  and     r15, rcx
0x18000eb94  mov     [rsp+1A0h+var_138], r15
0x18000eb99  test    byte ptr [rdx+18h], 1
0x18000eb9d  jz      short loc_18000EBBA
0x18000eb9f  lea     rax, ?g_wszAuxMessageSource@@3PAGA; ushort near * g_wszAuxMessageSource
0x18000eba6  cmp     cs:?g_wszAuxMessageSource@@3PAGA, r13w; ushort near * g_wszAuxMessageSource
0x18000ebae  cmovz   rax, r15
0x18000ebb2  mov     r15, rax
0x18000ebb5  mov     [rsp+1A0h+var_138], rax
0x18000ebba  mov     [rsp+1A0h+var_158], r13
0x18000ebbf  mov     [rbp+0A0h+var_D8], r13
0x18000ebc3  mov     [rbp+0A0h+var_F0], r13
0x18000ebc7  mov     [rbp+0A0h+var_108], r13
0x18000ebcb  mov     [rbp+0A0h+var_E8], r13
0x18000ebcf  mov     [rbp+0A0h+var_E0], r9
0x18000ebd3  mov     [rbp+0A0h+var_100], r13d
0x18000ebd7  mov     [rbp+0A0h+var_FC], 1
0x18000ebde  mov     [rbp+0A0h+var_F8], r10
0x18000ebe2  mov     [rbp+0A0h+var_118], r13d
0x18000ebe6  mov     [rbp+0A0h+var_114], 2
0x18000ebed  mov     [rbp+0A0h+var_110], r11
0x18000ebf1  mov     edx, 25h ; '%'; Ch
0x18000ebf6  mov     rcx, [r12]; Str
0x18000ebfa  call    cs:__imp_wcschr
0x18000ec00  test    rax, rax
0x18000ec03  jz      loc_18000F057
0x18000ec09  mov     rax, [r12]
0x18000ec0d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ec11  inc     rcx
0x18000ec14  cmp     [rax+rcx*2], r13w
0x18000ec19  jnz     short loc_18000EC11
0x18000ec1b  inc     ecx
0x18000ec1d  mov     eax, ecx
0x18000ec1f  shr     eax, 1
0x18000ec21  mov     [rsp+1A0h+var_144], eax
0x18000ec25  add     eax, ecx
0x18000ec27  mov     [rsp+1A0h+var_148], eax
0x18000ec2b  mov     esi, eax
0x18000ec2d  lea     rdx, [rax+rax]; uBytes
0x18000ec31  mov     ecx, 40h ; '@'; uFlags
0x18000ec36  call    cs:__imp_LocalAlloc
0x18000ec3c  mov     rbx, rax
0x18000ec3f  mov     [rsp+1A0h+var_158], rax
0x18000ec44  test    rax, rax
0x18000ec47  jz      loc_18000F057
0x18000ec4d  mov     r8, [r12]; unsigned __int16 *
0x18000ec51  mov     edx, esi; unsigned __int64
0x18000ec53  mov     rcx, rax; unsigned __int16 *
0x18000ec56  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ec5b  xor     esi, esi
0x18000ec5d  mov     edx, 25h ; '%'; Ch
0x18000ec62  test    rbx, rbx
0x18000ec65  jz      loc_18000F03F
0x18000ec6b  cmp     [rbx], si
0x18000ec6e  jz      loc_18000F03F
0x18000ec74  mov     rcx, rbx; Str
0x18000ec77  call    cs:__imp_wcschr
0x18000ec7d  mov     rbx, rax
0x18000ec80  mov     [rsp+1A0h+var_150], rax
0x18000ec85  test    rax, rax
0x18000ec88  jz      loc_18000F03F
0x18000ec8e  lea     rsi, [rax+2]
0x18000ec92  movzx   eax, word ptr [rsi]
0x18000ec95  sub     ax, 30h ; '0'
0x18000ec99  cmp     ax, 9
0x18000ec9d  ja      short loc_18000ECC0
0x18000ec9f  mov     rdx, r14; struct _EVENTLOGRECORD *
0x18000eca2  lea     rcx, [rsp+1A0h+var_158]; unsigned __int16 **
0x18000eca7  call    ?ReplaceStringInsert@@YAJPEAUSDescriptionStr@@PEAU_EVENTLOGRECORD@@@Z; ReplaceStringInsert(SDescriptionStr *,_EVENTLOGRECORD *)
0x18000ecac  inc     r13d
0x18000ecaf  cmp     r13d, 64h ; 'd'
0x18000ecb3  jnb     loc_18000F03F
0x18000ecb9  mov     rbx, [rsp+1A0h+var_150]
0x18000ecbe  jmp     short loc_18000EC5B
0x18000ecc0  mov     edx, 25h ; '%'
0x18000ecc5  cmp     [rsi], dx
0x18000ecc8  jnz     loc_18000ED82
0x18000ecce  lea     rcx, [rbx+4]
0x18000ecd2  movzx   eax, word ptr [rcx]
0x18000ecd5  sub     ax, 30h ; '0'
0x18000ecd9  cmp     ax, 9
0x18000ecdd  ja      short loc_18000ED1E
0x18000ecdf  lea     rax, [rbp+0A0h+arg_30]
0x18000ece6  mov     [rsp+1A0h+var_168], rax; enum PSK *
0x18000eceb  lea     rax, [rbp+0A0h+var_118]
0x18000ecef  mov     [rsp+1A0h+var_170], rax; struct SParamModule *
0x18000ecf4  lea     rax, [rbp+0A0h+var_100]
0x18000ecf8  mov     [rsp+1A0h+var_178], rax; struct SParamModule *
0x18000ecfd  lea     rax, [rbp+0A0h+var_E8]
0x18000ed01  mov     [rsp+1A0h+var_180], rax; struct SParamModule *
0x18000ed06  mov     r9, [rsp+1A0h+var_128]; unsigned __int16 *
0x18000ed0b  mov     r8, [rbp+0A0h+var_120]; struct CLogInfo *
0x18000ed0f  mov     rdx, r14; struct _EVENTLOGRECORD *
0x18000ed12  lea     rcx, [rsp+1A0h+var_158]; struct SDescriptionStr *
0x18000ed17  call    ?ReplaceParameterInsert@@YAXPEAUSDescriptionStr@@PEAU_EVENTLOGRECORD@@PEAVCLogInfo@@PEAGPEAUSParamModule@@44PEAW4PSK@@@Z; ReplaceParameterInsert(SDescriptionStr *,_EVENTLOGRECORD *,CLogInfo *,ushort *,SParamModule *,SParamModule *,SParamModule *,PSK *)
0x18000ed1c  jmp     short loc_18000ECAC
0x18000ed1e  cmp     [rcx], dx
0x18000ed21  jnz     short loc_18000ED79
0x18000ed23  movzx   eax, word ptr [rbx+6]
0x18000ed27  sub     ax, 30h ; '0'
0x18000ed2b  cmp     ax, 9
0x18000ed2f  ja      short loc_18000ED79
0x18000ed31  sub     rbx, [rsp+1A0h+var_158]
0x18000ed36  mov     [rsp+1A0h+var_150], rcx
0x18000ed3b  mov     rdx, r14; struct _EVENTLOGRECORD *
0x18000ed3e  lea     rcx, [rsp+1A0h+var_158]; unsigned __int16 **
0x18000ed43  call    ?ReplaceStringInsert@@YAJPEAUSDescriptionStr@@PEAU_EVENTLOGRECORD@@@Z; ReplaceStringInsert(SDescriptionStr *,_EVENTLOGRECORD *)
0x18000ed48  xor     esi, esi
0x18000ed4a  test    eax, eax
0x18000ed4c  jns     short loc_18000ED58
0x18000ed4e  mov     rbx, [rsp+1A0h+var_150]
0x18000ed53  jmp     loc_18000EC5D
0x18000ed58  sar     rbx, 1
0x18000ed5b  movsxd  rcx, ebx
0x18000ed5e  mov     rax, [rsp+1A0h+var_158]
0x18000ed63  lea     rbx, [rax+rcx*2]
0x18000ed67  inc     r13d
0x18000ed6a  cmp     r13d, 64h ; 'd'
0x18000ed6e  jnb     loc_18000F03F
0x18000ed74  jmp     loc_18000EC5D
0x18000ed79  add     rbx, 2
0x18000ed7d  jmp     loc_18000F00A
0x18000ed82  cmp     word ptr [rsi], 7Bh ; '{'
0x18000ed86  jnz     loc_18000F007
0x18000ed8c  lea     r14, [rbx+4]
0x18000ed90  mov     edx, 7Dh ; '}'; Ch
0x18000ed95  mov     rcx, r14; Str
0x18000ed98  cmp     word ptr [r14], 53h ; 'S'
0x18000ed9d  jz      loc_18000EEB2
0x18000eda3  call    cs:__imp_wcschr
0x18000eda9  mov     r14, rax
0x18000edac  test    rax, rax
0x18000edaf  jnz     short loc_18000EDBB
0x18000edb1  mov     rbx, rsi
0x18000edb4  xor     esi, esi
0x18000edb6  jmp     loc_18000EF34
0x18000edbb  mov     r8, r14
0x18000edbe  sub     r8, rbx
0x18000edc1  sar     r8, 1
0x18000edc4  mov     rdx, rsi
0x18000edc7  lea     rcx, [rbp+0A0h+StringSid]
0x18000edcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG_K@Z; std::wstring::wstring(ushort const *,unsigned __int64)
0x18000edd0  nop
0x18000edd1  xor     esi, esi
0x18000edd3  test    r15, r15
0x18000edd6  jz      short loc_18000EDEA
0x18000edd8  mov     rdx, r15
0x18000eddb  lea     rcx, [rbp+0A0h+var_90]
0x18000eddf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000ede4  nop
0x18000ede5  or      edi, 1
0x18000ede8  jmp     short loc_18000EDF7
0x18000edea  lea     rcx, [rbp+0A0h+var_70]
0x18000edee  call    ?GetComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetComputerNameAsString(void)
0x18000edf3  nop
0x18000edf4  or      edi, 2
0x18000edf7  mov     [rsp+1A0h+var_160], edi
0x18000edfb  lea     r8, [rbp+0A0h+StringSid]
0x18000edff  mov     rdx, rax
0x18000ee02  lea     rcx, [rbp+0A0h+var_D0]
0x18000ee06  call    ?GetMappedGUID@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@0@Z; GetMappedGUID(std::wstring const &,std::wstring const &)
0x18000ee0b  nop
0x18000ee0c  test    dil, 2
0x18000ee10  jz      short loc_18000EE28
0x18000ee12  and     edi, 0FFFFFFFDh
0x18000ee15  mov     [rsp+1A0h+var_160], edi
0x18000ee19  xor     r8d, r8d
0x18000ee1c  mov     dl, 1
0x18000ee1e  lea     rcx, [rbp+0A0h+var_70]
0x18000ee22  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ee27  nop
0x18000ee28  test    dil, 1
0x18000ee2c  jz      short loc_18000EE43
0x18000ee2e  and     edi, 0FFFFFFFEh
0x18000ee31  mov     [rsp+1A0h+var_160], edi
0x18000ee35  xor     r8d, r8d
0x18000ee38  mov     dl, 1
0x18000ee3a  lea     rcx, [rbp+0A0h+var_90]
0x18000ee3e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ee43  cmp     [rbp+0A0h+var_C0], rsi
0x18000ee47  jnz     short loc_18000EE4E
0x18000ee49  mov     rbx, r14
0x18000ee4c  jmp     short loc_18000EE90
0x18000ee4e  lea     r9, [r14+2]; unsigned __int16 *
0x18000ee52  lea     rcx, [rbp+0A0h+var_D0]
0x18000ee56  cmp     [rbp+0A0h+var_B8], 8
0x18000ee5b  cmovnb  rcx, [rbp+0A0h+var_D0]; unsigned __int16 *
0x18000ee60  lea     rax, [rsp+1A0h+var_144]
0x18000ee65  mov     [rsp+1A0h+var_178], rax; unsigned int *
0x18000ee6a  lea     rax, [rsp+1A0h+var_148]
0x18000ee6f  mov     [rsp+1A0h+var_180], rax; unsigned int *
0x18000ee74  lea     r8, [rsp+1A0h+var_150]; unsigned __int16 **
0x18000ee79  lea     rdx, [rsp+1A0h+var_158]; unsigned __int16 **
0x18000ee7e  call    ?ReplaceSubStr@@YAJPEBGPEAPEAG10PEAK2@Z; ReplaceSubStr(ushort const *,ushort * *,ushort * *,ushort const *,ulong *,ulong *)
0x18000ee83  test    eax, eax
0x18000ee85  js      loc_18000F011
0x18000ee8b  mov     rbx, [rsp+1A0h+var_150]
0x18000ee90  xor     r8d, r8d
0x18000ee93  mov     dl, 1
0x18000ee95  lea     rcx, [rbp+0A0h+var_D0]
0x18000ee99  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ee9e  nop
0x18000ee9f  xor     r8d, r8d
0x18000eea2  mov     dl, 1
0x18000eea4  lea     rcx, [rbp+0A0h+StringSid]
0x18000eea8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000eead  jmp     loc_18000EF34
0x18000eeb2  call    cs:__imp_wcschr
0x18000eeb8  mov     r15, rax
0x18000eebb  test    rax, rax
0x18000eebe  jnz     short loc_18000EEC7
0x18000eec0  mov     rbx, rsi
0x18000eec3  xor     esi, esi
0x18000eec5  jmp     short loc_18000EF2F
0x18000eec7  mov     r8, r15
0x18000eeca  sub     r8, rbx
0x18000eecd  sar     r8, 1
0x18000eed0  sub     r8, 2
0x18000eed4  mov     rdx, r14
0x18000eed7  lea     rcx, [rbp+0A0h+StringSid]
0x18000eedb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG_K@Z; std::wstring::wstring(ushort const *,unsigned __int64)
0x18000eee0  nop
0x18000eee1  lea     rcx, [rbp+0A0h+var_D0]
0x18000eee5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000eeea  nop
0x18000eeeb  xor     esi, esi
0x18000eeed  mov     [rsp+1A0h+Sid], rsi
0x18000eef2  lea     rcx, [rbp+0A0h+StringSid]
0x18000eef6  cmp     [rbp+0A0h+var_98], 8
0x18000eefb  cmovnb  rcx, [rbp+0A0h+StringSid]; StringSid
0x18000ef00  lea     rdx, [rsp+1A0h+Sid]; Sid
0x18000ef05  call    cs:__imp_ConvertStringSidToSidW
0x18000ef0b  test    eax, eax
0x18000ef0d  jnz     short loc_18000EF3E
0x18000ef0f  mov     rbx, r15
0x18000ef12  xor     r8d, r8d
0x18000ef15  mov     dl, 1
0x18000ef17  lea     rcx, [rbp+0A0h+var_D0]
0x18000ef1b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ef20  nop
0x18000ef21  xor     r8d, r8d
0x18000ef24  mov     dl, 1
0x18000ef26  lea     rcx, [rbp+0A0h+StringSid]
0x18000ef2a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ef2f  mov     r15, [rsp+1A0h+var_138]
0x18000ef34  mov     r14, [rsp+1A0h+var_140]
0x18000ef39  jmp     loc_18000EC5D
0x18000ef3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ef42  mov     r14, [rsp+1A0h+var_140]
0x18000ef47  inc     rax
0x18000ef4a  cmp     [r14+rax*2+38h], si
0x18000ef50  jnz     short loc_18000EF47
0x18000ef52  add     rax, 1Dh
0x18000ef56  lea     rdx, [r14+rax*2]; unsigned __int16 *
0x18000ef5a  mov     r9, [rsp+1A0h+Sid]; void *
0x18000ef5f  mov     r8, [rsp+1A0h+var_138]; unsigned __int16 *
0x18000ef64  lea     rcx, [rbp+0A0h+var_90]; unsigned __int16 *
0x18000ef68  call    ?GetMappedSID@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0QEAX@Z; GetMappedSID(ushort const *,ushort const *,void * const)
0x18000ef6d  mov     rdx, rax
0x18000ef70  lea     rcx, [rbp+0A0h+var_D0]
0x18000ef74  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ef79  xor     r8d, r8d
0x18000ef7c  mov     dl, 1
0x18000ef7e  lea     rcx, [rbp+0A0h+var_90]
0x18000ef82  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ef87  mov     rcx, [rsp+1A0h+Sid]; hMem
0x18000ef8c  call    cs:__imp_LocalFree
0x18000ef92  mov     [rsp+1A0h+Sid], rsi
0x18000ef97  cmp     [rbp+0A0h+var_C0], rsi
0x18000ef9b  jnz     short loc_18000EFA2
0x18000ef9d  mov     rbx, r15
0x18000efa0  jmp     short loc_18000EFE0
0x18000efa2  lea     r9, [r15+2]; unsigned __int16 *
  ... truncated ...
```
