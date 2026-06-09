# UpdateMSIFile(ushort const *,_GUID,_GUID,_GUID,int,int,int,ushort * *)

- ea: `0x18002673c`
- end: `0x18002696f`
- name: `?UpdateMSIFile@@YAJPEBGU_GUID@@11HHHPEAPEAG@Z`
- size: `563`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, GUID *rguid, struct _GUID *Buf1, GUID *, int, int, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180025af4`

## callees

- `0x18002474c`
- `0x180024a88`
- `0x1800264b0`
- `0x18002673c`
- `0x180026978`
- `0x180026d98`
- `0x180026ee4`
- `0x180055502`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800267ac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800267e7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800268f1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800267ac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800267e7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800268f1`
- `msi!__imp_MsiCloseHandle` at `0x180026946`
- `msi!__imp_MsiCloseHandle` at `0x180026946`
- `msi!__imp_MsiDatabaseCommit` at `0x180026929`
- `msi!__imp_MsiDatabaseCommit` at `0x180026929`
- `msi!__imp_MsiOpenDatabaseW` at `0x180026818`
- `msi!__imp_MsiOpenDatabaseW` at `0x180026818`

## pseudocode

```c
__int64 __fastcall UpdateMSIFile(
        LPCWSTR lpExistingFileName,
        GUID *rguid,
        struct _GUID *Buf1,
        GUID *a4,
        int a5,
        int a6,
        int a7,
        unsigned __int16 **a8)
{
  int updated; // ebx
  signed int v13; // eax
  bool v14; // cc
  OLECHAR *v15; // rdx
  MSIHANDLE phDatabase[4]; // [rsp+20h] [rbp-E0h] BYREF
  OLECHAR v18[40]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v20[40]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v21[304]; // [rsp+120h] [rbp+20h] BYREF

  phDatabase[0] = 0;
  memset_0(v18, 0, sizeof(v18));
  memset_0(sz, 0, sizeof(sz));
  if ( !StringFromGUID2(rguid, sz, 40) || memcmp_0(Buf1, &GUID_NULL, 0x10u) && !StringFromGUID2(Buf1, v18, 40) )
    goto LABEL_2;
  updated = CopyMSIForUpdate(lpExistingFileName, v18, a8);
  if ( updated < 0 )
    goto LABEL_24;
  v13 = MsiOpenDatabaseW(*a8, (LPCWSTR)1, phDatabase);
  v14 = v13 <= 0;
  if ( v13 )
    goto LABEL_21;
  if ( a5 )
  {
    updated = RemoveAllUsersFromMSI(phDatabase[0]);
    if ( updated < 0 )
      goto LABEL_24;
  }
  if ( a6 )
  {
    updated = UpdateSummaryInfo(phDatabase[0], v18, v21);
    if ( updated < 0 )
      goto LABEL_24;
    updated = UpdateProperty(phDatabase[0], L"UpgradeCode", v18);
    if ( updated < 0 )
      goto LABEL_24;
    updated = UpdateProperty(phDatabase[0], L"ProductCode", v18);
    if ( updated < 0 )
      goto LABEL_24;
    updated = UpdateProperty(phDatabase[0], L"ProductName", v21);
    if ( updated < 0 )
      goto LABEL_24;
    updated = UpdateMSITables(phDatabase[0], sz, v18);
    if ( updated < 0 )
      goto LABEL_24;
  }
  if ( !a7 )
    goto LABEL_20;
  if ( !StringFromGUID2(a4, v20, 40) )
  {
LABEL_2:
    updated = -2147467259;
    goto LABEL_24;
  }
  v15 = v18;
  if ( !v18[0] )
    v15 = sz;
  updated = AddUninstallActionToMSI(phDatabase[0], v15, v20);
  if ( updated >= 0 )
  {
LABEL_20:
    v13 = MsiDatabaseCommit(phDatabase[0]);
    v14 = v13 <= 0;
    if ( !v13 )
      goto LABEL_24;
LABEL_21:
    if ( v14 )
      updated = v13;
    else
      updated = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_24:
  MsiCloseHandle(phDatabase[0]);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18002673c  push    rbp
0x18002673e  push    rbx
0x18002673f  push    rsi
0x180026740  push    rdi
0x180026741  push    r13
0x180026743  push    r14
0x180026745  push    r15
0x180026747  lea     rbp, [rsp-290h]
0x18002674f  sub     rsp, 390h
0x180026756  mov     rax, cs:__security_cookie
0x18002675d  xor     rax, rsp
0x180026760  mov     [rbp+2C0h+var_40], rax
0x180026767  mov     rdi, [rbp+2C0h+arg_38]
0x18002676e  xor     r13d, r13d
0x180026771  mov     rsi, r8
0x180026774  mov     [rsp+3C0h+phDatabase], r13d
0x180026779  mov     rbx, rdx
0x18002677c  mov     r14, rcx
0x18002677f  xor     edx, edx; Val
0x180026781  lea     rcx, [rsp+3C0h+var_390]; void *
0x180026786  lea     r8d, [r13+50h]; Size
0x18002678a  mov     r15, r9
0x18002678d  call    memset_0
0x180026792  xor     edx, edx; Val
0x180026794  lea     r8d, [r13+50h]; Size
0x180026798  lea     rcx, [rbp+2C0h+sz]; void *
0x18002679c  call    memset_0
0x1800267a1  lea     r8d, [r13+28h]; cchMax
0x1800267a5  mov     rcx, rbx; rguid
0x1800267a8  lea     rdx, [rbp+2C0h+sz]; lpsz
0x1800267ac  call    cs:__imp_StringFromGUID2
0x1800267b2  test    eax, eax
0x1800267b4  jnz     short loc_1800267C0
0x1800267b6  mov     ebx, 80004005h
0x1800267bb  jmp     loc_180026942
0x1800267c0  mov     r8d, 10h; Size
0x1800267c6  lea     rdx, GUID_NULL; Buf2
0x1800267cd  mov     rcx, rsi; Buf1
0x1800267d0  call    memcmp_0
0x1800267d5  test    eax, eax
0x1800267d7  jz      short loc_1800267F1
0x1800267d9  mov     r8d, 28h ; '('; cchMax
0x1800267df  lea     rdx, [rsp+3C0h+var_390]; lpsz
0x1800267e4  mov     rcx, rsi; rguid
0x1800267e7  call    cs:__imp_StringFromGUID2
0x1800267ed  test    eax, eax
0x1800267ef  jz      short loc_1800267B6
0x1800267f1  mov     r8, rdi; unsigned __int16 **
0x1800267f4  lea     rdx, [rsp+3C0h+var_390]; unsigned __int16 *
0x1800267f9  mov     rcx, r14; lpExistingFileName
0x1800267fc  call    ?CopyMSIForUpdate@@YAJPEBG0PEAPEAG@Z; CopyMSIForUpdate(ushort const *,ushort const *,ushort * *)
0x180026801  mov     ebx, eax
0x180026803  test    eax, eax
0x180026805  js      loc_180026942
0x18002680b  mov     rcx, [rdi]; szDatabasePath
0x18002680e  lea     r8, [rsp+3C0h+phDatabase]; phDatabase
0x180026813  mov     edx, 1; szPersist
0x180026818  call    cs:__imp_MsiOpenDatabaseW
0x18002681e  test    eax, eax
0x180026820  jnz     loc_180026933
0x180026826  cmp     [rbp+2C0h+arg_20], r13d
0x18002682d  jz      short loc_180026842
0x18002682f  mov     ecx, [rsp+3C0h+phDatabase]; unsigned int
0x180026833  call    ?RemoveAllUsersFromMSI@@YAJK@Z; RemoveAllUsersFromMSI(ulong)
0x180026838  mov     ebx, eax
0x18002683a  test    eax, eax
0x18002683c  js      loc_180026942
0x180026842  cmp     [rbp+2C0h+arg_28], r13d
0x180026849  jz      loc_1800268DB
0x18002684f  mov     ecx, [rsp+3C0h+phDatabase]; unsigned int
0x180026853  lea     r8, [rbp+2C0h+var_2A0]; unsigned __int16 *
0x180026857  lea     rdx, [rsp+3C0h+var_390]; unsigned __int16 *
0x18002685c  call    ?UpdateSummaryInfo@@YAJKPEBGPEAGK@Z; UpdateSummaryInfo(ulong,ushort const *,ushort *,ulong)
0x180026861  mov     ebx, eax
0x180026863  test    eax, eax
0x180026865  js      loc_180026942
0x18002686b  mov     ecx, [rsp+3C0h+phDatabase]; hDatabase
0x18002686f  lea     r8, [rsp+3C0h+var_390]; unsigned __int16 *
0x180026874  lea     rdx, aUpgradecode; "UpgradeCode"
0x18002687b  call    ?UpdateProperty@@YAJKPEBG0@Z; UpdateProperty(ulong,ushort const *,ushort const *)
0x180026880  mov     ebx, eax
0x180026882  test    eax, eax
0x180026884  js      loc_180026942
0x18002688a  mov     ecx, [rsp+3C0h+phDatabase]; hDatabase
0x18002688e  lea     r8, [rsp+3C0h+var_390]; unsigned __int16 *
0x180026893  lea     rdx, aProductcode; "ProductCode"
0x18002689a  call    ?UpdateProperty@@YAJKPEBG0@Z; UpdateProperty(ulong,ushort const *,ushort const *)
0x18002689f  mov     ebx, eax
0x1800268a1  test    eax, eax
0x1800268a3  js      loc_180026942
0x1800268a9  mov     ecx, [rsp+3C0h+phDatabase]; hDatabase
0x1800268ad  lea     r8, [rbp+2C0h+var_2A0]; unsigned __int16 *
0x1800268b1  lea     rdx, aProductname; "ProductName"
0x1800268b8  call    ?UpdateProperty@@YAJKPEBG0@Z; UpdateProperty(ulong,ushort const *,ushort const *)
0x1800268bd  mov     ebx, eax
0x1800268bf  test    eax, eax
0x1800268c1  js      short loc_180026942
0x1800268c3  mov     ecx, [rsp+3C0h+phDatabase]; hDatabase
0x1800268c7  lea     r8, [rsp+3C0h+var_390]; unsigned __int16 *
0x1800268cc  lea     rdx, [rbp+2C0h+sz]; unsigned __int16 *
0x1800268d0  call    ?UpdateMSITables@@YAJKPEBG0@Z; UpdateMSITables(ulong,ushort const *,ushort const *)
0x1800268d5  mov     ebx, eax
0x1800268d7  test    eax, eax
0x1800268d9  js      short loc_180026942
0x1800268db  cmp     [rbp+2C0h+arg_30], r13d
0x1800268e2  jz      short loc_180026925
0x1800268e4  mov     r8d, 28h ; '('; cchMax
0x1800268ea  lea     rdx, [rbp+2C0h+var_2F0]; lpsz
0x1800268ee  mov     rcx, r15; rguid
0x1800268f1  call    cs:__imp_StringFromGUID2
0x1800268f7  test    eax, eax
0x1800268f9  jz      loc_1800267B6
0x1800268ff  cmp     [rsp+3C0h+var_390], r13w
0x180026905  lea     rax, [rbp+2C0h+sz]
0x180026909  mov     ecx, [rsp+3C0h+phDatabase]; hDatabase
0x18002690d  lea     rdx, [rsp+3C0h+var_390]
0x180026912  cmovz   rdx, rax; unsigned __int16 *
0x180026916  lea     r8, [rbp+2C0h+var_2F0]; unsigned __int16 *
0x18002691a  call    ?AddUninstallActionToMSI@@YAJKPEBG0@Z; AddUninstallActionToMSI(ulong,ushort const *,ushort const *)
0x18002691f  mov     ebx, eax
0x180026921  test    eax, eax
0x180026923  js      short loc_180026942
0x180026925  mov     ecx, [rsp+3C0h+phDatabase]; hDatabase
0x180026929  call    cs:__imp_MsiDatabaseCommit
0x18002692f  test    eax, eax
0x180026931  jz      short loc_180026942
0x180026933  jg      short loc_180026939
0x180026935  mov     ebx, eax
0x180026937  jmp     short loc_180026942
0x180026939  movzx   ebx, ax
0x18002693c  or      ebx, 80070000h
0x180026942  mov     ecx, [rsp+3C0h+phDatabase]; hAny
0x180026946  call    cs:__imp_MsiCloseHandle
0x18002694c  mov     eax, ebx
0x18002694e  mov     rcx, [rbp+2C0h+var_40]
0x180026955  xor     rcx, rsp; StackCookie
0x180026958  call    __security_check_cookie
0x18002695d  add     rsp, 390h
0x180026964  pop     r15
0x180026966  pop     r14
0x180026968  pop     r13
0x18002696a  pop     rdi
0x18002696b  pop     rsi
0x18002696c  pop     rbx
0x18002696d  pop     rbp
0x18002696e  retn
```
