# CreateBackupKeyW2K(_GUID *,uchar * *,ulong *)

- ea: `0x180031674`
- end: `0x180031766`
- name: `?CreateBackupKeyW2K@@YAHPEAU_GUID@@PEAPEAEPEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180030f00`
- `0x1800354c8`

## callees

- `0x180007f10`
- `0x180031674`
- `0x180034ff8`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800316a8`
- `RPCRT4!UuidCreate` at `0x1800316a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003174e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003174e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031734`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800316e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800316e9`
- `bcrypt!BCryptGenRandom` at `0x18003170b`
- `bcrypt!BCryptGenRandom` at `0x18003170b`

## string_xrefs

- `0x1800316c7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CreateBackupKeyW2K(struct _GUID *a1, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned int v6; // eax
  DWORD v7; // edi
  DWORD v8; // ecx
  unsigned __int8 *v9; // rax
  NTSTATUS v10; // eax
  unsigned __int8 *v11; // rcx

  if ( !a1 || !a2 || !a3 )
    goto LABEL_11;
  *a2 = 0;
  v6 = UuidCreate(a1);
  v7 = v6;
  if ( v6 && v6 != 1824 )
  {
    DebugTraceError(v6, "RpcStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", 2332);
    v8 = v7;
LABEL_12:
    SetLastError(v8);
    return 0;
  }
  *a3 = 260;
  v9 = (unsigned __int8 *)LocalAlloc(0, 0x104u);
  *a2 = v9;
  if ( !v9 )
  {
LABEL_11:
    v8 = 87;
    goto LABEL_12;
  }
  v10 = BCryptGenRandom(0, v9, *a3, 2u);
  v11 = *a2;
  if ( v10 >= 0 )
  {
    *(_DWORD *)v11 = 1;
    return SaveBackupKey(a1, *a2, *a3);
  }
  LocalFree(v11);
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180031674  push    rbx
0x180031676  push    rbp
0x180031677  push    rsi
0x180031678  push    rdi
0x180031679  sub     rsp, 28h
0x18003167d  mov     rsi, r8
0x180031680  mov     rbx, rdx
0x180031683  mov     rbp, rcx
0x180031686  test    rcx, rcx
0x180031689  jz      loc_180031749
0x18003168f  test    rdx, rdx
0x180031692  jz      loc_180031749
0x180031698  test    r8, r8
0x18003169b  jz      loc_180031749
0x1800316a1  mov     qword ptr [rdx], 0
0x1800316a8  call    cs:__imp_UuidCreate
0x1800316af  nop     dword ptr [rax+rax+00h]
0x1800316b4  mov     edi, eax
0x1800316b6  test    eax, eax
0x1800316b8  jz      short loc_1800316E0
0x1800316ba  cmp     eax, 720h
0x1800316bf  jz      short loc_1800316E0
0x1800316c1  mov     r9d, 91Ch
0x1800316c7  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800316ce  lea     rdx, aRpcstatus; "RpcStatus"
0x1800316d5  mov     ecx, eax
0x1800316d7  call    DebugTraceError
0x1800316dc  mov     ecx, edi
0x1800316de  jmp     short loc_18003174E
0x1800316e0  mov     edx, 104h; uBytes
0x1800316e5  xor     ecx, ecx; uFlags
0x1800316e7  mov     [rsi], edx
0x1800316e9  call    cs:__imp_LocalAlloc
0x1800316f0  nop     dword ptr [rax+rax+00h]
0x1800316f5  mov     [rbx], rax
0x1800316f8  test    rax, rax
0x1800316fb  jz      short loc_180031749
0x1800316fd  mov     r8d, [rsi]; cbBuffer
0x180031700  mov     r9d, 2; dwFlags
0x180031706  mov     rdx, rax; pbBuffer
0x180031709  xor     ecx, ecx; hAlgorithm
0x18003170b  call    cs:__imp_BCryptGenRandom
0x180031712  nop     dword ptr [rax+rax+00h]
0x180031717  mov     rcx, [rbx]; hMem
0x18003171a  test    eax, eax
0x18003171c  js      short loc_180031734
0x18003171e  mov     dword ptr [rcx], 1
0x180031724  mov     rcx, rbp; struct _GUID *
0x180031727  mov     r8d, [rsi]; unsigned int
0x18003172a  mov     rdx, [rbx]; unsigned __int8 *
0x18003172d  call    ?SaveBackupKey@@YAHPEAU_GUID@@PEAEK@Z; SaveBackupKey(_GUID *,uchar *,ulong)
0x180031732  jmp     short loc_18003175C
0x180031734  call    cs:__imp_LocalFree
0x18003173b  nop     dword ptr [rax+rax+00h]
0x180031740  mov     qword ptr [rbx], 0
0x180031747  jmp     short loc_18003175A
0x180031749  mov     ecx, 57h ; 'W'; dwErrCode
0x18003174e  call    cs:__imp_SetLastError
0x180031755  nop     dword ptr [rax+rax+00h]
0x18003175a  xor     eax, eax
0x18003175c  add     rsp, 28h
0x180031760  pop     rdi
0x180031761  pop     rsi
0x180031762  pop     rbp
0x180031763  pop     rbx
0x180031764  retn
```
