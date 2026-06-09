# SrvCryptEncapsulate

- ea: `0x18000e560`
- end: `0x18000e68b`
- name: `SrvCryptEncapsulate`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x18000e560`
- `0x180019010`

## string_xrefs

- `0x18000e628`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e66d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptEncapsulate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10)
{
  __int64 v11; // r9
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  unsigned int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax

  if ( !a6 || !a9 )
  {
    v12 = -2146893785;
    v11 = 4241;
    v13 = 2148073511LL;
    goto LABEL_16;
  }
  if ( !a1 )
  {
    v11 = 4250;
LABEL_5:
    v12 = -2146893786;
    v13 = 2148073510LL;
LABEL_16:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v11);
    return (unsigned int)v12;
  }
  v14 = SrvLookupAndReferenceKey(a1, a3, 0);
  v15 = v14;
  if ( !v14 )
  {
    v11 = 4259;
    goto LABEL_5;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64, int, __int64, int))(*(_QWORD *)(v14 + 32) + 280LL))(
          *(_QWORD *)(*(_QWORD *)(v14 + 32) + 296LL),
          *(_QWORD *)(v14 + 40),
          a4,
          a5,
          a6,
          a7,
          a8,
          a9,
          a10);
  v17 = v16;
  if ( v16 )
  {
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 4281);
    v12 = NormalizeNteStatus(v17);
  }
  else
  {
    v12 = 0;
  }
  v18 = SrvDereferenceKey(v15);
  if ( v18 < 0 && v12 >= 0 )
    return (unsigned int)v18;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e560  push    rbx
0x18000e562  push    rbp
0x18000e563  push    rsi
0x18000e564  push    rdi
0x18000e565  sub     rsp, 58h
0x18000e569  mov     rsi, [rsp+78h+arg_28]
0x18000e571  mov     rbp, r9
0x18000e574  mov     rax, r8
0x18000e577  test    rsi, rsi
0x18000e57a  jz      loc_18000E65D
0x18000e580  mov     rbx, [rsp+78h+arg_40]
0x18000e588  test    rbx, rbx
0x18000e58b  jz      loc_18000E65D
0x18000e591  test    rcx, rcx
0x18000e594  jnz     short loc_18000E5AB
0x18000e596  mov     r9d, 109Ah
0x18000e59c  mov     ebx, 80090026h
0x18000e5a1  mov     ecx, 80090026h
0x18000e5a6  jmp     loc_18000E66D
0x18000e5ab  xor     r8d, r8d
0x18000e5ae  mov     rdx, rax
0x18000e5b1  call    SrvLookupAndReferenceKey
0x18000e5b6  mov     rdi, rax
0x18000e5b9  test    rax, rax
0x18000e5bc  jnz     short loc_18000E5C6
0x18000e5be  mov     r9d, 10A3h
0x18000e5c4  jmp     short loc_18000E59C
0x18000e5c6  mov     rcx, [rax+20h]
0x18000e5ca  mov     r8, rbp
0x18000e5cd  mov     eax, [rsp+78h+arg_48]
0x18000e5d4  mov     r9d, [rsp+78h+arg_20]
0x18000e5dc  mov     rdx, [rdi+28h]
0x18000e5e0  mov     r10, [rcx+118h]
0x18000e5e7  mov     rcx, [rcx+128h]
0x18000e5ee  mov     [rsp+78h+var_38], eax
0x18000e5f2  mov     eax, [rsp+78h+arg_38]
0x18000e5f9  mov     [rsp+78h+var_40], rbx
0x18000e5fe  mov     [rsp+78h+var_48], eax
0x18000e602  mov     rax, [rsp+78h+arg_30]
0x18000e60a  mov     [rsp+78h+var_50], rax
0x18000e60f  mov     rax, r10
0x18000e612  mov     [rsp+78h+var_58], rsi
0x18000e617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61c  mov     ebx, eax
0x18000e61e  test    eax, eax
0x18000e620  jz      short loc_18000E648
0x18000e622  mov     r9d, 10B9h
0x18000e628  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e62f  lea     rdx, aStatus; "Status"
0x18000e636  mov     ecx, eax
0x18000e638  call    DebugTraceError
0x18000e63d  mov     ecx, ebx
0x18000e63f  call    NormalizeNteStatus
0x18000e644  mov     ebx, eax
0x18000e646  jmp     short loc_18000E64A
0x18000e648  xor     ebx, ebx
0x18000e64a  mov     rcx, rdi
0x18000e64d  call    SrvDereferenceKey
0x18000e652  test    eax, eax
0x18000e654  jns     short loc_18000E680
0x18000e656  test    ebx, ebx
0x18000e658  cmovns  ebx, eax
0x18000e65b  jmp     short loc_18000E680
0x18000e65d  mov     ebx, 80090027h
0x18000e662  mov     r9d, 1091h
0x18000e668  mov     ecx, 80090027h
0x18000e66d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e674  lea     rdx, aStatus; "Status"
0x18000e67b  call    DebugTraceError
0x18000e680  mov     eax, ebx
0x18000e682  add     rsp, 58h
0x18000e686  pop     rdi
0x18000e687  pop     rsi
0x18000e688  pop     rbp
0x18000e689  pop     rbx
0x18000e68a  retn
```
