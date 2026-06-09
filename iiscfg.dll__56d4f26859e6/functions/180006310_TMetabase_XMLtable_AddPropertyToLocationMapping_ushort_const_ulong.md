# TMetabase_XMLtable::AddPropertyToLocationMapping(ushort const *,ulong)

- ea: `0x180006310`
- end: `0x1800064c5`
- name: `?AddPropertyToLocationMapping@TMetabase_XMLtable@@AEAAJPEBGK@Z`
- size: `437`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005cb8`
- `0x180005fdc`
- `0x180006750`

## callees

- `0x18000540c`
- `0x180005870`
- `0x180006310`
- `0x180006710`
- `0x18000bf74`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180006426`
- `IisRTL!PuDbgPrint` at `0x180006426`

## string_xrefs

- `0x18000640b`: `TMetabase_XMLtable::AddPropertyToLocationMapping`
- `0x180006418`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TMetabase_XMLtable::AddPropertyToLocationMapping(
        TMetabase_XMLtable *this,
        const unsigned __int16 *a2,
        int a3)
{
  _DWORD *v4; // rdi
  unsigned int v5; // edx
  _QWORD *v6; // rsi
  int v7; // esi
  unsigned int v9; // ebp
  unsigned int v10; // r14d
  __int64 v11; // r15
  _DWORD *v12; // rax
  LPVOID v13[11]; // [rsp+40h] [rbp-58h] BYREF

  v4 = (_DWORD *)((char *)this + 1636);
  if ( !*((_BYTE *)this + 1601) && *v4 )
  {
    v5 = ++*(_DWORD *)(*((_QWORD *)this + 211) + 24LL * *((unsigned int *)this + 418) + 8);
    if ( v5 > *((_DWORD *)this + 410) )
      *((_DWORD *)this + 410) = v5;
    return 0;
  }
  TMetabase_XMLtable::TLocation::TLocation((TMetabase_XMLtable::TLocation *)v13, a2, a3);
  v6 = (_QWORD *)((char *)this + 1688);
  if ( *v4
    && TMetabase_XMLtable::TLocation::CompareLocation(
         (TMetabase_XMLtable::TLocation *)v13,
         (const struct TMetabase_XMLtable::TLocation *)(*v6 + 24LL * (unsigned int)(*v4 - 1))) != 3 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
        131,
        "TMetabase_XMLtable::AddPropertyToLocationMapping",
        "Location %s is out of order.  The previous location was %s\r\n",
        (const char *)v13[0],
        *(const char **)(*v6 + 24LL * *((unsigned int *)this + 418)));
    v9 = 0;
    v10 = *((_DWORD *)this + 425);
    if ( v10 )
    {
      do
      {
        v11 = v9 + ((v10 - v9) >> 1);
        if ( TMetabase_XMLtable::TLocation::CompareLocation(
               (TMetabase_XMLtable::TLocation *)(*v6 + 24 * v11),
               (const struct TMetabase_XMLtable::TLocation *)v13) == 3 )
          v10 = v9 + ((v10 - v9) >> 1);
        else
          v9 = v11 + 1;
      }
      while ( v9 < v10 );
    }
    *((_DWORD *)this + 418) = v9;
    v7 = CCfgArray<TMetabase_XMLtable::TLocation>::InsertAt((char *)this + 1688, v13, v9);
    if ( v7 >= 0 )
    {
      *((_BYTE *)this + 1624) = 1;
      v12 = (_DWORD *)((char *)this + 1636);
      goto LABEL_19;
    }
LABEL_7:
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(v13);
    return (unsigned int)v7;
  }
  v7 = CCfgArray<TMetabase_XMLtable::TLocation>::InsertAt((char *)this + 1688, v13, *((unsigned int *)this + 425));
  if ( v7 < 0 )
    goto LABEL_7;
  *((_DWORD *)this + 418) = *v4;
  v12 = v4;
LABEL_19:
  *v4 = *v12 + 1;
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>(v13);
  return 0;
}

```

## disassembly

```asm
0x180006310  push    rbx
0x180006312  push    rbp
0x180006313  push    rsi
0x180006314  push    rdi
0x180006315  push    r14
0x180006317  push    r15
0x180006319  sub     rsp, 68h
0x18000631d  mov     rbx, rcx
0x180006320  lea     rdi, [rcx+664h]
0x180006327  cmp     byte ptr [rcx+641h], 0
0x18000632e  jnz     short loc_180006376
0x180006330  cmp     dword ptr [rdi], 0
0x180006333  jbe     short loc_180006376
0x180006335  mov     eax, [rcx+688h]
0x18000633b  lea     rdx, [rax+rax*2]
0x18000633f  mov     rax, [rcx+698h]
0x180006346  inc     dword ptr [rax+rdx*8+8]
0x18000634a  mov     eax, [rcx+688h]
0x180006350  lea     rcx, [rax+rax*2]
0x180006354  mov     rax, [rbx+698h]
0x18000635b  mov     edx, [rax+rcx*8+8]; unsigned __int16 *
0x18000635f  cmp     edx, [rbx+668h]
0x180006365  jbe     loc_1800064B6
0x18000636b  mov     [rbx+668h], edx
0x180006371  jmp     loc_1800064B6
0x180006376  lea     rcx, [rsp+98h+var_58]; this
0x18000637b  call    ??0TLocation@TMetabase_XMLtable@@QEAA@PEBGK@Z; TMetabase_XMLtable::TLocation::TLocation(ushort const *,ulong)
0x180006380  nop
0x180006381  mov     eax, [rdi]
0x180006383  lea     rsi, [rbx+698h]
0x18000638a  test    eax, eax
0x18000638c  jnz     short loc_1800063BA
0x18000638e  mov     r8d, [rsi+0Ch]
0x180006392  lea     rdx, [rsp+98h+var_58]
0x180006397  mov     rcx, rsi
0x18000639a  call    ?InsertAt@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAAJAEBVTLocation@TMetabase_XMLtable@@K@Z; CCfgArray<TMetabase_XMLtable::TLocation>::InsertAt(TMetabase_XMLtable::TLocation const &,ulong)
0x18000639f  mov     esi, eax
0x1800063a1  test    eax, eax
0x1800063a3  jns     loc_180006462
0x1800063a9  lea     rcx, [rsp+98h+var_58]; void *
0x1800063ae  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800063b3  mov     eax, esi
0x1800063b5  jmp     loc_1800064B8
0x1800063ba  dec     eax
0x1800063bc  lea     rdx, [rax+rax*2]
0x1800063c0  mov     rax, [rsi]
0x1800063c3  lea     rdx, [rax+rdx*8]; struct TMetabase_XMLtable::TLocation *
0x1800063c7  lea     rcx, [rsp+98h+var_58]; this
0x1800063cc  call    ?CompareLocation@TLocation@TMetabase_XMLtable@@AEBAHAEBV12@@Z; TMetabase_XMLtable::TLocation::CompareLocation(TMetabase_XMLtable::TLocation const &)
0x1800063d1  cmp     eax, 3
0x1800063d4  jz      short loc_18000638E
0x1800063d6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800063dd  jz      short loc_18000642C
0x1800063df  mov     eax, [rbx+688h]
0x1800063e5  lea     rcx, [rax+rax*2]
0x1800063e9  mov     rax, [rsi]
0x1800063ec  mov     rax, [rax+rcx*8]
0x1800063f0  mov     [rsp+98h+var_68], rax
0x1800063f5  mov     rax, [rsp+98h+var_58]
0x1800063fa  mov     [rsp+98h+var_70], rax
0x1800063ff  lea     rax, aLocationSIsOut; "Location %s is out of order.  The previ"...
0x180006406  mov     [rsp+98h+var_78], rax
0x18000640b  lea     r9, aTmetabaseXmlta_0; "TMetabase_XMLtable::AddPropertyToLocati"...
0x180006412  mov     r8d, 83h
0x180006418  lea     rdx, aInetsrvIisMbCo_6; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000641f  mov     rcx, cs:g_pDebug
0x180006426  call    cs:__imp_PuDbgPrint
0x18000642c  xor     ebp, ebp
0x18000642e  mov     r14d, [rsi+0Ch]
0x180006432  test    r14d, r14d
0x180006435  jz      short loc_180006478
0x180006437  mov     r15d, r14d
0x18000643a  sub     r15d, ebp
0x18000643d  shr     r15d, 1
0x180006440  add     r15d, ebp
0x180006443  lea     rcx, [r15+r15*2]
0x180006447  mov     rax, [rsi]
0x18000644a  lea     rcx, [rax+rcx*8]; this
0x18000644e  lea     rdx, [rsp+98h+var_58]; struct TMetabase_XMLtable::TLocation *
0x180006453  call    ?CompareLocation@TLocation@TMetabase_XMLtable@@AEBAHAEBV12@@Z; TMetabase_XMLtable::TLocation::CompareLocation(TMetabase_XMLtable::TLocation const &)
0x180006458  cmp     eax, 3
0x18000645b  jnz     short loc_18000646F
0x18000645d  mov     r14d, r15d
0x180006460  jmp     short loc_180006473
0x180006462  mov     eax, [rdi]
0x180006464  mov     [rbx+688h], eax
0x18000646a  mov     rax, rdi
0x18000646d  jmp     short loc_1800064A6
0x18000646f  lea     ebp, [r15+1]
0x180006473  cmp     ebp, r14d
0x180006476  jb      short loc_180006437
0x180006478  mov     [rbx+688h], ebp
0x18000647e  mov     r8d, ebp
0x180006481  lea     rdx, [rsp+98h+var_58]
0x180006486  mov     rcx, rsi
0x180006489  call    ?InsertAt@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAAJAEBVTLocation@TMetabase_XMLtable@@K@Z; CCfgArray<TMetabase_XMLtable::TLocation>::InsertAt(TMetabase_XMLtable::TLocation const &,ulong)
0x18000648e  mov     esi, eax
0x180006490  test    eax, eax
0x180006492  js      loc_1800063A9
0x180006498  mov     byte ptr [rbx+658h], 1
0x18000649f  lea     rax, [rbx+664h]
0x1800064a6  mov     eax, [rax]
0x1800064a8  inc     eax
0x1800064aa  mov     [rdi], eax
0x1800064ac  lea     rcx, [rsp+98h+var_58]; void *
0x1800064b1  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800064b6  xor     eax, eax
0x1800064b8  add     rsp, 68h
0x1800064bc  pop     r15
0x1800064be  pop     r14
0x1800064c0  pop     rdi
0x1800064c1  pop     rsi
0x1800064c2  pop     rbp
0x1800064c3  pop     rbx
0x1800064c4  retn
```
