# Performance::RegistryTransferable<PerfDiagShutdown::CRuntimeInformationConfig>::readWriteImpl(bool)

- ea: `0x18001a008`
- end: `0x18001a3e0`
- name: `?readWriteImpl@?$RegistryTransferable@VCRuntimeInformationConfig@PerfDiagShutdown@@@Performance@@AEAAJ_N@Z`
- size: `984`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800b63d0`
- `0x1800b63e0`
- `0x1800b67d8`

## callees

- `0x18001890c`
- `0x180018aa4`
- `0x180019310`
- `0x18001933c`
- `0x180019370`
- `0x180019f7c`
- `0x18001a008`
- `0x18001a3e8`
- `0x18001a56c`
- `0x18002d40c`
- `0x180039b68`
- `0x180041bb4`
- `0x180041ea8`
- `0x180042fe0`
- `0x180044074`
- `0x1800441e4`
- `0x180056c14`
- `0x180057836`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a38b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a38b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a3c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a3c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Performance::RegistryTransferable<PerfDiagShutdown::CRuntimeInformationConfig>::readWriteImpl(
        char *a1,
        char a2)
{
  __int64 v4; // rsi
  unsigned __int16 *v5; // r9
  int v6; // eax
  unsigned int v7; // r9d
  signed int StringValue; // ebx
  __int64 i; // r13
  const WCHAR *v10; // rdx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  unsigned __int64 *v15; // r8
  int DWORDValue; // eax
  char *v17; // r8
  unsigned int v18; // r9d
  bool v19; // cc
  const unsigned __int16 **v20; // r14
  unsigned __int16 *BufferSetLength; // rax
  char *v22; // r14
  int BinaryValue; // eax
  void *v24; // rbx
  int v25; // eax
  unsigned int v26; // edi
  unsigned int *v27; // r8
  unsigned int lpData; // [rsp+20h] [rbp-88h]
  struct _SECURITY_ATTRIBUTES *v30; // [rsp+30h] [rbp-78h]
  unsigned int *v31; // [rsp+38h] [rbp-70h]
  HKEY v32; // [rsp+40h] [rbp-68h] BYREF
  ATL::CAtlException *v33; // [rsp+48h] [rbp-60h] BYREF
  HKEY hKey[11]; // [rsp+50h] [rbp-58h] BYREF
  void *Block; // [rsp+B0h] [rbp+8h] BYREF
  size_t Size; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v37; // [rsp+C0h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+20h] BYREF

  v32 = 0;
  lpSubKey = 0;
  v4 = (**(__int64 (__fastcall ***)(char *, HKEY *, LPCWSTR *))a1)(a1, &v32, &lpSubKey);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v32, lpSubKey, v5, lpData, a2 != 0 ? 131103 : 131097, v30, v31);
  StringValue = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
    {
      StringValue = (unsigned __int16)v6;
      goto LABEL_26;
    }
    goto LABEL_54;
  }
  for ( i = 0; ; ++i )
  {
    v10 = *(const WCHAR **)(v4 + 24 * i);
    if ( !v10 )
    {
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      return 0;
    }
    v11 = *(_DWORD *)(v4 + 24 * i + 8);
    if ( !v11 )
    {
      v27 = (unsigned int *)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
      {
        LODWORD(Block) = *v27;
        DWORDValue = RegSetValueExW(hKey[0], v10, 0, 4u, (const BYTE *)&Block, 4u);
      }
      else
      {
        DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)hKey, v10, v27);
      }
      goto LABEL_50;
    }
    v12 = v11 - 1;
    if ( v12 )
      break;
    v22 = &a1[*(int *)(v4 + 24 * i + 12)];
    if ( a2 )
    {
      v18 = (*((_DWORD *)v22 + 2) - *(_DWORD *)v22) & 0xFFFFFFFC;
      v17 = *(char **)v22;
LABEL_17:
      DWORDValue = ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, v10, v17, v18);
LABEL_50:
      v19 = DWORDValue <= 0;
      if ( DWORDValue )
      {
LABEL_51:
        if ( !v19 )
          DWORDValue = (unsigned __int16)DWORDValue | 0x80070000;
        StringValue = DWORDValue;
        goto LABEL_54;
      }
      continue;
    }
    Block = 0;
    LODWORD(Size) = 0;
    BinaryValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v10, 0, (unsigned int *)&Size);
    StringValue = BinaryValue;
    if ( BinaryValue )
    {
      if ( BinaryValue > 0 )
        StringValue = (unsigned __int16)BinaryValue | 0x80070000;
      operator delete(0);
      goto LABEL_54;
    }
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&Block, (unsigned int)Size) )
    {
LABEL_41:
      operator delete(Block);
      StringValue = -2147024882;
      goto LABEL_54;
    }
    v24 = Block;
    v25 = ATL::CRegKey::QueryBinaryValue(
            (ATL::CRegKey *)hKey,
            *(const unsigned __int16 **)(v4 + 24 * i),
            Block,
            (unsigned int *)&Size);
    v26 = v25;
    if ( v25 )
    {
      if ( v25 > 0 )
        v26 = (unsigned __int16)v25 | 0x80070000;
      operator delete(v24);
      StringValue = v26;
      goto LABEL_54;
    }
    try
    {
      std::vector<unsigned long>::resize(v22, (unsigned __int64)(unsigned int)Size >> 2);
      memcpy_0(*(void **)v22, v24, (unsigned int)Size);
      operator delete(v24);
    }
    catch ( std::bad_alloc )
    {
      goto LABEL_41;
    }
LABEL_46:
    ;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 != 1 )
      {
        StringValue = -2147418113;
        goto LABEL_54;
      }
      v15 = (unsigned __int64 *)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
        DWORDValue = ATL::CRegKey::SetQWORDValue((ATL::CRegKey *)hKey, v10, *v15);
      else
        DWORDValue = ATL::CRegKey::QueryQWORDValue((ATL::CRegKey *)hKey, v10, v15);
      goto LABEL_50;
    }
    v17 = &a1[*(int *)(v4 + 24 * i + 12)];
    if ( a2 )
    {
      v18 = *(_DWORD *)(v4 + 24 * i + 16);
      goto LABEL_17;
    }
    v37 = *(_DWORD *)(v4 + 24 * i + 16);
    DWORDValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v10, v17, &v37);
    v19 = DWORDValue <= 0;
    if ( DWORDValue )
      goto LABEL_51;
    if ( v37 != *(_DWORD *)(v4 + 24 * i + 16) )
    {
      StringValue = -2147024883;
      goto LABEL_54;
    }
    goto LABEL_46;
  }
  v20 = (const unsigned __int16 **)&a1[*(int *)(v4 + 24 * i + 12)];
  if ( a2 )
  {
    StringValue = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, v10, *v20, v7);
  }
  else
  {
    LODWORD(Block) = 0;
    StringValue = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, v10, 0, (unsigned int *)&Block);
    if ( !StringValue )
    {
      if ( (_DWORD)Block )
      {
        try
        {
          BufferSetLength = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(
                                                  v20,
                                                  (unsigned int)Block);
          StringValue = ATL::CRegKey::QueryStringValue(
                          (ATL::CRegKey *)hKey,
                          *(const unsigned __int16 **)(v4 + 24 * i),
                          BufferSetLength,
                          (unsigned int *)&Block);
          if ( StringValue || !(_DWORD)Block )
            ATL::CSimpleStringT<unsigned short,0>::SetLength(v20, 0);
          else
            ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v20);
        }
        catch ( ATL::CAtlException *v33 )
        {
          LODWORD(Block) = *(_DWORD *)v33;
          StringValue = (int)Block;
          goto LABEL_54;
        }
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty(v20);
      }
    }
  }
  if ( !StringValue )
    goto LABEL_46;
  if ( StringValue <= 0 )
    goto LABEL_54;
  StringValue = (unsigned __int16)StringValue;
LABEL_26:
  StringValue |= 0x80070000;
LABEL_54:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18001a008  mov     r11, rsp
0x18001a00b  push    rbx
0x18001a00c  push    rsi
0x18001a00d  push    rdi
0x18001a00e  push    r12
0x18001a010  push    r13
0x18001a012  push    r14
0x18001a014  push    r15
0x18001a016  sub     rsp, 70h
0x18001a01a  mov     r12b, dl
0x18001a01d  mov     r15, rcx
0x18001a020  mov     qword ptr [r11-68h], 0
0x18001a028  mov     qword ptr [r11+20h], 0
0x18001a030  mov     rax, [rcx]
0x18001a033  lea     r8, [r11+20h]
0x18001a037  lea     rdx, [r11-68h]
0x18001a03b  mov     rax, [rax]
0x18001a03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a043  mov     rsi, rax
0x18001a046  mov     [rsp+0A8h+hKey], 0
0x18001a04f  mov     [rsp+0A8h+var_50], 0
0x18001a058  mov     [rsp+0A8h+var_48], 0
0x18001a061  mov     cl, r12b
0x18001a064  neg     cl
0x18001a066  sbb     edx, edx
0x18001a068  and     edx, 6
0x18001a06b  add     edx, 20019h
0x18001a071  mov     [rsp+0A8h+cbData], edx; unsigned int
0x18001a075  mov     r8, [rsp+0A8h+lpSubKey]; lpSubKey
0x18001a07d  mov     rdx, [rsp+0A8h+var_68]; hKey
0x18001a082  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a087  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001a08c  mov     ebx, eax
0x18001a08e  test    eax, eax
0x18001a090  jz      short loc_18001A0A0
0x18001a092  jle     loc_18001A3AD
0x18001a098  movzx   ebx, ax
0x18001a09b  jmp     loc_18001A19F
0x18001a0a0  xor     r13d, r13d
0x18001a0a3  lea     rdi, ds:0[r13*2]
0x18001a0ab  add     rdi, r13
0x18001a0ae  mov     rdx, [rsi+rdi*8]; unsigned __int16 *
0x18001a0b2  test    rdx, rdx
0x18001a0b5  jz      loc_18001A3BB
0x18001a0bb  mov     ecx, [rsi+rdi*8+8]
0x18001a0bf  test    ecx, ecx
0x18001a0c1  jz      loc_18001A351
0x18001a0c7  sub     ecx, 1
0x18001a0ca  jz      loc_18001A236
0x18001a0d0  sub     ecx, 1
0x18001a0d3  jz      loc_18001A172
0x18001a0d9  sub     ecx, 1
0x18001a0dc  jz      short loc_18001A116
0x18001a0de  cmp     ecx, 1
0x18001a0e1  jz      short loc_18001A0ED
0x18001a0e3  mov     ebx, 8000FFFFh
0x18001a0e8  jmp     loc_18001A3AD
0x18001a0ed  movsxd  r8, dword ptr [rsi+rdi*8+0Ch]
0x18001a0f2  add     r8, r15; unsigned __int64 *
0x18001a0f5  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a0fa  test    r12b, r12b
0x18001a0fd  jz      short loc_18001A10C
0x18001a0ff  mov     r8, [r8]; unsigned __int64
0x18001a102  call    ?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z; ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)
0x18001a107  jmp     loc_18001A39D
0x18001a10c  call    ?QueryQWORDValue@CRegKey@ATL@@QEAAJPEBGAEA_K@Z; ATL::CRegKey::QueryQWORDValue(ushort const *,unsigned __int64 &)
0x18001a111  jmp     loc_18001A39D
0x18001a116  movsxd  r8, dword ptr [rsi+rdi*8+0Ch]
0x18001a11b  add     r8, r15; void *
0x18001a11e  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a123  test    r12b, r12b
0x18001a126  jz      short loc_18001A137
0x18001a128  mov     r9d, [rsi+rdi*8+10h]; unsigned int
0x18001a12d  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18001a132  jmp     loc_18001A39D
0x18001a137  mov     eax, [rsi+rdi*8+10h]
0x18001a13b  mov     [rsp+0A8h+arg_10], eax
0x18001a142  lea     r9, [rsp+0A8h+arg_10]; unsigned int *
0x18001a14a  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001a14f  test    eax, eax
0x18001a151  jnz     loc_18001A3A1
0x18001a157  mov     eax, [rsi+rdi*8+10h]
0x18001a15b  cmp     [rsp+0A8h+arg_10], eax
0x18001a162  jz      loc_18001A344
0x18001a168  mov     ebx, 8007000Dh
0x18001a16d  jmp     loc_18001A3AD
0x18001a172  movsxd  r14, dword ptr [rsi+rdi*8+0Ch]
0x18001a177  add     r14, r15
0x18001a17a  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a17f  test    r12b, r12b
0x18001a182  jz      short loc_18001A1AA
0x18001a184  mov     r8, [r14]; unsigned __int16 *
0x18001a187  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001a18c  mov     ebx, eax
0x18001a18e  test    ebx, ebx
0x18001a190  jz      loc_18001A344
0x18001a196  jle     loc_18001A3AD
0x18001a19c  movzx   ebx, bx
0x18001a19f  or      ebx, 80070000h
0x18001a1a5  jmp     loc_18001A3AD
0x18001a1aa  mov     dword ptr [rsp+0A8h+Block], 0
0x18001a1b5  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18001a1bd  xor     r8d, r8d; unsigned __int16 *
0x18001a1c0  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001a1c5  mov     ebx, eax
0x18001a1c7  test    eax, eax
0x18001a1c9  jnz     short loc_18001A18E
0x18001a1cb  mov     edx, dword ptr [rsp+0A8h+Block]
0x18001a1d2  mov     rcx, r14
0x18001a1d5  test    edx, edx
0x18001a1d7  jnz     short loc_18001A1E0
0x18001a1d9  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001a1de  jmp     short loc_18001A225
0x18001a1e0  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18001a1e5  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18001a1ed  mov     r8, rax; unsigned __int16 *
0x18001a1f0  mov     rdx, [rsi+rdi*8]; unsigned __int16 *
0x18001a1f4  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a1f9  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001a1fe  mov     ebx, eax
0x18001a200  test    eax, eax
0x18001a202  jnz     short loc_18001A21B
0x18001a204  mov     edx, dword ptr [rsp+0A8h+Block]
0x18001a20b  test    edx, edx
0x18001a20d  jz      short loc_18001A21B
0x18001a20f  dec     edx
0x18001a211  mov     rcx, r14
0x18001a214  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18001a219  jmp     short loc_18001A225
0x18001a21b  xor     edx, edx
0x18001a21d  mov     rcx, r14
0x18001a220  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001a225  jmp     loc_18001A18E
0x18001a22a  mov     ebx, dword ptr [rsp+0A8h+Block]
0x18001a231  jmp     loc_18001A3AD
0x18001a236  movsxd  r14, dword ptr [rsi+rdi*8+0Ch]
0x18001a23b  add     r14, r15
0x18001a23e  test    r12b, r12b
0x18001a241  jz      short loc_18001A25B
0x18001a243  mov     r9, [r14+8]
0x18001a247  sub     r9, [r14]
0x18001a24a  and     r9d, 0FFFFFFFCh
0x18001a24e  mov     r8, [r14]
0x18001a251  lea     rcx, [rsp+0A8h+hKey]
0x18001a256  jmp     loc_18001A12D
0x18001a25b  mov     [rsp+0A8h+Block], 0
0x18001a267  mov     dword ptr [rsp+0A8h+Size], 0
0x18001a272  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18001a27a  xor     r8d, r8d; void *
0x18001a27d  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a282  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001a287  mov     ebx, eax
0x18001a289  test    eax, eax
0x18001a28b  jz      short loc_18001A2A4
0x18001a28d  jle     short loc_18001A298
0x18001a28f  movzx   ebx, ax
0x18001a292  or      ebx, 80070000h
0x18001a298  xor     ecx, ecx; Block
0x18001a29a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a29f  jmp     loc_18001A3AD
0x18001a2a4  mov     edx, dword ptr [rsp+0A8h+Size]
0x18001a2ab  lea     rcx, [rsp+0A8h+Block]
0x18001a2b3  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18001a2b8  test    al, al
0x18001a2ba  jnz     short loc_18001A2D3
0x18001a2bc  mov     rcx, [rsp+0A8h+Block]; Block
0x18001a2c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a2c9  mov     ebx, 8007000Eh
0x18001a2ce  jmp     loc_18001A3AD
0x18001a2d3  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18001a2db  mov     rbx, [rsp+0A8h+Block]
0x18001a2e3  mov     r8, rbx; void *
0x18001a2e6  mov     rdx, [rsi+rdi*8]; unsigned __int16 *
0x18001a2ea  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a2ef  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001a2f4  mov     edi, eax
0x18001a2f6  test    eax, eax
0x18001a2f8  jz      short loc_18001A314
0x18001a2fa  jle     short loc_18001A305
0x18001a2fc  movzx   edi, ax
0x18001a2ff  or      edi, 80070000h
0x18001a305  mov     rcx, rbx; Block
0x18001a308  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a30d  mov     ebx, edi
0x18001a30f  jmp     loc_18001A3AD
0x18001a314  mov     edx, dword ptr [rsp+0A8h+Size]
0x18001a31b  shr     rdx, 2
0x18001a31f  mov     rcx, r14
0x18001a322  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18001a327  nop
0x18001a328  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x18001a330  mov     rdx, rbx; Src
0x18001a333  mov     rcx, [r14]; void *
0x18001a336  call    memcpy_0
0x18001a33b  nop
0x18001a33c  mov     rcx, rbx; Block
0x18001a33f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a344  inc     r13
0x18001a347  jmp     loc_18001A0A3
0x18001a34c  jmp     loc_18001A2BC
0x18001a351  movsxd  r8, dword ptr [rsi+rdi*8+0Ch]
0x18001a356  add     r8, r15; unsigned int *
0x18001a359  test    r12b, r12b
0x18001a35c  jz      short loc_18001A393
0x18001a35e  mov     eax, [r8]
0x18001a361  mov     dword ptr [rsp+0A8h+Block], eax
0x18001a368  mov     [rsp+0A8h+cbData], 4; cbData
0x18001a370  lea     rax, [rsp+0A8h+Block]
0x18001a378  mov     [rsp+0A8h+lpData], rax; lpData
0x18001a37d  mov     r9d, 4; dwType
0x18001a383  xor     r8d, r8d; Reserved
0x18001a386  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001a38b  call    cs:__imp_RegSetValueExW
0x18001a391  jmp     short loc_18001A39D
0x18001a393  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a398  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001a39d  test    eax, eax
0x18001a39f  jz      short loc_18001A344
0x18001a3a1  jle     short loc_18001A3AB
0x18001a3a3  movzx   eax, ax
0x18001a3a6  or      eax, 80070000h
0x18001a3ab  mov     ebx, eax
0x18001a3ad  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a3b2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a3b7  mov     eax, ebx
0x18001a3b9  jmp     short loc_18001A3D0
0x18001a3bb  cmp     [rsp+0A8h+hKey], 0
0x18001a3c1  jz      short loc_18001A3CE
0x18001a3c3  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001a3c8  call    cs:__imp_RegCloseKey
0x18001a3ce  xor     eax, eax
0x18001a3d0  add     rsp, 70h
0x18001a3d4  pop     r15
0x18001a3d6  pop     r14
0x18001a3d8  pop     r13
0x18001a3da  pop     r12
0x18001a3dc  pop     rdi
0x18001a3dd  pop     rsi
0x18001a3de  pop     rbx
0x18001a3df  retn
```
