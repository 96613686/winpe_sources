# CImpITransactionLocal::Abort(BOID *,int,int)

- ea: `0x10049030`
- end: `0x1004914f`
- name: `?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z`
- size: `287`
- prototype: `int(CImpITransactionLocal *__hidden this, struct BOID *, int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x10016c40`
- `0x10016d50`
- `0x1001bdc0`
- `0x1001c380`
- `0x10049030`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10049133`
- `KERNEL32!LeaveCriticalSection` at `0x10049133`
- `KERNEL32!EnterCriticalSection` at `0x10049071`
- `KERNEL32!EnterCriticalSection` at `0x10049071`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004905e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004905e`
- `msjet40!__imp__JetBeginTransaction@4` at `0x100490ef`
- `msjet40!__imp__JetBeginTransaction@4` at `0x100490ef`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10049096`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10049096`
- `msjet40!__imp__JetRollback@8` at `0x100490b8`
- `msjet40!__imp__JetRollback@8` at `0x100490b8`

## pseudocode

```c
int __stdcall CImpITransactionLocal::Abort(CImpITransactionLocal *this, struct BOID *a2, int a3, int a4)
{
  int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // esi
  int v6; // eax
  JET_ERR v7; // eax
  CDBSession *v8; // ecx
  const struct _GUID *v10; // [esp+0h] [ebp-24h]
  const struct _GUID *v11; // [esp+4h] [ebp-20h]
  _DWORD v12[4]; // [esp+14h] [ebp-10h] BYREF

  v4 = 0;
  SetErrorInfo(0, 0);
  v5 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v5);
  v12[3] = 0;
  v6 = *((_DWORD *)this + 2);
  if ( a4 == 1 )
  {
    v4 = -2147168247;
    if ( !JetGetDatabaseInfo(*(_DWORD *)(v6 + 16), *(_DWORD *)(v6 + 20), v12, 4, 3) )
      CExtError::SendHRtoOLEAuto(-2147168247, (__int128 *)&IID_ITransactionLocal, 0, v10, (int)v11);
  }
  else
  {
    v7 = JetRollback(*(_DWORD *)(v6 + 16), 0);
    if ( v7 == -1054 )
    {
      v4 = -2147168242;
    }
    else if ( v7 )
    {
      v4 = -2147467259;
    }
    else
    {
      v8 = (CDBSession *)*((_DWORD *)this + 2);
      v12[0] = *(_DWORD *)(*((_DWORD *)v8 + 22) + 24);
      CDBSession::popTransactionState(v8, 1);
      if ( a3 != 1 )
        goto LABEL_13;
      v7 = JetBeginTransaction(*(_DWORD *)(*((_DWORD *)this + 2) + 16));
      if ( !v7 )
      {
        CDBSession::pushTransactionState(*((CDBSession **)this + 2));
        *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 88) + 24) = v12[0];
        goto LABEL_13;
      }
      v4 = -2147418113;
    }
    CExtError::SendJetErrortoOLEAuto(
      v4,
      *(char **)(*((_DWORD *)this + 2) + 16),
      v7,
      (int)&IID_ITransactionLocal,
      (int)v10,
      v11);
  }
LABEL_13:
  if ( v5 )
    LeaveCriticalSection(v5);
  return v4;
}

```

## disassembly

```asm
0x10049030  mov     edi, edi
0x10049032  push    ebp
0x10049033  mov     ebp, esp
0x10049035  push    0FFFFFFFFh
0x10049037  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x1004903c  mov     eax, large fs:0
0x10049042  push    eax
0x10049043  sub     esp, 8
0x10049046  push    ebx
0x10049047  push    esi
0x10049048  push    edi; struct _GUID *
0x10049049  mov     eax, ___security_cookie
0x1004904e  xor     eax, ebp
0x10049050  push    eax; int
0x10049051  lea     eax, [ebp+var_C]
0x10049054  mov     large fs:0, eax
0x1004905a  xor     edi, edi
0x1004905c  push    edi; perrinfo
0x1004905d  push    edi; dwReserved
0x1004905e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10049064  mov     ebx, [ebp+this]
0x10049067  mov     esi, [ebx+8]
0x1004906a  add     esi, 68h ; 'h'
0x1004906d  push    esi; lpCriticalSection
0x1004906e  mov     [ebp+var_14], esi
0x10049071  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10049077  cmp     [ebp+arg_C], 1
0x1004907b  mov     [ebp+var_4], edi
0x1004907e  mov     eax, [ebx+8]
0x10049081  jnz     short loc_100490B3
0x10049083  push    3
0x10049085  push    4
0x10049087  lea     ecx, [ebp+var_10]
0x1004908a  mov     edi, 8004D009h
0x1004908f  push    ecx
0x10049090  push    dword ptr [eax+14h]
0x10049093  push    dword ptr [eax+10h]
0x10049096  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1004909c  test    eax, eax
0x1004909e  jnz     loc_1004912E
0x100490a4  push    eax; int
0x100490a5  push    offset _IID_ITransactionLocal; int
0x100490aa  mov     edx, edi
0x100490ac  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100490b1  jmp     short loc_1004912E
0x100490b3  push    0; grbit
0x100490b5  push    dword ptr [eax+10h]; sesid
0x100490b8  call    ds:__imp__JetRollback@8; JetRollback(x,x)
0x100490be  cmp     eax, 0FFFFFBE2h
0x100490c3  jz      short loc_10049116
0x100490c5  test    eax, eax
0x100490c7  jz      short loc_100490D0
0x100490c9  mov     edi, 80004005h
0x100490ce  jmp     short loc_1004911B
0x100490d0  mov     ecx, [ebx+8]; this
0x100490d3  push    1; int
0x100490d5  mov     eax, [ecx+58h]
0x100490d8  mov     eax, [eax+18h]
0x100490db  mov     [ebp+var_10], eax
0x100490de  call    ?popTransactionState@CDBSession@@QAEJH@Z; CDBSession::popTransactionState(int)
0x100490e3  cmp     [ebp+arg_8], 1
0x100490e7  jnz     short loc_1004912E
0x100490e9  mov     eax, [ebx+8]
0x100490ec  push    dword ptr [eax+10h]; sesid
0x100490ef  call    ds:__imp__JetBeginTransaction@4; JetBeginTransaction(x)
0x100490f5  test    eax, eax
0x100490f7  jz      short loc_10049100
0x100490f9  mov     edi, 8000FFFFh
0x100490fe  jmp     short loc_1004911B
0x10049100  mov     ecx, [ebx+8]; this
0x10049103  call    ?pushTransactionState@CDBSession@@QAEJXZ; CDBSession::pushTransactionState(void)
0x10049108  mov     eax, [ebx+8]
0x1004910b  mov     ecx, [ebp+var_10]
0x1004910e  mov     eax, [eax+58h]
0x10049111  mov     [eax+18h], ecx
0x10049114  jmp     short loc_1004912E
0x10049116  mov     edi, 8004D00Eh
0x1004911b  mov     ecx, [ebx+8]
0x1004911e  mov     edx, edi
0x10049120  push    offset _IID_ITransactionLocal; int
0x10049125  push    eax; unsigned int
0x10049126  mov     ecx, [ecx+10h]
0x10049129  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1004912e  test    esi, esi
0x10049130  jz      short loc_10049139
0x10049132  push    esi; lpCriticalSection
0x10049133  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10049139  mov     eax, edi
0x1004913b  mov     ecx, [ebp+var_C]
0x1004913e  mov     large fs:0, ecx
0x10049145  pop     ecx
0x10049146  pop     edi
0x10049147  pop     esi
0x10049148  pop     ebx
0x10049149  mov     esp, ebp
0x1004914b  pop     ebp
0x1004914c  retn    10h
0x1004dde0  lea     ecx, [ebp+var_14]; this
0x1004dde3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dded  nop
0x1004ddee  nop
0x1004ddef  mov     edx, [esp-4+arg_4]
0x1004ddf3  lea     eax, [edx+0Ch]
0x1004ddf6  mov     ecx, [edx-18h]
0x1004ddf9  xor     ecx, eax; StackCookie
0x1004ddfb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004de00  mov     eax, offset stru_1004F3D8
0x1004de05  jmp     ___CxxFrameHandler3
```
