# DsRolepSetMachineAccountType

- ea: `0x180020084`
- end: `0x1800201be`
- name: `DsRolepSetMachineAccountType`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005400`

## callees

- `0x180008f24`
- `0x180016374`
- `0x18001ee88`
- `0x18001f5b0`
- `0x180020084`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200db`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800200d1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800200d1`
- `NTDSETUP!NtdsSetReplicaMachineAccount` at `0x180020173`
- `NTDSETUP!NtdsSetReplicaMachineAccount` at `0x180020173`

## pseudocode

```c
__int64 __fastcall DsRolepSetMachineAccountType(
        _WORD *a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  PVOID v9; // rsi
  WCHAR *v12; // rbp
  unsigned int LastError; // ebx
  DWORD nSize; // [rsp+30h] [rbp-88h] BYREF
  PVOID v16; // [rsp+38h] [rbp-80h] BYREF
  WCHAR Buffer[20]; // [rsp+40h] [rbp-78h] BYREF

  nSize = 16;
  v9 = 0;
  v16 = 0;
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    StringCchCatW(Buffer, 0x11u, L"$");
    v12 = Buffer;
  }
  else
  {
    v12 = 0;
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_11;
  }
  LastError = DsRolepCreateAuthIdentForCreds(a3, a4, &v16);
  if ( LastError )
  {
    v9 = v16;
  }
  else
  {
    DsRolepLogPrintRoutine(4, "Searching for the machine account for %ws on %ws...\n", v12, a1);
    DsRolepSetCurrentOperationStatus(28695, 0, 0);
    if ( a1 && *a1 == 92 )
      a1 += 2;
    v9 = v16;
    LastError = NtdsSetReplicaMachineAccount(v16, a2, a1, v12, a6, a7);
  }
LABEL_11:
  DsRolepLogPrintRoutine(4, "NtdsSetReplicaMachineAccount returned %d\n", LastError);
  DsRolepFreeAuthIdentForCreds(v9);
  return LastError;
}

```

## disassembly

```asm
0x180020084  push    rbx
0x180020086  push    rbp
0x180020087  push    rsi
0x180020088  push    rdi
0x180020089  push    r12
0x18002008b  push    r13
0x18002008d  push    r14
0x18002008f  push    r15
0x180020091  sub     rsp, 78h
0x180020095  mov     rax, cs:__security_cookie
0x18002009c  xor     rax, rsp
0x18002009f  mov     [rsp+0B8h+var_50], rax
0x1800200a4  mov     r13, [rsp+0B8h+arg_30]
0x1800200ac  mov     r12, rdx
0x1800200af  mov     rdi, rcx
0x1800200b2  mov     [rsp+0B8h+nSize], 10h
0x1800200ba  xor     esi, esi
0x1800200bc  lea     rdx, [rsp+0B8h+nSize]; nSize
0x1800200c1  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x1800200c6  mov     [rsp+0B8h+var_80], rsi
0x1800200cb  mov     r15, r9
0x1800200ce  mov     r14, r8
0x1800200d1  call    cs:__imp_GetComputerNameW
0x1800200d7  test    eax, eax
0x1800200d9  jnz     short loc_1800200EE
0x1800200db  call    cs:__imp_GetLastError
0x1800200e1  xor     ebp, ebp
0x1800200e3  mov     ebx, eax
0x1800200e5  test    eax, eax
0x1800200e7  jz      short loc_180020109
0x1800200e9  jmp     loc_180020182
0x1800200ee  lea     r8, asc_18003AFD0; "$"
0x1800200f5  mov     edx, 11h; cchDest
0x1800200fa  lea     rcx, [rsp+0B8h+Buffer]; pszDest
0x1800200ff  call    StringCchCatW
0x180020104  lea     rbp, [rsp+0B8h+Buffer]
0x180020109  lea     r8, [rsp+0B8h+var_80]
0x18002010e  mov     rdx, r15
0x180020111  mov     rcx, r14; pszSrc
0x180020114  call    DsRolepCreateAuthIdentForCreds
0x180020119  mov     ebx, eax
0x18002011b  test    eax, eax
0x18002011d  jnz     short loc_18002017D
0x18002011f  mov     r9, rdi
0x180020122  lea     rdx, aSearchingForTh; "Searching for the machine account for %"...
0x180020129  mov     r8, rbp
0x18002012c  lea     ecx, [rax+4]
0x18002012f  call    DsRolepLogPrintRoutine
0x180020134  xor     r8d, r8d
0x180020137  xor     edx, edx
0x180020139  mov     ecx, 7017h
0x18002013e  call    DsRolepSetCurrentOperationStatus
0x180020143  test    rdi, rdi
0x180020146  jz      short loc_180020152
0x180020148  cmp     word ptr [rdi], 5Ch ; '\'
0x18002014c  jnz     short loc_180020152
0x18002014e  add     rdi, 4
0x180020152  mov     eax, [rsp+0B8h+arg_28]
0x180020159  mov     r9, rbp
0x18002015c  mov     rsi, [rsp+0B8h+var_80]
0x180020161  mov     r8, rdi
0x180020164  mov     rcx, rsi
0x180020167  mov     [rsp+0B8h+var_90], r13
0x18002016c  mov     rdx, r12
0x18002016f  mov     [rsp+0B8h+var_98], eax
0x180020173  call    cs:__imp_NtdsSetReplicaMachineAccount
0x180020179  mov     ebx, eax
0x18002017b  jmp     short loc_180020182
0x18002017d  mov     rsi, [rsp+0B8h+var_80]
0x180020182  mov     r8d, ebx
0x180020185  lea     rdx, aNtdssetreplica_0; "NtdsSetReplicaMachineAccount returned %"...
0x18002018c  mov     ecx, 4
0x180020191  call    DsRolepLogPrintRoutine
0x180020196  mov     rcx, rsi; P
0x180020199  call    DsRolepFreeAuthIdentForCreds
0x18002019e  mov     eax, ebx
0x1800201a0  mov     rcx, [rsp+0B8h+var_50]
0x1800201a5  xor     rcx, rsp; StackCookie
0x1800201a8  call    __security_check_cookie
0x1800201ad  add     rsp, 78h
0x1800201b1  pop     r15
0x1800201b3  pop     r14
0x1800201b5  pop     r13
0x1800201b7  pop     r12
0x1800201b9  pop     rdi
0x1800201ba  pop     rsi
0x1800201bb  pop     rbp
0x1800201bc  pop     rbx
0x1800201bd  retn
```
