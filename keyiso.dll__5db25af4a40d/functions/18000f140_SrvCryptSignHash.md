# SrvCryptSignHash

- ea: `0x18000f140`
- end: `0x18000f248`
- name: `SrvCryptSignHash`
- size: `264`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x18000f140`
- `0x180019010`

## string_xrefs

- `0x18000f15b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f208`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10)
{
  __int64 v11; // r9
  int v12; // ebx
  volatile signed __int64 *v13; // rax
  volatile signed __int64 *v14; // rdi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax

  if ( !a1 )
  {
    v11 = 3516;
LABEL_3:
    v12 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v11);
    return (unsigned int)v12;
  }
  v13 = SrvLookupAndReferenceKey(a1, a3, 0);
  v14 = v13;
  if ( !v13 )
  {
    v11 = 3525;
    goto LABEL_3;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, __int64, int, __int64, int))(*((_QWORD *)v13 + 4) + 200LL))(
          *(_QWORD *)(*((_QWORD *)v13 + 4) + 296LL),
          *((_QWORD *)v13 + 5),
          a4,
          a5,
          a6,
          a7,
          a8,
          a9,
          a10);
  v16 = v15;
  if ( v15 )
  {
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 3547);
    v12 = NormalizeNteStatus(v16);
  }
  else
  {
    v12 = 0;
  }
  v17 = SrvDereferenceKey(v14);
  if ( v17 < 0 && v12 >= 0 )
    return (unsigned int)v17;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000f140  mov     [rsp+arg_0], rbx
0x18000f145  push    rdi
0x18000f146  sub     rsp, 50h
0x18000f14a  mov     rbx, r9
0x18000f14d  mov     rax, r8
0x18000f150  test    rcx, rcx
0x18000f153  jnz     short loc_18000F17D
0x18000f155  mov     r9d, 0DBCh
0x18000f15b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f162  mov     ecx, 80090026h
0x18000f167  lea     rdx, aStatus; "Status"
0x18000f16e  mov     ebx, 80090026h
0x18000f173  call    DebugTraceError
0x18000f178  jmp     loc_18000F23B
0x18000f17d  xor     r8d, r8d
0x18000f180  mov     rdx, rax
0x18000f183  call    SrvLookupAndReferenceKey
0x18000f188  mov     rdi, rax
0x18000f18b  test    rax, rax
0x18000f18e  jnz     short loc_18000F198
0x18000f190  mov     r9d, 0DC5h
0x18000f196  jmp     short loc_18000F15B
0x18000f198  mov     rcx, [rax+20h]
0x18000f19c  mov     r8, rbx
0x18000f19f  mov     eax, [rsp+58h+arg_48]
0x18000f1a6  mov     r9, [rsp+58h+arg_20]
0x18000f1ae  mov     rdx, [rdi+28h]
0x18000f1b2  mov     r10, [rcx+0C8h]
0x18000f1b9  mov     rcx, [rcx+128h]
0x18000f1c0  mov     [rsp+58h+var_18], eax
0x18000f1c4  mov     rax, [rsp+58h+arg_40]
0x18000f1cc  mov     [rsp+58h+var_20], rax
0x18000f1d1  mov     eax, [rsp+58h+arg_38]
0x18000f1d8  mov     [rsp+58h+var_28], eax
0x18000f1dc  mov     rax, [rsp+58h+arg_30]
0x18000f1e4  mov     [rsp+58h+var_30], rax
0x18000f1e9  mov     eax, [rsp+58h+arg_28]
0x18000f1f0  mov     [rsp+58h+var_38], eax
0x18000f1f4  mov     rax, r10
0x18000f1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1fc  mov     ebx, eax
0x18000f1fe  test    eax, eax
0x18000f200  jz      short loc_18000F228
0x18000f202  mov     r9d, 0DDBh
0x18000f208  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f20f  lea     rdx, aStatus; "Status"
0x18000f216  mov     ecx, eax
0x18000f218  call    DebugTraceError
0x18000f21d  mov     ecx, ebx
0x18000f21f  call    NormalizeNteStatus
0x18000f224  mov     ebx, eax
0x18000f226  jmp     short loc_18000F22A
0x18000f228  xor     ebx, ebx
0x18000f22a  mov     rcx, rdi
0x18000f22d  call    SrvDereferenceKey
0x18000f232  test    eax, eax
0x18000f234  jns     short loc_18000F23B
0x18000f236  test    ebx, ebx
0x18000f238  cmovns  ebx, eax
0x18000f23b  mov     eax, ebx
0x18000f23d  mov     rbx, [rsp+58h+arg_0]
0x18000f242  add     rsp, 50h
0x18000f246  pop     rdi
0x18000f247  retn
```
