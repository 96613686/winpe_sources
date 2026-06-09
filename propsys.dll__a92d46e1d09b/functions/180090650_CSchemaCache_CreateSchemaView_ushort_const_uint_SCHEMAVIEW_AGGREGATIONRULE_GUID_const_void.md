# CSchemaCache::CreateSchemaView(ushort const * *,uint,SCHEMAVIEW_AGGREGATIONRULE,_GUID const &,void * *)

- ea: `0x180090650`
- end: `0x1800907a3`
- name: `?CreateSchemaView@CSchemaCache@@UEAAJPEAPEBGIW4SCHEMAVIEW_AGGREGATIONRULE@@AEBU_GUID@@PEAPEAX@Z`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180035af0`
- `0x180037c70`
- `0x1800394e0`
- `0x1800395b0`
- `0x18006ed20`
- `0x18007c440`
- `0x180090650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009074a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009074a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800906ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800906ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090777`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090777`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSchemaCache::CreateSchemaView(
        CGlobalMappingData **a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned int v9; // edi
  int CachedSchemaRegistrationForURI; // ebx
  char *v11; // rcx
  _OWORD *v12; // rdx
  struct CACHED_SCHEMA_REGISTRATION *v14; // [rsp+20h] [rbp-40h] BYREF
  _DWORD v15[2]; // [rsp+28h] [rbp-38h] BYREF
  CGlobalMappingData **v16; // [rsp+30h] [rbp-30h]
  LPVOID pv[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v18; // [rsp+48h] [rbp-18h]

  v9 = 0;
  *a6 = 0;
  v15[0] = a4;
  v15[1] = 0;
  v16 = a1;
  pv[0] = 0;
  pv[1] = 0;
  v18 = 0u;
  EnterCriticalSection(&CSchemaCache::s_critsec);
  CachedSchemaRegistrationForURI = CSchemaCache::_EnsureGlobalMappingLoaded((CSchemaCache *)a1, 0);
  if ( CachedSchemaRegistrationForURI >= 0 )
  {
    while ( 1 )
    {
      if ( v9 >= a3 )
        goto LABEL_10;
      v14 = 0;
      CachedSchemaRegistrationForURI = CGlobalMappingData::GetCachedSchemaRegistrationForURI(
                                         a1[3],
                                         *(const unsigned __int16 **)(a2 + 8LL * v9),
                                         &v14);
      if ( CachedSchemaRegistrationForURI >= 0 )
      {
        CachedSchemaRegistrationForURI = 0;
        v11 = (char *)pv[1];
        if ( pv[1] != *((LPVOID *)&v18 + 1) )
          goto LABEL_7;
        CachedSchemaRegistrationForURI = CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_EnsureCapacity(
                                           pv,
                                           (char *)pv[1] + 1);
        if ( CachedSchemaRegistrationForURI >= 0 )
          break;
      }
LABEL_9:
      ++v9;
      if ( CachedSchemaRegistrationForURI < 0 )
        goto LABEL_10;
    }
    v11 = (char *)pv[1];
LABEL_7:
    pv[1] = v11 + 1;
    v12 = (char *)pv[0] + 16 * (_QWORD)(v11 + 1) - 16;
    if ( v12 )
      *v12 = *(_OWORD *)v14;
    goto LABEL_9;
  }
LABEL_10:
  LeaveCriticalSection(&CSchemaCache::s_critsec);
  if ( CachedSchemaRegistrationForURI >= 0 )
    CachedSchemaRegistrationForURI = CSchemaObject<ISchemaView,CSchemaView,SCHEMA_VIEW_INIT>::CreateInstance(
                                       a5,
                                       a6,
                                       v15);
  CSchemaCache::_FlushPendingNotifications((CSchemaCache *)a1);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  return (unsigned int)CachedSchemaRegistrationForURI;
}

```

## disassembly

```asm
0x180090650  mov     [rsp-38h+arg_10], rbx
0x180090655  push    rbp
0x180090656  push    rsi
0x180090657  push    rdi
0x180090658  push    r12
0x18009065a  push    r13
0x18009065c  push    r14
0x18009065e  push    r15
0x180090660  mov     rbp, rsp
0x180090663  sub     rsp, 60h
0x180090667  mov     rax, cs:__security_cookie
0x18009066e  xor     rax, rsp
0x180090671  mov     [rbp+var_8], rax
0x180090675  mov     r15d, r8d
0x180090678  mov     r13, rdx
0x18009067b  mov     rsi, rcx
0x18009067e  mov     r12, [rbp+arg_20]
0x180090682  mov     r14, [rbp+arg_28]
0x180090686  xor     edi, edi
0x180090688  mov     [r14], rdi
0x18009068b  mov     [rbp+var_38], r9d
0x18009068f  xor     eax, eax
0x180090691  mov     [rbp+var_34], eax
0x180090694  mov     [rbp+var_30], rcx
0x180090698  xorps   xmm0, xmm0
0x18009069b  movups  xmmword ptr [rbp+pv], xmm0
0x18009069f  movups  [rbp+var_18], xmm0
0x1800906a3  mov     [rbp+pv], rdi
0x1800906a7  mov     [rbp+pv+8], rdi
0x1800906ab  mov     qword ptr [rbp+var_18], rdi
0x1800906af  mov     qword ptr [rbp+var_18+8], rdi
0x1800906b3  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x1800906ba  call    cs:__imp_EnterCriticalSection
0x1800906c0  xor     edx, edx; int
0x1800906c2  mov     rcx, rsi; this
0x1800906c5  call    ?_EnsureGlobalMappingLoaded@CSchemaCache@@AEAAJH@Z; CSchemaCache::_EnsureGlobalMappingLoaded(int)
0x1800906ca  mov     ebx, eax
0x1800906cc  test    eax, eax
0x1800906ce  js      short loc_180090743
0x1800906d0  cmp     edi, r15d
0x1800906d3  jnb     short loc_180090743
0x1800906d5  mov     [rbp+var_40], 0
0x1800906dd  mov     edx, edi
0x1800906df  lea     r8, [rbp+var_40]; struct CACHED_SCHEMA_REGISTRATION **
0x1800906e3  mov     rdx, [r13+rdx*8+0]; unsigned __int16 *
0x1800906e8  mov     rcx, [rsi+18h]; this
0x1800906ec  call    ?GetCachedSchemaRegistrationForURI@CGlobalMappingData@@QEAAJPEBGPEAPEBUCACHED_SCHEMA_REGISTRATION@@@Z; CGlobalMappingData::GetCachedSchemaRegistrationForURI(ushort const *,CACHED_SCHEMA_REGISTRATION const * *)
0x1800906f1  mov     ebx, eax
0x1800906f3  test    eax, eax
0x1800906f5  js      short loc_18009073D
0x1800906f7  xor     ebx, ebx
0x1800906f9  mov     rcx, [rbp+pv+8]
0x1800906fd  cmp     rcx, qword ptr [rbp+var_18+8]
0x180090701  jnz     short loc_18009071A
0x180090703  lea     rdx, [rcx+1]
0x180090707  lea     rcx, [rbp+pv]
0x18009070b  call    ?_EnsureCapacity@?$CTSimpleArray@U_GUID@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@U_GUID@@@@V?$CSimpleArrayStandardCompareHelper@U_GUID@@@@V?$CSimpleArrayStandardMergeHelper@U_GUID@@@@@@QEAAJ_K0@Z; CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180090710  mov     ebx, eax
0x180090712  test    eax, eax
0x180090714  js      short loc_18009073D
0x180090716  mov     rcx, [rbp+pv+8]
0x18009071a  inc     rcx
0x18009071d  mov     [rbp+pv+8], rcx
0x180090721  shl     rcx, 4
0x180090725  mov     rdx, [rbp+pv]
0x180090729  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18009072d  add     rdx, rcx
0x180090730  jz      short loc_18009073D
0x180090732  mov     rax, [rbp+var_40]
0x180090736  movups  xmm0, xmmword ptr [rax]
0x180090739  movdqu  xmmword ptr [rdx], xmm0
0x18009073d  inc     edi
0x18009073f  test    ebx, ebx
0x180090741  jns     short loc_1800906D0
0x180090743  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x18009074a  call    cs:__imp_LeaveCriticalSection
0x180090750  test    ebx, ebx
0x180090752  js      short loc_180090765
0x180090754  lea     r8, [rbp+var_38]
0x180090758  mov     rdx, r14
0x18009075b  mov     rcx, r12
0x18009075e  call    ?CreateInstance@?$CSchemaObject@UISchemaView@@VCSchemaView@@USCHEMA_VIEW_INIT@@@@SAJAEBU_GUID@@PEAPEAXPEBUSCHEMA_VIEW_INIT@@@Z; CSchemaObject<ISchemaView,CSchemaView,SCHEMA_VIEW_INIT>::CreateInstance(_GUID const &,void * *,SCHEMA_VIEW_INIT const *)
0x180090763  mov     ebx, eax
0x180090765  mov     rcx, rsi; this
0x180090768  call    ?_FlushPendingNotifications@CSchemaCache@@AEAAJXZ; CSchemaCache::_FlushPendingNotifications(void)
0x18009076d  nop
0x18009076e  mov     rcx, [rbp+pv]; pv
0x180090772  test    rcx, rcx
0x180090775  jz      short loc_18009077D
0x180090777  call    cs:__imp_CoTaskMemFree
0x18009077d  mov     eax, ebx
0x18009077f  mov     rcx, [rbp+var_8]
0x180090783  xor     rcx, rsp; StackCookie
0x180090786  call    __security_check_cookie
0x18009078b  mov     rbx, [rsp+60h+arg_10]
0x180090793  add     rsp, 60h
0x180090797  pop     r15
0x180090799  pop     r14
0x18009079b  pop     r13
0x18009079d  pop     r12
0x18009079f  pop     rdi
0x1800907a0  pop     rsi
0x1800907a1  pop     rbp
0x1800907a2  retn
```
