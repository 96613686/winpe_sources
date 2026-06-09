# SslImportKey

- ea: `0x1800061f0`
- end: `0x1800063ff`
- name: `SslImportKey`
- size: `527`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800061f0`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x18009d860`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800062f0`
- `ntoskrnl!ExAllocatePool2` at `0x1800062f0`
- `ntoskrnl!SkIsSecureKernel` at `0x18000637f`
- `ntoskrnl!SkIsSecureKernel` at `0x18000637f`
- `ntoskrnl!SkAllocatePool` at `0x1800063a1`
- `ntoskrnl!SkAllocatePool` at `0x1800063a1`

## string_xrefs

- `0x180006257`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000629c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800063b2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800063d7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslImportKey(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, int a5, int a6)
{
  unsigned int v10; // ebp
  int v11; // edx
  int v12; // eax
  _OWORD *Pool; // rax
  _DWORD *v14; // rsi
  int v15; // eax

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 )
    {
      LOBYTE(v12) = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
      {
        v12 = ((int)SkIsSecureKernel(a1, a2) >> 31) + 2;
        g_TrustedEnvironment = v12;
      }
      if ( (v12 & 2) != 0 )
        Pool = (_OWORD *)SkAllocatePool(512, 32, 1650945603);
      else
        Pool = (_OWORD *)ExAllocatePool2(64, 32, 1650945603);
      v14 = Pool;
      if ( Pool )
      {
        *Pool = 0;
        Pool[1] = 0;
        v15 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64, __int64, int, int))(a1 + 176))(
                *(_QWORD *)(a1 + 424),
                Pool + 1,
                a3,
                a4,
                a5,
                a6);
        v10 = v15;
        if ( v15 < 0 )
        {
          DebugTraceError(
            (unsigned int)v15,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            2619);
          MSCryptFree(v14);
        }
        else
        {
          *v14 = 32;
          *(_QWORD *)(v14 + 1) = 1145324610;
          v14[3] = 1;
          *((_QWORD *)v14 + 3) = a1;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
          *a2 = v14;
          return 0;
        }
      }
      else
      {
        v10 = -2146893810;
        DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2600);
      }
    }
    else
    {
      v10 = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          0,
          a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          24);
    }
  }
  else
  {
    v10 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v11 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v11 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v11,
          a3,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          17);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800061f0  push    rbx
0x1800061f2  push    rbp
0x1800061f3  push    rsi
0x1800061f4  push    rdi
0x1800061f5  push    r14
0x1800061f7  sub     rsp, 40h
0x1800061fb  mov     rbp, r9
0x1800061fe  mov     r14, r8
0x180006201  mov     rdi, rdx
0x180006204  mov     rbx, rcx
0x180006207  test    rcx, rcx
0x18000620a  jz      short loc_180006227
0x18000620c  cmp     dword ptr [rcx], 1B0h
0x180006212  jb      short loc_180006227
0x180006214  cmp     dword ptr [rcx+4], 44444441h
0x18000621b  jnz     short loc_180006227
0x18000621d  cmp     dword ptr [rcx+0Ch], 0
0x180006221  jz      loc_1800062C5
0x180006227  mov     ebp, 80090026h
0x18000622c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006233  lea     rax, WPP_GLOBAL_Control
0x18000623a  cmp     rcx, rax
0x18000623d  jz      loc_180006371
0x180006243  mov     edx, [rcx+2Ch]
0x180006246  test    dl, 1
0x180006249  jz      loc_180006371
0x18000624f  mov     [rsp+68h+var_38], 0A11h
0x180006257  lea     rax, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000625e  mov     [rsp+68h+var_40], rax
0x180006263  mov     [rsp+68h+var_48], 80090026h
0x18000626b  jmp     short loc_1800062B0
0x18000626d  mov     ebp, 80090027h
0x180006272  mov     rcx, cs:WPP_GLOBAL_Control
0x180006279  lea     rax, WPP_GLOBAL_Control
0x180006280  cmp     rcx, rax
0x180006283  jz      loc_180006371
0x180006289  mov     eax, [rcx+2Ch]
0x18000628c  test    al, 1
0x18000628e  jz      loc_180006371
0x180006294  mov     [rsp+68h+var_38], 0A18h
0x18000629c  lea     rax, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800062a3  mov     [rsp+68h+var_40], rax
0x1800062a8  mov     [rsp+68h+var_48], 80090027h
0x1800062b0  mov     rcx, [rcx+18h]
0x1800062b4  lea     r9, aStatus; "Status"
0x1800062bb  call    WPP_SF_sDsd
0x1800062c0  jmp     loc_180006371
0x1800062c5  test    rdi, rdi
0x1800062c8  jz      short loc_18000626D
0x1800062ca  mov     eax, cs:g_TrustedEnvironment
0x1800062d0  test    eax, eax
0x1800062d2  jz      loc_18000637F
0x1800062d8  mov     edx, 20h ; ' '
0x1800062dd  mov     r8d, 62676E43h
0x1800062e3  test    al, 2
0x1800062e5  jnz     loc_18000639C
0x1800062eb  mov     ecx, 40h ; '@'
0x1800062f0  call    cs:__imp_ExAllocatePool2
0x1800062f7  nop     dword ptr [rax+rax+00h]
0x1800062fc  mov     rsi, rax
0x1800062ff  test    rax, rax
0x180006302  jz      loc_1800063B2
0x180006308  lea     rdx, [rax+10h]
0x18000630c  xorps   xmm0, xmm0
0x18000630f  movups  xmmword ptr [rax], xmm0
0x180006312  mov     r9, rbp
0x180006315  mov     r8, r14
0x180006318  movups  xmmword ptr [rax+10h], xmm0
0x18000631c  mov     eax, [rsp+68h+arg_28]
0x180006323  mov     rcx, [rbx+1A8h]
0x18000632a  mov     dword ptr [rsp+68h+var_40], eax
0x18000632e  mov     eax, [rsp+68h+arg_20]
0x180006335  mov     [rsp+68h+var_48], eax
0x180006339  mov     rax, [rbx+0B0h]
0x180006340  call    _guard_dispatch_icall
0x180006345  mov     ebp, eax
0x180006347  test    eax, eax
0x180006349  js      loc_1800063D7
0x18000634f  mov     dword ptr [rsi], 20h ; ' '
0x180006355  mov     qword ptr [rsi+4], 44444442h
0x18000635d  mov     dword ptr [rsi+0Ch], 1
0x180006364  mov     [rsi+18h], rbx
0x180006368  lock inc dword ptr [rbx+10h]
0x18000636c  mov     [rdi], rsi
0x18000636f  xor     ebp, ebp
0x180006371  mov     eax, ebp
0x180006373  add     rsp, 40h
0x180006377  pop     r14
0x180006379  pop     rdi
0x18000637a  pop     rsi
0x18000637b  pop     rbp
0x18000637c  pop     rbx
0x18000637d  retn
0x18000637f  call    cs:__imp_SkIsSecureKernel
0x180006386  nop     dword ptr [rax+rax+00h]
0x18000638b  sar     eax, 1Fh
0x18000638e  add     eax, 2
0x180006391  mov     cs:g_TrustedEnvironment, eax
0x180006397  jmp     loc_1800062D8
0x18000639c  mov     ecx, 200h
0x1800063a1  call    cs:__imp_SkAllocatePool
0x1800063a8  nop     dword ptr [rax+rax+00h]
0x1800063ad  jmp     loc_1800062FC
0x1800063b2  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800063b9  mov     r9d, 0A28h
0x1800063bf  lea     rdx, aStatus; "Status"
0x1800063c6  mov     ecx, 8009000Eh
0x1800063cb  mov     ebp, 8009000Eh
0x1800063d0  call    DebugTraceError
0x1800063d5  jmp     short loc_180006371
0x1800063d7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800063de  mov     r9d, 0A3Bh
0x1800063e4  lea     rdx, aStatus; "Status"
0x1800063eb  mov     ecx, eax
0x1800063ed  call    DebugTraceError
0x1800063f2  mov     rcx, rsi; P
0x1800063f5  call    MSCryptFree
0x1800063fa  jmp     loc_180006371
```
