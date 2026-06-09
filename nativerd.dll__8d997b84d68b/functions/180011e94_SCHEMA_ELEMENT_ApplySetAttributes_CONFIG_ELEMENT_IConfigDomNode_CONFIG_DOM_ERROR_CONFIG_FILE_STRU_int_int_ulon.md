# SCHEMA_ELEMENT::ApplySetAttributes(CONFIG_ELEMENT *,IConfigDomNode *,CONFIG_DOM_ERROR *,CONFIG_FILE *,STRU *,int *,int *,ulong)

- ea: `0x180011e94`
- end: `0x1800124b4`
- name: `?ApplySetAttributes@SCHEMA_ELEMENT@@AEAAJPEAVCONFIG_ELEMENT@@PEAVIConfigDomNode@@PEAVCONFIG_DOM_ERROR@@PEAVCONFIG_FILE@@PEAVSTRU@@PEAH5K@Z`
- size: `1568`
- prototype: `__int64 __fastcall(SCHEMA_ELEMENT *this, struct CONFIG_ELEMENT *, struct IConfigDomNode *, struct CONFIG_DOM_ERROR *, struct CONFIG_FILE *, struct STRU *, int *, int *, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180013138`

## callees

- `0x18000b8cc`
- `0x180011af8`
- `0x180011e94`
- `0x1800124bc`
- `0x180012fec`
- `0x18001a118`
- `0x18001bc1c`
- `0x18001c250`
- `0x18001d160`
- `0x18001d2fc`
- `0x18001d604`
- `0x18004acd8`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180011fcd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011fd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011fe1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011fcd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011fd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011fe1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800120c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012119`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001217e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800123f6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012417`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800120c2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012119`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001217e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800123f6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180012417`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800120a3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800120a3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011f2f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011f55`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011f8c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011f2f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011f55`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011f8c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800122a3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800122a3`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012229`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012479`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012229`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180012479`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18001234d`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180012398`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18001234d`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180012398`

## pseudocode

```c
__int64 __fastcall SCHEMA_ELEMENT::ApplySetAttributes(
        SCHEMA_ELEMENT *this,
        struct CONFIG_ELEMENT *a2,
        struct IConfigDomNode *a3,
        struct CONFIG_DOM_ERROR *a4,
        struct CONFIG_FILE *a5,
        struct STRU *a6,
        int *a7,
        int *a8,
        char a9)
{
  int v12; // ebx
  struct ATTRIBUTE_VALUE *v13; // rax
  struct ATTRIBUTE_VALUE *v14; // rdi
  int *v16; // rdi
  unsigned int v17; // ecx
  char *v18; // r14
  unsigned int v19; // r13d
  unsigned __int16 i; // r12
  SCHEMA_ELEMENT *v21; // r15
  const WCHAR *v22; // rbx
  __int64 v23; // r15
  char *v24; // rax
  int v25; // ecx
  int v26; // edx
  __int64 v27; // rax
  const WCHAR *v28; // rax
  wchar_t *v29; // rax
  wchar_t *Str; // rax
  int v31; // ebx
  char *v32; // rax
  const unsigned __int16 *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const WCHAR **v36; // rdx
  unsigned int v37; // r9d
  int v38; // edx
  wchar_t *v39; // rax
  __int64 v40; // rcx
  char *v41; // rax
  struct VALIDATION_EXCEPTION *v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v44; // [rsp+4Ch] [rbp-B4h] BYREF
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+54h] [rbp-ACh]
  CONFIG_DOM_ERROR *v47; // [rsp+58h] [rbp-A8h]
  char *v48[2]; // [rsp+60h] [rbp-A0h] BYREF
  SCHEMA_ELEMENT *v49; // [rsp+70h] [rbp-90h]
  struct CONFIG_FILE *v50; // [rsp+78h] [rbp-88h]
  int *v51; // [rsp+80h] [rbp-80h]
  STRU *v52; // [rsp+88h] [rbp-78h]
  int *v53; // [rsp+90h] [rbp-70h]
  CONFIG_ELEMENT *v54; // [rsp+98h] [rbp-68h]
  _BYTE v55[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v56[56]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v57[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v58[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v59[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v60[64]; // [rsp+250h] [rbp+150h] BYREF

  v54 = a2;
  v49 = this;
  v50 = a5;
  v52 = a6;
  v53 = a7;
  v51 = a8;
  v47 = a4;
  v44 = 0;
  memset_0(v58, 0, sizeof(v58));
  STRU::STRU((STRU *)v55, v58, 0x40u);
  memset_0(v59, 0, sizeof(v59));
  STRU::STRU((STRU *)v56, v59, 0x40u);
  v42 = 0;
  *(_OWORD *)v48 = 0;
  memset_0(v60, 0, sizeof(v60));
  STRU::STRU((STRU *)v57, v60, 0x40u);
  v43 = 0;
  v45 = 0;
  if ( a2 && a3 && a4 && a5 && a6 && a7 && (v16 = v51) != 0 )
  {
    v12 = (*(__int64 (__fastcall **)(struct IConfigDomNode *, unsigned int *))(*(_QWORD *)a3 + 48LL))(a3, &v44);
    if ( v12 >= 0 )
    {
      v17 = 0;
      v18 = (char *)&szDomain;
      v19 = -1073739080;
      while ( 2 )
      {
        v46 = v17;
        if ( v17 < v44 )
        {
          v12 = (*(__int64 (__fastcall **)(struct IConfigDomNode *, _QWORD, _BYTE *, _BYTE *))(*(_QWORD *)a3 + 32LL))(
                  a3,
                  v17,
                  v55,
                  v56);
          if ( v12 >= 0 )
          {
            for ( i = 0; ; ++i )
            {
              v21 = v49;
              if ( i >= *((_WORD *)v49 + 16) )
                goto LABEL_32;
              v22 = &szDomain;
              v23 = *((_QWORD *)BUFFER::QueryPtr((SCHEMA_ELEMENT *)((char *)v49 + 40)) + i);
              if ( *(_QWORD *)(v23 + 24) )
                v22 = *(const WCHAR **)(v23 + 24);
              v24 = (char *)((char *)STRU::QueryStr((STRU *)v55) - (char *)v22);
              do
              {
                v25 = *(unsigned __int16 *)&v24[(_QWORD)v22];
                v26 = *v22 - v25;
                if ( v26 )
                  break;
                ++v22;
              }
              while ( v25 );
              if ( !v26 )
                break;
            }
            v27 = *(_QWORD *)(v23 + 56);
            if ( !v27 || SMALL_STRU::IsEmpty((SMALL_STRU *)(v27 + 8)) )
              goto LABEL_26;
            v28 = &szDomain;
            if ( *v36 )
              v28 = *v36;
            if ( !v28 )
            {
LABEL_26:
              if ( v23 )
              {
                v13 = (struct ATTRIBUTE_VALUE *)operator new(0x20u);
                v14 = v13;
                if ( !v13 )
                {
                  v12 = -2147024888;
                  break;
                }
                *(_QWORD *)v13 = 1;
                *((_QWORD *)v13 + 1) = 0;
                *((_QWORD *)v13 + 3) = 0;
                v43 = 0;
                Str = STRU::QueryStr((STRU *)v56);
                v12 = SCHEMA_ATTRIBUTE::CopyString(
                        (SCHEMA_ATTRIBUTE *)v23,
                        Str,
                        v14,
                        (const unsigned __int16 **)v50,
                        &v42,
                        a9,
                        &v43);
                if ( v12 < 0 )
                {
                  v40 = *(_QWORD *)(v23 + 24);
                  if ( v43 )
                  {
                    v19 = -1073739035;
                    if ( v40 )
                      v18 = *(char **)(v23 + 24);
                    v48[0] = v18;
                    if ( v12 != -2146893802 )
                      v19 = -1073739091;
                  }
                  else
                  {
                    v41 = (char *)&szDomain;
                    if ( v40 )
                      v41 = *(char **)(v23 + 24);
                    v48[0] = v41;
                    if ( v42 )
                      v48[1] = (char *)STRU::QueryStr((struct VALIDATION_EXCEPTION *)((char *)v42 + 208));
                    else
                      v48[1] = (char *)&szDomain;
                  }
                  CONFIG_DOM_ERROR::SetNodeError(v47, v12, a3, v19, (const char **const)v48);
                }
                else
                {
                  v31 = 0;
                  if ( !v42 )
                    goto LABEL_39;
                  v32 = (char *)&szDomain;
                  if ( *(_QWORD *)(v23 + 24) )
                    v32 = *(char **)(v23 + 24);
                  v48[0] = v32;
                  v12 = -2147024883;
                  v48[1] = (char *)STRU::QueryStr((struct VALIDATION_EXCEPTION *)((char *)v42 + 208));
                  CONFIG_DOM_ERROR::SetNodeError(v47, -2147024883, a3, 0xC0000AB8, (const char **const)v48);
                  if ( (*(_BYTE *)(v23 + 20) & 1) == 0 && (*(_BYTE *)(v23 + 20) & 2) == 0 )
                  {
                    v12 = ATTRIBUTE_VALUE::Copy(v14, *(struct ATTRIBUTE_VALUE **)(v23 + 32));
                    if ( v12 >= 0 )
                    {
                      v33 = &szDomain;
                      v34 = *((_QWORD *)v47 + 1);
                      if ( *(_QWORD *)(v34 + 32) )
                        v33 = *(const unsigned __int16 **)(v34 + 32);
                      STRU::Copy((struct VALIDATION_EXCEPTION *)((char *)v42 + 152), v33);
                      v35 = (*(__int64 (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)a3 + 56LL))(a3);
                      *((_DWORD *)v42 + 9) = v35;
                      (*(void (__fastcall **)(struct IConfigDomNode *, char *, char *, char *))(*(_QWORD *)a3 + 64LL))(
                        a3,
                        (char *)v42 + 320,
                        (char *)v42 + 376,
                        (char *)v42 + 432);
                      ATTRIBUTE_VALUE::SetException(v14, v42);
                      v31 = 1;
                      VALIDATION_EXCEPTION::DereferenceValidationException(v42);
                      v42 = 0;
LABEL_39:
                      v12 = CONFIG_ELEMENT::SetAttributeValue(v54, i, v14, v31, 0, 1, 0);
                      if ( v12 >= 0 )
                      {
                        ATTRIBUTE_VALUE::DereferenceAttributeValue(v14);
                        v16 = v51;
                        goto LABEL_36;
                      }
                    }
                  }
                }
                ATTRIBUTE_VALUE::DereferenceAttributeValue(v14);
                break;
              }
            }
            v21 = v49;
LABEL_32:
            v29 = STRU::QueryStr((STRU *)v55);
            v12 = SCHEMA_ELEMENT::ConvertStringToBuiltInAttribute(v29, (enum BUILT_IN_ATTRIBUTE *)&v45);
            if ( v12 < 0 )
              break;
            switch ( v45 )
            {
              case 1:
                if ( (*((_DWORD *)v50 + 68) & 0x3C0) == 0xC0 )
                  goto LABEL_61;
                v12 = STRU::Copy(v52, (const struct STRU *)v56);
                if ( v12 >= 0 )
                {
                  *v53 = 0;
                  *v16 = 0;
                  goto LABEL_36;
                }
                break;
              case 2:
                if ( (*((_DWORD *)v50 + 68) & 0x3C0) != 0xC0 || (*((_BYTE *)v21 + 20) & 8) == 0 )
                  goto LABEL_61;
                v12 = STRU::Copy(v52, (const struct STRU *)v56);
                if ( v12 >= 0 )
                {
                  *v53 = 1;
                  *v16 = 1;
                  goto LABEL_36;
                }
                break;
              case 3:
LABEL_36:
                v17 = v46 + 1;
                continue;
              case 4:
                v12 = -2147024846;
                v37 = -1073739025;
                v38 = -2147024846;
LABEL_60:
                CONFIG_DOM_ERROR::SetNodeError(v47, v38, a3, v37, (const char **const)v48);
                goto LABEL_5;
              default:
LABEL_61:
                if ( (a9 & 4) != 0 )
                  goto LABEL_36;
                v39 = STRU::QueryStr((STRU *)v55);
                if ( (unsigned int)LOCKING_ATTRIBUTES::IsLockingAttribute(v39) )
                  goto LABEL_36;
                v12 = -2147024883;
                v48[0] = (char *)STRU::QueryStr((STRU *)v55);
                v37 = -1073739120;
                v38 = -2147024883;
                goto LABEL_60;
            }
          }
        }
        break;
      }
    }
  }
  else
  {
    v12 = -2147024809;
  }
LABEL_5:
  STRU::~STRU((STRU *)v57);
  STRU::~STRU((STRU *)v56);
  STRU::~STRU((STRU *)v55);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180011e94  push    rbp
0x180011e96  push    rbx
0x180011e97  push    rsi
0x180011e98  push    rdi
0x180011e99  push    r12
0x180011e9b  push    r13
0x180011e9d  push    r14
0x180011e9f  push    r15
0x180011ea1  lea     rbp, [rsp-1E8h]
0x180011ea9  sub     rsp, 2E8h
0x180011eb0  mov     rax, cs:__security_cookie
0x180011eb7  xor     rax, rsp
0x180011eba  mov     [rbp+220h+var_50], rax
0x180011ec1  mov     rax, [rbp+220h+arg_38]
0x180011ec8  mov     rsi, r8
0x180011ecb  mov     r15, [rbp+220h+arg_20]
0x180011ed2  mov     r12, rdx
0x180011ed5  mov     r14, [rbp+220h+arg_28]
0x180011edc  mov     r8d, 80h; Size
0x180011ee2  mov     rbx, [rbp+220h+arg_30]
0x180011ee9  mov     rdi, r9
0x180011eec  mov     [rbp+220h+var_288], rdx
0x180011ef0  xor     edx, edx; Val
0x180011ef2  mov     [rsp+320h+var_2B0], rcx
0x180011ef7  lea     rcx, [rbp+220h+var_1D0]; void *
0x180011efb  mov     [rsp+320h+var_2A8], r15
0x180011f00  mov     [rbp+220h+var_298], r14
0x180011f04  mov     [rbp+220h+var_290], rbx
0x180011f08  mov     [rbp+220h+var_2A0], rax
0x180011f0c  mov     [rsp+320h+var_2C8], r9
0x180011f11  mov     [rsp+320h+var_2D4], 0
0x180011f19  call    memset_0
0x180011f1e  mov     r13d, 40h ; '@'
0x180011f24  lea     rdx, [rbp+220h+var_1D0]
0x180011f28  mov     r8d, r13d
0x180011f2b  lea     rcx, [rbp+220h+var_280]
0x180011f2f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011f35  xor     edx, edx; Val
0x180011f37  lea     r8d, [r13+40h]; Size
0x180011f3b  lea     rcx, [rbp+220h+var_150]; void *
0x180011f42  call    memset_0
0x180011f47  mov     r8d, r13d
0x180011f4a  lea     rdx, [rbp+220h+var_150]
0x180011f51  lea     rcx, [rbp+220h+var_248]
0x180011f55  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011f5b  xorps   xmm0, xmm0
0x180011f5e  mov     [rsp+320h+var_2E0], 0
0x180011f67  xor     edx, edx; Val
0x180011f69  lea     r8d, [r13+40h]; Size
0x180011f6d  lea     rcx, [rbp+220h+var_D0]; void *
0x180011f74  movups  xmmword ptr [rsp+320h+var_2C0], xmm0
0x180011f79  call    memset_0
0x180011f7e  mov     r8d, r13d
0x180011f81  lea     rdx, [rbp+220h+var_D0]
0x180011f88  lea     rcx, [rbp+220h+var_210]
0x180011f8c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011f92  mov     [rsp+320h+var_2D8], 0
0x180011f9a  mov     [rsp+320h+var_2D0], 0
0x180011fa2  test    r12, r12
0x180011fa5  jnz     short loc_18001200C
0x180011fa7  mov     ebx, 80070057h
0x180011fac  jmp     short loc_180011FC9
0x180011fae  mov     ecx, 20h ; ' '; Size
0x180011fb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011fb8  mov     rdi, rax
0x180011fbb  test    rax, rax
0x180011fbe  jnz     loc_180012167
0x180011fc4  mov     ebx, 80070008h
0x180011fc9  lea     rcx, [rbp+220h+var_210]
0x180011fcd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011fd3  lea     rcx, [rbp+220h+var_248]
0x180011fd7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011fdd  lea     rcx, [rbp+220h+var_280]
0x180011fe1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011fe7  mov     eax, ebx
0x180011fe9  mov     rcx, [rbp+220h+var_50]
0x180011ff0  xor     rcx, rsp; StackCookie
0x180011ff3  call    __security_check_cookie
0x180011ff8  add     rsp, 2E8h
0x180011fff  pop     r15
0x180012001  pop     r14
0x180012003  pop     r13
0x180012005  pop     r12
0x180012007  pop     rdi
0x180012008  pop     rsi
0x180012009  pop     rbx
0x18001200a  pop     rbp
0x18001200b  retn
0x18001200c  test    rsi, rsi
0x18001200f  jz      short loc_180011FA7
0x180012011  test    rdi, rdi
0x180012014  jz      short loc_180011FA7
0x180012016  test    r15, r15
0x180012019  jz      short loc_180011FA7
0x18001201b  test    r14, r14
0x18001201e  jz      short loc_180011FA7
0x180012020  test    rbx, rbx
0x180012023  jz      short loc_180011FA7
0x180012025  mov     rdi, [rbp+220h+var_2A0]
0x180012029  test    rdi, rdi
0x18001202c  jz      loc_180011FA7
0x180012032  mov     rax, [rsi]
0x180012035  lea     rdx, [rsp+320h+var_2D4]
0x18001203a  mov     rcx, rsi
0x18001203d  mov     rax, [rax+30h]
0x180012041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012046  mov     ebx, eax
0x180012048  test    eax, eax
0x18001204a  js      loc_180011FC9
0x180012050  xor     ecx, ecx
0x180012052  lea     r14, szDomain
0x180012059  mov     r13d, 0C0000AB8h
0x18001205f  mov     [rsp+320h+var_2CC], ecx
0x180012063  cmp     ecx, [rsp+320h+var_2D4]
0x180012067  jnb     loc_180011FC9
0x18001206d  mov     rax, [rsi]
0x180012070  lea     r9, [rbp+220h+var_248]
0x180012074  mov     edx, ecx
0x180012076  lea     r8, [rbp+220h+var_280]
0x18001207a  mov     rcx, rsi
0x18001207d  mov     rax, [rax+20h]
0x180012081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012086  mov     ebx, eax
0x180012088  test    eax, eax
0x18001208a  js      loc_180011FC9
0x180012090  xor     r12d, r12d
0x180012093  mov     r15, [rsp+320h+var_2B0]
0x180012098  cmp     r12w, [r15+20h]
0x18001209d  jnb     short loc_180012115
0x18001209f  lea     rcx, [r15+28h]
0x1800120a3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800120a9  movzx   ecx, r12w
0x1800120ad  mov     rbx, r14
0x1800120b0  mov     r15, [rax+rcx*8]
0x1800120b4  lea     rcx, [rbp+220h+var_280]
0x1800120b8  cmp     qword ptr [r15+18h], 0
0x1800120bd  cmovnz  rbx, [r15+18h]
0x1800120c2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800120c8  sub     rax, rbx
0x1800120cb  movzx   edx, word ptr [rbx]
0x1800120ce  movzx   ecx, word ptr [rbx+rax]
0x1800120d2  sub     edx, ecx
0x1800120d4  jnz     short loc_1800120DE
0x1800120d6  add     rbx, 2
0x1800120da  test    ecx, ecx
0x1800120dc  jnz     short loc_1800120CB
0x1800120de  xor     ebx, ebx
0x1800120e0  test    edx, edx
0x1800120e2  jz      short loc_1800120EA
0x1800120e4  inc     r12w
0x1800120e8  jmp     short loc_180012093
0x1800120ea  mov     rax, [r15+38h]
0x1800120ee  test    rax, rax
0x1800120f1  jnz     loc_180012311
0x1800120f7  test    r15, r15
0x1800120fa  jz      short loc_180012110
0x1800120fc  jmp     loc_180011FAE
0x180012101  cmp     [rdx], rbx
0x180012104  mov     rax, r14
0x180012107  cmovnz  rax, [rdx]
0x18001210b  test    rax, rax
0x18001210e  jz      short loc_1800120F7
0x180012110  mov     r15, [rsp+320h+var_2B0]
0x180012115  lea     rcx, [rbp+220h+var_280]
0x180012119  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001211f  mov     rcx, rax; String1
0x180012122  lea     rdx, [rsp+320h+var_2D0]; enum BUILT_IN_ATTRIBUTE *
0x180012127  call    ?ConvertStringToBuiltInAttribute@SCHEMA_ELEMENT@@CAJPEBGPEAW4BUILT_IN_ATTRIBUTE@@@Z; SCHEMA_ELEMENT::ConvertStringToBuiltInAttribute(ushort const *,BUILT_IN_ATTRIBUTE *)
0x18001212c  mov     ebx, eax
0x18001212e  test    eax, eax
0x180012130  js      loc_180011FC9
0x180012136  mov     eax, [rsp+320h+var_2D0]
0x18001213a  mov     r12d, 1
0x180012140  cmp     eax, r12d
0x180012143  jz      loc_18001232A
0x180012149  cmp     eax, 2
0x18001214c  jz      loc_180012372
0x180012152  cmp     eax, 3
0x180012155  jnz     loc_1800123B7
0x18001215b  mov     ecx, [rsp+320h+var_2CC]
0x18001215f  add     ecx, r12d
0x180012162  jmp     loc_18001205F
0x180012167  mov     qword ptr [rax], 1
0x18001216e  lea     rcx, [rbp+220h+var_248]
0x180012172  mov     [rax+8], rbx
0x180012176  mov     [rax+18h], rbx
0x18001217a  mov     [rsp+320h+var_2D8], ebx
0x18001217e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180012184  mov     r9, [rsp+320h+var_2A8]; struct CONFIG_FILE *
0x180012189  mov     r8, rdi; struct ATTRIBUTE_VALUE *
0x18001218c  mov     rdx, rax; String1
0x18001218f  mov     rcx, r15; this
0x180012192  lea     rax, [rsp+320h+var_2D8]
0x180012197  mov     [rsp+320h+var_2F0], rax; int *
0x18001219c  mov     eax, [rbp+220h+arg_40]
0x1800121a2  mov     [rsp+320h+var_2F8], eax; unsigned int
0x1800121a6  lea     rax, [rsp+320h+var_2E0]
0x1800121ab  mov     [rsp+320h+var_300], rax; struct VALIDATION_EXCEPTION **
0x1800121b0  call    ?CopyString@SCHEMA_ATTRIBUTE@@QEAAJPEBGPEAVATTRIBUTE_VALUE@@PEAVCONFIG_FILE@@PEAPEAVVALIDATION_EXCEPTION@@KPEAH@Z; SCHEMA_ATTRIBUTE::CopyString(ushort const *,ATTRIBUTE_VALUE *,CONFIG_FILE *,VALIDATION_EXCEPTION * *,ulong,int *)
0x1800121b5  xor     edx, edx
0x1800121b7  mov     ebx, eax
0x1800121b9  test    eax, eax
0x1800121bb  js      loc_18001242C
0x1800121c1  mov     rcx, [rsp+320h+var_2E0]
0x1800121c6  mov     ebx, edx
0x1800121c8  test    rcx, rcx
0x1800121cb  jnz     short loc_180012211
0x1800121cd  mov     rcx, [rbp+220h+var_288]; this
0x1800121d1  mov     r9d, ebx; int
0x1800121d4  mov     dword ptr [rsp+320h+var_2F0], edx; int
0x1800121d8  mov     r8, rdi; struct ATTRIBUTE_VALUE *
0x1800121db  mov     [rsp+320h+var_2F8], 1; int
0x1800121e3  mov     dword ptr [rsp+320h+var_300], edx; int
0x1800121e7  movzx   edx, r12w; unsigned __int16
0x1800121eb  call    ?SetAttributeValue@CONFIG_ELEMENT@@QEAAJGPEAVATTRIBUTE_VALUE@@HHHH@Z; CONFIG_ELEMENT::SetAttributeValue(ushort,ATTRIBUTE_VALUE *,int,int,int,int)
0x1800121f0  mov     ebx, eax
0x1800121f2  test    eax, eax
0x1800121f4  js      loc_1800124A7
0x1800121fa  mov     rcx, rdi; this
0x1800121fd  call    ?DereferenceAttributeValue@ATTRIBUTE_VALUE@@QEBAXXZ; ATTRIBUTE_VALUE::DereferenceAttributeValue(void)
0x180012202  mov     rdi, [rbp+220h+var_2A0]
0x180012206  mov     r12d, 1
0x18001220c  jmp     loc_18001215B
0x180012211  cmp     [r15+18h], rdx
0x180012215  mov     rax, r14
0x180012218  cmovnz  rax, [r15+18h]
0x18001221d  add     rcx, 0D0h
0x180012224  mov     [rsp+320h+var_2C0], rax
0x180012229  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001222f  mov     rcx, [rsp+320h+var_2C8]; this
0x180012234  mov     ebx, 8007000Dh
0x180012239  mov     [rsp+320h+var_2C0+8], rax
0x18001223e  mov     r9d, r13d; unsigned int
0x180012241  lea     rax, [rsp+320h+var_2C0]
0x180012246  mov     r8, rsi; struct IConfigDomNode *
0x180012249  mov     edx, ebx; int
0x18001224b  mov     [rsp+320h+var_300], rax; char **
0x180012250  call    ?SetNodeError@CONFIG_DOM_ERROR@@QEAAJJPEAVIConfigDomNode@@KQEAPEBD@Z; CONFIG_DOM_ERROR::SetNodeError(long,IConfigDomNode *,ulong,char const * * const)
0x180012255  test    byte ptr [r15+14h], 1
0x18001225a  jnz     loc_1800124A7
0x180012260  test    byte ptr [r15+14h], 2
0x180012265  jnz     loc_1800124A7
0x18001226b  mov     rdx, [r15+20h]; struct ATTRIBUTE_VALUE *
0x18001226f  mov     rcx, rdi; this
0x180012272  call    ?Copy@ATTRIBUTE_VALUE@@QEAAJPEAV1@@Z; ATTRIBUTE_VALUE::Copy(ATTRIBUTE_VALUE *)
0x180012277  mov     ebx, eax
0x180012279  test    eax, eax
0x18001227b  js      loc_1800124A7
0x180012281  mov     rcx, [rsp+320h+var_2E0]
0x180012286  mov     rdx, r14
0x180012289  mov     rax, [rsp+320h+var_2C8]
0x18001228e  mov     rax, [rax+8]
0x180012292  cmp     qword ptr [rax+20h], 0
0x180012297  cmovnz  rdx, [rax+20h]
0x18001229c  add     rcx, 98h
0x1800122a3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800122a9  mov     rax, [rsi]
0x1800122ac  mov     rcx, rsi
0x1800122af  mov     rax, [rax+38h]
0x1800122b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b8  mov     rcx, [rsp+320h+var_2E0]
0x1800122bd  mov     [rcx+24h], eax
0x1800122c0  mov     rcx, rsi
0x1800122c3  mov     rdx, [rsp+320h+var_2E0]
0x1800122c8  mov     rax, [rsi]
0x1800122cb  lea     r9, [rdx+1B0h]
0x1800122d2  mov     rax, [rax+40h]
0x1800122d6  lea     r8, [rdx+178h]
0x1800122dd  add     rdx, 140h
0x1800122e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122e9  mov     rdx, [rsp+320h+var_2E0]; struct VALIDATION_EXCEPTION *
0x1800122ee  mov     rcx, rdi; this
0x1800122f1  call    ?SetException@ATTRIBUTE_VALUE@@QEAAXPEAVVALIDATION_EXCEPTION@@@Z; ATTRIBUTE_VALUE::SetException(VALIDATION_EXCEPTION *)
0x1800122f6  mov     rcx, [rsp+320h+var_2E0]; this
0x1800122fb  mov     ebx, 1
0x180012300  call    ?DereferenceValidationException@VALIDATION_EXCEPTION@@QEAAXXZ; VALIDATION_EXCEPTION::DereferenceValidationException(void)
0x180012305  xor     edx, edx
0x180012307  mov     [rsp+320h+var_2E0], rdx
0x18001230c  jmp     loc_1800121CD
0x180012311  lea     rdx, [rax+8]
0x180012315  mov     rcx, rdx; this
0x180012318  call    ?IsEmpty@SMALL_STRU@@QEBA_NXZ; SMALL_STRU::IsEmpty(void)
0x18001231d  test    al, al
0x18001231f  jnz     loc_1800120F7
0x180012325  jmp     loc_180012101
0x18001232a  mov     rax, [rsp+320h+var_2A8]
0x18001232f  mov     eax, [rax+110h]
0x180012335  and     eax, 3C0h
0x18001233a  cmp     eax, 0C0h
0x18001233f  jz      loc_1800123E5
0x180012345  mov     rcx, [rbp+220h+var_298]
0x180012349  lea     rdx, [rbp+220h+var_248]
0x18001234d  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180012353  mov     ebx, eax
0x180012355  test    eax, eax
0x180012357  js      loc_180011FC9
0x18001235d  mov     rax, [rbp+220h+var_290]
0x180012361  mov     dword ptr [rax], 0
0x180012367  mov     dword ptr [rdi], 0
0x18001236d  jmp     loc_18001215B
  ... truncated ...
```
