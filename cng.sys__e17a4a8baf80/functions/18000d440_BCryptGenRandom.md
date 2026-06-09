# BCryptGenRandom

- ea: `0x18000d440`
- end: `0x18000d5bf`
- name: `BCryptGenRandom`
- size: `383`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e104`
- `0x180053184`
- `0x1800619c0`
- `0x180072064`

## callees

- `0x18000d440`
- `0x18000daf0`
- `0x18000e104`
- `0x18001155c`
- `0x1800123d0`
- `0x18005200c`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000d4c6`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000d4c6`

## string_xrefs

- `0x18000d51c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a54b6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptGenRandom(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)
{
  __int64 v8; // rax
  int v9; // eax
  NTSTATUS v10; // ebx
  int v12; // edx
  __int64 v13; // r9
  __int64 v14; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqdD(*((_QWORD *)WPP_GLOBAL_Control + 3), 40, cbBuffer, hAlgorithm, pbBuffer, cbBuffer, dwFlags);
  if ( (dwFlags & 2) == 0 )
  {
    v8 = ValidateBaseAlgHandle(hAlgorithm);
    if ( v8 )
    {
      if ( *(_DWORD *)(v8 + 36) == 6 )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, _QWORD, _QWORD))(v8 + 88))(
               *(_QWORD *)(v8 + 24),
               pbBuffer,
               cbBuffer,
               dwFlags);
        v10 = v9;
        if ( v9 >= 0 )
          return v10;
        v13 = 7098;
        goto LABEL_20;
      }
      v10 = -1073741816;
      v13 = 7087;
      v14 = 3221225480LL;
    }
    else
    {
      v10 = -1073741816;
      v13 = 7080;
      v14 = 3221225480LL;
    }
    goto LABEL_21;
  }
  if ( !KeGetCurrentIrql() )
  {
    if ( !hAlgorithm )
    {
      v9 = BCryptGenSystemPreferredRandom(pbBuffer, cbBuffer, dwFlags & 0xFFFFFFFD);
      v10 = v9;
      if ( v9 >= 0 )
        return v10;
      v13 = 7069;
LABEL_20:
      v14 = (unsigned int)v9;
      goto LABEL_21;
    }
    v10 = -1073741811;
    v13 = 7059;
    v14 = 3221225485LL;
LABEL_21:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v13);
    return v10;
  }
  v10 = -1073741637;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0 )
    return v10;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 3),
    v12,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
    (unsigned int)"Status",
    187,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
    140);
  return -1073741637;
}

```

## disassembly

```asm
0x18000d440  push    rbx
0x18000d442  push    rbp
0x18000d443  push    rsi
0x18000d444  push    rdi
0x18000d445  push    r14
0x18000d447  sub     rsp, 40h
0x18000d44b  mov     ebx, r9d
0x18000d44e  mov     esi, r8d
0x18000d451  mov     rbp, rdx
0x18000d454  mov     rdi, rcx
0x18000d457  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d45e  lea     r14, WPP_GLOBAL_Control
0x18000d465  cmp     rcx, r14
0x18000d468  jz      short loc_18000D475
0x18000d46a  mov     eax, [rcx+2Ch]
0x18000d46d  test    al, 4
0x18000d46f  jnz     loc_18000D552
0x18000d475  test    bl, 2
0x18000d478  jnz     short loc_18000D4C6
0x18000d47a  mov     rcx, rdi
0x18000d47d  call    ValidateBaseAlgHandle
0x18000d482  mov     rcx, rax
0x18000d485  test    rax, rax
0x18000d488  jz      loc_18000D58A
0x18000d48e  cmp     dword ptr [rax+24h], 6
0x18000d492  jnz     loc_18000D59F
0x18000d498  mov     rax, [rax+58h]
0x18000d49c  mov     r9d, ebx
0x18000d49f  mov     rcx, [rcx+18h]
0x18000d4a3  mov     r8d, esi
0x18000d4a6  mov     rdx, rbp
0x18000d4a9  call    _guard_dispatch_icall
0x18000d4ae  mov     ebx, eax
0x18000d4b0  test    eax, eax
0x18000d4b2  js      loc_18000D5B4
0x18000d4b8  mov     eax, ebx
0x18000d4ba  add     rsp, 40h
0x18000d4be  pop     r14
0x18000d4c0  pop     rdi
0x18000d4c1  pop     rsi
0x18000d4c2  pop     rbp
0x18000d4c3  pop     rbx
0x18000d4c4  retn
0x18000d4c6  call    cs:__imp_KeGetCurrentIrql
0x18000d4cd  nop     dword ptr [rax+rax+00h]
0x18000d4d2  test    al, al
0x18000d4d4  jnz     short loc_18000D500
0x18000d4d6  test    rdi, rdi
0x18000d4d9  jnz     loc_18000D575
0x18000d4df  and     ebx, 0FFFFFFFDh
0x18000d4e2  mov     edx, esi; cbBuffer
0x18000d4e4  mov     r8d, ebx; dwFlags
0x18000d4e7  mov     rcx, rbp; pbBuffer
0x18000d4ea  call    BCryptGenSystemPreferredRandom
0x18000d4ef  mov     ebx, eax
0x18000d4f1  test    eax, eax
0x18000d4f3  jns     short loc_18000D4B8
0x18000d4f5  mov     r9d, 1B9Dh
0x18000d4fb  jmp     loc_1800A54B4
0x18000d500  mov     ebx, 0C00000BBh
0x18000d505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d50c  cmp     rcx, r14
0x18000d50f  jz      short loc_18000D4B8
0x18000d511  mov     eax, [rcx+2Ch]
0x18000d514  test    al, 1
0x18000d516  jz      short loc_18000D4B8
0x18000d518  mov     rcx, [rcx+18h]
0x18000d51c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d523  mov     [rsp+68h+var_38], 1B8Ch
0x18000d52b  lea     r9, aStatus; "Status"
0x18000d532  mov     [rsp+68h+var_40], r8
0x18000d537  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x18000d53f  call    WPP_SF_sDsd
0x18000d544  mov     eax, ebx
0x18000d546  add     rsp, 40h
0x18000d54a  pop     r14
0x18000d54c  pop     rdi
0x18000d54d  pop     rsi
0x18000d54e  pop     rbp
0x18000d54f  pop     rbx
0x18000d550  retn
0x18000d552  mov     rcx, [rcx+18h]
0x18000d556  mov     edx, 28h ; '('
0x18000d55b  mov     [rsp+68h+var_38], ebx
0x18000d55f  mov     r9, rdi
0x18000d562  mov     dword ptr [rsp+68h+var_40], esi
0x18000d566  mov     [rsp+68h+var_48], rbp
0x18000d56b  call    WPP_SF_qqdD
0x18000d570  jmp     loc_18000D475
0x18000d575  mov     ebx, 0C000000Dh
0x18000d57a  mov     r9d, 1B93h
0x18000d580  mov     ecx, 0C000000Dh
0x18000d585  jmp     loc_1800A54B6
0x18000d58a  mov     ebx, 0C0000008h
0x18000d58f  mov     r9d, 1BA8h
0x18000d595  mov     ecx, 0C0000008h
0x18000d59a  jmp     loc_1800A54B6
0x18000d59f  mov     ebx, 0C0000008h
0x18000d5a4  mov     r9d, 1BAFh
0x18000d5aa  mov     ecx, 0C0000008h
0x18000d5af  jmp     loc_1800A54B6
0x18000d5b4  mov     r9d, 1BBAh
0x18000d5ba  jmp     loc_1800A54B4
0x1800a54b4  mov     ecx, eax
0x1800a54b6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a54bd  lea     rdx, aStatus; "Status"
0x1800a54c4  call    DebugTraceError
0x1800a54c9  nop
0x1800a54ca  jmp     loc_18000D4B8
```
