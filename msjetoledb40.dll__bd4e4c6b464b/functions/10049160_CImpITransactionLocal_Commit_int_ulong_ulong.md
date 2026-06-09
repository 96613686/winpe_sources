# CImpITransactionLocal::Commit(int,ulong,ulong)

- ea: `0x10049160`
- end: `0x10049284`
- name: `?Commit@CImpITransactionLocal@@UAGJHKK@Z`
- size: `292`
- prototype: `int(CImpITransactionLocal *__hidden this, int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x10016c40`
- `0x10016d50`
- `0x1001bdc0`
- `0x1001f2d0`
- `0x10049160`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10049268`
- `KERNEL32!LeaveCriticalSection` at `0x10049268`
- `KERNEL32!EnterCriticalSection` at `0x100491a1`
- `KERNEL32!EnterCriticalSection` at `0x100491a1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004918e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004918e`
- `msjet40!__imp__JetBeginTransaction@4` at `0x10049224`
- `msjet40!__imp__JetBeginTransaction@4` at `0x10049224`
- `msjet40!__imp__JetCommitTransaction@8` at `0x100491ed`
- `msjet40!__imp__JetCommitTransaction@8` at `0x100491ed`

## pseudocode

```c
int __stdcall CImpITransactionLocal::Commit(CImpITransactionLocal *this, int a2, unsigned int a3, unsigned int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  JoltProperties *v5; // edi
  unsigned int v6; // eax
  int v7; // edi
  JET_ERR v8; // eax
  CDBSession *v9; // ecx
  int v11; // [esp+0h] [ebp-24h]
  const struct _GUID *v12; // [esp+4h] [ebp-20h]
  unsigned int v13[4]; // [esp+14h] [ebp-10h] BYREF

  SetErrorInfo(0, 0);
  v4 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v4);
  v13[3] = 0;
  v5 = *(JoltProperties **)(*((_DWORD *)this + 2) + 148);
  if ( JoltProperties::BinarySearch(v5, 0x116u, v13) < 0 )
    v6 = 0;
  else
    v6 = *((_DWORD *)v5 + 4) + 48 * v13[0];
  v7 = 0;
  v8 = JetCommitTransaction(*(_DWORD *)(*((_DWORD *)this + 2) + 16), 8 * (*(_DWORD *)(v6 + 24) & 1));
  if ( v8 == -1054 )
  {
    v7 = -2147168242;
  }
  else if ( v8 )
  {
    v7 = -2147168254;
  }
  else
  {
    v9 = (CDBSession *)*((_DWORD *)this + 2);
    v13[0] = *(_DWORD *)(*((_DWORD *)v9 + 22) + 24);
    CDBSession::popTransactionState(v9, 0);
    if ( a2 != 1 )
      goto LABEL_13;
    v8 = JetBeginTransaction(*(_DWORD *)(*((_DWORD *)this + 2) + 16));
    if ( !v8 )
    {
      CDBSession::pushTransactionState(*((CDBSession **)this + 2));
      *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 88) + 24) = v13[0];
      goto LABEL_13;
    }
    v7 = -2147418113;
  }
  CExtError::SendJetErrortoOLEAuto(
    v7,
    *(char **)(*((_DWORD *)this + 2) + 16),
    v8,
    (int)&IID_ITransactionLocal,
    v11,
    v12);
LABEL_13:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v7;
}

```

## disassembly

```asm
0x10049160  mov     edi, edi
0x10049162  push    ebp
0x10049163  mov     ebp, esp
0x10049165  push    0FFFFFFFFh
0x10049167  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x1004916c  mov     eax, large fs:0
0x10049172  push    eax
0x10049173  sub     esp, 8
0x10049176  push    ebx
0x10049177  push    esi
0x10049178  push    edi; struct _GUID *
0x10049179  mov     eax, ___security_cookie
0x1004917e  xor     eax, ebp
0x10049180  push    eax; int
0x10049181  lea     eax, [ebp+var_C]
0x10049184  mov     large fs:0, eax
0x1004918a  push    0; perrinfo
0x1004918c  push    0; dwReserved
0x1004918e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10049194  mov     ebx, [ebp+this]
0x10049197  mov     esi, [ebx+8]
0x1004919a  add     esi, 68h ; 'h'
0x1004919d  push    esi; lpCriticalSection
0x1004919e  mov     [ebp+var_14], esi
0x100491a1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100491a7  mov     [ebp+var_4], 0
0x100491ae  mov     eax, [ebx+8]
0x100491b1  mov     edi, [eax+94h]
0x100491b7  lea     eax, [ebp+var_10]
0x100491ba  push    eax; unsigned int *
0x100491bb  push    116h; unsigned int
0x100491c0  mov     ecx, edi; this
0x100491c2  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x100491c7  test    eax, eax
0x100491c9  js      short loc_100491D9
0x100491cb  mov     eax, [ebp+var_10]
0x100491ce  lea     eax, [eax+eax*2]
0x100491d1  shl     eax, 4
0x100491d4  add     eax, [edi+10h]
0x100491d7  jmp     short loc_100491DB
0x100491d9  xor     eax, eax
0x100491db  mov     eax, [eax+18h]
0x100491de  xor     edi, edi
0x100491e0  and     eax, 1
0x100491e3  shl     eax, 3
0x100491e6  push    eax; grbit
0x100491e7  mov     eax, [ebx+8]
0x100491ea  push    dword ptr [eax+10h]; sesid
0x100491ed  call    ds:__imp__JetCommitTransaction@8; JetCommitTransaction(x,x)
0x100491f3  cmp     eax, 0FFFFFBE2h
0x100491f8  jz      short loc_1004924B
0x100491fa  test    eax, eax
0x100491fc  jz      short loc_10049205
0x100491fe  mov     edi, 8004D002h
0x10049203  jmp     short loc_10049250
0x10049205  mov     ecx, [ebx+8]; this
0x10049208  push    0; int
0x1004920a  mov     eax, [ecx+58h]
0x1004920d  mov     eax, [eax+18h]
0x10049210  mov     [ebp+var_10], eax
0x10049213  call    ?popTransactionState@CDBSession@@QAEJH@Z; CDBSession::popTransactionState(int)
0x10049218  cmp     [ebp+arg_4], 1
0x1004921c  jnz     short loc_10049263
0x1004921e  mov     eax, [ebx+8]
0x10049221  push    dword ptr [eax+10h]; sesid
0x10049224  call    ds:__imp__JetBeginTransaction@4; JetBeginTransaction(x)
0x1004922a  test    eax, eax
0x1004922c  jz      short loc_10049235
0x1004922e  mov     edi, 8000FFFFh
0x10049233  jmp     short loc_10049250
0x10049235  mov     ecx, [ebx+8]; this
0x10049238  call    ?pushTransactionState@CDBSession@@QAEJXZ; CDBSession::pushTransactionState(void)
0x1004923d  mov     eax, [ebx+8]
0x10049240  mov     ecx, [ebp+var_10]
0x10049243  mov     eax, [eax+58h]
0x10049246  mov     [eax+18h], ecx
0x10049249  jmp     short loc_10049263
0x1004924b  mov     edi, 8004D00Eh
0x10049250  mov     ecx, [ebx+8]
0x10049253  mov     edx, edi
0x10049255  push    offset _IID_ITransactionLocal; int
0x1004925a  push    eax; unsigned int
0x1004925b  mov     ecx, [ecx+10h]
0x1004925e  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10049263  test    esi, esi
0x10049265  jz      short loc_1004926E
0x10049267  push    esi; lpCriticalSection
0x10049268  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004926e  mov     eax, edi
0x10049270  mov     ecx, [ebp+var_C]
0x10049273  mov     large fs:0, ecx
0x1004927a  pop     ecx
0x1004927b  pop     edi
0x1004927c  pop     esi
0x1004927d  pop     ebx
0x1004927e  mov     esp, ebp
0x10049280  pop     ebp
0x10049281  retn    10h
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
