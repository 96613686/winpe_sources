# WEB_ADMIN_SERVICE::CreateAppPoolIsolation(ushort const *)

- ea: `0x1800044d4`
- end: `0x180004793`
- name: `?CreateAppPoolIsolation@WEB_ADMIN_SERVICE@@AEAAJPEBG@Z`
- size: `703`
- prototype: `__int64 __fastcall(WEB_ADMIN_SERVICE *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180005388`

## callees

- `0x180001234`
- `0x180001274`
- `0x1800044d4`
- `0x18000a158`
- `0x18000d2a0`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000470d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000470d`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800045b9`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800045b9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000454e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004560`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000454e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004560`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004506`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004511`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800045fe`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000460b`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004506`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180004511`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800045fe`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18000460b`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180004755`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180004763`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180004755`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180004763`
- `iisutil!ReadMultiStringParameterValueFromAnyService` at `0x180004673`
- `iisutil!ReadMultiStringParameterValueFromAnyService` at `0x18000468f`
- `iisutil!ReadMultiStringParameterValueFromAnyService` at `0x180004673`
- `iisutil!ReadMultiStringParameterValueFromAnyService` at `0x18000468f`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800046ad`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800046d2`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800046ad`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800046d2`

## string_xrefs

- `0x18000466c`: `System\CurrentControlSet\Services\WAS\Parameters`
- `0x180004688`: `System\CurrentControlSet\Services\WAS\Parameters`
- `0x180004665`: `ConfigIsolationSectionsExcluded`
- `0x180004681`: `ConfigIsolationSectionsIncluded`

## pseudocode

```c
__int64 __fastcall WEB_ADMIN_SERVICE::CreateAppPoolIsolation(WEB_ADMIN_SERVICE *this, const unsigned __int16 *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  signed int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  signed int LastError; // eax
  void *v10; // rdi
  _BYTE v12[56]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v13[56]; // [rsp+88h] [rbp-60h] BYREF

  MULTISZ::MULTISZ((MULTISZ *)v13);
  MULTISZ::MULTISZ((MULTISZ *)v12);
  v4 = operator new(0x1F8u);
  v5 = v4;
  if ( v4 )
  {
    v4[3] = 1;
    *(_QWORD *)v4 = &APP_POOL_ISOLATION::`vftable';
    v4[4] = 0;
    v4[5] = 0;
    *((_QWORD *)v4 + 3) = 0;
    STRU::STRU((STRU *)(v4 + 8));
    *((_QWORD *)v5 + 11) = -1;
    STRU::STRU((STRU *)(v5 + 24));
    CLKRHashTable::CLKRHashTable(
      (CLKRHashTable *)(v5 + 40),
      "STRING_TO_STRING_SET_TABLE",
      (unsigned __int64 (*)(const void *))CTypedHashTable<SITEAPP_HASH,SITEAPP_ENTRY,unsigned short const *,CLKRHashTable>::_ExtractKey,
      (unsigned int (*)(unsigned __int64))CTypedHashTable<STRING_TO_STRING_SET_TABLE,STRING_TO_STRING_SET_TABLE_ITEM,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
      (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<STRING_TO_STRING_SET_TABLE,STRING_TO_STRING_SET_TABLE_ITEM,unsigned short const *,CLKRHashTable>::_EqualKeys,
      (void (*)(const void *, int))CTypedHashTable<STRING_TO_STRING_SET_TABLE,STRING_TO_STRING_SET_TABLE_ITEM,unsigned short const *,CLKRHashTable>::_AddRefRecord,
      4.0,
      1u,
      0,
      0);
    *((_QWORD *)v5 + 19) = &REQUEST_QUEUE_INSTANCE_TABLE::`vftable';
    *((_QWORD *)v5 + 29) = 0;
    *((_QWORD *)v5 + 30) = 0;
    *((_QWORD *)v5 + 31) = 0;
    *((_QWORD *)v5 + 32) = 0;
    *((_QWORD *)v5 + 33) = 0;
    *((_QWORD *)v5 + 34) = 0;
    MULTISZ::MULTISZ((MULTISZ *)(v5 + 70));
    MULTISZ::MULTISZ((MULTISZ *)(v5 + 84));
    *((_QWORD *)v5 + 50) = 1364350797;
    *((_QWORD *)v5 + 49) = &MULTI_WORK_QUEUE::`vftable';
    v5[120] = 0;
    *((_QWORD *)v5 + 61) = 0;
    *((_QWORD *)v5 + 62) = 0;
    v5[2] = 1397313601;
  }
  else
  {
    v5 = 0;
  }
  *((_QWORD *)this + 229) = v5;
  if ( !v5 )
  {
    v6 = -2147024882;
LABEL_18:
    v10 = (void *)*((_QWORD *)this + 229);
    if ( v10 )
    {
      APP_POOL_ISOLATION::~APP_POOL_ISOLATION(*((APP_POOL_ISOLATION **)this + 229));
      operator delete(v10);
    }
    *((_QWORD *)this + 229) = 0;
    goto LABEL_21;
  }
  ReadMultiStringParameterValueFromAnyService(
    L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
    L"ConfigIsolationSectionsExcluded",
    (struct MULTISZ *)v12);
  ReadMultiStringParameterValueFromAnyService(
    L"System\\CurrentControlSet\\Services\\WAS\\Parameters",
    L"ConfigIsolationSectionsIncluded",
    (struct MULTISZ *)v13);
  v7 = 0;
  while ( MULTISZ::Append((MULTISZ *)v12, (const unsigned __int16 *)(&g_DefaultSectionExclusionList)[v7]) )
  {
    if ( (unsigned int)++v7 >= 5 )
    {
      v8 = 0;
      while ( MULTISZ::Append((MULTISZ *)v13, (const unsigned __int16 *)(&g_DefaultSectionInclusionList)[v8]) )
      {
        if ( (unsigned int)++v8 >= 2 )
        {
          v6 = APP_POOL_ISOLATION::Initialize(
                 *((APP_POOL_ISOLATION **)this + 229),
                 a2,
                 (struct MULTISZ *)v12,
                 (struct MULTISZ *)v13);
          goto LABEL_17;
        }
      }
      break;
    }
  }
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = -2147467259;
  }
LABEL_17:
  if ( v6 < 0 )
    goto LABEL_18;
LABEL_21:
  MULTISZ::~MULTISZ((MULTISZ *)v12);
  MULTISZ::~MULTISZ((MULTISZ *)v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800044d4  mov     r11, rsp
0x1800044d7  mov     [r11+18h], rbx
0x1800044db  mov     [r11+20h], rbp
0x1800044df  push    rsi
0x1800044e0  push    rdi
0x1800044e1  push    r15
0x1800044e3  sub     rsp, 0D0h
0x1800044ea  mov     rax, cs:__security_cookie
0x1800044f1  xor     rax, rsp
0x1800044f4  mov     [rsp+0E8h+var_28], rax
0x1800044fc  mov     rsi, rcx
0x1800044ff  mov     rdi, rdx
0x180004502  lea     rcx, [r11-60h]
0x180004506  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18000450c  lea     rcx, [rsp+0E8h+var_98]
0x180004511  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180004517  mov     ecx, 1F8h; Size
0x18000451c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004521  xor     ebp, ebp
0x180004523  mov     rbx, rax
0x180004526  test    rax, rax
0x180004529  jz      loc_180004647
0x18000452f  mov     dword ptr [rbx+0Ch], 1
0x180004536  lea     rax, ??_7APP_POOL_ISOLATION@@6B@; const APP_POOL_ISOLATION::`vftable'
0x18000453d  mov     [rbx], rax
0x180004540  lea     rcx, [rbx+20h]
0x180004544  mov     [rbx+10h], ebp
0x180004547  mov     [rbx+14h], ebp
0x18000454a  mov     [rbx+18h], rbp
0x18000454e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004554  lea     rcx, [rbx+60h]
0x180004558  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x180004560  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004566  movsd   xmm0, cs:__real@4010000000000000
0x18000456e  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VSTRING_TO_STRING_SET_TABLE@@VSTRING_TO_STRING_SET_TABLE_ITEM@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<STRING_TO_STRING_SET_TABLE,STRING_TO_STRING_SET_TABLE_ITEM,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180004575  mov     [rsp+0E8h+var_A0], bpl
0x18000457a  lea     rcx, [rbx+0A0h]
0x180004581  mov     [rsp+0E8h+var_A8], ebp
0x180004585  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VSTRING_TO_STRING_SET_TABLE@@VSTRING_TO_STRING_SET_TABLE_ITEM@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<STRING_TO_STRING_SET_TABLE,STRING_TO_STRING_SET_TABLE_ITEM,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18000458c  mov     [rsp+0E8h+var_B0], 1
0x180004594  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSITEAPP_HASH@@VSITEAPP_ENTRY@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<SITEAPP_HASH,SITEAPP_ENTRY,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x18000459b  movsd   [rsp+0E8h+var_B8], xmm0
0x1800045a1  lea     rdx, aStringToString; "STRING_TO_STRING_SET_TABLE"
0x1800045a8  mov     [rsp+0E8h+var_C0], rax
0x1800045ad  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSTRING_TO_STRING_SET_TABLE@@VSTRING_TO_STRING_SET_TABLE_ITEM@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<STRING_TO_STRING_SET_TABLE,STRING_TO_STRING_SET_TABLE_ITEM,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800045b4  mov     [rsp+0E8h+var_C8], rax
0x1800045b9  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800045bf  lea     rax, ??_7REQUEST_QUEUE_INSTANCE_TABLE@@6B@; const REQUEST_QUEUE_INSTANCE_TABLE::`vftable'
0x1800045c6  mov     [rbx+98h], rax
0x1800045cd  lea     rcx, [rbx+118h]
0x1800045d4  mov     [rbx+0E8h], rbp
0x1800045db  mov     [rbx+0F0h], rbp
0x1800045e2  mov     [rbx+0F8h], rbp
0x1800045e9  mov     [rbx+100h], rbp
0x1800045f0  mov     [rbx+108h], rbp
0x1800045f7  mov     [rbx+110h], rbp
0x1800045fe  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180004604  lea     rcx, [rbx+150h]
0x18000460b  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180004611  lea     rax, ??_7MULTI_WORK_QUEUE@@6B@; const MULTI_WORK_QUEUE::`vftable'
0x180004618  mov     qword ptr [rbx+190h], 5152574Dh
0x180004623  mov     [rbx+188h], rax
0x18000462a  mov     [rbx+1E0h], ebp
0x180004630  mov     [rbx+1E8h], rbp
0x180004637  mov     [rbx+1F0h], rbp
0x18000463e  mov     dword ptr [rbx+8], 53495041h
0x180004645  jmp     short loc_18000464A
0x180004647  mov     rbx, rbp
0x18000464a  mov     [rsi+728h], rbx
0x180004651  test    rbx, rbx
0x180004654  jnz     short loc_180004660
0x180004656  mov     ebx, 8007000Eh
0x18000465b  jmp     loc_18000472D
0x180004660  lea     r8, [rsp+0E8h+var_98]
0x180004665  lea     rdx, aConfigisolatio_0; "ConfigIsolationSectionsExcluded"
0x18000466c  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WA"...
0x180004673  call    cs:__imp_?ReadMultiStringParameterValueFromAnyService@@YAJPEBG0PEAVMULTISZ@@@Z; ReadMultiStringParameterValueFromAnyService(ushort const *,ushort const *,MULTISZ *)
0x180004679  lea     r8, [rsp+0E8h+var_60]
0x180004681  lea     rdx, aConfigisolatio_2; "ConfigIsolationSectionsIncluded"
0x180004688  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\WA"...
0x18000468f  call    cs:__imp_?ReadMultiStringParameterValueFromAnyService@@YAJPEBG0PEAVMULTISZ@@@Z; ReadMultiStringParameterValueFromAnyService(ushort const *,ushort const *,MULTISZ *)
0x180004695  mov     ebx, ebp
0x180004697  lea     r15, __ImageBase
0x18000469e  mov     edx, ebx
0x1800046a0  lea     rcx, [rsp+0E8h+var_98]
0x1800046a5  mov     rdx, ds:rva ?g_DefaultSectionExclusionList@@3PAPEBGA[r15+rdx*8]; ushort const * near * g_DefaultSectionExclusionList ...
0x1800046ad  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800046b3  test    eax, eax
0x1800046b5  jz      short loc_180004703
0x1800046b7  inc     ebx
0x1800046b9  cmp     ebx, 5
0x1800046bc  jb      short loc_18000469E
0x1800046be  mov     ebx, ebp
0x1800046c0  mov     edx, ebx
0x1800046c2  lea     rcx, [rsp+0E8h+var_60]
0x1800046ca  mov     rdx, ds:rva ?g_DefaultSectionInclusionList@@3PAPEBGA[r15+rdx*8]; ushort const * near * g_DefaultSectionInclusionList ...
0x1800046d2  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800046d8  test    eax, eax
0x1800046da  jz      short loc_180004703
0x1800046dc  inc     ebx
0x1800046de  cmp     ebx, 2
0x1800046e1  jb      short loc_1800046C0
0x1800046e3  mov     rcx, [rsi+728h]; this
0x1800046ea  lea     r9, [rsp+0E8h+var_60]; struct MULTISZ *
0x1800046f2  lea     r8, [rsp+0E8h+var_98]; struct MULTISZ *
0x1800046f7  mov     rdx, rdi; unsigned __int16 *
0x1800046fa  call    ?Initialize@APP_POOL_ISOLATION@@QEAAJPEBGPEAVMULTISZ@@1@Z; APP_POOL_ISOLATION::Initialize(ushort const *,MULTISZ *,MULTISZ *)
0x1800046ff  mov     ebx, eax
0x180004701  jmp     short loc_180004729
0x180004703  call    cs:__imp_GetLastError
0x180004709  test    eax, eax
0x18000470b  jz      short loc_180004724
0x18000470d  call    cs:__imp_GetLastError
0x180004713  mov     ebx, eax
0x180004715  test    eax, eax
0x180004717  jle     short loc_180004729
0x180004719  movzx   ebx, ax
0x18000471c  or      ebx, 80070000h
0x180004722  jmp     short loc_180004729
0x180004724  mov     ebx, 80004005h
0x180004729  test    ebx, ebx
0x18000472b  jns     short loc_180004750
0x18000472d  mov     rdi, [rsi+728h]
0x180004734  test    rdi, rdi
0x180004737  jz      short loc_180004749
0x180004739  mov     rcx, rdi; this
0x18000473c  call    ??1APP_POOL_ISOLATION@@QEAA@XZ; APP_POOL_ISOLATION::~APP_POOL_ISOLATION(void)
0x180004741  mov     rcx, rdi; Block
0x180004744  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004749  mov     [rsi+728h], rbp
0x180004750  lea     rcx, [rsp+0E8h+var_98]
0x180004755  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x18000475b  lea     rcx, [rsp+0E8h+var_60]
0x180004763  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180004769  mov     eax, ebx
0x18000476b  mov     rcx, [rsp+0E8h+var_28]
0x180004773  xor     rcx, rsp; StackCookie
0x180004776  call    __security_check_cookie
0x18000477b  lea     r11, [rsp+0E8h+var_18]
0x180004783  mov     rbx, [r11+30h]
0x180004787  mov     rbp, [r11+38h]
0x18000478b  mov     rsp, r11
0x18000478e  pop     r15
0x180004790  pop     rdi
0x180004791  pop     rsi
0x180004792  retn
```
