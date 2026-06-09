# DhcpRegGetExpandValue

- ea: `0x18001db9c`
- end: `0x18001ddd8`
- name: `DhcpRegGetExpandValue`
- size: `572`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001cdc8`
- `0x1800666e0`

## callees

- `0x18001db9c`
- `0x18001dde0`
- `0x18008f6d8`
- `0x1800cda92`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001dcee`
- `ADVAPI32!RegSetValueExW` at `0x18001dcee`
- `KERNEL32!HeapAlloc` at `0x18001dc33`
- `KERNEL32!HeapAlloc` at `0x18001dc87`
- `KERNEL32!HeapAlloc` at `0x18001dc33`
- `KERNEL32!HeapAlloc` at `0x18001dc87`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001dd0d`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001dd0d`
- `KERNEL32!GetLastError` at `0x18001dd39`
- `KERNEL32!GetLastError` at `0x18001dd39`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001dca9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001dca9`
- `KERNEL32!HeapFree` at `0x18001dd5d`
- `KERNEL32!HeapFree` at `0x18001dd7a`
- `KERNEL32!HeapFree` at `0x18001dd97`
- `KERNEL32!HeapFree` at `0x18001ddb4`
- `KERNEL32!HeapFree` at `0x18001dd5d`
- `KERNEL32!HeapFree` at `0x18001dd7a`
- `KERNEL32!HeapFree` at `0x18001dd97`
- `KERNEL32!HeapFree` at `0x18001ddb4`

## string_xrefs

- `0x18001dc4e`: `DatabasePath`
- `0x18001dc61`: `BackupDatabasePath`

## pseudocode

```c
__int64 __fastcall DhcpRegGetExpandValue(LPCWSTR lpValueName, DWORD a2, CHAR **a3)
{
  CHAR *v4; // r14
  CHAR *v5; // rsi
  BYTE *lpData; // rbp
  DWORD Value; // ebx
  __int64 v8; // r15
  __int64 v9; // rax
  DWORD v10; // r12d
  WCHAR *v11; // rax
  DWORD v12; // eax
  DWORD v13; // eax

  *a3 = 0;
  v4 = 0;
  v5 = 0;
  lpData = 0;
  Value = DhcpRegGetValue(DhcpGlobalRegParam, lpValueName);
  if ( !Value )
  {
    v4 = (CHAR *)DhcpUnicodeToOem(0);
    if ( !v4 )
    {
      Value = 8;
      goto LABEL_20;
    }
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( v4[v9] );
    v10 = v9 + 261;
    v5 = (CHAR *)HeapAlloc(gDhcpHeap, 8u, (unsigned int)(v9 + 261));
    if ( !v5 )
      goto LABEL_7;
    if ( wcscmp_0(lpValueName, L"DatabasePath") && wcscmp_0(lpValueName, L"BackupDatabasePath") )
      goto LABEL_15;
    v11 = (WCHAR *)HeapAlloc(gDhcpHeap, 8u, 2LL * v10);
    lpData = (BYTE *)v11;
    if ( !v11 )
    {
LABEL_7:
      Value = 8;
      goto LABEL_20;
    }
    v12 = ExpandEnvironmentStringsW(0, v11, v10);
    if ( !v12 )
    {
LABEL_19:
      Value = GetLastError();
      goto LABEL_20;
    }
    if ( v12 > v10 )
    {
LABEL_18:
      Value = 208;
      goto LABEL_20;
    }
    do
      ++v8;
    while ( *(_WORD *)&lpData[2 * v8] );
    Value = RegSetValueExW(DhcpGlobalRegParam, lpValueName, 0, a2, lpData, 2 * v8 + 2);
    if ( !Value )
    {
LABEL_15:
      v13 = ExpandEnvironmentStringsA(v4, v5, v10);
      if ( v13 )
      {
        if ( v13 <= v10 )
        {
          *a3 = v5;
          v5 = 0;
          goto LABEL_20;
        }
        goto LABEL_18;
      }
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v4 )
    HeapFree(gDhcpHeap, 0, v4);
  if ( v5 )
    HeapFree(gDhcpHeap, 0, v5);
  if ( lpData )
    HeapFree(gDhcpHeap, 0, lpData);
  return Value;
}

```

## disassembly

```asm
0x18001db9c  mov     rax, rsp
0x18001db9f  mov     [rax+8], rbx
0x18001dba3  mov     [rax+18h], r8
0x18001dba7  mov     [rax+10h], edx
0x18001dbaa  push    rbp
0x18001dbab  push    rsi
0x18001dbac  push    rdi
0x18001dbad  push    r12
0x18001dbaf  push    r13
0x18001dbb1  push    r14
0x18001dbb3  push    r15
0x18001dbb5  sub     rsp, 30h
0x18001dbb9  xor     edi, edi
0x18001dbbb  lea     r9, [rax+20h]
0x18001dbbf  mov     [r8], rdi
0x18001dbc2  mov     r13, rcx
0x18001dbc5  mov     r8d, edx
0x18001dbc8  mov     [rax+20h], rdi
0x18001dbcc  mov     rdx, rcx; lpValueName
0x18001dbcf  mov     r14d, edi
0x18001dbd2  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18001dbd9  mov     esi, edi
0x18001dbdb  mov     ebp, edi
0x18001dbdd  call    DhcpRegGetValue
0x18001dbe2  mov     ebx, eax
0x18001dbe4  test    eax, eax
0x18001dbe6  jnz     loc_18001DD47
0x18001dbec  mov     rcx, [rsp+68h+lpSrc]; SourceString
0x18001dbf4  xor     edx, edx
0x18001dbf6  call    DhcpUnicodeToOem
0x18001dbfb  mov     r14, rax
0x18001dbfe  test    rax, rax
0x18001dc01  jnz     short loc_18001DC0B
0x18001dc03  lea     ebx, [rdi+8]
0x18001dc06  jmp     loc_18001DD47
0x18001dc0b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001dc0f  mov     rax, r15
0x18001dc12  inc     rax
0x18001dc15  cmp     [r14+rax], dil
0x18001dc19  jnz     short loc_18001DC12
0x18001dc1b  mov     rcx, cs:gDhcpHeap; hHeap
0x18001dc22  lea     r12d, [rax+105h]
0x18001dc29  mov     edi, 8
0x18001dc2e  mov     r8d, r12d; dwBytes
0x18001dc31  mov     edx, edi; dwFlags
0x18001dc33  call    cs:__imp_HeapAlloc
0x18001dc3a  nop     dword ptr [rax+rax+00h]
0x18001dc3f  mov     rsi, rax
0x18001dc42  test    rax, rax
0x18001dc45  jnz     short loc_18001DC4E
0x18001dc47  mov     ebx, edi
0x18001dc49  jmp     loc_18001DD47
0x18001dc4e  lea     rdx, aDatabasepath; "DatabasePath"
0x18001dc55  mov     rcx, r13; String1
0x18001dc58  call    wcscmp_0
0x18001dc5d  test    eax, eax
0x18001dc5f  jz      short loc_18001DC78
0x18001dc61  lea     rdx, aBackupdatabase; "BackupDatabasePath"
0x18001dc68  mov     rcx, r13; String1
0x18001dc6b  call    wcscmp_0
0x18001dc70  test    eax, eax
0x18001dc72  jnz     loc_18001DD02
0x18001dc78  mov     rcx, cs:gDhcpHeap; hHeap
0x18001dc7f  mov     edx, edi; dwFlags
0x18001dc81  mov     r8d, r12d
0x18001dc84  add     r8, r8; dwBytes
0x18001dc87  call    cs:__imp_HeapAlloc
0x18001dc8e  nop     dword ptr [rax+rax+00h]
0x18001dc93  mov     rbp, rax
0x18001dc96  test    rax, rax
0x18001dc99  jz      short loc_18001DC47
0x18001dc9b  mov     rcx, [rsp+68h+lpSrc]; lpSrc
0x18001dca3  mov     r8d, r12d; nSize
0x18001dca6  mov     rdx, rax; lpDst
0x18001dca9  call    cs:__imp_ExpandEnvironmentStringsW
0x18001dcb0  nop     dword ptr [rax+rax+00h]
0x18001dcb5  xor     edi, edi
0x18001dcb7  test    eax, eax
0x18001dcb9  jz      short loc_18001DD39
0x18001dcbb  cmp     eax, r12d
0x18001dcbe  ja      short loc_18001DD32
0x18001dcc0  inc     r15
0x18001dcc3  cmp     [rbp+r15*2+0], di
0x18001dcc9  jnz     short loc_18001DCC0
0x18001dccb  mov     r9d, [rsp+68h+dwType]; dwType
0x18001dcd0  lea     eax, ds:2[r15*2]
0x18001dcd8  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18001dcdf  xor     r8d, r8d; Reserved
0x18001dce2  mov     [rsp+68h+cbData], eax; cbData
0x18001dce6  mov     rdx, r13; lpValueName
0x18001dce9  mov     [rsp+68h+lpData], rbp; lpData
0x18001dcee  call    cs:__imp_RegSetValueExW
0x18001dcf5  nop     dword ptr [rax+rax+00h]
0x18001dcfa  mov     ebx, eax
0x18001dcfc  test    eax, eax
0x18001dcfe  jnz     short loc_18001DD47
0x18001dd00  jmp     short loc_18001DD04
0x18001dd02  xor     edi, edi
0x18001dd04  mov     r8d, r12d; nSize
0x18001dd07  mov     rdx, rsi; lpDst
0x18001dd0a  mov     rcx, r14; lpSrc
0x18001dd0d  call    cs:__imp_ExpandEnvironmentStringsA
0x18001dd14  nop     dword ptr [rax+rax+00h]
0x18001dd19  test    eax, eax
0x18001dd1b  jz      short loc_18001DD39
0x18001dd1d  cmp     eax, r12d
0x18001dd20  ja      short loc_18001DD32
0x18001dd22  mov     rax, [rsp+68h+arg_10]
0x18001dd2a  mov     [rax], rsi
0x18001dd2d  mov     rsi, rdi
0x18001dd30  jmp     short loc_18001DD47
0x18001dd32  mov     ebx, 0D0h
0x18001dd37  jmp     short loc_18001DD47
0x18001dd39  call    cs:__imp_GetLastError
0x18001dd40  nop     dword ptr [rax+rax+00h]
0x18001dd45  mov     ebx, eax
0x18001dd47  mov     r8, [rsp+68h+lpSrc]; lpMem
0x18001dd4f  test    r8, r8
0x18001dd52  jz      short loc_18001DD69
0x18001dd54  mov     rcx, cs:gDhcpHeap; hHeap
0x18001dd5b  xor     edx, edx; dwFlags
0x18001dd5d  call    cs:__imp_HeapFree
0x18001dd64  nop     dword ptr [rax+rax+00h]
0x18001dd69  test    r14, r14
0x18001dd6c  jz      short loc_18001DD86
0x18001dd6e  mov     rcx, cs:gDhcpHeap; hHeap
0x18001dd75  mov     r8, r14; lpMem
0x18001dd78  xor     edx, edx; dwFlags
0x18001dd7a  call    cs:__imp_HeapFree
0x18001dd81  nop     dword ptr [rax+rax+00h]
0x18001dd86  test    rsi, rsi
0x18001dd89  jz      short loc_18001DDA3
0x18001dd8b  mov     rcx, cs:gDhcpHeap; hHeap
0x18001dd92  mov     r8, rsi; lpMem
0x18001dd95  xor     edx, edx; dwFlags
0x18001dd97  call    cs:__imp_HeapFree
0x18001dd9e  nop     dword ptr [rax+rax+00h]
0x18001dda3  test    rbp, rbp
0x18001dda6  jz      short loc_18001DDC0
0x18001dda8  mov     rcx, cs:gDhcpHeap; hHeap
0x18001ddaf  mov     r8, rbp; lpMem
0x18001ddb2  xor     edx, edx; dwFlags
0x18001ddb4  call    cs:__imp_HeapFree
0x18001ddbb  nop     dword ptr [rax+rax+00h]
0x18001ddc0  mov     eax, ebx
0x18001ddc2  mov     rbx, [rsp+68h+arg_0]
0x18001ddc7  add     rsp, 30h
0x18001ddcb  pop     r15
0x18001ddcd  pop     r14
0x18001ddcf  pop     r13
0x18001ddd1  pop     r12
0x18001ddd3  pop     rdi
0x18001ddd4  pop     rsi
0x18001ddd5  pop     rbp
0x18001ddd6  retn
```
