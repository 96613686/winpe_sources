# SaveTypes(CMDBaseObject *,CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *)

- ea: `0x180012938`
- end: `0x180012c8c`
- name: `?SaveTypes@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@@Z`
- size: `852`
- prototype: `int(struct CMDBaseObject *, struct CWriter *, struct CMBSchemaWriter **, struct CMBCollectionWriter **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800120b4`

## callees

- `0x180004290`
- `0x180007bd0`
- `0x180011658`
- `0x180011a38`
- `0x180012938`
- `0x18002f630`
- `0x18002fa90`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180012b28`
- `IisRTL!PuDbgPrintW` at `0x180012b8d`
- `IisRTL!PuDbgPrintW` at `0x180012c30`
- `IisRTL!PuDbgPrintW` at `0x180012c70`
- `IisRTL!PuDbgPrintW` at `0x180012b28`
- `IisRTL!PuDbgPrintW` at `0x180012b8d`
- `IisRTL!PuDbgPrintW` at `0x180012c30`
- `IisRTL!PuDbgPrintW` at `0x180012c70`

## string_xrefs

- `0x180012a2d`: `IIsConfigObject`
- `0x180012c4c`: `[SaveSchema] Unable to open /Schema/Properties/Types. GetChildObject failed with hr = 0x%x.\n`
- `0x180012c0f`: `[SaveSchema] Error while saving types tree. GetPropertyWriter for ID:%d failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SaveTypes(
        struct CMDBaseObject *a1,
        struct CWriter *a2,
        struct CMBSchemaWriter **a3,
        struct CMBCollectionWriter **a4)
{
  unsigned int v5; // esi
  CMDBaseObject *ChildObject; // rax
  int CollectionWriter; // ebx
  CMDBaseObject *v8; // r12
  unsigned int *v9; // rdi
  __int64 v10; // rax
  int MBPropertyWriter; // eax
  struct PropValue *v12; // rax
  int v13; // eax
  __int64 v14; // rax
  struct CMDBaseObject **v16; // [rsp+28h] [rbp-48h]
  struct CMDBaseData **v17; // [rsp+30h] [rbp-40h]
  __int64 v18; // [rsp+38h] [rbp-38h]
  __int64 v19; // [rsp+40h] [rbp-30h]
  struct CMBPropertyWriter *v20; // [rsp+50h] [rbp-20h] BYREF
  struct CMDBaseData *v21; // [rsp+58h] [rbp-18h] BYREF
  char *v22; // [rsp+60h] [rbp-10h] BYREF

  LODWORD(v20) = 0;
  v21 = 0;
  v22 = (char *)L"Types";
  v5 = 1;
  ChildObject = CMDBaseObject::GetChildObject(a1, &v22, (int *)&v20, 1);
  CollectionWriter = (int)v20;
  v8 = ChildObject;
  if ( (int)v20 >= 0 && ChildObject )
  {
    CollectionWriter = CMDBaseObject::EnumDataObject(ChildObject, 0, 0, 0, 0, 0, &v21);
    if ( CollectionWriter < 0 )
      return (unsigned int)CollectionWriter;
    while ( 1 )
    {
      v9 = (unsigned int *)v21;
      if ( !v21 )
        return 0;
      v10 = *(_QWORD *)v21;
      v20 = 0;
      if ( (*(unsigned int (__fastcall **)(struct CMDBaseData *))(v10 + 8))(v21) == 3
        && (*(unsigned int (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v9 + 32LL))(v9, 1) == 56 )
      {
        if ( (unsigned int)PropertyNotInShippedSchema(a2, v9[2]) )
        {
          if ( !*a4 )
          {
            CollectionWriter = GetCollectionWriter(a2, a3, a4, L"IIsConfigObject", 0, 0);
            if ( CollectionWriter < 0 )
              return (unsigned int)CollectionWriter;
          }
          MBPropertyWriter = CMBCollectionWriter::GetMBPropertyWriter(*a4, v9[2], &v20);
          CollectionWriter = MBPropertyWriter;
          if ( MBPropertyWriter < 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(v17) = MBPropertyWriter;
              LODWORD(v16) = v9[2];
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
                1993,
                "SaveTypes",
                L"[SaveSchema] Error while saving types tree. GetPropertyWriter for ID:%d failed with hr = 0x%x.\n",
                v16,
                v17);
            }
            return (unsigned int)CollectionWriter;
          }
          v12 = (struct PropValue *)(*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
          v13 = CMBPropertyWriter::AddTypeToProperty(v20, v12);
          CollectionWriter = v13;
          if ( v13 < 0 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(v17) = v13;
              LODWORD(v16) = v9[2];
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
                2003,
                "SaveTypes",
                L"[SaveSchema] Error while saving types tree. AddTypeToProperty for ID:%d failed with hr = 0x%x.\n",
                v16,
                v17);
            }
            return (unsigned int)CollectionWriter;
          }
        }
      }
      else
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v19) = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v9 + 32LL))(v9, 1);
          LODWORD(v18) = 3;
          LODWORD(v17) = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v9 + 8LL))(v9);
          LODWORD(v16) = v9[2];
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
            1945,
            "SaveTypes",
            L"[SaveSchema] Encountered non-binary data in the type tree of the schema.\n"
             "Ignoring type entry for this ID: %d.\n"
             "Type: %d.(Expected %d)\n"
             "Length: %d(Expected %d).\n",
            v16,
            v17,
            v18,
            v19,
            56);
        }
        if ( (*(unsigned int (__fastcall **)(unsigned int *))(*(_QWORD *)v9 + 8LL))(v9) == 2
          && (g_dwDebugFlags & 3) != 0 )
        {
          v14 = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
          PuDbgPrintW(g_pDebug, "inetsrv\\iis\\mb\\metadata\\saveschema.cpp", 1951, "SaveTypes", L"Data: %s.\n", v14);
        }
      }
      CollectionWriter = CMDBaseObject::EnumDataObject(v8, v5, 0, 0, 0, 0, &v21);
      if ( CollectionWriter < 0 )
        return (unsigned int)CollectionWriter;
      ++v5;
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
      1916,
      "SaveTypes",
      L"[SaveSchema] Unable to open /Schema/Properties/Types. GetChildObject failed with hr = 0x%x.\n",
      (_DWORD)v20);
  return (unsigned int)CollectionWriter;
}

```

## disassembly

```asm
0x180012938  mov     [rsp-28h+arg_0], rbx
0x18001293d  mov     [rsp-28h+arg_10], r8
0x180012942  mov     [rsp-28h+arg_8], rdx
0x180012947  push    rbp
0x180012948  push    rsi
0x180012949  push    rdi
0x18001294a  push    r12
0x18001294c  push    r13
0x18001294e  mov     rbp, rsp
0x180012951  sub     rsp, 70h
0x180012955  xor     edi, edi
0x180012957  lea     rax, aTypes; "Types"
0x18001295e  mov     r13, r9
0x180012961  mov     dword ptr [rbp+var_20], edi
0x180012964  lea     r8, [rbp+var_20]; int *
0x180012968  mov     [rbp+var_18], rdi
0x18001296c  lea     rdx, [rbp+var_10]; char **
0x180012970  mov     [rbp+var_10], rax
0x180012974  lea     esi, [rdi+1]
0x180012977  mov     r9d, esi; int
0x18001297a  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x18001297f  mov     ebx, dword ptr [rbp+var_20]
0x180012982  mov     r12, rax
0x180012985  test    ebx, ebx
0x180012987  js      loc_180012C3C
0x18001298d  test    rax, rax
0x180012990  jz      loc_180012C3C
0x180012996  lea     rax, [rbp+var_18]
0x18001299a  xor     r9d, r9d; unsigned int
0x18001299d  mov     [rsp+70h+var_40], rax; struct CMDBaseData **
0x1800129a2  xor     r8d, r8d; unsigned int
0x1800129a5  mov     [rsp+70h+var_48], rdi; struct CMDBaseObject **
0x1800129aa  xor     edx, edx; unsigned int
0x1800129ac  mov     rcx, r12; this
0x1800129af  mov     [rsp+70h+var_50], edi; unsigned int
0x1800129b3  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x1800129b8  mov     ebx, eax
0x1800129ba  test    eax, eax
0x1800129bc  js      loc_180012C76
0x1800129c2  mov     rdi, [rbp+var_18]
0x1800129c6  test    rdi, rdi
0x1800129c9  jz      loc_180012C38
0x1800129cf  mov     rax, [rdi]
0x1800129d2  mov     rcx, rdi
0x1800129d5  mov     [rbp+var_20], 0
0x1800129dd  mov     rax, [rax+8]
0x1800129e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129e6  cmp     eax, 3
0x1800129e9  jnz     loc_180012AB1
0x1800129ef  mov     rax, [rdi]
0x1800129f2  xor     r8d, r8d
0x1800129f5  mov     rcx, rdi
0x1800129f8  mov     rax, [rax+20h]
0x1800129fc  lea     edx, [r8+1]
0x180012a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a05  cmp     eax, 38h ; '8'
0x180012a08  jnz     loc_180012AB1
0x180012a0e  mov     rbx, [rbp+arg_8]
0x180012a12  mov     edx, [rdi+8]; unsigned int
0x180012a15  mov     rcx, rbx; struct CWriter *
0x180012a18  call    ?PropertyNotInShippedSchema@@YAHPEAVCWriter@@K@Z; PropertyNotInShippedSchema(CWriter *,ulong)
0x180012a1d  xor     ecx, ecx
0x180012a1f  test    eax, eax
0x180012a21  jz      short loc_180012A9A
0x180012a23  cmp     [r13+0], rcx
0x180012a27  jnz     short loc_180012A52
0x180012a29  mov     rdx, [rbp+arg_10]; struct CMBSchemaWriter **
0x180012a2d  lea     r9, aIisconfigobjec; "IIsConfigObject"
0x180012a34  mov     [rsp+70h+var_48], rcx; unsigned __int16 *
0x180012a39  mov     r8, r13; struct CMBCollectionWriter **
0x180012a3c  mov     [rsp+70h+var_50], ecx; int
0x180012a40  mov     rcx, rbx; struct CWriter *
0x180012a43  call    ?GetCollectionWriter@@YAJPEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@PEBGH3@Z; GetCollectionWriter(CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *,ushort const *,int,ushort const *)
0x180012a48  mov     ebx, eax
0x180012a4a  test    eax, eax
0x180012a4c  js      loc_180012C76
0x180012a52  mov     edx, [rdi+8]; unsigned int
0x180012a55  lea     r8, [rbp+var_20]; struct CMBPropertyWriter **
0x180012a59  mov     rcx, [r13+0]; this
0x180012a5d  call    ?GetMBPropertyWriter@CMBCollectionWriter@@QEAAJKPEAPEAVCMBPropertyWriter@@@Z; CMBCollectionWriter::GetMBPropertyWriter(ulong,CMBPropertyWriter * *)
0x180012a62  mov     ebx, eax
0x180012a64  test    eax, eax
0x180012a66  js      loc_180012BF5
0x180012a6c  mov     rax, [rdi]
0x180012a6f  xor     r8d, r8d
0x180012a72  mov     rcx, rdi
0x180012a75  mov     rax, [rax+18h]
0x180012a79  lea     edx, [r8+1]
0x180012a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a82  mov     rcx, [rbp+var_20]; this
0x180012a86  mov     rdx, rax; struct PropValue *
0x180012a89  call    ?AddTypeToProperty@CMBPropertyWriter@@QEAAJPEAUPropValue@@@Z; CMBPropertyWriter::AddTypeToProperty(PropValue *)
0x180012a8e  xor     ecx, ecx
0x180012a90  mov     ebx, eax
0x180012a92  test    eax, eax
0x180012a94  js      loc_180012BCE
0x180012a9a  lea     rax, [rbp+var_18]
0x180012a9e  mov     [rsp+70h+var_40], rax
0x180012aa3  mov     [rsp+70h+var_48], rcx
0x180012aa8  mov     [rsp+70h+var_50], ecx
0x180012aac  jmp     loc_180012BAD
0x180012ab1  test    byte ptr cs:g_dwDebugFlags, 3
0x180012ab8  jz      short loc_180012B2E
0x180012aba  mov     rax, [rdi]
0x180012abd  xor     r8d, r8d
0x180012ac0  mov     rcx, rdi
0x180012ac3  mov     rax, [rax+20h]
0x180012ac7  lea     edx, [r8+1]
0x180012acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ad0  mov     ebx, eax
0x180012ad2  mov     rcx, rdi
0x180012ad5  mov     rax, [rdi]
0x180012ad8  mov     rax, [rax+8]
0x180012adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ae1  mov     rcx, cs:g_pDebug
0x180012ae8  lea     r9, aSavetypes; "SaveTypes"
0x180012aef  mov     [rsp+70h+var_28], 38h ; '8'
0x180012af8  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012aff  mov     dword ptr [rsp+70h+var_30], ebx
0x180012b03  mov     r8d, 799h
0x180012b09  mov     dword ptr [rsp+70h+var_38], 3
0x180012b11  mov     dword ptr [rsp+70h+var_40], eax
0x180012b15  mov     eax, [rdi+8]
0x180012b18  mov     dword ptr [rsp+70h+var_48], eax
0x180012b1c  lea     rax, aSaveschemaEnco_0; "[SaveSchema] Encountered non-binary dat"...
0x180012b23  mov     qword ptr [rsp+70h+var_50], rax
0x180012b28  call    cs:__imp_PuDbgPrintW
0x180012b2e  mov     rax, [rdi]
0x180012b31  mov     rcx, rdi
0x180012b34  mov     rax, [rax+8]
0x180012b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b3d  cmp     eax, 2
0x180012b40  jnz     short loc_180012B93
0x180012b42  test    byte ptr cs:g_dwDebugFlags, 3
0x180012b49  jz      short loc_180012B93
0x180012b4b  mov     rax, [rdi]
0x180012b4e  xor     r8d, r8d
0x180012b51  mov     rcx, rdi
0x180012b54  mov     rax, [rax+18h]
0x180012b58  lea     edx, [r8+1]
0x180012b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b61  mov     rcx, cs:g_pDebug
0x180012b68  lea     r9, aSavetypes; "SaveTypes"
0x180012b6f  mov     [rsp+70h+var_48], rax
0x180012b74  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012b7b  lea     rax, aDataS; "Data: %s.\n"
0x180012b82  mov     r8d, 79Fh
0x180012b88  mov     qword ptr [rsp+70h+var_50], rax
0x180012b8d  call    cs:__imp_PuDbgPrintW
0x180012b93  lea     rax, [rbp+var_18]
0x180012b97  mov     [rsp+70h+var_40], rax; struct CMDBaseData **
0x180012b9c  mov     [rsp+70h+var_48], 0; struct CMDBaseObject **
0x180012ba5  mov     [rsp+70h+var_50], 0; unsigned int
0x180012bad  xor     r9d, r9d; unsigned int
0x180012bb0  xor     r8d, r8d; unsigned int
0x180012bb3  mov     edx, esi; unsigned int
0x180012bb5  mov     rcx, r12; this
0x180012bb8  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180012bbd  mov     ebx, eax
0x180012bbf  test    eax, eax
0x180012bc1  js      loc_180012C76
0x180012bc7  inc     esi
0x180012bc9  jmp     loc_1800129C2
0x180012bce  test    byte ptr cs:g_dwDebugFlags, 3
0x180012bd5  jz      loc_180012C76
0x180012bdb  mov     dword ptr [rsp+70h+var_40], eax
0x180012bdf  mov     r8d, 7D3h
0x180012be5  mov     eax, [rdi+8]
0x180012be8  mov     dword ptr [rsp+70h+var_48], eax
0x180012bec  lea     rax, aSaveschemaErro_6; "[SaveSchema] Error while saving types t"...
0x180012bf3  jmp     short loc_180012C16
0x180012bf5  test    byte ptr cs:g_dwDebugFlags, 3
0x180012bfc  jz      short loc_180012C76
0x180012bfe  mov     dword ptr [rsp+70h+var_40], eax
0x180012c02  mov     r8d, 7C9h
0x180012c08  mov     eax, [rdi+8]
0x180012c0b  mov     dword ptr [rsp+70h+var_48], eax
0x180012c0f  lea     rax, aSaveschemaErro_2; "[SaveSchema] Error while saving types t"...
0x180012c16  mov     rcx, cs:g_pDebug
0x180012c1d  lea     r9, aSavetypes; "SaveTypes"
0x180012c24  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012c2b  mov     qword ptr [rsp+70h+var_50], rax
0x180012c30  call    cs:__imp_PuDbgPrintW
0x180012c36  jmp     short loc_180012C76
0x180012c38  xor     ebx, ebx
0x180012c3a  jmp     short loc_180012C76
0x180012c3c  test    byte ptr cs:g_dwDebugFlags, 3
0x180012c43  jz      short loc_180012C76
0x180012c45  mov     rcx, cs:g_pDebug
0x180012c4c  lea     rax, aSaveschemaUnab_3; "[SaveSchema] Unable to open /Schema/Pro"...
0x180012c53  mov     dword ptr [rsp+70h+var_48], ebx
0x180012c57  lea     r9, aSavetypes; "SaveTypes"
0x180012c5e  mov     r8d, 77Ch
0x180012c64  mov     qword ptr [rsp+70h+var_50], rax
0x180012c69  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012c70  call    cs:__imp_PuDbgPrintW
0x180012c76  mov     eax, ebx
0x180012c78  mov     rbx, [rsp+70h+arg_0]
0x180012c80  add     rsp, 70h
0x180012c84  pop     r13
0x180012c86  pop     r12
0x180012c88  pop     rdi
0x180012c89  pop     rsi
0x180012c8a  pop     rbp
0x180012c8b  retn
```
