# CGenerateMSI::AddPartitionUninstallAction(ushort const *)

- ea: `0x18002c820`
- end: `0x18002cad3`
- name: `?AddPartitionUninstallAction@CGenerateMSI@@UEAAJPEBG@Z`
- size: `691`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180027418`
- `0x18002c820`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ca30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ca30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c9f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c9f0`
- `msi!__imp_MsiCloseHandle` at `0x18002c9d3`
- `msi!__imp_MsiCloseHandle` at `0x18002ca4c`
- `msi!__imp_MsiCloseHandle` at `0x18002ca88`
- `msi!__imp_MsiCloseHandle` at `0x18002c9d3`
- `msi!__imp_MsiCloseHandle` at `0x18002ca4c`
- `msi!__imp_MsiCloseHandle` at `0x18002ca88`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002c9b1`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002ca25`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002ca6a`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002c9b1`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002ca25`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002ca6a`
- `msi!__imp_MsiViewExecute` at `0x18002c9c7`
- `msi!__imp_MsiViewExecute` at `0x18002ca40`
- `msi!__imp_MsiViewExecute` at `0x18002ca7c`
- `msi!__imp_MsiViewExecute` at `0x18002c9c7`
- `msi!__imp_MsiViewExecute` at `0x18002ca40`
- `msi!__imp_MsiViewExecute` at `0x18002ca7c`

## string_xrefs

- `0x18002c84e`: `INSERT INTO Property (Property, Value) VALUES ('COMPLUSPARTITIONUNINSTALLPATH', 'rundll32.exe')`
- `0x18002c855`: `INSERT INTO CustomAction (Action, Type, Source, Target) VALUES ('COMPlusCustomPartitionUninstall', 50, 'COMPLUSPARTITIONUNINSTALLPATH', 'catsrvut.dll,COMPlusUninstallAction RemovePartition:%s')`
- `0x18002c94b`: `INSERT INTO InstallExecuteSequence (Action, Condition, Sequence) VALUES ('COMPlusCustomPartitionUninstall', 'REMOVE="ALL"', 5755)`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::AddPartitionUninstallAction(CGenerateMSI *this, const unsigned __int16 *a2)
{
  const wchar_t *v2; // rax
  __int64 v4; // rdx
  unsigned __int16 *v6; // rcx
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  const wchar_t *v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  MSIHANDLE v24; // ecx
  signed int v25; // ebx
  bool v26; // cc
  unsigned __int16 *v27; // rax
  WCHAR *v28; // rdi
  MSIHANDLE phView[4]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR szQuery[96]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v32[136]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v33[200]; // [rsp+200h] [rbp+100h] BYREF

  v2 = L"INSERT INTO CustomAction (Action, Type, Source, Target) VALUES ('COMPlusCustomPartitionUninstall', 50, 'COMPLUSPA"
        "RTITIONUNINSTALLPATH', 'catsrvut.dll,COMPlusUninstallAction RemovePartition:%s')";
  wcscpy(szQuery, L"INSERT INTO Property (Property, Value) VALUES ('COMPLUSPARTITIONUNINSTALLPATH', 'rundll32.exe')");
  v4 = 3;
  v6 = v33;
  do
  {
    v7 = *((_OWORD *)v2 + 1);
    *(_OWORD *)v6 = *(_OWORD *)v2;
    v8 = *((_OWORD *)v2 + 2);
    *((_OWORD *)v6 + 1) = v7;
    v9 = *((_OWORD *)v2 + 3);
    *((_OWORD *)v6 + 2) = v8;
    v10 = *((_OWORD *)v2 + 4);
    *((_OWORD *)v6 + 3) = v9;
    v11 = *((_OWORD *)v2 + 5);
    *((_OWORD *)v6 + 4) = v10;
    v12 = *((_OWORD *)v2 + 6);
    *((_OWORD *)v6 + 5) = v11;
    v13 = *((_OWORD *)v2 + 7);
    v2 += 64;
    *((_OWORD *)v6 + 6) = v12;
    *((_OWORD *)v6 + 7) = v13;
    v6 += 64;
    --v4;
  }
  while ( v4 );
  v14 = 2;
  *(_DWORD *)v6 = *(_DWORD *)v2;
  v15 = v32;
  v16 = L"INSERT INTO InstallExecuteSequence (Action, Condition, Sequence) VALUES ('COMPlusCustomPartitionUninstall', 'REM"
         "OVE=\"ALL\"', 5755)";
  do
  {
    v17 = *((_OWORD *)v16 + 1);
    *(_OWORD *)v15 = *(_OWORD *)v16;
    v18 = *((_OWORD *)v16 + 2);
    *((_OWORD *)v15 + 1) = v17;
    v19 = *((_OWORD *)v16 + 3);
    *((_OWORD *)v15 + 2) = v18;
    v20 = *((_OWORD *)v16 + 4);
    *((_OWORD *)v15 + 3) = v19;
    v21 = *((_OWORD *)v16 + 5);
    *((_OWORD *)v15 + 4) = v20;
    v22 = *((_OWORD *)v16 + 6);
    *((_OWORD *)v15 + 5) = v21;
    v23 = *((_OWORD *)v16 + 7);
    v16 += 64;
    *((_OWORD *)v15 + 6) = v22;
    *((_OWORD *)v15 + 7) = v23;
    v15 += 64;
    --v14;
  }
  while ( v14 );
  *(_DWORD *)v15 = *(_DWORD *)v16;
  v24 = *((_DWORD *)this + 16);
  phView[0] = 0;
  v25 = MsiDatabaseOpenViewW(v24, szQuery, phView);
  if ( v25 )
  {
LABEL_15:
    v26 = v25 <= 0;
    goto LABEL_16;
  }
  v25 = MsiViewExecute(phView[0], 0);
  MsiCloseHandle(phView[0]);
  phView[0] = 0;
  v26 = v25 <= 0;
  if ( !v25 )
  {
    v27 = (unsigned __int16 *)CoTaskMemAlloc(0x1D4u);
    v28 = v27;
    if ( !v27 || (int)StringCbPrintfW(v27, 0x1D4u, v33, a2) < 0 )
      return 2147942487LL;
    v25 = MsiDatabaseOpenViewW(*((_DWORD *)this + 16), v28, phView);
    CoTaskMemFree(v28);
    v26 = v25 <= 0;
    if ( !v25 )
    {
      v25 = MsiViewExecute(phView[0], 0);
      MsiCloseHandle(phView[0]);
      phView[0] = 0;
      v26 = v25 <= 0;
      if ( !v25 )
      {
        v25 = MsiDatabaseOpenViewW(*((_DWORD *)this + 16), v32, phView);
        if ( !v25 )
        {
          v25 = MsiViewExecute(phView[0], 0);
          MsiCloseHandle(phView[0]);
          v26 = v25 <= 0;
          if ( !v25 )
            return 0;
          goto LABEL_16;
        }
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  if ( !v26 )
    return (unsigned __int16)v25 | 0x80070000;
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x18002c820  mov     [rsp-8+arg_10], rbx
0x18002c825  mov     [rsp-8+arg_18], rsi
0x18002c82a  push    rbp
0x18002c82b  push    rdi
0x18002c82c  push    r14
0x18002c82e  lea     rbp, [rsp-2A0h]
0x18002c836  sub     rsp, 3A0h
0x18002c83d  mov     rax, cs:__security_cookie
0x18002c844  xor     rax, rsp
0x18002c847  mov     [rbp+2B0h+var_20], rax
0x18002c84e  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_1; "INSERT INTO Property (Property, Value) "...
0x18002c855  lea     rax, aInsertIntoCust_0; "INSERT INTO CustomAction (Action, Type,"...
0x18002c85c  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_1+10h; "NTO Property (Property, Value) VALUES ("...
0x18002c863  mov     r14, rdx
0x18002c866  movups  xmmword ptr [rsp+3B0h+szQuery], xmm0
0x18002c86b  mov     edx, 3
0x18002c870  mov     rsi, rcx
0x18002c873  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_1+20h; "erty (Property, Value) VALUES ('COMPLUS"...
0x18002c87a  lea     rcx, [rbp+2B0h+var_1B0]
0x18002c881  movups  [rsp+3B0h+var_370], xmm1
0x18002c886  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_1+30h; "operty, Value) VALUES ('COMPLUSPARTITIO"...
0x18002c88d  lea     r8d, [rdx+7Dh]
0x18002c891  movups  [rsp+3B0h+var_360], xmm0
0x18002c896  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_1+40h; "Value) VALUES ('COMPLUSPARTITIONUNINSTA"...
0x18002c89d  movups  [rsp+3B0h+var_350], xmm1
0x18002c8a2  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_1+50h; "ALUES ('COMPLUSPARTITIONUNINSTALLPATH',"...
0x18002c8a9  movups  [rsp+3B0h+var_340], xmm0
0x18002c8ae  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_1+60h; "COMPLUSPARTITIONUNINSTALLPATH', 'rundll"...
0x18002c8b5  movups  [rbp+2B0h+var_330], xmm1
0x18002c8b9  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_1+70h; "ARTITIONUNINSTALLPATH', 'rundll32.exe')"
0x18002c8c0  movups  [rbp+2B0h+var_320], xmm0
0x18002c8c4  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_1+80h; "UNINSTALLPATH', 'rundll32.exe')"
0x18002c8cb  movups  [rbp+2B0h+var_310], xmm1
0x18002c8cf  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_1+90h; "LPATH', 'rundll32.exe')"
0x18002c8d6  movups  [rbp+2B0h+var_300], xmm0
0x18002c8da  movaps  xmm0, xmmword ptr cs:aInsertIntoProp_1+0A0h; "'rundll32.exe')"
0x18002c8e1  movups  [rbp+2B0h+var_2F0], xmm1
0x18002c8e5  movaps  xmm1, xmmword ptr cs:aInsertIntoProp_1+0B0h; "2.exe')"
0x18002c8ec  movups  [rbp+2B0h+var_2E0], xmm0
0x18002c8f0  movups  [rbp+2B0h+var_2D0], xmm1
0x18002c8f4  movups  xmm0, xmmword ptr [rax]
0x18002c8f7  movups  xmm1, xmmword ptr [rax+10h]
0x18002c8fb  movups  xmmword ptr [rcx], xmm0
0x18002c8fe  movups  xmm0, xmmword ptr [rax+20h]
0x18002c902  movups  xmmword ptr [rcx+10h], xmm1
0x18002c906  movups  xmm1, xmmword ptr [rax+30h]
0x18002c90a  movups  xmmword ptr [rcx+20h], xmm0
0x18002c90e  movups  xmm0, xmmword ptr [rax+40h]
0x18002c912  movups  xmmword ptr [rcx+30h], xmm1
0x18002c916  movups  xmm1, xmmword ptr [rax+50h]
0x18002c91a  movups  xmmword ptr [rcx+40h], xmm0
0x18002c91e  movups  xmm0, xmmword ptr [rax+60h]
0x18002c922  movups  xmmword ptr [rcx+50h], xmm1
0x18002c926  movups  xmm1, xmmword ptr [rax+70h]
0x18002c92a  add     rax, r8
0x18002c92d  movups  xmmword ptr [rcx+60h], xmm0
0x18002c931  movups  xmmword ptr [rcx+70h], xmm1
0x18002c935  add     rcx, r8
0x18002c938  sub     rdx, 1
0x18002c93c  jnz     short loc_18002C8F4
0x18002c93e  mov     eax, [rax]
0x18002c940  mov     edx, 2
0x18002c945  mov     [rcx], eax
0x18002c947  lea     rcx, [rbp+2B0h+var_2C0]
0x18002c94b  lea     rax, aInsertIntoInst; "INSERT INTO InstallExecuteSequence (Act"...
0x18002c952  movups  xmm0, xmmword ptr [rax]
0x18002c955  movups  xmm1, xmmword ptr [rax+10h]
0x18002c959  movups  xmmword ptr [rcx], xmm0
0x18002c95c  movups  xmm0, xmmword ptr [rax+20h]
0x18002c960  movups  xmmword ptr [rcx+10h], xmm1
0x18002c964  movups  xmm1, xmmword ptr [rax+30h]
0x18002c968  movups  xmmword ptr [rcx+20h], xmm0
0x18002c96c  movups  xmm0, xmmword ptr [rax+40h]
0x18002c970  movups  xmmword ptr [rcx+30h], xmm1
0x18002c974  movups  xmm1, xmmword ptr [rax+50h]
0x18002c978  movups  xmmword ptr [rcx+40h], xmm0
0x18002c97c  movups  xmm0, xmmword ptr [rax+60h]
0x18002c980  movups  xmmword ptr [rcx+50h], xmm1
0x18002c984  movups  xmm1, xmmword ptr [rax+70h]
0x18002c988  add     rax, r8
0x18002c98b  movups  xmmword ptr [rcx+60h], xmm0
0x18002c98f  movups  xmmword ptr [rcx+70h], xmm1
0x18002c993  add     rcx, r8
0x18002c996  sub     rdx, 1
0x18002c99a  jnz     short loc_18002C952
0x18002c99c  mov     eax, [rax]
0x18002c99e  lea     r8, [rsp+3B0h+phView]; phView
0x18002c9a3  mov     [rcx], eax
0x18002c9a5  mov     ecx, [rsi+40h]; hDatabase
0x18002c9a8  mov     [rsp+3B0h+phView], edx
0x18002c9ac  lea     rdx, [rsp+3B0h+szQuery]; szQuery
0x18002c9b1  call    cs:__imp_MsiDatabaseOpenViewW
0x18002c9b7  mov     ebx, eax
0x18002c9b9  test    eax, eax
0x18002c9bb  jnz     loc_18002CA9D
0x18002c9c1  mov     ecx, [rsp+3B0h+phView]; hView
0x18002c9c5  xor     edx, edx; hRecord
0x18002c9c7  call    cs:__imp_MsiViewExecute
0x18002c9cd  mov     ecx, [rsp+3B0h+phView]; hAny
0x18002c9d1  mov     ebx, eax
0x18002c9d3  call    cs:__imp_MsiCloseHandle
0x18002c9d9  mov     [rsp+3B0h+phView], 0
0x18002c9e1  test    ebx, ebx
0x18002c9e3  jnz     loc_18002CA9F
0x18002c9e9  mov     ebx, 1D4h
0x18002c9ee  mov     ecx, ebx; cb
0x18002c9f0  call    cs:__imp_CoTaskMemAlloc
0x18002c9f6  mov     rdi, rax
0x18002c9f9  test    rax, rax
0x18002c9fc  jz      loc_18002CA96
0x18002ca02  mov     r9, r14
0x18002ca05  lea     r8, [rbp+2B0h+var_1B0]; unsigned __int16 *
0x18002ca0c  mov     edx, ebx; unsigned __int64
0x18002ca0e  mov     rcx, rax; unsigned __int16 *
0x18002ca11  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ca16  test    eax, eax
0x18002ca18  js      short loc_18002CA96
0x18002ca1a  mov     ecx, [rsi+40h]; hDatabase
0x18002ca1d  lea     r8, [rsp+3B0h+phView]; phView
0x18002ca22  mov     rdx, rdi; szQuery
0x18002ca25  call    cs:__imp_MsiDatabaseOpenViewW
0x18002ca2b  mov     rcx, rdi; pv
0x18002ca2e  mov     ebx, eax
0x18002ca30  call    cs:__imp_CoTaskMemFree
0x18002ca36  test    ebx, ebx
0x18002ca38  jnz     short loc_18002CA9F
0x18002ca3a  mov     ecx, [rsp+3B0h+phView]; hView
0x18002ca3e  xor     edx, edx; hRecord
0x18002ca40  call    cs:__imp_MsiViewExecute
0x18002ca46  mov     ecx, [rsp+3B0h+phView]; hAny
0x18002ca4a  mov     ebx, eax
0x18002ca4c  call    cs:__imp_MsiCloseHandle
0x18002ca52  mov     [rsp+3B0h+phView], 0
0x18002ca5a  test    ebx, ebx
0x18002ca5c  jnz     short loc_18002CA9F
0x18002ca5e  mov     ecx, [rsi+40h]; hDatabase
0x18002ca61  lea     r8, [rsp+3B0h+phView]; phView
0x18002ca66  lea     rdx, [rbp+2B0h+var_2C0]; szQuery
0x18002ca6a  call    cs:__imp_MsiDatabaseOpenViewW
0x18002ca70  mov     ebx, eax
0x18002ca72  test    eax, eax
0x18002ca74  jnz     short loc_18002CA9D
0x18002ca76  mov     ecx, [rsp+3B0h+phView]; hView
0x18002ca7a  xor     edx, edx; hRecord
0x18002ca7c  call    cs:__imp_MsiViewExecute
0x18002ca82  mov     ecx, [rsp+3B0h+phView]; hAny
0x18002ca86  mov     ebx, eax
0x18002ca88  call    cs:__imp_MsiCloseHandle
0x18002ca8e  test    ebx, ebx
0x18002ca90  jnz     short loc_18002CA9F
0x18002ca92  xor     eax, eax
0x18002ca94  jmp     short loc_18002CAAC
0x18002ca96  mov     eax, 80070057h
0x18002ca9b  jmp     short loc_18002CAAC
0x18002ca9d  test    ebx, ebx
0x18002ca9f  jle     short loc_18002CAAA
0x18002caa1  movzx   ebx, bx
0x18002caa4  or      ebx, 80070000h
0x18002caaa  mov     eax, ebx
0x18002caac  mov     rcx, [rbp+2B0h+var_20]
0x18002cab3  xor     rcx, rsp; StackCookie
0x18002cab6  call    __security_check_cookie
0x18002cabb  lea     r11, [rsp+3B0h+var_10]
0x18002cac3  mov     rbx, [r11+30h]
0x18002cac7  mov     rsi, [r11+38h]
0x18002cacb  mov     rsp, r11
0x18002cace  pop     r14
0x18002cad0  pop     rdi
0x18002cad1  pop     rbp
0x18002cad2  retn
```
