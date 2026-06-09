# CImpIDBUserAttributes::DeleteObject(tagDBID *,tagDBID *)

- ea: `0x1000d6c0`
- end: `0x1000d7be`
- name: `?DeleteObject@CImpIDBUserAttributes@@UAGJPAUtagDBID@@0@Z`
- size: `254`
- prototype: `int(CImpIDBUserAttributes *__hidden this, struct tagDBID *, struct tagDBID *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1000d6c0`
- `0x1001bdc0`
- `0x1001c380`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000d7a2`
- `KERNEL32!LeaveCriticalSection` at `0x1000d7a2`
- `KERNEL32!EnterCriticalSection` at `0x1000d701`
- `KERNEL32!EnterCriticalSection` at `0x1000d701`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d6ee`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000d6ee`
- `msjet40!__imp__JetDeleteObject@16` at `0x1000d733`
- `msjet40!__imp__JetDeleteObject@16` at `0x1000d733`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d786`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1000d786`

## pseudocode

```c
int __stdcall CImpIDBUserAttributes::DeleteObject(CImpIDBUserAttributes *this, struct tagDBID *a2, struct tagDBID *a3)
{
  int v3; // edi
  struct _RTL_CRITICAL_SECTION *v4; // esi
  unsigned int v5; // eax
  const struct _GUID *v7; // [esp+0h] [ebp-24h]
  const struct _GUID *v8; // [esp+4h] [ebp-20h]
  _BYTE v9[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v10; // [esp+14h] [ebp-10h]
  int v11; // [esp+20h] [ebp-4h]

  v3 = 0;
  SetErrorInfo(0, 0);
  v10 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 104);
  v4 = v10;
  EnterCriticalSection(v10);
  v11 = 0;
  if ( a2 && a3 && a2->eKind == 2 && a3->eKind == 2 )
  {
    v5 = JetDeleteObject(
           *(_DWORD *)(*((_DWORD *)this + 2) + 16),
           *(_DWORD *)(*((_DWORD *)this + 2) + 20),
           a2->uName.ulPropid,
           a3->uName.ulPropid);
    if ( v5 == -8114 || v5 == -1809 )
    {
      v3 = -2147217911;
    }
    else
    {
      if ( !v5 )
        goto LABEL_14;
      v3 = -2147467259;
    }
    CExtError::SendJetErrortoOLEAuto(
      v3,
      *(char **)(*((_DWORD *)this + 2) + 16),
      v5,
      (int)&IID_IDBUserAttributes,
      (int)v7,
      v8);
  }
  else
  {
    v3 = -2147024809;
    if ( !JetGetDatabaseInfo(*(_DWORD *)(*((_DWORD *)this + 2) + 16), *(_DWORD *)(*((_DWORD *)this + 2) + 20), v9, 4, 3) )
      CExtError::SendHRtoOLEAuto((int)&IID_IDBUserAttributes, 0, v7, (int)v8);
  }
LABEL_14:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v3;
}

```

## disassembly

```asm
0x1000d6c0  mov     edi, edi
0x1000d6c2  push    ebp
0x1000d6c3  mov     ebp, esp
0x1000d6c5  push    0FFFFFFFFh
0x1000d6c7  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1000d6cc  mov     eax, large fs:0
0x1000d6d2  push    eax
0x1000d6d3  sub     esp, 8
0x1000d6d6  push    ebx
0x1000d6d7  push    esi
0x1000d6d8  push    edi; int
0x1000d6d9  mov     eax, ___security_cookie
0x1000d6de  xor     eax, ebp
0x1000d6e0  push    eax; struct _GUID *
0x1000d6e1  lea     eax, [ebp+var_C]
0x1000d6e4  mov     large fs:0, eax
0x1000d6ea  xor     edi, edi
0x1000d6ec  push    edi; perrinfo
0x1000d6ed  push    edi; dwReserved
0x1000d6ee  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000d6f4  mov     ebx, [ebp+this]
0x1000d6f7  mov     esi, [ebx+8]
0x1000d6fa  add     esi, 68h ; 'h'
0x1000d6fd  push    esi; lpCriticalSection
0x1000d6fe  mov     [ebp+var_10], esi
0x1000d701  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000d707  mov     edx, [ebp+arg_4]
0x1000d70a  mov     [ebp+var_4], edi
0x1000d70d  test    edx, edx
0x1000d70f  jz      short loc_1000D770
0x1000d711  mov     ecx, [ebp+arg_8]
0x1000d714  test    ecx, ecx
0x1000d716  jz      short loc_1000D770
0x1000d718  cmp     dword ptr [edx+10h], 2
0x1000d71c  jnz     short loc_1000D770
0x1000d71e  cmp     dword ptr [ecx+10h], 2
0x1000d722  jnz     short loc_1000D770
0x1000d724  push    dword ptr [ecx+14h]
0x1000d727  mov     eax, [ebx+8]
0x1000d72a  push    dword ptr [edx+14h]
0x1000d72d  push    dword ptr [eax+14h]
0x1000d730  push    dword ptr [eax+10h]
0x1000d733  call    ds:__imp__JetDeleteObject@16; JetDeleteObject(x,x,x,x)
0x1000d739  cmp     eax, 0FFFFE04Eh
0x1000d73e  jz      short loc_1000D752
0x1000d740  cmp     eax, 0FFFFF8EFh
0x1000d745  jz      short loc_1000D752
0x1000d747  test    eax, eax
0x1000d749  jz      short loc_1000D79D
0x1000d74b  mov     edi, 80004005h
0x1000d750  jmp     short loc_1000D75B
0x1000d752  mov     edi, 80040E09h
0x1000d757  test    eax, eax
0x1000d759  jz      short loc_1000D775
0x1000d75b  mov     ecx, [ebx+8]
0x1000d75e  mov     edx, edi
0x1000d760  push    offset _IID_IDBUserAttributes; int
0x1000d765  push    eax; unsigned int
0x1000d766  mov     ecx, [ecx+10h]
0x1000d769  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1000d76e  jmp     short loc_1000D79D
0x1000d770  mov     edi, 80070057h
0x1000d775  mov     eax, [ebx+8]
0x1000d778  lea     ecx, [ebp+var_14]
0x1000d77b  push    3
0x1000d77d  push    4
0x1000d77f  push    ecx
0x1000d780  push    dword ptr [eax+14h]
0x1000d783  push    dword ptr [eax+10h]
0x1000d786  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1000d78c  test    eax, eax
0x1000d78e  jnz     short loc_1000D79D
0x1000d790  push    eax; int
0x1000d791  push    offset _IID_IDBUserAttributes; int
0x1000d796  mov     edx, edi
0x1000d798  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1000d79d  test    esi, esi
0x1000d79f  jz      short loc_1000D7A8
0x1000d7a1  push    esi; lpCriticalSection
0x1000d7a2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000d7a8  mov     eax, edi
0x1000d7aa  mov     ecx, [ebp+var_C]
0x1000d7ad  mov     large fs:0, ecx
0x1000d7b4  pop     ecx
0x1000d7b5  pop     edi
0x1000d7b6  pop     esi
0x1000d7b7  pop     ebx
0x1000d7b8  mov     esp, ebp
0x1000d7ba  pop     ebp
0x1000d7bb  retn    0Ch
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
