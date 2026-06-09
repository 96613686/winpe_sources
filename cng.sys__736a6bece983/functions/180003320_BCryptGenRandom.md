# BCryptGenRandom

- ea: `0x180003320`
- end: `0x18000349f`
- name: `BCryptGenRandom`
- size: `383`
- prototype: `NTSTATUS __stdcall(BCRYPT_ALG_HANDLE hAlgorithm, PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003fe4`
- `0x180049b14`
- `0x1800580e0`
- `0x1800688c4`

## callees

- `0x180003320`
- `0x1800039d0`
- `0x180003fe4`
- `0x18000743c`
- `0x1800082b0`
- `0x1800489ac`
- `0x18009f6d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800033a6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800033a6`

## string_xrefs

- `0x1800033fc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800a0548`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180003320  push    rbx
0x180003322  push    rbp
0x180003323  push    rsi
0x180003324  push    rdi
0x180003325  push    r14
0x180003327  sub     rsp, 40h
0x18000332b  mov     ebx, r9d
0x18000332e  mov     esi, r8d
0x180003331  mov     rbp, rdx
0x180003334  mov     rdi, rcx
0x180003337  mov     rcx, cs:WPP_GLOBAL_Control
0x18000333e  lea     r14, WPP_GLOBAL_Control
0x180003345  cmp     rcx, r14
0x180003348  jz      short loc_180003355
0x18000334a  mov     eax, [rcx+2Ch]
0x18000334d  test    al, 4
0x18000334f  jnz     loc_180003432
0x180003355  test    bl, 2
0x180003358  jnz     short loc_1800033A6
0x18000335a  mov     rcx, rdi
0x18000335d  call    ValidateBaseAlgHandle
0x180003362  mov     rcx, rax
0x180003365  test    rax, rax
0x180003368  jz      loc_18000346A
0x18000336e  cmp     dword ptr [rax+24h], 6
0x180003372  jnz     loc_18000347F
0x180003378  mov     rax, [rax+58h]
0x18000337c  mov     r9d, ebx
0x18000337f  mov     rcx, [rcx+18h]
0x180003383  mov     r8d, esi
0x180003386  mov     rdx, rbp
0x180003389  call    _guard_dispatch_icall
0x18000338e  mov     ebx, eax
0x180003390  test    eax, eax
0x180003392  js      loc_180003494
0x180003398  mov     eax, ebx
0x18000339a  add     rsp, 40h
0x18000339e  pop     r14
0x1800033a0  pop     rdi
0x1800033a1  pop     rsi
0x1800033a2  pop     rbp
0x1800033a3  pop     rbx
0x1800033a4  retn
0x1800033a6  call    cs:__imp_KeGetCurrentIrql
0x1800033ad  nop     dword ptr [rax+rax+00h]
0x1800033b2  test    al, al
0x1800033b4  jnz     short loc_1800033E0
0x1800033b6  test    rdi, rdi
0x1800033b9  jnz     loc_180003455
0x1800033bf  and     ebx, 0FFFFFFFDh
0x1800033c2  mov     edx, esi; cbBuffer
0x1800033c4  mov     r8d, ebx; dwFlags
0x1800033c7  mov     rcx, rbp; pbBuffer
0x1800033ca  call    BCryptGenSystemPreferredRandom
0x1800033cf  mov     ebx, eax
0x1800033d1  test    eax, eax
0x1800033d3  jns     short loc_180003398
0x1800033d5  mov     r9d, 1B9Dh
0x1800033db  jmp     loc_1800A0546
0x1800033e0  mov     ebx, 0C00000BBh
0x1800033e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033ec  cmp     rcx, r14
0x1800033ef  jz      short loc_180003398
0x1800033f1  mov     eax, [rcx+2Ch]
0x1800033f4  test    al, 1
0x1800033f6  jz      short loc_180003398
0x1800033f8  mov     rcx, [rcx+18h]
0x1800033fc  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003403  mov     [rsp+68h+var_38], 1B8Ch
0x18000340b  lea     r9, aStatus; "Status"
0x180003412  mov     [rsp+68h+var_40], r8
0x180003417  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x18000341f  call    WPP_SF_sDsd
0x180003424  mov     eax, ebx
0x180003426  add     rsp, 40h
0x18000342a  pop     r14
0x18000342c  pop     rdi
0x18000342d  pop     rsi
0x18000342e  pop     rbp
0x18000342f  pop     rbx
0x180003430  retn
0x180003432  mov     rcx, [rcx+18h]
0x180003436  mov     edx, 28h ; '('
0x18000343b  mov     [rsp+68h+var_38], ebx
0x18000343f  mov     r9, rdi
0x180003442  mov     dword ptr [rsp+68h+var_40], esi
0x180003446  mov     [rsp+68h+var_48], rbp
0x18000344b  call    WPP_SF_qqdD
0x180003450  jmp     loc_180003355
0x180003455  mov     ebx, 0C000000Dh
0x18000345a  mov     r9d, 1B93h
0x180003460  mov     ecx, 0C000000Dh
0x180003465  jmp     loc_1800A0548
0x18000346a  mov     ebx, 0C0000008h
0x18000346f  mov     r9d, 1BA8h
0x180003475  mov     ecx, 0C0000008h
0x18000347a  jmp     loc_1800A0548
0x18000347f  mov     ebx, 0C0000008h
0x180003484  mov     r9d, 1BAFh
0x18000348a  mov     ecx, 0C0000008h
0x18000348f  jmp     loc_1800A0548
0x180003494  mov     r9d, 1BBAh
0x18000349a  jmp     loc_1800A0546
0x1800a0546  mov     ecx, eax
0x1800a0548  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a054f  lea     rdx, aStatus; "Status"
0x1800a0556  call    DebugTraceError
0x1800a055b  nop
0x1800a055c  jmp     loc_180003398
```
