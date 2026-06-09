# CEXTLOG::LogCustomInformation(ulong,_CUSTOM_LOG_DATA *,char *)

- ea: `0x180005020`
- end: `0x18000538c`
- name: `?LogCustomInformation@CEXTLOG@@UEAAJKPEAU_CUSTOM_LOG_DATA@@PEAD@Z`
- size: `876`
- prototype: `__int64 __fastcall(CEXTLOG *__hidden this, unsigned int, struct _CUSTOM_LOG_DATA *, char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180003374`
- `0x180003d48`
- `0x180005020`
- `0x18000ec56`
- `0x18000ec62`
- `0x18000eca0`
- `0x18000ed30`

## import_xrefs

- `IisRTL!?Lock@TS_RESOURCE@@QEAAXW4TSRES_LOCK_TYPE@@@Z` at `0x18000509b`
- `IisRTL!?Lock@TS_RESOURCE@@QEAAXW4TSRES_LOCK_TYPE@@@Z` at `0x18000509b`
- `IisRTL!?Unlock@TS_RESOURCE@@QEAAXXZ` at `0x18000535a`
- `IisRTL!?Unlock@TS_RESOURCE@@QEAAXXZ` at `0x18000535a`
- `IisRTL!?SetSystemTime@EXTLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x18000518b`
- `IisRTL!?SetSystemTime@EXTLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x18000518b`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x180005320`
- `IisRTL!?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z` at `0x180005320`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x1800051a0`
- `IisRTL!?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z` at `0x1800051a0`
- `IisRTL!?Convert@TS_RESOURCE@@QEAAXW4TSRES_CONV_TYPE@@@Z` at `0x1800052ca`
- `IisRTL!?Convert@TS_RESOURCE@@QEAAXW4TSRES_CONV_TYPE@@@Z` at `0x1800052ca`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800050eb`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800050eb`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005300`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005300`
- `KERNEL32!GetLocalTime` at `0x18000532d`
- `KERNEL32!GetLocalTime` at `0x18000532d`

## pseudocode

```c
__int64 __fastcall CEXTLOG::LogCustomInformation(CEXTLOG *this, unsigned int a2, struct _CUSTOM_LOG_DATA *a3, char *a4)
{
  char *v6; // r15
  int v7; // r13d
  unsigned int v8; // ebx
  __int64 v9; // r14
  unsigned int v10; // eax
  _QWORD *v11; // r12
  int Key; // eax
  __int64 v13; // rcx
  char *v14; // rax
  signed __int64 v15; // rdx
  int v16; // r8d
  int v17; // r9d
  int v18; // r13d
  unsigned __int64 v19; // rcx
  char *v20; // rdi
  __int64 v21; // r12
  __int64 v22; // r15
  unsigned int v23; // edi
  __int64 v24; // rbx
  int v25; // r15d
  char *v26; // rdx
  __int64 v27; // r15
  unsigned int i; // ebx
  unsigned int v29; // eax
  ASCLOG_DATETIME_CACHE *v30; // rcx
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  struct _CUSTOM_LOG_DATA *v33; // [rsp+40h] [rbp-C0h]
  char *v34; // [rsp+48h] [rbp-B8h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v36[20]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+100h] [rbp+0h] BYREF
  void *v38[30]; // [rsp+150h] [rbp+50h] BYREF
  char Src[32]; // [rsp+240h] [rbp+140h] BYREF
  char v40[10240]; // [rsp+260h] [rbp+160h] BYREF

  v33 = a3;
  v34 = a4;
  v6 = a4;
  SystemTime = 0;
  memset_0(v36, 0, 0xF0u);
  memset_0(v38, 0, sizeof(v38));
  TS_RESOURCE::Lock((char *)this + 3144, 0);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( a2 )
  {
    v10 = a2;
    do
    {
      if ( (unsigned int)v9 >= 0x1E )
        break;
      v11 = &v36[v9];
      if ( v11 )
      {
        v32 = 0;
        Key = CLKRHashTable::FindKey((char *)this + 3240, *((_QWORD *)v33 + 2 * v8), &v32);
        v13 = v32;
        *v11 = v32;
        if ( !Key && *(_DWORD *)(v13 + 128) )
        {
          LOBYTE(Key) = v13 != *((_QWORD *)this + v9 + 363);
          v7 |= Key;
          v38[v9] = (void *)*((_QWORD *)v33 + 2 * v8 + 1);
          v9 = (unsigned int)(v9 + 1);
        }
        v10 = a2;
      }
      ++v8;
    }
    while ( v8 < v10 );
    v6 = v34;
  }
  if ( v6 )
  {
    v14 = (char *)*((_QWORD *)this + 359);
    v15 = v6 - v14;
    do
    {
      v16 = (unsigned __int8)v14[v15];
      v17 = (unsigned __int8)*v14 - v16;
      if ( v17 )
        break;
      ++v14;
    }
    while ( v16 );
    v18 = v7 | (*((_DWORD *)this + 724) != (_DWORD)v9) | (v17 != 0);
  }
  else
  {
    v18 = v7 | (*((_DWORD *)this + 724) != (_DWORD)v9);
  }
  EXTLOG_DATETIME_CACHE::SetSystemTime((CEXTLOG *)((char *)this + 1584), &SystemTime);
  CACHED_DATETIME_FORMATS::GetFormattedDateTime((CEXTLOG *)((char *)this + 1584), &SystemTime, Src);
  v20 = v40;
  if ( (*((_BYTE *)this + 1576) & 3) != 0 )
  {
    v21 = -1;
    v22 = -1;
    do
      ++v22;
    while ( Src[v22] );
    if ( (*((_BYTE *)this + 1576) & 1) != 0 )
    {
      if ( (unsigned int)v22 >= 0x2800 )
      {
LABEL_22:
        v23 = 0;
        goto LABEL_34;
      }
      v24 = (unsigned int)v22;
      memcpy_0(v40, Src, (unsigned int)v22);
      v25 = v22 + 1;
      v40[v24] = 32;
      v20 = &v40[v25];
    }
    else
    {
      v25 = v22 + 1;
    }
    if ( (*((_BYTE *)this + 1576) & 2) != 0 )
    {
      v26 = &Src[v25];
      do
        ++v21;
      while ( v26[v21] );
      if ( (unsigned int)v21 >= 0x2800 )
        goto LABEL_22;
      memcpy_0(v20, v26, (unsigned int)v21);
      v19 = (unsigned int)(v21 + 1);
      v20[(unsigned int)v21] = 32;
      v20 += v19;
    }
  }
  v27 = 0;
  for ( i = (unsigned int)&v37 + 10592 - (_DWORD)v20; (unsigned int)v27 < (unsigned int)v9; v27 = (unsigned int)(v27 + 1) )
  {
    v29 = CEXTLOG::ConvertDataToString((CEXTLOG *)v19, *(_DWORD *)(v36[v27] + 64LL), v38[v27], v20, i);
    if ( v29 > i )
      goto LABEL_22;
    v19 = v29;
    i -= v29;
    v20 += v29;
  }
  *(_WORD *)(v20 - 1) = 2573;
  v23 = (_DWORD)v20 - (unsigned int)v40 + 1;
LABEL_34:
  if ( v18 )
  {
    TS_RESOURCE::Convert((char *)this + 3144, 1);
    *((_DWORD *)this + 724) = v9;
    if ( (_DWORD)v9 )
      memcpy_0((char *)this + 2904, v36, 8LL * (unsigned int)v9);
    STR::Copy((CEXTLOG *)((char *)this + 2840), v34);
  }
  if ( *((_DWORD *)this + 395) )
  {
    v30 = (ASCLOG_DATETIME_CACHE *)*((_QWORD *)this + 332);
    if ( v30 )
      ASCLOG_DATETIME_CACHE::SetLocalTime(v30, &SystemTime);
    else
      GetLocalTime(&SystemTime);
  }
  CLogFileCtrl::WriteLogInformation(this, &SystemTime, v40, v23, 1, v18);
  TS_RESOURCE::Unlock((CEXTLOG *)((char *)this + 3144));
  return 0;
}

```

## disassembly

```asm
0x180005020  mov     [rsp-8+arg_8], rbx
0x180005025  push    rbp
0x180005026  push    rsi
0x180005027  push    rdi
0x180005028  push    r12
0x18000502a  push    r13
0x18000502c  push    r14
0x18000502e  push    r15
0x180005030  lea     rbp, [rsp-2980h]
0x180005038  mov     eax, 2A80h
0x18000503d  call    _alloca_probe
0x180005042  sub     rsp, rax
0x180005045  mov     rax, cs:__security_cookie
0x18000504c  xor     rax, rsp
0x18000504f  mov     [rbp+29B0h+var_40], rax
0x180005056  mov     [rsp+2AB0h+var_2A70], r8
0x18000505b  mov     edi, edx
0x18000505d  mov     rsi, rcx
0x180005060  mov     [rsp+2AB0h+var_2A68], r9
0x180005065  xorps   xmm0, xmm0
0x180005068  lea     rcx, [rsp+2AB0h+var_2A50]; void *
0x18000506d  mov     ebx, 0F0h
0x180005072  xor     edx, edx; Val
0x180005074  mov     r8d, ebx; Size
0x180005077  mov     r15, r9
0x18000507a  movups  xmmword ptr [rsp+2AB0h+SystemTime.wYear], xmm0
0x18000507f  call    memset_0
0x180005084  mov     r8d, ebx; Size
0x180005087  lea     rcx, [rbp+29B0h+var_2960]; void *
0x18000508b  xor     edx, edx; Val
0x18000508d  call    memset_0
0x180005092  lea     rcx, [rsi+0C48h]
0x180005099  xor     edx, edx
0x18000509b  call    cs:__imp_?Lock@TS_RESOURCE@@QEAAXW4TSRES_LOCK_TYPE@@@Z; TS_RESOURCE::Lock(TSRES_LOCK_TYPE)
0x1800050a1  xor     r13d, r13d
0x1800050a4  xor     ebx, ebx
0x1800050a6  xor     r14d, r14d
0x1800050a9  test    edi, edi
0x1800050ab  jz      loc_180005133
0x1800050b1  mov     eax, edi
0x1800050b3  cmp     r14d, 1Eh
0x1800050b7  jnb     short loc_18000512E
0x1800050b9  lea     r12, [rsp+2AB0h+var_2A50]
0x1800050be  lea     r12, [r12+r14*8]
0x1800050c2  test    r12, r12
0x1800050c5  jz      short loc_180005128
0x1800050c7  mov     rax, [rsp+2AB0h+var_2A70]
0x1800050cc  lea     rcx, [rsi+0CA8h]
0x1800050d3  mov     r15d, ebx
0x1800050d6  lea     r8, [rsp+2AB0h+var_2A78]
0x1800050db  add     r15, r15
0x1800050de  mov     [rsp+2AB0h+var_2A78], 0
0x1800050e7  mov     rdx, [rax+r15*8]
0x1800050eb  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800050f1  mov     rcx, [rsp+2AB0h+var_2A78]
0x1800050f6  mov     [r12], rcx
0x1800050fa  test    eax, eax
0x1800050fc  jnz     short loc_180005126
0x1800050fe  cmp     [rcx+80h], eax
0x180005104  jz      short loc_180005126
0x180005106  cmp     rcx, [rsi+r14*8+0B58h]
0x18000510e  setnz   al
0x180005111  or      r13d, eax
0x180005114  mov     rax, [rsp+2AB0h+var_2A70]
0x180005119  mov     rax, [rax+r15*8+8]
0x18000511e  mov     [rbp+r14*8+29B0h+var_2960], rax
0x180005123  inc     r14d
0x180005126  mov     eax, edi
0x180005128  inc     ebx
0x18000512a  cmp     ebx, eax
0x18000512c  jb      short loc_1800050B3
0x18000512e  mov     r15, [rsp+2AB0h+var_2A68]
0x180005133  xor     ecx, ecx
0x180005135  cmp     [rsi+0B50h], r14d
0x18000513c  setnz   cl
0x18000513f  or      ecx, r13d
0x180005142  test    r15, r15
0x180005145  jz      short loc_180005179
0x180005147  mov     rax, [rsi+0B38h]
0x18000514e  mov     rdx, r15
0x180005151  sub     rdx, rax
0x180005154  movzx   r9d, byte ptr [rax]
0x180005158  movzx   r8d, byte ptr [rax+rdx]
0x18000515d  sub     r9d, r8d
0x180005160  jnz     short loc_18000516A
0x180005162  inc     rax
0x180005165  test    r8d, r8d
0x180005168  jnz     short loc_180005154
0x18000516a  xor     r13d, r13d
0x18000516d  test    r9d, r9d
0x180005170  setnz   r13b
0x180005174  or      r13d, ecx
0x180005177  jmp     short loc_18000517C
0x180005179  mov     r13d, ecx
0x18000517c  lea     rbx, [rsi+630h]
0x180005183  mov     rcx, rbx
0x180005186  lea     rdx, [rsp+2AB0h+SystemTime]
0x18000518b  call    cs:__imp_?SetSystemTime@EXTLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z; EXTLOG_DATETIME_CACHE::SetSystemTime(_SYSTEMTIME *)
0x180005191  lea     r8, [rbp+29B0h+Src]
0x180005198  mov     rcx, rbx
0x18000519b  lea     rdx, [rsp+2AB0h+SystemTime]
0x1800051a0  call    cs:__imp_?GetFormattedDateTime@CACHED_DATETIME_FORMATS@@QEAAKPEBU_SYSTEMTIME@@PEAD@Z; CACHED_DATETIME_FORMATS::GetFormattedDateTime(_SYSTEMTIME const *,char *)
0x1800051a6  test    byte ptr [rsi+628h], 3
0x1800051ad  lea     rdi, [rbp+29B0h+var_2850]
0x1800051b4  jz      loc_180005264
0x1800051ba  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800051be  lea     rax, [rbp+29B0h+Src]
0x1800051c5  mov     r15, r12
0x1800051c8  inc     r15
0x1800051cb  cmp     byte ptr [rax+r15], 0
0x1800051d0  jnz     short loc_1800051C8
0x1800051d2  test    byte ptr [rsi+628h], 1
0x1800051d9  jz      short loc_18000521E
0x1800051db  cmp     r15d, 2800h
0x1800051e2  jb      short loc_1800051EB
0x1800051e4  xor     edi, edi
0x1800051e6  jmp     loc_1800052B6
0x1800051eb  mov     r8d, r15d; Size
0x1800051ee  lea     rdx, [rbp+29B0h+Src]; Src
0x1800051f5  lea     rcx, [rbp+29B0h+var_2850]; void *
0x1800051fc  mov     ebx, r15d
0x1800051ff  call    memcpy_0
0x180005204  inc     r15d
0x180005207  mov     [rbp+rbx+29B0h+var_2850], 20h ; ' '
0x18000520f  mov     eax, r15d
0x180005212  lea     rdi, [rbp+29B0h+var_2850]
0x180005219  add     rdi, rax
0x18000521c  jmp     short loc_180005221
0x18000521e  inc     r15d
0x180005221  test    byte ptr [rsi+628h], 2
0x180005228  jz      short loc_180005264
0x18000522a  mov     eax, r15d
0x18000522d  lea     rdx, [rbp+29B0h+Src]
0x180005234  add     rdx, rax; Src
0x180005237  inc     r12
0x18000523a  cmp     byte ptr [rdx+r12], 0
0x18000523f  jnz     short loc_180005237
0x180005241  cmp     r12d, 2800h
0x180005248  jnb     short loc_1800051E4
0x18000524a  mov     r8d, r12d; Size
0x18000524d  mov     rcx, rdi; void *
0x180005250  mov     ebx, r12d
0x180005253  call    memcpy_0
0x180005258  lea     ecx, [r12+1]; this
0x18000525d  mov     byte ptr [rbx+rdi], 20h ; ' '
0x180005261  add     rdi, rcx
0x180005264  lea     rbx, [rbp+29B0h+var_50]
0x18000526b  xor     r15d, r15d
0x18000526e  sub     ebx, edi
0x180005270  test    r14d, r14d
0x180005273  jz      short loc_1800052A5
0x180005275  mov     rdx, [rsp+r15*8+2AB0h+var_2A50]
0x18000527a  mov     r9, rdi; char *
0x18000527d  mov     r8, [rbp+r15*8+29B0h+var_2960]; void *
0x180005282  mov     [rsp+2AB0h+var_2A90], ebx; unsigned int
0x180005286  mov     edx, [rdx+40h]; unsigned int
0x180005289  call    ?ConvertDataToString@CEXTLOG@@IEAAKKPEAXPEADK@Z; CEXTLOG::ConvertDataToString(ulong,void *,char *,ulong)
0x18000528e  cmp     eax, ebx
0x180005290  ja      loc_1800051E4
0x180005296  mov     ecx, eax
0x180005298  sub     ebx, eax
0x18000529a  add     rdi, rcx
0x18000529d  inc     r15d
0x1800052a0  cmp     r15d, r14d
0x1800052a3  jb      short loc_180005275
0x1800052a5  mov     word ptr [rdi-1], 0A0Dh
0x1800052ab  lea     rax, [rbp+29B0h+var_2850]
0x1800052b2  sub     edi, eax
0x1800052b4  inc     edi
0x1800052b6  lea     rbx, [rsi+0C48h]
0x1800052bd  test    r13d, r13d
0x1800052c0  jz      short loc_180005306
0x1800052c2  mov     edx, 1
0x1800052c7  mov     rcx, rbx
0x1800052ca  call    cs:__imp_?Convert@TS_RESOURCE@@QEAAXW4TSRES_CONV_TYPE@@@Z; TS_RESOURCE::Convert(TSRES_CONV_TYPE)
0x1800052d0  mov     [rsi+0B50h], r14d
0x1800052d7  test    r14d, r14d
0x1800052da  jz      short loc_1800052F4
0x1800052dc  mov     r8d, r14d
0x1800052df  lea     rcx, [rsi+0B58h]; void *
0x1800052e6  shl     r8, 3; Size
0x1800052ea  lea     rdx, [rsp+2AB0h+var_2A50]; Src
0x1800052ef  call    memcpy_0
0x1800052f4  mov     rdx, [rsp+2AB0h+var_2A68]
0x1800052f9  lea     rcx, [rsi+0B18h]
0x180005300  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180005306  cmp     dword ptr [rsi+62Ch], 0
0x18000530d  jz      short loc_180005333
0x18000530f  mov     rcx, [rsi+0A60h]
0x180005316  test    rcx, rcx
0x180005319  jz      short loc_180005328
0x18000531b  lea     rdx, [rsp+2AB0h+SystemTime]
0x180005320  call    cs:__imp_?SetLocalTime@ASCLOG_DATETIME_CACHE@@QEAAXPEAU_SYSTEMTIME@@@Z; ASCLOG_DATETIME_CACHE::SetLocalTime(_SYSTEMTIME *)
0x180005326  jmp     short loc_180005333
0x180005328  lea     rcx, [rsp+2AB0h+SystemTime]; lpSystemTime
0x18000532d  call    cs:__imp_GetLocalTime
0x180005333  mov     [rsp+2AB0h+var_2A88], r13d; int
0x180005338  lea     r8, [rbp+29B0h+var_2850]; Src
0x18000533f  mov     r9d, edi; Size
0x180005342  mov     [rsp+2AB0h+var_2A90], 1; int
0x18000534a  lea     rdx, [rsp+2AB0h+SystemTime]; struct _SYSTEMTIME *
0x18000534f  mov     rcx, rsi; this
0x180005352  call    ?WriteLogInformation@CLogFileCtrl@@IEAAXAEAU_SYSTEMTIME@@PEADKHH@Z; CLogFileCtrl::WriteLogInformation(_SYSTEMTIME &,char *,ulong,int,int)
0x180005357  mov     rcx, rbx
0x18000535a  call    cs:__imp_?Unlock@TS_RESOURCE@@QEAAXXZ; TS_RESOURCE::Unlock(void)
0x180005360  xor     eax, eax
0x180005362  mov     rcx, [rbp+29B0h+var_40]
0x180005369  xor     rcx, rsp; StackCookie
0x18000536c  call    __security_check_cookie
0x180005371  mov     rbx, [rsp+2AB0h+arg_8]
0x180005379  add     rsp, 2A80h
0x180005380  pop     r15
0x180005382  pop     r14
0x180005384  pop     r13
0x180005386  pop     r12
0x180005388  pop     rdi
0x180005389  pop     rsi
0x18000538a  pop     rbp
0x18000538b  retn
```
