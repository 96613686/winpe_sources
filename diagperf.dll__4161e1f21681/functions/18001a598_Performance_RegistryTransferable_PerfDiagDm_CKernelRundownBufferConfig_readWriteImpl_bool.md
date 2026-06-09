# Performance::RegistryTransferable<PerfDiagDm::CKernelRundownBufferConfig>::readWriteImpl(bool)

- ea: `0x18001a598`
- end: `0x18001a97c`
- name: `?readWriteImpl@?$RegistryTransferable@VCKernelRundownBufferConfig@PerfDiagDm@@@Performance@@AEAAJ_N@Z`
- size: `996`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800335b8`
- `0x1800aeb80`
- `0x1800aef90`

## callees

- `0x18001890c`
- `0x180018aa4`
- `0x180019310`
- `0x18001933c`
- `0x180019370`
- `0x180019f7c`
- `0x18001a3e8`
- `0x18001a56c`
- `0x18001a598`
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

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a921`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a626`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a964`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a626`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a964`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Performance::RegistryTransferable<PerfDiagDm::CKernelRundownBufferConfig>::readWriteImpl(
        char *a1,
        char a2)
{
  __int64 v4; // r14
  unsigned __int16 *v5; // r9
  int v6; // eax
  unsigned int v7; // r9d
  unsigned int v8; // ebx
  __int64 i; // rax
  __int64 v11; // rsi
  const WCHAR *v12; // rdx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  signed int StringValue; // edi
  unsigned __int64 *v18; // r8
  signed int QWORDValue; // eax
  bool v20; // cc
  char *v21; // r8
  bool v22; // zf
  const unsigned __int16 **v23; // rbx
  unsigned __int16 *BufferSetLength; // rax
  char *v25; // r15
  int v26; // eax
  int BinaryValue; // eax
  void *v28; // rcx
  void *v29; // rbx
  int v30; // eax
  unsigned int *v31; // r8
  LSTATUS DWORDValue; // eax
  unsigned int lpData; // [rsp+20h] [rbp-88h]
  struct _SECURITY_ATTRIBUTES *v34; // [rsp+30h] [rbp-78h]
  unsigned int *v35; // [rsp+38h] [rbp-70h]
  HKEY v36; // [rsp+40h] [rbp-68h] BYREF
  __int64 v37; // [rsp+48h] [rbp-60h]
  ATL::CAtlException *v38; // [rsp+50h] [rbp-58h] BYREF
  HKEY hKey[10]; // [rsp+58h] [rbp-50h] BYREF
  void *Block; // [rsp+B0h] [rbp+8h] BYREF
  size_t Size; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v42; // [rsp+C0h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+20h] BYREF

  v36 = 0;
  lpSubKey = 0;
  v4 = (**(__int64 (__fastcall ***)(char *, HKEY *, LPCWSTR *))a1)(a1, &v36, &lpSubKey);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v36, lpSubKey, v5, lpData, a2 != 0 ? 131103 : 131097, v34, v35);
  v8 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v8 = (unsigned __int16)v6 | 0x80070000;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v8;
  }
  for ( i = 0; ; i = v37 + 1 )
  {
    v37 = i;
    v11 = 3 * i;
    v12 = *(const WCHAR **)(v4 + 24 * i);
    if ( !v12 )
      break;
    v13 = *(_DWORD *)(v4 + 24 * i + 8);
    if ( !v13 )
    {
      v31 = (unsigned int *)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
      {
        LODWORD(Block) = *v31;
        DWORDValue = RegSetValueExW(hKey[0], v12, 0, 4u, (const BYTE *)&Block, 4u);
      }
      else
      {
        DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)hKey, v12, v31);
      }
      StringValue = DWORDValue;
      v22 = DWORDValue == 0;
LABEL_55:
      if ( !v22 )
      {
LABEL_56:
        v20 = StringValue <= 0;
LABEL_57:
        if ( v20 )
          goto LABEL_60;
        StringValue = (unsigned __int16)StringValue;
LABEL_59:
        StringValue |= 0x80070000;
        goto LABEL_60;
      }
      continue;
    }
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( !v15 )
      {
        v23 = (const unsigned __int16 **)&a1[*(int *)(v4 + 24 * i + 12)];
        if ( a2 )
        {
          StringValue = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, v12, *v23, v7);
        }
        else
        {
          LODWORD(Block) = 0;
          StringValue = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, v12, 0, (unsigned int *)&Block);
          if ( !StringValue )
          {
            if ( (_DWORD)Block )
            {
              try
              {
                BufferSetLength = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(
                                                        v23,
                                                        (unsigned int)Block);
                StringValue = ATL::CRegKey::QueryStringValue(
                                (ATL::CRegKey *)hKey,
                                *(const unsigned __int16 **)(v4 + 8 * v11),
                                BufferSetLength,
                                (unsigned int *)&Block);
                if ( StringValue || !(_DWORD)Block )
                  ATL::CSimpleStringT<unsigned short,0>::SetLength(v23, 0);
                else
                  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v23);
              }
              catch ( ATL::CAtlException *v38 )
              {
                LODWORD(Block) = *(_DWORD *)v38;
                StringValue = (int)Block;
                goto LABEL_60;
              }
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::Empty(v23);
            }
          }
        }
LABEL_19:
        v20 = StringValue <= 0;
        if ( StringValue )
          goto LABEL_57;
        continue;
      }
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 != 1 )
        {
          StringValue = -2147418113;
          goto LABEL_60;
        }
        v18 = (unsigned __int64 *)&a1[*(int *)(v4 + 24 * i + 12)];
        if ( a2 )
          QWORDValue = ATL::CRegKey::SetQWORDValue((ATL::CRegKey *)hKey, v12, *v18);
        else
          QWORDValue = ATL::CRegKey::QueryQWORDValue((ATL::CRegKey *)hKey, v12, v18);
        StringValue = QWORDValue;
        goto LABEL_19;
      }
      v21 = &a1[*(int *)(v4 + 24 * i + 12)];
      if ( !a2 )
      {
        v42 = *(_DWORD *)(v4 + 24 * i + 16);
        StringValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v12, v21, &v42);
        if ( StringValue )
          goto LABEL_56;
        if ( v42 != *(_DWORD *)(v4 + 8 * v11 + 16) )
        {
          StringValue = -2147024883;
          goto LABEL_60;
        }
        continue;
      }
      StringValue = ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, v12, v21, *(_DWORD *)(v4 + 24 * i + 16));
      v22 = StringValue == 0;
      goto LABEL_55;
    }
    v25 = &a1[*(int *)(v4 + 24 * i + 12)];
    if ( a2 )
    {
      v26 = ATL::CRegKey::SetBinaryValue(
              (ATL::CRegKey *)hKey,
              v12,
              *(const void **)v25,
              (*((_DWORD *)v25 + 2) - *(_DWORD *)v25) & 0xFFFFFFFC);
      StringValue = v26;
      if ( v26 )
      {
        if ( v26 <= 0 )
          goto LABEL_60;
        StringValue = (unsigned __int16)v26;
        goto LABEL_59;
      }
    }
    else
    {
      Block = 0;
      LODWORD(Size) = 0;
      BinaryValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v12, 0, (unsigned int *)&Size);
      StringValue = BinaryValue;
      if ( BinaryValue )
      {
        if ( BinaryValue > 0 )
          StringValue = (unsigned __int16)BinaryValue | 0x80070000;
        v28 = 0;
        goto LABEL_44;
      }
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&Block, (unsigned int)Size) )
      {
LABEL_46:
        operator delete(Block);
        StringValue = -2147024882;
        goto LABEL_60;
      }
      v29 = Block;
      v30 = ATL::CRegKey::QueryBinaryValue(
              (ATL::CRegKey *)hKey,
              *(const unsigned __int16 **)(v4 + 8 * v11),
              Block,
              (unsigned int *)&Size);
      StringValue = v30;
      if ( v30 )
      {
        if ( v30 > 0 )
          StringValue = (unsigned __int16)v30 | 0x80070000;
        v28 = v29;
LABEL_44:
        operator delete(v28);
LABEL_60:
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        return (unsigned int)StringValue;
      }
      try
      {
        std::vector<unsigned long>::resize(v25, (unsigned __int64)(unsigned int)Size >> 2);
        memcpy_0(*(void **)v25, v29, (unsigned int)Size);
        operator delete(v29);
      }
      catch ( std::bad_alloc )
      {
        goto LABEL_46;
      }
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x18001a598  mov     r11, rsp
0x18001a59b  push    rbx
0x18001a59c  push    rsi
0x18001a59d  push    rdi
0x18001a59e  push    r12
0x18001a5a0  push    r13
0x18001a5a2  push    r14
0x18001a5a4  push    r15
0x18001a5a6  sub     rsp, 70h
0x18001a5aa  mov     r13b, dl
0x18001a5ad  mov     r12, rcx
0x18001a5b0  xor     r15d, r15d
0x18001a5b3  mov     [r11-68h], r15
0x18001a5b7  mov     [r11+20h], r15
0x18001a5bb  mov     rax, [rcx]
0x18001a5be  lea     r8, [r11+20h]
0x18001a5c2  lea     rdx, [r11-68h]
0x18001a5c6  mov     rax, [rax]
0x18001a5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ce  mov     r14, rax
0x18001a5d1  mov     [rsp+0A8h+hKey], r15
0x18001a5d6  mov     [rsp+0A8h+var_48], r15
0x18001a5db  mov     [rsp+0A8h+var_40], r15
0x18001a5e0  mov     cl, r13b
0x18001a5e3  neg     cl
0x18001a5e5  sbb     edx, edx
0x18001a5e7  and     edx, 6
0x18001a5ea  add     edx, 20019h
0x18001a5f0  mov     [rsp+0A8h+cbData], edx; unsigned int
0x18001a5f4  mov     r8, [rsp+0A8h+lpSubKey]; lpSubKey
0x18001a5fc  mov     rdx, [rsp+0A8h+var_68]; hKey
0x18001a601  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a606  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001a60b  mov     ebx, eax
0x18001a60d  test    eax, eax
0x18001a60f  jz      short loc_18001A633
0x18001a611  jle     short loc_18001A61C
0x18001a613  movzx   ebx, ax
0x18001a616  or      ebx, 80070000h
0x18001a61c  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001a621  test    rcx, rcx
0x18001a624  jz      short loc_18001A62C
0x18001a626  call    cs:__imp_RegCloseKey
0x18001a62c  mov     eax, ebx
0x18001a62e  jmp     loc_18001A96C
0x18001a633  mov     rax, r15
0x18001a636  mov     [rsp+0A8h+var_60], rax
0x18001a63b  lea     rsi, [rax+rax*2]
0x18001a63f  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001a643  test    rdx, rdx
0x18001a646  jz      loc_18001A958
0x18001a64c  mov     ecx, [r14+rsi*8+8]
0x18001a651  test    ecx, ecx
0x18001a653  jz      loc_18001A8E7
0x18001a659  sub     ecx, 1
0x18001a65c  jz      loc_18001A7BB
0x18001a662  sub     ecx, 1
0x18001a665  jz      loc_18001A714
0x18001a66b  sub     ecx, 1
0x18001a66e  jz      short loc_18001A6B4
0x18001a670  cmp     ecx, 1
0x18001a673  jz      short loc_18001A67F
0x18001a675  mov     edi, 8000FFFFh
0x18001a67a  jmp     loc_18001A94A
0x18001a67f  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18001a684  add     r8, r12; unsigned __int64 *
0x18001a687  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a68c  test    r13b, r13b
0x18001a68f  jz      short loc_18001A69B
0x18001a691  mov     r8, [r8]; unsigned __int64
0x18001a694  call    ?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z; ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)
0x18001a699  jmp     short loc_18001A6A0
0x18001a69b  call    ?QueryQWORDValue@CRegKey@ATL@@QEAAJPEBGAEA_K@Z; ATL::CRegKey::QueryQWORDValue(ushort const *,unsigned __int64 &)
0x18001a6a0  mov     edi, eax
0x18001a6a2  test    edi, edi
0x18001a6a4  jnz     loc_18001A93F
0x18001a6aa  mov     rax, [rsp+0A8h+var_60]
0x18001a6af  inc     rax
0x18001a6b2  jmp     short loc_18001A636
0x18001a6b4  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18001a6b9  add     r8, r12; void *
0x18001a6bc  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a6c1  test    r13b, r13b
0x18001a6c4  jz      short loc_18001A6D9
0x18001a6c6  mov     r9d, [r14+rsi*8+10h]; unsigned int
0x18001a6cb  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18001a6d0  mov     edi, eax
0x18001a6d2  test    eax, eax
0x18001a6d4  jmp     loc_18001A937
0x18001a6d9  mov     eax, [r14+rsi*8+10h]
0x18001a6de  mov     [rsp+0A8h+arg_10], eax
0x18001a6e5  lea     r9, [rsp+0A8h+arg_10]; unsigned int *
0x18001a6ed  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001a6f2  mov     edi, eax
0x18001a6f4  test    eax, eax
0x18001a6f6  jnz     loc_18001A93D
0x18001a6fc  mov     eax, [r14+rsi*8+10h]
0x18001a701  cmp     [rsp+0A8h+arg_10], eax
0x18001a708  jz      short loc_18001A6AA
0x18001a70a  mov     edi, 8007000Dh
0x18001a70f  jmp     loc_18001A94A
0x18001a714  movsxd  rbx, dword ptr [r14+rsi*8+0Ch]
0x18001a719  add     rbx, r12
0x18001a71c  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a721  test    r13b, r13b
0x18001a724  jz      short loc_18001A735
0x18001a726  mov     r8, [rbx]; unsigned __int16 *
0x18001a729  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001a72e  mov     edi, eax
0x18001a730  jmp     loc_18001A6A2
0x18001a735  mov     dword ptr [rsp+0A8h+Block], r15d
0x18001a73d  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18001a745  xor     r8d, r8d; unsigned __int16 *
0x18001a748  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001a74d  mov     edi, eax
0x18001a74f  test    eax, eax
0x18001a751  jnz     short loc_18001A730
0x18001a753  mov     edx, dword ptr [rsp+0A8h+Block]
0x18001a75a  mov     rcx, rbx
0x18001a75d  test    edx, edx
0x18001a75f  jnz     short loc_18001A768
0x18001a761  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001a766  jmp     short loc_18001A7AD
0x18001a768  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18001a76d  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18001a775  mov     r8, rax; unsigned __int16 *
0x18001a778  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001a77c  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a781  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001a786  mov     edi, eax
0x18001a788  test    eax, eax
0x18001a78a  jnz     short loc_18001A7A3
0x18001a78c  mov     edx, dword ptr [rsp+0A8h+Block]
0x18001a793  test    edx, edx
0x18001a795  jz      short loc_18001A7A3
0x18001a797  dec     edx
0x18001a799  mov     rcx, rbx
0x18001a79c  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18001a7a1  jmp     short loc_18001A7AD
0x18001a7a3  xor     edx, edx
0x18001a7a5  mov     rcx, rbx
0x18001a7a8  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001a7ad  jmp     short loc_18001A730
0x18001a7af  mov     edi, dword ptr [rsp+0A8h+Block]
0x18001a7b6  jmp     loc_18001A94A
0x18001a7bb  movsxd  r15, dword ptr [r14+rsi*8+0Ch]
0x18001a7c0  add     r15, r12
0x18001a7c3  test    r13b, r13b
0x18001a7c6  jz      short loc_18001A7FB
0x18001a7c8  mov     r9, [r15+8]
0x18001a7cc  sub     r9, [r15]
0x18001a7cf  and     r9d, 0FFFFFFFCh; unsigned int
0x18001a7d3  mov     r8, [r15]; void *
0x18001a7d6  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a7db  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18001a7e0  mov     edi, eax
0x18001a7e2  xor     r15d, r15d
0x18001a7e5  test    eax, eax
0x18001a7e7  jz      loc_18001A6AA
0x18001a7ed  jle     loc_18001A94A
0x18001a7f3  movzx   edi, ax
0x18001a7f6  jmp     loc_18001A944
0x18001a7fb  mov     [rsp+0A8h+Block], 0
0x18001a807  mov     dword ptr [rsp+0A8h+Size], 0
0x18001a812  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18001a81a  xor     r8d, r8d; void *
0x18001a81d  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a822  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001a827  mov     edi, eax
0x18001a829  test    eax, eax
0x18001a82b  jz      short loc_18001A844
0x18001a82d  jle     short loc_18001A838
0x18001a82f  movzx   edi, ax
0x18001a832  or      edi, 80070000h
0x18001a838  xor     ecx, ecx; Block
0x18001a83a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a83f  jmp     loc_18001A94A
0x18001a844  mov     edx, dword ptr [rsp+0A8h+Size]
0x18001a84b  lea     rcx, [rsp+0A8h+Block]
0x18001a853  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18001a858  test    al, al
0x18001a85a  jnz     short loc_18001A873
0x18001a85c  mov     rcx, [rsp+0A8h+Block]; Block
0x18001a864  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a869  mov     edi, 8007000Eh
0x18001a86e  jmp     loc_18001A94A
0x18001a873  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18001a87b  mov     rbx, [rsp+0A8h+Block]
0x18001a883  mov     r8, rbx; void *
0x18001a886  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001a88a  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a88f  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001a894  mov     edi, eax
0x18001a896  test    eax, eax
0x18001a898  jz      short loc_18001A8AA
0x18001a89a  jle     short loc_18001A8A5
0x18001a89c  movzx   edi, ax
0x18001a89f  or      edi, 80070000h
0x18001a8a5  mov     rcx, rbx
0x18001a8a8  jmp     short loc_18001A83A
0x18001a8aa  mov     edx, dword ptr [rsp+0A8h+Size]
0x18001a8b1  shr     rdx, 2
0x18001a8b5  mov     rcx, r15
0x18001a8b8  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18001a8bd  nop
0x18001a8be  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x18001a8c6  mov     rdx, rbx; Src
0x18001a8c9  mov     rcx, [r15]; void *
0x18001a8cc  call    memcpy_0
0x18001a8d1  nop
0x18001a8d2  mov     rcx, rbx; Block
0x18001a8d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a8da  xor     r15d, r15d
0x18001a8dd  jmp     loc_18001A6AA
0x18001a8e2  jmp     loc_18001A85C
0x18001a8e7  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18001a8ec  add     r8, r12; unsigned int *
0x18001a8ef  test    r13b, r13b
0x18001a8f2  jz      short loc_18001A929
0x18001a8f4  mov     eax, [r8]
0x18001a8f7  mov     dword ptr [rsp+0A8h+Block], eax
0x18001a8fe  mov     [rsp+0A8h+cbData], 4; cbData
0x18001a906  lea     rax, [rsp+0A8h+Block]
0x18001a90e  mov     [rsp+0A8h+lpData], rax; lpData
0x18001a913  mov     r9d, 4; dwType
0x18001a919  xor     r8d, r8d; Reserved
0x18001a91c  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001a921  call    cs:__imp_RegSetValueExW
0x18001a927  jmp     short loc_18001A933
0x18001a929  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a92e  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001a933  mov     edi, eax
0x18001a935  test    eax, eax
0x18001a937  jz      loc_18001A6AA
0x18001a93d  test    edi, edi
0x18001a93f  jle     short loc_18001A94A
0x18001a941  movzx   edi, di
0x18001a944  or      edi, 80070000h
0x18001a94a  lea     rcx, [rsp+0A8h+hKey]; this
0x18001a94f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a954  mov     eax, edi
0x18001a956  jmp     short loc_18001A96C
0x18001a958  cmp     [rsp+0A8h+hKey], r15
0x18001a95d  jz      short loc_18001A96A
0x18001a95f  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001a964  call    cs:__imp_RegCloseKey
0x18001a96a  xor     eax, eax
0x18001a96c  add     rsp, 70h
0x18001a970  pop     r15
0x18001a972  pop     r14
0x18001a974  pop     r13
0x18001a976  pop     r12
0x18001a978  pop     rdi
0x18001a979  pop     rsi
0x18001a97a  pop     rbx
0x18001a97b  retn
```
