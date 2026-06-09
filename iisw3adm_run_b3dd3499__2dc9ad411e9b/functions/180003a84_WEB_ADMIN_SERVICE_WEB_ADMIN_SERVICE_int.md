# WEB_ADMIN_SERVICE::WEB_ADMIN_SERVICE(int)

- ea: `0x180003a84`
- end: `0x180003e1b`
- name: `??0WEB_ADMIN_SERVICE@@QEAA@H@Z`
- size: `919`
- prototype: `WEB_ADMIN_SERVICE *__fastcall(WEB_ADMIN_SERVICE *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180002c90`
- `0x180003770`

## callees

- `0x18000e4dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003b51`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180003b51`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003cab`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003cab`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180003c1c`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180003c39`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180003c1c`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180003c39`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003c51`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003d5b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003d68`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003d75`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003c51`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003d5b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003d68`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003d75`
- `iisutil!??0CSecurityDispenser@@QEAA@XZ` at `0x180003cfb`
- `iisutil!??0CSecurityDispenser@@QEAA@XZ` at `0x180003cfb`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180003b29`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180003b36`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180003b29`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180003b36`

## string_xrefs

- `0x180003ca4`: `TOKEN_CACHE`

## pseudocode

```c
WEB_ADMIN_SERVICE *__fastcall WEB_ADMIN_SERVICE::WEB_ADMIN_SERVICE(WEB_ADMIN_SERVICE *this, int a2)
{
  const unsigned __int16 *v4; // rbx
  const unsigned __int16 *v5; // rdx
  WEB_ADMIN_SERVICE *result; // rax

  *((_QWORD *)this + 5) = 1262702412;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &WEB_ADMIN_SERVICE::`vftable';
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 2) = &WORK_QUEUE::`vftable';
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_DWORD *)this + 6) = 1363890775;
  UL_AND_WORKER_MANAGER::UL_AND_WORKER_MANAGER((WEB_ADMIN_SERVICE *)((char *)this + 112));
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 86) = &CONFIG_AND_CONTROL_MANAGER::`vftable';
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 88) = &CONFIG_MANAGER::`vftable';
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  MULTISZ::MULTISZ((WEB_ADMIN_SERVICE *)((char *)this + 824));
  MULTISZ::MULTISZ((WEB_ADMIN_SERVICE *)((char *)this + 880));
  *((_DWORD *)this + 234) = 0;
  *((_DWORD *)this + 235) = 0;
  InitializeSRWLock((PSRWLOCK)this + 118);
  *((_DWORD *)this + 242) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 120) = 0;
  v4 = L"HostableWebCore";
  *((_QWORD *)this + 125) = 0;
  *((_QWORD *)this + 126) = 0;
  *((_QWORD *)this + 127) = 0;
  v5 = L"HostableWebCore";
  *((_QWORD *)this + 128) = 0;
  if ( !a2 )
    v5 = L"WAS";
  *((_QWORD *)this + 123) = 0;
  *((_DWORD *)this + 248) = -2147467259;
  *((_QWORD *)this + 129) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_DWORD *)this + 238) = 0;
  *((_QWORD *)this + 130) = 1;
  *((_DWORD *)this + 178) = 1296516675;
  *((_QWORD *)this + 131) = 0;
  *((_QWORD *)this + 132) = 1;
  *((_DWORD *)this + 174) = 1196245827;
  EVENT_LOG::EVENT_LOG((WEB_ADMIN_SERVICE *)((char *)this + 1064), v5);
  if ( !a2 )
    v4 = L"W3SVC";
  EVENT_LOG::EVENT_LOG((WEB_ADMIN_SERVICE *)((char *)this + 1068), v4);
  *((_QWORD *)this + 134) = 1262702412;
  STRU::STRU((WEB_ADMIN_SERVICE *)((char *)this + 1184));
  CLKRHashTable::CLKRHashTable(
    (WEB_ADMIN_SERVICE *)((char *)this + 1240),
    "TOKEN_CACHE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  *((_DWORD *)this + 336) &= ~1u;
  *((_DWORD *)this + 336) |= 2u;
  *((_QWORD *)this + 170) = (char *)this + 1352;
  *((_QWORD *)this + 169) = (char *)this + 1352;
  *((_QWORD *)this + 164) = 0;
  *((_QWORD *)this + 165) = 0;
  *((_QWORD *)this + 166) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_DWORD *)this + 337) = 0;
  *((_QWORD *)this + 171) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_QWORD *)this + 173) = 0;
  *((_DWORD *)this + 353) = 0;
  CSecurityDispenser::CSecurityDispenser((WEB_ADMIN_SERVICE *)((char *)this + 1416));
  *((_QWORD *)this + 195) = 0;
  *((_QWORD *)this + 197) = &WMS_ERROR_LOGGER::`vftable';
  *((_DWORD *)this + 392) = 0;
  *((_DWORD *)this + 396) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 205) = 0;
  *((_DWORD *)this + 412) = a2;
  STRU::STRU((WEB_ADMIN_SERVICE *)((char *)this + 1656));
  STRU::STRU((WEB_ADMIN_SERVICE *)((char *)this + 1712));
  STRU::STRU((WEB_ADMIN_SERVICE *)((char *)this + 1768));
  *((_QWORD *)this + 228) = 0;
  *((_DWORD *)this + 350) = -1;
  *((_DWORD *)this + 351) = -1;
  result = this;
  *((_QWORD *)this + 229) = 0;
  *((_QWORD *)this + 230) = 1;
  *((_QWORD *)this + 231) = 0;
  *((_DWORD *)this + 393) = 0;
  *((_DWORD *)this + 3) = 1;
  *((_QWORD *)this + 140) = 0;
  *((_DWORD *)this + 282) = 32;
  *((_DWORD *)this + 283) = 1;
  *((_QWORD *)this + 142) = 7;
  *((_QWORD *)this + 143) = 0;
  *((_DWORD *)this + 288) = 0;
  *((_QWORD *)this + 145) = 0;
  *((_QWORD *)this + 146) = 0;
  *((_DWORD *)this + 294) = 0;
  *((_QWORD *)this + 174) = 0;
  *((_DWORD *)this + 352) = 0;
  *((_DWORD *)this + 2) = 1448296791;
  return result;
}

```

## disassembly

```asm
0x180003a84  push    rbx
0x180003a86  push    rsi
0x180003a87  push    rdi
0x180003a88  push    r14
0x180003a8a  push    r15
0x180003a8c  sub     rsp, 50h
0x180003a90  xor     r15d, r15d
0x180003a93  mov     qword ptr [rcx+28h], 4B434F4Ch
0x180003a9b  lea     rax, ??_7WEB_ADMIN_SERVICE@@6B@; const WEB_ADMIN_SERVICE::`vftable'
0x180003aa2  mov     [rcx+20h], r15
0x180003aa6  mov     [rcx], rax
0x180003aa9  mov     rsi, rcx
0x180003aac  lea     rax, ??_7WORK_QUEUE@@6B@; const WORK_QUEUE::`vftable'
0x180003ab3  mov     [rcx+58h], r15
0x180003ab7  mov     [rcx+10h], rax
0x180003abb  mov     edi, edx
0x180003abd  mov     [rcx+60h], r15
0x180003ac1  mov     [rcx+68h], r15d
0x180003ac5  mov     dword ptr [rcx+18h], 514B5257h
0x180003acc  add     rcx, 70h ; 'p'; this
0x180003ad0  call    ??0UL_AND_WORKER_MANAGER@@QEAA@XZ; UL_AND_WORKER_MANAGER::UL_AND_WORKER_MANAGER(void)
0x180003ad5  lea     rax, ??_7CONFIG_AND_CONTROL_MANAGER@@6B@; const CONFIG_AND_CONTROL_MANAGER::`vftable'
0x180003adc  mov     [rsi+300h], r15
0x180003ae3  mov     [rsi+2B0h], rax
0x180003aea  lea     rcx, [rsi+338h]
0x180003af1  lea     rax, ??_7CONFIG_MANAGER@@6B@; const CONFIG_MANAGER::`vftable'
0x180003af8  mov     [rsi+308h], r15
0x180003aff  mov     [rsi+2C0h], rax
0x180003b06  mov     [rsi+310h], r15
0x180003b0d  mov     [rsi+318h], r15
0x180003b14  mov     [rsi+320h], r15
0x180003b1b  mov     [rsi+328h], r15
0x180003b22  mov     [rsi+330h], r15
0x180003b29  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180003b2f  lea     rcx, [rsi+370h]
0x180003b36  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180003b3c  mov     [rsi+3A8h], r15d
0x180003b43  lea     rcx, [rsi+3B0h]; SRWLock
0x180003b4a  mov     [rsi+3ACh], r15d
0x180003b51  call    cs:__imp_InitializeSRWLock
0x180003b57  mov     [rsi+3C8h], r15d
0x180003b5e  lea     r14d, [r15+1]
0x180003b62  mov     [rsi+3D0h], r15
0x180003b69  lea     rax, aWas_0; "WAS"
0x180003b70  mov     [rsi+3C0h], r15
0x180003b77  lea     rbx, aHostablewebcor_0; "HostableWebCore"
0x180003b7e  mov     [rsi+3E8h], r15
0x180003b85  lea     rcx, [rsi+428h]
0x180003b8c  mov     [rsi+3F0h], r15
0x180003b93  test    edi, edi
0x180003b95  mov     [rsi+3F8h], r15
0x180003b9c  mov     rdx, rbx
0x180003b9f  mov     [rsi+400h], r15
0x180003ba6  cmovz   rdx, rax
0x180003baa  mov     [rsi+3D8h], r15
0x180003bb1  mov     dword ptr [rsi+3E0h], 80004005h
0x180003bbb  mov     [rsi+408h], r15
0x180003bc2  mov     [rsi+2D0h], r15
0x180003bc9  mov     [rsi+2D8h], r15
0x180003bd0  mov     [rsi+2E0h], r15
0x180003bd7  mov     [rsi+2E8h], r15
0x180003bde  mov     [rsi+2F0h], r15
0x180003be5  mov     [rsi+2F8h], r15
0x180003bec  mov     [rsi+3B8h], r15d
0x180003bf3  mov     [rsi+410h], r14
0x180003bfa  mov     dword ptr [rsi+2C8h], 4D474643h
0x180003c04  mov     [rsi+418h], r15
0x180003c0b  mov     [rsi+420h], r14
0x180003c12  mov     dword ptr [rsi+2B8h], 474D4343h
0x180003c1c  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180003c22  lea     rax, aW3svc; "W3SVC"
0x180003c29  test    edi, edi
0x180003c2b  lea     rcx, [rsi+42Ch]
0x180003c32  cmovz   rbx, rax
0x180003c36  mov     rdx, rbx
0x180003c39  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180003c3f  lea     rcx, [rsi+4A0h]
0x180003c46  mov     qword ptr [rsi+430h], 4B434F4Ch
0x180003c51  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003c57  movsd   xmm0, cs:__real@4010000000000000
0x180003c5f  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180003c66  mov     [rsp+78h+var_30], r15b
0x180003c6b  lea     rbx, [rsi+4D8h]
0x180003c72  mov     [rsp+78h+var_38], r15d
0x180003c77  mov     [rsp+78h+var_40], r14d
0x180003c7c  movsd   [rsp+78h+var_48], xmm0
0x180003c82  mov     [rsp+78h+var_50], rax
0x180003c87  lea     rax, ?_EqualKeys@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180003c8e  mov     rcx, rbx
0x180003c91  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180003c98  mov     [rsp+78h+var_58], rax
0x180003c9d  lea     r8, ?_ExtractKey@?$CTypedHashTable@VTOKEN_CACHE@@VTOKEN_CACHE_ENTRY@@PEAVTOKEN_CACHE_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x180003ca4  lea     rdx, aTokenCache; "TOKEN_CACHE"
0x180003cab  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180003cb1  and     dword ptr [rbx+68h], 0FFFFFFFEh
0x180003cb5  lea     rax, [rbx+70h]
0x180003cb9  or      dword ptr [rbx+68h], 2
0x180003cbd  lea     rcx, [rsi+588h]
0x180003cc4  mov     [rax+8], rax
0x180003cc8  mov     [rax], rax
0x180003ccb  mov     [rbx+48h], r15
0x180003ccf  mov     [rbx+50h], r15
0x180003cd3  mov     [rbx+58h], r15
0x180003cd7  mov     [rbx+60h], r15
0x180003cdb  mov     [rbx+6Ch], r15d
0x180003cdf  mov     [rbx+80h], r15
0x180003ce6  mov     [rbx+88h], r15
0x180003ced  mov     [rbx+90h], r15
0x180003cf4  mov     [rsi+584h], r15d
0x180003cfb  call    cs:__imp_??0CSecurityDispenser@@QEAA@XZ; CSecurityDispenser::CSecurityDispenser(void)
0x180003d01  lea     rax, ??_7WMS_ERROR_LOGGER@@6B@; const WMS_ERROR_LOGGER::`vftable'
0x180003d08  mov     [rsi+618h], r15
0x180003d0f  lea     rcx, [rsi+678h]
0x180003d16  mov     [rsi+628h], rax
0x180003d1d  mov     [rsi+620h], r15d
0x180003d24  mov     [rsi+630h], r15d
0x180003d2b  mov     [rsi+640h], r15
0x180003d32  mov     [rsi+648h], r15
0x180003d39  mov     [rsi+650h], r15
0x180003d40  mov     [rsi+658h], r15
0x180003d47  mov     [rsi+660h], r15
0x180003d4e  mov     [rsi+668h], r15
0x180003d55  mov     [rsi+670h], edi
0x180003d5b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003d61  lea     rcx, [rsi+6B0h]
0x180003d68  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003d6e  lea     rcx, [rsi+6E8h]
0x180003d75  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003d7b  or      eax, 0FFFFFFFFh
0x180003d7e  mov     [rsi+720h], r15
0x180003d85  mov     [rsi+578h], eax
0x180003d8b  mov     [rsi+57Ch], eax
0x180003d91  mov     rax, rsi
0x180003d94  mov     [rsi+728h], r15
0x180003d9b  mov     [rsi+730h], r14
0x180003da2  mov     [rsi+738h], r15
0x180003da9  mov     [rsi+624h], r15d
0x180003db0  mov     [rsi+0Ch], r14d
0x180003db4  mov     [rsi+460h], r15
0x180003dbb  mov     dword ptr [rsi+468h], 20h ; ' '
0x180003dc5  mov     [rsi+46Ch], r14d
0x180003dcc  mov     qword ptr [rsi+470h], 7
0x180003dd7  mov     [rsi+478h], r15
0x180003dde  mov     [rsi+480h], r15d
0x180003de5  mov     [rsi+488h], r15
0x180003dec  mov     [rsi+490h], r15
0x180003df3  mov     [rsi+498h], r15d
0x180003dfa  mov     [rsi+570h], r15
0x180003e01  mov     [rsi+580h], r15d
0x180003e08  mov     dword ptr [rsi+8], 56534157h
0x180003e0f  add     rsp, 50h
0x180003e13  pop     r15
0x180003e15  pop     r14
0x180003e17  pop     rdi
0x180003e18  pop     rsi
0x180003e19  pop     rbx
0x180003e1a  retn
```
