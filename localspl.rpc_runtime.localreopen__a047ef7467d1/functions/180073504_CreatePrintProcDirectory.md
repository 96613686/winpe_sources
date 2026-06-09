# CreatePrintProcDirectory

- ea: `0x180073504`
- end: `0x18007366c`
- name: `CreatePrintProcDirectory`
- size: `360`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180090898`

## callees

- `0x180034748`
- `0x180073504`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007364c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800735f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007364c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180073587`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800735eb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180073642`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180073587`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800735eb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180073642`
- `SPOOLSS!DllFreeSplMem` at `0x180073655`
- `SPOOLSS!DllFreeSplMem` at `0x180073655`
- `SPOOLSS!DllAllocSplMem` at `0x180073554`
- `SPOOLSS!DllAllocSplMem` at `0x180073554`

## pseudocode

```c
unsigned __int16 *__fastcall CreatePrintProcDirectory(unsigned __int16 *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r8
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int16 *result; // rax
  const WCHAR *v9; // rbx
  unsigned int v10; // [rsp+28h] [rbp-8h]
  unsigned int v11; // [rsp+28h] [rbp-8h]
  unsigned int v12; // [rsp+28h] [rbp-8h]
  unsigned int v13; // [rsp+28h] [rbp-8h]
  unsigned int v14; // [rsp+28h] [rbp-8h]
  unsigned __int64 v15; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v16; // [rsp+70h] [rbp+40h] BYREF

  v3 = -1;
  v16 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  do
    ++v3;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 32) + 2 * v3) );
  v6 = v4 + v3;
  v7 = 2 * v6 + 24;
  v15 = v7;
  result = (unsigned __int16 *)DllAllocSplMem((unsigned int)(2 * v6 + 24));
  v9 = result;
  if ( result )
  {
    StringCbCopyExW(result, v7, *(const unsigned __int16 **)(a2 + 32), &v16, &v15, v10);
    if ( CreateDirectoryW(v9, 0) || GetLastError() == 183 )
    {
      StringCbCopyExW(v16, v15, L"\\", &v16, &v15, v11);
      StringCbCopyExW(v16, v15, L"PRTPROCS", &v16, &v15, v12);
      if ( CreateDirectoryW(v9, 0) || GetLastError() == 183 )
      {
        StringCbCopyExW(v16, v15, L"\\", &v16, &v15, v13);
        StringCbCopyExW(v16, v15, a1, &v16, &v15, v14);
        if ( !CreateDirectoryW(v9, 0) )
          GetLastError();
      }
    }
    return (unsigned __int16 *)DllFreeSplMem(v9);
  }
  return result;
}

```

## disassembly

```asm
0x180073504  mov     [rsp-28h+arg_0], rbx
0x180073509  push    rbp
0x18007350a  push    rsi
0x18007350b  push    rdi
0x18007350c  push    r14
0x18007350e  push    r15
0x180073510  mov     rbp, rsp
0x180073513  sub     rsp, 30h
0x180073517  xor     r15d, r15d
0x18007351a  mov     rsi, rdx
0x18007351d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180073521  mov     [rbp+arg_10], r15
0x180073525  mov     r8, rax
0x180073528  mov     r14, rcx
0x18007352b  inc     r8
0x18007352e  cmp     [rcx+r8*2], r15w
0x180073533  jnz     short loc_18007352B
0x180073535  mov     rcx, [rdx+20h]
0x180073539  inc     rax
0x18007353c  cmp     [rcx+rax*2], r15w
0x180073541  jnz     short loc_180073539
0x180073543  add     rax, r8
0x180073546  lea     rdi, ds:18h[rax*2]
0x18007354e  mov     ecx, edi
0x180073550  mov     [rbp+arg_8], rdi
0x180073554  call    cs:__imp_DllAllocSplMem
0x18007355a  mov     rbx, rax
0x18007355d  test    rax, rax
0x180073560  jz      loc_18007365B
0x180073566  mov     r8, [rsi+20h]; unsigned __int16 *
0x18007356a  lea     rax, [rbp+arg_8]
0x18007356e  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x180073572  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x180073577  mov     rdx, rdi; unsigned __int64
0x18007357a  mov     rcx, rbx; unsigned __int16 *
0x18007357d  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180073582  xor     edx, edx; lpSecurityAttributes
0x180073584  mov     rcx, rbx; lpPathName
0x180073587  call    cs:__imp_CreateDirectoryW
0x18007358d  mov     edi, 0B7h
0x180073592  test    eax, eax
0x180073594  jnz     short loc_1800735A4
0x180073596  call    cs:__imp_GetLastError
0x18007359c  cmp     eax, edi
0x18007359e  jnz     loc_180073652
0x1800735a4  mov     rdx, [rbp+arg_8]; unsigned __int64
0x1800735a8  lea     rax, [rbp+arg_8]
0x1800735ac  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x1800735b0  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x1800735b4  lea     r8, SubBlock; "\\"
0x1800735bb  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x1800735c0  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800735c5  mov     rdx, [rbp+arg_8]; unsigned __int64
0x1800735c9  lea     rax, [rbp+arg_8]
0x1800735cd  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x1800735d1  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x1800735d5  lea     r8, szPrintProcDir; "PRTPROCS"
0x1800735dc  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x1800735e1  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800735e6  xor     edx, edx; lpSecurityAttributes
0x1800735e8  mov     rcx, rbx; lpPathName
0x1800735eb  call    cs:__imp_CreateDirectoryW
0x1800735f1  test    eax, eax
0x1800735f3  jnz     short loc_1800735FF
0x1800735f5  call    cs:__imp_GetLastError
0x1800735fb  cmp     eax, edi
0x1800735fd  jnz     short loc_180073652
0x1800735ff  mov     rdx, [rbp+arg_8]; unsigned __int64
0x180073603  lea     rax, [rbp+arg_8]
0x180073607  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18007360b  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x18007360f  lea     r8, SubBlock; "\\"
0x180073616  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x18007361b  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180073620  mov     rdx, [rbp+arg_8]; unsigned __int64
0x180073624  lea     rax, [rbp+arg_8]
0x180073628  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18007362c  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x180073630  mov     r8, r14; unsigned __int16 *
0x180073633  mov     [rsp+30h+var_10], rax; unsigned __int64 *
0x180073638  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18007363d  xor     edx, edx; lpSecurityAttributes
0x18007363f  mov     rcx, rbx; lpPathName
0x180073642  call    cs:__imp_CreateDirectoryW
0x180073648  test    eax, eax
0x18007364a  jnz     short loc_180073652
0x18007364c  call    cs:__imp_GetLastError
0x180073652  mov     rcx, rbx
0x180073655  call    cs:__imp_DllFreeSplMem
0x18007365b  mov     rbx, [rsp+30h+arg_0]
0x180073660  add     rsp, 30h
0x180073664  pop     r15
0x180073666  pop     r14
0x180073668  pop     rdi
0x180073669  pop     rsi
0x18007366a  pop     rbp
0x18007366b  retn
```
