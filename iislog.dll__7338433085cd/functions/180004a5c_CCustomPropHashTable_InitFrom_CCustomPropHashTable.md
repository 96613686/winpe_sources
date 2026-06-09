# CCustomPropHashTable::InitFrom(CCustomPropHashTable &)

- ea: `0x180004a5c`
- end: `0x180004bb1`
- name: `?InitFrom@CCustomPropHashTable@@QEAAHAEAV1@@Z`
- size: `341`
- prototype: `__int64 __fastcall(CCustomPropHashTable *__hidden this, struct CCustomPropHashTable *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004c70`

## callees

- `0x180001008`
- `0x1800038f0`
- `0x180003cd8`
- `0x180004a5c`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180004b9a`
- `IisRTL!PuDbgPrint` at `0x180004b9a`
- `IisRTL!?Copy@STR@@QEAAHAEBV1@@Z` at `0x180004b10`
- `IisRTL!?Copy@STR@@QEAAHAEBV1@@Z` at `0x180004b26`
- `IisRTL!?Copy@STR@@QEAAHAEBV1@@Z` at `0x180004b10`
- `IisRTL!?Copy@STR@@QEAAHAEBV1@@Z` at `0x180004b26`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004b4e`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004b4e`

## string_xrefs

- `0x180004b7c`: `inetsrv\iis\svcs\infocomm\log\plugin\extlogc.cpp`

## pseudocode

```c
__int64 __fastcall CCustomPropHashTable::InitFrom(CCustomPropHashTable *this, struct CCustomPropHashTable *a2)
{
  CCustomPropHashTable *v2; // r15
  unsigned int v4; // edi
  unsigned __int64 v5; // rbp
  __int64 v6; // rax
  bool v7; // cf
  size_t v8; // rax
  unsigned __int64 *v9; // rax
  _QWORD *v10; // rsi
  LOG_PROPERTY_INFO *v11; // r14
  int v12; // eax
  unsigned int v13; // ebp
  __int64 v14; // rcx
  _DWORD *v15; // r14
  __int64 v16; // rsi

  v2 = g_pGlobalLoggingProperties;
  v4 = 0;
  CCustomPropHashTable::ClearTableAndStorage(this);
  if ( *((_DWORD *)v2 + 20) )
  {
    v5 = *((unsigned int *)v2 + 20);
    v6 = 136 * v5;
    if ( !is_mul_ok(v5, 0x88u) )
      v6 = -1;
    v7 = __CFADD__(v6, 8);
    v8 = v6 + 8;
    if ( v7 )
      v8 = -1;
    v9 = (unsigned __int64 *)operator new(v8);
    if ( v9 )
    {
      v10 = v9 + 1;
      *v9 = v5;
      v11 = (LOG_PROPERTY_INFO *)(v9 + 1);
      do
      {
        LOG_PROPERTY_INFO::LOG_PROPERTY_INFO(v11);
        v11 = (LOG_PROPERTY_INFO *)((char *)v11 + 136);
        --v5;
      }
      while ( v5 );
    }
    else
    {
      v10 = 0;
    }
    *((_QWORD *)this + 9) = v10;
    if ( v10 )
    {
      v12 = *((_DWORD *)v2 + 20);
      v13 = 0;
      *((_DWORD *)this + 20) = v12;
      v4 = 1;
      if ( v12 )
      {
        while ( 1 )
        {
          v14 = 136LL * v13;
          v15 = (_DWORD *)(v14 + *((_QWORD *)v2 + 9));
          v16 = v14 + *((_QWORD *)this + 9);
          if ( !STR::Copy((STR *)v16, (const struct STR *)v15)
            || !STR::Copy((STR *)(v16 + 72), (const struct STR *)(v15 + 18)) )
          {
            break;
          }
          *(_DWORD *)(v16 + 56) = v15[14];
          *(_DWORD *)(v16 + 60) = v15[15];
          *(_DWORD *)(v16 + 64) = v15[16];
          if ( (unsigned int)CLKRHashTable::InsertRecord(this, v16, 0) )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\extlogc.cpp",
                391,
                "CCustomPropHashTable::InitFrom",
                "InitFrom: Unable to insert Property %s\n",
                *(const char **)(v16 + 32));
            return 0;
          }
          if ( ++v13 >= *((_DWORD *)this + 20) )
            return v4;
        }
        return 0;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004a5c  push    rbx
0x180004a5e  push    rbp
0x180004a5f  push    rsi
0x180004a60  push    rdi
0x180004a61  push    r14
0x180004a63  push    r15
0x180004a65  sub     rsp, 38h
0x180004a69  mov     r15, cs:?g_pGlobalLoggingProperties@@3PEAVCCustomPropHashTable@@EA; CCustomPropHashTable * g_pGlobalLoggingProperties
0x180004a70  mov     rbx, rcx
0x180004a73  xor     edi, edi
0x180004a75  call    ?ClearTableAndStorage@CCustomPropHashTable@@QEAAXXZ; CCustomPropHashTable::ClearTableAndStorage(void)
0x180004a7a  cmp     [r15+50h], edi
0x180004a7e  jz      loc_180004BA2
0x180004a84  mov     ebp, [r15+50h]
0x180004a88  lea     rcx, [rdi-1]
0x180004a8c  mov     eax, 88h
0x180004a91  mul     rbp
0x180004a94  cmovb   rax, rcx
0x180004a98  add     rax, 8
0x180004a9c  cmovb   rax, rcx
0x180004aa0  mov     rcx, rax; Size
0x180004aa3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004aa8  test    rax, rax
0x180004aab  jz      short loc_180004ACE
0x180004aad  lea     rsi, [rax+8]
0x180004ab1  mov     [rax], rbp
0x180004ab4  mov     r14, rsi
0x180004ab7  mov     rcx, r14; this
0x180004aba  call    ??0LOG_PROPERTY_INFO@@QEAA@XZ; LOG_PROPERTY_INFO::LOG_PROPERTY_INFO(void)
0x180004abf  add     r14, 88h
0x180004ac6  sub     rbp, 1
0x180004aca  jnz     short loc_180004AB7
0x180004acc  jmp     short loc_180004AD0
0x180004ace  xor     esi, esi
0x180004ad0  mov     [rbx+48h], rsi
0x180004ad4  test    rsi, rsi
0x180004ad7  jz      loc_180004BA2
0x180004add  mov     eax, [r15+50h]
0x180004ae1  xor     ebp, ebp
0x180004ae3  mov     [rbx+50h], eax
0x180004ae6  mov     edi, 1
0x180004aeb  test    eax, eax
0x180004aed  jz      loc_180004BA2
0x180004af3  mov     rsi, [rbx+48h]
0x180004af7  mov     r14, [r15+48h]
0x180004afb  mov     eax, ebp
0x180004afd  imul    rcx, rax, 88h
0x180004b04  add     r14, rcx
0x180004b07  add     rsi, rcx
0x180004b0a  mov     rdx, r14
0x180004b0d  mov     rcx, rsi
0x180004b10  call    cs:__imp_?Copy@STR@@QEAAHAEBV1@@Z; STR::Copy(STR const &)
0x180004b16  test    eax, eax
0x180004b18  jz      loc_180004BA0
0x180004b1e  lea     rdx, [r14+48h]
0x180004b22  lea     rcx, [rsi+48h]
0x180004b26  call    cs:__imp_?Copy@STR@@QEAAHAEBV1@@Z; STR::Copy(STR const &)
0x180004b2c  test    eax, eax
0x180004b2e  jz      short loc_180004BA0
0x180004b30  mov     eax, [r14+38h]
0x180004b34  xor     r8d, r8d
0x180004b37  mov     [rsi+38h], eax
0x180004b3a  mov     rdx, rsi
0x180004b3d  mov     eax, [r14+3Ch]
0x180004b41  mov     rcx, rbx
0x180004b44  mov     [rsi+3Ch], eax
0x180004b47  mov     eax, [r14+40h]
0x180004b4b  mov     [rsi+40h], eax
0x180004b4e  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180004b54  test    eax, eax
0x180004b56  jnz     short loc_180004B61
0x180004b58  inc     ebp
0x180004b5a  cmp     ebp, [rbx+50h]
0x180004b5d  jb      short loc_180004AF3
0x180004b5f  jmp     short loc_180004BA2
0x180004b61  test    byte ptr cs:g_dwDebugFlags, 3
0x180004b68  jz      short loc_180004BA0
0x180004b6a  mov     rax, [rsi+20h]
0x180004b6e  lea     r9, aCcustomprophas_0; "CCustomPropHashTable::InitFrom"
0x180004b75  mov     rcx, cs:g_pDebug
0x180004b7c  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x180004b83  mov     [rsp+68h+var_40], rax
0x180004b88  mov     r8d, 187h
0x180004b8e  lea     rax, aInitfromUnable; "InitFrom: Unable to insert Property %s"...
0x180004b95  mov     [rsp+68h+var_48], rax
0x180004b9a  call    cs:__imp_PuDbgPrint
0x180004ba0  xor     edi, edi
0x180004ba2  mov     eax, edi
0x180004ba4  add     rsp, 38h
0x180004ba8  pop     r15
0x180004baa  pop     r14
0x180004bac  pop     rdi
0x180004bad  pop     rsi
0x180004bae  pop     rbp
0x180004baf  pop     rbx
0x180004bb0  retn
```
