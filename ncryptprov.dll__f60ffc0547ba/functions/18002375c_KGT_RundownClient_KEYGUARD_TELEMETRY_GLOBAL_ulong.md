# KGT_RundownClient(KEYGUARD_TELEMETRY_GLOBAL *,ulong)

- ea: `0x18002375c`
- end: `0x18002389c`
- name: `?KGT_RundownClient@@YAXPEAUKEYGUARD_TELEMETRY_GLOBAL@@K@Z`
- size: `320`
- prototype: `void __fastcall(struct KEYGUARD_TELEMETRY_GLOBAL *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800236d0`

## callees

- `0x18001a0cc`
- `0x18001ba54`
- `0x18001bc6c`
- `0x18002375c`
- `0x180028a70`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180023799`
- `ntdll!RtlLeaveCriticalSection` at `0x180023799`
- `ntdll!RtlEnterCriticalSection` at `0x18002376c`
- `ntdll!RtlEnterCriticalSection` at `0x18002376c`
- `ntdll!RtlDllShutdownInProgress` at `0x1800237ca`
- `ntdll!RtlDllShutdownInProgress` at `0x1800237ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800237b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800237b5`

## pseudocode

```c
void __fastcall KGT_RundownClient(struct _RTL_CRITICAL_SECTION *a1, unsigned int a2)
{
  struct KEYGUARD_TELEMETRY_PID *Pid; // rax
  struct KEYGUARD_TELEMETRY_PID *v5; // rbx
  int **v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ecx
  int v10; // r8d
  bool v11; // zf
  int *v12; // rax
  __int64 v13; // [rsp+50h] [rbp-20h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h] BYREF
  __int64 v16; // [rsp+68h] [rbp-8h] BYREF
  __int64 v17; // [rsp+90h] [rbp+20h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+30h] BYREF
  int *v19; // [rsp+A8h] [rbp+38h] BYREF

  RtlEnterCriticalSection(a1);
  Pid = KGT_GetPid((struct KEYGUARD_TELEMETRY_GLOBAL *)a1, a2);
  v5 = Pid;
  if ( Pid )
    std::_Hash<std::_Umap_traits<unsigned long,KEYGUARD_TELEMETRY_PID *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,KEYGUARD_TELEMETRY_PID *>>,0>>::_Erase<unsigned long>(
      &a1[2],
      Pid);
  RtlLeaveCriticalSection(a1);
  if ( v5 )
  {
    v6 = (int **)*((_QWORD *)v5 + 2);
    LocalFree(v5);
    if ( v6 )
    {
      if ( !RtlDllShutdownInProgress()
        && dword_180079160
        && (unsigned __int8)tlgKeywordOn(&dword_180079160, 0x400000000000LL, v7, v8) )
      {
        v11 = *v6 == 0;
        v12 = &dword_18006B48C;
        v17 = 0x2000000;
        if ( !v11 )
          v12 = *v6;
        v19 = v12;
        v18 = 0x1000000;
        v13 = 0;
        v14 = -1;
        v15 = 0;
        v16 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v9,
          (unsigned int)&word_18006FD8E,
          v10,
          (unsigned int)&v16,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v13,
          (__int64)&v19,
          (__int64)&v18,
          (__int64)&v17);
      }
    }
  }
}

```

## disassembly

```asm
0x18002375c  push    rbp
0x18002375e  push    rbx
0x18002375f  push    rdi
0x180023760  mov     rbp, rsp
0x180023763  sub     rsp, 70h
0x180023767  mov     ebx, edx
0x180023769  mov     rdi, rcx
0x18002376c  call    cs:__imp_RtlEnterCriticalSection
0x180023773  nop     dword ptr [rax+rax+00h]
0x180023778  mov     edx, ebx; unsigned int
0x18002377a  mov     rcx, rdi; struct KEYGUARD_TELEMETRY_GLOBAL *
0x18002377d  call    ?KGT_GetPid@@YAPEAUKEYGUARD_TELEMETRY_PID@@PEAUKEYGUARD_TELEMETRY_GLOBAL@@K@Z; KGT_GetPid(KEYGUARD_TELEMETRY_GLOBAL *,ulong)
0x180023782  mov     rbx, rax
0x180023785  test    rax, rax
0x180023788  jz      short loc_180023796
0x18002378a  lea     rcx, [rdi+50h]
0x18002378e  mov     rdx, rax
0x180023791  call    ??$_Erase@K@?$_Hash@V?$_Umap_traits@KPEAUKEYGUARD_TELEMETRY_PID@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUKEYGUARD_TELEMETRY_PID@@@std@@@3@$0A@@std@@@std@@AEAA_KAEBK@Z; std::_Hash<std::_Umap_traits<ulong,KEYGUARD_TELEMETRY_PID *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,KEYGUARD_TELEMETRY_PID *>>,0>>::_Erase<ulong>(ulong const &)
0x180023796  mov     rcx, rdi; CriticalSection
0x180023799  call    cs:__imp_RtlLeaveCriticalSection
0x1800237a0  nop     dword ptr [rax+rax+00h]
0x1800237a5  test    rbx, rbx
0x1800237a8  jz      loc_180023893
0x1800237ae  mov     rdi, [rbx+10h]
0x1800237b2  mov     rcx, rbx; hMem
0x1800237b5  call    cs:__imp_LocalFree
0x1800237bc  nop     dword ptr [rax+rax+00h]
0x1800237c1  test    rdi, rdi
0x1800237c4  jz      loc_180023893
0x1800237ca  call    cs:__imp_RtlDllShutdownInProgress
0x1800237d1  nop     dword ptr [rax+rax+00h]
0x1800237d6  test    al, al
0x1800237d8  jnz     loc_180023893
0x1800237de  mov     eax, cs:dword_180079160
0x1800237e4  test    eax, eax
0x1800237e6  jz      loc_180023893
0x1800237ec  mov     rdx, 400000000000h
0x1800237f6  lea     rcx, dword_180079160
0x1800237fd  call    _tlgKeywordOn
0x180023802  test    al, al
0x180023804  jz      loc_180023893
0x18002380a  cmp     qword ptr [rdi], 0
0x18002380e  lea     rax, dword_18006B48C
0x180023815  lea     r9, [rbp+var_8]
0x180023819  mov     [rbp+arg_0], 2000000h
0x180023821  cmovnz  rax, [rdi]
0x180023825  lea     rdx, word_18006FD8E
0x18002382c  mov     [rbp+arg_18], rax
0x180023830  lea     rax, [rbp+arg_0]
0x180023834  mov     [rsp+70h+var_28], rax
0x180023839  lea     rax, [rbp+arg_10]
0x18002383d  mov     [rsp+70h+var_30], rax
0x180023842  lea     rax, [rbp+arg_18]
0x180023846  mov     [rsp+70h+var_38], rax
0x18002384b  lea     rax, [rbp+var_20]
0x18002384f  mov     [rsp+70h+var_40], rax
0x180023854  lea     rax, [rbp+var_18]
0x180023858  mov     [rsp+70h+var_48], rax
0x18002385d  lea     rax, [rbp+var_10]
0x180023861  mov     [rsp+70h+var_50], rax
0x180023866  mov     [rbp+arg_10], 1000000h
0x18002386e  mov     [rbp+var_20], 0
0x180023876  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x18002387e  mov     [rbp+var_10], 0
0x180023886  mov     [rbp+var_8], 0
0x18002388e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@222AEBU?$_tlgWrapSz@G@@22@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180023893  add     rsp, 70h
0x180023897  pop     rdi
0x180023898  pop     rbx
0x180023899  pop     rbp
0x18002389a  retn
```
