# CMBCollectionWriter::BeginWriteCollection(void)

- ea: `0x18002f494`
- end: `0x18002f627`
- name: `?BeginWriteCollection@CMBCollectionWriter@@AEAAJXZ`
- size: `403`
- prototype: `__int64 __fastcall(CMBCollectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18002f998`

## callees

- `0x180006d08`
- `0x180008a08`
- `0x18002bdb4`
- `0x18002f494`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002f4ba`
- `msvcrt!_wcsicmp` at `0x18002f4ba`

## string_xrefs

- `0x18002f4a4`: `IIsConfigObject`

## pseudocode

```c
__int64 __fastcall CMBCollectionWriter::BeginWriteCollection(CMBCollectionWriter *this)
{
  const wchar_t *v2; // rcx
  _WORD *v3; // rsi
  wchar_t *v4; // r14
  int v5; // eax
  int v6; // edi
  _WORD *v7; // rdx
  __int64 v8; // rbp
  __int64 v9; // r8
  __int64 v10; // r8
  _WORD *v11; // rdx
  __int64 v12; // r8
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  v2 = (const wchar_t *)*((_QWORD *)this + 1);
  v3 = 0;
  Block = 0;
  v4 = L"\"  MetaFlagsEx=\"NOTABLESCHEMAHEAPENTRY\">\r\n";
  if ( _wcsicmp(v2, L"IIsConfigObject") )
    v4 = L"\"    InheritsPropertiesFrom=\"MetabaseBaseClass\" >\r\n";
  if ( !*((_DWORD *)this + 6)
    || (v5 = CWriterGlobalHelper::FlagToString(
               *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
               0x40u,
               (unsigned __int16 **)&Block,
               L"TABLEMETA",
               0xAu),
        v3 = Block,
        v6 = v5,
        v5 >= 0) )
  {
    v6 = CWriter::WriteToFile(*(CWriter **)this, L"\t\t<Collection         InternalName =\"", g_cchBeginCollection, 0);
    if ( v6 >= 0 )
    {
      v7 = (_WORD *)*((_QWORD *)this + 1);
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      v6 = CWriter::WriteToFile(*(CWriter **)this, v7, v9, 0);
      if ( v6 >= 0 )
      {
        if ( !*((_DWORD *)this + 6) )
          goto LABEL_26;
        v6 = CWriter::WriteToFile(*(CWriter **)this, L"\"  MetaFlagsEx=\"", g_cchMetaFlagsExEq, 0);
        if ( v6 >= 0 )
        {
          v10 = -1;
          do
            ++v10;
          while ( v3[v10] );
          v6 = CWriter::WriteToFile(*(CWriter **)this, v3, v10, 0);
          if ( v6 >= 0 )
          {
LABEL_26:
            if ( !*((_QWORD *)this + 2) )
              goto LABEL_27;
            v6 = CWriter::WriteToFile(*(CWriter **)this, L"\"    ContainerClassList=\"", g_cchContainerClassListEq, 0);
            if ( v6 >= 0 )
            {
              v11 = (_WORD *)*((_QWORD *)this + 2);
              v12 = -1;
              do
                ++v12;
              while ( v11[v12] );
              v6 = CWriter::WriteToFile(*(CWriter **)this, v11, v12, 0);
              if ( v6 >= 0 )
              {
LABEL_27:
                do
                  ++v8;
                while ( v4[v8] );
                v6 = CWriter::WriteToFile(*(CWriter **)this, v4, v8, 0);
              }
            }
          }
        }
      }
    }
  }
  if ( v3 )
    operator delete(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002f494  push    rbx
0x18002f496  push    rbp
0x18002f497  push    rsi
0x18002f498  push    rdi
0x18002f499  push    r14
0x18002f49b  push    r15
0x18002f49d  sub     rsp, 38h
0x18002f4a1  mov     rbx, rcx
0x18002f4a4  lea     rdx, aIisconfigobjec; "IIsConfigObject"
0x18002f4ab  mov     rcx, [rcx+8]; String1
0x18002f4af  xor     r15d, r15d
0x18002f4b2  mov     esi, r15d
0x18002f4b5  mov     [rsp+68h+Block], r15
0x18002f4ba  call    cs:__imp__wcsicmp
0x18002f4c0  test    eax, eax
0x18002f4c2  lea     rcx, aInheritsproper; "\"    InheritsPropertiesFrom=\"Metabase"...
0x18002f4c9  lea     r14, aMetaflagsexNot; "\"  MetaFlagsEx=\"NOTABLESCHEMAHEAPENTR"...
0x18002f4d0  cmovnz  r14, rcx
0x18002f4d4  cmp     [rbx+18h], r15d
0x18002f4d8  jz      short loc_18002F510
0x18002f4da  mov     rcx, [rbx]
0x18002f4dd  lea     r9, aTablemeta; "TABLEMETA"
0x18002f4e4  lea     r8, [rsp+68h+Block]; unsigned __int16 **
0x18002f4e9  mov     [rsp+68h+var_48], 0Ah; unsigned int
0x18002f4f1  lea     edx, [r15+40h]; unsigned int
0x18002f4f5  mov     rcx, [rcx+10040h]; this
0x18002f4fc  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002f501  mov     rsi, [rsp+68h+Block]
0x18002f506  mov     edi, eax
0x18002f508  test    eax, eax
0x18002f50a  js      loc_18002F60B
0x18002f510  mov     r8d, cs:?g_cchBeginCollection@@3KA; unsigned int
0x18002f517  lea     rdx, aCollectionInte; "\t\t<Collection         InternalName ="...
0x18002f51e  mov     rcx, [rbx]; this
0x18002f521  xor     r9d, r9d; int
0x18002f524  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f529  mov     edi, eax
0x18002f52b  test    eax, eax
0x18002f52d  js      loc_18002F60B
0x18002f533  mov     rdx, [rbx+8]; void *
0x18002f537  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002f53b  mov     r8, rbp
0x18002f53e  inc     r8; unsigned int
0x18002f541  cmp     [rdx+r8*2], r15w
0x18002f546  jnz     short loc_18002F53E
0x18002f548  mov     rcx, [rbx]; this
0x18002f54b  xor     r9d, r9d; int
0x18002f54e  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f553  mov     edi, eax
0x18002f555  test    eax, eax
0x18002f557  js      loc_18002F60B
0x18002f55d  cmp     [rbx+18h], r15d
0x18002f561  jz      short loc_18002F5A7
0x18002f563  mov     r8d, cs:?g_cchMetaFlagsExEq@@3KA; unsigned int
0x18002f56a  lea     rdx, aMetaflagsex_0; "\"  MetaFlagsEx=\""
0x18002f571  mov     rcx, [rbx]; this
0x18002f574  xor     r9d, r9d; int
0x18002f577  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f57c  mov     edi, eax
0x18002f57e  test    eax, eax
0x18002f580  js      loc_18002F60B
0x18002f586  mov     r8, rbp
0x18002f589  inc     r8; unsigned int
0x18002f58c  cmp     [rsi+r8*2], r15w
0x18002f591  jnz     short loc_18002F589
0x18002f593  mov     rcx, [rbx]; this
0x18002f596  xor     r9d, r9d; int
0x18002f599  mov     rdx, rsi; void *
0x18002f59c  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f5a1  mov     edi, eax
0x18002f5a3  test    eax, eax
0x18002f5a5  js      short loc_18002F60B
0x18002f5a7  cmp     [rbx+10h], r15
0x18002f5ab  jz      short loc_18002F5EE
0x18002f5ad  mov     r8d, cs:?g_cchContainerClassListEq@@3KA; unsigned int
0x18002f5b4  lea     rdx, aContainerclass; "\"    ContainerClassList=\""
0x18002f5bb  mov     rcx, [rbx]; this
0x18002f5be  xor     r9d, r9d; int
0x18002f5c1  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f5c6  mov     edi, eax
0x18002f5c8  test    eax, eax
0x18002f5ca  js      short loc_18002F60B
0x18002f5cc  mov     rdx, [rbx+10h]; void *
0x18002f5d0  mov     r8, rbp
0x18002f5d3  inc     r8; unsigned int
0x18002f5d6  cmp     [rdx+r8*2], r15w
0x18002f5db  jnz     short loc_18002F5D3
0x18002f5dd  mov     rcx, [rbx]; this
0x18002f5e0  xor     r9d, r9d; int
0x18002f5e3  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f5e8  mov     edi, eax
0x18002f5ea  test    eax, eax
0x18002f5ec  js      short loc_18002F60B
0x18002f5ee  inc     rbp
0x18002f5f1  cmp     [r14+rbp*2], r15w
0x18002f5f6  jnz     short loc_18002F5EE
0x18002f5f8  mov     rcx, [rbx]; this
0x18002f5fb  mov     r8d, ebp; unsigned int
0x18002f5fe  xor     r9d, r9d; int
0x18002f601  mov     rdx, r14; void *
0x18002f604  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f609  mov     edi, eax
0x18002f60b  test    rsi, rsi
0x18002f60e  jz      short loc_18002F618
0x18002f610  mov     rcx, rsi; Block
0x18002f613  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f618  mov     eax, edi
0x18002f61a  add     rsp, 38h
0x18002f61e  pop     r15
0x18002f620  pop     r14
0x18002f622  pop     rdi
0x18002f623  pop     rsi
0x18002f624  pop     rbp
0x18002f625  pop     rbx
0x18002f626  retn
```
