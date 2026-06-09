# RegTable::InitializeTable(void)

- ea: `0x180009498`
- end: `0x1800097a5`
- name: `?InitializeTable@RegTable@@AEAAJXZ`
- size: `781`
- prototype: `__int64 __fastcall(RegTable *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009384`

## callees

- `0x180009498`
- `0x18000b028`
- `0x18000b568`
- `0x18000d538`
- `0x18000d694`
- `0x18001fecc`
- `0x18003efe8`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800094e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000956c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000956c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000965f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000965f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000961e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000961e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009759`

## pseudocode

```c
__int64 __fastcall RegTable::InitializeTable(RegTable *this)
{
  LSTATUS v2; // eax
  int Existing; // ebx
  DWORD i; // r12d
  LSTATUS v6; // eax
  __int64 *v7; // r14
  volatile signed __int32 *v8; // rdi
  char *v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  void *v12; // rcx
  int v13; // eax
  unsigned int v14; // edx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  const OLECHAR *v16; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[120]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(*((HKEY *)this + 1), (LPCWSTR)this + 9, 0, 0x20019u, &hKey);
  Existing = v2;
  if ( v2 == 2 )
    return 1;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
    return (unsigned int)Existing;
  }
  for ( i = 0; ; ++i )
  {
    cchName = 117;
    ftLastWriteTime = 0;
    v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    Existing = v6;
    if ( v6 )
      break;
    pv = 0;
    Existing = RegRow::CreateExisting(this, Name, (struct RegRow **)&pv);
    if ( Existing < 0 )
      goto LABEL_20;
    v7 = (__int64 *)pv;
    if ( !*((_BYTE *)this + 16) )
    {
      LODWORD(v16) = 0;
      v10 = (*(__int64 (__fastcall **)(LPVOID, const OLECHAR **))(*(_QWORD *)pv + 184LL))(pv, &v16);
      if ( v10 < 0 )
      {
        if ( v10 != -2147160063 )
          goto LABEL_20;
        pv = 0;
        (*(void (__fastcall **)(__int64 *, LPVOID *))(*v7 + 64))(v7, &pv);
        v12 = pv;
        if ( pv )
        {
          v13 = *((_DWORD *)this + 135);
          if ( v13 == 1 )
          {
            v14 = -2147479287;
            goto LABEL_37;
          }
          if ( v13 == 2 )
          {
            v14 = -2147479286;
LABEL_37:
            LogMessage(0x11u, v14, 1u, pv);
            v12 = pv;
          }
          CoTaskMemFree(v12);
        }
        if ( v7 )
          (*(void (__fastcall **)(__int64 *, __int64))(*v7 + 152))(v7, 1);
        continue;
      }
      v11 = *v7;
      if ( (_DWORD)v16 )
        (*(void (__fastcall **)(__int64 *))(v11 + 72))(v7);
      else
        (*(void (__fastcall **)(__int64 *))(v11 + 80))(v7);
    }
    pv = (LPVOID)&dword_180053104;
    Existing = CString::AssignNoThrow((CString *)&pv, Name);
    if ( Existing < 0 )
    {
      v9 = (char *)pv - 12;
      if ( (char *)pv - 12 != (char *)&qword_1800530F8
        && _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
      {
        CoTaskMemFree(v9);
      }
      goto LABEL_20;
    }
    v8 = (volatile signed __int32 *)((char *)pv - 12);
    if ( *((int *)pv - 3) < 0 )
    {
      v16 = &dword_180053104;
    }
    else
    {
      v16 = (const OLECHAR *)pv;
      _InterlockedIncrement(v8);
    }
    Existing = CMap<CString,unsigned short const *,RegRow *,RegRow *>::SetAtWithActualKeyType(
                 (char *)this + 576,
                 &v16,
                 v7);
    if ( Existing < 0 )
    {
      CString::~CString((CString *)&pv);
      goto LABEL_20;
    }
    if ( v8 != (volatile signed __int32 *)&qword_1800530F8 && _InterlockedExchangeAdd(v8, 0xFFFFFFFF) == 1 )
      CoTaskMemFree((LPVOID)v8);
  }
  if ( v6 == 259 )
  {
    Existing = 0;
  }
  else if ( v6 > 0 )
  {
    Existing = (unsigned __int16)v6 | 0x80070000;
  }
LABEL_20:
  RegCloseKey(hKey);
  if ( Existing < 0 )
    RegTable::ClearMap(this);
  return (unsigned int)Existing;
}

```

## disassembly

```asm
0x180009498  push    rbp
0x18000949a  push    rbx
0x18000949b  push    rdi
0x18000949c  push    r12
0x18000949e  push    r14
0x1800094a0  push    r15
0x1800094a2  lea     rbp, [rsp-78h]
0x1800094a7  sub     rsp, 178h
0x1800094ae  mov     rax, cs:__security_cookie
0x1800094b5  xor     rax, rsp
0x1800094b8  mov     [rbp+0A0h+var_40], rax
0x1800094bc  mov     r15, rcx
0x1800094bf  mov     [rsp+1A0h+hKey], 0
0x1800094c8  lea     rdx, [rcx+12h]; lpSubKey
0x1800094cc  mov     r9d, 20019h; samDesired
0x1800094d2  mov     rcx, [rcx+8]; hKey
0x1800094d6  lea     rax, [rsp+1A0h+hKey]
0x1800094db  xor     r8d, r8d; ulOptions
0x1800094de  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800094e3  call    cs:__imp_RegOpenKeyExW
0x1800094e9  mov     ebx, eax
0x1800094eb  cmp     eax, 2
0x1800094ee  jnz     short loc_180009512
0x1800094f0  lea     ebx, [rax-1]
0x1800094f3  mov     eax, ebx
0x1800094f5  mov     rcx, [rbp+0A0h+var_40]
0x1800094f9  xor     rcx, rsp; StackCookie
0x1800094fc  call    __security_check_cookie
0x180009501  add     rsp, 178h
0x180009508  pop     r15
0x18000950a  pop     r14
0x18000950c  pop     r12
0x18000950e  pop     rdi
0x18000950f  pop     rbx
0x180009510  pop     rbp
0x180009511  retn
0x180009512  test    eax, eax
0x180009514  jnz     loc_18000968B
0x18000951a  xor     r12d, r12d
0x18000951d  lea     rdi, dword_180053104
0x180009524  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180009529  lea     rax, [rsp+1A0h+ftLastWriteTime]
0x18000952e  mov     [rsp+1A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180009533  lea     r9, [rsp+1A0h+cchName]; lpcchName
0x180009538  mov     [rsp+1A0h+lpcchClass], 0; lpcchClass
0x180009541  lea     r8, [rsp+1A0h+Name]; lpName
0x180009546  mov     [rsp+1A0h+lpClass], 0; lpClass
0x18000954f  mov     edx, r12d; dwIndex
0x180009552  mov     [rsp+1A0h+phkResult], 0; lpReserved
0x18000955b  mov     [rsp+1A0h+cchName], 75h ; 'u'
0x180009563  mov     qword ptr [rsp+1A0h+ftLastWriteTime.dwLowDateTime], 0
0x18000956c  call    cs:__imp_RegEnumKeyExW
0x180009572  mov     ebx, eax
0x180009574  test    eax, eax
0x180009576  jnz     loc_180009793
0x18000957c  lea     r8, [rsp+1A0h+pv]; struct RegRow **
0x180009581  mov     [rsp+1A0h+pv], 0
0x18000958a  lea     rdx, [rsp+1A0h+Name]; unsigned __int16 *
0x18000958f  mov     rcx, r15; struct RegTable *
0x180009592  call    ?CreateExisting@RegRow@@SAJPEAVRegTable@@PEBGAEAPEAV1@@Z; RegRow::CreateExisting(RegTable *,ushort const *,RegRow * &)
0x180009597  mov     ebx, eax
0x180009599  test    eax, eax
0x18000959b  js      loc_18000965A
0x1800095a1  cmp     byte ptr [r15+10h], 0
0x1800095a6  mov     r14, [rsp+1A0h+pv]
0x1800095ab  jz      loc_1800096AE
0x1800095b1  lea     rdx, [rsp+1A0h+Name]; unsigned __int16 *
0x1800095b6  mov     [rsp+1A0h+pv], rdi
0x1800095bb  lea     rcx, [rsp+1A0h+pv]; this
0x1800095c0  call    ?AssignNoThrow@CString@@QEAAJPEBG@Z; CString::AssignNoThrow(ushort const *)
0x1800095c5  mov     ebx, eax
0x1800095c7  test    eax, eax
0x1800095c9  js      short loc_180009633
0x1800095cb  mov     rax, [rsp+1A0h+pv]
0x1800095d0  lea     rcx, [r15+240h]
0x1800095d7  lea     rdi, [rax-0Ch]
0x1800095db  cmp     dword ptr [rdi], 0
0x1800095de  jl      loc_18000967A
0x1800095e4  mov     [rsp+1A0h+var_158], rax
0x1800095e9  lock inc dword ptr [rdi]
0x1800095ec  mov     r8, r14
0x1800095ef  lea     rdx, [rsp+1A0h+var_158]
0x1800095f4  call    ?SetAtWithActualKeyType@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@QEAAJVCString@@PEAVRegRow@@@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::SetAtWithActualKeyType(CString,RegRow *)
0x1800095f9  mov     ebx, eax
0x1800095fb  test    eax, eax
0x1800095fd  js      loc_180009784
0x180009603  lea     rax, qword_1800530F8
0x18000960a  cmp     rdi, rax
0x18000960d  jz      short loc_180009624
0x18000960f  or      eax, 0FFFFFFFFh
0x180009612  lock xadd [rdi], eax
0x180009616  cmp     eax, 1
0x180009619  jnz     short loc_180009624
0x18000961b  mov     rcx, rdi; pv
0x18000961e  call    cs:__imp_CoTaskMemFree
0x180009624  lea     rdi, dword_180053104
0x18000962b  inc     r12d
0x18000962e  jmp     loc_180009524
0x180009633  mov     rcx, [rsp+1A0h+pv]
0x180009638  lea     rax, qword_1800530F8
0x18000963f  add     rcx, 0FFFFFFFFFFFFFFF4h; pv
0x180009643  cmp     rcx, rax
0x180009646  jz      short loc_18000965A
0x180009648  or      eax, 0FFFFFFFFh
0x18000964b  lock xadd [rcx], eax
0x18000964f  cmp     eax, 1
0x180009652  jnz     short loc_18000965A
0x180009654  call    cs:__imp_CoTaskMemFree
0x18000965a  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000965f  call    cs:__imp_RegCloseKey
0x180009665  test    ebx, ebx
0x180009667  jns     loc_1800094F3
0x18000966d  mov     rcx, r15; this
0x180009670  call    ?ClearMap@RegTable@@AEAAXXZ; RegTable::ClearMap(void)
0x180009675  jmp     loc_1800094F3
0x18000967a  lea     rax, dword_180053104
0x180009681  mov     [rsp+1A0h+var_158], rax
0x180009686  jmp     loc_1800095EC
0x18000968b  jle     loc_1800094F3
0x180009691  movzx   ebx, ax
0x180009694  or      ebx, 80070000h
0x18000969a  jmp     loc_1800094F3
0x18000969f  test    eax, eax
0x1800096a1  jle     short loc_18000965A
0x1800096a3  movzx   ebx, ax
0x1800096a6  or      ebx, 80070000h
0x1800096ac  jmp     short loc_18000965A
0x1800096ae  mov     dword ptr [rsp+1A0h+var_158], 0
0x1800096b6  lea     rdx, [rsp+1A0h+var_158]
0x1800096bb  mov     rcx, [r14]
0x1800096be  mov     rax, [rcx+0B8h]
0x1800096c5  mov     rcx, r14
0x1800096c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096cd  test    eax, eax
0x1800096cf  js      short loc_1800096F3
0x1800096d1  mov     rax, [r14]
0x1800096d4  xor     edx, edx
0x1800096d6  mov     rcx, r14
0x1800096d9  cmp     dword ptr [rsp+1A0h+var_158], edx
0x1800096dd  jz      short loc_1800096E5
0x1800096df  mov     rax, [rax+48h]
0x1800096e3  jmp     short loc_1800096E9
0x1800096e5  mov     rax, [rax+50h]
0x1800096e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ee  jmp     loc_1800095B1
0x1800096f3  cmp     eax, 8004F001h
0x1800096f8  jnz     loc_18000965A
0x1800096fe  mov     [rsp+1A0h+pv], 0
0x180009707  lea     rdx, [rsp+1A0h+pv]
0x18000970c  mov     rax, [r14]
0x18000970f  mov     rcx, r14
0x180009712  mov     rax, [rax+40h]
0x180009716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971b  mov     rcx, [rsp+1A0h+pv]
0x180009720  test    rcx, rcx
0x180009723  jz      short loc_18000975F
0x180009725  mov     eax, [r15+21Ch]
0x18000972c  cmp     eax, 1
0x18000972f  jnz     short loc_180009738
0x180009731  mov     edx, 80001109h
0x180009736  jmp     short loc_180009742
0x180009738  cmp     eax, 2
0x18000973b  jnz     short loc_180009759
0x18000973d  mov     edx, 8000110Ah; unsigned int
0x180009742  mov     r8d, 1; unsigned int
0x180009748  mov     r9, rcx
0x18000974b  lea     ecx, [r8+10h]; unsigned __int16
0x18000974f  call    ?LogMessage@@YAXGKKZZ; LogMessage(ushort,ulong,ulong,...)
0x180009754  mov     rcx, [rsp+1A0h+pv]; pv
0x180009759  call    cs:__imp_CoTaskMemFree
0x18000975f  test    r14, r14
0x180009762  jz      loc_18000962B
0x180009768  mov     rax, [r14]
0x18000976b  mov     edx, 1
0x180009770  mov     rcx, r14
0x180009773  mov     rax, [rax+98h]
0x18000977a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000977f  jmp     loc_18000962B
0x180009784  lea     rcx, [rsp+1A0h+pv]; this
0x180009789  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18000978e  jmp     loc_18000965A
0x180009793  cmp     eax, 103h
0x180009798  jnz     loc_18000969F
0x18000979e  xor     ebx, ebx
0x1800097a0  jmp     loc_18000965A
```
