# myGetSidFromDomain(ushort *,void * *)

- ea: `0x18002a290`
- end: `0x18002a467`
- name: `?myGetSidFromDomain@@YAKPEAGPEAPEAX@Z`
- size: `471`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002ffbc`
- `0x1800328a4`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000dce0`
- `0x18000eac0`
- `0x18002a1a4`
- `0x18002a290`
- `0x18002a530`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a2c6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a35b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a391`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a3c6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a3f4`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a426`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a432`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a2c6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a35b`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a391`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a3c6`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a3f4`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a426`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x18002a432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a2db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a446`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a451`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a451`

## pseudocode

```c
__int64 __fastcall myGetSidFromDomain(unsigned __int16 *a1, void **a2)
{
  void (*v5)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  const unsigned __int16 *v6; // rcx
  int TargetMachineDomainDnsName; // eax
  unsigned int v8; // edi
  unsigned int v9; // ecx
  int DomainSidInCache; // eax
  int updated; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-28h]
  int v14; // [rsp+24h] [rbp-24h]
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF
  void (*v16)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+68h] [rbp+20h]

  hMem = 0;
  if ( !g_fInitDone )
    return 2147943514LL;
  v5 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v16 = v5;
  EnterCriticalSection(&g_csDomainSidCache);
  if ( a1 )
    goto LABEL_14;
  v14 = 0;
  v6 = (const unsigned __int16 *)g_pwszEnterpriseRoot;
  if ( !g_pwszEnterpriseRoot )
  {
    TargetMachineDomainDnsName = myGetTargetMachineDomainDnsName(0, 0, 0, (unsigned __int16 **)&g_pwszEnterpriseRoot);
    v8 = TargetMachineDomainDnsName;
    v14 = TargetMachineDomainDnsName;
    if ( TargetMachineDomainDnsName )
    {
      v9 = 34800422;
LABEL_10:
      CSPrintErrorLineFile(v9, TargetMachineDomainDnsName);
      goto LABEL_11;
    }
    v6 = (const unsigned __int16 *)g_pwszEnterpriseRoot;
  }
  TargetMachineDomainDnsName = myDupString(v6, (unsigned __int16 **)&hMem);
  v8 = TargetMachineDomainDnsName;
  v14 = TargetMachineDomainDnsName;
  if ( TargetMachineDomainDnsName )
  {
    v9 = 34997030;
    goto LABEL_10;
  }
LABEL_11:
  v13 = v8;
  if ( v8 )
  {
    CSPrintErrorLineFile(0x1510326u, v8);
    _set_se_translator(v5);
    goto LABEL_24;
  }
  a1 = (unsigned __int16 *)hMem;
LABEL_14:
  DomainSidInCache = myFindDomainSidInCache(a1, a2);
  v8 = DomainSidInCache;
  v13 = DomainSidInCache;
  if ( !DomainSidInCache )
  {
    if ( !*a2 )
    {
      updated = myUpdateDomainSidCache();
      v8 = updated;
      v13 = updated;
      if ( updated )
      {
        CSPrintErrorLineFile(0x15D0326u, updated);
        _set_se_translator(v5);
        goto LABEL_24;
      }
      v12 = myFindDomainSidInCache(a1, a2);
      v8 = v12;
      v13 = v12;
      if ( v12 )
      {
        CSPrintErrorLineFile(0x1600326u, v12);
        _set_se_translator(v5);
        goto LABEL_24;
      }
      if ( !*a2 )
      {
        v8 = -2147467259;
        v13 = -2147467259;
        CSPrintErrorLineFileData2(a1, 0x1650326u, -2147467259, 0);
        _set_se_translator(v5);
        goto LABEL_24;
      }
    }
    _set_se_translator(v5);
    goto LABEL_24;
  }
  CSPrintErrorLineFile(0x1570326u, DomainSidInCache);
  _set_se_translator(v5);
LABEL_24:
  LeaveCriticalSection(&g_csDomainSidCache);
  LocalFree(hMem);
  return v8;
}

```

## disassembly

```asm
0x18002a290  mov     [rsp+arg_0], rbx
0x18002a295  push    rsi
0x18002a296  push    rdi
0x18002a297  push    r14
0x18002a299  sub     rsp, 30h
0x18002a29d  mov     r14, rdx
0x18002a2a0  mov     rsi, rcx
0x18002a2a3  mov     [rsp+48h+hMem], 0
0x18002a2ac  cmp     cs:?g_fInitDone@@3HA, 0; int g_fInitDone
0x18002a2b3  jnz     short loc_18002A2BF
0x18002a2b5  mov     eax, 8007045Ah
0x18002a2ba  jmp     loc_18002A459
0x18002a2bf  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x18002a2c6  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a2cc  mov     rbx, rax
0x18002a2cf  mov     [rsp+48h+arg_18], rax
0x18002a2d4  lea     rcx, ?g_csDomainSidCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002a2db  call    cs:__imp_EnterCriticalSection
0x18002a2e1  test    rsi, rsi
0x18002a2e4  jnz     loc_18002A36C
0x18002a2ea  mov     [rsp+48h+var_24], esi
0x18002a2ee  mov     rcx, cs:?g_pwszEnterpriseRoot@@3PEAGEA; lpString
0x18002a2f5  test    rcx, rcx
0x18002a2f8  jnz     short loc_18002A323
0x18002a2fa  lea     r9, ?g_pwszEnterpriseRoot@@3PEAGEA; unsigned __int16 **
0x18002a301  xor     r8d, r8d; unsigned __int16 **
0x18002a304  xor     edx, edx; unsigned __int16 **
0x18002a306  call    ?myGetTargetMachineDomainDnsName@@YAJPEBGPEAPEAG11@Z; myGetTargetMachineDomainDnsName(ushort const *,ushort * *,ushort * *,ushort * *)
0x18002a30b  mov     edi, eax
0x18002a30d  mov     [rsp+48h+var_24], eax
0x18002a311  test    eax, eax
0x18002a313  jz      short loc_18002A31C
0x18002a315  mov     ecx, 2130326h
0x18002a31a  jmp     short loc_18002A33C
0x18002a31c  mov     rcx, cs:?g_pwszEnterpriseRoot@@3PEAGEA; Src
0x18002a323  lea     rdx, [rsp+48h+hMem]; unsigned __int16 **
0x18002a328  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18002a32d  mov     edi, eax
0x18002a32f  mov     [rsp+48h+var_24], eax
0x18002a333  test    eax, eax
0x18002a335  jz      short loc_18002A343
0x18002a337  mov     ecx, 2160326h; unsigned int
0x18002a33c  mov     edx, eax; int
0x18002a33e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a343  mov     [rsp+48h+var_28], edi
0x18002a347  test    edi, edi
0x18002a349  jz      short loc_18002A367
0x18002a34b  mov     edx, edi; int
0x18002a34d  mov     ecx, 1510326h; unsigned int
0x18002a352  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a357  nop
0x18002a358  mov     rcx, rbx
0x18002a35b  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a361  nop
0x18002a362  jmp     loc_18002A43F
0x18002a367  mov     rsi, [rsp+48h+hMem]
0x18002a36c  mov     rdx, r14; void **
0x18002a36f  mov     rcx, rsi; String1
0x18002a372  call    ?myFindDomainSidInCache@@YAKPEBGPEAPEAX@Z; myFindDomainSidInCache(ushort const *,void * *)
0x18002a377  mov     edi, eax
0x18002a379  mov     [rsp+48h+var_28], eax
0x18002a37d  test    eax, eax
0x18002a37f  jz      short loc_18002A39D
0x18002a381  mov     edx, eax; int
0x18002a383  mov     ecx, 1570326h; unsigned int
0x18002a388  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a38d  nop
0x18002a38e  mov     rcx, rbx
0x18002a391  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a397  nop
0x18002a398  jmp     loc_18002A43F
0x18002a39d  cmp     qword ptr [r14], 0
0x18002a3a1  jnz     loc_18002A42F
0x18002a3a7  call    ?myUpdateDomainSidCache@@YAKXZ; myUpdateDomainSidCache(void)
0x18002a3ac  mov     edi, eax
0x18002a3ae  mov     [rsp+48h+var_28], eax
0x18002a3b2  test    eax, eax
0x18002a3b4  jz      short loc_18002A3CF
0x18002a3b6  mov     edx, eax; int
0x18002a3b8  mov     ecx, 15D0326h; unsigned int
0x18002a3bd  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a3c2  nop
0x18002a3c3  mov     rcx, rbx
0x18002a3c6  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a3cc  nop
0x18002a3cd  jmp     short loc_18002A43F
0x18002a3cf  mov     rdx, r14; void **
0x18002a3d2  mov     rcx, rsi; String1
0x18002a3d5  call    ?myFindDomainSidInCache@@YAKPEBGPEAPEAX@Z; myFindDomainSidInCache(ushort const *,void * *)
0x18002a3da  mov     edi, eax
0x18002a3dc  mov     [rsp+48h+var_28], eax
0x18002a3e0  test    eax, eax
0x18002a3e2  jz      short loc_18002A3FD
0x18002a3e4  mov     edx, eax; int
0x18002a3e6  mov     ecx, 1600326h; unsigned int
0x18002a3eb  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002a3f0  nop
0x18002a3f1  mov     rcx, rbx
0x18002a3f4  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a3fa  nop
0x18002a3fb  jmp     short loc_18002A43F
0x18002a3fd  cmp     qword ptr [r14], 0
0x18002a401  jnz     short loc_18002A42F
0x18002a403  mov     edi, 80004005h
0x18002a408  mov     [rsp+48h+var_28], edi
0x18002a40c  xor     r9d, r9d; int
0x18002a40f  mov     edx, 1650326h; unsigned int
0x18002a414  mov     r8d, 80004005h; int
0x18002a41a  mov     rcx, rsi; unsigned __int16 *
0x18002a41d  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18002a422  nop
0x18002a423  mov     rcx, rbx
0x18002a426  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a42c  nop
0x18002a42d  jmp     short loc_18002A43F
0x18002a42f  mov     rcx, rbx
0x18002a432  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18002a438  nop
0x18002a439  jmp     short loc_18002A43F
0x18002a43b  mov     edi, [rsp+48h+var_28]
0x18002a43f  lea     rcx, ?g_csDomainSidCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002a446  call    cs:__imp_LeaveCriticalSection
0x18002a44c  mov     rcx, [rsp+48h+hMem]; hMem
0x18002a451  call    cs:__imp_LocalFree
0x18002a457  mov     eax, edi
0x18002a459  mov     rbx, [rsp+48h+arg_0]
0x18002a45e  add     rsp, 30h
0x18002a462  pop     r14
0x18002a464  pop     rdi
0x18002a465  pop     rsi
0x18002a466  retn
```
