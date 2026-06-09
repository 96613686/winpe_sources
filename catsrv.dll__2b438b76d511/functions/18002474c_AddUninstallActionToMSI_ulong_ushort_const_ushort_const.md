# AddUninstallActionToMSI(ulong,ushort const *,ushort const *)

- ea: `0x18002474c`
- end: `0x180024a81`
- name: `?AddUninstallActionToMSI@@YAJKPEBG0@Z`
- size: `821`
- prototype: `__int64 __fastcall(MSIHANDLE hDatabase, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002673c`

## callees

- `0x180009ee0`
- `0x18002474c`
- `0x180055550`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x1800249a4`
- `msi!__imp_MsiCloseHandle` at `0x180024a10`
- `msi!__imp_MsiCloseHandle` at `0x180024a47`
- `msi!__imp_MsiCloseHandle` at `0x1800249a4`
- `msi!__imp_MsiCloseHandle` at `0x180024a10`
- `msi!__imp_MsiCloseHandle` at `0x180024a47`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180024984`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x1800249f4`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180024a2b`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180024984`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x1800249f4`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180024a2b`
- `msi!__imp_MsiViewExecute` at `0x180024999`
- `msi!__imp_MsiViewExecute` at `0x180024a05`
- `msi!__imp_MsiViewExecute` at `0x180024a3c`
- `msi!__imp_MsiViewExecute` at `0x180024999`
- `msi!__imp_MsiViewExecute` at `0x180024a05`
- `msi!__imp_MsiViewExecute` at `0x180024a3c`

## string_xrefs

- `0x180024770`: `INSERT INTO Property (Property, Value) VALUES ('COMPLUSUNINSTALLPATH', 'rundll32.exe')`
- `0x1800247a7`: `INSERT INTO CustomAction (Action, Type, Source, Target) VALUES ('COMPlusCustomUninstall', 50, 'COMPLUSUNINSTALLPATH', 'catsrvut.dll,COMPlusUninstallAction RemoveApplication:%s:%s')`
- `0x1800248b5`: `INSERT INTO InstallExecuteSequence (Action, Condition, Sequence) VALUES ('COMPlusCustomUninstall', 'REMOVE="ALL"', 5750)`

## pseudocode

```c
__int64 __fastcall AddUninstallActionToMSI(MSIHANDLE hDatabase, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rax
  __int64 v5; // rdx
  const wchar_t *v8; // rcx
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  signed int v23; // ebx
  bool v24; // cc
  void *v25; // rsp
  __int64 result; // rax
  WCHAR v27[240]; // [rsp+10h] [rbp-210h] BYREF
  MSIHANDLE phView[4]; // [rsp+220h] [rbp+0h] BYREF
  _OWORD v29[16]; // [rsp+230h] [rbp+10h] BYREF
  WCHAR szQuery[88]; // [rsp+330h] [rbp+110h] BYREF
  unsigned __int16 v31[184]; // [rsp+3E0h] [rbp+1C0h] BYREF

  v3 = v31;
  wcscpy(szQuery, L"INSERT INTO Property (Property, Value) VALUES ('COMPLUSUNINSTALLPATH', 'rundll2.exe')");
  v5 = 2;
  v8 = L"INSERT INTO CustomAction (Action, Type, Source, Target) VALUES ('COMPlusCustomUninstall', 50, 'COMPLUSUNINSTALLPA"
        "TH', 'catsrvut.dll,COMPlusUninstallAction RemoveApplication:%s:%s')";
  do
  {
    v9 = *((_OWORD *)v8 + 1);
    *(_OWORD *)v3 = *(_OWORD *)v8;
    v10 = *((_OWORD *)v8 + 2);
    *((_OWORD *)v3 + 1) = v9;
    v11 = *((_OWORD *)v8 + 3);
    *((_OWORD *)v3 + 2) = v10;
    v12 = *((_OWORD *)v8 + 4);
    *((_OWORD *)v3 + 3) = v11;
    v13 = *((_OWORD *)v8 + 5);
    *((_OWORD *)v3 + 4) = v12;
    v14 = *((_OWORD *)v8 + 6);
    *((_OWORD *)v3 + 5) = v13;
    v15 = *((_OWORD *)v8 + 7);
    v8 += 64;
    *((_OWORD *)v3 + 6) = v14;
    *((_OWORD *)v3 + 7) = v15;
    v3 += 64;
    --v5;
  }
  while ( v5 );
  v16 = *(_OWORD *)v8;
  phView[0] = 0;
  v17 = *((_OWORD *)v8 + 1);
  *(_OWORD *)v3 = v16;
  v18 = *((_OWORD *)v8 + 2);
  *((_OWORD *)v3 + 1) = v17;
  v19 = *((_OWORD *)v8 + 3);
  *((_OWORD *)v3 + 2) = v18;
  v20 = *((_OWORD *)v8 + 4);
  *((_OWORD *)v3 + 3) = v19;
  v21 = *((_OWORD *)v8 + 5);
  *((_OWORD *)v3 + 4) = v20;
  v22 = *(_OWORD *)(v8 + 45);
  *((_OWORD *)v3 + 5) = v21;
  *(_OWORD *)(v3 + 45) = v22;
  wcscpy(
    (wchar_t *)v29,
    L"INSERT INTO InstallExecuteSequence (Action, Condition, Sequence) VALUES ('COMPlusCustomUninstall', 'REMOVE=\"ALL\"', 5750)");
  v23 = MsiDatabaseOpenViewW(hDatabase, szQuery, phView);
  if ( v23 )
    goto LABEL_11;
  v23 = MsiViewExecute(phView[0], 0);
  MsiCloseHandle(phView[0]);
  phView[0] = 0;
  v24 = v23 <= 0;
  if ( v23 )
    goto LABEL_12;
  v25 = alloca(528);
  result = StringCchPrintfW(v27, 0x105u, v31, a3, a2);
  if ( (int)result < 0 )
    return result;
  v23 = MsiDatabaseOpenViewW(hDatabase, v27, phView);
  if ( v23 )
    goto LABEL_11;
  v23 = MsiViewExecute(phView[0], 0);
  MsiCloseHandle(phView[0]);
  phView[0] = 0;
  v24 = v23 <= 0;
  if ( v23 )
    goto LABEL_12;
  v23 = MsiDatabaseOpenViewW(hDatabase, (LPCWSTR)v29, phView);
  if ( v23 )
  {
LABEL_11:
    v24 = v23 <= 0;
    goto LABEL_12;
  }
  v23 = MsiViewExecute(phView[0], 0);
  MsiCloseHandle(phView[0]);
  v24 = v23 <= 0;
  if ( !v23 )
    return 0;
LABEL_12:
  if ( !v24 )
    return (unsigned __int16)v23 | 0x80070000;
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18002474c  push    rbp
0x18002474e  push    rbx
0x18002474f  push    rsi
0x180024750  push    rdi
0x180024751  push    r14
0x180024753  sub     rsp, 370h
0x18002475a  lea     rbp, [rsp+30h]
0x18002475f  mov     rax, cs:__security_cookie
0x180024766  xor     rax, rbp
0x180024769  mov     [rbp+360h+var_30], rax
0x180024770  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_0; "INSERT INTO Property (Property, Value) "...
0x180024777  lea     rax, [rbp+360h+var_1A0]
0x18002477e  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_0+10h; "NTO Property (Property, Value) VALUES ("...
0x180024785  mov     rsi, rdx
0x180024788  movups  xmmword ptr [rbp+360h+szQuery], xmm0
0x18002478f  mov     edx, 2
0x180024794  mov     r14, r8
0x180024797  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_0+20h; "erty (Property, Value) VALUES ('COMPLUS"...
0x18002479e  mov     edi, ecx
0x1800247a0  movups  [rbp+360h+var_230], xmm0
0x1800247a7  lea     rcx, aInsertIntoCust; "INSERT INTO CustomAction (Action, Type,"...
0x1800247ae  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_0+40h; "Value) VALUES ('COMPLUSUNINSTALLPATH', "...
0x1800247b5  lea     r8d, [rdx+7Eh]
0x1800247b9  movups  [rbp+360h+var_240], xmm1
0x1800247c0  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_0+30h; "operty, Value) VALUES ('COMPLUSUNINSTAL"...
0x1800247c7  movups  [rbp+360h+var_210], xmm0
0x1800247ce  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_0+60h; "COMPLUSUNINSTALLPATH', 'rundll32.exe')"
0x1800247d5  movups  [rbp+360h+var_220], xmm1
0x1800247dc  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_0+50h; "ALUES ('COMPLUSUNINSTALLPATH', 'rundll3"...
0x1800247e3  movups  [rbp+360h+var_1F0], xmm0
0x1800247ea  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_0+80h; "PATH', 'rundll32.exe')"
0x1800247f1  movups  [rbp+360h+var_200], xmm1
0x1800247f8  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_0+70h; "NINSTALLPATH', 'rundll32.exe')"
0x1800247ff  movups  [rbp+360h+var_1D0], xmm0
0x180024806  movups  xmm0, xmmword ptr cs:aInsertIntoProp_0+9Eh; "2.exe')"
0x18002480d  movups  [rbp+360h+var_1E0], xmm1
0x180024814  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_0+90h; "rundll32.exe')"
0x18002481b  movups  [rbp+360h+var_1C0], xmm1
0x180024822  movups  [rbp+360h+var_1C0+0Eh], xmm0
0x180024829  movups  xmm0, xmmword ptr [rcx]
0x18002482c  movups  xmm1, xmmword ptr [rcx+10h]
0x180024830  movups  xmmword ptr [rax], xmm0
0x180024833  movups  xmm0, xmmword ptr [rcx+20h]
0x180024837  movups  xmmword ptr [rax+10h], xmm1
0x18002483b  movups  xmm1, xmmword ptr [rcx+30h]
0x18002483f  movups  xmmword ptr [rax+20h], xmm0
0x180024843  movups  xmm0, xmmword ptr [rcx+40h]
0x180024847  movups  xmmword ptr [rax+30h], xmm1
0x18002484b  movups  xmm1, xmmword ptr [rcx+50h]
0x18002484f  movups  xmmword ptr [rax+40h], xmm0
0x180024853  movups  xmm0, xmmword ptr [rcx+60h]
0x180024857  movups  xmmword ptr [rax+50h], xmm1
0x18002485b  movups  xmm1, xmmword ptr [rcx+70h]
0x18002485f  add     rcx, r8
0x180024862  movups  xmmword ptr [rax+60h], xmm0
0x180024866  movups  xmmword ptr [rax+70h], xmm1
0x18002486a  add     rax, r8
0x18002486d  sub     rdx, 1
0x180024871  jnz     short loc_180024829
0x180024873  movups  xmm0, xmmword ptr [rcx]
0x180024876  mov     [rbp+360h+phView], edx
0x180024879  lea     r8, [rbp+360h+phView]; phView
0x18002487d  movups  xmm1, xmmword ptr [rcx+10h]
0x180024881  lea     rdx, [rbp+360h+szQuery]; szQuery
0x180024888  movups  xmmword ptr [rax], xmm0
0x18002488b  movups  xmm0, xmmword ptr [rcx+20h]
0x18002488f  movups  xmmword ptr [rax+10h], xmm1
0x180024893  movups  xmm1, xmmword ptr [rcx+30h]
0x180024897  movups  xmmword ptr [rax+20h], xmm0
0x18002489b  movups  xmm0, xmmword ptr [rcx+40h]
0x18002489f  movups  xmmword ptr [rax+30h], xmm1
0x1800248a3  movups  xmm1, xmmword ptr [rcx+50h]
0x1800248a7  movups  xmmword ptr [rax+40h], xmm0
0x1800248ab  movups  xmm0, xmmword ptr [rcx+5Ah]
0x1800248af  mov     ecx, edi; hDatabase
0x1800248b1  movups  xmmword ptr [rax+50h], xmm1
0x1800248b5  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0; "INSERT INTO InstallExecuteSequence (Act"...
0x1800248bc  movups  xmmword ptr [rax+5Ah], xmm0
0x1800248c0  movzx   eax, word ptr cs:aInsertIntoInst_0+0F0h; ""
0x1800248c7  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+10h; "NTO InstallExecuteSequence (Action, Con"...
0x1800248ce  movups  xmmword ptr [rbp+360h+var_350], xmm1
0x1800248d2  mov     [rbp+360h+var_260], ax
0x1800248d9  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+20h; "allExecuteSequence (Action, Condition, "...
0x1800248e0  movups  xmmword ptr [rbp+360h+var_350+10h], xmm0
0x1800248e4  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+30h; "teSequence (Action, Condition, Sequence"...
0x1800248eb  movups  xmmword ptr [rbp+360h+var_350+20h], xmm1
0x1800248ef  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+40h; "ce (Action, Condition, Sequence) VALUES"...
0x1800248f6  movups  xmmword ptr [rbp+360h+var_350+30h], xmm0
0x1800248fa  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+50h; "on, Condition, Sequence) VALUES ('COMPl"...
0x180024901  movups  xmmword ptr [rbp+360h+var_350+40h], xmm1
0x180024905  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+60h; "ition, Sequence) VALUES ('COMPlusCustom"...
0x18002490c  movups  xmmword ptr [rbp+360h+var_350+50h], xmm0
0x180024910  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+70h; "equence) VALUES ('COMPlusCustomUninstal"...
0x180024917  movups  xmmword ptr [rbp+360h+var_350+60h], xmm1
0x18002491b  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+80h; " VALUES ('COMPlusCustomUninstall', 'REM"...
0x180024922  movups  xmmword ptr [rbp+360h+var_350+70h], xmm0
0x180024929  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+90h; "('COMPlusCustomUninstall', 'REMOVE=\"AL"...
0x180024930  movups  [rbp+360h+var_2D0], xmm1
0x180024937  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+0A0h; "sCustomUninstall', 'REMOVE=\"ALL\"', 57"...
0x18002493e  movups  [rbp+360h+var_2C0], xmm0
0x180024945  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+0B0h; "ninstall', 'REMOVE=\"ALL\"', 5750)"
0x18002494c  movups  [rbp+360h+var_2B0], xmm1
0x180024953  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+0C0h; "', 'REMOVE=\"ALL\"', 5750)"
0x18002495a  movups  [rbp+360h+var_2A0], xmm0
0x180024961  movaps  xmm0, xmmword ptr cs:aInsertIntoInst_0+0D0h; "VE=\"ALL\"', 5750)"
0x180024968  movups  [rbp+360h+var_290], xmm1
0x18002496f  movaps  xmm1, xmmword ptr cs:aInsertIntoInst_0+0E0h; "', 5750)"
0x180024976  movups  [rbp+360h+var_280], xmm0
0x18002497d  movups  [rbp+360h+var_270], xmm1
0x180024984  call    cs:__imp_MsiDatabaseOpenViewW
0x18002498a  mov     ebx, eax
0x18002498c  test    eax, eax
0x18002498e  jnz     loc_180024A55
0x180024994  mov     ecx, [rbp+360h+phView]; hView
0x180024997  xor     edx, edx; hRecord
0x180024999  call    cs:__imp_MsiViewExecute
0x18002499f  mov     ecx, [rbp+360h+phView]; hAny
0x1800249a2  mov     ebx, eax
0x1800249a4  call    cs:__imp_MsiCloseHandle
0x1800249aa  mov     [rbp+360h+phView], 0
0x1800249b1  test    ebx, ebx
0x1800249b3  jnz     loc_180024A57
0x1800249b9  mov     eax, [rsp+390h+var_390]
0x1800249bc  mov     eax, 210h
0x1800249c1  sub     rsp, rax
0x1800249c4  lea     rbx, [rsp+5A0h+var_570]
0x1800249c9  mov     eax, [rbx]
0x1800249cb  mov     r9, r14
0x1800249ce  mov     [rsp+5A0h+var_580], rsi
0x1800249d3  lea     r8, [rbp+360h+var_1A0]; unsigned __int16 *
0x1800249da  mov     edx, 105h; unsigned __int64
0x1800249df  mov     rcx, rbx; unsigned __int16 *
0x1800249e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800249e7  test    eax, eax
0x1800249e9  js      short loc_180024A64
0x1800249eb  lea     r8, [rbp+360h+phView]; phView
0x1800249ef  mov     rdx, rbx; szQuery
0x1800249f2  mov     ecx, edi; hDatabase
0x1800249f4  call    cs:__imp_MsiDatabaseOpenViewW
0x1800249fa  mov     ebx, eax
0x1800249fc  test    eax, eax
0x1800249fe  jnz     short loc_180024A55
0x180024a00  mov     ecx, [rbp+360h+phView]; hView
0x180024a03  xor     edx, edx; hRecord
0x180024a05  call    cs:__imp_MsiViewExecute
0x180024a0b  mov     ecx, [rbp+360h+phView]; hAny
0x180024a0e  mov     ebx, eax
0x180024a10  call    cs:__imp_MsiCloseHandle
0x180024a16  mov     [rbp+360h+phView], 0
0x180024a1d  test    ebx, ebx
0x180024a1f  jnz     short loc_180024A57
0x180024a21  lea     r8, [rbp+360h+phView]; phView
0x180024a25  mov     ecx, edi; hDatabase
0x180024a27  lea     rdx, [rbp+360h+var_350]; szQuery
0x180024a2b  call    cs:__imp_MsiDatabaseOpenViewW
0x180024a31  mov     ebx, eax
0x180024a33  test    eax, eax
0x180024a35  jnz     short loc_180024A55
0x180024a37  mov     ecx, [rbp+360h+phView]; hView
0x180024a3a  xor     edx, edx; hRecord
0x180024a3c  call    cs:__imp_MsiViewExecute
0x180024a42  mov     ecx, [rbp+360h+phView]; hAny
0x180024a45  mov     ebx, eax
0x180024a47  call    cs:__imp_MsiCloseHandle
0x180024a4d  test    ebx, ebx
0x180024a4f  jnz     short loc_180024A57
0x180024a51  xor     eax, eax
0x180024a53  jmp     short loc_180024A64
0x180024a55  test    ebx, ebx
0x180024a57  jle     short loc_180024A62
0x180024a59  movzx   ebx, bx
0x180024a5c  or      ebx, 80070000h
0x180024a62  mov     eax, ebx
0x180024a64  mov     rcx, [rbp+360h+var_30]
0x180024a6b  xor     rcx, rbp; StackCookie
0x180024a6e  call    __security_check_cookie
0x180024a73  lea     rsp, [rbp+340h]
0x180024a7a  pop     r14
0x180024a7c  pop     rdi
0x180024a7d  pop     rsi
0x180024a7e  pop     rbx
0x180024a7f  pop     rbp
0x180024a80  retn
```
