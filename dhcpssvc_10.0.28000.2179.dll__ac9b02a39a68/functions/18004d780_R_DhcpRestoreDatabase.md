# R_DhcpRestoreDatabase

- ea: `0x18004d780`
- end: `0x18004d9c5`
- name: `R_DhcpRestoreDatabase`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002030`
- `0x1800025a4`
- `0x180003228`
- `0x18004d2b4`
- `0x18004d780`
- `0x18008f5b4`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18004d99c`
- `ADVAPI32!RegSetValueExW` at `0x18004d99c`
- `KERNEL32!LocalFree` at `0x18004d874`
- `KERNEL32!LocalFree` at `0x18004d8e5`
- `KERNEL32!LocalFree` at `0x18004d94e`
- `KERNEL32!LocalFree` at `0x18004d874`
- `KERNEL32!LocalFree` at `0x18004d8e5`
- `KERNEL32!LocalFree` at `0x18004d94e`
- `KERNEL32!HeapFree` at `0x18004d81e`
- `KERNEL32!HeapFree` at `0x18004d81e`

## string_xrefs

- `0x18004d98a`: `RestoreDatabasePath`

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
0x18004d780  mov     [rsp-28h+arg_0], rbx
0x18004d785  push    rbp
0x18004d786  push    rsi
0x18004d787  push    rdi
0x18004d788  push    r14
0x18004d78a  push    r15
0x18004d78c  mov     rbp, rsp
0x18004d78f  sub     rsp, 40h
0x18004d793  xor     r15d, r15d
0x18004d796  mov     r14, rdx
0x18004d799  mov     [rbp+arg_10], r15d
0x18004d79d  mov     [rbp+hMem], r15
0x18004d7a1  mov     [rbp+arg_18], r15
0x18004d7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d7ac  lea     rax, WPP_GLOBAL_Control
0x18004d7b3  cmp     rcx, rax
0x18004d7b6  jz      short loc_18004D7D5
0x18004d7b8  test    dword ptr [rcx+1Ch], 200h
0x18004d7bf  jz      short loc_18004D7D5
0x18004d7c1  mov     rcx, [rcx+10h]
0x18004d7c5  lea     edx, [r15+18h]
0x18004d7c9  lea     r8, WPP_cd9a90b2784e355e97772e1cf15e838a_Traceguids
0x18004d7d0  call    WPP_SF_
0x18004d7d5  mov     ecx, 0A0000000h
0x18004d7da  call    DhcpApiAccessCheck
0x18004d7df  test    eax, eax
0x18004d7e1  jnz     loc_18004D9B3
0x18004d7e7  test    r14, r14
0x18004d7ea  jnz     short loc_18004D7F5
0x18004d7ec  lea     eax, [r14+57h]
0x18004d7f0  jmp     loc_18004D9B3
0x18004d7f5  mov     rcx, cs:DhcpGlobalOemJetBackupPath; SourceString
0x18004d7fc  xor     edx, edx
0x18004d7fe  call    DhcpOemToUnicode
0x18004d803  test    rax, rax
0x18004d806  jnz     short loc_18004D812
0x18004d808  mov     eax, 54Fh
0x18004d80d  jmp     loc_18004D9B3
0x18004d812  mov     rcx, cs:gDhcpHeap; hHeap
0x18004d819  mov     r8, rax; lpMem
0x18004d81c  xor     edx, edx; dwFlags
0x18004d81e  call    cs:__imp_HeapFree
0x18004d825  nop     dword ptr [rax+rax+00h]
0x18004d82a  lea     r9, aDhcpcfg; "DhcpCfg"
0x18004d831  mov     r8, r14
0x18004d834  lea     rdx, a12; "%1\\%2"
0x18004d83b  lea     rcx, [rbp+hMem]
0x18004d83f  call    FormatMessageForStrings
0x18004d844  test    eax, eax
0x18004d846  jnz     short loc_18004D88E
0x18004d848  mov     rcx, [rbp+hMem]
0x18004d84c  lea     r9, [rbp+arg_10]
0x18004d850  call    PerformAccessCheckAgainstFileObject
0x18004d855  mov     ebx, eax
0x18004d857  mov     edi, 1
0x18004d85c  add     eax, 0FFFFFFFEh
0x18004d85f  cmp     eax, edi
0x18004d861  ja      short loc_18004D86D
0x18004d863  mov     ebx, r15d
0x18004d866  mov     [rbp+arg_10], edi
0x18004d869  mov     esi, edi
0x18004d86b  jmp     short loc_18004D870
0x18004d86d  mov     esi, [rbp+arg_10]
0x18004d870  mov     rcx, [rbp+hMem]; hMem
0x18004d874  call    cs:__imp_LocalFree
0x18004d87b  nop     dword ptr [rax+rax+00h]
0x18004d880  mov     [rbp+hMem], r15
0x18004d884  test    ebx, ebx
0x18004d886  jnz     loc_18004D9B1
0x18004d88c  jmp     short loc_18004D898
0x18004d88e  mov     edi, 1
0x18004d893  mov     esi, edi
0x18004d895  mov     [rbp+arg_10], edi
0x18004d898  test    esi, esi
0x18004d89a  jz      loc_18004D9AC
0x18004d8a0  mov     r9, cs:DhcpGlobalOemDatabaseName
0x18004d8a7  lea     rdx, a1New2S; "%1\\new\\%2!S!"
0x18004d8ae  mov     r8, r14
0x18004d8b1  lea     rcx, [rbp+arg_18]
0x18004d8b5  call    FormatMessageForStrings
0x18004d8ba  test    eax, eax
0x18004d8bc  jnz     short loc_18004D8FF
0x18004d8be  mov     rcx, [rbp+arg_18]
0x18004d8c2  lea     r9, [rbp+arg_10]
0x18004d8c6  call    PerformAccessCheckAgainstFileObject
0x18004d8cb  mov     ebx, eax
0x18004d8cd  add     eax, 0FFFFFFFEh
0x18004d8d0  cmp     eax, edi
0x18004d8d2  ja      short loc_18004D8DE
0x18004d8d4  mov     ebx, r15d
0x18004d8d7  mov     [rbp+arg_10], edi
0x18004d8da  mov     esi, edi
0x18004d8dc  jmp     short loc_18004D8E1
0x18004d8de  mov     esi, [rbp+arg_10]
0x18004d8e1  mov     rcx, [rbp+arg_18]; hMem
0x18004d8e5  call    cs:__imp_LocalFree
0x18004d8ec  nop     dword ptr [rax+rax+00h]
0x18004d8f1  mov     [rbp+arg_18], r15
0x18004d8f5  test    ebx, ebx
0x18004d8f7  jnz     loc_18004D9B1
0x18004d8fd  jmp     short loc_18004D904
0x18004d8ff  mov     esi, edi
0x18004d901  mov     [rbp+arg_10], edi
0x18004d904  test    esi, esi
0x18004d906  jz      loc_18004D9AC
0x18004d90c  mov     r9, cs:DhcpGlobalOemDatabaseName
0x18004d913  lea     rdx, a12S; "%1\\%2!S!"
0x18004d91a  mov     r8, r14
0x18004d91d  lea     rcx, [rbp+arg_18]
0x18004d921  call    FormatMessageForStrings
0x18004d926  test    eax, eax
0x18004d928  jnz     short loc_18004D964
0x18004d92a  mov     rcx, [rbp+arg_18]
0x18004d92e  lea     r9, [rbp+arg_10]
0x18004d932  call    PerformAccessCheckAgainstFileObject
0x18004d937  mov     ebx, eax
0x18004d939  add     eax, 0FFFFFFFEh
0x18004d93c  cmp     eax, edi
0x18004d93e  ja      short loc_18004D947
0x18004d940  mov     ebx, r15d
0x18004d943  mov     esi, edi
0x18004d945  jmp     short loc_18004D94A
0x18004d947  mov     esi, [rbp+arg_10]
0x18004d94a  mov     rcx, [rbp+arg_18]; hMem
0x18004d94e  call    cs:__imp_LocalFree
0x18004d955  nop     dword ptr [rax+rax+00h]
0x18004d95a  mov     [rbp+arg_18], r15
0x18004d95e  test    ebx, ebx
0x18004d960  jnz     short loc_18004D9B1
0x18004d962  jmp     short loc_18004D966
0x18004d964  mov     esi, edi
0x18004d966  test    esi, esi
0x18004d968  jz      short loc_18004D9AC
0x18004d96a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d96e  inc     rax
0x18004d971  cmp     [r14+rax*2], r15w
0x18004d976  jnz     short loc_18004D96E
0x18004d978  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18004d97f  lea     eax, ds:2[rax*2]
0x18004d986  mov     [rsp+40h+cbData], eax; cbData
0x18004d98a  lea     rdx, aRestoredatabas; "RestoreDatabasePath"
0x18004d991  mov     r9d, edi; dwType
0x18004d994  mov     [rsp+40h+lpData], r14; lpData
0x18004d999  xor     r8d, r8d; Reserved
0x18004d99c  call    cs:__imp_RegSetValueExW
0x18004d9a3  nop     dword ptr [rax+rax+00h]
0x18004d9a8  mov     ebx, eax
0x18004d9aa  jmp     short loc_18004D9B1
0x18004d9ac  mov     ebx, 5
0x18004d9b1  mov     eax, ebx
0x18004d9b3  mov     rbx, [rsp+40h+arg_0]
0x18004d9b8  add     rsp, 40h
0x18004d9bc  pop     r15
0x18004d9be  pop     r14
0x18004d9c0  pop     rdi
0x18004d9c1  pop     rsi
0x18004d9c2  pop     rbp
0x18004d9c3  retn
```
