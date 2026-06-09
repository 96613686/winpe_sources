# CImpIOpenRowset::OpenRowset(IUnknown *,tagDBID *,tagDBID *,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x10025180`
- end: `0x100254d6`
- name: `?OpenRowset@CImpIOpenRowset@@UAGJPAUIUnknown@@PAUtagDBID@@1ABU_GUID@@KQAUtagDBPROPSET@@PAPAU2@@Z`
- size: `854`
- prototype: `int(CImpIOpenRowset *__hidden this, struct IUnknown *, struct tagDBID *, struct tagDBID *, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x10021070`
- `0x100215b0`
- `0x10025180`
- `0x10027cf0`
- `0x10028340`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10025453`
- `KERNEL32!LeaveCriticalSection` at `0x10025453`
- `KERNEL32!EnterCriticalSection` at `0x100251e1`
- `KERNEL32!EnterCriticalSection` at `0x100251e1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100251ce`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100251ce`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100254a5`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100254a5`

## pseudocode

```c
int __stdcall CImpIOpenRowset::OpenRowset(
        CImpIOpenRowset *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        struct tagDBID *a4,
        struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  CImpIOpenRowset *v8; // edi
  struct _RTL_CRITICAL_SECTION *v9; // esi
  struct tagDBID *v10; // eax
  struct tagDBID *v11; // edx
  int v12; // ebx
  int v13; // ecx
  int v14; // eax
  struct _GUID *v15; // edx
  GUID *v16; // ecx
  unsigned int v17; // edi
  bool v18; // cf
  int v19; // eax
  CRowset *v20; // eax
  CRowset *v21; // ecx
  LPOLESTR pwszName; // eax
  struct _GUID *v23; // edx
  GUID *v24; // ecx
  unsigned int v25; // edi
  struct IUnknown **v26; // ecx
  CRowset *v27; // eax
  int v29; // eax
  int v30; // ecx
  int v31; // eax
  const struct _GUID *v32; // [esp+0h] [ebp-44h]
  int v33; // [esp+4h] [ebp-40h]
  _DWORD v34[4]; // [esp+10h] [ebp-34h] BYREF
  int v35; // [esp+20h] [ebp-24h]
  unsigned int v36; // [esp+24h] [ebp-20h] BYREF
  LPCRITICAL_SECTION v37; // [esp+28h] [ebp-1Ch]
  BOOL v38; // [esp+2Ch] [ebp-18h]
  int v39; // [esp+30h] [ebp-14h] BYREF
  CRowset *v40; // [esp+34h] [ebp-10h]
  int v41; // [esp+40h] [ebp-4h]

  v34[0] = &CRowsetProperties::`vftable';
  v40 = 0;
  memset(&v34[1], 0, 12);
  v35 = 0;
  v41 = 0;
  v39 = 0xFFFF;
  SetErrorInfo(0, 0);
  v8 = this;
  v37 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 104);
  v9 = v37;
  EnterCriticalSection(v37);
  LOBYTE(v41) = 1;
  if ( a8 )
    *a8 = 0;
  v10 = a3;
  v11 = a4;
  if ( !a3 && !a4 )
  {
LABEL_5:
    v12 = -2147024809;
LABEL_59:
    v19 = *((_DWORD *)v8 + 2);
LABEL_60:
    v30 = *(_DWORD *)(v19 + 20);
    v31 = *(_DWORD *)(v19 + 16);
LABEL_61:
    if ( !JetGetDatabaseInfo(v31, v30, &v36, 4, 3) )
      CExtError::SendHRtoOLEAuto(v12, (__int128 *)&IID_IOpenRowset, 0, v32, v33);
LABEL_63:
    v27 = v40;
    if ( v12 >= 0 )
      goto LABEL_52;
    v26 = a8;
    if ( !a8 )
      goto LABEL_50;
    goto LABEL_49;
  }
  if ( a6 && !a7 )
  {
    v12 = -2147024809;
    goto LABEL_59;
  }
  v13 = 0;
  if ( a6 )
  {
    while ( 1 )
    {
      v8 = this;
      if ( !a7[v13].rgProperties )
      {
        v11 = a4;
        if ( a7[v13].cProperties )
          goto LABEL_5;
      }
      if ( ++v13 >= a6 )
      {
        v10 = a3;
        break;
      }
    }
  }
  if ( !v10 )
  {
    if ( v11 )
    {
      v12 = -2147217867;
      goto LABEL_59;
    }
LABEL_58:
    v12 = -2147217865;
    goto LABEL_59;
  }
  if ( v10->eKind != 2 || !v10->uName.ulPropid )
    goto LABEL_58;
  if ( v11 && (v11->eKind != 2 || !v11->uName.ulPropid) )
  {
    v12 = -2147217867;
    goto LABEL_59;
  }
  v12 = CSettableProperties::FInit((CSettableProperties *)v34);
  if ( v12 < 0 )
    goto LABEL_56;
  v12 = CRowsetProperties::CopyPropertiesFromStaticTable(
          (CRowsetProperties *)v34,
          (const struct DBInfoProps *)&rgDBInfoProps);
  if ( v12 < 0 )
    goto LABEL_56;
  v35 = *(_DWORD *)(*((_DWORD *)v8 + 2) + 84) + 152;
  v14 = CSettableProperties::SetProperties((CSettableProperties *)v34, a6, a7, 0);
  v12 = v14;
  if ( v14 < 0 )
    goto LABEL_56;
  if ( a8 )
  {
    v38 = v14 == 265946;
    v12 = CRowsetProperties::ValidateStateForJetOpenTable(
            (CRowsetProperties *)v34,
            &v36,
            a5,
            (enum eJetCursorType *)&v39,
            0);
    if ( v12 < 0 )
      goto LABEL_56;
    v20 = (CRowset *)operator new(0xF0u);
    v36 = (unsigned int)v20;
    if ( v20 )
    {
      v21 = CRowset::CRowset(v20, a2);
      v40 = v21;
      if ( v21 )
      {
        if ( a4 )
          pwszName = a4->uName.pwszName;
        else
          pwszName = 0;
        v12 = CRowset::FInit(
                (int)v21,
                *((_DWORD *)v8 + 2),
                0,
                (int)a3->uName.pwszName,
                pwszName,
                0,
                (struct CSettableProperties *)v34,
                v39,
                0,
                0,
                0,
                0,
                a6,
                (unsigned int)a7,
                a5);
        if ( v12 >= 0 )
        {
          if ( a2 )
          {
            v23 = a5;
            v24 = &IID_IUnknown;
            v25 = 12;
            while ( v24->Data1 == v23->Data1 )
            {
              v24 = (GUID *)((char *)v24 + 4);
              v23 = (struct _GUID *)((char *)v23 + 4);
              v18 = v25 < 4;
              v25 -= 4;
              if ( v18 )
                goto LABEL_42;
            }
            v12 = -2147217886;
            v19 = *((_DWORD *)this + 2);
            goto LABEL_60;
          }
LABEL_42:
          v12 = (**(int (__thiscall ***)(_DWORD, CRowset *, struct _GUID *, struct IUnknown **))v40)(
                  **(_DWORD **)v40,
                  v40,
                  a5,
                  a8);
          if ( v12 >= 0 )
          {
            v12 = 0;
            if ( v38 )
              v12 = 265946;
            goto LABEL_52;
          }
          v8 = this;
LABEL_56:
          v29 = *((_DWORD *)v8 + 2);
          v30 = *(_DWORD *)(v29 + 20);
          v31 = *(_DWORD *)(v29 + 16);
          if ( v12 == -2147024882 )
            goto LABEL_63;
          goto LABEL_61;
        }
LABEL_48:
        v26 = a8;
        v27 = v40;
LABEL_49:
        *v26 = 0;
LABEL_50:
        if ( v27 )
          (*(void (__thiscall **)(CRowset *, int))(*(_DWORD *)v27 + 12))(v40, 1);
        goto LABEL_52;
      }
    }
    else
    {
      v40 = 0;
    }
    v12 = -2147024882;
    goto LABEL_48;
  }
  v15 = a5;
  v16 = &GUID_NULL;
  v17 = 12;
  while ( v16->Data1 == v15->Data1 )
  {
    v16 = (GUID *)((char *)v16 + 4);
    v15 = (struct _GUID *)((char *)v15 + 4);
    v18 = v17 < 4;
    v17 -= 4;
    if ( v18 )
    {
      v12 = -2147467262;
      v19 = *((_DWORD *)this + 2);
      goto LABEL_60;
    }
  }
LABEL_52:
  if ( v9 )
    LeaveCriticalSection(v9);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v34);
  return v12;
}

```

## disassembly

```asm
0x10025180  mov     edi, edi
0x10025182  push    ebp
0x10025183  mov     ebp, esp
0x10025185  push    0FFFFFFFFh
0x10025187  push    offset ?OpenRowset@CImpIOpenRowset@@UAGJPAUIUnknown@@PAUtagDBID@@1ABU_GUID@@KQAUtagDBPROPSET@@PAPAU2@@Z_SEH
0x1002518c  mov     eax, large fs:0
0x10025192  push    eax
0x10025193  sub     esp, 28h
0x10025196  push    ebx
0x10025197  push    esi
0x10025198  push    edi; int
0x10025199  mov     eax, ___security_cookie
0x1002519e  xor     eax, ebp
0x100251a0  push    eax; struct _GUID *
0x100251a1  lea     eax, [ebp+var_C]
0x100251a4  mov     large fs:0, eax
0x100251aa  xor     ecx, ecx
0x100251ac  mov     [ebp+var_34], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x100251b3  mov     [ebp+var_10], ecx
0x100251b6  mov     [ebp+var_30], ecx
0x100251b9  mov     [ebp+var_2C], ecx
0x100251bc  mov     [ebp+var_28], ecx
0x100251bf  mov     [ebp+var_24], ecx
0x100251c2  push    ecx; perrinfo
0x100251c3  mov     [ebp+var_4], ecx
0x100251c6  push    ecx; dwReserved
0x100251c7  mov     [ebp+var_14], 0FFFFh
0x100251ce  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100251d4  mov     edi, [ebp+this]
0x100251d7  mov     esi, [edi+8]
0x100251da  add     esi, 68h ; 'h'
0x100251dd  push    esi; lpCriticalSection
0x100251de  mov     [ebp+var_1C], esi
0x100251e1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100251e7  mov     eax, [ebp+arg_1C]
0x100251ea  mov     byte ptr [ebp+var_4], 1
0x100251ee  test    eax, eax
0x100251f0  jz      short loc_100251F8
0x100251f2  mov     dword ptr [eax], 0
0x100251f8  mov     eax, [ebp+arg_8]
0x100251fb  mov     edx, [ebp+arg_C]
0x100251fe  test    eax, eax
0x10025200  jnz     short loc_10025210
0x10025202  test    edx, edx
0x10025204  jnz     short loc_10025210
0x10025206  mov     ebx, 80070057h
0x1002520b  jmp     loc_10025492
0x10025210  mov     ebx, [ebp+arg_14]
0x10025213  test    ebx, ebx
0x10025215  jz      short loc_10025227
0x10025217  cmp     [ebp+arg_18], 0
0x1002521b  jnz     short loc_10025227
0x1002521d  mov     ebx, 80070057h
0x10025222  jmp     loc_10025492
0x10025227  xor     ecx, ecx
0x10025229  test    ebx, ebx
0x1002522b  jz      short loc_10025254
0x1002522d  nop     dword ptr [eax]
0x10025230  mov     edi, [ebp+arg_18]
0x10025233  lea     eax, [ecx+ecx*2]
0x10025236  cmp     dword ptr [edi+eax*8], 0
0x1002523a  mov     edi, [ebp+this]
0x1002523d  jnz     short loc_1002524C
0x1002523f  mov     edx, [ebp+arg_18]
0x10025242  cmp     dword ptr [edx+eax*8+4], 0
0x10025247  mov     edx, [ebp+arg_C]
0x1002524a  jnz     short loc_10025206
0x1002524c  inc     ecx
0x1002524d  cmp     ecx, ebx
0x1002524f  jb      short loc_10025230
0x10025251  mov     eax, [ebp+arg_8]
0x10025254  test    eax, eax
0x10025256  jnz     short loc_1002526A
0x10025258  test    edx, edx
0x1002525a  jz      loc_1002548D
0x10025260  mov     ebx, 80040E35h
0x10025265  jmp     loc_10025492
0x1002526a  cmp     dword ptr [eax+10h], 2
0x1002526e  jnz     loc_1002548D
0x10025274  cmp     dword ptr [eax+14h], 0
0x10025278  jz      loc_1002548D
0x1002527e  test    edx, edx
0x10025280  jz      short loc_10025298
0x10025282  cmp     dword ptr [edx+10h], 2
0x10025286  jnz     short loc_1002528E
0x10025288  cmp     dword ptr [edx+14h], 0
0x1002528c  jnz     short loc_10025298
0x1002528e  mov     ebx, 80040E35h
0x10025293  jmp     loc_10025492
0x10025298  lea     ecx, [ebp+var_34]; this
0x1002529b  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x100252a0  mov     ebx, eax
0x100252a2  test    ebx, ebx
0x100252a4  js      loc_1002547A
0x100252aa  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x100252af  lea     ecx, [ebp+var_34]; this
0x100252b2  call    ?CopyPropertiesFromStaticTable@CRowsetProperties@@QAEJPBUDBInfoProps@@@Z; CRowsetProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x100252b7  mov     ebx, eax
0x100252b9  test    ebx, ebx
0x100252bb  js      loc_1002547A
0x100252c1  mov     eax, [edi+8]
0x100252c4  lea     ecx, [ebp+var_34]; this
0x100252c7  push    0; struct CDBSession *
0x100252c9  push    [ebp+arg_18]; struct tagDBPROPSET *
0x100252cc  mov     eax, [eax+54h]
0x100252cf  push    [ebp+arg_14]; unsigned int
0x100252d2  add     eax, 98h
0x100252d7  mov     [ebp+var_24], eax
0x100252da  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x100252df  mov     ebx, eax
0x100252e1  test    ebx, ebx
0x100252e3  js      loc_1002547A
0x100252e9  cmp     [ebp+arg_1C], 0
0x100252ed  jnz     short loc_10025325
0x100252ef  mov     edx, [ebp+arg_10]
0x100252f2  mov     ecx, offset _GUID_NULL
0x100252f7  mov     edi, 0Ch
0x100252fc  nop     dword ptr [eax+00h]
0x10025300  mov     eax, [ecx]
0x10025302  cmp     eax, [edx]
0x10025304  jnz     loc_1002544E
0x1002530a  add     ecx, 4
0x1002530d  add     edx, 4
0x10025310  sub     edi, 4
0x10025313  jnb     short loc_10025300
0x10025315  mov     eax, [ebp+this]
0x10025318  mov     ebx, 80004002h
0x1002531d  mov     eax, [eax+8]
0x10025320  jmp     loc_10025495
0x10025325  xor     eax, eax
0x10025327  lea     ecx, [ebp+var_34]; this
0x1002532a  cmp     ebx, 40EDAh
0x10025330  push    0; int
0x10025332  setz    al
0x10025335  mov     [ebp+var_18], eax
0x10025338  lea     eax, [ebp+var_14]
0x1002533b  push    eax; enum eJetCursorType *
0x1002533c  push    [ebp+arg_10]; struct _GUID *
0x1002533f  lea     eax, [ebp+var_20]
0x10025342  push    eax; unsigned int *
0x10025343  call    ?ValidateStateForJetOpenTable@CRowsetProperties@@QAEJAAKABU_GUID@@AAW4eJetCursorType@@H@Z; CRowsetProperties::ValidateStateForJetOpenTable(ulong &,_GUID const &,eJetCursorType &,int)
0x10025348  mov     ebx, eax
0x1002534a  test    ebx, ebx
0x1002534c  js      loc_1002547A
0x10025352  push    0F0h; Size
0x10025357  call    ??2@YAPAXI@Z; operator new(uint)
0x1002535c  add     esp, 4
0x1002535f  mov     [ebp+var_20], eax
0x10025362  test    eax, eax
0x10025364  jz      loc_10025420
0x1002536a  push    [ebp+arg_4]; struct IUnknown *
0x1002536d  mov     ecx, eax; this
0x1002536f  call    ??0CRowset@@QAE@PAUIUnknown@@@Z; CRowset::CRowset(IUnknown *)
0x10025374  mov     ecx, eax
0x10025376  mov     [ebp+var_10], ecx
0x10025379  test    ecx, ecx
0x1002537b  jz      loc_10025425
0x10025381  mov     eax, [ebp+arg_C]
0x10025384  test    eax, eax
0x10025386  jz      short loc_1002538D
0x10025388  mov     eax, [eax+14h]
0x1002538b  jmp     short loc_1002538F
0x1002538d  xor     eax, eax
0x1002538f  push    [ebp+arg_10]
0x10025392  lea     edx, [ebp+var_34]
0x10025395  push    [ebp+arg_18]
0x10025398  push    [ebp+arg_14]
0x1002539b  push    0
0x1002539d  push    0
0x1002539f  push    0
0x100253a1  push    0
0x100253a3  push    [ebp+var_14]
0x100253a6  push    edx
0x100253a7  push    0
0x100253a9  push    eax
0x100253aa  mov     eax, [ebp+arg_8]
0x100253ad  xor     edx, edx
0x100253af  push    dword ptr [eax+14h]
0x100253b2  push    0
0x100253b4  push    dword ptr [edi+8]
0x100253b7  call    ?FInit@CRowset@@QAGJKPAVCDBSession@@PAVCCommand@@PAG2KABVCRowsetProperties@@W4eJetCursorType@@PAXPAKPAVColumnData@@HKQAUtagDBPROPSET@@ABU_GUID@@@Z; CRowset::FInit(ulong,CDBSession *,CCommand *,ushort *,ushort *,ulong,CRowsetProperties const &,eJetCursorType,void *,ulong *,ColumnData *,int,ulong,tagDBPROPSET * const,_GUID const &)
0x100253bc  mov     ebx, eax
0x100253be  test    ebx, ebx
0x100253c0  js      short loc_1002542A
0x100253c2  cmp     [ebp+arg_4], 0
0x100253c6  jz      short loc_100253E6
0x100253c8  mov     edx, [ebp+arg_10]
0x100253cb  mov     ecx, offset _IID_IUnknown
0x100253d0  mov     edi, 0Ch
0x100253d5  mov     eax, [ecx]
0x100253d7  cmp     eax, [edx]
0x100253d9  jnz     short loc_10025413
0x100253db  add     ecx, 4
0x100253de  add     edx, 4
0x100253e1  sub     edi, 4
0x100253e4  jnb     short loc_100253D5
0x100253e6  mov     ecx, [ebp+var_10]
0x100253e9  push    [ebp+arg_1C]
0x100253ec  push    [ebp+arg_10]
0x100253ef  mov     eax, [ecx]
0x100253f1  push    ecx
0x100253f2  mov     edi, [eax]
0x100253f4  mov     ecx, edi
0x100253f6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100253fc  call    edi
0x100253fe  mov     ebx, eax
0x10025400  test    ebx, ebx
0x10025402  js      short loc_10025477
0x10025404  xor     ebx, ebx
0x10025406  cmp     [ebp+var_18], 1
0x1002540a  jnz     short loc_1002544E
0x1002540c  mov     ebx, 40EDAh
0x10025411  jmp     short loc_1002544E
0x10025413  mov     eax, [ebp+this]
0x10025416  mov     ebx, 80040E22h
0x1002541b  mov     eax, [eax+8]
0x1002541e  jmp     short loc_10025495
0x10025420  xor     ecx, ecx
0x10025422  mov     [ebp+var_10], ecx
0x10025425  mov     ebx, 8007000Eh
0x1002542a  mov     ecx, [ebp+arg_1C]
0x1002542d  mov     eax, [ebp+var_10]
0x10025430  mov     dword ptr [ecx], 0
0x10025436  test    eax, eax
0x10025438  jz      short loc_1002544E
0x1002543a  mov     eax, [eax]
0x1002543c  push    1
0x1002543e  mov     edi, [eax+0Ch]
0x10025441  mov     ecx, edi
0x10025443  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025449  mov     ecx, [ebp+var_10]
0x1002544c  call    edi
0x1002544e  test    esi, esi
0x10025450  jz      short loc_10025459
0x10025452  push    esi; lpCriticalSection
0x10025453  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025459  lea     ecx, [ebp+var_34]; this
0x1002545c  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10025461  mov     eax, ebx
0x10025463  mov     ecx, [ebp+var_C]
0x10025466  mov     large fs:0, ecx
0x1002546d  pop     ecx
0x1002546e  pop     edi
0x1002546f  pop     esi
0x10025470  pop     ebx
0x10025471  mov     esp, ebp
0x10025473  pop     ebp
0x10025474  retn    20h ; ' '
0x10025477  mov     edi, [ebp+this]
0x1002547a  mov     eax, [edi+8]
0x1002547d  mov     ecx, [eax+14h]
0x10025480  mov     eax, [eax+10h]
0x10025483  cmp     ebx, 8007000Eh
0x10025489  jz      short loc_100254BC
0x1002548b  jmp     short loc_1002549B
0x1002548d  mov     ebx, 80040E37h
0x10025492  mov     eax, [edi+8]
0x10025495  mov     ecx, [eax+14h]
0x10025498  mov     eax, [eax+10h]
0x1002549b  push    3
0x1002549d  push    4
0x1002549f  lea     edx, [ebp+var_20]
0x100254a2  push    edx
0x100254a3  push    ecx
0x100254a4  push    eax
0x100254a5  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100254ab  test    eax, eax
0x100254ad  jnz     short loc_100254BC
0x100254af  push    eax; int
0x100254b0  push    offset _IID_IOpenRowset; int
0x100254b5  mov     edx, ebx
0x100254b7  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100254bc  mov     eax, [ebp+var_10]
0x100254bf  mov     [ebp+var_10], eax
0x100254c2  test    ebx, ebx
0x100254c4  jns     short loc_1002544E
0x100254c6  mov     ecx, [ebp+arg_1C]
0x100254c9  test    ecx, ecx
0x100254cb  jz      loc_10025436
0x100254d1  jmp     loc_10025430
0x1004e910  lea     ecx, [ebp+var_34]; this
0x1004e913  jmp     ??1CTableProperties@@UAE@XZ; CTableProperties::~CTableProperties(void)
0x1004e918  lea     ecx, [ebp+var_1C]; this
0x1004e91b  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e925  nop
0x1004e926  nop
0x1004e927  mov     edx, [esp-4+arg_4]
0x1004e92b  lea     eax, [edx+0Ch]
0x1004e92e  mov     ecx, [edx-38h]
0x1004e931  xor     ecx, eax; StackCookie
0x1004e933  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e938  mov     eax, offset stru_1004FC2C
0x1004e93d  jmp     ___CxxFrameHandler3
```
