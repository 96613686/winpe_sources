# CreateNonIISConfigObjectCollections(CMDBaseObject *,CWriter *,CMBSchemaWriter * *)

- ea: `0x180011320`
- end: `0x18001164f`
- name: `?CreateNonIISConfigObjectCollections@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(struct CMDBaseObject *, struct CWriter *, struct CMBSchemaWriter **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800120b4`

## callees

- `0x180004290`
- `0x1800053b0`
- `0x180007810`
- `0x180007bd0`
- `0x180010da0`
- `0x180010f00`
- `0x180011320`
- `0x180011658`
- `0x1800119a8`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180011524`
- `IisRTL!PuDbgPrintW` at `0x1800115ef`
- `IisRTL!PuDbgPrintW` at `0x18001162f`
- `IisRTL!PuDbgPrintW` at `0x180011524`
- `IisRTL!PuDbgPrintW` at `0x1800115ef`
- `IisRTL!PuDbgPrintW` at `0x18001162f`

## string_xrefs

- `0x18001160b`: `[SaveSchema] Unable to open /Schema/Classes. GetChildObject failed with hr = 0x%x.\n`
- `0x18001150b`: `CreateNonIISConfigObjectCollections`
- `0x1800115dc`: `CreateNonIISConfigObjectCollections`
- `0x180011616`: `CreateNonIISConfigObjectCollections`

## pseudocode

```c
__int64 __fastcall CreateNonIISConfigObjectCollections(
        struct CMDBaseObject *a1,
        struct CWriter *a2,
        struct CMBSchemaWriter **a3)
{
  struct CMDBaseObject *ChildObject; // rax
  int CollectionWriter; // ebx
  CMDBaseObject *v5; // r14
  struct CMDBaseObject *i; // rdx
  CMDBaseObject *v7; // rax
  CMDBaseObject *v8; // rsi
  unsigned __int16 *v9; // r12
  unsigned __int16 *v10; // r13
  unsigned int v11; // r15d
  const unsigned __int16 *Name; // rdi
  int v13; // eax
  int *v14; // r15
  unsigned __int16 *v15; // rbx
  int v16; // eax
  int v17; // eax
  struct CMDBaseData *v19; // [rsp+40h] [rbp-20h] BYREF
  struct CMBCollectionWriter *v20; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp-10h]
  char *v22; // [rsp+58h] [rbp-8h] BYREF
  int v25; // [rsp+B8h] [rbp+58h] BYREF

  v25 = 0;
  v22 = (char *)L"Classes";
  ChildObject = CMDBaseObject::GetChildObject(a1, &v22, &v25, 1);
  CollectionWriter = v25;
  v5 = ChildObject;
  if ( v25 >= 0 && ChildObject )
  {
    for ( i = 0; ; i = v8 )
    {
      v7 = CMDBaseObject::NextChildObject(v5, i);
      v8 = v7;
      if ( !v7 )
        return 0;
      v21 = 0;
      v25 = 0;
      v9 = 0;
      v22 = (char *)&v25;
      v10 = 0;
      v11 = 1;
      Name = (const unsigned __int16 *)CMDBaseObject::GetName(v7, 1, 0);
      v20 = 0;
      v19 = 0;
      CollectionWriter = CMDBaseObject::EnumDataObject(v8, 0, 0, 0, 0, 0, &v19);
      if ( CollectionWriter < 0 )
        return (unsigned int)CollectionWriter;
      while ( v19 )
      {
        v13 = *((_DWORD *)v19 + 2);
        switch ( v13 )
        {
          case 6355:
            v9 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct CMDBaseData *, __int64))(*(_QWORD *)v19 + 24LL))(
                                       v19,
                                       1);
            break;
          case 6356:
            v10 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct CMDBaseData *, __int64))(*(_QWORD *)v19 + 24LL))(
                                        v19,
                                        1);
            break;
          case 6351:
            v22 = (char *)(*(__int64 (__fastcall **)(struct CMDBaseData *, __int64))(*(_QWORD *)v19 + 24LL))(v19, 1);
            break;
          case 6350:
            v21 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct CMDBaseData *, __int64))(*(_QWORD *)v19 + 24LL))(
                                        v19,
                                        1);
            break;
        }
        CollectionWriter = CMDBaseObject::EnumDataObject(v8, v11, 0, 0, 0, 0, &v19);
        if ( CollectionWriter < 0 )
          return (unsigned int)CollectionWriter;
        ++v11;
      }
      v14 = (int *)v22;
      v15 = v21;
      if ( ClassDiffersFromShippedSchema(Name, *(_DWORD *)v22, v21)
        || (unsigned int)ClassPropertiesDifferFromShippedSchema(Name, v9, v10) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
            684,
            "CreateNonIISConfigObjectCollections",
            L"[SaveSchema] Saving collection: %s.\n",
            Name);
        CollectionWriter = GetCollectionWriter(a2, a3, &v20, Name, *v14, v15);
        if ( CollectionWriter < 0 )
          return (unsigned int)CollectionWriter;
        v16 = ParseAndAddPropertiesToNonIISConfigObjectCollection(v9, 0, v20);
        CollectionWriter = v16;
        if ( v16 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
              704,
              "CreateNonIISConfigObjectCollections",
              L"[SaveSchema] Error while saving classes tree. Could not add optional properties %s for class %s failed with hr = 0x%x.\n",
              v9,
              Name,
              v16);
          return (unsigned int)CollectionWriter;
        }
        v17 = ParseAndAddPropertiesToNonIISConfigObjectCollection(v10, 1, v20);
        CollectionWriter = v17;
        if ( v17 < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
              715,
              "CreateNonIISConfigObjectCollections",
              L"[SaveSchema] Error while saving classes tree. Could not add manditory properties %s for class %s failed with hr = 0x%x.\n",
              v10,
              Name,
              v17);
          return (unsigned int)CollectionWriter;
        }
      }
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
      592,
      "CreateNonIISConfigObjectCollections",
      L"[SaveSchema] Unable to open /Schema/Classes. GetChildObject failed with hr = 0x%x.\n",
      v25);
  return (unsigned int)CollectionWriter;
}

```

## disassembly

```asm
0x180011320  mov     [rsp-38h+arg_0], rbx
0x180011325  mov     [rsp-38h+arg_10], r8
0x18001132a  mov     [rsp-38h+arg_8], rdx
0x18001132f  push    rbp
0x180011330  push    rsi
0x180011331  push    rdi
0x180011332  push    r12
0x180011334  push    r13
0x180011336  push    r14
0x180011338  push    r15
0x18001133a  mov     rbp, rsp
0x18001133d  sub     rsp, 60h
0x180011341  lea     rax, aClasses; "Classes"
0x180011348  mov     [rbp+arg_18], 0
0x18001134f  mov     r9d, 1; int
0x180011355  mov     [rbp+var_8], rax
0x180011359  lea     r8, [rbp+arg_18]; int *
0x18001135d  lea     rdx, [rbp+var_8]; char **
0x180011361  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x180011366  mov     ebx, [rbp+arg_18]
0x180011369  mov     r14, rax
0x18001136c  test    ebx, ebx
0x18001136e  js      loc_1800115FB
0x180011374  test    rax, rax
0x180011377  jz      loc_1800115FB
0x18001137d  xor     edx, edx; struct CMDBaseObject *
0x18001137f  mov     rcx, r14; this
0x180011382  call    ?NextChildObject@CMDBaseObject@@QEAAPEAV1@PEAV1@@Z; CMDBaseObject::NextChildObject(CMDBaseObject *)
0x180011387  mov     rsi, rax
0x18001138a  test    rax, rax
0x18001138d  jz      loc_1800115F7
0x180011393  xor     ebx, ebx
0x180011395  lea     r15, [rbp+arg_18]
0x180011399  xor     r8d, r8d; unsigned int *
0x18001139c  mov     [rbp+var_10], rbx
0x1800113a0  mov     rcx, rax; this
0x1800113a3  mov     [rbp+arg_18], ebx
0x1800113a6  xor     r12d, r12d
0x1800113a9  mov     [rbp+var_8], r15
0x1800113ad  lea     edx, [rbx+1]; int
0x1800113b0  xor     r13d, r13d
0x1800113b3  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x1800113b8  xor     ecx, ecx
0x1800113ba  lea     r15d, [r12+1]
0x1800113bf  mov     rdi, rax
0x1800113c2  mov     [rbp+var_18], rcx
0x1800113c6  lea     rax, [rbp+var_20]
0x1800113ca  mov     [rbp+var_20], rcx
0x1800113ce  mov     [rsp+60h+var_30], rax; struct CMDBaseData **
0x1800113d3  xor     r9d, r9d; unsigned int
0x1800113d6  mov     [rsp+60h+var_38], rcx; struct CMDBaseObject **
0x1800113db  xor     r8d, r8d; unsigned int
0x1800113de  mov     [rsp+60h+var_40], ecx; unsigned int
0x1800113e2  xor     edx, edx; unsigned int
0x1800113e4  mov     rcx, rsi; this
0x1800113e7  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x1800113ec  mov     ebx, eax
0x1800113ee  test    eax, eax
0x1800113f0  js      loc_180011635
0x1800113f6  mov     rcx, [rbp+var_20]
0x1800113fa  test    rcx, rcx
0x1800113fd  jz      loc_1800114BF
0x180011403  mov     eax, [rcx+8]
0x180011406  cmp     eax, 18D3h
0x18001140b  jnz     short loc_180011425
0x18001140d  mov     rax, [rcx]
0x180011410  xor     r8d, r8d
0x180011413  mov     rax, [rax+18h]
0x180011417  lea     edx, [r8+1]
0x18001141b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011420  mov     r12, rax
0x180011423  jmp     short loc_180011482
0x180011425  cmp     eax, 18D4h
0x18001142a  jnz     short loc_180011444
0x18001142c  mov     rax, [rcx]
0x18001142f  xor     r8d, r8d
0x180011432  mov     rax, [rax+18h]
0x180011436  lea     edx, [r8+1]
0x18001143a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001143f  mov     r13, rax
0x180011442  jmp     short loc_180011482
0x180011444  cmp     eax, 18CFh
0x180011449  jnz     short loc_180011464
0x18001144b  mov     rax, [rcx]
0x18001144e  xor     r8d, r8d
0x180011451  mov     rax, [rax+18h]
0x180011455  lea     edx, [r8+1]
0x180011459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145e  mov     [rbp+var_8], rax
0x180011462  jmp     short loc_180011482
0x180011464  cmp     eax, 18CEh
0x180011469  jnz     short loc_180011482
0x18001146b  mov     rax, [rcx]
0x18001146e  xor     r8d, r8d
0x180011471  mov     rax, [rax+18h]
0x180011475  lea     edx, [r8+1]
0x180011479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001147e  mov     [rbp+var_10], rax
0x180011482  lea     rax, [rbp+var_20]
0x180011486  xor     r9d, r9d; unsigned int
0x180011489  mov     [rsp+60h+var_30], rax; struct CMDBaseData **
0x18001148e  xor     r8d, r8d; unsigned int
0x180011491  mov     [rsp+60h+var_38], 0; struct CMDBaseObject **
0x18001149a  mov     edx, r15d; unsigned int
0x18001149d  mov     rcx, rsi; this
0x1800114a0  mov     [rsp+60h+var_40], 0; unsigned int
0x1800114a8  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x1800114ad  mov     ebx, eax
0x1800114af  test    eax, eax
0x1800114b1  js      loc_180011635
0x1800114b7  inc     r15d
0x1800114ba  jmp     loc_1800113F6
0x1800114bf  mov     r15, [rbp+var_8]
0x1800114c3  mov     rcx, rdi; unsigned __int16 *
0x1800114c6  mov     rbx, [rbp+var_10]
0x1800114ca  mov     r8, rbx; unsigned __int16 *
0x1800114cd  mov     edx, [r15]; int
0x1800114d0  call    ?ClassDiffersFromShippedSchema@@YAHPEBGHPEAG@Z; ClassDiffersFromShippedSchema(ushort const *,int,ushort *)
0x1800114d5  test    eax, eax
0x1800114d7  jnz     short loc_1800114EF
0x1800114d9  mov     r8, r13; unsigned __int16 *
0x1800114dc  mov     rdx, r12; unsigned __int16 *
0x1800114df  mov     rcx, rdi; unsigned __int16 *
0x1800114e2  call    ?ClassPropertiesDifferFromShippedSchema@@YAHPEBGPEAG1@Z; ClassPropertiesDifferFromShippedSchema(ushort const *,ushort *,ushort *)
0x1800114e7  test    eax, eax
0x1800114e9  jz      loc_18001157F
0x1800114ef  test    byte ptr cs:g_dwDebugFlags, 3
0x1800114f6  jz      short loc_18001152A
0x1800114f8  mov     rcx, cs:g_pDebug
0x1800114ff  lea     rax, aSaveschemaSavi; "[SaveSchema] Saving collection: %s.\n"
0x180011506  mov     [rsp+60h+var_38], rdi
0x18001150b  lea     r9, aCreatenoniisco; "CreateNonIISConfigObjectCollections"
0x180011512  mov     r8d, 2ACh
0x180011518  mov     qword ptr [rsp+60h+var_40], rax
0x18001151d  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180011524  call    cs:__imp_PuDbgPrintW
0x18001152a  mov     eax, [r15]
0x18001152d  lea     r8, [rbp+var_18]; struct CMBCollectionWriter **
0x180011531  mov     rdx, [rbp+arg_10]; struct CMBSchemaWriter **
0x180011535  mov     r9, rdi; unsigned __int16 *
0x180011538  mov     rcx, [rbp+arg_8]; struct CWriter *
0x18001153c  mov     [rsp+60h+var_38], rbx; unsigned __int16 *
0x180011541  mov     [rsp+60h+var_40], eax; int
0x180011545  call    ?GetCollectionWriter@@YAJPEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@PEBGH3@Z; GetCollectionWriter(CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *,ushort const *,int,ushort const *)
0x18001154a  mov     ebx, eax
0x18001154c  test    eax, eax
0x18001154e  js      loc_180011635
0x180011554  mov     r8, [rbp+var_18]; this
0x180011558  xor     edx, edx; int
0x18001155a  mov     rcx, r12; unsigned __int16 *
0x18001155d  call    ?ParseAndAddPropertiesToNonIISConfigObjectCollection@@YAJPEBGHPEAVCMBCollectionWriter@@@Z; ParseAndAddPropertiesToNonIISConfigObjectCollection(ushort const *,int,CMBCollectionWriter *)
0x180011562  mov     ebx, eax
0x180011564  test    eax, eax
0x180011566  js      short loc_1800115B1
0x180011568  mov     r8, [rbp+var_18]; this
0x18001156c  mov     edx, 1; int
0x180011571  mov     rcx, r13; unsigned __int16 *
0x180011574  call    ?ParseAndAddPropertiesToNonIISConfigObjectCollection@@YAJPEBGHPEAVCMBCollectionWriter@@@Z; ParseAndAddPropertiesToNonIISConfigObjectCollection(ushort const *,int,CMBCollectionWriter *)
0x180011579  mov     ebx, eax
0x18001157b  test    eax, eax
0x18001157d  js      short loc_180011587
0x18001157f  mov     rdx, rsi
0x180011582  jmp     loc_18001137F
0x180011587  test    byte ptr cs:g_dwDebugFlags, 3
0x18001158e  jz      loc_180011635
0x180011594  mov     [rsp+60h+var_28], eax
0x180011598  mov     r8d, 2CBh
0x18001159e  mov     [rsp+60h+var_30], rdi
0x1800115a3  lea     rax, aSaveschemaErro_8; "[SaveSchema] Error while saving classes"...
0x1800115aa  mov     [rsp+60h+var_38], r13
0x1800115af  jmp     short loc_1800115D5
0x1800115b1  test    byte ptr cs:g_dwDebugFlags, 3
0x1800115b8  jz      short loc_180011635
0x1800115ba  mov     [rsp+60h+var_28], eax
0x1800115be  mov     r8d, 2C0h
0x1800115c4  mov     [rsp+60h+var_30], rdi
0x1800115c9  lea     rax, aSaveschemaErro_0; "[SaveSchema] Error while saving classes"...
0x1800115d0  mov     [rsp+60h+var_38], r12
0x1800115d5  mov     rcx, cs:g_pDebug
0x1800115dc  lea     r9, aCreatenoniisco; "CreateNonIISConfigObjectCollections"
0x1800115e3  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x1800115ea  mov     qword ptr [rsp+60h+var_40], rax
0x1800115ef  call    cs:__imp_PuDbgPrintW
0x1800115f5  jmp     short loc_180011635
0x1800115f7  xor     ebx, ebx
0x1800115f9  jmp     short loc_180011635
0x1800115fb  test    byte ptr cs:g_dwDebugFlags, 3
0x180011602  jz      short loc_180011635
0x180011604  mov     rcx, cs:g_pDebug
0x18001160b  lea     rax, aSaveschemaUnab_5; "[SaveSchema] Unable to open /Schema/Cla"...
0x180011612  mov     dword ptr [rsp+60h+var_38], ebx
0x180011616  lea     r9, aCreatenoniisco; "CreateNonIISConfigObjectCollections"
0x18001161d  mov     r8d, 250h
0x180011623  mov     qword ptr [rsp+60h+var_40], rax
0x180011628  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x18001162f  call    cs:__imp_PuDbgPrintW
0x180011635  mov     eax, ebx
0x180011637  mov     rbx, [rsp+60h+arg_0]
0x18001163f  add     rsp, 60h
0x180011643  pop     r15
0x180011645  pop     r14
0x180011647  pop     r13
0x180011649  pop     r12
0x18001164b  pop     rdi
0x18001164c  pop     rsi
0x18001164d  pop     rbp
0x18001164e  retn
```
