# CImpIRowsetLocate::GetRowsAtRatio(ulong,ulong,ulong,ulong,long,ulong *,ulong * *)

- ea: `0x10032280`
- end: `0x1003250a`
- name: `?GetRowsAtRatio@CImpIRowsetLocate@@UAGJKKKKJPAKPAPAK@Z`
- size: `650`
- prototype: `int(CImpIRowsetLocate *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, int, unsigned int *, unsigned int **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10032280`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100324e4`
- `KERNEL32!LeaveCriticalSection` at `0x100324e4`
- `KERNEL32!EnterCriticalSection` at `0x10032333`
- `KERNEL32!EnterCriticalSection` at `0x10032333`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100322c3`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100322c3`
- `msjet40!__imp__JetGetBookmark@20` at `0x10032425`
- `msjet40!__imp__JetGetBookmark@20` at `0x10032425`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100324c8`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100324c8`
- `msjet40!__imp__JetGotoPosition@12` at `0x100323fa`
- `msjet40!__imp__JetGotoPosition@12` at `0x100323fa`
- `msjet40!__imp__JetMove@16` at `0x10032389`
- `msjet40!__imp__JetMove@16` at `0x10032389`

## pseudocode

```c
int __stdcall CImpIRowsetLocate::GetRowsAtRatio(
        CImpIRowsetLocate *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        unsigned int *a7,
        unsigned int **a8)
{
  int v8; // edi
  struct _RTL_CRITICAL_SECTION *v9; // esi
  struct _RTL_CRITICAL_SECTION *v10; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v12; // ecx
  int isZombie; // eax
  bool v14; // zf
  JET_ERR Bookmark; // eax
  const struct _GUID *v17; // [esp+0h] [ebp-48h]
  const struct _GUID *v18; // [esp+4h] [ebp-44h]
  unsigned int pcbActual; // [esp+10h] [ebp-38h] BYREF
  _BYTE pvBookmark[4]; // [esp+14h] [ebp-34h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [esp+18h] [ebp-30h]
  unsigned int *v22; // [esp+1Ch] [ebp-2Ch] BYREF
  unsigned int **v23; // [esp+20h] [ebp-28h]
  CImpIRowsetLocate *v24; // [esp+24h] [ebp-24h]
  JET_RECPOS precpos; // [esp+28h] [ebp-20h] BYREF
  int v26; // [esp+44h] [ebp-4h]

  v8 = 0;
  v24 = this;
  v22 = a7;
  v23 = a8;
  SetErrorInfo(0, 0);
  v9 = 0;
  v21 = 0;
  v26 = 0;
  if ( a7 )
    *a7 = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)v24 + 2);
  LockSemaphore = v10[2].LockSemaphore;
  if ( !LockSemaphore
    || (LockSemaphore[4] != 1 || (v12 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v12)),
        isZombie != 1) )
  {
    if ( v10[4].SpinCount || v10[9].SpinCount )
    {
      if ( ((int)v10[4].DebugInfo & 0x400) != 0 )
      {
        v8 = -2147217888;
        goto LABEL_44;
      }
      v9 = v10 + 3;
      v21 = v10 + 3;
      EnterCriticalSection(v10 + 3);
      if ( !a7 || (v14 = v23 == 0, *a7 = 0, v14) )
      {
        v8 = -2147024809;
        goto LABEL_44;
      }
      if ( !a5 || a4 > a5 )
      {
        v8 = -2147217902;
        goto LABEL_44;
      }
      if ( a4 )
      {
        if ( a5 == a4 )
        {
          if ( a6 > 0 )
          {
            v8 = 265926;
            goto LABEL_47;
          }
          if ( a6 < 0 )
          {
            Bookmark = JetMove(
                         *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 16),
                         *(_DWORD *)(*((_DWORD *)v24 + 2) + 108),
                         0x7FFFFFFF,
                         0);
            goto LABEL_21;
          }
        }
      }
      else
      {
        if ( a6 > 0 )
        {
          Bookmark = JetMove(
                       *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 16),
                       *(_DWORD *)(*((_DWORD *)v24 + 2) + 108),
                       0x80000000,
                       0);
LABEL_21:
          if ( Bookmark == -1603 )
            goto LABEL_24;
          if ( Bookmark > 0 )
          {
LABEL_23:
            v8 = -2147467259;
LABEL_41:
            CExtError::SendJetErrortoOLEAuto(
              v8,
              *(char **)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 16),
              Bookmark,
              (int)&IID_IRowsetScroll,
              (int)v17,
              v18);
            goto LABEL_47;
          }
LABEL_34:
          Bookmark = JetGetBookmark(
                       *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 16),
                       *(_DWORD *)(*((_DWORD *)v24 + 2) + 108),
                       pvBookmark,
                       4u,
                       &pcbActual);
          if ( Bookmark != -1603 )
          {
            if ( !Bookmark )
            {
              v8 = (*(int (__thiscall **)(_DWORD, CImpIRowsetLocate *, unsigned int, unsigned int, int, _BYTE *, _DWORD, int, unsigned int *, unsigned int **))(*(_DWORD *)v24 + 36))(
                     *(_DWORD *)(*(_DWORD *)v24 + 36),
                     v24,
                     a2,
                     a3,
                     4,
                     pvBookmark,
                     0,
                     a6,
                     v22,
                     v23);
              if ( v8 >= 0 )
                goto LABEL_47;
              goto LABEL_44;
            }
            goto LABEL_23;
          }
LABEL_24:
          v8 = 265926;
          goto LABEL_41;
        }
        if ( a6 < 0 )
        {
          v8 = 265926;
          goto LABEL_47;
        }
      }
      precpos.centriesTotal = a5;
      precpos.cbStruct = 16;
      precpos.centriesLT = a4;
      Bookmark = JetGotoPosition(
                   *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 16),
                   *(_DWORD *)(*((_DWORD *)v24 + 2) + 108),
                   &precpos);
      if ( Bookmark == -1603 )
      {
        if ( !a6 )
        {
          *v23 = 0;
          goto LABEL_47;
        }
      }
      else if ( !Bookmark )
      {
        goto LABEL_34;
      }
      v8 = -2147467259;
      goto LABEL_41;
    }
  }
  v8 = -2147418113;
LABEL_44:
  if ( v8 != -2147024882
    && !JetGetDatabaseInfo(
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 16),
          *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v24 + 2) + 56) + 20),
          &v22,
          4,
          3) )
  {
    CExtError::SendHRtoOLEAuto(v8, (__int128 *)&IID_IRowsetScroll, 0, v17, (int)v18);
  }
LABEL_47:
  if ( v9 )
    LeaveCriticalSection(v9);
  return v8;
}

```

## disassembly

```asm
0x10032280  mov     edi, edi
0x10032282  push    ebp
0x10032283  mov     ebp, esp
0x10032285  push    0FFFFFFFFh
0x10032287  push    offset ?GetRowsAtRatio@CImpIRowsetLocate@@UAGJKKKKJPAKPAPAK@Z_SEH
0x1003228c  mov     eax, large fs:0
0x10032292  push    eax
0x10032293  sub     esp, 2Ch
0x10032296  mov     eax, ___security_cookie
0x1003229b  xor     eax, ebp
0x1003229d  mov     [ebp+var_10], eax
0x100322a0  push    ebx
0x100322a1  push    esi
0x100322a2  push    edi; int
0x100322a3  push    eax; struct _GUID *
0x100322a4  lea     eax, [ebp+var_C]
0x100322a7  mov     large fs:0, eax
0x100322ad  mov     eax, [ebp+this]
0x100322b0  xor     edi, edi
0x100322b2  mov     ebx, [ebp+arg_18]
0x100322b5  push    edi; perrinfo
0x100322b6  mov     [ebp+var_24], eax
0x100322b9  mov     eax, [ebp+arg_1C]
0x100322bc  push    edi; dwReserved
0x100322bd  mov     [ebp+var_2C], ebx
0x100322c0  mov     [ebp+var_28], eax
0x100322c3  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100322c9  xor     esi, esi
0x100322cb  mov     [ebp+var_30], esi
0x100322ce  mov     [ebp+var_4], esi
0x100322d1  test    ebx, ebx
0x100322d3  jz      short loc_100322D7
0x100322d5  mov     [ebx], esi
0x100322d7  mov     edx, [ebp+var_24]
0x100322da  mov     edx, [edx+8]
0x100322dd  mov     eax, [edx+40h]
0x100322e0  test    eax, eax
0x100322e2  jz      short loc_10032300
0x100322e4  cmp     dword ptr [eax+10h], 1
0x100322e8  jnz     short loc_100322F8
0x100322ea  mov     ecx, [eax+8]; this
0x100322ed  test    ecx, ecx
0x100322ef  jz      short loc_100322F8
0x100322f1  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x100322f6  jmp     short loc_100322FB
0x100322f8  mov     eax, [eax+0Ch]
0x100322fb  cmp     eax, 1
0x100322fe  jz      short loc_1003230F
0x10032300  cmp     dword ptr [edx+74h], 0
0x10032304  jnz     short loc_10032319
0x10032306  cmp     dword ptr [edx+0ECh], 0
0x1003230d  jnz     short loc_10032319
0x1003230f  mov     edi, 8000FFFFh
0x10032314  jmp     loc_100324A9
0x10032319  test    dword ptr [edx+60h], 400h
0x10032320  jz      short loc_1003232C
0x10032322  mov     edi, 80040E20h
0x10032327  jmp     loc_100324A9
0x1003232c  lea     esi, [edx+48h]
0x1003232f  push    esi; lpCriticalSection
0x10032330  mov     [ebp+var_30], esi
0x10032333  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10032339  test    ebx, ebx
0x1003233b  jz      loc_100324A4
0x10032341  cmp     [ebp+var_28], 0
0x10032345  mov     dword ptr [ebx], 0
0x1003234b  jz      loc_100324A4
0x10032351  mov     eax, [ebp+arg_10]
0x10032354  test    eax, eax
0x10032356  jz      loc_1003249D
0x1003235c  mov     ecx, [ebp+arg_C]
0x1003235f  cmp     ecx, eax
0x10032361  ja      loc_1003249D
0x10032367  mov     ebx, [ebp+arg_14]
0x1003236a  test    ecx, ecx
0x1003236c  jnz     short loc_100323BC
0x1003236e  test    ebx, ebx
0x10032370  jle     short loc_100323B0
0x10032372  push    0; grbit
0x10032374  push    80000000h; cRow
0x10032379  mov     eax, [ebp+var_24]
0x1003237c  mov     eax, [eax+8]
0x1003237f  mov     ecx, [eax+6Ch]
0x10032382  mov     eax, [eax+38h]
0x10032385  push    ecx; tableid
0x10032386  push    dword ptr [eax+10h]; sesid
0x10032389  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1003238f  cmp     eax, 0FFFFF9BDh
0x10032394  jz      short loc_100323A6
0x10032396  test    eax, eax
0x10032398  jz      short loc_1003240B
0x1003239a  js      short loc_1003240B
0x1003239c  mov     edi, 80004005h
0x100323a1  jmp     loc_10032482
0x100323a6  mov     edi, 40EC6h
0x100323ab  jmp     loc_10032482
0x100323b0  jns     short loc_100323D9
0x100323b2  mov     edi, 40EC6h
0x100323b7  jmp     loc_100324DF
0x100323bc  cmp     eax, ecx
0x100323be  jnz     short loc_100323D9
0x100323c0  test    ebx, ebx
0x100323c2  jle     short loc_100323CE
0x100323c4  mov     edi, 40EC6h
0x100323c9  jmp     loc_100324DF
0x100323ce  jns     short loc_100323D9
0x100323d0  push    0
0x100323d2  push    7FFFFFFFh
0x100323d7  jmp     short loc_10032379
0x100323d9  mov     [ebp+precpos.centriesTotal], eax
0x100323dc  lea     edx, [ebp+precpos]
0x100323df  mov     eax, [ebp+var_24]
0x100323e2  mov     [ebp+precpos.cbStruct], 10h
0x100323e9  mov     [ebp+precpos.centriesLT], ecx
0x100323ec  push    edx; precpos
0x100323ed  mov     eax, [eax+8]
0x100323f0  mov     ecx, [eax+6Ch]
0x100323f3  mov     eax, [eax+38h]
0x100323f6  push    ecx; tableid
0x100323f7  push    dword ptr [eax+10h]; sesid
0x100323fa  call    ds:__imp__JetGotoPosition@12; JetGotoPosition(x,x,x)
0x10032400  cmp     eax, 0FFFFF9BDh
0x10032405  jz      short loc_1003246E
0x10032407  test    eax, eax
0x10032409  jnz     short loc_10032479
0x1003240b  mov     eax, [ebp+var_24]
0x1003240e  lea     edx, [ebp+pcbActual]
0x10032411  push    edx; pcbActual
0x10032412  push    4; cbMax
0x10032414  lea     edx, [ebp+pvBookmark]
0x10032417  mov     eax, [eax+8]
0x1003241a  push    edx; pvBookmark
0x1003241b  mov     ecx, [eax+6Ch]
0x1003241e  mov     eax, [eax+38h]
0x10032421  push    ecx; tableid
0x10032422  push    dword ptr [eax+10h]; sesid
0x10032425  call    ds:__imp__JetGetBookmark@20; JetGetBookmark(x,x,x,x,x)
0x1003242b  cmp     eax, 0FFFFF9BDh
0x10032430  jz      loc_100323A6
0x10032436  test    eax, eax
0x10032438  jnz     loc_1003239C
0x1003243e  push    [ebp+var_28]
0x10032441  mov     ecx, [ebp+var_24]
0x10032444  push    [ebp+var_2C]
0x10032447  push    ebx
0x10032448  mov     eax, [ecx]
0x1003244a  push    0
0x1003244c  mov     edi, [eax+24h]
0x1003244f  lea     eax, [ebp+pvBookmark]
0x10032452  push    eax
0x10032453  push    4
0x10032455  push    [ebp+arg_8]
0x10032458  push    [ebp+arg_4]
0x1003245b  push    ecx
0x1003245c  mov     ecx, edi
0x1003245e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10032464  call    edi
0x10032466  mov     edi, eax
0x10032468  test    edi, edi
0x1003246a  jns     short loc_100324DF
0x1003246c  jmp     short loc_100324A9
0x1003246e  test    ebx, ebx
0x10032470  jnz     short loc_10032479
0x10032472  mov     eax, [ebp+var_28]
0x10032475  mov     [eax], ebx
0x10032477  jmp     short loc_100324DF
0x10032479  mov     edi, 80004005h
0x1003247e  test    eax, eax
0x10032480  jz      short loc_100324A9
0x10032482  push    offset _IID_IRowsetScroll; int
0x10032487  push    eax; unsigned int
0x10032488  mov     eax, [ebp+var_24]
0x1003248b  mov     edx, edi
0x1003248d  mov     eax, [eax+8]
0x10032490  mov     ecx, [eax+38h]
0x10032493  mov     ecx, [ecx+10h]
0x10032496  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1003249b  jmp     short loc_100324DF
0x1003249d  mov     edi, 80040E12h
0x100324a2  jmp     short loc_100324A9
0x100324a4  mov     edi, 80070057h
0x100324a9  mov     eax, [ebp+var_24]
0x100324ac  mov     eax, [eax+8]
0x100324af  mov     eax, [eax+38h]
0x100324b2  cmp     edi, 8007000Eh
0x100324b8  jz      short loc_100324DF
0x100324ba  push    3
0x100324bc  push    4
0x100324be  lea     ecx, [ebp+var_2C]
0x100324c1  push    ecx
0x100324c2  push    dword ptr [eax+14h]
0x100324c5  push    dword ptr [eax+10h]
0x100324c8  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100324ce  test    eax, eax
0x100324d0  jnz     short loc_100324DF
0x100324d2  push    eax; int
0x100324d3  push    offset _IID_IRowsetScroll; int
0x100324d8  mov     edx, edi
0x100324da  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100324df  test    esi, esi
0x100324e1  jz      short loc_100324EA
0x100324e3  push    esi; lpCriticalSection
0x100324e4  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100324ea  mov     eax, edi
0x100324ec  mov     ecx, [ebp+var_C]
0x100324ef  mov     large fs:0, ecx
0x100324f6  pop     ecx
0x100324f7  pop     edi
0x100324f8  pop     esi
0x100324f9  pop     ebx
0x100324fa  mov     ecx, [ebp+var_10]
0x100324fd  xor     ecx, ebp; StackCookie
0x100324ff  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032504  mov     esp, ebp
0x10032506  pop     ebp
0x10032507  retn    20h ; ' '
0x1004ecf0  lea     ecx, [ebp+var_30]; this
0x1004ecf3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004ecfd  nop
0x1004ecfe  nop
0x1004ecff  mov     edx, [esp-4+arg_4]
0x1004ed03  lea     eax, [edx+0Ch]
0x1004ed06  mov     ecx, [edx-3Ch]
0x1004ed09  xor     ecx, eax; StackCookie
0x1004ed0b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ed10  mov     ecx, [edx-4]
0x1004ed13  xor     ecx, eax; StackCookie
0x1004ed15  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ed1a  mov     eax, offset stru_1004FEFC
0x1004ed1f  jmp     ___CxxFrameHandler3
```
