# CDataObject::GetDataHere(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180009620`
- end: `0x180009811`
- name: `?GetDataHere@CDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(CDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009620`
- `0x1800098e0`
- `0x180009a24`
- `0x180009b98`
- `0x180011914`
- `0x180024010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180009659`
- `ole32!CreateStreamOnHGlobal` at `0x180009659`

## pseudocode

```c
__int64 __fastcall CDataObject::GetDataHere(CDataObject *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  int cfFormat; // r14d
  HRESULT v6; // ebx
  int v7; // eax
  const wchar_t *v8; // rdx
  __int64 v9; // r8
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  CDataObject *v15; // [rsp+58h] [rbp+28h] BYREF
  LPSTREAM ppstm; // [rsp+60h] [rbp+30h] BYREF

  cfFormat = a2->cfFormat;
  a3->pUnkForRelease = 0;
  ppstm = 0;
  v6 = CreateStreamOnHGlobal(a3->hBitmap, 0, &ppstm);
  if ( v6 >= 0 )
  {
    if ( cfFormat == CDataObject::s_cfDisplayName )
    {
      v7 = CDataObject::_WriteDisplayName(this, ppstm);
LABEL_39:
      v6 = v7;
      goto LABEL_41;
    }
    if ( cfFormat == CDataObject::s_cfInternal )
    {
      v15 = this;
      v8 = (const wchar_t *)&v15;
      v9 = 8;
LABEL_38:
      v7 = (*(__int64 (__fastcall **)(LPSTREAM, const wchar_t *, __int64, _QWORD))(*(_QWORD *)ppstm + 32LL))(
             ppstm,
             v8,
             v9,
             0);
      goto LABEL_39;
    }
    if ( cfFormat == CDataObject::s_cfExportScopeAbbrev )
    {
      v7 = CDataObject::_WriteScopeAbbrev(this, ppstm);
      goto LABEL_39;
    }
    if ( cfFormat == CDataObject::s_cfExportScopeFilter )
    {
      if ( *((_DWORD *)this + 7) == 1 )
      {
        v7 = CFilter::Save((CFilter *)(*((_QWORD *)this + 2) + 2648LL), ppstm);
        goto LABEL_39;
      }
      goto LABEL_10;
    }
    if ( cfFormat == CDataObject::s_cfExportResultRecNo )
    {
      if ( *((_DWORD *)this + 7) == 2 )
      {
        v8 = (const wchar_t *)((char *)this + 16);
        v9 = 8;
        goto LABEL_38;
      }
LABEL_10:
      v6 = -2147221398;
      goto LABEL_41;
    }
    if ( cfFormat == CDataObject::s_cfNodeType )
    {
      v10 = *((_DWORD *)this + 7);
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 1 )
          {
LABEL_19:
            v6 = -2147418113;
            goto LABEL_41;
          }
          v8 = (const wchar_t *)&GUID_ResultRecordNode;
        }
        else
        {
          v8 = (const wchar_t *)&GUID_ScopeViewNode;
        }
      }
      else
      {
        v8 = (const wchar_t *)&GUID_EventViewerRootNode;
      }
      v9 = 16;
      goto LABEL_38;
    }
    if ( cfFormat == CDataObject::s_cfNodeId2 )
    {
      v7 = CDataObject::_WriteNodeId2(this, a3);
      goto LABEL_39;
    }
    if ( cfFormat == CDataObject::s_cfNodeTypeString )
    {
      v12 = *((_DWORD *)this + 7);
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          if ( v13 != 1 )
            goto LABEL_19;
          v8 = L"{7D7FE374-E403-11D0-9A97-00C04FD8DBF7}";
        }
        else
        {
          v8 = L"{7AB4A1FC-E403-11D0-9A97-00C04FD8DBF7}";
        }
      }
      else
      {
        v8 = (const wchar_t *)L"{DC1C6BEC-4E2A-11D0-B702-00C04FD8DBF7}";
      }
      v9 = 78;
      goto LABEL_38;
    }
    if ( cfFormat == CDataObject::s_cfSnapinClsid )
    {
      v9 = 16;
      v8 = (const wchar_t *)&CLSID_EventLogSnapin;
      goto LABEL_38;
    }
    if ( cfFormat == CDataObject::s_cfSnapinPreloads )
    {
      LODWORD(v15) = 1;
      v8 = (const wchar_t *)&v15;
      v9 = 4;
      goto LABEL_38;
    }
    v6 = -2147221404;
  }
LABEL_41:
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009620  mov     [rsp-18h+arg_0], rbx
0x180009625  mov     [rsp-18h+arg_18], rsi
0x18000962a  push    rbp
0x18000962b  push    rdi
0x18000962c  push    r14
0x18000962e  mov     rbp, rsp
0x180009631  sub     rsp, 30h
0x180009635  movzx   r14d, word ptr [rdx]
0x180009639  mov     rsi, r8
0x18000963c  mov     rdi, rcx
0x18000963f  mov     qword ptr [r8+10h], 0
0x180009647  lea     r8, [rbp+ppstm]; ppstm
0x18000964b  mov     [rbp+ppstm], 0
0x180009653  xor     edx, edx; fDeleteOnRelease
0x180009655  mov     rcx, [rsi+8]; hGlobal
0x180009659  call    cs:__imp_CreateStreamOnHGlobal
0x18000965f  mov     ebx, eax
0x180009661  test    eax, eax
0x180009663  js      loc_1800097E7
0x180009669  cmp     r14d, cs:?s_cfDisplayName@CDataObject@@2IB; uint const CDataObject::s_cfDisplayName
0x180009670  mov     eax, r14d
0x180009673  jnz     short loc_180009686
0x180009675  mov     rdx, [rbp+ppstm]; struct IStream *
0x180009679  mov     rcx, rdi; this
0x18000967c  call    ?_WriteDisplayName@CDataObject@@AEAAJPEAUIStream@@@Z; CDataObject::_WriteDisplayName(IStream *)
0x180009681  jmp     loc_1800097DE
0x180009686  cmp     eax, cs:?s_cfInternal@CDataObject@@2IB; uint const CDataObject::s_cfInternal
0x18000968c  jnz     short loc_1800096A1
0x18000968e  mov     [rbp+arg_8], rdi
0x180009692  lea     rdx, [rbp+arg_8]
0x180009696  mov     r8d, 8
0x18000969c  jmp     loc_1800097CB
0x1800096a1  cmp     eax, cs:?s_cfExportScopeAbbrev@CDataObject@@2IB; uint const CDataObject::s_cfExportScopeAbbrev
0x1800096a7  jnz     short loc_1800096BA
0x1800096a9  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800096ad  mov     rcx, rdi; this
0x1800096b0  call    ?_WriteScopeAbbrev@CDataObject@@AEAAJPEAUIStream@@@Z; CDataObject::_WriteScopeAbbrev(IStream *)
0x1800096b5  jmp     loc_1800097DE
0x1800096ba  cmp     eax, cs:?s_cfExportScopeFilter@CDataObject@@2IB; uint const CDataObject::s_cfExportScopeFilter
0x1800096c0  jnz     short loc_1800096EB
0x1800096c2  cmp     dword ptr [rdi+1Ch], 1
0x1800096c6  jz      short loc_1800096D2
0x1800096c8  mov     ebx, 8004006Ah
0x1800096cd  jmp     loc_1800097E7
0x1800096d2  mov     rcx, [rdi+10h]
0x1800096d6  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800096da  add     rcx, 0A58h; this
0x1800096e1  call    ?Save@CFilter@@QEAAJPEAUIStream@@@Z; CFilter::Save(IStream *)
0x1800096e6  jmp     loc_1800097DE
0x1800096eb  cmp     eax, cs:?s_cfExportResultRecNo@CDataObject@@2IB; uint const CDataObject::s_cfExportResultRecNo
0x1800096f1  jnz     short loc_180009708
0x1800096f3  cmp     dword ptr [rdi+1Ch], 2
0x1800096f7  jnz     short loc_1800096C8
0x1800096f9  lea     rdx, [rdi+10h]
0x1800096fd  mov     r8d, 8
0x180009703  jmp     loc_1800097CB
0x180009708  cmp     eax, cs:?s_cfNodeType@CDataObject@@2IB; uint const CDataObject::s_cfNodeType
0x18000970e  jnz     short loc_18000974C
0x180009710  mov     ecx, [rdi+1Ch]
0x180009713  test    ecx, ecx
0x180009715  jz      short loc_18000973D
0x180009717  sub     ecx, 1
0x18000971a  jz      short loc_180009734
0x18000971c  cmp     ecx, 1
0x18000971f  jz      short loc_18000972B
0x180009721  mov     ebx, 8000FFFFh
0x180009726  jmp     loc_1800097E7
0x18000972b  lea     rdx, ?GUID_ResultRecordNode@@3U_GUID@@B; _GUID const GUID_ResultRecordNode
0x180009732  jmp     short loc_180009744
0x180009734  lea     rdx, ?GUID_ScopeViewNode@@3U_GUID@@B; _GUID const GUID_ScopeViewNode
0x18000973b  jmp     short loc_180009744
0x18000973d  lea     rdx, ?GUID_EventViewerRootNode@@3U_GUID@@B; _GUID const GUID_EventViewerRootNode
0x180009744  mov     r8d, 10h
0x18000974a  jmp     short loc_1800097CB
0x18000974c  cmp     eax, cs:?s_cfNodeId2@CDataObject@@2IB; uint const CDataObject::s_cfNodeId2
0x180009752  jnz     short loc_180009761
0x180009754  mov     rdx, rsi; struct tagSTGMEDIUM *
0x180009757  mov     rcx, rdi; this
0x18000975a  call    ?_WriteNodeId2@CDataObject@@AEAAJPEAUtagSTGMEDIUM@@@Z; CDataObject::_WriteNodeId2(tagSTGMEDIUM *)
0x18000975f  jmp     short loc_1800097DE
0x180009761  cmp     eax, cs:?s_cfNodeTypeString@CDataObject@@2IB; uint const CDataObject::s_cfNodeTypeString
0x180009767  jnz     short loc_18000979B
0x180009769  mov     ecx, [rdi+1Ch]
0x18000976c  test    ecx, ecx
0x18000976e  jz      short loc_18000978C
0x180009770  sub     ecx, 1
0x180009773  jz      short loc_180009783
0x180009775  cmp     ecx, 1
0x180009778  jnz     short loc_180009721
0x18000977a  lea     rdx, a7d7fe374E40311; "{7D7FE374-E403-11D0-9A97-00C04FD8DBF7}"
0x180009781  jmp     short loc_180009793
0x180009783  lea     rdx, a7ab4a1fcE40311; "{7AB4A1FC-E403-11D0-9A97-00C04FD8DBF7}"
0x18000978a  jmp     short loc_180009793
0x18000978c  lea     rdx, aDc1c6bec4e2a11; "{DC1C6BEC-4E2A-11D0-B702-00C04FD8DBF7}"
0x180009793  mov     r8d, 4Eh ; 'N'
0x180009799  jmp     short loc_1800097CB
0x18000979b  cmp     eax, cs:?s_cfSnapinClsid@CDataObject@@2IB; uint const CDataObject::s_cfSnapinClsid
0x1800097a1  jnz     short loc_1800097B2
0x1800097a3  mov     r8d, 10h
0x1800097a9  lea     rdx, ?CLSID_EventLogSnapin@@3U_GUID@@B; _GUID const CLSID_EventLogSnapin
0x1800097b0  jmp     short loc_1800097CB
0x1800097b2  cmp     eax, cs:?s_cfSnapinPreloads@CDataObject@@2IB; uint const CDataObject::s_cfSnapinPreloads
0x1800097b8  jnz     short loc_1800097E2
0x1800097ba  mov     dword ptr [rbp+arg_8], 1
0x1800097c1  lea     rdx, [rbp+arg_8]
0x1800097c5  mov     r8d, 4
0x1800097cb  mov     rcx, [rbp+ppstm]
0x1800097cf  xor     r9d, r9d
0x1800097d2  mov     rax, [rcx]
0x1800097d5  mov     rax, [rax+20h]
0x1800097d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097de  mov     ebx, eax
0x1800097e0  jmp     short loc_1800097E7
0x1800097e2  mov     ebx, 80040064h
0x1800097e7  mov     rcx, [rbp+ppstm]
0x1800097eb  test    rcx, rcx
0x1800097ee  jz      short loc_1800097FC
0x1800097f0  mov     rax, [rcx]
0x1800097f3  mov     rax, [rax+10h]
0x1800097f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fc  mov     rsi, [rsp+30h+arg_18]
0x180009801  mov     eax, ebx
0x180009803  mov     rbx, [rsp+30h+arg_0]
0x180009808  add     rsp, 30h
0x18000980c  pop     r14
0x18000980e  pop     rdi
0x18000980f  pop     rbp
0x180009810  retn
```
