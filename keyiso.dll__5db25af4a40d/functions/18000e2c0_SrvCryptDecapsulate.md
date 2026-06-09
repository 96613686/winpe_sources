# SrvCryptDecapsulate

- ea: `0x18000e2c0`
- end: `0x18000e3de`
- name: `SrvCryptDecapsulate`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x18000e2c0`
- `0x180019010`

## string_xrefs

- `0x18000e2f9`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e399`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptDecapsulate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax

  if ( !a8 )
  {
    v10 = -2146893785;
    v11 = 4335;
    v12 = 2148073511LL;
LABEL_3:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v11);
    return (unsigned int)v10;
  }
  if ( !a1 )
  {
    v11 = 4344;
LABEL_6:
    v10 = -2146893786;
    v12 = 2148073510LL;
    goto LABEL_3;
  }
  v13 = SrvLookupAndReferenceKey(a1, a3, 0);
  v14 = v13;
  if ( !v13 )
  {
    v11 = 4353;
    goto LABEL_6;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, int, __int64, int))(*(_QWORD *)(v13 + 32)
                                                                                               + 288LL))(
          *(_QWORD *)(*(_QWORD *)(v13 + 32) + 296LL),
          *(_QWORD *)(v13 + 40),
          a4,
          a5,
          a6,
          a7,
          a8,
          a9);
  v16 = v15;
  if ( v15 )
  {
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 4374);
    v10 = NormalizeNteStatus(v16);
  }
  else
  {
    v10 = 0;
  }
  v17 = SrvDereferenceKey(v14);
  if ( v17 < 0 && v10 >= 0 )
    return (unsigned int)v17;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000e2c0  mov     [rsp+arg_0], rbx
0x18000e2c5  mov     [rsp+arg_8], rsi
0x18000e2ca  push    rdi
0x18000e2cb  sub     rsp, 50h
0x18000e2cf  mov     rbx, [rsp+58h+arg_38]
0x18000e2d7  mov     rsi, r9
0x18000e2da  mov     rax, r8
0x18000e2dd  test    rbx, rbx
0x18000e2e0  jnz     short loc_18000E30A
0x18000e2e2  mov     ebx, 80090027h
0x18000e2e7  mov     r9d, 10EFh
0x18000e2ed  mov     ecx, 80090027h
0x18000e2f2  lea     rdx, aStatus; "Status"
0x18000e2f9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e300  call    DebugTraceError
0x18000e305  jmp     loc_18000E3CC
0x18000e30a  test    rcx, rcx
0x18000e30d  jnz     short loc_18000E321
0x18000e30f  mov     r9d, 10F8h
0x18000e315  mov     ebx, 80090026h
0x18000e31a  mov     ecx, 80090026h
0x18000e31f  jmp     short loc_18000E2F2
0x18000e321  xor     r8d, r8d
0x18000e324  mov     rdx, rax
0x18000e327  call    SrvLookupAndReferenceKey
0x18000e32c  mov     rdi, rax
0x18000e32f  test    rax, rax
0x18000e332  jnz     short loc_18000E33C
0x18000e334  mov     r9d, 1101h
0x18000e33a  jmp     short loc_18000E315
0x18000e33c  mov     rcx, [rax+20h]
0x18000e340  mov     r8, rsi
0x18000e343  mov     eax, [rsp+58h+arg_40]
0x18000e34a  mov     r9d, [rsp+58h+arg_20]
0x18000e352  mov     rdx, [rdi+28h]
0x18000e356  mov     r10, [rcx+120h]
0x18000e35d  mov     rcx, [rcx+128h]
0x18000e364  mov     [rsp+58h+var_20], eax
0x18000e368  mov     eax, [rsp+58h+arg_30]
0x18000e36f  mov     [rsp+58h+var_28], rbx
0x18000e374  mov     [rsp+58h+var_30], eax
0x18000e378  mov     rax, [rsp+58h+arg_28]
0x18000e380  mov     [rsp+58h+var_38], rax
0x18000e385  mov     rax, r10
0x18000e388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e38d  mov     ebx, eax
0x18000e38f  test    eax, eax
0x18000e391  jz      short loc_18000E3B9
0x18000e393  mov     r9d, 1116h
0x18000e399  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e3a0  lea     rdx, aStatus; "Status"
0x18000e3a7  mov     ecx, eax
0x18000e3a9  call    DebugTraceError
0x18000e3ae  mov     ecx, ebx
0x18000e3b0  call    NormalizeNteStatus
0x18000e3b5  mov     ebx, eax
0x18000e3b7  jmp     short loc_18000E3BB
0x18000e3b9  xor     ebx, ebx
0x18000e3bb  mov     rcx, rdi
0x18000e3be  call    SrvDereferenceKey
0x18000e3c3  test    eax, eax
0x18000e3c5  jns     short loc_18000E3CC
0x18000e3c7  test    ebx, ebx
0x18000e3c9  cmovns  ebx, eax
0x18000e3cc  mov     rsi, [rsp+58h+arg_8]
0x18000e3d1  mov     eax, ebx
0x18000e3d3  mov     rbx, [rsp+58h+arg_0]
0x18000e3d8  add     rsp, 50h
0x18000e3dc  pop     rdi
0x18000e3dd  retn
```
