# CImpIDBUserAttributes::RenameObject(tagDBID *,tagDBID *,ushort *)

- ea: `0x1000d7d0`
- end: `0x1000d8d1`
- name: `?RenameObject@CImpIDBUserAttributes@@UAGJPAUtagDBID@@0PAG@Z`
- size: `257`
- prototype: `int(CImpIDBUserAttributes *__hidden this, struct tagDBID *, struct tagDBID *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000d7d0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000d8b5`
- `KERNEL32!LeaveCriticalSection` at `0x1000d8b5`
- `KERNEL32!EnterCriticalSection` at `0x1000d811`
- `KERNEL32!EnterCriticalSection` at `0x1000d811`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d7fe`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d7fe`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d899`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d899`
- `msjet40!__imp__JetRenameObject@20` at `0x1000d846`
- `msjet40!__imp__JetRenameObject@20` at `0x1000d846`

## pseudocode

```c
int __stdcall CImpIDBUserAttributes::RenameObject(
        CImpIDBUserAttributes *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        unsigned __int16 *a4)
{
  int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // esi
  unsigned int v6; // eax
  const struct _GUID *v8; // [esp+0h] [ebp-24h]
  const struct _GUID *v9; // [esp+4h] [ebp-20h]
  _BYTE v10[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v11; // [esp+14h] [ebp-10h]
  int v12; // [esp+20h] [ebp-4h]

  v4 = 0;
  SetErrorInfo(0, 0);
  v11 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 104);
  v5 = v11;
  EnterCriticalSection(v11);
  v12 = 0;
  if ( a2 && a3 && a2->eKind == 2 && a3->eKind == 2 )
  {
    v6 = JetRenameObject(
           *(_DWORD *)(*((_DWORD *)this + 2) + 16),
           *(_DWORD *)(*((_DWORD *)this + 2) + 20),
           a2->uName.ulPropid,
           a3->uName.ulPropid,
           a4);
    if ( v6 == -8114 || v6 == -1809 )
    {
      v4 = -2147217911;
    }
    else
    {
      if ( !v6 )
        goto LABEL_14;
      v4 = -2147467259;
    }
    CExtError::SendJetErrortoOLEAuto(
      v4,
      *(char **)(*((_DWORD *)this + 2) + 16),
      v6,
      (int)&IID_IDBUserAttributes,
      (int)v8,
      v9);
  }
  else
  {
    v4 = -2147024809;
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*((_DWORD *)this + 2) + 16),
            *(_DWORD *)(*((_DWORD *)this + 2) + 20),
            v10,
            4,
            3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBUserAttributes, 0, v8, (int)v9);
  }
LABEL_14:
  if ( v5 )
    LeaveCriticalSection(v5);
  return v4;
}

```

## disassembly

```asm
0x1000d7d0  mov     edi, edi
0x1000d7d2  push    ebp
0x1000d7d3  mov     ebp, esp
0x1000d7d5  push    0FFFFFFFFh
0x1000d7d7  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1000d7dc  mov     eax, large fs:0
0x1000d7e2  push    eax
0x1000d7e3  sub     esp, 8
0x1000d7e6  push    ebx
0x1000d7e7  push    esi
0x1000d7e8  push    edi; int
0x1000d7e9  mov     eax, ___security_cookie
0x1000d7ee  xor     eax, ebp
0x1000d7f0  push    eax; struct _GUID *
0x1000d7f1  lea     eax, [ebp+var_C]
0x1000d7f4  mov     large fs:0, eax
0x1000d7fa  xor     edi, edi
0x1000d7fc  push    edi; perrinfo
0x1000d7fd  push    edi; dwReserved
0x1000d7fe  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000d804  mov     ebx, [ebp+this]
0x1000d807  mov     esi, [ebx+8]
0x1000d80a  add     esi, 68h ; 'h'
0x1000d80d  push    esi; lpCriticalSection
0x1000d80e  mov     [ebp+var_10], esi
0x1000d811  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000d817  mov     edx, [ebp+arg_4]
0x1000d81a  mov     [ebp+var_4], edi
0x1000d81d  test    edx, edx
0x1000d81f  jz      short loc_1000D883
0x1000d821  mov     ecx, [ebp+arg_8]
0x1000d824  test    ecx, ecx
0x1000d826  jz      short loc_1000D883
0x1000d828  cmp     dword ptr [edx+10h], 2
0x1000d82c  jnz     short loc_1000D883
0x1000d82e  cmp     dword ptr [ecx+10h], 2
0x1000d832  jnz     short loc_1000D883
0x1000d834  push    [ebp+arg_C]
0x1000d837  mov     eax, [ebx+8]
0x1000d83a  push    dword ptr [ecx+14h]
0x1000d83d  push    dword ptr [edx+14h]
0x1000d840  push    dword ptr [eax+14h]
0x1000d843  push    dword ptr [eax+10h]
0x1000d846  call    ds:__imp__JetRenameObject@20; JetRenameObject(x,x,x,x,x)
0x1000d84c  cmp     eax, 0FFFFE04Eh
0x1000d851  jz      short loc_1000D865
0x1000d853  cmp     eax, 0FFFFF8EFh
0x1000d858  jz      short loc_1000D865
0x1000d85a  test    eax, eax
0x1000d85c  jz      short loc_1000D8B0
0x1000d85e  mov     edi, 80004005h
0x1000d863  jmp     short loc_1000D86E
0x1000d865  mov     edi, 80040E09h
0x1000d86a  test    eax, eax
0x1000d86c  jz      short loc_1000D888
0x1000d86e  mov     ecx, [ebx+8]
0x1000d871  mov     edx, edi
0x1000d873  push    offset _IID_IDBUserAttributes; int
0x1000d878  push    eax; unsigned int
0x1000d879  mov     ecx, [ecx+10h]
0x1000d87c  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1000d881  jmp     short loc_1000D8B0
0x1000d883  mov     edi, 80070057h
0x1000d888  mov     eax, [ebx+8]
0x1000d88b  lea     ecx, [ebp+var_14]
0x1000d88e  push    3
0x1000d890  push    4
0x1000d892  push    ecx
0x1000d893  push    dword ptr [eax+14h]
0x1000d896  push    dword ptr [eax+10h]
0x1000d899  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000d89f  test    eax, eax
0x1000d8a1  jnz     short loc_1000D8B0
0x1000d8a3  push    eax; int
0x1000d8a4  push    offset _IID_IDBUserAttributes; int
0x1000d8a9  mov     edx, edi
0x1000d8ab  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000d8b0  test    esi, esi
0x1000d8b2  jz      short loc_1000D8BB
0x1000d8b4  push    esi; lpCriticalSection
0x1000d8b5  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000d8bb  mov     eax, edi
0x1000d8bd  mov     ecx, [ebp+var_C]
0x1000d8c0  mov     large fs:0, ecx
0x1000d8c7  pop     ecx
0x1000d8c8  pop     edi
0x1000d8c9  pop     esi
0x1000d8ca  pop     ebx
0x1000d8cb  mov     esp, ebp
0x1000d8cd  pop     ebp
0x1000d8ce  retn    10h
0x1004ddb0  lea     ecx, [ebp+var_10]; this
0x1004ddb3  jmp     ??1CMutex@@QAE@XZ
0x1004ddbd  nop
0x1004ddbe  nop
0x1004ddbf  mov     edx, [esp-4+arg_4]
0x1004ddc3  lea     eax, [edx+0Ch]
0x1004ddc6  mov     ecx, [edx-18h]
0x1004ddc9  xor     ecx, eax; StackCookie
0x1004ddcb  call    @__security_check_cookie@4
0x1004ddd0  mov     eax, offset stru_1004F3AC
0x1004ddd5  jmp     ___CxxFrameHandler3
```
