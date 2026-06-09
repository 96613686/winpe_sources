# Performance::RegistryTransferable<PerfDiagBoot::CSharedRegistryConfig>::readWriteImpl(bool)

- ea: `0x18003d1a0`
- end: `0x18003d556`
- name: `?readWriteImpl@?$RegistryTransferable@VCSharedRegistryConfig@PerfDiagBoot@@@Performance@@AEAAJ_N@Z`
- size: `950`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `20`
- tags: `file_ops, registry_config`

## callers

- `0x1800279d8`
- `0x18003d190`
- `0x1800b4fe0`

## callees

- `0x18001890c`
- `0x180018aa4`
- `0x180019310`
- `0x18001933c`
- `0x180019370`
- `0x180019f7c`
- `0x18001a3e8`
- `0x18001a56c`
- `0x18002d40c`
- `0x180039b68`
- `0x18003d1a0`
- `0x180041bb4`
- `0x180041ea8`
- `0x180042fe0`
- `0x180044010`
- `0x180044074`
- `0x1800441e4`
- `0x180056c14`
- `0x180057836`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d23f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d23f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Performance::RegistryTransferable<PerfDiagBoot::CSharedRegistryConfig>::readWriteImpl(
        char *a1,
        char a2)
{
  __int64 v4; // r14
  unsigned __int16 *v5; // r9
  int v6; // eax
  unsigned int v7; // ebx
  __int64 i; // rax
  __int64 v10; // rsi
  const unsigned __int16 *v11; // rdx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  signed int StringValue; // edi
  __int64 *v17; // r8
  LSTATUS DWORDValue; // eax
  bool v19; // cc
  BYTE *v20; // r8
  const BYTE **v21; // rbx
  unsigned __int16 *BufferSetLength; // rax
  char *v23; // r15
  LSTATUS v24; // eax
  int BinaryValue; // eax
  void *v26; // rcx
  void *v27; // rbx
  int v28; // eax
  int *v29; // r8
  unsigned int v30; // [rsp+20h] [rbp-88h]
  HKEY v31; // [rsp+40h] [rbp-68h] BYREF
  __int64 v32; // [rsp+48h] [rbp-60h]
  ATL::CAtlException *v33; // [rsp+50h] [rbp-58h] BYREF
  HKEY hKey[10]; // [rsp+58h] [rbp-50h] BYREF
  void *Block; // [rsp+B0h] [rbp+8h] BYREF
  size_t Size; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v37; // [rsp+C0h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+20h] BYREF

  v31 = 0;
  lpSubKey = 0;
  v4 = (**(__int64 (__fastcall ***)(char *, HKEY *, LPCWSTR *))a1)(a1, &v31, &lpSubKey);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v31, lpSubKey, v5, v30, a2 != 0 ? 131103 : 131097);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v7;
  }
  for ( i = 0; ; i = v32 + 1 )
  {
    v32 = i;
    v10 = 3 * i;
    v11 = *(const unsigned __int16 **)(v4 + 24 * i);
    if ( !v11 )
    {
      StringValue = 0;
      goto LABEL_59;
    }
    v12 = *(_DWORD *)(v4 + 24 * i + 8);
    if ( !v12 )
    {
      v29 = (int *)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
        DWORDValue = ATL::CRegKey::SetDWORDValue(hKey, v11, *v29);
      else
        DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)hKey, v11, (unsigned int *)v29);
      goto LABEL_18;
    }
    v13 = v12 - 1;
    if ( !v13 )
      break;
    v14 = v13 - 1;
    if ( !v14 )
    {
      v21 = (const BYTE **)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
      {
        StringValue = ATL::CRegKey::SetStringValue(hKey, v11, *v21);
      }
      else
      {
        LODWORD(Block) = 0;
        StringValue = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, v11, 0, (unsigned int *)&Block);
        if ( !StringValue )
        {
          if ( (_DWORD)Block )
          {
            try
            {
              BufferSetLength = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(
                                                      v21,
                                                      (unsigned int)Block);
              StringValue = ATL::CRegKey::QueryStringValue(
                              (ATL::CRegKey *)hKey,
                              *(const unsigned __int16 **)(v4 + 8 * v10),
                              BufferSetLength,
                              (unsigned int *)&Block);
              if ( StringValue || !(_DWORD)Block )
                ATL::CSimpleStringT<unsigned short,0>::SetLength(v21, 0);
              else
                ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v21);
            }
            catch ( ATL::CAtlException *v33 )
            {
              LODWORD(Block) = *(_DWORD *)v33;
              StringValue = (int)Block;
              goto LABEL_59;
            }
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::Empty(v21);
          }
        }
      }
      goto LABEL_19;
    }
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
      {
        StringValue = -2147418113;
        goto LABEL_59;
      }
      v17 = (__int64 *)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
        DWORDValue = ATL::CRegKey::SetQWORDValue(hKey, v11, *v17);
      else
        DWORDValue = ATL::CRegKey::QueryQWORDValue((ATL::CRegKey *)hKey, v11, (unsigned __int64 *)v17);
LABEL_18:
      StringValue = DWORDValue;
LABEL_19:
      v19 = StringValue <= 0;
      if ( StringValue )
        goto LABEL_20;
      continue;
    }
    v20 = (BYTE *)&a1[*(int *)(v4 + 24 * i + 12)];
    if ( a2 )
    {
      StringValue = ATL::CRegKey::SetBinaryValue(hKey, v11, v20, *(_DWORD *)(v4 + 24 * i + 16));
      if ( StringValue )
        goto LABEL_29;
    }
    else
    {
      v37 = *(_DWORD *)(v4 + 24 * i + 16);
      StringValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v11, v20, &v37);
      if ( StringValue )
      {
LABEL_29:
        v19 = StringValue <= 0;
LABEL_20:
        if ( v19 )
          goto LABEL_59;
        StringValue = (unsigned __int16)StringValue;
        goto LABEL_22;
      }
      if ( v37 != *(_DWORD *)(v4 + 8 * v10 + 16) )
      {
        StringValue = -2147024883;
        goto LABEL_59;
      }
    }
LABEL_25:
    ;
  }
  v23 = &a1[*(int *)(v4 + 24 * i + 12)];
  if ( a2 )
  {
    v24 = ATL::CRegKey::SetBinaryValue(
            hKey,
            v11,
            *(const BYTE **)v23,
            (*((_DWORD *)v23 + 2) - *(_DWORD *)v23) & 0xFFFFFFFC);
    StringValue = v24;
    if ( !v24 )
      goto LABEL_25;
    if ( v24 <= 0 )
      goto LABEL_59;
    StringValue = (unsigned __int16)v24;
LABEL_22:
    StringValue |= 0x80070000;
    goto LABEL_59;
  }
  Block = 0;
  LODWORD(Size) = 0;
  BinaryValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v11, 0, (unsigned int *)&Size);
  StringValue = BinaryValue;
  if ( BinaryValue )
  {
    if ( BinaryValue > 0 )
      StringValue = (unsigned __int16)BinaryValue | 0x80070000;
    v26 = 0;
    goto LABEL_48;
  }
  if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&Block, (unsigned int)Size) )
  {
LABEL_50:
    operator delete(Block);
    StringValue = -2147024882;
    goto LABEL_59;
  }
  v27 = Block;
  v28 = ATL::CRegKey::QueryBinaryValue(
          (ATL::CRegKey *)hKey,
          *(const unsigned __int16 **)(v4 + 8 * v10),
          Block,
          (unsigned int *)&Size);
  StringValue = v28;
  if ( !v28 )
  {
    try
    {
      std::vector<unsigned long>::resize(v23, (unsigned __int64)(unsigned int)Size >> 2);
      memcpy_0(*(void **)v23, v27, (unsigned int)Size);
      operator delete(v27);
    }
    catch ( std::bad_alloc )
    {
      goto LABEL_50;
    }
    goto LABEL_25;
  }
  if ( v28 > 0 )
    StringValue = (unsigned __int16)v28 | 0x80070000;
  v26 = v27;
LABEL_48:
  operator delete(v26);
LABEL_59:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18003d1a0  mov     r11, rsp
0x18003d1a3  push    rbx
0x18003d1a4  push    rsi
0x18003d1a5  push    rdi
0x18003d1a6  push    r12
0x18003d1a8  push    r13
0x18003d1aa  push    r14
0x18003d1ac  push    r15
0x18003d1ae  sub     rsp, 70h
0x18003d1b2  mov     r13b, dl
0x18003d1b5  mov     r12, rcx
0x18003d1b8  mov     qword ptr [r11-68h], 0
0x18003d1c0  mov     qword ptr [r11+20h], 0
0x18003d1c8  mov     rax, [rcx]
0x18003d1cb  lea     r8, [r11+20h]
0x18003d1cf  lea     rdx, [r11-68h]
0x18003d1d3  mov     rax, [rax]
0x18003d1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1db  mov     r14, rax
0x18003d1de  mov     [rsp+0A8h+hKey], 0
0x18003d1e7  mov     [rsp+0A8h+var_48], 0
0x18003d1f0  mov     [rsp+0A8h+var_40], 0
0x18003d1f9  mov     cl, r13b
0x18003d1fc  neg     cl
0x18003d1fe  sbb     edx, edx
0x18003d200  and     edx, 6
0x18003d203  add     edx, 20019h
0x18003d209  mov     [rsp+0A8h+var_80], edx; unsigned int
0x18003d20d  mov     r8, [rsp+0A8h+lpSubKey]; lpSubKey
0x18003d215  mov     rdx, [rsp+0A8h+var_68]; hKey
0x18003d21a  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d21f  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18003d224  mov     ebx, eax
0x18003d226  test    eax, eax
0x18003d228  jz      short loc_18003D24C
0x18003d22a  jle     short loc_18003D235
0x18003d22c  movzx   ebx, ax
0x18003d22f  or      ebx, 80070000h
0x18003d235  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18003d23a  test    rcx, rcx
0x18003d23d  jz      short loc_18003D245
0x18003d23f  call    cs:__imp_RegCloseKey
0x18003d245  mov     eax, ebx
0x18003d247  jmp     loc_18003D546
0x18003d24c  xor     eax, eax
0x18003d24e  mov     [rsp+0A8h+var_60], rax
0x18003d253  lea     rsi, [rax+rax*2]
0x18003d257  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18003d25b  test    rdx, rdx
0x18003d25e  jz      loc_18003D538
0x18003d264  mov     ecx, [r14+rsi*8+8]
0x18003d269  test    ecx, ecx
0x18003d26b  jz      loc_18003D50F
0x18003d271  sub     ecx, 1
0x18003d274  jz      loc_18003D3E9
0x18003d27a  sub     ecx, 1
0x18003d27d  jz      loc_18003D33C
0x18003d283  sub     ecx, 1
0x18003d286  jz      short loc_18003D2D2
0x18003d288  cmp     ecx, 1
0x18003d28b  jz      short loc_18003D297
0x18003d28d  mov     edi, 8000FFFFh
0x18003d292  jmp     loc_18003D53A
0x18003d297  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18003d29c  add     r8, r12; unsigned __int64 *
0x18003d29f  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d2a4  test    r13b, r13b
0x18003d2a7  jz      short loc_18003D2B3
0x18003d2a9  mov     r8, [r8]; unsigned __int64
0x18003d2ac  call    ?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z; ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)
0x18003d2b1  jmp     short loc_18003D2B8
0x18003d2b3  call    ?QueryQWORDValue@CRegKey@ATL@@QEAAJPEBGAEA_K@Z; ATL::CRegKey::QueryQWORDValue(ushort const *,unsigned __int64 &)
0x18003d2b8  mov     edi, eax
0x18003d2ba  test    edi, edi
0x18003d2bc  jz      short loc_18003D2F4
0x18003d2be  jle     loc_18003D53A
0x18003d2c4  movzx   edi, di
0x18003d2c7  or      edi, 80070000h
0x18003d2cd  jmp     loc_18003D53A
0x18003d2d2  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18003d2d7  add     r8, r12; void *
0x18003d2da  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d2df  test    r13b, r13b
0x18003d2e2  jz      short loc_18003D301
0x18003d2e4  mov     r9d, [r14+rsi*8+10h]; unsigned int
0x18003d2e9  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18003d2ee  mov     edi, eax
0x18003d2f0  test    eax, eax
0x18003d2f2  jnz     short loc_18003D338
0x18003d2f4  mov     rax, [rsp+0A8h+var_60]
0x18003d2f9  inc     rax
0x18003d2fc  jmp     loc_18003D24E
0x18003d301  mov     eax, [r14+rsi*8+10h]
0x18003d306  mov     [rsp+0A8h+arg_10], eax
0x18003d30d  lea     r9, [rsp+0A8h+arg_10]; unsigned int *
0x18003d315  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18003d31a  mov     edi, eax
0x18003d31c  test    eax, eax
0x18003d31e  jnz     short loc_18003D338
0x18003d320  mov     eax, [r14+rsi*8+10h]
0x18003d325  cmp     [rsp+0A8h+arg_10], eax
0x18003d32c  jz      short loc_18003D2F4
0x18003d32e  mov     edi, 8007000Dh
0x18003d333  jmp     loc_18003D53A
0x18003d338  test    edi, edi
0x18003d33a  jmp     short loc_18003D2BE
0x18003d33c  movsxd  rbx, dword ptr [r14+rsi*8+0Ch]
0x18003d341  add     rbx, r12
0x18003d344  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d349  test    r13b, r13b
0x18003d34c  jz      short loc_18003D35D
0x18003d34e  mov     r8, [rbx]; unsigned __int16 *
0x18003d351  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18003d356  mov     edi, eax
0x18003d358  jmp     loc_18003D2BA
0x18003d35d  mov     dword ptr [rsp+0A8h+Block], 0
0x18003d368  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18003d370  xor     r8d, r8d; unsigned __int16 *
0x18003d373  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18003d378  mov     edi, eax
0x18003d37a  test    eax, eax
0x18003d37c  jnz     short loc_18003D358
0x18003d37e  mov     edx, dword ptr [rsp+0A8h+Block]
0x18003d385  mov     rcx, rbx
0x18003d388  test    edx, edx
0x18003d38a  jnz     short loc_18003D393
0x18003d38c  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18003d391  jmp     short loc_18003D3D8
0x18003d393  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18003d398  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18003d3a0  mov     r8, rax; unsigned __int16 *
0x18003d3a3  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18003d3a7  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d3ac  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18003d3b1  mov     edi, eax
0x18003d3b3  test    eax, eax
0x18003d3b5  jnz     short loc_18003D3CE
0x18003d3b7  mov     edx, dword ptr [rsp+0A8h+Block]
0x18003d3be  test    edx, edx
0x18003d3c0  jz      short loc_18003D3CE
0x18003d3c2  dec     edx
0x18003d3c4  mov     rcx, rbx
0x18003d3c7  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18003d3cc  jmp     short loc_18003D3D8
0x18003d3ce  xor     edx, edx
0x18003d3d0  mov     rcx, rbx
0x18003d3d3  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18003d3d8  jmp     loc_18003D358
0x18003d3dd  mov     edi, dword ptr [rsp+0A8h+Block]
0x18003d3e4  jmp     loc_18003D53A
0x18003d3e9  movsxd  r15, dword ptr [r14+rsi*8+0Ch]
0x18003d3ee  add     r15, r12
0x18003d3f1  test    r13b, r13b
0x18003d3f4  jz      short loc_18003D426
0x18003d3f6  mov     r9, [r15+8]
0x18003d3fa  sub     r9, [r15]
0x18003d3fd  and     r9d, 0FFFFFFFCh; unsigned int
0x18003d401  mov     r8, [r15]; void *
0x18003d404  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d409  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18003d40e  mov     edi, eax
0x18003d410  test    eax, eax
0x18003d412  jz      loc_18003D2F4
0x18003d418  jle     loc_18003D53A
0x18003d41e  movzx   edi, ax
0x18003d421  jmp     loc_18003D2C7
0x18003d426  mov     [rsp+0A8h+Block], 0
0x18003d432  mov     dword ptr [rsp+0A8h+Size], 0
0x18003d43d  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18003d445  xor     r8d, r8d; void *
0x18003d448  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d44d  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18003d452  mov     edi, eax
0x18003d454  test    eax, eax
0x18003d456  jz      short loc_18003D46F
0x18003d458  jle     short loc_18003D463
0x18003d45a  movzx   edi, ax
0x18003d45d  or      edi, 80070000h
0x18003d463  xor     ecx, ecx; Block
0x18003d465  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d46a  jmp     loc_18003D53A
0x18003d46f  mov     edx, dword ptr [rsp+0A8h+Size]
0x18003d476  lea     rcx, [rsp+0A8h+Block]
0x18003d47e  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18003d483  test    al, al
0x18003d485  jnz     short loc_18003D49E
0x18003d487  mov     rcx, [rsp+0A8h+Block]; Block
0x18003d48f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d494  mov     edi, 8007000Eh
0x18003d499  jmp     loc_18003D53A
0x18003d49e  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18003d4a6  mov     rbx, [rsp+0A8h+Block]
0x18003d4ae  mov     r8, rbx; void *
0x18003d4b1  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18003d4b5  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d4ba  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18003d4bf  mov     edi, eax
0x18003d4c1  test    eax, eax
0x18003d4c3  jz      short loc_18003D4D5
0x18003d4c5  jle     short loc_18003D4D0
0x18003d4c7  movzx   edi, ax
0x18003d4ca  or      edi, 80070000h
0x18003d4d0  mov     rcx, rbx
0x18003d4d3  jmp     short loc_18003D465
0x18003d4d5  mov     edx, dword ptr [rsp+0A8h+Size]
0x18003d4dc  shr     rdx, 2
0x18003d4e0  mov     rcx, r15
0x18003d4e3  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18003d4e8  nop
0x18003d4e9  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x18003d4f1  mov     rdx, rbx; Src
0x18003d4f4  mov     rcx, [r15]; void *
0x18003d4f7  call    memcpy_0
0x18003d4fc  nop
0x18003d4fd  mov     rcx, rbx; Block
0x18003d500  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d505  jmp     loc_18003D2F4
0x18003d50a  jmp     loc_18003D487
0x18003d50f  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18003d514  add     r8, r12; unsigned int *
0x18003d517  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d51c  test    r13b, r13b
0x18003d51f  jz      short loc_18003D52E
0x18003d521  mov     r8d, [r8]; unsigned int
0x18003d524  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18003d529  jmp     loc_18003D2B8
0x18003d52e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18003d533  jmp     loc_18003D2B8
0x18003d538  xor     edi, edi
0x18003d53a  lea     rcx, [rsp+0A8h+hKey]; this
0x18003d53f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003d544  mov     eax, edi
0x18003d546  add     rsp, 70h
0x18003d54a  pop     r15
0x18003d54c  pop     r14
0x18003d54e  pop     r13
0x18003d550  pop     r12
0x18003d552  pop     rdi
0x18003d553  pop     rsi
0x18003d554  pop     rbx
0x18003d555  retn
```
