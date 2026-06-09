# CImpIDBUserAttributes::DeleteAttribute(tagDBID *,tagDBID *,tagDBID *,tagDBID *)

- ea: `0x1000d8e0`
- end: `0x1000da35`
- name: `?DeleteAttribute@CImpIDBUserAttributes@@UAGJPAUtagDBID@@000@Z`
- size: `341`
- prototype: `int(CImpIDBUserAttributes *__hidden this, struct tagDBID *, struct tagDBID *, struct tagDBID *, struct tagDBID *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000d8e0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000da19`
- `KERNEL32!LeaveCriticalSection` at `0x1000da19`
- `KERNEL32!EnterCriticalSection` at `0x1000d921`
- `KERNEL32!EnterCriticalSection` at `0x1000d921`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d90e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d90e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d9fd`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d9fd`
- `msjet40!__imp__JetSetProperty@40` at `0x1000d9aa`
- `msjet40!__imp__JetSetProperty@40` at `0x1000d9aa`

## pseudocode

```c
int __stdcall CImpIDBUserAttributes::DeleteAttribute(
        CImpIDBUserAttributes *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        struct tagDBID *a4,
        struct tagDBID *a5)
{
  int v5; // edi
  struct _RTL_CRITICAL_SECTION *v6; // esi
  LPOLESTR pwszName; // ecx
  unsigned int v8; // eax
  const struct _GUID *v10; // [esp+0h] [ebp-24h]
  const struct _GUID *v11; // [esp+4h] [ebp-20h]
  _DWORD v12[4]; // [esp+14h] [ebp-10h] BYREF

  v5 = 0;
  SetErrorInfo(0, 0);
  v6 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v6);
  v12[3] = 0;
  if ( !a2 || !a3 || a2->eKind != 2 || a3->eKind != 2 || a4 && a4->eKind != 2 )
    goto LABEL_20;
  if ( !a5 )
  {
    v12[0] = 0;
    goto LABEL_11;
  }
  if ( a5->eKind != 2 )
  {
LABEL_20:
    v5 = -2147024809;
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*((_DWORD *)this + 2) + 16),
            *(_DWORD *)(*((_DWORD *)this + 2) + 20),
            v12,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(-2147024809, (__int128 *)&IID_IDBUserAttributes, 0, v10, (int)v11);
    goto LABEL_23;
  }
  v12[0] = a5->uName.pwszName;
LABEL_11:
  if ( a4 )
    pwszName = a4->uName.pwszName;
  else
    pwszName = 0;
  v8 = JetSetProperty(
         *(_DWORD *)(*((_DWORD *)this + 2) + 16),
         *(_DWORD *)(*((_DWORD *)this + 2) + 20),
         a2->uName.ulPropid,
         a3->uName.ulPropid,
         pwszName,
         v12[0],
         0,
         0,
         1,
         64);
  if ( v8 == -8114 || v8 == -1809 )
  {
    v5 = -2147217911;
  }
  else
  {
    if ( !v8 )
      goto LABEL_23;
    v5 = -2147467259;
  }
  CExtError::SendJetErrortoOLEAuto(
    v5,
    *(char **)(*((_DWORD *)this + 2) + 16),
    v8,
    (int)&IID_IDBUserAttributes,
    (int)v10,
    v11);
LABEL_23:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v5;
}

```

## disassembly

```asm
0x1000d8e0  mov     edi, edi
0x1000d8e2  push    ebp
0x1000d8e3  mov     ebp, esp
0x1000d8e5  push    0FFFFFFFFh
0x1000d8e7  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x1000d8ec  mov     eax, large fs:0
0x1000d8f2  push    eax
0x1000d8f3  sub     esp, 8
0x1000d8f6  push    ebx
0x1000d8f7  push    esi
0x1000d8f8  push    edi; int
0x1000d8f9  mov     eax, ___security_cookie
0x1000d8fe  xor     eax, ebp
0x1000d900  push    eax; struct _GUID *
0x1000d901  lea     eax, [ebp+var_C]
0x1000d904  mov     large fs:0, eax
0x1000d90a  xor     edi, edi
0x1000d90c  push    edi; perrinfo
0x1000d90d  push    edi; dwReserved
0x1000d90e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000d914  mov     ebx, [ebp+this]
0x1000d917  mov     esi, [ebx+8]
0x1000d91a  add     esi, 68h ; 'h'
0x1000d91d  push    esi; lpCriticalSection
0x1000d91e  mov     [ebp+var_14], esi
0x1000d921  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000d927  mov     eax, [ebp+arg_4]
0x1000d92a  mov     [ebp+var_4], edi
0x1000d92d  test    eax, eax
0x1000d92f  jz      loc_1000D9E7
0x1000d935  mov     edx, [ebp+arg_8]
0x1000d938  test    edx, edx
0x1000d93a  jz      loc_1000D9E7
0x1000d940  cmp     dword ptr [eax+10h], 2
0x1000d944  jnz     loc_1000D9E7
0x1000d94a  cmp     dword ptr [edx+10h], 2
0x1000d94e  jnz     loc_1000D9E7
0x1000d954  mov     eax, [ebp+arg_C]
0x1000d957  test    eax, eax
0x1000d959  jz      short loc_1000D965
0x1000d95b  cmp     dword ptr [eax+10h], 2
0x1000d95f  jnz     loc_1000D9E7
0x1000d965  mov     ecx, [ebp+arg_10]
0x1000d968  test    ecx, ecx
0x1000d96a  jz      short loc_1000D97A
0x1000d96c  cmp     dword ptr [ecx+10h], 2
0x1000d970  jnz     short loc_1000D9E7
0x1000d972  mov     ecx, [ecx+14h]
0x1000d975  mov     [ebp+var_10], ecx
0x1000d978  jmp     short loc_1000D981
0x1000d97a  mov     [ebp+var_10], 0
0x1000d981  test    eax, eax
0x1000d983  jz      short loc_1000D98A
0x1000d985  mov     ecx, [eax+14h]
0x1000d988  jmp     short loc_1000D98C
0x1000d98a  xor     ecx, ecx
0x1000d98c  mov     eax, [ebx+8]
0x1000d98f  push    40h ; '@'
0x1000d991  push    1
0x1000d993  push    0
0x1000d995  push    0
0x1000d997  push    [ebp+var_10]
0x1000d99a  push    ecx
0x1000d99b  push    dword ptr [edx+14h]
0x1000d99e  mov     ecx, [ebp+arg_4]
0x1000d9a1  push    dword ptr [ecx+14h]
0x1000d9a4  push    dword ptr [eax+14h]
0x1000d9a7  push    dword ptr [eax+10h]
0x1000d9aa  call    ds:__imp__JetSetProperty@40; JetSetProperty(x,x,x,x,x,x,x,x,x,x)
0x1000d9b0  cmp     eax, 0FFFFE04Eh
0x1000d9b5  jz      short loc_1000D9C9
0x1000d9b7  cmp     eax, 0FFFFF8EFh
0x1000d9bc  jz      short loc_1000D9C9
0x1000d9be  test    eax, eax
0x1000d9c0  jz      short loc_1000DA14
0x1000d9c2  mov     edi, 80004005h
0x1000d9c7  jmp     short loc_1000D9D2
0x1000d9c9  mov     edi, 80040E09h
0x1000d9ce  test    eax, eax
0x1000d9d0  jz      short loc_1000D9EC
0x1000d9d2  mov     ecx, [ebx+8]
0x1000d9d5  mov     edx, edi
0x1000d9d7  push    offset _IID_IDBUserAttributes; int
0x1000d9dc  push    eax; unsigned int
0x1000d9dd  mov     ecx, [ecx+10h]
0x1000d9e0  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1000d9e5  jmp     short loc_1000DA14
0x1000d9e7  mov     edi, 80070057h
0x1000d9ec  mov     eax, [ebx+8]
0x1000d9ef  lea     ecx, [ebp+var_10]
0x1000d9f2  push    3
0x1000d9f4  push    4
0x1000d9f6  push    ecx
0x1000d9f7  push    dword ptr [eax+14h]
0x1000d9fa  push    dword ptr [eax+10h]
0x1000d9fd  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000da03  test    eax, eax
0x1000da05  jnz     short loc_1000DA14
0x1000da07  push    eax; int
0x1000da08  push    offset _IID_IDBUserAttributes; int
0x1000da0d  mov     edx, edi
0x1000da0f  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000da14  test    esi, esi
0x1000da16  jz      short loc_1000DA1F
0x1000da18  push    esi; lpCriticalSection
0x1000da19  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000da1f  mov     eax, edi
0x1000da21  mov     ecx, [ebp+var_C]
0x1000da24  mov     large fs:0, ecx
0x1000da2b  pop     ecx
0x1000da2c  pop     edi
0x1000da2d  pop     esi
0x1000da2e  pop     ebx
0x1000da2f  mov     esp, ebp
0x1000da31  pop     ebp
0x1000da32  retn    14h
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
