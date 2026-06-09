# CImpIRowsetUpdate::Undo(ulong,ulong,ulong const * const,ulong *,ulong * *,ulong * *)

- ea: `0x100336f0`
- end: `0x10033896`
- name: `?Undo@CImpIRowsetUpdate@@UAGJKKQBKPAKPAPAK2@Z`
- size: `422`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, const unsigned int *const, unsigned int *, unsigned int **, unsigned int **)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x10027a40`
- `0x100336f0`
- `0x100338a0`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1003387a`
- `KERNEL32!LeaveCriticalSection` at `0x1003387a`
- `KERNEL32!EnterCriticalSection` at `0x100337bc`
- `KERNEL32!EnterCriticalSection` at `0x100337bc`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1003371e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1003371e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10033814`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10033814`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::Undo(
        struct _RTL_CRITICAL_SECTION **this,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int **a6,
        unsigned int **a7)
{
  int v7; // edi
  struct _RTL_CRITICAL_SECTION *v8; // esi
  unsigned int **v9; // ebx
  CImpIRowsetUpdate *v10; // ecx
  struct _RTL_CRITICAL_SECTION *v11; // edx
  HANDLE LockSemaphore; // eax
  bool v13; // zf
  int isZombie; // eax
  unsigned int *v15; // edx
  unsigned int v16; // ecx
  int v17; // eax
  const struct _GUID *v19; // [esp+0h] [ebp-28h]
  int v20; // [esp+4h] [ebp-24h]
  CTransactionState *v21; // [esp+14h] [ebp-14h] BYREF
  unsigned int **v22; // [esp+18h] [ebp-10h]
  int v23; // [esp+24h] [ebp-4h]

  v7 = 0;
  SetErrorInfo(0, 0);
  v8 = 0;
  v23 = 0;
  if ( a5 )
  {
    v9 = a6;
    *a5 = 0;
    if ( a6 )
      *a6 = 0;
  }
  else
  {
    v9 = 0;
    if ( !a3 )
    {
      v22 = 0;
      goto LABEL_6;
    }
  }
  v22 = a7;
  if ( a7 )
    *a7 = 0;
LABEL_6:
  v10 = (CImpIRowsetUpdate *)this;
  v11 = this[2];
  LockSemaphore = v11[2].LockSemaphore;
  if ( LockSemaphore
    && (*((_DWORD *)LockSemaphore + 4) != 1
     || (v13 = *((_DWORD *)LockSemaphore + 2) == 0,
         v21 = (CTransactionState *)*((_DWORD *)LockSemaphore + 2),
         v11 = this[2],
         v13)
      ? (CImpIRowsetUpdate *)(isZombie = *((_DWORD *)LockSemaphore + 3))
      : (isZombie = CTransactionState::isZombie(v21), v10 = (CImpIRowsetUpdate *)this),
        isZombie == 1)
    || !v11[4].SpinCount && !v11[9].SpinCount )
  {
    v7 = -2147418113;
    goto LABEL_26;
  }
  if ( ((int)v11[4].DebugInfo & 0x400) != 0 )
  {
    v7 = -2147217888;
    goto LABEL_26;
  }
  v8 = v11 + 3;
  EnterCriticalSection(v11 + 3);
  v10 = (CImpIRowsetUpdate *)this;
  v21 = (CTransactionState *)this[2];
  if ( !*((_DWORD *)v21 + 59) )
  {
    v7 = -2147418113;
    goto LABEL_26;
  }
  if ( !a4 && a3 || a5 && !v9 )
  {
    v7 = -2147024809;
LABEL_26:
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v10 + 2) + 56) + 16),
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v10 + 2) + 56) + 20),
            &v21,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(v7, (__int128 *)&IID_IRowsetUpdate, 0, v19, v20);
    goto LABEL_33;
  }
  if ( a3 )
  {
    v17 = CImpIRowsetUpdate::InternalUndo((CImpIRowsetUpdate *)this, (unsigned int)this, a3, a4, a5, v9, v22, 0);
  }
  else
  {
    if ( !CPendingChange::IsPending((CTransactionState *)((char *)v21 + 220)) )
      goto LABEL_33;
    v21 = (CTransactionState *)*((_DWORD *)v21 + 56);
    v17 = CImpIRowsetUpdate::InternalUndo(
            (CImpIRowsetUpdate *)this,
            v16,
            1u,
            (const unsigned int *)&v21,
            v15,
            v9,
            v22,
            1);
  }
  v7 = v17;
LABEL_33:
  if ( v8 )
    LeaveCriticalSection(v8);
  return v7;
}

```

## disassembly

```asm
0x100336f0  mov     edi, edi
0x100336f2  push    ebp
0x100336f3  mov     ebp, esp
0x100336f5  push    0FFFFFFFFh
0x100336f7  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x100336fc  mov     eax, large fs:0
0x10033702  push    eax
0x10033703  sub     esp, 0Ch
0x10033706  push    ebx
0x10033707  push    esi
0x10033708  push    edi; int
0x10033709  mov     eax, ___security_cookie
0x1003370e  xor     eax, ebp
0x10033710  push    eax; struct _GUID *
0x10033711  lea     eax, [ebp+var_C]
0x10033714  mov     large fs:0, eax
0x1003371a  xor     edi, edi
0x1003371c  push    edi; perrinfo
0x1003371d  push    edi; dwReserved
0x1003371e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10033724  xor     esi, esi
0x10033726  mov     [ebp+var_18], esi
0x10033729  mov     eax, [ebp+arg_10]
0x1003372c  mov     [ebp+var_4], esi
0x1003372f  test    eax, eax
0x10033731  jz      short loc_1003377B
0x10033733  mov     ebx, [ebp+arg_14]
0x10033736  mov     [eax], esi
0x10033738  test    ebx, ebx
0x1003373a  jz      short loc_1003373E
0x1003373c  mov     [ebx], esi
0x1003373e  mov     eax, [ebp+arg_18]
0x10033741  mov     [ebp+var_10], eax
0x10033744  test    eax, eax
0x10033746  jz      short loc_1003374E
0x10033748  mov     dword ptr [eax], 0
0x1003374e  mov     ecx, [ebp+this]
0x10033751  mov     edx, [ecx+8]
0x10033754  mov     eax, [edx+40h]
0x10033757  test    eax, eax
0x10033759  jz      short loc_1003378F
0x1003375b  cmp     dword ptr [eax+10h], 1
0x1003375f  jnz     short loc_10033787
0x10033761  mov     edx, [eax+8]
0x10033764  test    edx, edx
0x10033766  mov     [ebp+var_14], edx
0x10033769  mov     edx, [ecx+8]
0x1003376c  jz      short loc_10033787
0x1003376e  mov     ecx, [ebp+var_14]; this
0x10033771  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10033776  mov     ecx, [ebp+this]
0x10033779  jmp     short loc_1003378A
0x1003377b  xor     ebx, ebx
0x1003377d  cmp     [ebp+arg_8], ebx
0x10033780  jnz     short loc_1003373E
0x10033782  mov     [ebp+var_10], ebx
0x10033785  jmp     short loc_1003374E
0x10033787  mov     eax, [eax+0Ch]
0x1003378a  cmp     eax, 1
0x1003378d  jz      short loc_1003379E
0x1003378f  cmp     dword ptr [edx+74h], 0
0x10033793  jnz     short loc_100337A5
0x10033795  cmp     dword ptr [edx+0ECh], 0
0x1003379c  jnz     short loc_100337A5
0x1003379e  mov     edi, 8000FFFFh
0x100337a3  jmp     short loc_100337F8
0x100337a5  test    dword ptr [edx+60h], 400h
0x100337ac  jz      short loc_100337B5
0x100337ae  mov     edi, 80040E20h
0x100337b3  jmp     short loc_100337F8
0x100337b5  lea     esi, [edx+48h]
0x100337b8  push    esi; lpCriticalSection
0x100337b9  mov     [ebp+var_18], esi
0x100337bc  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100337c2  mov     ecx, [ebp+this]; this
0x100337c5  mov     eax, [ecx+8]
0x100337c8  mov     [ebp+var_14], eax
0x100337cb  cmp     dword ptr [eax+0ECh], 0
0x100337d2  jnz     short loc_100337DB
0x100337d4  mov     edi, 8000FFFFh
0x100337d9  jmp     short loc_100337F8
0x100337db  cmp     [ebp+arg_C], 0
0x100337df  mov     eax, [ebp+arg_8]
0x100337e2  jnz     short loc_100337E8
0x100337e4  test    eax, eax
0x100337e6  jnz     short loc_100337F3
0x100337e8  mov     edx, [ebp+arg_10]
0x100337eb  test    edx, edx
0x100337ed  jz      short loc_1003382D
0x100337ef  test    ebx, ebx
0x100337f1  jnz     short loc_1003382D
0x100337f3  mov     edi, 80070057h
0x100337f8  mov     eax, [ecx+8]
0x100337fb  mov     eax, [eax+38h]
0x100337fe  cmp     edi, 8007000Eh
0x10033804  jz      short loc_10033875
0x10033806  push    3
0x10033808  push    4
0x1003380a  lea     ecx, [ebp+var_14]
0x1003380d  push    ecx
0x1003380e  push    dword ptr [eax+14h]
0x10033811  push    dword ptr [eax+10h]
0x10033814  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1003381a  test    eax, eax
0x1003381c  jnz     short loc_10033875
0x1003381e  push    eax; int
0x1003381f  push    offset _IID_IRowsetUpdate; int
0x10033824  mov     edx, edi
0x10033826  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1003382b  jmp     short loc_10033875
0x1003382d  test    eax, eax
0x1003382f  jnz     short loc_10033862
0x10033831  mov     ecx, [ebp+var_14]
0x10033834  add     ecx, 0DCh; this
0x1003383a  call    ?IsPending@CPendingChange@@QBEHXZ; CPendingChange::IsPending(void)
0x1003383f  test    eax, eax
0x10033841  jz      short loc_10033875
0x10033843  mov     eax, [ebp+var_14]
0x10033846  push    1
0x10033848  push    [ebp+var_10]
0x1003384b  mov     eax, [eax+0E0h]
0x10033851  push    ebx
0x10033852  push    edx
0x10033853  mov     [ebp+var_14], eax
0x10033856  lea     eax, [ebp+var_14]
0x10033859  push    eax
0x1003385a  push    1
0x1003385c  push    ecx
0x1003385d  mov     ecx, [ebp+this]
0x10033860  jmp     short loc_1003386E
0x10033862  push    0; int
0x10033864  push    [ebp+var_10]; unsigned int **
0x10033867  push    ebx; unsigned int **
0x10033868  push    edx; unsigned int *
0x10033869  push    [ebp+arg_C]; unsigned int *
0x1003386c  push    eax; unsigned int
0x1003386d  push    ecx; unsigned int
0x1003386e  call    ?InternalUndo@CImpIRowsetUpdate@@AAEJKKQBKPAKPAPAK2H@Z; CImpIRowsetUpdate::InternalUndo(ulong,ulong,ulong const * const,ulong *,ulong * *,ulong * *,int)
0x10033873  mov     edi, eax
0x10033875  test    esi, esi
0x10033877  jz      short loc_10033880
0x10033879  push    esi; lpCriticalSection
0x1003387a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10033880  mov     eax, edi
0x10033882  mov     ecx, [ebp+var_C]
0x10033885  mov     large fs:0, ecx
0x1003388c  pop     ecx
0x1003388d  pop     edi
0x1003388e  pop     esi
0x1003388f  pop     ebx
0x10033890  mov     esp, ebp
0x10033892  pop     ebp
0x10033893  retn    1Ch
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
