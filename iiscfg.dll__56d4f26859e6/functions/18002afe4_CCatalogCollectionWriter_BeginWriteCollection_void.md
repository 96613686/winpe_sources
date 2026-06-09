# CCatalogCollectionWriter::BeginWriteCollection(void)

- ea: `0x18002afe4`
- end: `0x18002b226`
- name: `?BeginWriteCollection@CCatalogCollectionWriter@@AEAAJXZ`
- size: `578`
- prototype: `__int64 __fastcall(CCatalogCollectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002b458`

## callees

- `0x18002ac94`
- `0x18002afe4`
- `0x18002c604`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b1b3`
- `msvcrt!_wcsicmp` at `0x18002b1b3`
- `ole32!CoTaskMemFree` at `0x18002b1f1`
- `ole32!CoTaskMemFree` at `0x18002b1ff`
- `ole32!CoTaskMemFree` at `0x18002b1f1`
- `ole32!CoTaskMemFree` at `0x18002b1ff`

## string_xrefs

- `0x18002b1ac`: `IIsConfigObject`

## pseudocode

```c
__int64 __fastcall CCatalogCollectionWriter::BeginWriteCollection(CCatalogCollectionWriter *this)
{
  CWriter *v2; // rcx
  void *v3; // rbp
  unsigned __int16 *v4; // rsi
  int v5; // ebx
  char *v6; // rdx
  __int64 v7; // r14
  __int64 v8; // r8
  unsigned int v9; // edx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // r8
  char *v13; // rdx
  int v14; // eax
  unsigned int v15; // r8d
  wchar_t *v16; // rdx
  LPVOID pv; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v19; // [rsp+68h] [rbp+10h] BYREF

  v2 = *(CWriter **)this;
  v3 = 0;
  pv = 0;
  v4 = 0;
  v19 = 0;
  v5 = CWriter::WriteToFile(v2, (char *)L"\t\t<Collection         InternalName =\"", g_cchBeginCollection, 0);
  if ( v5 < 0 )
    return (unsigned int)v5;
  v6 = (char *)*((_QWORD *)this + 2);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&v6[2 * v8] );
  v5 = CWriter::WriteToFile(*(CWriter **)this, v6, v8, 0);
  if ( v5 < 0 )
    return (unsigned int)v5;
  v9 = **((_DWORD **)this + 11) & 0x7B;
  if ( v9 )
  {
    v5 = CWriterGlobalHelper::FlagToString(
           *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
           v9,
           (unsigned __int16 **)&pv,
           L"TABLEMETA",
           0xAu);
    if ( v5 < 0
      || (v5 = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"  MetaFlagsEx=\"", g_cchMetaFlagsExEq, 0), v5 < 0) )
    {
      v3 = pv;
      goto LABEL_26;
    }
    v3 = pv;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)pv + v10) );
    v5 = CWriter::WriteToFile(*(CWriter **)this, (char *)pv, v10, 0);
    if ( v5 < 0 )
      goto LABEL_26;
  }
  v11 = **((_DWORD **)this + 10);
  if ( !v11 )
    goto LABEL_17;
  v5 = CWriterGlobalHelper::FlagToString(
         *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
         v11,
         &v19,
         L"TABLEMETA",
         9u);
  if ( v5 < 0
    || (v5 = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"  MetaFlags=\"", g_cchMetaFlagsEq, 0), v5 < 0) )
  {
    v4 = v19;
  }
  else
  {
    v4 = v19;
    v12 = -1;
    do
      ++v12;
    while ( v19[v12] );
    v5 = CWriter::WriteToFile(*(CWriter **)this, (char *)v19, v12, 0);
    if ( v5 >= 0 )
    {
LABEL_17:
      if ( !*((_QWORD *)this + 15) )
        goto LABEL_22;
      v5 = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"    ContainerClassList=\"", g_cchContainerClassListEq, 0);
      if ( v5 >= 0 )
      {
        v13 = (char *)*((_QWORD *)this + 15);
        do
          ++v7;
        while ( *(_WORD *)&v13[2 * v7] );
        v5 = CWriter::WriteToFile(*(CWriter **)this, v13, v7, 0);
        if ( v5 >= 0 )
        {
LABEL_22:
          v14 = _wcsicmp(*((const wchar_t **)this + 2), L"IIsConfigObject");
          v15 = g_cchInheritsFrom;
          v16 = L"\">\r\n";
          if ( v14 )
            v16 = L"\"    InheritsPropertiesFrom=\"MetabaseBaseClass\" >\r\n";
          else
            v15 = g_cchEndBeginCollectionCatalog;
          v5 = CWriter::WriteToFile(*(CWriter **)this, (char *)v16, v15, 0);
        }
      }
    }
  }
LABEL_26:
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002afe4  mov     [rsp+arg_10], rbx
0x18002afe9  push    rbp
0x18002afea  push    rsi
0x18002afeb  push    rdi
0x18002afec  push    r14
0x18002afee  push    r15
0x18002aff0  sub     rsp, 30h
0x18002aff4  mov     r8d, cs:?g_cchBeginCollection@@3KA; unsigned int
0x18002affb  lea     rdx, aCollectionInte; "\t\t<Collection         InternalName ="...
0x18002b002  xor     r15d, r15d
0x18002b005  mov     rdi, rcx
0x18002b008  mov     rcx, [rcx]; this
0x18002b00b  xor     r9d, r9d; int
0x18002b00e  mov     ebp, r15d
0x18002b011  mov     [rsp+58h+pv], r15
0x18002b016  mov     esi, r15d
0x18002b019  mov     [rsp+58h+arg_8], r15
0x18002b01e  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b023  mov     ebx, eax
0x18002b025  test    eax, eax
0x18002b027  js      loc_18002B205
0x18002b02d  mov     rdx, [rdi+10h]; void *
0x18002b031  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002b035  mov     r8, r14
0x18002b038  inc     r8; unsigned int
0x18002b03b  cmp     [rdx+r8*2], r15w
0x18002b040  jnz     short loc_18002B038
0x18002b042  mov     rcx, [rdi]; this
0x18002b045  xor     r9d, r9d; int
0x18002b048  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b04d  mov     ebx, eax
0x18002b04f  test    eax, eax
0x18002b051  js      loc_18002B205
0x18002b057  mov     rax, [rdi+58h]
0x18002b05b  mov     edx, [rax]
0x18002b05d  and     edx, 7Bh; unsigned int
0x18002b060  jz      short loc_18002B0DD
0x18002b062  mov     rcx, [rdi]
0x18002b065  lea     r9, aTablemeta; "TABLEMETA"
0x18002b06c  lea     r8, [rsp+58h+pv]; unsigned __int16 **
0x18002b071  mov     [rsp+58h+var_38], 0Ah; unsigned int
0x18002b079  mov     rcx, [rcx+10040h]; this
0x18002b080  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002b085  mov     ebx, eax
0x18002b087  test    eax, eax
0x18002b089  js      loc_18002B218
0x18002b08f  mov     r8d, cs:?g_cchMetaFlagsExEq@@3KA; unsigned int
0x18002b096  lea     rdx, aMetaflagsex_0; "\"  MetaFlagsEx=\""
0x18002b09d  mov     rcx, [rdi]; this
0x18002b0a0  xor     r9d, r9d; int
0x18002b0a3  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b0a8  mov     ebx, eax
0x18002b0aa  test    eax, eax
0x18002b0ac  js      loc_18002B218
0x18002b0b2  mov     rbp, [rsp+58h+pv]
0x18002b0b7  mov     r8, r14
0x18002b0ba  inc     r8; unsigned int
0x18002b0bd  cmp     [rbp+r8*2+0], r15w
0x18002b0c3  jnz     short loc_18002B0BA
0x18002b0c5  mov     rcx, [rdi]; this
0x18002b0c8  xor     r9d, r9d; int
0x18002b0cb  mov     rdx, rbp; void *
0x18002b0ce  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b0d3  mov     ebx, eax
0x18002b0d5  test    eax, eax
0x18002b0d7  js      loc_18002B1E9
0x18002b0dd  mov     rax, [rdi+50h]
0x18002b0e1  mov     edx, [rax]; unsigned int
0x18002b0e3  test    edx, edx
0x18002b0e5  jz      short loc_18002B161
0x18002b0e7  mov     rcx, [rdi]
0x18002b0ea  lea     r9, aTablemeta; "TABLEMETA"
0x18002b0f1  lea     r8, [rsp+58h+arg_8]; unsigned __int16 **
0x18002b0f6  mov     [rsp+58h+var_38], 9; unsigned int
0x18002b0fe  mov     rcx, [rcx+10040h]; this
0x18002b105  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002b10a  mov     ebx, eax
0x18002b10c  test    eax, eax
0x18002b10e  js      loc_18002B21F
0x18002b114  mov     r8d, cs:?g_cchMetaFlagsEq@@3KA; unsigned int
0x18002b11b  lea     rdx, aMetaflags_1; "\"  MetaFlags=\""
0x18002b122  mov     rcx, [rdi]; this
0x18002b125  xor     r9d, r9d; int
0x18002b128  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b12d  mov     ebx, eax
0x18002b12f  test    eax, eax
0x18002b131  js      loc_18002B21F
0x18002b137  mov     rsi, [rsp+58h+arg_8]
0x18002b13c  mov     r8, r14
0x18002b13f  inc     r8; unsigned int
0x18002b142  cmp     [rsi+r8*2], r15w
0x18002b147  jnz     short loc_18002B13F
0x18002b149  mov     rcx, [rdi]; this
0x18002b14c  xor     r9d, r9d; int
0x18002b14f  mov     rdx, rsi; void *
0x18002b152  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b157  mov     ebx, eax
0x18002b159  test    eax, eax
0x18002b15b  js      loc_18002B1E9
0x18002b161  cmp     [rdi+78h], r15
0x18002b165  jz      short loc_18002B1A8
0x18002b167  mov     r8d, cs:?g_cchContainerClassListEq@@3KA; unsigned int
0x18002b16e  lea     rdx, aContainerclass_0; "\"    ContainerClassList=\""
0x18002b175  mov     rcx, [rdi]; this
0x18002b178  xor     r9d, r9d; int
0x18002b17b  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b180  mov     ebx, eax
0x18002b182  test    eax, eax
0x18002b184  js      short loc_18002B1E9
0x18002b186  mov     rdx, [rdi+78h]; void *
0x18002b18a  inc     r14
0x18002b18d  cmp     [rdx+r14*2], r15w
0x18002b192  jnz     short loc_18002B18A
0x18002b194  mov     rcx, [rdi]; this
0x18002b197  xor     r9d, r9d; int
0x18002b19a  mov     r8d, r14d; unsigned int
0x18002b19d  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b1a2  mov     ebx, eax
0x18002b1a4  test    eax, eax
0x18002b1a6  js      short loc_18002B1E9
0x18002b1a8  mov     rcx, [rdi+10h]; String1
0x18002b1ac  lea     rdx, aIisconfigobjec; "IIsConfigObject"
0x18002b1b3  call    cs:__imp__wcsicmp
0x18002b1b9  mov     r8d, cs:?g_cchInheritsFrom@@3KA; ulong g_cchInheritsFrom
0x18002b1c0  lea     rcx, aInheritsproper_0; "\"    InheritsPropertiesFrom=\"Metabase"...
0x18002b1c7  test    eax, eax
0x18002b1c9  lea     rdx, asc_18003CA38; "\">\r\n"
0x18002b1d0  cmovz   r8d, cs:?g_cchEndBeginCollectionCatalog@@3KA; unsigned int
0x18002b1d8  cmovnz  rdx, rcx; void *
0x18002b1dc  mov     rcx, [rdi]; this
0x18002b1df  xor     r9d, r9d; int
0x18002b1e2  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b1e7  mov     ebx, eax
0x18002b1e9  test    rbp, rbp
0x18002b1ec  jz      short loc_18002B1F7
0x18002b1ee  mov     rcx, rbp; pv
0x18002b1f1  call    cs:__imp_CoTaskMemFree
0x18002b1f7  test    rsi, rsi
0x18002b1fa  jz      short loc_18002B205
0x18002b1fc  mov     rcx, rsi; pv
0x18002b1ff  call    cs:__imp_CoTaskMemFree
0x18002b205  mov     eax, ebx
0x18002b207  mov     rbx, [rsp+58h+arg_10]
0x18002b20c  add     rsp, 30h
0x18002b210  pop     r15
0x18002b212  pop     r14
0x18002b214  pop     rdi
0x18002b215  pop     rsi
0x18002b216  pop     rbp
0x18002b217  retn
0x18002b218  mov     rbp, [rsp+58h+pv]
0x18002b21d  jmp     short loc_18002B1E9
0x18002b21f  mov     rsi, [rsp+58h+arg_8]
0x18002b224  jmp     short loc_18002B1E9
```
