# SrvCryptCreatePersistedKey

- ea: `0x18000e120`
- end: `0x18000e2ab`
- name: `SrvCryptCreatePersistedKey`
- size: `395`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1800025b0`
- `0x180002d20`
- `0x180003cf0`
- `0x1800048f0`
- `0x180005510`
- `0x180006e60`
- `0x18000a638`
- `0x18000e120`
- `0x180019010`

## string_xrefs

- `0x18000e13f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e195`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e21f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptCreatePersistedKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7)
{
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rsi
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rdi
  unsigned int v17; // eax
  int v18; // eax
  bool v19; // zf

  if ( !a1 )
  {
    v10 = 535;
LABEL_3:
    v11 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v10);
    return (unsigned int)NormalizeNteStatus(v11);
  }
  v12 = SrvLookupAndReferenceProvider(a1, a2, 0);
  if ( !v12 )
  {
    v10 = 544;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v11 = -2146893785;
    v13 = 551;
    v14 = 2148073511LL;
LABEL_8:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v13);
    goto LABEL_15;
  }
  v15 = MSCryptAlloc(56);
  v16 = (_QWORD *)v15;
  if ( !v15 )
  {
    v11 = -2146893810;
    v13 = 565;
    v14 = 2148073486LL;
    goto LABEL_8;
  }
  *(_OWORD *)v15 = 0;
  *(_OWORD *)(v15 + 16) = 0;
  *(_OWORD *)(v15 + 32) = 0;
  *(_QWORD *)(v15 + 48) = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, int, int))(v12 + 64))(
          *(_QWORD *)(v12 + 296),
          v15 + 40,
          a4,
          a5,
          a6,
          a7);
  v11 = v17;
  if ( !v17 )
  {
    *v16 = 1145324615;
    v16[1] = 1;
    v16[4] = v12;
    SrvAddKeyToList(a1, v16, a3);
    return 0;
  }
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 587);
  if ( v16[5] )
    (*(void (__fastcall **)(_QWORD))(v12 + 128))(*(_QWORD *)(v12 + 296));
  SrvCryptLocalFree(v16);
LABEL_15:
  v18 = SrvDereferenceProvider(v12);
  if ( v18 >= 0 )
  {
    v19 = v11 == 0;
  }
  else
  {
    v19 = v11 == 0;
    if ( (v11 & 0x80000000) == 0 )
    {
      v11 = v18;
      return (unsigned int)NormalizeNteStatus(v11);
    }
  }
  if ( !v19 )
    return (unsigned int)NormalizeNteStatus(v11);
  return v11;
}

```

## disassembly

```asm
0x18000e120  push    rbx
0x18000e122  push    rbp
0x18000e123  push    rsi
0x18000e124  push    rdi
0x18000e125  push    r14
0x18000e127  sub     rsp, 40h
0x18000e12b  mov     rbx, r9
0x18000e12e  mov     r14, r8
0x18000e131  mov     rbp, rcx
0x18000e134  test    rcx, rcx
0x18000e137  jnz     short loc_18000E161
0x18000e139  mov     r9d, 217h
0x18000e13f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e146  mov     ecx, 80090026h
0x18000e14b  lea     rdx, aStatus; "Status"
0x18000e152  mov     ebx, 80090026h
0x18000e157  call    DebugTraceError
0x18000e15c  jmp     loc_18000E270
0x18000e161  xor     r8d, r8d
0x18000e164  call    SrvLookupAndReferenceProvider
0x18000e169  mov     rsi, rax
0x18000e16c  test    rax, rax
0x18000e16f  jnz     short loc_18000E179
0x18000e171  mov     r9d, 220h
0x18000e177  jmp     short loc_18000E13F
0x18000e179  test    r14, r14
0x18000e17c  jnz     short loc_18000E1A6
0x18000e17e  mov     ebx, 80090027h
0x18000e183  mov     r9d, 227h
0x18000e189  mov     ecx, 80090027h
0x18000e18e  lea     rdx, aStatus; "Status"
0x18000e195  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e19c  call    DebugTraceError
0x18000e1a1  jmp     loc_18000E258
0x18000e1a6  mov     ecx, 38h ; '8'
0x18000e1ab  call    MSCryptAlloc
0x18000e1b0  mov     rdi, rax
0x18000e1b3  test    rax, rax
0x18000e1b6  jnz     short loc_18000E1CA
0x18000e1b8  mov     ebx, 8009000Eh
0x18000e1bd  mov     r9d, 235h
0x18000e1c3  mov     ecx, 8009000Eh
0x18000e1c8  jmp     short loc_18000E18E
0x18000e1ca  mov     ecx, [rsp+68h+arg_30]
0x18000e1d1  lea     rdx, [rdi+28h]
0x18000e1d5  mov     r9, [rsp+68h+arg_20]
0x18000e1dd  xorps   xmm0, xmm0
0x18000e1e0  movups  xmmword ptr [rdi], xmm0
0x18000e1e3  mov     [rsp+68h+var_40], ecx
0x18000e1e7  xor     eax, eax
0x18000e1e9  mov     ecx, [rsp+68h+arg_28]
0x18000e1f0  mov     r8, rbx
0x18000e1f3  movups  xmmword ptr [rdi+10h], xmm0
0x18000e1f7  mov     [rsp+68h+var_48], ecx
0x18000e1fb  movups  xmmword ptr [rdi+20h], xmm0
0x18000e1ff  mov     [rdi+30h], rax
0x18000e203  mov     rcx, [rsi+128h]
0x18000e20a  mov     rax, [rsi+40h]
0x18000e20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e213  mov     ebx, eax
0x18000e215  test    eax, eax
0x18000e217  jz      short loc_18000E27B
0x18000e219  mov     r9d, 24Bh
0x18000e21f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e226  lea     rdx, aStatus; "Status"
0x18000e22d  mov     ecx, eax
0x18000e22f  call    DebugTraceError
0x18000e234  mov     rdx, [rdi+28h]
0x18000e238  test    rdx, rdx
0x18000e23b  jz      short loc_18000E250
0x18000e23d  mov     rcx, [rsi+128h]
0x18000e244  mov     rax, [rsi+80h]
0x18000e24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e250  mov     rcx, rdi; P
0x18000e253  call    SrvCryptLocalFree
0x18000e258  mov     rcx, rsi
0x18000e25b  call    SrvDereferenceProvider
0x18000e260  test    eax, eax
0x18000e262  jns     short loc_18000E26C
0x18000e264  test    ebx, ebx
0x18000e266  js      short loc_18000E26E
0x18000e268  mov     ebx, eax
0x18000e26a  jmp     short loc_18000E270
0x18000e26c  test    ebx, ebx
0x18000e26e  jz      short loc_18000E29E
0x18000e270  mov     ecx, ebx
0x18000e272  call    NormalizeNteStatus
0x18000e277  mov     ebx, eax
0x18000e279  jmp     short loc_18000E29E
0x18000e27b  mov     r8, r14
0x18000e27e  mov     qword ptr [rdi], 44444447h
0x18000e285  mov     rdx, rdi
0x18000e288  mov     qword ptr [rdi+8], 1
0x18000e290  mov     rcx, rbp
0x18000e293  mov     [rdi+20h], rsi
0x18000e297  call    SrvAddKeyToList
0x18000e29c  xor     ebx, ebx
0x18000e29e  mov     eax, ebx
0x18000e2a0  add     rsp, 40h
0x18000e2a4  pop     r14
0x18000e2a6  pop     rdi
0x18000e2a7  pop     rsi
0x18000e2a8  pop     rbp
0x18000e2a9  pop     rbx
0x18000e2aa  retn
```
