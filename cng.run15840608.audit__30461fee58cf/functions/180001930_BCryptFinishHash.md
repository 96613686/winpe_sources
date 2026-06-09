# BCryptFinishHash

- ea: `0x180001930`
- end: `0x180001aa9`
- name: `BCryptFinishHash`
- size: `377`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, PUCHAR pbOutput, ULONG cbOutput, ULONG dwFlags)`
- caller_count: `11`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001ab0`
- `0x180049084`
- `0x180058070`
- `0x180067ec4`
- `0x180068500`
- `0x1800687b8`
- `0x180068d98`
- `0x180082888`
- `0x180083724`
- `0x180083a3c`

## callees

- `0x180001930`
- `0x18000743c`
- `0x1800082b0`
- `0x180047f1c`
- `0x18009d860`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000198d`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000198d`

## string_xrefs

- `0x180001a03`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180001a35`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18009e318`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptFinishHash(BCRYPT_HASH_HANDLE hHash, PUCHAR pbOutput, ULONG cbOutput, ULONG dwFlags)
{
  __int64 v8; // rsi
  int v9; // edi
  int v10; // r8d
  int v12; // edx
  int v13; // eax
  __int64 v14; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 3), 35, cbOutput, hHash, pbOutput, cbOutput, dwFlags);
  if ( hHash
    && *(_DWORD *)hHash >= 0x28u
    && *((_DWORD *)hHash + 1) == 1431655763
    && (*(_DWORD *)(*((_QWORD *)hHash + 1) + 32LL) || KeGetCurrentIrql() < 2u) )
  {
    v8 = *((_QWORD *)hHash + 1);
    v9 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v8 + 104))(
           *((_QWORD *)hHash + 2),
           pbOutput,
           cbOutput,
           dwFlags);
    if ( v9 >= 0 )
    {
      if ( (*(_DWORD *)(v8 + 8) & 8) == 0 )
        return 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v8 + 96))(
              *((_QWORD *)hHash + 3),
              pbOutput,
              cbOutput,
              dwFlags);
      v9 = v13;
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v8 + 104))(
                *((_QWORD *)hHash + 3),
                pbOutput,
                cbOutput,
                dwFlags);
        v9 = v13;
        if ( v13 >= 0 )
          return 0;
        v14 = 6164;
      }
      else
      {
        v14 = 6155;
      }
      DebugTraceError((unsigned int)v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v14);
      return v9;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v12 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v12 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v12,
          v10,
          (unsigned int)"Status",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
          255);
    }
  }
  else
  {
    v9 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)pbOutput,
        cbOutput,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        245);
  }
  return v9;
}

```

## disassembly

```asm
0x180001930  push    rbx
0x180001932  push    rbp
0x180001933  push    rdi
0x180001934  push    r12
0x180001936  push    r14
0x180001938  push    r15
0x18000193a  sub     rsp, 48h
0x18000193e  mov     ebp, r9d
0x180001941  mov     r14d, r8d
0x180001944  mov     r15, rdx
0x180001947  mov     rbx, rcx
0x18000194a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001951  lea     r12, WPP_GLOBAL_Control
0x180001958  cmp     rcx, r12
0x18000195b  jz      short loc_180001968
0x18000195d  mov     eax, [rcx+2Ch]
0x180001960  test    al, 4
0x180001962  jnz     loc_180001A5A
0x180001968  mov     [rsp+78h+arg_0], rsi
0x180001970  test    rbx, rbx
0x180001973  jz      short loc_1800019E3
0x180001975  cmp     dword ptr [rbx], 28h ; '('
0x180001978  jb      short loc_1800019E3
0x18000197a  cmp     dword ptr [rbx+4], 55555553h
0x180001981  jnz     short loc_1800019E3
0x180001983  mov     rax, [rbx+8]
0x180001987  cmp     dword ptr [rax+20h], 0
0x18000198b  jnz     short loc_18000199D
0x18000198d  call    cs:__imp_KeGetCurrentIrql
0x180001994  nop     dword ptr [rax+rax+00h]
0x180001999  cmp     al, 2
0x18000199b  jnb     short loc_1800019E3
0x18000199d  mov     rsi, [rbx+8]
0x1800019a1  mov     r9d, ebp
0x1800019a4  mov     rcx, [rbx+10h]
0x1800019a8  mov     r8d, r14d
0x1800019ab  mov     rdx, r15
0x1800019ae  mov     rax, [rsi+68h]
0x1800019b2  call    _guard_dispatch_icall
0x1800019b7  mov     edi, eax
0x1800019b9  test    eax, eax
0x1800019bb  js      short loc_180001A19
0x1800019bd  mov     eax, [rsi+8]
0x1800019c0  test    al, 8
0x1800019c2  jnz     loc_180001A7E
0x1800019c8  xor     edi, edi
0x1800019ca  mov     rsi, [rsp+78h+arg_0]
0x1800019d2  mov     eax, edi
0x1800019d4  add     rsp, 48h
0x1800019d8  pop     r15
0x1800019da  pop     r14
0x1800019dc  pop     r12
0x1800019de  pop     rdi
0x1800019df  pop     rbp
0x1800019e0  pop     rbx
0x1800019e1  retn
0x1800019e3  mov     edi, 0C0000008h
0x1800019e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019ef  cmp     rcx, r12
0x1800019f2  jz      short loc_1800019CA
0x1800019f4  mov     eax, [rcx+2Ch]
0x1800019f7  test    al, 1
0x1800019f9  jz      short loc_1800019CA
0x1800019fb  mov     [rsp+78h+var_48], 17F5h
0x180001a03  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001a0a  mov     [rsp+78h+var_50], rax
0x180001a0f  mov     dword ptr [rsp+78h+var_58], 0C0000008h
0x180001a17  jmp     short loc_180001A45
0x180001a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a20  cmp     rcx, r12
0x180001a23  jz      short loc_1800019CA
0x180001a25  mov     edx, [rcx+2Ch]
0x180001a28  test    dl, 1
0x180001a2b  jz      short loc_1800019CA
0x180001a2d  mov     [rsp+78h+var_48], 17FFh
0x180001a35  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001a3c  mov     [rsp+78h+var_50], rax
0x180001a41  mov     dword ptr [rsp+78h+var_58], edi
0x180001a45  mov     rcx, [rcx+18h]
0x180001a49  lea     r9, aStatus; "Status"
0x180001a50  call    WPP_SF_sDsd
0x180001a55  jmp     loc_1800019CA
0x180001a5a  mov     rcx, [rcx+18h]
0x180001a5e  mov     edx, 23h ; '#'
0x180001a63  mov     [rsp+78h+var_48], ebp
0x180001a67  mov     r9, rbx
0x180001a6a  mov     dword ptr [rsp+78h+var_50], r14d
0x180001a6f  mov     [rsp+78h+var_58], r15
0x180001a74  call    WPP_SF_qqdD
0x180001a79  jmp     loc_180001968
0x180001a7e  mov     rax, [rsi+60h]
0x180001a82  mov     r9d, ebp
0x180001a85  mov     rcx, [rbx+18h]
0x180001a89  mov     r8d, r14d
0x180001a8c  mov     rdx, r15
0x180001a8f  call    _guard_dispatch_icall
0x180001a94  mov     edi, eax
0x180001a96  test    eax, eax
0x180001a98  jns     loc_18009E333
0x180001a9e  mov     r9d, 180Bh
0x180001aa4  jmp     loc_18009E318
0x18009e312  mov     r9d, 1814h
0x18009e318  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009e31f  mov     ecx, eax
0x18009e321  lea     rdx, aStatus; "Status"
0x18009e328  call    DebugTraceError
0x18009e32d  nop
0x18009e32e  jmp     loc_1800019CA
0x18009e333  mov     rax, [rsi+68h]
0x18009e337  mov     r9d, ebp
0x18009e33a  mov     rcx, [rbx+18h]
0x18009e33e  mov     r8d, r14d
0x18009e341  mov     rdx, r15
0x18009e344  call    _guard_dispatch_icall
0x18009e349  mov     edi, eax
0x18009e34b  test    eax, eax
0x18009e34d  jns     loc_1800019C8
0x18009e353  jmp     short loc_18009E312
```
