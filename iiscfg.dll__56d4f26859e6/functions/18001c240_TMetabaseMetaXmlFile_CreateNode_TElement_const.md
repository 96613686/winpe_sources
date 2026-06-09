# TMetabaseMetaXmlFile::CreateNode(TElement const &)

- ea: `0x18001c240`
- end: `0x18001c696`
- name: `?CreateNode@TMetabaseMetaXmlFile@@UEAAJAEBUTElement@@@Z`
- size: `1110`
- prototype: `int(TMetabaseMetaXmlFile *__hidden this, const struct TElement *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180019554`
- `0x1800199c8`
- `0x18001aac4`
- `0x18001b188`
- `0x18001b354`
- `0x18001b628`
- `0x18001c240`
- `0x18001c69c`
- `0x18001c814`
- `0x18001d488`
- `0x18001d504`
- `0x18001d604`
- `0x180030010`

## string_xrefs

- `0x18001c5b0`: `Error - Found Level 1 element when expecting IIsConfigObjectTable\n`

## pseudocode

```c
__int64 __fastcall TMetabaseMetaXmlFile::CreateNode(TMetabaseMetaXmlFile *this, const struct TElement *a2)
{
  TMetabaseMetaXmlFile *v4; // r14
  unsigned int v5; // ebp
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  TMetabaseMetaXmlFile *v9; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdx
  __int64 TableMetaRow; // rbx
  TMetabaseMetaXmlFile *v19; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v20; // rax
  bool IsEqual; // al
  BOOL v22; // r15d
  __int64 v23; // rbx
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rdi
  int v28; // eax
  TMetabaseMetaXmlFile *v29; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v30; // rax
  unsigned int v31; // ebx
  TMetabaseMetaXmlFile *v32; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v33; // rax
  const wchar_t *v34; // rdx
  TMetabaseMetaXmlFile *v35; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *v36; // rax
  TMetabaseMetaXmlFile *v37; // rcx
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // rax
  unsigned int v39; // [rsp+68h] [rbp+10h] BYREF
  __int64 v40; // [rsp+70h] [rbp+18h] BYREF

  if ( *((_DWORD *)a2 + 6) == 1 && (*((_BYTE *)a2 + 16) & 2) == 0 )
  {
    v4 = (TMetabaseMetaXmlFile *)((char *)this - 288);
    v5 = 0;
    v6 = *((_DWORD *)this + 576);
    if ( !v6 )
    {
      if ( *(_DWORD *)a2 == 1
        && TMetabaseMetaXmlFile::TSizedString::IsEqual(
             (TMetabaseMetaXmlFile *)((char *)this + 88),
             *((const unsigned __int16 **)a2 + 1),
             *((_DWORD *)a2 + 1)) )
      {
        Attribute = TMetabaseMetaXmlFile::GetAttribute(v37, a2, (TMetabaseMetaXmlFile *)((char *)this + 248));
        if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(
               (const struct TMetabaseMetaXmlFile::TAttr *)((char *)Attribute + 16),
               (TMetabaseMetaXmlFile *)((char *)this + 280)) )
        {
          *((_DWORD *)this + 576) = 1;
        }
      }
      return v5;
    }
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          switch ( *(_DWORD *)a2 )
          {
            case 1:
              return 2149647639LL;
            case 2:
              if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(
                     (TMetabaseMetaXmlFile *)((char *)this + 56),
                     *((const unsigned __int16 **)a2 + 1),
                     *((_DWORD *)a2 + 1)) )
              {
                v10 = TMetabaseMetaXmlFile::GetAttribute(v9, a2, (TMetabaseMetaXmlFile *)((char *)this + 248));
                v11 = TMetabaseMetaXmlFile::AddStringToHeap(
                        v4,
                        (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v10 + 16));
                v12 = v11;
                *((_DWORD *)this + 564) = v11;
                v13 = *(_QWORD *)v4;
                v39 = 0;
                v40 = 0;
                v14 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(v13 + 144))(v4, v12);
                v15 = *((_QWORD *)this + 293);
                v40 = v14;
                if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *, unsigned int *))(*(_QWORD *)v15 + 24LL))(
                       v15,
                       0,
                       &v40,
                       &v39) >= 0 )
                {
                  v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)v4 + 144LL))(
                                                    v4,
                                                    *((unsigned int *)this + 564));
                  if ( !v16 )
                    return 2147942413LL;
                  *(_BYTE *)(v39 + *((_QWORD *)this + 65)) = 1;
                  TableMetaRow = FixedTableHeap::FindTableMetaRow(*((FixedTableHeap **)this + 287), v16);
                  v20 = TMetabaseMetaXmlFile::GetAttribute(v19, a2, (TMetabaseMetaXmlFile *)((char *)this + 72));
                  TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(
                    v4,
                    (const struct TableMeta *)(*((_QWORD *)this + 287)
                                             + *(unsigned int *)(*((_QWORD *)this + 287) + 88LL)
                                             + 108 * TableMetaRow),
                    0,
                    (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v20 + 16));
                }
                else
                {
                  TMetabaseMetaXmlFile::AddTableMetaToHeap(v4, a2);
                }
              }
              break;
            case 3:
              if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(
                     (TMetabaseMetaXmlFile *)((char *)this + 360),
                     *((const unsigned __int16 **)a2 + 1),
                     *((_DWORD *)a2 + 1)) )
              {
                TMetabaseMetaXmlFile::AddColumnMetaViaReferenceToHeap(v4, a2);
              }
              break;
            case 4:
              (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 286))(
                *((_QWORD *)this + 286),
                L"Tag found under inherited property.  Tags are being ignored\r\n");
              break;
          }
        }
        return v5;
      }
      if ( *(_DWORD *)a2 != 1 )
      {
        if ( *(_DWORD *)a2 != 2 )
        {
          if ( *(_DWORD *)a2 == 3 )
          {
            if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(
                   (TMetabaseMetaXmlFile *)((char *)this + 360),
                   *((const unsigned __int16 **)a2 + 1),
                   *((_DWORD *)a2 + 1)) )
            {
              v30 = TMetabaseMetaXmlFile::GetAttribute(v29, a2, (TMetabaseMetaXmlFile *)((char *)this + 248));
              v31 = TMetabaseMetaXmlFile::AddStringToHeap(
                      v4,
                      (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v30 + 16));
              if ( TMetabaseMetaXmlFile::ShouldAddColumnMetaToHeap(v4, a2, v31) )
                TMetabaseMetaXmlFile::AddColumnMetaToHeap(v4, a2, v31);
              else
                *((_DWORD *)v4 + 634) = 0;
            }
          }
          else if ( *(_DWORD *)a2 == 4 )
          {
            IsEqual = TMetabaseMetaXmlFile::TSizedString::IsEqual(
                        (TMetabaseMetaXmlFile *)((char *)this + 184),
                        *((const unsigned __int16 **)a2 + 1),
                        *((_DWORD *)a2 + 1));
            v22 = IsEqual;
            if ( IsEqual
              || TMetabaseMetaXmlFile::TSizedString::IsEqual(
                   (TMetabaseMetaXmlFile *)((char *)this + 152),
                   *((const unsigned __int16 **)a2 + 1),
                   *((_DWORD *)a2 + 1)) )
            {
              if ( *((_DWORD *)this + 562) )
              {
                v23 = *(_QWORD *)v4;
                v24 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *))(*(_QWORD *)v4 + 264LL))(v4);
                v25 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v23 + 176))(
                        v4,
                        (unsigned int)(v24 - 1));
                v26 = *(_QWORD *)v4;
                v27 = v25;
                v28 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)v4 + 152LL))(
                        v4,
                        *(unsigned int *)(v25 + 24));
                *(_DWORD *)(v27 + 24) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v26 + 16))(
                                          v4,
                                          v28 | ((!v22 + 1) << 6));
                TMetabaseMetaXmlFile::AddTagMetaToHeap(v4, a2);
              }
            }
          }
          return v5;
        }
        if ( !TMetabaseMetaXmlFile::TSizedString::IsEqual(
                (TMetabaseMetaXmlFile *)((char *)this + 56),
                *((const unsigned __int16 **)a2 + 1),
                *((_DWORD *)a2 + 1)) )
          return v5;
        v33 = TMetabaseMetaXmlFile::GetAttribute(v32, a2, (TMetabaseMetaXmlFile *)((char *)this + 248));
        if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(
               (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v33 + 16),
               (TMetabaseMetaXmlFile *)((char *)this + 216)) )
        {
          return v5;
        }
        *((_DWORD *)this + 576) = 3;
        return (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, const struct TElement *))(*(_QWORD *)this + 8LL))(
                 this,
                 a2);
      }
      v34 = L"Error - Found Level 1 element when expecting GlobalProperties\r\n";
    }
    else
    {
      if ( *(_DWORD *)a2 != 1 )
      {
        if ( *(_DWORD *)a2 != 2 )
          return v5;
        if ( !TMetabaseMetaXmlFile::TSizedString::IsEqual(
                (TMetabaseMetaXmlFile *)((char *)this + 56),
                *((const unsigned __int16 **)a2 + 1),
                *((_DWORD *)a2 + 1)) )
          return v5;
        v36 = TMetabaseMetaXmlFile::GetAttribute(v35, a2, (TMetabaseMetaXmlFile *)((char *)this + 248));
        if ( TMetabaseMetaXmlFile::TSizedString::IsEqual(
               (const struct TMetabaseMetaXmlFile::TAttr *)((char *)v36 + 16),
               (TMetabaseMetaXmlFile *)((char *)this + 296)) )
        {
          return v5;
        }
        *((_DWORD *)this + 576) = 2;
        return (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, const struct TElement *))(*(_QWORD *)this + 8LL))(
                 this,
                 a2);
      }
      v34 = L"Error - Found Level 1 element when expecting IIsConfigObjectTable\r\n";
    }
    (***((void (__fastcall ****)(_QWORD, const wchar_t *))this + 286))(*((_QWORD *)this + 286), v34);
    return 2149647651LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18001c240  mov     [rsp+arg_0], rbx
0x18001c245  push    rbp
0x18001c246  push    rsi
0x18001c247  push    rdi
0x18001c248  push    r14
0x18001c24a  push    r15
0x18001c24c  sub     rsp, 30h
0x18001c250  cmp     dword ptr [rdx+18h], 1
0x18001c254  mov     rsi, rdx
0x18001c257  mov     rdi, rcx
0x18001c25a  jnz     loc_18001C683
0x18001c260  test    byte ptr [rdx+10h], 2
0x18001c264  jnz     loc_18001C683
0x18001c26a  lea     r14, [rcx-120h]
0x18001c271  xor     ebp, ebp
0x18001c273  mov     ecx, [r14+0A20h]
0x18001c27a  test    ecx, ecx
0x18001c27c  jz      loc_18001C638
0x18001c282  sub     ecx, 1
0x18001c285  jz      loc_18001C5AB
0x18001c28b  sub     ecx, 1
0x18001c28e  jz      loc_18001C417
0x18001c294  cmp     ecx, 1
0x18001c297  jnz     loc_18001C67F
0x18001c29d  mov     ecx, [rdx]
0x18001c29f  sub     ecx, 1
0x18001c2a2  jz      loc_18001C40D
0x18001c2a8  sub     ecx, 1
0x18001c2ab  jz      short loc_18001C305
0x18001c2ad  sub     ecx, 1
0x18001c2b0  jz      short loc_18001C2D9
0x18001c2b2  cmp     ecx, 1
0x18001c2b5  jnz     loc_18001C67F
0x18001c2bb  mov     rcx, [rdi+8F0h]
0x18001c2c2  lea     rdx, aTagFoundUnderI; "Tag found under inherited property.  Ta"...
0x18001c2c9  mov     rax, [rcx]
0x18001c2cc  mov     rax, [rax]
0x18001c2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2d4  jmp     loc_18001C67F
0x18001c2d9  mov     r8d, [rdx+4]; unsigned int
0x18001c2dd  lea     rcx, [rdi+168h]; this
0x18001c2e4  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c2e8  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c2ed  test    al, al
0x18001c2ef  jz      loc_18001C67F
0x18001c2f5  mov     rdx, rsi; struct TElement *
0x18001c2f8  mov     rcx, r14; this
0x18001c2fb  call    ?AddColumnMetaViaReferenceToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@@Z; TMetabaseMetaXmlFile::AddColumnMetaViaReferenceToHeap(TElement const &)
0x18001c300  jmp     loc_18001C67F
0x18001c305  mov     r8d, [rdx+4]; unsigned int
0x18001c309  lea     rcx, [rdi+38h]; this
0x18001c30d  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c311  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c316  test    al, al
0x18001c318  jz      loc_18001C67F
0x18001c31e  lea     r8, [rdi+0F8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c325  mov     rdx, rsi; struct TElement *
0x18001c328  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c32d  mov     rcx, r14; this
0x18001c330  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c334  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001c339  mov     edx, eax
0x18001c33b  mov     [rdi+8D0h], eax
0x18001c341  mov     rax, [r14]
0x18001c344  mov     rcx, r14
0x18001c347  mov     [rsp+58h+arg_8], ebp
0x18001c34b  mov     [rsp+58h+arg_10], rbp
0x18001c350  mov     rax, [rax+90h]
0x18001c357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c35c  mov     rcx, [rdi+928h]
0x18001c363  lea     r9, [rsp+58h+arg_8]
0x18001c368  mov     [rsp+58h+arg_10], rax
0x18001c36d  lea     r8, [rsp+58h+arg_10]
0x18001c372  xor     edx, edx
0x18001c374  mov     rax, [rcx]
0x18001c377  mov     rax, [rax+18h]
0x18001c37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c380  mov     rcx, r14; this
0x18001c383  test    eax, eax
0x18001c385  jns     short loc_18001C394
0x18001c387  mov     rdx, rsi; struct TElement *
0x18001c38a  call    ?AddTableMetaToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@@Z; TMetabaseMetaXmlFile::AddTableMetaToHeap(TElement const &)
0x18001c38f  jmp     loc_18001C67F
0x18001c394  mov     rax, [r14]
0x18001c397  mov     edx, [rdi+8D0h]
0x18001c39d  mov     rax, [rax+90h]
0x18001c3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3a9  mov     rdx, rax; unsigned __int16 *
0x18001c3ac  test    rax, rax
0x18001c3af  jnz     short loc_18001C3BB
0x18001c3b1  mov     eax, 8007000Dh
0x18001c3b6  jmp     loc_18001C685
0x18001c3bb  mov     ecx, [rsp+58h+arg_8]
0x18001c3bf  mov     rax, [rdi+208h]
0x18001c3c6  mov     byte ptr [rcx+rax], 1
0x18001c3ca  mov     rcx, [rdi+8F8h]; this
0x18001c3d1  call    ?FindTableMetaRow@FixedTableHeap@@QEBAKPEBG@Z; FixedTableHeap::FindTableMetaRow(ushort const *)
0x18001c3d6  lea     r8, [rdi+48h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c3da  mov     ebx, eax
0x18001c3dc  mov     rdx, rsi; struct TElement *
0x18001c3df  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c3e4  mov     r8, [rdi+8F8h]
0x18001c3eb  mov     rcx, r14; this
0x18001c3ee  imul    rdx, rbx, 6Ch ; 'l'
0x18001c3f2  lea     r9, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c3f6  mov     eax, [r8+58h]
0x18001c3fa  add     rax, r8
0x18001c3fd  xor     r8d, r8d; bool
0x18001c400  add     rdx, rax; struct TableMeta *
0x18001c403  call    ?AddShippedTableMetaToHeap@TMetabaseMetaXmlFile@@AEAAXPEBUTableMeta@@_NPEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(TableMeta const *,bool,TMetabaseMetaXmlFile::TSizedString const *)
0x18001c408  jmp     loc_18001C67F
0x18001c40d  mov     eax, 80210517h
0x18001c412  jmp     loc_18001C685
0x18001c417  mov     ecx, [rdx]
0x18001c419  sub     ecx, 1
0x18001c41c  jz      loc_18001C5A2
0x18001c422  sub     ecx, 1
0x18001c425  jz      loc_18001C553
0x18001c42b  sub     ecx, 1
0x18001c42e  jz      loc_18001C4E9
0x18001c434  cmp     ecx, 1
0x18001c437  jnz     loc_18001C67F
0x18001c43d  mov     r8d, [rdx+4]; unsigned int
0x18001c441  lea     rcx, [rdi+0B8h]; this
0x18001c448  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c44c  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c451  movzx   r15d, al
0x18001c455  test    al, al
0x18001c457  jnz     short loc_18001C475
0x18001c459  mov     r8d, [rsi+4]; unsigned int
0x18001c45d  lea     rcx, [rdi+98h]; this
0x18001c464  mov     rdx, [rsi+8]; unsigned __int16 *
0x18001c468  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c46d  test    al, al
0x18001c46f  jz      loc_18001C67F
0x18001c475  cmp     [rdi+8C8h], ebp
0x18001c47b  jz      loc_18001C67F
0x18001c481  mov     rbx, [r14]
0x18001c484  mov     rcx, r14
0x18001c487  mov     rax, [rbx+108h]
0x18001c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c493  mov     rcx, r14
0x18001c496  lea     edx, [rax-1]
0x18001c499  mov     rax, [rbx+0B0h]
0x18001c4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4a5  mov     rbx, [r14]
0x18001c4a8  mov     rdi, rax
0x18001c4ab  mov     rcx, r14
0x18001c4ae  mov     edx, [rax+18h]
0x18001c4b1  mov     rax, [rbx+98h]
0x18001c4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4bd  mov     edx, r15d
0x18001c4c0  mov     rcx, r14
0x18001c4c3  xor     edx, 1
0x18001c4c6  inc     edx
0x18001c4c8  shl     edx, 6
0x18001c4cb  or      edx, eax
0x18001c4cd  mov     rax, [rbx+10h]
0x18001c4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4d6  mov     rdx, rsi; struct TElement *
0x18001c4d9  mov     [rdi+18h], eax
0x18001c4dc  mov     rcx, r14; this
0x18001c4df  call    ?AddTagMetaToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@@Z; TMetabaseMetaXmlFile::AddTagMetaToHeap(TElement const &)
0x18001c4e4  jmp     loc_18001C67F
0x18001c4e9  mov     r8d, [rdx+4]; unsigned int
0x18001c4ed  lea     rcx, [rdi+168h]; this
0x18001c4f4  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c4f8  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c4fd  test    al, al
0x18001c4ff  jz      loc_18001C67F
0x18001c505  lea     r8, [rdi+0F8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c50c  mov     rdx, rsi; struct TElement *
0x18001c50f  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c514  mov     rcx, r14; this
0x18001c517  lea     rdx, [rax+10h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c51b  call    ?AddStringToHeap@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::AddStringToHeap(TMetabaseMetaXmlFile::TSizedString const &)
0x18001c520  mov     r8d, eax; unsigned int
0x18001c523  mov     rdx, rsi; struct TElement *
0x18001c526  mov     rcx, r14; this
0x18001c529  mov     ebx, eax
0x18001c52b  call    ?ShouldAddColumnMetaToHeap@TMetabaseMetaXmlFile@@AEAA_NAEBUTElement@@K@Z; TMetabaseMetaXmlFile::ShouldAddColumnMetaToHeap(TElement const &,ulong)
0x18001c530  test    al, al
0x18001c532  jz      short loc_18001C547
0x18001c534  mov     r8d, ebx; unsigned int
0x18001c537  mov     rdx, rsi; struct TElement *
0x18001c53a  mov     rcx, r14; this
0x18001c53d  call    ?AddColumnMetaToHeap@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@K@Z; TMetabaseMetaXmlFile::AddColumnMetaToHeap(TElement const &,ulong)
0x18001c542  jmp     loc_18001C67F
0x18001c547  mov     [r14+9E8h], ebp
0x18001c54e  jmp     loc_18001C67F
0x18001c553  mov     r8d, [rdx+4]; unsigned int
0x18001c557  lea     rcx, [rdi+38h]; this
0x18001c55b  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c55f  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c564  test    al, al
0x18001c566  jz      loc_18001C67F
0x18001c56c  lea     r8, [rdi+0F8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c573  mov     rdx, rsi; struct TElement *
0x18001c576  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c57b  lea     rdx, [rdi+0D8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c582  lea     rcx, [rax+10h]; this
0x18001c586  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NAEBU12@@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(TMetabaseMetaXmlFile::TSizedString const &)
0x18001c58b  test    al, al
0x18001c58d  jnz     loc_18001C67F
0x18001c593  mov     dword ptr [rdi+900h], 3
0x18001c59d  jmp     loc_18001C622
0x18001c5a2  lea     rdx, aErrorFoundLeve_0; "Error - Found Level 1 element when expe"...
0x18001c5a9  jmp     short loc_18001C5B7
0x18001c5ab  cmp     dword ptr [rdx], 1
0x18001c5ae  jnz     short loc_18001C5D3
0x18001c5b0  lea     rdx, aErrorFoundLeve; "Error - Found Level 1 element when expe"...
0x18001c5b7  mov     rcx, [rdi+8F0h]
0x18001c5be  mov     rax, [rcx]
0x18001c5c1  mov     rax, [rax]
0x18001c5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5c9  mov     eax, 80210523h
0x18001c5ce  jmp     loc_18001C685
0x18001c5d3  cmp     dword ptr [rdx], 2
0x18001c5d6  jnz     loc_18001C67F
0x18001c5dc  mov     r8d, [rdx+4]; unsigned int
0x18001c5e0  lea     rcx, [rdi+38h]; this
0x18001c5e4  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c5e8  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c5ed  test    al, al
0x18001c5ef  jz      loc_18001C67F
0x18001c5f5  lea     r8, [rdi+0F8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c5fc  mov     rdx, rsi; struct TElement *
0x18001c5ff  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c604  lea     rdx, [rdi+128h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c60b  lea     rcx, [rax+10h]; this
0x18001c60f  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NAEBU12@@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(TMetabaseMetaXmlFile::TSizedString const &)
0x18001c614  test    al, al
0x18001c616  jnz     short loc_18001C67F
0x18001c618  mov     dword ptr [rdi+900h], 2
0x18001c622  mov     rax, [rdi]
0x18001c625  mov     rdx, rsi
0x18001c628  mov     rcx, rdi
0x18001c62b  mov     rax, [rax+8]
0x18001c62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c634  mov     ebp, eax
0x18001c636  jmp     short loc_18001C67F
0x18001c638  cmp     dword ptr [rdx], 1
0x18001c63b  jnz     short loc_18001C67F
0x18001c63d  mov     r8d, [rdx+4]; unsigned int
0x18001c641  lea     rcx, [rdi+58h]; this
0x18001c645  mov     rdx, [rdx+8]; unsigned __int16 *
0x18001c649  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NPEBGK@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(ushort const *,ulong)
0x18001c64e  test    al, al
0x18001c650  jz      short loc_18001C67F
0x18001c652  lea     r8, [rdi+0F8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c659  mov     rdx, rsi; struct TElement *
0x18001c65c  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001c661  lea     rdx, [rdi+118h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001c668  lea     rcx, [rax+10h]; this
0x18001c66c  call    ?IsEqual@TSizedString@TMetabaseMetaXmlFile@@QEBA_NAEBU12@@Z; TMetabaseMetaXmlFile::TSizedString::IsEqual(TMetabaseMetaXmlFile::TSizedString const &)
0x18001c671  test    al, al
0x18001c673  jz      short loc_18001C67F
0x18001c675  mov     dword ptr [rdi+900h], 1
0x18001c67f  mov     eax, ebp
0x18001c681  jmp     short loc_18001C685
0x18001c683  xor     eax, eax
0x18001c685  mov     rbx, [rsp+58h+arg_0]
0x18001c68a  add     rsp, 30h
0x18001c68e  pop     r15
0x18001c690  pop     r14
0x18001c692  pop     rdi
0x18001c693  pop     rsi
0x18001c694  pop     rbp
0x18001c695  retn
```
