# AddEntryInLookupCache(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,void *,ulong,ushort const *,ushort const *)

- ea: `0x18000477c`
- end: `0x180004983`
- name: `?AddEntryInLookupCache@@YAJPEAUHKEY__@@0PEBG11PEAXK11@Z`
- size: `519`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, PSID SourceSid, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180048e60`

## callees

- `0x18000477c`
- `0x180004e80`
- `0x180007fc0`
- `0x18000a600`
- `0x18004e1b8`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180004822`
- `ntdll!RtlReleaseResource` at `0x1800048b5`
- `ntdll!RtlReleaseResource` at `0x180004822`
- `ntdll!RtlReleaseResource` at `0x1800048b5`
- `ntdll!RtlAcquireResourceShared` at `0x1800047b2`
- `ntdll!RtlAcquireResourceShared` at `0x1800047b2`

## string_xrefs

- `0x18000485a`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180004902`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18000493e`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180004878`: `_AddEntryInLookupCache`
- `0x180004920`: `_AddEntryInLookupCache(SubPkg)`
- `0x180004965`: `FlushIdentityCache`

## pseudocode

```c
__int64 __fastcall AddEntryInLookupCache(
        HKEY hKey,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        PSID SourceSid,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9)
{
  unsigned int v13; // ebx
  const char *v15; // r9
  const char *v16; // rax
  int v17; // r8d
  const char *v18; // r10
  const char *v19; // rax
  void *v20; // [rsp+20h] [rbp-88h]
  int v21; // [rsp+50h] [rbp-58h] BYREF
  int v22[21]; // [rsp+54h] [rbp-54h] BYREF

  v21 = 0;
  v22[0] = 0;
  RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
  v13 = _AddEntryInLookupCache(hKey, a3, a4, a5, SourceSid, a7, a8, a9, &v21);
  if ( v13 )
  {
    v15 = "";
    do
      v16 = v15--;
    while ( *v15 != 92 && v15 > "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" );
    v17 = 2289;
    v18 = "_AddEntryInLookupCache";
LABEL_11:
    if ( *v15 == 92 )
      v15 = v16;
    LODWORD(v20) = v17;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v15, v20, v18, &Class);
    RtlReleaseResource(&g_LookupsCacheLock);
    return v13;
  }
  if ( a2 )
  {
    v13 = _AddEntryInLookupCache(a2, a3, a4, a5, SourceSid, a7, a8, a9, v22);
    if ( v13 )
    {
      v15 = "";
      do
        v16 = v15--;
      while ( *v15 != 92 && v15 > "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" );
      v17 = 2304;
      v18 = "_AddEntryInLookupCache(SubPkg)";
      goto LABEL_11;
    }
  }
  RtlReleaseResource(&g_LookupsCacheLock);
  if ( (v21 || v22[0]) && (v13 = FlushIdentityCache(SourceSid)) != 0 )
  {
    v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(v20) = 2313;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v13, v19, v20, "FlushIdentityCache", &Class);
  }
  else
  {
    return 0;
  }
  return v13;
}

```

## disassembly

```asm
0x18000477c  push    rbx
0x18000477e  push    rbp
0x18000477f  push    rsi
0x180004780  push    rdi
0x180004781  push    r12
0x180004783  push    r13
0x180004785  push    r14
0x180004787  push    r15
0x180004789  sub     rsp, 68h
0x18000478d  mov     rsi, rdx
0x180004790  mov     [rsp+0A8h+var_58], 0
0x180004798  mov     rbx, rcx
0x18000479b  mov     [rsp+0A8h+var_54], 0
0x1800047a3  mov     dl, 1; Wait
0x1800047a5  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800047ac  mov     rbp, r9
0x1800047af  mov     r14, r8
0x1800047b2  call    cs:__imp_RtlAcquireResourceShared
0x1800047b8  mov     r15, [rsp+0A8h+arg_40]
0x1800047c0  lea     rax, [rsp+0A8h+var_58]
0x1800047c5  mov     r12, [rsp+0A8h+arg_38]
0x1800047cd  mov     r8, rbp; unsigned __int16 *
0x1800047d0  mov     r13d, [rsp+0A8h+arg_30]
0x1800047d8  mov     rdx, r14; unsigned __int16 *
0x1800047db  mov     rdi, [rsp+0A8h+SourceSid]
0x1800047e3  mov     rcx, rbx; hKey
0x1800047e6  mov     r9, [rsp+0A8h+arg_20]; unsigned __int16 *
0x1800047ee  mov     [rsp+0A8h+var_68], rax; int *
0x1800047f3  mov     [rsp+0A8h+var_70], r15; unsigned __int16 *
0x1800047f8  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x1800047fd  mov     [rsp+0A8h+var_80], r13d; unsigned int
0x180004802  mov     [rsp+0A8h+var_88], rdi; void *
0x180004807  call    ?_AddEntryInLookupCache@@YAJPEAUHKEY__@@PEBG11PEAXK11PEAH@Z; _AddEntryInLookupCache(HKEY__ *,ushort const *,ushort const *,ushort const *,void *,ulong,ushort const *,ushort const *,int *)
0x18000480c  mov     ebx, eax
0x18000480e  test    eax, eax
0x180004810  jnz     short loc_180004853
0x180004812  test    rsi, rsi
0x180004815  jnz     loc_1800048BD
0x18000481b  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180004822  call    cs:__imp_RtlReleaseResource
0x180004828  cmp     [rsp+0A8h+var_58], 0
0x18000482d  jnz     loc_18000492C
0x180004833  cmp     [rsp+0A8h+var_54], 0
0x180004838  jnz     loc_18000492C
0x18000483e  xor     ebx, ebx
0x180004840  mov     eax, ebx
0x180004842  add     rsp, 68h
0x180004846  pop     r15
0x180004848  pop     r14
0x18000484a  pop     r13
0x18000484c  pop     r12
0x18000484e  pop     rdi
0x18000484f  pop     rsi
0x180004850  pop     rbp
0x180004851  pop     rbx
0x180004852  retn
0x180004853  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x18000485a  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180004861  mov     rax, r9
0x180004864  dec     r9
0x180004867  cmp     byte ptr [r9], 5Ch ; '\'
0x18000486b  jz      short loc_180004872
0x18000486d  cmp     r9, rcx
0x180004870  ja      short loc_180004861
0x180004872  mov     r8d, 8F1h
0x180004878  lea     r10, aAddentryinlook_2; "_AddEntryInLookupCache"
0x18000487f  xor     ecx, ecx
0x180004881  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180004888  cmp     byte ptr [r9], 5Ch ; '\'
0x18000488c  cmovz   r9, rax
0x180004890  lea     rax, Class
0x180004897  mov     [rsp+0A8h+var_78], rax
0x18000489c  mov     qword ptr [rsp+0A8h+var_80], r10
0x1800048a1  mov     dword ptr [rsp+0A8h+var_88], r8d
0x1800048a6  mov     r8d, ebx
0x1800048a9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800048ae  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1800048b5  call    cs:__imp_RtlReleaseResource
0x1800048bb  jmp     short loc_180004840
0x1800048bd  mov     r9, [rsp+0A8h+arg_20]; unsigned __int16 *
0x1800048c5  lea     rax, [rsp+0A8h+var_54]
0x1800048ca  mov     [rsp+0A8h+var_68], rax; int *
0x1800048cf  mov     r8, rbp; unsigned __int16 *
0x1800048d2  mov     [rsp+0A8h+var_70], r15; unsigned __int16 *
0x1800048d7  mov     rdx, r14; unsigned __int16 *
0x1800048da  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x1800048df  mov     rcx, rsi; hKey
0x1800048e2  mov     [rsp+0A8h+var_80], r13d; unsigned int
0x1800048e7  mov     [rsp+0A8h+var_88], rdi; void *
0x1800048ec  call    ?_AddEntryInLookupCache@@YAJPEAUHKEY__@@PEBG11PEAXK11PEAH@Z; _AddEntryInLookupCache(HKEY__ *,ushort const *,ushort const *,ushort const *,void *,ulong,ushort const *,ushort const *,int *)
0x1800048f1  mov     ebx, eax
0x1800048f3  test    eax, eax
0x1800048f5  jz      loc_18000481B
0x1800048fb  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x180004902  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180004909  mov     rax, r9
0x18000490c  dec     r9
0x18000490f  cmp     byte ptr [r9], 5Ch ; '\'
0x180004913  jz      short loc_18000491A
0x180004915  cmp     r9, rcx
0x180004918  ja      short loc_180004909
0x18000491a  mov     r8d, 900h
0x180004920  lea     r10, aAddentryinlook_1; "_AddEntryInLookupCache(SubPkg)"
0x180004927  jmp     loc_18000487F
0x18000492c  mov     rcx, rdi; SourceSid
0x18000492f  call    ?FlushIdentityCache@@YAJPEAX@Z; FlushIdentityCache(void *)
0x180004934  mov     ebx, eax
0x180004936  test    eax, eax
0x180004938  jz      loc_18000483E
0x18000493e  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x180004945  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000494a  mov     r9, rax
0x18000494d  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180004954  lea     rax, Class
0x18000495b  mov     r8d, ebx
0x18000495e  mov     [rsp+0A8h+var_78], rax
0x180004963  xor     ecx, ecx
0x180004965  lea     rax, aFlushidentityc_0; "FlushIdentityCache"
0x18000496c  mov     qword ptr [rsp+0A8h+var_80], rax
0x180004971  mov     dword ptr [rsp+0A8h+var_88], 909h
0x180004979  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000497e  jmp     loc_180004840
```
