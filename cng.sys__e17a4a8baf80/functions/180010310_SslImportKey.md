# SslImportKey

- ea: `0x180010310`
- end: `0x18001051f`
- name: `SslImportKey`
- size: `527`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180010310`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180010410`
- `ntoskrnl!ExAllocatePool2` at `0x180010410`
- `ntoskrnl!SkIsSecureKernel` at `0x18001049f`
- `ntoskrnl!SkIsSecureKernel` at `0x18001049f`
- `ntoskrnl!SkAllocatePool` at `0x1800104c1`
- `ntoskrnl!SkAllocatePool` at `0x1800104c1`

## string_xrefs

- `0x180010377`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800103bc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800104d2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800104f7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

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
0x180010310  push    rbx
0x180010312  push    rbp
0x180010313  push    rsi
0x180010314  push    rdi
0x180010315  push    r14
0x180010317  sub     rsp, 40h
0x18001031b  mov     rbp, r9
0x18001031e  mov     r14, r8
0x180010321  mov     rdi, rdx
0x180010324  mov     rbx, rcx
0x180010327  test    rcx, rcx
0x18001032a  jz      short loc_180010347
0x18001032c  cmp     dword ptr [rcx], 1B0h
0x180010332  jb      short loc_180010347
0x180010334  cmp     dword ptr [rcx+4], 44444441h
0x18001033b  jnz     short loc_180010347
0x18001033d  cmp     dword ptr [rcx+0Ch], 0
0x180010341  jz      loc_1800103E5
0x180010347  mov     ebp, 80090026h
0x18001034c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010353  lea     rax, WPP_GLOBAL_Control
0x18001035a  cmp     rcx, rax
0x18001035d  jz      loc_180010491
0x180010363  mov     edx, [rcx+2Ch]
0x180010366  test    dl, 1
0x180010369  jz      loc_180010491
0x18001036f  mov     [rsp+68h+var_38], 0A11h
0x180010377  lea     rax, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001037e  mov     [rsp+68h+var_40], rax
0x180010383  mov     [rsp+68h+var_48], 80090026h
0x18001038b  jmp     short loc_1800103D0
0x18001038d  mov     ebp, 80090027h
0x180010392  mov     rcx, cs:WPP_GLOBAL_Control
0x180010399  lea     rax, WPP_GLOBAL_Control
0x1800103a0  cmp     rcx, rax
0x1800103a3  jz      loc_180010491
0x1800103a9  mov     eax, [rcx+2Ch]
0x1800103ac  test    al, 1
0x1800103ae  jz      loc_180010491
0x1800103b4  mov     [rsp+68h+var_38], 0A18h
0x1800103bc  lea     rax, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800103c3  mov     [rsp+68h+var_40], rax
0x1800103c8  mov     [rsp+68h+var_48], 80090027h
0x1800103d0  mov     rcx, [rcx+18h]
0x1800103d4  lea     r9, aStatus; "Status"
0x1800103db  call    WPP_SF_sDsd
0x1800103e0  jmp     loc_180010491
0x1800103e5  test    rdi, rdi
0x1800103e8  jz      short loc_18001038D
0x1800103ea  mov     eax, cs:g_TrustedEnvironment
0x1800103f0  test    eax, eax
0x1800103f2  jz      loc_18001049F
0x1800103f8  mov     edx, 20h ; ' '
0x1800103fd  mov     r8d, 62676E43h
0x180010403  test    al, 2
0x180010405  jnz     loc_1800104BC
0x18001040b  mov     ecx, 40h ; '@'
0x180010410  call    cs:__imp_ExAllocatePool2
0x180010417  nop     dword ptr [rax+rax+00h]
0x18001041c  mov     rsi, rax
0x18001041f  test    rax, rax
0x180010422  jz      loc_1800104D2
0x180010428  lea     rdx, [rax+10h]
0x18001042c  xorps   xmm0, xmm0
0x18001042f  movups  xmmword ptr [rax], xmm0
0x180010432  mov     r9, rbp
0x180010435  mov     r8, r14
0x180010438  movups  xmmword ptr [rax+10h], xmm0
0x18001043c  mov     eax, [rsp+68h+arg_28]
0x180010443  mov     rcx, [rbx+1A8h]
0x18001044a  mov     dword ptr [rsp+68h+var_40], eax
0x18001044e  mov     eax, [rsp+68h+arg_20]
0x180010455  mov     [rsp+68h+var_48], eax
0x180010459  mov     rax, [rbx+0B0h]
0x180010460  call    _guard_dispatch_icall
0x180010465  mov     ebp, eax
0x180010467  test    eax, eax
0x180010469  js      loc_1800104F7
0x18001046f  mov     dword ptr [rsi], 20h ; ' '
0x180010475  mov     qword ptr [rsi+4], 44444442h
0x18001047d  mov     dword ptr [rsi+0Ch], 1
0x180010484  mov     [rsi+18h], rbx
0x180010488  lock inc dword ptr [rbx+10h]
0x18001048c  mov     [rdi], rsi
0x18001048f  xor     ebp, ebp
0x180010491  mov     eax, ebp
0x180010493  add     rsp, 40h
0x180010497  pop     r14
0x180010499  pop     rdi
0x18001049a  pop     rsi
0x18001049b  pop     rbp
0x18001049c  pop     rbx
0x18001049d  retn
0x18001049f  call    cs:__imp_SkIsSecureKernel
0x1800104a6  nop     dword ptr [rax+rax+00h]
0x1800104ab  sar     eax, 1Fh
0x1800104ae  add     eax, 2
0x1800104b1  mov     cs:g_TrustedEnvironment, eax
0x1800104b7  jmp     loc_1800103F8
0x1800104bc  mov     ecx, 200h
0x1800104c1  call    cs:__imp_SkAllocatePool
0x1800104c8  nop     dword ptr [rax+rax+00h]
0x1800104cd  jmp     loc_18001041C
0x1800104d2  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800104d9  mov     r9d, 0A28h
0x1800104df  lea     rdx, aStatus; "Status"
0x1800104e6  mov     ecx, 8009000Eh
0x1800104eb  mov     ebp, 8009000Eh
0x1800104f0  call    DebugTraceError
0x1800104f5  jmp     short loc_180010491
0x1800104f7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800104fe  mov     r9d, 0A3Bh
0x180010504  lea     rdx, aStatus; "Status"
0x18001050b  mov     ecx, eax
0x18001050d  call    DebugTraceError
0x180010512  mov     rcx, rsi; P
0x180010515  call    MSCryptFree
0x18001051a  jmp     loc_180010491
```
