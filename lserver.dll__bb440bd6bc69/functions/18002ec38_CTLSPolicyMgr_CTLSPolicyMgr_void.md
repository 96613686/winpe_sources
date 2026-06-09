# CTLSPolicyMgr::CTLSPolicyMgr(void)

- ea: `0x18002ec38`
- end: `0x18002ef9c`
- name: `??0CTLSPolicyMgr@@QEAA@XZ`
- size: `868`
- prototype: `CTLSPolicyMgr *__fastcall(CTLSPolicyMgr *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001b00`

## callees

- `0x18000205c`
- `0x180005665`
- `0x180022fcc`
- `0x18002ec38`
- `0x18002f354`
- `0x18002f9cc`
- `0x180031104`
- `0x180031144`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002eed7`
- `msvcrt!wcscpy_s` at `0x18002eef4`
- `msvcrt!wcscpy_s` at `0x18002eed7`
- `msvcrt!wcscpy_s` at `0x18002eef4`
- `KERNEL32!CreateEventW` at `0x18002ec8a`
- `KERNEL32!CreateEventW` at `0x18002eca7`
- `KERNEL32!CreateEventW` at `0x18002ed33`
- `KERNEL32!CreateEventW` at `0x18002ed50`
- `KERNEL32!CreateEventW` at `0x18002edd4`
- `KERNEL32!CreateEventW` at `0x18002edf1`
- `KERNEL32!CreateEventW` at `0x18002ec8a`
- `KERNEL32!CreateEventW` at `0x18002eca7`
- `KERNEL32!CreateEventW` at `0x18002ed33`
- `KERNEL32!CreateEventW` at `0x18002ed50`
- `KERNEL32!CreateEventW` at `0x18002edd4`
- `KERNEL32!CreateEventW` at `0x18002edf1`
- `KERNEL32!CreateMutexW` at `0x18002ecc1`
- `KERNEL32!CreateMutexW` at `0x18002ed6a`
- `KERNEL32!CreateMutexW` at `0x18002ee0b`
- `KERNEL32!CreateMutexW` at `0x18002ecc1`
- `KERNEL32!CreateMutexW` at `0x18002ed6a`
- `KERNEL32!CreateMutexW` at `0x18002ee0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
CTLSPolicyMgr *__fastcall CTLSPolicyMgr::CTLSPolicyMgr(CTLSPolicyMgr *this)
{
  HANDLE MutexW; // rax
  HANDLE v2; // rax
  HANDLE v3; // rax
  CTLSPolicy *v4; // rax
  HINSTANCE v5; // rdx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r9
  CTLSPolicy *v8; // rbx
  enum POLICYSTATUS (__high *v10)(void *, union _ULARGE_INTEGER *, struct __PMLICENSETOBERETURN *, unsigned int *, unsigned int *); // [rsp+20h] [rbp-488h]
  enum POLICYSTATUS (__high *v11)(void *, unsigned int, int, void *, void **, unsigned int *, unsigned int); // [rsp+28h] [rbp-480h]
  enum POLICYSTATUS (__high *v12)(void *, unsigned int, void *, void **, unsigned int *); // [rsp+30h] [rbp-478h]
  enum POLICYSTATUS (__high *v13)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *); // [rsp+38h] [rbp-470h]
  enum POLICYSTATUS (__high *v14)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *); // [rsp+40h] [rbp-468h]
  enum POLICYSTATUS (__high *v15)(void *, unsigned int, void *, void *, unsigned int *); // [rsp+48h] [rbp-460h]
  enum POLICYSTATUS (__high *v16)(void **); // [rsp+50h] [rbp-458h]
  wchar_t Destination[256]; // [rsp+90h] [rbp-418h] BYREF
  wchar_t v18[256]; // [rsp+290h] [rbp-218h] BYREF

  qword_1800E9130 = (__int64)CreateEventW(0, 1, 0, 0);
  PolicyMgr = CreateEventW(0, 0, 1, 0);
  MutexW = CreateMutexW(0, 0, 0);
  qword_1800E9128 = (__int64)MutexW;
  if ( qword_1800E9130 && PolicyMgr && MutexW )
  {
    dword_1800E9138 = -1;
    dword_1800E913C = -1;
    qword_1800E9140 = 0;
  }
  qword_1800E9148 = 0;
  qword_1800E9150 = 0;
  qword_1800E9148 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__PolicyModule const,CTLSPolicy *>>>::_Buyheadnode();
  qword_1800E9168 = (__int64)CreateEventW(0, 1, 0, 0);
  qword_1800E9158 = (__int64)CreateEventW(0, 0, 1, 0);
  v2 = CreateMutexW(0, 0, 0);
  qword_1800E9160 = (__int64)v2;
  if ( qword_1800E9168 && qword_1800E9158 && v2 )
    xmmword_1800E9170 = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  qword_1800E9180 = 0;
  qword_1800E9188 = 0;
  qword_1800E9180 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__PolicyModule const,CTLSPolicy *>>>::_Buyheadnode();
  qword_1800E91A0 = (__int64)CreateEventW(0, 1, 0, 0);
  qword_1800E9190 = (__int64)CreateEventW(0, 0, 1, 0);
  v3 = CreateMutexW(0, 0, 0);
  qword_1800E9198 = (__int64)v3;
  if ( qword_1800E91A0 && qword_1800E9190 && v3 )
  {
    dword_1800E91A8 = -1;
    dword_1800E91AC = -1;
    qword_1800E91B0 = 0;
  }
  qword_1800E91B8 = 0;
  qword_1800E91C0 = 0;
  qword_1800E91B8 = (CTLSPolicyMgr *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__PolicyModule const,__TranslationValue>>>::_Buyheadnode();
  memset_0(Destination, 0, sizeof(Destination));
  memset_0(v18, 0, sizeof(v18));
  LoadResourceString(0x78u, &g_szDefPolCompanyName, 255);
  LoadResourceString(0x78u, &g_szDefProductId, 255);
  wcscpy_s(Destination, 0x100u, &g_szDefPolCompanyName);
  wcscpy_s(v18, 0x100u, &g_szDefProductId);
  v4 = (CTLSPolicy *)operator new(0x658u);
  v8 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 7) = 0;
    *((_QWORD *)v4 + 8) = 0;
    *((_QWORD *)v4 + 9) = 0;
    *((_QWORD *)v4 + 10) = 0;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
    CTLSPolicy::CreatePolicy(v8, v5, v6, v7, v10, v11, v12, v13, v14, v15, v16);
  *(_QWORD *)std::map<__PolicyModule,CTLSPolicy *>::operator[](&qword_1800E9148, Destination) = v8;
  return (CTLSPolicyMgr *)&PolicyMgr;
}

```

## disassembly

```asm
0x18002ec38  mov     rax, rsp
0x18002ec3b  mov     [rax+8], rbx
0x18002ec3f  mov     [rax+10h], rbp
0x18002ec43  mov     [rax+18h], rsi
0x18002ec47  mov     [rax+20h], rdi
0x18002ec4b  push    r14
0x18002ec4d  sub     rsp, 4A0h
0x18002ec54  mov     rax, cs:__security_cookie
0x18002ec5b  xor     rax, rsp
0x18002ec5e  mov     [rsp+4A8h+var_18], rax
0x18002ec66  mov     rax, [rsp+4A8h+var_448]
0x18002ec6b  mov     [rsp+4A8h+var_438], rax
0x18002ec70  lea     r14, ?PolicyMgr@@3VCTLSPolicyMgr@@A; CTLSPolicyMgr PolicyMgr
0x18002ec77  mov     [rsp+4A8h+var_438], r14
0x18002ec7c  xor     r9d, r9d; lpName
0x18002ec7f  xor     r8d, r8d; bInitialState
0x18002ec82  lea     edi, [r9+1]
0x18002ec86  mov     edx, edi; bManualReset
0x18002ec88  xor     ecx, ecx; lpEventAttributes
0x18002ec8a  call    cs:__imp_CreateEventW
0x18002ec91  nop     dword ptr [rax+rax+00h]
0x18002ec96  mov     cs:qword_1800E9130, rax
0x18002ec9d  xor     r9d, r9d; lpName
0x18002eca0  mov     r8d, edi; bInitialState
0x18002eca3  xor     edx, edx; bManualReset
0x18002eca5  xor     ecx, ecx; lpEventAttributes
0x18002eca7  call    cs:__imp_CreateEventW
0x18002ecae  nop     dword ptr [rax+rax+00h]
0x18002ecb3  mov     cs:?PolicyMgr@@3VCTLSPolicyMgr@@A, rax; CTLSPolicyMgr PolicyMgr
0x18002ecba  xor     r8d, r8d; lpName
0x18002ecbd  xor     edx, edx; bInitialOwner
0x18002ecbf  xor     ecx, ecx; lpMutexAttributes
0x18002ecc1  call    cs:__imp_CreateMutexW
0x18002ecc8  nop     dword ptr [rax+rax+00h]
0x18002eccd  mov     cs:qword_1800E9128, rax
0x18002ecd4  or      ebx, 0FFFFFFFFh
0x18002ecd7  xor     esi, esi
0x18002ecd9  cmp     cs:qword_1800E9130, rsi
0x18002ece0  jz      short loc_18002ED03
0x18002ece2  cmp     cs:?PolicyMgr@@3VCTLSPolicyMgr@@A, rsi; CTLSPolicyMgr PolicyMgr
0x18002ece9  jz      short loc_18002ED03
0x18002eceb  test    rax, rax
0x18002ecee  jz      short loc_18002ED03
0x18002ecf0  mov     cs:dword_1800E9138, ebx
0x18002ecf6  mov     cs:dword_1800E913C, ebx
0x18002ecfc  mov     cs:qword_1800E9140, rsi
0x18002ed03  lea     rbp, qword_1800E9148
0x18002ed0a  mov     [rsp+4A8h+var_448], rbp
0x18002ed0f  mov     cs:qword_1800E9148, rsi
0x18002ed16  mov     cs:qword_1800E9150, rsi
0x18002ed1d  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@V?$allocator@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__PolicyModule const,CTLSPolicy *>>>::_Buyheadnode(void)
0x18002ed22  mov     cs:qword_1800E9148, rax
0x18002ed29  xor     r9d, r9d; lpName
0x18002ed2c  xor     r8d, r8d; bInitialState
0x18002ed2f  mov     edx, edi; bManualReset
0x18002ed31  xor     ecx, ecx; lpEventAttributes
0x18002ed33  call    cs:__imp_CreateEventW
0x18002ed3a  nop     dword ptr [rax+rax+00h]
0x18002ed3f  mov     cs:qword_1800E9168, rax
0x18002ed46  xor     r9d, r9d; lpName
0x18002ed49  mov     r8d, edi; bInitialState
0x18002ed4c  xor     edx, edx; bManualReset
0x18002ed4e  xor     ecx, ecx; lpEventAttributes
0x18002ed50  call    cs:__imp_CreateEventW
0x18002ed57  nop     dword ptr [rax+rax+00h]
0x18002ed5c  mov     cs:qword_1800E9158, rax
0x18002ed63  xor     r8d, r8d; lpName
0x18002ed66  xor     edx, edx; bInitialOwner
0x18002ed68  xor     ecx, ecx; lpMutexAttributes
0x18002ed6a  call    cs:__imp_CreateMutexW
0x18002ed71  nop     dword ptr [rax+rax+00h]
0x18002ed76  mov     cs:qword_1800E9160, rax
0x18002ed7d  cmp     cs:qword_1800E9168, rsi
0x18002ed84  jz      short loc_18002EDA4
0x18002ed86  cmp     cs:qword_1800E9158, rsi
0x18002ed8d  jz      short loc_18002EDA4
0x18002ed8f  test    rax, rax
0x18002ed92  jz      short loc_18002EDA4
0x18002ed94  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x18002ed9c  movdqa  cs:xmmword_1800E9170, xmm0
0x18002eda4  lea     rax, qword_1800E9180
0x18002edab  mov     [rsp+4A8h+var_448], rax
0x18002edb0  mov     cs:qword_1800E9180, rsi
0x18002edb7  mov     cs:qword_1800E9188, rsi
0x18002edbe  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@V?$allocator@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__PolicyModule const,CTLSPolicy *>>>::_Buyheadnode(void)
0x18002edc3  mov     cs:qword_1800E9180, rax
0x18002edca  xor     r9d, r9d; lpName
0x18002edcd  xor     r8d, r8d; bInitialState
0x18002edd0  mov     edx, edi; bManualReset
0x18002edd2  xor     ecx, ecx; lpEventAttributes
0x18002edd4  call    cs:__imp_CreateEventW
0x18002eddb  nop     dword ptr [rax+rax+00h]
0x18002ede0  mov     cs:qword_1800E91A0, rax
0x18002ede7  xor     r9d, r9d; lpName
0x18002edea  mov     r8d, edi; bInitialState
0x18002eded  xor     edx, edx; bManualReset
0x18002edef  xor     ecx, ecx; lpEventAttributes
0x18002edf1  call    cs:__imp_CreateEventW
0x18002edf8  nop     dword ptr [rax+rax+00h]
0x18002edfd  mov     cs:qword_1800E9190, rax
0x18002ee04  xor     r8d, r8d; lpName
0x18002ee07  xor     edx, edx; bInitialOwner
0x18002ee09  xor     ecx, ecx; lpMutexAttributes
0x18002ee0b  call    cs:__imp_CreateMutexW
0x18002ee12  nop     dword ptr [rax+rax+00h]
0x18002ee17  mov     cs:qword_1800E9198, rax
0x18002ee1e  cmp     cs:qword_1800E91A0, rsi
0x18002ee25  jz      short loc_18002EE48
0x18002ee27  cmp     cs:qword_1800E9190, rsi
0x18002ee2e  jz      short loc_18002EE48
0x18002ee30  test    rax, rax
0x18002ee33  jz      short loc_18002EE48
0x18002ee35  mov     cs:dword_1800E91A8, ebx
0x18002ee3b  mov     cs:dword_1800E91AC, ebx
0x18002ee41  mov     cs:qword_1800E91B0, rsi
0x18002ee48  lea     rax, qword_1800E91B8
0x18002ee4f  mov     [rsp+4A8h+var_448], rax
0x18002ee54  mov     cs:qword_1800E91B8, rsi
0x18002ee5b  mov     cs:qword_1800E91C0, rsi
0x18002ee62  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBU__PolicyModule@@U__TranslationValue@@@std@@V?$allocator@U?$pair@$$CBU__PolicyModule@@U__TranslationValue@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU__PolicyModule@@U__TranslationValue@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__PolicyModule const,__TranslationValue>>>::_Buyheadnode(void)
0x18002ee67  mov     cs:qword_1800E91B8, rax
0x18002ee6e  mov     ebx, 200h
0x18002ee73  mov     r8d, ebx; Size
0x18002ee76  xor     edx, edx; Val
0x18002ee78  lea     rcx, [rsp+4A8h+Destination]; void *
0x18002ee80  call    memset_0
0x18002ee85  mov     r8d, ebx; Size
0x18002ee88  xor     edx, edx; Val
0x18002ee8a  lea     rcx, [rsp+4A8h+var_218]; void *
0x18002ee92  call    memset_0
0x18002ee97  mov     edi, 0FFh
0x18002ee9c  mov     r8d, edi; cchBufferMax
0x18002ee9f  lea     rdx, ?g_szDefPolCompanyName@@3PAGA; lpBuffer
0x18002eea6  mov     ebx, 78h ; 'x'
0x18002eeab  mov     ecx, ebx; uID
0x18002eead  call    LoadResourceString
0x18002eeb2  mov     r8d, edi; cchBufferMax
0x18002eeb5  lea     rdx, ?g_szDefProductId@@3PAGA; lpBuffer
0x18002eebc  mov     ecx, ebx; uID
0x18002eebe  call    LoadResourceString
0x18002eec3  lea     r8, ?g_szDefPolCompanyName@@3PAGA; Source
0x18002eeca  lea     ebx, [rdi+1]
0x18002eecd  mov     edx, ebx; SizeInWords
0x18002eecf  lea     rcx, [rsp+4A8h+Destination]; Destination
0x18002eed7  call    cs:__imp_wcscpy_s
0x18002eede  nop     dword ptr [rax+rax+00h]
0x18002eee3  lea     r8, ?g_szDefProductId@@3PAGA; Source
0x18002eeea  mov     edx, ebx; SizeInWords
0x18002eeec  lea     rcx, [rsp+4A8h+var_218]; Destination
0x18002eef4  call    cs:__imp_wcscpy_s
0x18002eefb  nop     dword ptr [rax+rax+00h]
0x18002ef00  mov     ecx, 658h; Size
0x18002ef05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ef0a  mov     rbx, rax
0x18002ef0d  mov     [rsp+4A8h+var_428], rax
0x18002ef15  test    rax, rax
0x18002ef18  jz      short loc_18002EF47
0x18002ef1a  mov     [rax], rsi
0x18002ef1d  mov     [rax+8], rsi
0x18002ef21  mov     [rax+10h], rsi
0x18002ef25  mov     [rax+18h], rsi
0x18002ef29  mov     [rax+20h], rsi
0x18002ef2d  mov     [rax+28h], rsi
0x18002ef31  mov     [rax+30h], rsi
0x18002ef35  mov     [rax+38h], rsi
0x18002ef39  mov     [rax+40h], rsi
0x18002ef3d  mov     [rax+48h], rsi
0x18002ef41  mov     [rax+50h], rsi
0x18002ef45  jmp     short loc_18002EF4A
0x18002ef47  mov     rbx, rsi
0x18002ef4a  test    rbx, rbx
0x18002ef4d  jz      short loc_18002EF57
0x18002ef4f  mov     rcx, rbx; this
0x18002ef52  call    ?CreatePolicy@CTLSPolicy@@AEAAXPEAUHINSTANCE__@@PEBG1P6A?AW4POLICYSTATUS@@PEAXPEAT_ULARGE_INTEGER@@PEAU__PMLICENSETOBERETURN@@PEAK5@ZP6A?AW43@2KH2PEAPEAX5K@ZP6A?AW43@2K275@ZP6A?AW43@1115@ZP6A?AW43@1115@ZP6A?AW43@2K225@ZP6A?AW43@7@Z@Z; CTLSPolicy::CreatePolicy(HINSTANCE__ *,ushort const *,ushort const *,POLICYSTATUS (*)(void *,_ULARGE_INTEGER *,__PMLICENSETOBERETURN *,ulong *,ulong *),POLICYSTATUS (*)(void *,ulong,int,void *,void * *,ulong *,ulong),POLICYSTATUS (*)(void *,ulong,void *,void * *,ulong *),POLICYSTATUS (*)(ushort const *,ushort const *,ushort const *,ulong *),POLICYSTATUS (*)(ushort const *,ushort const *,ushort const *,ulong *),POLICYSTATUS (*)(void *,ulong,void *,void *,ulong *),POLICYSTATUS (*)(void * *))
0x18002ef57  lea     rdx, [rsp+4A8h+Destination]
0x18002ef5f  mov     rcx, rbp
0x18002ef62  call    ??A?$map@U__PolicyModule@@PEAVCTLSPolicy@@U?$less@U__PolicyModule@@@std@@V?$allocator@U?$pair@$$CBU__PolicyModule@@PEAVCTLSPolicy@@@std@@@4@@std@@QEAAAEAPEAVCTLSPolicy@@AEBU__PolicyModule@@@Z; std::map<__PolicyModule,CTLSPolicy *>::operator[](__PolicyModule const &)
0x18002ef67  mov     [rax], rbx
0x18002ef6a  mov     rax, r14
0x18002ef6d  mov     rcx, [rsp+4A8h+var_18]
0x18002ef75  xor     rcx, rsp; StackCookie
0x18002ef78  call    __security_check_cookie
0x18002ef7d  lea     r11, [rsp+4A8h+var_8]
0x18002ef85  mov     rbx, [r11+10h]
0x18002ef89  mov     rbp, [r11+18h]
0x18002ef8d  mov     rsi, [r11+20h]
0x18002ef91  mov     rdi, [r11+28h]
0x18002ef95  mov     rsp, r11
0x18002ef98  pop     r14
0x18002ef9a  retn
```
