# CImpIDBCreateCommand::CreateCommand(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x10017160`
- end: `0x100173f1`
- name: `?CreateCommand@CImpIDBCreateCommand@@UAGJPAUIUnknown@@ABU_GUID@@PAPAU2@@Z`
- size: `657`
- prototype: `int(CImpIDBCreateCommand *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1000ba80`
- `0x1000ba90`
- `0x10013b20`
- `0x10013f50`
- `0x10017160`
- `0x1001c380`
- `0x1001c6d0`
- `0x10049670`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x100172b6`
- `KERNEL32!InitializeCriticalSection` at `0x100172b6`
- `KERNEL32!LeaveCriticalSection` at `0x100173d5`
- `KERNEL32!LeaveCriticalSection` at `0x100173d5`
- `KERNEL32!EnterCriticalSection` at `0x100171ae`
- `KERNEL32!EnterCriticalSection` at `0x100171ae`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001718e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001718e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001737e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001737e`

## pseudocode

```c
int __stdcall CImpIDBCreateCommand::CreateCommand(
        CImpIDBCreateCommand *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  struct IUnknown *v5; // ebx
  int v6; // edi
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  _DWORD *v10; // eax
  struct CRowsetProperties *v11; // ecx
  int v12; // edi
  struct IUnknown *v13; // eax
  volatile signed __int32 *AddRef; // eax
  const struct _GUID *v15; // edx
  GUID *v16; // ecx
  unsigned int v17; // edi
  bool v18; // cf
  int v19; // eax
  int v20; // eax
  const struct _GUID *v22; // [esp+0h] [ebp-28h]
  int v23; // [esp+4h] [ebp-24h]
  _BYTE v24[4]; // [esp+10h] [ebp-18h] BYREF
  LPCRITICAL_SECTION v25; // [esp+14h] [ebp-14h]
  void *Block; // [esp+18h] [ebp-10h]
  int v27; // [esp+24h] [ebp-4h]

  SetErrorInfo(0, 0);
  if ( a4 )
    *a4 = 0;
  v25 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 104);
  v4 = v25;
  EnterCriticalSection(v25);
  v5 = 0;
  v27 = 0;
  if ( !a4 )
  {
    v6 = -2147024809;
    Block = (void *)-2147024809;
    v7 = *((_DWORD *)this + 2);
    v8 = *(_DWORD *)(v7 + 20);
    v9 = *(_DWORD *)(v7 + 16);
    goto LABEL_19;
  }
  v10 = operator new(0x114u);
  v5 = (struct IUnknown *)v10;
  Block = v10;
  if ( v10 )
  {
    v12 = *((_DWORD *)this + 2);
    *v10 = &CCommand::`vftable';
    v10[1] = 0;
    v10[3] = 0;
    v10[4] = 0;
    v10[5] = 0;
    v10[6] = 0;
    v10[7] = 0;
    v10[8] = 0;
    v10[9] = 0;
    v10[10] = 0;
    v10[11] = 0;
    v10[12] = 0;
    v10[14] = 0;
    v10[15] = 0;
    v10[16] = 0;
    v10[17] = 0;
    v10[18] = 0;
    v10[19] = 0;
    v10[20] = 0;
    v10[21] = 0;
    v10[22] = 0;
    v10[23] = 0;
    v10[24] = 0;
    v10[25] = -1;
    v10[26] = 0;
    v10[27] = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 62));
    v13 = v5;
    LOBYTE(v27) = 4;
    v5[13].lpVtbl = (struct IUnknownVtbl *)v12;
    if ( a2 )
      v13 = a2;
    v5[68].lpVtbl = 0;
    v5[2].lpVtbl = (struct IUnknownVtbl *)v13;
    (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(v12 + 28) + 4))(
      *(_DWORD *)(**(_DWORD **)(v12 + 28) + 4),
      *(_DWORD *)(v12 + 28));
    AddRef = (volatile signed __int32 *)v5[13].lpVtbl[7].AddRef;
    v5[14].lpVtbl = (struct IUnknownVtbl *)AddRef;
    if ( AddRef )
      _InterlockedIncrement(AddRef);
  }
  else
  {
    v5 = 0;
  }
  LOBYTE(v27) = 0;
  if ( !v5 )
  {
    v6 = -2147024882;
    goto LABEL_25;
  }
  v6 = CCommand::FInit((CCommand *)v5, v11);
  Block = (void *)v6;
  if ( v6 < 0 )
  {
LABEL_18:
    v19 = *((_DWORD *)this + 2);
    v8 = *(_DWORD *)(v19 + 20);
    v9 = *(_DWORD *)(v19 + 16);
    if ( v6 == -2147024882 )
    {
LABEL_22:
      ((void (__thiscall *)(struct IUnknown *, int))v5->lpVtbl[1].QueryInterface)(v5, 1);
      v6 = (int)Block;
      goto LABEL_25;
    }
    goto LABEL_19;
  }
  if ( !a2 )
  {
LABEL_17:
    v6 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **), struct IUnknown *, const struct _GUID *, struct IUnknown **))v5->lpVtbl->QueryInterface)(
           v5->lpVtbl->QueryInterface,
           v5,
           a3,
           a4);
    Block = (void *)v6;
    if ( v6 >= 0 )
      goto LABEL_25;
    goto LABEL_18;
  }
  v15 = a3;
  v16 = &IID_IUnknown;
  v17 = 12;
  while ( v16->Data1 == v15->Data1 )
  {
    v16 = (GUID *)((char *)v16 + 4);
    v15 = (const struct _GUID *)((char *)v15 + 4);
    v18 = v17 < 4;
    v17 -= 4;
    if ( v18 )
      goto LABEL_17;
  }
  v6 = -2147217886;
  Block = (void *)-2147217886;
  v20 = *((_DWORD *)this + 2);
  v8 = *(_DWORD *)(v20 + 20);
  v9 = *(_DWORD *)(v20 + 16);
LABEL_19:
  if ( !JetGetDatabaseInfo(v9, v8, v24, 4, 3) )
    CExtError::SendHRtoOLEAuto(v6, (__int128 *)&IID_IDBCreateCommand, 0, v22, v23);
  if ( v5 )
    goto LABEL_22;
LABEL_25:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v6;
}

```

## disassembly

```asm
0x10017160  mov     edi, edi
0x10017162  push    ebp
0x10017163  mov     ebp, esp
0x10017165  push    0FFFFFFFFh
0x10017167  push    offset ?CreateCommand@CImpIDBCreateCommand@@UAGJPAUIUnknown@@ABU_GUID@@PAPAU2@@Z_SEH
0x1001716c  mov     eax, large fs:0
0x10017172  push    eax
0x10017173  sub     esp, 0Ch
0x10017176  push    ebx
0x10017177  push    esi
0x10017178  push    edi; int
0x10017179  mov     eax, ___security_cookie
0x1001717e  xor     eax, ebp
0x10017180  push    eax; struct _GUID *
0x10017181  lea     eax, [ebp+var_C]
0x10017184  mov     large fs:0, eax
0x1001718a  push    0; perrinfo
0x1001718c  push    0; dwReserved
0x1001718e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10017194  mov     edi, [ebp+arg_C]
0x10017197  test    edi, edi
0x10017199  jz      short loc_100171A1
0x1001719b  mov     dword ptr [edi], 0
0x100171a1  mov     esi, [ebp+this]
0x100171a4  mov     esi, [esi+8]
0x100171a7  add     esi, 68h ; 'h'
0x100171aa  push    esi; lpCriticalSection
0x100171ab  mov     [ebp+var_14], esi
0x100171ae  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100171b4  xor     ebx, ebx
0x100171b6  mov     [ebp+var_4], 0
0x100171bd  test    edi, edi
0x100171bf  jnz     short loc_100171DA
0x100171c1  mov     eax, [ebp+this]
0x100171c4  mov     edi, 80070057h
0x100171c9  mov     [ebp+Block], edi
0x100171cc  mov     eax, [eax+8]
0x100171cf  mov     ecx, [eax+14h]
0x100171d2  mov     eax, [eax+10h]
0x100171d5  jmp     loc_10017374
0x100171da  push    114h; Size
0x100171df  call    ??2@YAPAXI@Z; operator new(uint)
0x100171e4  mov     ebx, eax
0x100171e6  add     esp, 4
0x100171e9  mov     [ebp+Block], ebx
0x100171ec  test    ebx, ebx
0x100171ee  jz      loc_100172FF
0x100171f4  mov     eax, [ebp+this]
0x100171f7  mov     edi, [eax+8]
0x100171fa  mov     dword ptr [ebx], offset ??_7CCommand@@6B@; const CCommand::`vftable'
0x10017200  mov     dword ptr [ebx+4], 0
0x10017207  mov     dword ptr [ebx+0Ch], 0
0x1001720e  mov     dword ptr [ebx+10h], 0
0x10017215  mov     dword ptr [ebx+14h], 0
0x1001721c  mov     dword ptr [ebx+18h], 0
0x10017223  mov     dword ptr [ebx+1Ch], 0
0x1001722a  mov     dword ptr [ebx+20h], 0
0x10017231  mov     dword ptr [ebx+24h], 0
0x10017238  mov     dword ptr [ebx+28h], 0
0x1001723f  mov     dword ptr [ebx+2Ch], 0
0x10017246  mov     dword ptr [ebx+30h], 0
0x1001724d  mov     dword ptr [ebx+38h], 0
0x10017254  mov     dword ptr [ebx+3Ch], 0
0x1001725b  mov     dword ptr [ebx+40h], 0
0x10017262  mov     dword ptr [ebx+44h], 0
0x10017269  mov     dword ptr [ebx+48h], 0
0x10017270  mov     dword ptr [ebx+4Ch], 0
0x10017277  mov     dword ptr [ebx+50h], 0
0x1001727e  mov     dword ptr [ebx+54h], 0
0x10017285  mov     dword ptr [ebx+58h], 0
0x1001728c  mov     dword ptr [ebx+5Ch], 0
0x10017293  lea     eax, [ebx+0F8h]
0x10017299  mov     dword ptr [ebx+60h], 0
0x100172a0  push    eax; lpCriticalSection
0x100172a1  mov     dword ptr [ebx+64h], 0FFFFFFFFh
0x100172a8  mov     dword ptr [ebx+68h], 0
0x100172af  mov     dword ptr [ebx+6Ch], 0
0x100172b6  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x100172bc  mov     ecx, [ebp+arg_4]
0x100172bf  mov     eax, ebx
0x100172c1  test    ecx, ecx
0x100172c3  mov     byte ptr [ebp+var_4], 4
0x100172c7  mov     [ebx+34h], edi
0x100172ca  cmovnz  eax, ecx
0x100172cd  mov     dword ptr [ebx+110h], 0
0x100172d7  mov     [ebx+8], eax
0x100172da  mov     eax, [edi+1Ch]
0x100172dd  push    eax
0x100172de  mov     ecx, [eax]
0x100172e0  mov     edi, [ecx+4]
0x100172e3  mov     ecx, edi
0x100172e5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100172eb  call    edi
0x100172ed  mov     eax, [ebx+34h]
0x100172f0  mov     eax, [eax+58h]
0x100172f3  mov     [ebx+38h], eax
0x100172f6  test    eax, eax
0x100172f8  jz      short loc_10017301
0x100172fa  lock inc dword ptr [eax]
0x100172fd  jmp     short loc_10017301
0x100172ff  xor     ebx, ebx
0x10017301  mov     byte ptr [ebp+var_4], 0
0x10017305  test    ebx, ebx
0x10017307  jz      loc_100173CB
0x1001730d  push    ecx; struct CRowsetProperties *
0x1001730e  mov     ecx, ebx; this
0x10017310  call    ?FInit@CCommand@@QAEJPAVCRowsetProperties@@@Z; CCommand::FInit(CRowsetProperties *)
0x10017315  mov     edi, eax
0x10017317  mov     [ebp+Block], edi
0x1001731a  test    edi, edi
0x1001731c  js      short loc_10017360
0x1001731e  cmp     [ebp+arg_4], 0
0x10017322  jz      short loc_10017342
0x10017324  mov     edx, [ebp+arg_8]
0x10017327  mov     ecx, offset _IID_IUnknown
0x1001732c  mov     edi, 0Ch
0x10017331  mov     eax, [ecx]
0x10017333  cmp     eax, [edx]
0x10017335  jnz     short loc_100173B5
0x10017337  add     ecx, 4
0x1001733a  add     edx, 4
0x1001733d  sub     edi, 4
0x10017340  jnb     short loc_10017331
0x10017342  push    [ebp+arg_C]
0x10017345  mov     eax, [ebx]
0x10017347  push    [ebp+arg_8]
0x1001734a  push    ebx
0x1001734b  mov     edi, [eax]
0x1001734d  mov     ecx, edi
0x1001734f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10017355  call    edi
0x10017357  mov     edi, eax
0x10017359  mov     [ebp+Block], eax
0x1001735c  test    edi, edi
0x1001735e  jns     short loc_100173D0
0x10017360  mov     eax, [ebp+this]
0x10017363  mov     eax, [eax+8]
0x10017366  mov     ecx, [eax+14h]
0x10017369  mov     eax, [eax+10h]
0x1001736c  cmp     edi, 8007000Eh
0x10017372  jz      short loc_1001739D
0x10017374  push    3
0x10017376  push    4
0x10017378  lea     edx, [ebp+var_18]
0x1001737b  push    edx
0x1001737c  push    ecx
0x1001737d  push    eax
0x1001737e  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10017384  test    eax, eax
0x10017386  jnz     short loc_10017395
0x10017388  push    eax; int
0x10017389  push    offset _IID_IDBCreateCommand; int
0x1001738e  mov     edx, edi
0x10017390  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10017395  test    edi, edi
0x10017397  jns     short loc_100173D0
0x10017399  test    ebx, ebx
0x1001739b  jz      short loc_100173D0
0x1001739d  mov     eax, [ebx]
0x1001739f  push    1
0x100173a1  mov     edi, [eax+0Ch]
0x100173a4  mov     ecx, edi
0x100173a6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100173ac  mov     ecx, ebx
0x100173ae  call    edi
0x100173b0  mov     edi, [ebp+Block]
0x100173b3  jmp     short loc_100173D0
0x100173b5  mov     eax, [ebp+this]
0x100173b8  mov     edi, 80040E22h
0x100173bd  mov     [ebp+Block], edi
0x100173c0  mov     eax, [eax+8]
0x100173c3  mov     ecx, [eax+14h]
0x100173c6  mov     eax, [eax+10h]
0x100173c9  jmp     short loc_10017374
0x100173cb  mov     edi, 8007000Eh
0x100173d0  test    esi, esi
0x100173d2  jz      short loc_100173DB
0x100173d4  push    esi; lpCriticalSection
0x100173d5  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100173db  mov     eax, edi
0x100173dd  mov     ecx, [ebp+var_C]
0x100173e0  mov     large fs:0, ecx
0x100173e7  pop     ecx
0x100173e8  pop     edi
0x100173e9  pop     esi
0x100173ea  pop     ebx
0x100173eb  mov     esp, ebp
0x100173ed  pop     ebp
0x100173ee  retn    10h
0x1004e2e0  lea     ecx, [ebp+var_14]; this
0x1004e2e3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e2e8  mov     eax, [ebp+Block]
0x1004e2eb  push    eax; Block
0x1004e2ec  call    ??3@YAXPAX@Z; operator delete(void *)
0x1004e2f1  pop     ecx
0x1004e2f2  retn
0x1004e2f3  mov     ecx, [ebp+Block]; this
0x1004e2f6  jmp     ??1CBaseObj@@UAE@XZ; CBaseObj::~CBaseObj(void)
0x1004e2fb  mov     ecx, [ebp+Block]
0x1004e2fe  add     ecx, 54h ; 'T'; this
0x1004e301  jmp     ??1CJetParameterList@@QAE@XZ; CJetParameterList::~CJetParameterList(void)
0x1004e306  mov     ecx, [ebp+Block]
0x1004e309  add     ecx, 0F8h; lpCriticalSection
0x1004e30f  jmp     ??1CriticalSection@@QAE@XZ; CriticalSection::~CriticalSection(void)
0x1004e319  nop
0x1004e31a  nop
0x1004e31b  mov     edx, [esp-4+arg_4]
0x1004e31f  lea     eax, [edx+0Ch]
0x1004e322  mov     ecx, [edx-1Ch]
0x1004e325  xor     ecx, eax; StackCookie
0x1004e327  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e32c  mov     eax, offset stru_1004F794
0x1004e331  jmp     ___CxxFrameHandler3
```
