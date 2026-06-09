# GetAccountKey

- ea: `0x18000c814`
- end: `0x18000c917`
- name: `GetAccountKey`
- size: `259`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c920`
- `0x18000e5d4`
- `0x18001268c`
- `0x180012e04`
- `0x180016a80`
- `0x180017660`
- `0x1800189b0`

## callees

- `0x18000bf94`
- `0x18000c814`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c8f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c89d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c89d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c837`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c837`
- `DMCmnUtils!BigStrcat` at `0x18000c864`
- `DMCmnUtils!BigStrcat` at `0x18000c864`

## pseudocode

```c
__int64 __fastcall GetAccountKey(const unsigned __int16 *a1, int a2, REGSAM a3, HKEY *a4, _QWORD *a5)
{
  unsigned int AccountbyServerID; // ebx
  char IsStateSeparationEnabled; // al
  const wchar_t *v10; // rdx
  WCHAR *v11; // rsi
  int v12; // edi
  LSTATUS v13; // eax
  DWORD phkResult; // [rsp+20h] [rbp-48h]

  AccountbyServerID = 0;
  if ( a2 == 1 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
    v10 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
    if ( !IsStateSeparationEnabled )
      v10 = L"Software\\Microsoft\\Provisioning\\OMADM\\Accounts";
    v11 = BigStrcat(3u, v10, L"\\", a1);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        v13 = RegOpenKeyExW((HKEY)qword_18002A528[v12], v11, 0, a3, a4);
        if ( !v13 )
          break;
        if ( (v13 == 2 || v13 == 5) && (unsigned int)++v12 < 2 )
          continue;
        AccountbyServerID = -2147024894;
        goto LABEL_16;
      }
      if ( a5 )
        *a5 = qword_18002A528[v12];
    }
    else
    {
      AccountbyServerID = -2147024882;
    }
  }
  else
  {
    v11 = 0;
    if ( !a2 )
      AccountbyServerID = FindAccountbyServerID(a1, a3, a4, a5, phkResult);
  }
LABEL_16:
  LocalFree(v11);
  return AccountbyServerID;
}

```

## disassembly

```asm
0x18000c814  push    rbx
0x18000c816  push    rbp
0x18000c817  push    rsi
0x18000c818  push    rdi
0x18000c819  push    r12
0x18000c81b  push    r14
0x18000c81d  push    r15
0x18000c81f  sub     rsp, 30h
0x18000c823  xor     ebx, ebx
0x18000c825  mov     r14, r9
0x18000c828  mov     r15d, r8d
0x18000c82b  mov     rdi, rcx
0x18000c82e  cmp     edx, 1
0x18000c831  jnz     loc_18000C8DB
0x18000c837  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000c83e  nop     dword ptr [rax+rax+00h]
0x18000c843  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18000c84a  mov     r9, rdi
0x18000c84d  test    al, al
0x18000c84f  lea     rdx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x18000c856  lea     r8, asc_1800273F4; "\\"
0x18000c85d  cmovz   rdx, rcx
0x18000c861  lea     ecx, [rbx+3]
0x18000c864  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18000c86b  nop     dword ptr [rax+rax+00h]
0x18000c870  mov     rsi, rax
0x18000c873  test    rax, rax
0x18000c876  jnz     short loc_18000C87F
0x18000c878  mov     ebx, 8007000Eh
0x18000c87d  jmp     short loc_18000C8F6
0x18000c87f  xor     edi, edi
0x18000c881  movsxd  rbp, edi
0x18000c884  lea     r12, qword_18002A528
0x18000c88b  mov     r9d, r15d; samDesired
0x18000c88e  mov     qword ptr [rsp+68h+phkResult], r14; phkResult
0x18000c893  xor     r8d, r8d; ulOptions
0x18000c896  mov     rdx, rsi; lpSubKey
0x18000c899  mov     rcx, [r12+rbp*8]; hKey
0x18000c89d  call    cs:__imp_RegOpenKeyExW
0x18000c8a4  nop     dword ptr [rax+rax+00h]
0x18000c8a9  test    eax, eax
0x18000c8ab  jz      short loc_18000C8C5
0x18000c8ad  cmp     eax, 2
0x18000c8b0  jz      short loc_18000C8B7
0x18000c8b2  cmp     eax, 5
0x18000c8b5  jnz     short loc_18000C8BE
0x18000c8b7  inc     edi
0x18000c8b9  cmp     edi, 2
0x18000c8bc  jb      short loc_18000C881
0x18000c8be  mov     ebx, 80070002h
0x18000c8c3  jmp     short loc_18000C8F6
0x18000c8c5  mov     rcx, qword ptr [rsp+68h+arg_20]; int
0x18000c8cd  test    rcx, rcx
0x18000c8d0  jz      short loc_18000C8F6
0x18000c8d2  mov     rax, [r12+rbp*8]
0x18000c8d6  mov     [rcx], rax
0x18000c8d9  jmp     short loc_18000C8F6
0x18000c8db  xor     esi, esi
0x18000c8dd  test    edx, edx
0x18000c8df  jnz     short loc_18000C8F6
0x18000c8e1  mov     r9, qword ptr [rsp+68h+arg_20]; int
0x18000c8e9  mov     r8, r14; int
0x18000c8ec  mov     edx, r15d; int
0x18000c8ef  call    FindAccountbyServerID
0x18000c8f4  mov     ebx, eax
0x18000c8f6  mov     rcx, rsi; hMem
0x18000c8f9  call    cs:__imp_LocalFree
0x18000c900  nop     dword ptr [rax+rax+00h]
0x18000c905  mov     eax, ebx
0x18000c907  add     rsp, 30h
0x18000c90b  pop     r15
0x18000c90d  pop     r14
0x18000c90f  pop     r12
0x18000c911  pop     rdi
0x18000c912  pop     rsi
0x18000c913  pop     rbp
0x18000c914  pop     rbx
0x18000c915  retn
```
