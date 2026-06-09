# SaveNames(CMDBaseObject *,CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *)

- ea: `0x180011e74`
- end: `0x1800120ad`
- name: `?SaveNames@@YAJPEAVCMDBaseObject@@PEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@@Z`
- size: `569`
- prototype: `int(struct CMDBaseObject *, struct CWriter *, struct CMBSchemaWriter **, struct CMBCollectionWriter **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800120b4`

## callees

- `0x180004290`
- `0x180007bd0`
- `0x180011658`
- `0x180011a38`
- `0x180011e74`
- `0x18002f630`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180011f5b`
- `IisRTL!PuDbgPrintW` at `0x180012054`
- `IisRTL!PuDbgPrintW` at `0x180012094`
- `IisRTL!PuDbgPrintW` at `0x180011f5b`
- `IisRTL!PuDbgPrintW` at `0x180012054`
- `IisRTL!PuDbgPrintW` at `0x180012094`

## string_xrefs

- `0x180011f81`: `IIsConfigObject`
- `0x180012070`: `[SaveSchema] Unable to open /Schema/Properties/Names. GetChildObject failed with hr = 0x%x.\n`
- `0x180012048`: `[SaveSchema] Error while saving names tree. GetPropertyWriter for ID:%d failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SaveNames(
        struct CMDBaseObject *a1,
        struct CWriter *a2,
        struct CMBSchemaWriter **a3,
        struct CMBCollectionWriter **a4)
{
  unsigned int v7; // esi
  CMDBaseObject *ChildObject; // rax
  int CollectionWriter; // ebx
  CMDBaseObject *v10; // r14
  unsigned int *v11; // rdi
  __int64 v12; // rax
  int MBPropertyWriter; // eax
  __int64 v14; // rax
  struct CMDBaseObject **v16; // [rsp+28h] [rbp-40h]
  struct CMDBaseData **v17; // [rsp+30h] [rbp-38h]
  struct CMBPropertyWriter *v18; // [rsp+40h] [rbp-28h] BYREF
  struct CMDBaseData *v19; // [rsp+48h] [rbp-20h] BYREF
  char *v20; // [rsp+50h] [rbp-18h] BYREF

  LODWORD(v18) = 0;
  v19 = 0;
  v20 = (char *)L"Names";
  v7 = 1;
  ChildObject = CMDBaseObject::GetChildObject(a1, &v20, (int *)&v18, 1);
  CollectionWriter = (int)v18;
  v10 = ChildObject;
  if ( (int)v18 >= 0 && ChildObject )
  {
    CollectionWriter = CMDBaseObject::EnumDataObject(ChildObject, 0, 0, 0, 0, 0, &v19);
    if ( CollectionWriter < 0 )
      return (unsigned int)CollectionWriter;
    while ( 1 )
    {
      v11 = (unsigned int *)v19;
      while ( 1 )
      {
        if ( !v11 )
          return 0;
        v12 = *(_QWORD *)v11;
        v18 = 0;
        if ( (*(unsigned int (__fastcall **)(unsigned int *))(v12 + 8))(v11) == 2 )
          break;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(v16) = v11[2];
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
            1815,
            "SaveNames",
            L"[SaveSchema] Encountered non-string data in the names tree of the schema. Ignoring entry for this ID: %d \n",
            v16);
        }
      }
      if ( (unsigned int)PropertyNotInShippedSchema(a2, v11[2]) )
      {
        if ( !*a4 )
        {
          CollectionWriter = GetCollectionWriter(a2, a3, a4, L"IIsConfigObject", 0, 0);
          if ( CollectionWriter < 0 )
            return (unsigned int)CollectionWriter;
        }
        MBPropertyWriter = CMBCollectionWriter::GetMBPropertyWriter(*a4, v11[2], &v18);
        CollectionWriter = MBPropertyWriter;
        if ( MBPropertyWriter < 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(v17) = MBPropertyWriter;
            LODWORD(v16) = v11[2];
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
              1845,
              "SaveNames",
              L"[SaveSchema] Error while saving names tree. GetPropertyWriter for ID:%d failed with hr = 0x%x.\n",
              v16,
              v17);
          }
          return (unsigned int)CollectionWriter;
        }
        v14 = (*(__int64 (__fastcall **)(unsigned int *, __int64))(*(_QWORD *)v11 + 24LL))(v11, 1);
        *((_QWORD *)v18 + 1) = v14;
      }
      CollectionWriter = CMDBaseObject::EnumDataObject(v10, v7, 0, 0, 0, 0, &v19);
      if ( CollectionWriter < 0 )
        return (unsigned int)CollectionWriter;
      ++v7;
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
      1788,
      "SaveNames",
      L"[SaveSchema] Unable to open /Schema/Properties/Names. GetChildObject failed with hr = 0x%x.\n",
      (_DWORD)v18);
  return (unsigned int)CollectionWriter;
}

```

## disassembly

```asm
0x180011e74  push    rbp
0x180011e76  push    rbx
0x180011e77  push    rsi
0x180011e78  push    rdi
0x180011e79  push    r12
0x180011e7b  push    r13
0x180011e7d  push    r14
0x180011e7f  push    r15
0x180011e81  mov     rbp, rsp
0x180011e84  sub     rsp, 68h
0x180011e88  xor     edi, edi
0x180011e8a  lea     rax, aNames; "Names"
0x180011e91  mov     r15, r9
0x180011e94  mov     dword ptr [rbp+var_28], edi
0x180011e97  mov     r13, r8
0x180011e9a  mov     [rbp+var_20], rdi
0x180011e9e  mov     r12, rdx
0x180011ea1  mov     [rbp+var_18], rax
0x180011ea5  lea     esi, [rdi+1]
0x180011ea8  mov     r9d, esi; int
0x180011eab  lea     r8, [rbp+var_28]; int *
0x180011eaf  lea     rdx, [rbp+var_18]; char **
0x180011eb3  call    ?GetChildObject@CMDBaseObject@@QEAAPEAV1@AEAPEADPEAJH@Z; CMDBaseObject::GetChildObject(char * &,long *,int)
0x180011eb8  mov     ebx, dword ptr [rbp+var_28]
0x180011ebb  mov     r14, rax
0x180011ebe  test    ebx, ebx
0x180011ec0  js      loc_180012060
0x180011ec6  test    rax, rax
0x180011ec9  jz      loc_180012060
0x180011ecf  lea     rax, [rbp+var_20]
0x180011ed3  xor     r9d, r9d; unsigned int
0x180011ed6  mov     [rsp+68h+var_38], rax; struct CMDBaseData **
0x180011edb  xor     r8d, r8d; unsigned int
0x180011ede  mov     [rsp+68h+var_40], rdi; struct CMDBaseObject **
0x180011ee3  xor     edx, edx; unsigned int
0x180011ee5  mov     rcx, r14; this
0x180011ee8  mov     [rsp+68h+var_48], edi; unsigned int
0x180011eec  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180011ef1  mov     ebx, eax
0x180011ef3  test    eax, eax
0x180011ef5  js      loc_18001209A
0x180011efb  mov     rdi, [rbp+var_20]
0x180011eff  test    rdi, rdi
0x180011f02  jz      loc_18001205C
0x180011f08  mov     rax, [rdi]
0x180011f0b  mov     rcx, rdi
0x180011f0e  mov     [rbp+var_28], 0
0x180011f16  mov     rax, [rax+8]
0x180011f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f1f  cmp     eax, 2
0x180011f22  jz      short loc_180011F63
0x180011f24  test    byte ptr cs:g_dwDebugFlags, 3
0x180011f2b  jz      short loc_180011EFF
0x180011f2d  mov     eax, [rdi+8]
0x180011f30  lea     r9, aSavenames; "SaveNames"
0x180011f37  mov     rcx, cs:g_pDebug
0x180011f3e  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180011f45  mov     dword ptr [rsp+68h+var_40], eax
0x180011f49  mov     r8d, 717h
0x180011f4f  lea     rax, aSaveschemaEnco; "[SaveSchema] Encountered non-string dat"...
0x180011f56  mov     qword ptr [rsp+68h+var_48], rax
0x180011f5b  call    cs:__imp_PuDbgPrintW
0x180011f61  jmp     short loc_180011EFF
0x180011f63  mov     edx, [rdi+8]; unsigned int
0x180011f66  mov     rcx, r12; struct CWriter *
0x180011f69  call    ?PropertyNotInShippedSchema@@YAHPEAVCWriter@@K@Z; PropertyNotInShippedSchema(CWriter *,ulong)
0x180011f6e  test    eax, eax
0x180011f70  jz      short loc_180011FDE
0x180011f72  cmp     qword ptr [r15], 0
0x180011f76  jnz     short loc_180011FA8
0x180011f78  mov     [rsp+68h+var_40], 0; unsigned __int16 *
0x180011f81  lea     r9, aIisconfigobjec; "IIsConfigObject"
0x180011f88  mov     r8, r15; struct CMBCollectionWriter **
0x180011f8b  mov     [rsp+68h+var_48], 0; int
0x180011f93  mov     rdx, r13; struct CMBSchemaWriter **
0x180011f96  mov     rcx, r12; struct CWriter *
0x180011f99  call    ?GetCollectionWriter@@YAJPEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@PEBGH3@Z; GetCollectionWriter(CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *,ushort const *,int,ushort const *)
0x180011f9e  mov     ebx, eax
0x180011fa0  test    eax, eax
0x180011fa2  js      loc_18001209A
0x180011fa8  mov     edx, [rdi+8]; unsigned int
0x180011fab  lea     r8, [rbp+var_28]; struct CMBPropertyWriter **
0x180011faf  mov     rcx, [r15]; this
0x180011fb2  call    ?GetMBPropertyWriter@CMBCollectionWriter@@QEAAJKPEAPEAVCMBPropertyWriter@@@Z; CMBCollectionWriter::GetMBPropertyWriter(ulong,CMBPropertyWriter * *)
0x180011fb7  mov     ebx, eax
0x180011fb9  test    eax, eax
0x180011fbb  js      short loc_180012019
0x180011fbd  mov     rax, [rdi]
0x180011fc0  xor     r8d, r8d
0x180011fc3  mov     rcx, rdi
0x180011fc6  mov     rax, [rax+18h]
0x180011fca  lea     edx, [r8+1]
0x180011fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fd3  mov     rcx, rax
0x180011fd6  mov     rax, [rbp+var_28]
0x180011fda  mov     [rax+8], rcx
0x180011fde  lea     rax, [rbp+var_20]
0x180011fe2  xor     r9d, r9d; unsigned int
0x180011fe5  mov     [rsp+68h+var_38], rax; struct CMDBaseData **
0x180011fea  xor     r8d, r8d; unsigned int
0x180011fed  mov     [rsp+68h+var_40], 0; struct CMDBaseObject **
0x180011ff6  mov     edx, esi; unsigned int
0x180011ff8  mov     rcx, r14; this
0x180011ffb  mov     [rsp+68h+var_48], 0; unsigned int
0x180012003  call    ?EnumDataObject@CMDBaseObject@@QEAAJKKKKPEAPEAV1@PEAPEAVCMDBaseData@@@Z; CMDBaseObject::EnumDataObject(ulong,ulong,ulong,ulong,CMDBaseObject * *,CMDBaseData * *)
0x180012008  mov     ebx, eax
0x18001200a  test    eax, eax
0x18001200c  js      loc_18001209A
0x180012012  inc     esi
0x180012014  jmp     loc_180011EFB
0x180012019  test    byte ptr cs:g_dwDebugFlags, 3
0x180012020  jz      short loc_18001209A
0x180012022  mov     rcx, cs:g_pDebug
0x180012029  lea     r9, aSavenames; "SaveNames"
0x180012030  mov     dword ptr [rsp+68h+var_38], eax
0x180012034  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x18001203b  mov     eax, [rdi+8]
0x18001203e  mov     r8d, 735h
0x180012044  mov     dword ptr [rsp+68h+var_40], eax
0x180012048  lea     rax, aSaveschemaErro_1; "[SaveSchema] Error while saving names t"...
0x18001204f  mov     qword ptr [rsp+68h+var_48], rax
0x180012054  call    cs:__imp_PuDbgPrintW
0x18001205a  jmp     short loc_18001209A
0x18001205c  xor     ebx, ebx
0x18001205e  jmp     short loc_18001209A
0x180012060  test    byte ptr cs:g_dwDebugFlags, 3
0x180012067  jz      short loc_18001209A
0x180012069  mov     rcx, cs:g_pDebug
0x180012070  lea     rax, aSaveschemaUnab_6; "[SaveSchema] Unable to open /Schema/Pro"...
0x180012077  mov     dword ptr [rsp+68h+var_40], ebx
0x18001207b  lea     r9, aSavenames; "SaveNames"
0x180012082  mov     r8d, 6FCh
0x180012088  mov     qword ptr [rsp+68h+var_48], rax
0x18001208d  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x180012094  call    cs:__imp_PuDbgPrintW
0x18001209a  mov     eax, ebx
0x18001209c  add     rsp, 68h
0x1800120a0  pop     r15
0x1800120a2  pop     r14
0x1800120a4  pop     r13
0x1800120a6  pop     r12
0x1800120a8  pop     rdi
0x1800120a9  pop     rsi
0x1800120aa  pop     rbx
0x1800120ab  pop     rbp
0x1800120ac  retn
```
