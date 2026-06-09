# BasepIsProcessAllowed

- ea: `0x18003a020`
- end: `0x18003a194`
- name: `BasepIsProcessAllowed`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18003a020`
- `0x180084010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a05a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003a05a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a076`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003a076`
- `ntdll!NtOpenKey` at `0x18003a0bc`
- `ntdll!NtOpenKey` at `0x18003a0bc`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18003a11f`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18003a11f`
- `ntdll!NtClose` at `0x18003a0fb`
- `ntdll!NtClose` at `0x18003a0fb`

## pseudocode

```c
__int64 __fastcall BasepIsProcessAllowed(__int64 a1)
{
  unsigned int v2; // esi
  int v4; // ebx
  int v5; // eax
  int RegistryValues; // eax
  __int64 v7; // rbx
  unsigned int v8; // edi
  int v9; // eax
  __int64 i; // rbx
  void *KeyHandle; // [rsp+58h] [rbp+10h] BYREF

  KeyHandle = 0;
  v2 = 2;
  while ( !dword_1800BDAFC )
  {
    RtlAcquireSRWLockExclusive(&gsrwlAppCert);
    if ( dword_1800BDAFC )
      goto LABEL_4;
    v4 = 0;
    if ( NtOpenKey(&KeyHandle, 1u, (POBJECT_ATTRIBUTES)&stru_180085A90) >= 0 )
    {
      NtClose(KeyHandle);
      RegistryValues = RtlQueryRegistryValuesEx(2, L"Session Manager", &BasepAppCertTable, 0, 0);
      v4 = RegistryValues;
      if ( RegistryValues < 0 )
      {
        if ( RegistryValues != -1073741772 )
        {
LABEL_11:
          dword_1800BD300 = v4;
          v5 = 0;
          goto LABEL_10;
        }
        v4 = 0;
      }
    }
    if ( (__int64 *)BasepAppCertDllsList == &BasepAppCertDllsList )
      goto LABEL_11;
    v5 = 1;
LABEL_10:
    dword_1800BD2FC = v5;
    dword_1800BDAFC = 1;
LABEL_4:
    RtlReleaseSRWLockExclusive(&gsrwlAppCert);
  }
  if ( !dword_1800BD2FC )
    return (unsigned int)dword_1800BD300;
  v7 = BasepAppCertDllsList;
  v8 = 0;
  if ( (__int64 *)BasepAppCertDllsList != &BasepAppCertDllsList )
  {
    do
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(v7 + 32))(a1, 1);
      if ( v9 < 0 )
      {
        v8 = v9;
        v2 = 3;
      }
      v7 = *(_QWORD *)v7;
    }
    while ( (__int64 *)v7 != &BasepAppCertDllsList );
    for ( i = BasepAppCertDllsList; (__int64 *)i != &BasepAppCertDllsList; i = *(_QWORD *)i )
      (*(void (__fastcall **)(__int64, _QWORD))(i + 32))(a1, v2);
  }
  return v8;
}

```

## disassembly

```asm
0x18003a020  mov     [rsp+arg_0], rbx
0x18003a025  mov     [rsp+arg_10], rbp
0x18003a02a  push    rsi
0x18003a02b  push    rdi
0x18003a02c  push    r15
0x18003a02e  sub     rsp, 30h
0x18003a032  mov     rbp, rcx
0x18003a035  mov     [rsp+48h+KeyHandle], 0
0x18003a03e  mov     esi, 2
0x18003a043  lea     r15, BasepAppCertDllsList
0x18003a04a  cmp     cs:dword_1800BDAFC, 0
0x18003a051  jnz     short loc_18003A084
0x18003a053  lea     rcx, gsrwlAppCert
0x18003a05a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003a061  nop     dword ptr [rax+rax+00h]
0x18003a066  cmp     cs:dword_1800BDAFC, 0
0x18003a06d  jz      short loc_18003A0AB
0x18003a06f  lea     rcx, gsrwlAppCert
0x18003a076  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003a07d  nop     dword ptr [rax+rax+00h]
0x18003a082  jmp     short loc_18003A04A
0x18003a084  cmp     cs:dword_1800BD2FC, 0
0x18003a08b  jnz     loc_18003A13C
0x18003a091  mov     eax, cs:dword_1800BD300
0x18003a097  mov     rbx, [rsp+48h+arg_0]
0x18003a09c  mov     rbp, [rsp+48h+arg_10]
0x18003a0a1  add     rsp, 30h
0x18003a0a5  pop     r15
0x18003a0a7  pop     rdi
0x18003a0a8  pop     rsi
0x18003a0a9  retn
0x18003a0ab  xor     ebx, ebx
0x18003a0ad  lea     r8, stru_180085A90; ObjectAttributes
0x18003a0b4  lea     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x18003a0b9  lea     edx, [rbx+1]; DesiredAccess
0x18003a0bc  call    cs:__imp_NtOpenKey
0x18003a0c3  nop     dword ptr [rax+rax+00h]
0x18003a0c8  test    eax, eax
0x18003a0ca  jns     short loc_18003A0F6
0x18003a0cc  cmp     cs:BasepAppCertDllsList, r15
0x18003a0d3  jz      short loc_18003A0EC
0x18003a0d5  mov     eax, 1
0x18003a0da  mov     cs:dword_1800BD2FC, eax
0x18003a0e0  mov     cs:dword_1800BDAFC, 1
0x18003a0ea  jmp     short loc_18003A06F
0x18003a0ec  mov     cs:dword_1800BD300, ebx
0x18003a0f2  xor     eax, eax
0x18003a0f4  jmp     short loc_18003A0DA
0x18003a0f6  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x18003a0fb  call    cs:__imp_NtClose
0x18003a102  nop     dword ptr [rax+rax+00h]
0x18003a107  xor     r9d, r9d
0x18003a10a  mov     [rsp+48h+var_28], rbx
0x18003a10f  lea     r8, BasepAppCertTable
0x18003a116  mov     ecx, esi
0x18003a118  lea     rdx, aSessionManager; "Session Manager"
0x18003a11f  call    cs:__imp_RtlQueryRegistryValuesEx
0x18003a126  nop     dword ptr [rax+rax+00h]
0x18003a12b  mov     ebx, eax
0x18003a12d  test    eax, eax
0x18003a12f  jns     short loc_18003A0CC
0x18003a131  cmp     eax, 0C0000034h
0x18003a136  jnz     short loc_18003A0EC
0x18003a138  xor     ebx, ebx
0x18003a13a  jmp     short loc_18003A0CC
0x18003a13c  mov     rbx, cs:BasepAppCertDllsList
0x18003a143  xor     edi, edi
0x18003a145  cmp     rbx, r15
0x18003a148  jz      short loc_18003A18D
0x18003a14a  mov     rax, [rbx+20h]
0x18003a14e  mov     edx, 1
0x18003a153  mov     rcx, rbp
0x18003a156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a15b  test    eax, eax
0x18003a15d  jns     short loc_18003A166
0x18003a15f  mov     edi, eax
0x18003a161  mov     esi, 3
0x18003a166  mov     rbx, [rbx]
0x18003a169  cmp     rbx, r15
0x18003a16c  jnz     short loc_18003A14A
0x18003a16e  mov     rbx, cs:BasepAppCertDllsList
0x18003a175  jmp     short loc_18003A188
0x18003a177  mov     rax, [rbx+20h]
0x18003a17b  mov     edx, esi
0x18003a17d  mov     rcx, rbp
0x18003a180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a185  mov     rbx, [rbx]
0x18003a188  cmp     rbx, r15
0x18003a18b  jnz     short loc_18003A177
0x18003a18d  mov     eax, edi
0x18003a18f  jmp     loc_18003A097
```
