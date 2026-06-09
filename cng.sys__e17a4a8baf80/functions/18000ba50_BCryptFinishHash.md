# BCryptFinishHash

- ea: `0x18000ba50`
- end: `0x18000bbc9`
- name: `BCryptFinishHash`
- size: `377`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, PUCHAR pbOutput, ULONG cbOutput, ULONG dwFlags)`
- caller_count: `11`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b9b0`
- `0x18000bbd0`
- `0x180053184`
- `0x180062240`
- `0x180072064`
- `0x1800726a0`
- `0x180072958`
- `0x180072f38`
- `0x18008ca78`
- `0x18008d914`
- `0x18008dc2c`

## callees

- `0x18000ba50`
- `0x18001155c`
- `0x1800123d0`
- `0x18005200c`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000baad`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000baad`

## string_xrefs

- `0x18000bb23`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000bb55`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a50b6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18000ba50  push    rbx
0x18000ba52  push    rbp
0x18000ba53  push    rdi
0x18000ba54  push    r12
0x18000ba56  push    r14
0x18000ba58  push    r15
0x18000ba5a  sub     rsp, 48h
0x18000ba5e  mov     ebp, r9d
0x18000ba61  mov     r14d, r8d
0x18000ba64  mov     r15, rdx
0x18000ba67  mov     rbx, rcx
0x18000ba6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba71  lea     r12, WPP_GLOBAL_Control
0x18000ba78  cmp     rcx, r12
0x18000ba7b  jz      short loc_18000BA88
0x18000ba7d  mov     eax, [rcx+2Ch]
0x18000ba80  test    al, 4
0x18000ba82  jnz     loc_18000BB7A
0x18000ba88  mov     [rsp+78h+arg_0], rsi
0x18000ba90  test    rbx, rbx
0x18000ba93  jz      short loc_18000BB03
0x18000ba95  cmp     dword ptr [rbx], 28h ; '('
0x18000ba98  jb      short loc_18000BB03
0x18000ba9a  cmp     dword ptr [rbx+4], 55555553h
0x18000baa1  jnz     short loc_18000BB03
0x18000baa3  mov     rax, [rbx+8]
0x18000baa7  cmp     dword ptr [rax+20h], 0
0x18000baab  jnz     short loc_18000BABD
0x18000baad  call    cs:__imp_KeGetCurrentIrql
0x18000bab4  nop     dword ptr [rax+rax+00h]
0x18000bab9  cmp     al, 2
0x18000babb  jnb     short loc_18000BB03
0x18000babd  mov     rsi, [rbx+8]
0x18000bac1  mov     r9d, ebp
0x18000bac4  mov     rcx, [rbx+10h]
0x18000bac8  mov     r8d, r14d
0x18000bacb  mov     rdx, r15
0x18000bace  mov     rax, [rsi+68h]
0x18000bad2  call    _guard_dispatch_icall
0x18000bad7  mov     edi, eax
0x18000bad9  test    eax, eax
0x18000badb  js      short loc_18000BB39
0x18000badd  mov     eax, [rsi+8]
0x18000bae0  test    al, 8
0x18000bae2  jnz     loc_18000BB9E
0x18000bae8  xor     edi, edi
0x18000baea  mov     rsi, [rsp+78h+arg_0]
0x18000baf2  mov     eax, edi
0x18000baf4  add     rsp, 48h
0x18000baf8  pop     r15
0x18000bafa  pop     r14
0x18000bafc  pop     r12
0x18000bafe  pop     rdi
0x18000baff  pop     rbp
0x18000bb00  pop     rbx
0x18000bb01  retn
0x18000bb03  mov     edi, 0C0000008h
0x18000bb08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb0f  cmp     rcx, r12
0x18000bb12  jz      short loc_18000BAEA
0x18000bb14  mov     eax, [rcx+2Ch]
0x18000bb17  test    al, 1
0x18000bb19  jz      short loc_18000BAEA
0x18000bb1b  mov     [rsp+78h+var_48], 17F5h
0x18000bb23  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb2a  mov     [rsp+78h+var_50], rax
0x18000bb2f  mov     dword ptr [rsp+78h+var_58], 0C0000008h
0x18000bb37  jmp     short loc_18000BB65
0x18000bb39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb40  cmp     rcx, r12
0x18000bb43  jz      short loc_18000BAEA
0x18000bb45  mov     edx, [rcx+2Ch]
0x18000bb48  test    dl, 1
0x18000bb4b  jz      short loc_18000BAEA
0x18000bb4d  mov     [rsp+78h+var_48], 17FFh
0x18000bb55  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bb5c  mov     [rsp+78h+var_50], rax
0x18000bb61  mov     dword ptr [rsp+78h+var_58], edi
0x18000bb65  mov     rcx, [rcx+18h]
0x18000bb69  lea     r9, aStatus; "Status"
0x18000bb70  call    WPP_SF_sDsd
0x18000bb75  jmp     loc_18000BAEA
0x18000bb7a  mov     rcx, [rcx+18h]
0x18000bb7e  mov     edx, 23h ; '#'
0x18000bb83  mov     [rsp+78h+var_48], ebp
0x18000bb87  mov     r9, rbx
0x18000bb8a  mov     dword ptr [rsp+78h+var_50], r14d
0x18000bb8f  mov     [rsp+78h+var_58], r15
0x18000bb94  call    WPP_SF_qqdD
0x18000bb99  jmp     loc_18000BA88
0x18000bb9e  mov     rax, [rsi+60h]
0x18000bba2  mov     r9d, ebp
0x18000bba5  mov     rcx, [rbx+18h]
0x18000bba9  mov     r8d, r14d
0x18000bbac  mov     rdx, r15
0x18000bbaf  call    _guard_dispatch_icall
0x18000bbb4  mov     edi, eax
0x18000bbb6  test    eax, eax
0x18000bbb8  jns     loc_1800A50D1
0x18000bbbe  mov     r9d, 180Bh
0x18000bbc4  jmp     loc_1800A50B6
0x1800a50b0  mov     r9d, 1814h
0x1800a50b6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a50bd  mov     ecx, eax
0x1800a50bf  lea     rdx, aStatus; "Status"
0x1800a50c6  call    DebugTraceError
0x1800a50cb  nop
0x1800a50cc  jmp     loc_18000BAEA
0x1800a50d1  mov     rax, [rsi+68h]
0x1800a50d5  mov     r9d, ebp
0x1800a50d8  mov     rcx, [rbx+18h]
0x1800a50dc  mov     r8d, r14d
0x1800a50df  mov     rdx, r15
0x1800a50e2  call    _guard_dispatch_icall
0x1800a50e7  mov     edi, eax
0x1800a50e9  test    eax, eax
0x1800a50eb  jns     loc_18000BAE8
0x1800a50f1  jmp     short loc_1800A50B0
```
