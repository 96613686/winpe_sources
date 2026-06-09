# SrvCryptDeriveKey

- ea: `0x18000e3f0`
- end: `0x18000e552`
- name: `SrvCryptDeriveKey`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1800026e4`
- `0x180003cf0`
- `0x1800048f0`
- `0x180006010`
- `0x180008f00`
- `0x18000e3f0`
- `0x1800112e0`
- `0x180019010`

## string_xrefs

- `0x18000e40c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e46d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e501`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptDeriveKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  __int64 v10; // r9
  int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rsi
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rbp
  unsigned int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax

  if ( !a1 )
  {
    v10 = 2940;
LABEL_3:
    v11 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v10);
    return NormalizeNteStatus((unsigned int)v11);
  }
  v12 = SrvLookupAndReferenceSecret(a1, a3, 0);
  v13 = v12;
  if ( !v12 )
  {
    v10 = 2949;
    goto LABEL_3;
  }
  if ( a8 )
  {
    v16 = 0;
    v17 = *(_QWORD *)(v12 + 32);
    if ( !a5 || (v16 = MapRPCToBufferDesc(a5)) != 0 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64, int, __int64, int))(v17 + 240))(
              *(_QWORD *)(v17 + 296),
              *(_QWORD *)(v13 + 40),
              a4,
              v16,
              a6,
              a7,
              a8,
              a9);
      v19 = v18;
      if ( v18 )
      {
        DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2990);
        v11 = NormalizeNteStatus(v19);
      }
      else
      {
        v11 = 0;
      }
      if ( v16 )
        FreeBufferDesc(v16);
      goto LABEL_17;
    }
    v11 = -2146893810;
    v14 = 2969;
    v15 = 2148073486LL;
  }
  else
  {
    v11 = -2146893785;
    v14 = 2958;
    v15 = 2148073511LL;
  }
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v14);
LABEL_17:
  v20 = SrvDereferenceSecret(v13);
  if ( v20 < 0 && v11 >= 0 )
    v11 = v20;
  return NormalizeNteStatus((unsigned int)v11);
}

```

## disassembly

```asm
0x18000e3f0  push    rbx
0x18000e3f2  push    rbp
0x18000e3f3  push    rsi
0x18000e3f4  push    rdi
0x18000e3f5  push    r14
0x18000e3f7  sub     rsp, 50h
0x18000e3fb  mov     r14, r9
0x18000e3fe  mov     rax, r8
0x18000e401  test    rcx, rcx
0x18000e404  jnz     short loc_18000E42E
0x18000e406  mov     r9d, 0B7Ch
0x18000e40c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e413  mov     ecx, 80090026h
0x18000e418  lea     rdx, aStatus; "Status"
0x18000e41f  mov     ebx, 80090026h
0x18000e424  call    DebugTraceError
0x18000e429  jmp     loc_18000E541
0x18000e42e  xor     r8d, r8d
0x18000e431  mov     rdx, rax
0x18000e434  call    SrvLookupAndReferenceSecret
0x18000e439  mov     rsi, rax
0x18000e43c  test    rax, rax
0x18000e43f  jnz     short loc_18000E449
0x18000e441  mov     r9d, 0B85h
0x18000e447  jmp     short loc_18000E40C
0x18000e449  mov     rbx, [rsp+78h+arg_38]
0x18000e451  test    rbx, rbx
0x18000e454  jnz     short loc_18000E47E
0x18000e456  mov     ebx, 80090027h
0x18000e45b  mov     r9d, 0B8Eh
0x18000e461  mov     ecx, 80090027h
0x18000e466  lea     rdx, aStatus; "Status"
0x18000e46d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e474  call    DebugTraceError
0x18000e479  jmp     loc_18000E530
0x18000e47e  mov     rcx, [rsp+78h+arg_20]
0x18000e486  xor     edi, edi
0x18000e488  mov     rbp, [rax+20h]
0x18000e48c  test    rcx, rcx
0x18000e48f  jz      short loc_18000E4B0
0x18000e491  call    _MapRPCToBufferDesc
0x18000e496  mov     rdi, rax
0x18000e499  test    rax, rax
0x18000e49c  jnz     short loc_18000E4B0
0x18000e49e  mov     ebx, 8009000Eh
0x18000e4a3  mov     r9d, 0B99h
0x18000e4a9  mov     ecx, 8009000Eh
0x18000e4ae  jmp     short loc_18000E466
0x18000e4b0  mov     eax, [rsp+78h+arg_40]
0x18000e4b7  mov     r9, rdi
0x18000e4ba  mov     rdx, [rsi+28h]
0x18000e4be  mov     r8, r14
0x18000e4c1  mov     rcx, [rbp+128h]
0x18000e4c8  mov     [rsp+78h+var_40], eax
0x18000e4cc  mov     eax, [rsp+78h+arg_30]
0x18000e4d3  mov     [rsp+78h+var_48], rbx
0x18000e4d8  mov     [rsp+78h+var_50], eax
0x18000e4dc  mov     rax, [rsp+78h+arg_28]
0x18000e4e4  mov     [rsp+78h+var_58], rax
0x18000e4e9  mov     rax, [rbp+0F0h]
0x18000e4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4f5  mov     ebx, eax
0x18000e4f7  test    eax, eax
0x18000e4f9  jz      short loc_18000E521
0x18000e4fb  mov     r9d, 0BAEh
0x18000e501  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e508  lea     rdx, aStatus; "Status"
0x18000e50f  mov     ecx, eax
0x18000e511  call    DebugTraceError
0x18000e516  mov     ecx, ebx
0x18000e518  call    NormalizeNteStatus
0x18000e51d  mov     ebx, eax
0x18000e51f  jmp     short loc_18000E523
0x18000e521  xor     ebx, ebx
0x18000e523  test    rdi, rdi
0x18000e526  jz      short loc_18000E530
0x18000e528  mov     rcx, rdi
0x18000e52b  call    _FreeBufferDesc
0x18000e530  mov     rcx, rsi
0x18000e533  call    SrvDereferenceSecret
0x18000e538  test    eax, eax
0x18000e53a  jns     short loc_18000E541
0x18000e53c  test    ebx, ebx
0x18000e53e  cmovns  ebx, eax
0x18000e541  mov     ecx, ebx
0x18000e543  add     rsp, 50h
0x18000e547  pop     r14
0x18000e549  pop     rdi
0x18000e54a  pop     rsi
0x18000e54b  pop     rbp
0x18000e54c  pop     rbx
0x18000e54d  jmp     NormalizeNteStatus
```
