# Performance::RegistryTransferable<PerfDiagShared::CTracingEnablementConfig>::readWriteImpl(bool)

- ea: `0x18001a984`
- end: `0x18001ad4b`
- name: `?readWriteImpl@?$RegistryTransferable@VCTracingEnablementConfig@PerfDiagShared@@@Performance@@AEAAJ_N@Z`
- size: `967`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `file_ops, registry_config`

## callers

- `0x18002b580`
- `0x180044980`
- `0x1800b4f00`
- `0x1800b4ff0`
- `0x1800ba5f0`

## callees

- `0x18001890c`
- `0x180018aa4`
- `0x180019310`
- `0x18001933c`
- `0x180019370`
- `0x180019f7c`
- `0x18001a3e8`
- `0x18001a56c`
- `0x18001a984`
- `0x18002d40c`
- `0x180039b68`
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

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ad33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aa23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ad33`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Performance::RegistryTransferable<PerfDiagShared::CTracingEnablementConfig>::readWriteImpl(
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
  LSTATUS QWORDValue; // eax
  bool v19; // cc
  char *v20; // r8
  bool v21; // zf
  const BYTE **v22; // rbx
  unsigned __int16 *BufferSetLength; // rax
  char *v24; // r15
  LSTATUS v25; // eax
  int BinaryValue; // eax
  void *v27; // rcx
  void *v28; // rbx
  int v29; // eax
  int *v30; // r8
  LSTATUS DWORDValue; // eax
  unsigned int v32; // [rsp+20h] [rbp-88h]
  HKEY v33; // [rsp+40h] [rbp-68h] BYREF
  __int64 v34; // [rsp+48h] [rbp-60h]
  ATL::CAtlException *v35; // [rsp+50h] [rbp-58h] BYREF
  HKEY hKey[10]; // [rsp+58h] [rbp-50h] BYREF
  void *Block; // [rsp+B0h] [rbp+8h] BYREF
  size_t Size; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+C0h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+20h] BYREF

  v33 = 0;
  lpSubKey = 0;
  v4 = (**(__int64 (__fastcall ***)(char *, HKEY *, LPCWSTR *))a1)(a1, &v33, &lpSubKey);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v33, lpSubKey, v5, v32, a2 != 0 ? 131103 : 131097);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v7;
  }
  for ( i = 0; ; i = v34 + 1 )
  {
    v34 = i;
    v10 = 3 * i;
    v11 = *(const unsigned __int16 **)(v4 + 24 * i);
    if ( !v11 )
      break;
    v12 = *(_DWORD *)(v4 + 24 * i + 8);
    if ( !v12 )
    {
      v30 = (int *)&a1[*(int *)(v4 + 24 * i + 12)];
      if ( a2 )
        DWORDValue = ATL::CRegKey::SetDWORDValue(hKey, v11, *v30);
      else
        DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)hKey, v11, (unsigned int *)v30);
      StringValue = DWORDValue;
      v21 = DWORDValue == 0;
LABEL_55:
      if ( !v21 )
      {
LABEL_56:
        v19 = StringValue <= 0;
LABEL_57:
        if ( v19 )
          goto LABEL_60;
        StringValue = (unsigned __int16)StringValue;
LABEL_59:
        StringValue |= 0x80070000;
        goto LABEL_60;
      }
      continue;
    }
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( !v14 )
      {
        v22 = (const BYTE **)&a1[*(int *)(v4 + 24 * i + 12)];
        if ( a2 )
        {
          StringValue = ATL::CRegKey::SetStringValue(hKey, v11, *v22);
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
                                                        v22,
                                                        (unsigned int)Block);
                StringValue = ATL::CRegKey::QueryStringValue(
                                (ATL::CRegKey *)hKey,
                                *(const unsigned __int16 **)(v4 + 8 * v10),
                                BufferSetLength,
                                (unsigned int *)&Block);
                if ( StringValue || !(_DWORD)Block )
                  ATL::CSimpleStringT<unsigned short,0>::SetLength(v22, 0);
                else
                  ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v22);
              }
              catch ( ATL::CAtlException *v35 )
              {
                LODWORD(Block) = *(_DWORD *)v35;
                StringValue = (int)Block;
                goto LABEL_60;
              }
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::Empty(v22);
            }
          }
        }
LABEL_19:
        v19 = StringValue <= 0;
        if ( StringValue )
          goto LABEL_57;
        continue;
      }
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 != 1 )
        {
          StringValue = -2147418113;
          goto LABEL_60;
        }
        v17 = (__int64 *)&a1[*(int *)(v4 + 24 * i + 12)];
        if ( a2 )
          QWORDValue = ATL::CRegKey::SetQWORDValue(hKey, v11, *v17);
        else
          QWORDValue = ATL::CRegKey::QueryQWORDValue((ATL::CRegKey *)hKey, v11, (unsigned __int64 *)v17);
        StringValue = QWORDValue;
        goto LABEL_19;
      }
      v20 = &a1[*(int *)(v4 + 24 * i + 12)];
      if ( !a2 )
      {
        v39 = *(_DWORD *)(v4 + 24 * i + 16);
        StringValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v11, v20, &v39);
        if ( StringValue )
          goto LABEL_56;
        if ( v39 != *(_DWORD *)(v4 + 8 * v10 + 16) )
        {
          StringValue = -2147024883;
          goto LABEL_60;
        }
        continue;
      }
      StringValue = ATL::CRegKey::SetBinaryValue(hKey, v11, (const BYTE *)v20, *(_DWORD *)(v4 + 24 * i + 16));
      v21 = StringValue == 0;
      goto LABEL_55;
    }
    v24 = &a1[*(int *)(v4 + 24 * i + 12)];
    if ( a2 )
    {
      v25 = ATL::CRegKey::SetBinaryValue(
              hKey,
              v11,
              *(const BYTE **)v24,
              (*((_DWORD *)v24 + 2) - *(_DWORD *)v24) & 0xFFFFFFFC);
      StringValue = v25;
      if ( v25 )
      {
        if ( v25 <= 0 )
          goto LABEL_60;
        StringValue = (unsigned __int16)v25;
        goto LABEL_59;
      }
    }
    else
    {
      Block = 0;
      LODWORD(Size) = 0;
      BinaryValue = ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)hKey, v11, 0, (unsigned int *)&Size);
      StringValue = BinaryValue;
      if ( BinaryValue )
      {
        if ( BinaryValue > 0 )
          StringValue = (unsigned __int16)BinaryValue | 0x80070000;
        v27 = 0;
        goto LABEL_44;
      }
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&Block, (unsigned int)Size) )
      {
LABEL_46:
        operator delete(Block);
        StringValue = -2147024882;
        goto LABEL_60;
      }
      v28 = Block;
      v29 = ATL::CRegKey::QueryBinaryValue(
              (ATL::CRegKey *)hKey,
              *(const unsigned __int16 **)(v4 + 8 * v10),
              Block,
              (unsigned int *)&Size);
      StringValue = v29;
      if ( v29 )
      {
        if ( v29 > 0 )
          StringValue = (unsigned __int16)v29 | 0x80070000;
        v27 = v28;
LABEL_44:
        operator delete(v27);
LABEL_60:
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        return (unsigned int)StringValue;
      }
      try
      {
        std::vector<unsigned long>::resize(v24, (unsigned __int64)(unsigned int)Size >> 2);
        memcpy_0(*(void **)v24, v28, (unsigned int)Size);
        operator delete(v28);
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
0x18001a984  mov     r11, rsp
0x18001a987  push    rbx
0x18001a988  push    rsi
0x18001a989  push    rdi
0x18001a98a  push    r12
0x18001a98c  push    r13
0x18001a98e  push    r14
0x18001a990  push    r15
0x18001a992  sub     rsp, 70h
0x18001a996  mov     r13b, dl
0x18001a999  mov     r12, rcx
0x18001a99c  mov     qword ptr [r11-68h], 0
0x18001a9a4  mov     qword ptr [r11+20h], 0
0x18001a9ac  mov     rax, [rcx]
0x18001a9af  lea     r8, [r11+20h]
0x18001a9b3  lea     rdx, [r11-68h]
0x18001a9b7  mov     rax, [rax]
0x18001a9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9bf  mov     r14, rax
0x18001a9c2  mov     [rsp+0A8h+hKey], 0
0x18001a9cb  mov     [rsp+0A8h+var_48], 0
0x18001a9d4  mov     [rsp+0A8h+var_40], 0
0x18001a9dd  mov     cl, r13b
0x18001a9e0  neg     cl
0x18001a9e2  sbb     edx, edx
0x18001a9e4  and     edx, 6
0x18001a9e7  add     edx, 20019h
0x18001a9ed  mov     [rsp+0A8h+var_80], edx; unsigned int
0x18001a9f1  mov     r8, [rsp+0A8h+lpSubKey]; lpSubKey
0x18001a9f9  mov     rdx, [rsp+0A8h+var_68]; hKey
0x18001a9fe  lea     rcx, [rsp+0A8h+hKey]; this
0x18001aa03  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001aa08  mov     ebx, eax
0x18001aa0a  test    eax, eax
0x18001aa0c  jz      short loc_18001AA30
0x18001aa0e  jle     short loc_18001AA19
0x18001aa10  movzx   ebx, ax
0x18001aa13  or      ebx, 80070000h
0x18001aa19  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001aa1e  test    rcx, rcx
0x18001aa21  jz      short loc_18001AA29
0x18001aa23  call    cs:__imp_RegCloseKey
0x18001aa29  mov     eax, ebx
0x18001aa2b  jmp     loc_18001AD3B
0x18001aa30  xor     eax, eax
0x18001aa32  mov     [rsp+0A8h+var_60], rax
0x18001aa37  lea     rsi, [rax+rax*2]
0x18001aa3b  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001aa3f  test    rdx, rdx
0x18001aa42  jz      loc_18001AD29
0x18001aa48  mov     ecx, [r14+rsi*8+8]
0x18001aa4d  test    ecx, ecx
0x18001aa4f  jz      loc_18001ACE3
0x18001aa55  sub     ecx, 1
0x18001aa58  jz      loc_18001ABBD
0x18001aa5e  sub     ecx, 1
0x18001aa61  jz      loc_18001AB10
0x18001aa67  sub     ecx, 1
0x18001aa6a  jz      short loc_18001AAB0
0x18001aa6c  cmp     ecx, 1
0x18001aa6f  jz      short loc_18001AA7B
0x18001aa71  mov     edi, 8000FFFFh
0x18001aa76  jmp     loc_18001AD1B
0x18001aa7b  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18001aa80  add     r8, r12; unsigned __int64 *
0x18001aa83  lea     rcx, [rsp+0A8h+hKey]; this
0x18001aa88  test    r13b, r13b
0x18001aa8b  jz      short loc_18001AA97
0x18001aa8d  mov     r8, [r8]; unsigned __int64
0x18001aa90  call    ?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z; ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)
0x18001aa95  jmp     short loc_18001AA9C
0x18001aa97  call    ?QueryQWORDValue@CRegKey@ATL@@QEAAJPEBGAEA_K@Z; ATL::CRegKey::QueryQWORDValue(ushort const *,unsigned __int64 &)
0x18001aa9c  mov     edi, eax
0x18001aa9e  test    edi, edi
0x18001aaa0  jnz     loc_18001AD10
0x18001aaa6  mov     rax, [rsp+0A8h+var_60]
0x18001aaab  inc     rax
0x18001aaae  jmp     short loc_18001AA32
0x18001aab0  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18001aab5  add     r8, r12; void *
0x18001aab8  lea     rcx, [rsp+0A8h+hKey]; this
0x18001aabd  test    r13b, r13b
0x18001aac0  jz      short loc_18001AAD5
0x18001aac2  mov     r9d, [r14+rsi*8+10h]; unsigned int
0x18001aac7  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18001aacc  mov     edi, eax
0x18001aace  test    eax, eax
0x18001aad0  jmp     loc_18001AD08
0x18001aad5  mov     eax, [r14+rsi*8+10h]
0x18001aada  mov     [rsp+0A8h+arg_10], eax
0x18001aae1  lea     r9, [rsp+0A8h+arg_10]; unsigned int *
0x18001aae9  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001aaee  mov     edi, eax
0x18001aaf0  test    eax, eax
0x18001aaf2  jnz     loc_18001AD0E
0x18001aaf8  mov     eax, [r14+rsi*8+10h]
0x18001aafd  cmp     [rsp+0A8h+arg_10], eax
0x18001ab04  jz      short loc_18001AAA6
0x18001ab06  mov     edi, 8007000Dh
0x18001ab0b  jmp     loc_18001AD1B
0x18001ab10  movsxd  rbx, dword ptr [r14+rsi*8+0Ch]
0x18001ab15  add     rbx, r12
0x18001ab18  lea     rcx, [rsp+0A8h+hKey]; this
0x18001ab1d  test    r13b, r13b
0x18001ab20  jz      short loc_18001AB31
0x18001ab22  mov     r8, [rbx]; unsigned __int16 *
0x18001ab25  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001ab2a  mov     edi, eax
0x18001ab2c  jmp     loc_18001AA9E
0x18001ab31  mov     dword ptr [rsp+0A8h+Block], 0
0x18001ab3c  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18001ab44  xor     r8d, r8d; unsigned __int16 *
0x18001ab47  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001ab4c  mov     edi, eax
0x18001ab4e  test    eax, eax
0x18001ab50  jnz     short loc_18001AB2C
0x18001ab52  mov     edx, dword ptr [rsp+0A8h+Block]
0x18001ab59  mov     rcx, rbx
0x18001ab5c  test    edx, edx
0x18001ab5e  jnz     short loc_18001AB67
0x18001ab60  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001ab65  jmp     short loc_18001ABAC
0x18001ab67  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x18001ab6c  lea     r9, [rsp+0A8h+Block]; unsigned int *
0x18001ab74  mov     r8, rax; unsigned __int16 *
0x18001ab77  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001ab7b  lea     rcx, [rsp+0A8h+hKey]; this
0x18001ab80  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001ab85  mov     edi, eax
0x18001ab87  test    eax, eax
0x18001ab89  jnz     short loc_18001ABA2
0x18001ab8b  mov     edx, dword ptr [rsp+0A8h+Block]
0x18001ab92  test    edx, edx
0x18001ab94  jz      short loc_18001ABA2
0x18001ab96  dec     edx
0x18001ab98  mov     rcx, rbx
0x18001ab9b  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18001aba0  jmp     short loc_18001ABAC
0x18001aba2  xor     edx, edx
0x18001aba4  mov     rcx, rbx
0x18001aba7  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001abac  jmp     loc_18001AB2C
0x18001abb1  mov     edi, dword ptr [rsp+0A8h+Block]
0x18001abb8  jmp     loc_18001AD1B
0x18001abbd  movsxd  r15, dword ptr [r14+rsi*8+0Ch]
0x18001abc2  add     r15, r12
0x18001abc5  test    r13b, r13b
0x18001abc8  jz      short loc_18001ABFA
0x18001abca  mov     r9, [r15+8]
0x18001abce  sub     r9, [r15]
0x18001abd1  and     r9d, 0FFFFFFFCh; unsigned int
0x18001abd5  mov     r8, [r15]; void *
0x18001abd8  lea     rcx, [rsp+0A8h+hKey]; this
0x18001abdd  call    ?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z; ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)
0x18001abe2  mov     edi, eax
0x18001abe4  test    eax, eax
0x18001abe6  jz      loc_18001AAA6
0x18001abec  jle     loc_18001AD1B
0x18001abf2  movzx   edi, ax
0x18001abf5  jmp     loc_18001AD15
0x18001abfa  mov     [rsp+0A8h+Block], 0
0x18001ac06  mov     dword ptr [rsp+0A8h+Size], 0
0x18001ac11  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18001ac19  xor     r8d, r8d; void *
0x18001ac1c  lea     rcx, [rsp+0A8h+hKey]; this
0x18001ac21  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001ac26  mov     edi, eax
0x18001ac28  test    eax, eax
0x18001ac2a  jz      short loc_18001AC43
0x18001ac2c  jle     short loc_18001AC37
0x18001ac2e  movzx   edi, ax
0x18001ac31  or      edi, 80070000h
0x18001ac37  xor     ecx, ecx; Block
0x18001ac39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac3e  jmp     loc_18001AD1B
0x18001ac43  mov     edx, dword ptr [rsp+0A8h+Size]
0x18001ac4a  lea     rcx, [rsp+0A8h+Block]
0x18001ac52  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18001ac57  test    al, al
0x18001ac59  jnz     short loc_18001AC72
0x18001ac5b  mov     rcx, [rsp+0A8h+Block]; Block
0x18001ac63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ac68  mov     edi, 8007000Eh
0x18001ac6d  jmp     loc_18001AD1B
0x18001ac72  lea     r9, [rsp+0A8h+Size]; unsigned int *
0x18001ac7a  mov     rbx, [rsp+0A8h+Block]
0x18001ac82  mov     r8, rbx; void *
0x18001ac85  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001ac89  lea     rcx, [rsp+0A8h+hKey]; this
0x18001ac8e  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001ac93  mov     edi, eax
0x18001ac95  test    eax, eax
0x18001ac97  jz      short loc_18001ACA9
0x18001ac99  jle     short loc_18001ACA4
0x18001ac9b  movzx   edi, ax
0x18001ac9e  or      edi, 80070000h
0x18001aca4  mov     rcx, rbx
0x18001aca7  jmp     short loc_18001AC39
0x18001aca9  mov     edx, dword ptr [rsp+0A8h+Size]
0x18001acb0  shr     rdx, 2
0x18001acb4  mov     rcx, r15
0x18001acb7  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18001acbc  nop
0x18001acbd  mov     r8d, dword ptr [rsp+0A8h+Size]; Size
0x18001acc5  mov     rdx, rbx; Src
0x18001acc8  mov     rcx, [r15]; void *
0x18001accb  call    memcpy_0
0x18001acd0  nop
0x18001acd1  mov     rcx, rbx; Block
0x18001acd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001acd9  jmp     loc_18001AAA6
0x18001acde  jmp     loc_18001AC5B
0x18001ace3  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x18001ace8  add     r8, r12; unsigned int *
0x18001aceb  lea     rcx, [rsp+0A8h+hKey]; this
0x18001acf0  test    r13b, r13b
0x18001acf3  jz      short loc_18001ACFF
0x18001acf5  mov     r8d, [r8]; unsigned int
0x18001acf8  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001acfd  jmp     short loc_18001AD04
0x18001acff  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001ad04  mov     edi, eax
0x18001ad06  test    eax, eax
0x18001ad08  jz      loc_18001AAA6
0x18001ad0e  test    edi, edi
0x18001ad10  jle     short loc_18001AD1B
0x18001ad12  movzx   edi, di
0x18001ad15  or      edi, 80070000h
0x18001ad1b  lea     rcx, [rsp+0A8h+hKey]; this
0x18001ad20  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001ad25  mov     eax, edi
0x18001ad27  jmp     short loc_18001AD3B
0x18001ad29  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001ad2e  test    rcx, rcx
0x18001ad31  jz      short loc_18001AD39
0x18001ad33  call    cs:__imp_RegCloseKey
0x18001ad39  xor     eax, eax
0x18001ad3b  add     rsp, 70h
0x18001ad3f  pop     r15
0x18001ad41  pop     r14
0x18001ad43  pop     r13
0x18001ad45  pop     r12
0x18001ad47  pop     rdi
0x18001ad48  pop     rsi
0x18001ad49  pop     rbx
0x18001ad4a  retn
```
