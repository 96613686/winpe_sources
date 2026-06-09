# Tls1ComputeFinishedHash

- ea: `0x18000860c`
- end: `0x1800087fe`
- name: `Tls1ComputeFinishedHash`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *, ULONG cbOutput, __int64, int, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800091e0`

## callees

- `0x18000860c`
- `0x180008810`
- `0x18000b654`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18000868a`
- `bcrypt!BCryptFinishHash` at `0x180008763`
- `bcrypt!BCryptFinishHash` at `0x18000868a`
- `bcrypt!BCryptFinishHash` at `0x180008763`

## string_xrefs

- `0x180008785`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800087be`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800087d5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1ComputeFinishedHash(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4,
        ULONG cbOutput,
        __int64 a6,
        int a7,
        char a8)
{
  int v10; // ebp
  UCHAR *v12; // rdx
  NTSTATUS v13; // eax
  const char *v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  NTSTATUS v18; // eax
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  UCHAR pbOutput[64]; // [rsp+60h] [rbp-78h] BYREF

  v10 = 64;
  memset(pbOutput, 0, sizeof(pbOutput));
  if ( a7 != 12 )
  {
    v16 = -2146893785;
    v21 = 3206;
    v22 = 2148073511LL;
LABEL_20:
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v21);
    return v16;
  }
  if ( !a3 )
  {
    if ( cbOutput > 0x40 )
      goto LABEL_6;
    v10 = cbOutput;
    v12 = pbOutput;
    goto LABEL_5;
  }
  if ( cbOutput != 20 )
  {
    v19 = 3284;
    v20 = 2148073511LL;
LABEL_17:
    DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v19);
    goto LABEL_6;
  }
  v18 = BCryptFinishHash(a3, pbOutput, 0x10u, 0);
  if ( v18 >= 0 )
  {
    v12 = &pbOutput[16];
    v10 = 36;
LABEL_5:
    v13 = BCryptFinishHash(a4, v12, cbOutput, 0);
    if ( v13 >= 0 )
      goto LABEL_6;
    v19 = 3342;
    v20 = (unsigned int)v13;
    goto LABEL_17;
  }
  DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 3330);
  v10 = 36;
LABEL_6:
  if ( (a8 & 1) != 0 )
  {
    v14 = "client finished";
  }
  else
  {
    if ( (a8 & 2) == 0 )
      return (unsigned int)-2146893815;
    v14 = "server finished";
  }
  v15 = Tls1Prf(
          *(unsigned int *)(a2 + 8),
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 104LL),
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 136LL),
          a2 + 28,
          48,
          v14,
          15,
          pbOutput,
          v10,
          a6,
          12);
  v16 = v15;
  if ( v15 < 0 )
  {
    v21 = 3253;
    v22 = (unsigned int)v15;
    goto LABEL_20;
  }
  return v16;
}

```

## disassembly

```asm
0x18000860c  mov     [rsp+arg_0], rbx
0x180008611  push    rbp
0x180008612  push    r12
0x180008614  push    r13
0x180008616  push    r14
0x180008618  push    r15
0x18000861a  sub     rsp, 0B0h
0x180008621  mov     rax, cs:__security_cookie
0x180008628  xor     rax, rsp
0x18000862b  mov     [rsp+0D8h+var_38], rax
0x180008633  mov     r12, [rsp+0D8h+arg_28]
0x18000863b  lea     rcx, [rsp+0D8h+pbOutput]; void *
0x180008640  mov     r14, r8
0x180008643  mov     r13, rdx
0x180008646  mov     ebp, 40h ; '@'
0x18000864b  xor     edx, edx; Val
0x18000864d  mov     r8d, ebp; Size
0x180008650  mov     r15, r9
0x180008653  call    memset
0x180008658  cmp     [rsp+0D8h+arg_30], 0Ch
0x180008660  jnz     loc_18000879D
0x180008666  mov     ebx, [rsp+0D8h+cbOutput]
0x18000866d  test    r14, r14
0x180008670  jnz     loc_18000874F
0x180008676  cmp     ebx, ebp
0x180008678  ja      short loc_180008698
0x18000867a  mov     ebp, ebx
0x18000867c  lea     rdx, [rsp+0D8h+pbOutput]; pbOutput
0x180008681  xor     r9d, r9d; dwFlags
0x180008684  mov     r8d, ebx; cbOutput
0x180008687  mov     rcx, r15; hHash
0x18000868a  call    cs:__imp_BCryptFinishHash
0x180008690  test    eax, eax
0x180008692  js      loc_1800087F4
0x180008698  test    [rsp+0D8h+arg_38], 1
0x1800086a0  jnz     loc_18000873C
0x1800086a6  test    [rsp+0D8h+arg_38], 2
0x1800086ae  jz      loc_180008748
0x1800086b4  lea     rax, aServerFinished; "server finished"
0x1800086bb  mov     rdx, [r13+10h]
0x1800086bf  lea     rcx, [rsp+0D8h+pbOutput]
0x1800086c4  mov     [rsp+0D8h+var_88], 0Ch
0x1800086cc  lea     r9, [r13+1Ch]
0x1800086d0  mov     [rsp+0D8h+var_90], r12
0x1800086d5  mov     [rsp+0D8h+var_98], ebp
0x1800086d9  mov     r8, [rdx+88h]
0x1800086e0  mov     rdx, [rdx+68h]
0x1800086e4  mov     [rsp+0D8h+var_A0], rcx
0x1800086e9  mov     ecx, [r13+8]
0x1800086ed  mov     [rsp+0D8h+var_A8], 0Fh
0x1800086f5  mov     [rsp+0D8h+var_B0], rax
0x1800086fa  mov     [rsp+0D8h+var_B8], 30h ; '0'
0x180008702  call    Tls1Prf
0x180008707  mov     ebx, eax
0x180008709  test    eax, eax
0x18000870b  js      loc_1800087AF
0x180008711  mov     eax, ebx
0x180008713  mov     rcx, [rsp+0D8h+var_38]
0x18000871b  xor     rcx, rsp; StackCookie
0x18000871e  call    __security_check_cookie
0x180008723  mov     rbx, [rsp+0D8h+arg_0]
0x18000872b  add     rsp, 0B0h
0x180008732  pop     r15
0x180008734  pop     r14
0x180008736  pop     r13
0x180008738  pop     r12
0x18000873a  pop     rbp
0x18000873b  retn
0x18000873c  lea     rax, aClientFinished; "client finished"
0x180008743  jmp     loc_1800086BB
0x180008748  mov     ebx, 80090009h
0x18000874d  jmp     short loc_180008711
0x18000874f  cmp     ebx, 14h
0x180008752  jnz     short loc_18000877A
0x180008754  xor     r9d, r9d; dwFlags
0x180008757  lea     r8d, [rbx-4]; cbOutput
0x18000875b  lea     rdx, [rsp+0D8h+pbOutput]; pbOutput
0x180008760  mov     rcx, r14; hHash
0x180008763  call    cs:__imp_BCryptFinishHash
0x180008769  test    eax, eax
0x18000876b  js      short loc_1800087CF
0x18000876d  lea     rdx, [rsp+0D8h+var_68]
0x180008772  lea     ebp, [rbx+10h]
0x180008775  jmp     loc_180008681
0x18000877a  mov     r9d, 0CD4h
0x180008780  mov     ecx, 80090027h
0x180008785  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000878c  lea     rdx, aStatus; "Status"
0x180008793  call    DebugTraceError
0x180008798  jmp     loc_180008698
0x18000879d  mov     ebx, 80090027h
0x1800087a2  mov     r9d, 0C86h
0x1800087a8  mov     ecx, 80090027h
0x1800087ad  jmp     short loc_1800087B7
0x1800087af  mov     r9d, 0CB5h
0x1800087b5  mov     ecx, eax
0x1800087b7  lea     rdx, aStatus; "Status"
0x1800087be  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800087c5  call    DebugTraceError
0x1800087ca  jmp     loc_180008711
0x1800087cf  mov     r9d, 0D02h
0x1800087d5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800087dc  lea     rdx, aStatus; "Status"
0x1800087e3  mov     ecx, eax
0x1800087e5  call    DebugTraceError
0x1800087ea  mov     ebp, 24h ; '$'
0x1800087ef  jmp     loc_180008698
0x1800087f4  mov     r9d, 0D0Eh
0x1800087fa  mov     ecx, eax
0x1800087fc  jmp     short loc_180008785
```
