# BasepIsProcessAllowed

- ea: `0x180037460`
- end: `0x1800375b5`
- name: `BasepIsProcessAllowed`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180037460`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003749a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003749a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800374b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800374b0`
- `ntdll!NtOpenKey` at `0x1800374ef`
- `ntdll!NtOpenKey` at `0x1800374ef`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180037546`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180037546`
- `ntdll!NtClose` at `0x180037528`
- `ntdll!NtClose` at `0x180037528`

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
  while ( !dword_1800B5AFC )
  {
    RtlAcquireSRWLockExclusive(&gsrwlAppCert);
    if ( dword_1800B5AFC )
      goto LABEL_4;
    v4 = 0;
    if ( NtOpenKey(&KeyHandle, 1u, (POBJECT_ATTRIBUTES)&stru_18007DCF0) >= 0 )
    {
      NtClose(KeyHandle);
      RegistryValues = RtlQueryRegistryValuesEx(2, L"Session Manager", &BasepAppCertTable, 0, 0);
      v4 = RegistryValues;
      if ( RegistryValues < 0 )
      {
        if ( RegistryValues != -1073741772 )
        {
LABEL_11:
          dword_1800B5300 = v4;
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
    dword_1800B52FC = v5;
    dword_1800B5AFC = 1;
LABEL_4:
    RtlReleaseSRWLockExclusive(&gsrwlAppCert);
  }
  if ( !dword_1800B52FC )
    return (unsigned int)dword_1800B5300;
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
0x180037460  mov     [rsp+arg_0], rbx
0x180037465  mov     [rsp+arg_10], rbp
0x18003746a  push    rsi
0x18003746b  push    rdi
0x18003746c  push    r15
0x18003746e  sub     rsp, 30h
0x180037472  mov     rbp, rcx
0x180037475  mov     [rsp+48h+KeyHandle], 0
0x18003747e  mov     esi, 2
0x180037483  lea     r15, BasepAppCertDllsList
0x18003748a  cmp     cs:dword_1800B5AFC, 0
0x180037491  jnz     short loc_1800374B8
0x180037493  lea     rcx, gsrwlAppCert
0x18003749a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800374a0  cmp     cs:dword_1800B5AFC, 0
0x1800374a7  jz      short loc_1800374DE
0x1800374a9  lea     rcx, gsrwlAppCert
0x1800374b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800374b6  jmp     short loc_18003748A
0x1800374b8  cmp     cs:dword_1800B52FC, 0
0x1800374bf  jnz     loc_18003755D
0x1800374c5  mov     eax, cs:dword_1800B5300
0x1800374cb  mov     rbx, [rsp+48h+arg_0]
0x1800374d0  mov     rbp, [rsp+48h+arg_10]
0x1800374d5  add     rsp, 30h
0x1800374d9  pop     r15
0x1800374db  pop     rdi
0x1800374dc  pop     rsi
0x1800374dd  retn
0x1800374de  xor     ebx, ebx
0x1800374e0  lea     r8, stru_18007DCF0; ObjectAttributes
0x1800374e7  lea     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x1800374ec  lea     edx, [rbx+1]; DesiredAccess
0x1800374ef  call    cs:__imp_NtOpenKey
0x1800374f5  test    eax, eax
0x1800374f7  jns     short loc_180037523
0x1800374f9  cmp     cs:BasepAppCertDllsList, r15
0x180037500  jz      short loc_180037519
0x180037502  mov     eax, 1
0x180037507  mov     cs:dword_1800B52FC, eax
0x18003750d  mov     cs:dword_1800B5AFC, 1
0x180037517  jmp     short loc_1800374A9
0x180037519  mov     cs:dword_1800B5300, ebx
0x18003751f  xor     eax, eax
0x180037521  jmp     short loc_180037507
0x180037523  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x180037528  call    cs:__imp_NtClose
0x18003752e  xor     r9d, r9d
0x180037531  mov     [rsp+48h+var_28], rbx
0x180037536  lea     r8, BasepAppCertTable
0x18003753d  mov     ecx, esi
0x18003753f  lea     rdx, aSessionManager; "Session Manager"
0x180037546  call    cs:__imp_RtlQueryRegistryValuesEx
0x18003754c  mov     ebx, eax
0x18003754e  test    eax, eax
0x180037550  jns     short loc_1800374F9
0x180037552  cmp     eax, 0C0000034h
0x180037557  jnz     short loc_180037519
0x180037559  xor     ebx, ebx
0x18003755b  jmp     short loc_1800374F9
0x18003755d  mov     rbx, cs:BasepAppCertDllsList
0x180037564  xor     edi, edi
0x180037566  cmp     rbx, r15
0x180037569  jz      short loc_1800375AE
0x18003756b  mov     rax, [rbx+20h]
0x18003756f  mov     edx, 1
0x180037574  mov     rcx, rbp
0x180037577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003757c  test    eax, eax
0x18003757e  jns     short loc_180037587
0x180037580  mov     edi, eax
0x180037582  mov     esi, 3
0x180037587  mov     rbx, [rbx]
0x18003758a  cmp     rbx, r15
0x18003758d  jnz     short loc_18003756B
0x18003758f  mov     rbx, cs:BasepAppCertDllsList
0x180037596  jmp     short loc_1800375A9
0x180037598  mov     rax, [rbx+20h]
0x18003759c  mov     edx, esi
0x18003759e  mov     rcx, rbp
0x1800375a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375a6  mov     rbx, [rbx]
0x1800375a9  cmp     rbx, r15
0x1800375ac  jnz     short loc_180037598
0x1800375ae  mov     eax, edi
0x1800375b0  jmp     loc_1800374CB
```
