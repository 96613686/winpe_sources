# CImpITableDef::DropTable(tagDBID *)

- ea: `0x10044330`
- end: `0x10044459`
- name: `?DropTable@CImpITableDef@@UAGJPAUtagDBID@@@Z`
- size: `297`
- prototype: `int(CImpITableDef *__hidden this, struct tagDBID *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10044330`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1004443d`
- `KERNEL32!LeaveCriticalSection` at `0x1004443d`
- `KERNEL32!EnterCriticalSection` at `0x10044371`
- `KERNEL32!EnterCriticalSection` at `0x10044371`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004435e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004435e`
- `msjet40!__imp__JetDeleteTable@12` at `0x100443a2`
- `msjet40!__imp__JetDeleteTable@12` at `0x100443a2`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10044421`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10044421`

## pseudocode

```c
int __stdcall CImpITableDef::DropTable(CImpITableDef *this, struct tagDBID *a2)
{
  int v2; // edi
  struct _RTL_CRITICAL_SECTION *v3; // esi
  LPOLESTR pwszName; // ecx
  signed int v5; // eax
  const struct _GUID *v7; // [esp+0h] [ebp-24h]
  const struct _GUID *v8; // [esp+4h] [ebp-20h]
  _BYTE v9[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v10; // [esp+14h] [ebp-10h]
  int v11; // [esp+20h] [ebp-4h]

  v2 = 0;
  SetErrorInfo(0, 0);
  v10 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 104);
  v3 = v10;
  EnterCriticalSection(v10);
  v11 = 0;
  if ( !a2 )
  {
    v2 = -2147024809;
    goto LABEL_19;
  }
  if ( a2->eKind == 2 )
  {
    pwszName = a2->uName.pwszName;
    if ( pwszName )
    {
      v5 = JetDeleteTable(*(_DWORD *)(*((_DWORD *)this + 2) + 16), *(_DWORD *)(*((_DWORD *)this + 2) + 20), pwszName);
      if ( v5 > -1305 )
      {
        if ( v5 == -1304 || v5 == -1302 )
        {
          v2 = -2147217856;
          goto LABEL_17;
        }
        if ( !v5 )
          goto LABEL_21;
      }
      else
      {
        if ( v5 == -1305 )
        {
          v2 = -2147217865;
          goto LABEL_17;
        }
        if ( v5 == -8114 || v5 == -1907 || v5 == -1809 )
        {
          v2 = -2147217911;
LABEL_17:
          CExtError::SendJetErrortoOLEAuto(
            v2,
            *(char **)(*((_DWORD *)this + 2) + 16),
            v5,
            (int)&IID_ITableDefinition,
            (int)v7,
            v8);
          goto LABEL_21;
        }
      }
      v2 = -2147467259;
      goto LABEL_17;
    }
  }
  v2 = -2147217865;
LABEL_19:
  if ( !JetGetDatabaseInfo(*(_DWORD *)(*((_DWORD *)this + 2) + 16), *(_DWORD *)(*((_DWORD *)this + 2) + 20), v9, 4, 3) )
    CExtError::SendHRtoOLEAuto(v2, (__int128 *)&IID_ITableDefinition, 0, v7, (int)v8);
LABEL_21:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v2;
}

```

## disassembly

```asm
0x10044330  mov     edi, edi
0x10044332  push    ebp
0x10044333  mov     ebp, esp
0x10044335  push    0FFFFFFFFh
0x10044337  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1004433c  mov     eax, large fs:0
0x10044342  push    eax
0x10044343  sub     esp, 8
0x10044346  push    ebx
0x10044347  push    esi
0x10044348  push    edi; int
0x10044349  mov     eax, ___security_cookie
0x1004434e  xor     eax, ebp
0x10044350  push    eax; struct _GUID *
0x10044351  lea     eax, [ebp+var_C]
0x10044354  mov     large fs:0, eax
0x1004435a  xor     edi, edi
0x1004435c  push    edi; perrinfo
0x1004435d  push    edi; dwReserved
0x1004435e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10044364  mov     ebx, [ebp+this]
0x10044367  mov     esi, [ebx+8]
0x1004436a  add     esi, 68h ; 'h'
0x1004436d  push    esi; lpCriticalSection
0x1004436e  mov     [ebp+var_10], esi
0x10044371  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10044377  mov     eax, [ebp+arg_4]
0x1004437a  mov     [ebp+var_4], edi
0x1004437d  test    eax, eax
0x1004437f  jnz     short loc_1004438B
0x10044381  mov     edi, 80070057h
0x10044386  jmp     loc_10044410
0x1004438b  cmp     dword ptr [eax+10h], 2
0x1004438f  jnz     short loc_1004440B
0x10044391  mov     ecx, [eax+14h]
0x10044394  test    ecx, ecx
0x10044396  jz      short loc_1004440B
0x10044398  mov     eax, [ebx+8]
0x1004439b  push    ecx
0x1004439c  push    dword ptr [eax+14h]
0x1004439f  push    dword ptr [eax+10h]
0x100443a2  call    ds:__imp__JetDeleteTable@12; JetDeleteTable(x,x,x)
0x100443a8  cmp     eax, 0FFFFFAE7h
0x100443ad  jg      short loc_100443D4
0x100443af  jz      short loc_100443CD
0x100443b1  cmp     eax, 0FFFFE04Eh
0x100443b6  jz      short loc_100443C6
0x100443b8  cmp     eax, 0FFFFF88Dh
0x100443bd  jz      short loc_100443C6
0x100443bf  cmp     eax, 0FFFFF8EFh
0x100443c4  jnz     short loc_100443E6
0x100443c6  mov     edi, 80040E09h
0x100443cb  jmp     short loc_100443F6
0x100443cd  mov     edi, 80040E37h
0x100443d2  jmp     short loc_100443F6
0x100443d4  cmp     eax, 0FFFFFAE8h
0x100443d9  jz      short loc_100443ED
0x100443db  cmp     eax, 0FFFFFAEAh
0x100443e0  jz      short loc_100443ED
0x100443e2  test    eax, eax
0x100443e4  jz      short loc_10044438
0x100443e6  mov     edi, 80004005h
0x100443eb  jmp     short loc_100443F2
0x100443ed  mov     edi, 80040E40h
0x100443f2  test    eax, eax
0x100443f4  jz      short loc_10044410
0x100443f6  mov     ecx, [ebx+8]
0x100443f9  mov     edx, edi
0x100443fb  push    offset _IID_ITableDefinition; int
0x10044400  push    eax; unsigned int
0x10044401  mov     ecx, [ecx+10h]
0x10044404  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10044409  jmp     short loc_10044438
0x1004440b  mov     edi, 80040E37h
0x10044410  mov     eax, [ebx+8]
0x10044413  lea     ecx, [ebp+var_14]
0x10044416  push    3
0x10044418  push    4
0x1004441a  push    ecx
0x1004441b  push    dword ptr [eax+14h]
0x1004441e  push    dword ptr [eax+10h]
0x10044421  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10044427  test    eax, eax
0x10044429  jnz     short loc_10044438
0x1004442b  push    eax; int
0x1004442c  push    offset _IID_ITableDefinition; int
0x10044431  mov     edx, edi
0x10044433  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10044438  test    esi, esi
0x1004443a  jz      short loc_10044443
0x1004443c  push    esi; lpCriticalSection
0x1004443d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10044443  mov     eax, edi
0x10044445  mov     ecx, [ebp+var_C]
0x10044448  mov     large fs:0, ecx
0x1004444f  pop     ecx
0x10044450  pop     edi
0x10044451  pop     esi
0x10044452  pop     ebx
0x10044453  mov     esp, ebp
0x10044455  pop     ebp
0x10044456  retn    8
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
