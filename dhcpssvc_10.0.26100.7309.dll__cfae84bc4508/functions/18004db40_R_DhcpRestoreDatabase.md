# R_DhcpRestoreDatabase

- ea: `0x18004db40`
- end: `0x18004dd85`
- name: `R_DhcpRestoreDatabase`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002040`
- `0x1800025cc`
- `0x18000323c`
- `0x18004d67c`
- `0x18004db40`
- `0x18008f418`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004dd5c`
- `ADVAPI32!RegSetValueExW` at `0x18004dd5c`
- `KERNEL32!LocalFree` at `0x18004dc34`
- `KERNEL32!LocalFree` at `0x18004dca5`
- `KERNEL32!LocalFree` at `0x18004dd0e`
- `KERNEL32!LocalFree` at `0x18004dc34`
- `KERNEL32!LocalFree` at `0x18004dca5`
- `KERNEL32!LocalFree` at `0x18004dd0e`
- `KERNEL32!HeapFree` at `0x18004dbde`
- `KERNEL32!HeapFree` at `0x18004dbde`

## string_xrefs

- `0x18004dd4a`: `RestoreDatabasePath`

## pseudocode

```c
__int64 __fastcall R_DhcpRestoreDatabase(__int64 a1, const BYTE *a2)
{
  __int64 result; // rax
  void *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // esi
  __int64 v15; // rax
  HLOCAL hMem[2]; // [rsp+30h] [rbp-10h] BYREF
  int v17; // [rsp+80h] [rbp+40h] BYREF
  HLOCAL v18; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  hMem[0] = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_cd9a90b2784e355e97772e1cf15e838a_Traceguids);
  result = DhcpApiAccessCheck(0xA0000000);
  if ( !(_DWORD)result )
  {
    if ( !a2 )
      return 87;
    v4 = (void *)DhcpOemToUnicode(DhcpGlobalOemJetBackupPath);
    if ( !v4 )
      return 1359;
    HeapFree(gDhcpHeap, 0, v4);
    if ( (unsigned int)FormatMessageForStrings(hMem, L"%1\\%2", a2, L"DhcpCfg") )
    {
      v8 = 1;
      v17 = 1;
    }
    else
    {
      v7 = PerformAccessCheckAgainstFileObject((const WCHAR *)hMem[0], v5, v6, &v17);
      if ( v7 - 2 > 1 )
      {
        v8 = v17;
      }
      else
      {
        v7 = 0;
        v17 = 1;
        v8 = 1;
      }
      LocalFree(hMem[0]);
      hMem[0] = 0;
      if ( v7 )
        return v7;
    }
    if ( !v8 )
      return 5;
    if ( (unsigned int)FormatMessageForStrings(&v18, L"%1\\new\\%2!S!", a2, DhcpGlobalOemDatabaseName) )
    {
      v11 = 1;
      v17 = 1;
    }
    else
    {
      v7 = PerformAccessCheckAgainstFileObject((const WCHAR *)v18, v9, v10, &v17);
      if ( v7 - 2 > 1 )
      {
        v11 = v17;
      }
      else
      {
        v7 = 0;
        v17 = 1;
        v11 = 1;
      }
      LocalFree(v18);
      v18 = 0;
      if ( v7 )
        return v7;
    }
    if ( !v11 )
      return 5;
    if ( (unsigned int)FormatMessageForStrings(&v18, L"%1\\%2!S!", a2, DhcpGlobalOemDatabaseName) )
    {
      v14 = 1;
    }
    else
    {
      v7 = PerformAccessCheckAgainstFileObject((const WCHAR *)v18, v12, v13, &v17);
      if ( v7 - 2 > 1 )
      {
        v14 = v17;
      }
      else
      {
        v7 = 0;
        v14 = 1;
      }
      LocalFree(v18);
      v18 = 0;
      if ( v7 )
        return v7;
    }
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&a2[2 * v15] );
      return (unsigned int)RegSetValueExW(DhcpGlobalRegParam, L"RestoreDatabasePath", 0, 1u, a2, 2 * v15 + 2);
    }
    else
    {
      return 5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004db40  mov     [rsp-28h+arg_0], rbx
0x18004db45  push    rbp
0x18004db46  push    rsi
0x18004db47  push    rdi
0x18004db48  push    r14
0x18004db4a  push    r15
0x18004db4c  mov     rbp, rsp
0x18004db4f  sub     rsp, 40h
0x18004db53  xor     r15d, r15d
0x18004db56  mov     r14, rdx
0x18004db59  mov     [rbp+arg_10], r15d
0x18004db5d  mov     [rbp+hMem], r15
0x18004db61  mov     [rbp+arg_18], r15
0x18004db65  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db6c  lea     rax, WPP_GLOBAL_Control
0x18004db73  cmp     rcx, rax
0x18004db76  jz      short loc_18004DB95
0x18004db78  test    dword ptr [rcx+1Ch], 200h
0x18004db7f  jz      short loc_18004DB95
0x18004db81  mov     rcx, [rcx+10h]
0x18004db85  lea     edx, [r15+18h]
0x18004db89  lea     r8, WPP_cd9a90b2784e355e97772e1cf15e838a_Traceguids
0x18004db90  call    WPP_SF_
0x18004db95  mov     ecx, 0A0000000h
0x18004db9a  call    DhcpApiAccessCheck
0x18004db9f  test    eax, eax
0x18004dba1  jnz     loc_18004DD73
0x18004dba7  test    r14, r14
0x18004dbaa  jnz     short loc_18004DBB5
0x18004dbac  lea     eax, [r14+57h]
0x18004dbb0  jmp     loc_18004DD73
0x18004dbb5  mov     rcx, cs:DhcpGlobalOemJetBackupPath; SourceString
0x18004dbbc  xor     edx, edx
0x18004dbbe  call    DhcpOemToUnicode
0x18004dbc3  test    rax, rax
0x18004dbc6  jnz     short loc_18004DBD2
0x18004dbc8  mov     eax, 54Fh
0x18004dbcd  jmp     loc_18004DD73
0x18004dbd2  mov     rcx, cs:gDhcpHeap; hHeap
0x18004dbd9  mov     r8, rax; lpMem
0x18004dbdc  xor     edx, edx; dwFlags
0x18004dbde  call    cs:__imp_HeapFree
0x18004dbe5  nop     dword ptr [rax+rax+00h]
0x18004dbea  lea     r9, aDhcpcfg; "DhcpCfg"
0x18004dbf1  mov     r8, r14
0x18004dbf4  lea     rdx, a12; "%1\\%2"
0x18004dbfb  lea     rcx, [rbp+hMem]
0x18004dbff  call    FormatMessageForStrings
0x18004dc04  test    eax, eax
0x18004dc06  jnz     short loc_18004DC4E
0x18004dc08  mov     rcx, [rbp+hMem]
0x18004dc0c  lea     r9, [rbp+arg_10]
0x18004dc10  call    PerformAccessCheckAgainstFileObject
0x18004dc15  mov     ebx, eax
0x18004dc17  mov     edi, 1
0x18004dc1c  add     eax, 0FFFFFFFEh
0x18004dc1f  cmp     eax, edi
0x18004dc21  ja      short loc_18004DC2D
0x18004dc23  mov     ebx, r15d
0x18004dc26  mov     [rbp+arg_10], edi
0x18004dc29  mov     esi, edi
0x18004dc2b  jmp     short loc_18004DC30
0x18004dc2d  mov     esi, [rbp+arg_10]
0x18004dc30  mov     rcx, [rbp+hMem]; hMem
0x18004dc34  call    cs:__imp_LocalFree
0x18004dc3b  nop     dword ptr [rax+rax+00h]
0x18004dc40  mov     [rbp+hMem], r15
0x18004dc44  test    ebx, ebx
0x18004dc46  jnz     loc_18004DD71
0x18004dc4c  jmp     short loc_18004DC58
0x18004dc4e  mov     edi, 1
0x18004dc53  mov     esi, edi
0x18004dc55  mov     [rbp+arg_10], edi
0x18004dc58  test    esi, esi
0x18004dc5a  jz      loc_18004DD6C
0x18004dc60  mov     r9, cs:DhcpGlobalOemDatabaseName
0x18004dc67  lea     rdx, a1New2S; "%1\\new\\%2!S!"
0x18004dc6e  mov     r8, r14
0x18004dc71  lea     rcx, [rbp+arg_18]
0x18004dc75  call    FormatMessageForStrings
0x18004dc7a  test    eax, eax
0x18004dc7c  jnz     short loc_18004DCBF
0x18004dc7e  mov     rcx, [rbp+arg_18]
0x18004dc82  lea     r9, [rbp+arg_10]
0x18004dc86  call    PerformAccessCheckAgainstFileObject
0x18004dc8b  mov     ebx, eax
0x18004dc8d  add     eax, 0FFFFFFFEh
0x18004dc90  cmp     eax, edi
0x18004dc92  ja      short loc_18004DC9E
0x18004dc94  mov     ebx, r15d
0x18004dc97  mov     [rbp+arg_10], edi
0x18004dc9a  mov     esi, edi
0x18004dc9c  jmp     short loc_18004DCA1
0x18004dc9e  mov     esi, [rbp+arg_10]
0x18004dca1  mov     rcx, [rbp+arg_18]; hMem
0x18004dca5  call    cs:__imp_LocalFree
0x18004dcac  nop     dword ptr [rax+rax+00h]
0x18004dcb1  mov     [rbp+arg_18], r15
0x18004dcb5  test    ebx, ebx
0x18004dcb7  jnz     loc_18004DD71
0x18004dcbd  jmp     short loc_18004DCC4
0x18004dcbf  mov     esi, edi
0x18004dcc1  mov     [rbp+arg_10], edi
0x18004dcc4  test    esi, esi
0x18004dcc6  jz      loc_18004DD6C
0x18004dccc  mov     r9, cs:DhcpGlobalOemDatabaseName
0x18004dcd3  lea     rdx, a12S; "%1\\%2!S!"
0x18004dcda  mov     r8, r14
0x18004dcdd  lea     rcx, [rbp+arg_18]
0x18004dce1  call    FormatMessageForStrings
0x18004dce6  test    eax, eax
0x18004dce8  jnz     short loc_18004DD24
0x18004dcea  mov     rcx, [rbp+arg_18]
0x18004dcee  lea     r9, [rbp+arg_10]
0x18004dcf2  call    PerformAccessCheckAgainstFileObject
0x18004dcf7  mov     ebx, eax
0x18004dcf9  add     eax, 0FFFFFFFEh
0x18004dcfc  cmp     eax, edi
0x18004dcfe  ja      short loc_18004DD07
0x18004dd00  mov     ebx, r15d
0x18004dd03  mov     esi, edi
0x18004dd05  jmp     short loc_18004DD0A
0x18004dd07  mov     esi, [rbp+arg_10]
0x18004dd0a  mov     rcx, [rbp+arg_18]; hMem
0x18004dd0e  call    cs:__imp_LocalFree
0x18004dd15  nop     dword ptr [rax+rax+00h]
0x18004dd1a  mov     [rbp+arg_18], r15
0x18004dd1e  test    ebx, ebx
0x18004dd20  jnz     short loc_18004DD71
0x18004dd22  jmp     short loc_18004DD26
0x18004dd24  mov     esi, edi
0x18004dd26  test    esi, esi
0x18004dd28  jz      short loc_18004DD6C
0x18004dd2a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004dd2e  inc     rax
0x18004dd31  cmp     [r14+rax*2], r15w
0x18004dd36  jnz     short loc_18004DD2E
0x18004dd38  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18004dd3f  lea     eax, ds:2[rax*2]
0x18004dd46  mov     [rsp+40h+cbData], eax; cbData
0x18004dd4a  lea     rdx, aRestoredatabas; "RestoreDatabasePath"
0x18004dd51  mov     r9d, edi; dwType
0x18004dd54  mov     [rsp+40h+lpData], r14; lpData
0x18004dd59  xor     r8d, r8d; Reserved
0x18004dd5c  call    cs:__imp_RegSetValueExW
0x18004dd63  nop     dword ptr [rax+rax+00h]
0x18004dd68  mov     ebx, eax
0x18004dd6a  jmp     short loc_18004DD71
0x18004dd6c  mov     ebx, 5
0x18004dd71  mov     eax, ebx
0x18004dd73  mov     rbx, [rsp+40h+arg_0]
0x18004dd78  add     rsp, 40h
0x18004dd7c  pop     r15
0x18004dd7e  pop     r14
0x18004dd80  pop     rdi
0x18004dd81  pop     rsi
0x18004dd82  pop     rbp
0x18004dd83  retn
```
