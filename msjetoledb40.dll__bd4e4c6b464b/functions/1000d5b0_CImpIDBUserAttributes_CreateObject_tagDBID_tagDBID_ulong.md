# CImpIDBUserAttributes::CreateObject(tagDBID *,tagDBID *,ulong)

- ea: `0x1000d5b0`
- end: `0x1000d6b1`
- name: `?CreateObject@CImpIDBUserAttributes@@UAGJPAUtagDBID@@0K@Z`
- size: `257`
- prototype: `int(CImpIDBUserAttributes *__hidden this, struct tagDBID *, struct tagDBID *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000d5b0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000d695`
- `KERNEL32!LeaveCriticalSection` at `0x1000d695`
- `KERNEL32!EnterCriticalSection` at `0x1000d5f1`
- `KERNEL32!EnterCriticalSection` at `0x1000d5f1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d5de`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d5de`
- `msjet40!__imp__JetCreateObject@20` at `0x1000d626`
- `msjet40!__imp__JetCreateObject@20` at `0x1000d626`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d679`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d679`

## pseudocode

```c
int __stdcall CImpIDBUserAttributes::CreateObject(
        CImpIDBUserAttributes *this,
        struct tagDBID *a2,
        struct tagDBID *a3,
        unsigned int a4)
{
  int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // esi
  unsigned int Object; // eax
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
    Object = JetCreateObject(
               *(_DWORD *)(*((_DWORD *)this + 2) + 16),
               *(_DWORD *)(*((_DWORD *)this + 2) + 20),
               a2->uName.ulPropid,
               a3->uName.ulPropid,
               a4);
    if ( Object == -8114 || Object == -1809 )
    {
      v4 = -2147217911;
    }
    else
    {
      if ( !Object )
        goto LABEL_14;
      v4 = -2147467259;
    }
    CExtError::SendJetErrortoOLEAuto(
      v4,
      *(char **)(*((_DWORD *)this + 2) + 16),
      Object,
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
0x1000d5b0  mov     edi, edi
0x1000d5b2  push    ebp
0x1000d5b3  mov     ebp, esp
0x1000d5b5  push    0FFFFFFFFh
0x1000d5b7  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1000d5bc  mov     eax, large fs:0
0x1000d5c2  push    eax
0x1000d5c3  sub     esp, 8
0x1000d5c6  push    ebx
0x1000d5c7  push    esi
0x1000d5c8  push    edi; int
0x1000d5c9  mov     eax, ___security_cookie
0x1000d5ce  xor     eax, ebp
0x1000d5d0  push    eax; struct _GUID *
0x1000d5d1  lea     eax, [ebp+var_C]
0x1000d5d4  mov     large fs:0, eax
0x1000d5da  xor     edi, edi
0x1000d5dc  push    edi; perrinfo
0x1000d5dd  push    edi; dwReserved
0x1000d5de  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000d5e4  mov     ebx, [ebp+this]
0x1000d5e7  mov     esi, [ebx+8]
0x1000d5ea  add     esi, 68h ; 'h'
0x1000d5ed  push    esi; lpCriticalSection
0x1000d5ee  mov     [ebp+var_10], esi
0x1000d5f1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000d5f7  mov     edx, [ebp+arg_4]
0x1000d5fa  mov     [ebp+var_4], edi
0x1000d5fd  test    edx, edx
0x1000d5ff  jz      short loc_1000D663
0x1000d601  mov     ecx, [ebp+arg_8]
0x1000d604  test    ecx, ecx
0x1000d606  jz      short loc_1000D663
0x1000d608  cmp     dword ptr [edx+10h], 2
0x1000d60c  jnz     short loc_1000D663
0x1000d60e  cmp     dword ptr [ecx+10h], 2
0x1000d612  jnz     short loc_1000D663
0x1000d614  push    [ebp+arg_C]
0x1000d617  mov     eax, [ebx+8]
0x1000d61a  push    dword ptr [ecx+14h]
0x1000d61d  push    dword ptr [edx+14h]
0x1000d620  push    dword ptr [eax+14h]
0x1000d623  push    dword ptr [eax+10h]
0x1000d626  call    ds:__imp__JetCreateObject@20; JetCreateObject(x,x,x,x,x)
0x1000d62c  cmp     eax, 0FFFFE04Eh
0x1000d631  jz      short loc_1000D645
0x1000d633  cmp     eax, 0FFFFF8EFh
0x1000d638  jz      short loc_1000D645
0x1000d63a  test    eax, eax
0x1000d63c  jz      short loc_1000D690
0x1000d63e  mov     edi, 80004005h
0x1000d643  jmp     short loc_1000D64E
0x1000d645  mov     edi, 80040E09h
0x1000d64a  test    eax, eax
0x1000d64c  jz      short loc_1000D668
0x1000d64e  mov     ecx, [ebx+8]
0x1000d651  mov     edx, edi
0x1000d653  push    offset _IID_IDBUserAttributes; int
0x1000d658  push    eax; unsigned int
0x1000d659  mov     ecx, [ecx+10h]
0x1000d65c  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1000d661  jmp     short loc_1000D690
0x1000d663  mov     edi, 80070057h
0x1000d668  mov     eax, [ebx+8]
0x1000d66b  lea     ecx, [ebp+var_14]
0x1000d66e  push    3
0x1000d670  push    4
0x1000d672  push    ecx
0x1000d673  push    dword ptr [eax+14h]
0x1000d676  push    dword ptr [eax+10h]
0x1000d679  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000d67f  test    eax, eax
0x1000d681  jnz     short loc_1000D690
0x1000d683  push    eax; int
0x1000d684  push    offset _IID_IDBUserAttributes; int
0x1000d689  mov     edx, edi
0x1000d68b  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000d690  test    esi, esi
0x1000d692  jz      short loc_1000D69B
0x1000d694  push    esi; lpCriticalSection
0x1000d695  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000d69b  mov     eax, edi
0x1000d69d  mov     ecx, [ebp+var_C]
0x1000d6a0  mov     large fs:0, ecx
0x1000d6a7  pop     ecx
0x1000d6a8  pop     edi
0x1000d6a9  pop     esi
0x1000d6aa  pop     ebx
0x1000d6ab  mov     esp, ebp
0x1000d6ad  pop     ebp
0x1000d6ae  retn    10h
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
