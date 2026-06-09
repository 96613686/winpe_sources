# SrvCryptVerifyClaim

- ea: `0x18000f250`
- end: `0x18000f48f`
- name: `SrvCryptVerifyClaim`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1800026e4`
- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x180006010`
- `0x18000f250`
- `0x18000f78c`
- `0x180019010`

## string_xrefs

- `0x18000f27a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f2eb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f399`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f3d5`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptVerifyClaim(
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
  __int64 v10; // r14
  __int64 v13; // r9
  int v14; // ebx
  __int64 v15; // rbp
  __int64 v16; // rdi
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rsi
  __int64 v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // edx
  unsigned int v26; // edi
  __int64 v27; // rcx
  _OWORD v29[3]; // [rsp+50h] [rbp-38h] BYREF

  v10 = 0;
  v29[0] = 0;
  if ( !a1 )
  {
    v13 = 4090;
LABEL_3:
    v14 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v13);
    goto LABEL_30;
  }
  v15 = SrvLookupAndReferenceKey(a1, a3, 0);
  if ( !v15 )
  {
    v13 = 4099;
    goto LABEL_3;
  }
  v16 = 0;
  if ( !a4 || (v16 = SrvLookupAndReferenceKey(a1, a4, 0)) != 0 )
  {
    v19 = 0;
    v10 = *(_QWORD *)(v15 + 32);
    if ( !a6 || (v19 = MapRPCToBufferDesc(a6)) != 0 )
    {
      if ( v16 )
        v20 = *(_QWORD *)(v16 + 40);
      else
        v20 = 0;
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64, int, _OWORD *, int))(v10 + 272))(
              *(_QWORD *)(v10 + 296),
              *(_QWORD *)(v15 + 40),
              v20,
              a5,
              v19,
              a7,
              a8,
              v29,
              a10);
      v22 = v21;
      if ( v21 )
      {
        DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 4145);
        v14 = NormalizeNteStatus(v22);
      }
      else if ( (unsigned int)MapBufferDescToRPC(v29, a9) )
      {
        v14 = 0;
      }
      else
      {
        v14 = -2146893810;
        DebugTraceError(
          2148073486LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          4153);
      }
      if ( v19 )
        FreeBufferDesc(v19);
      goto LABEL_23;
    }
    v14 = -2146893810;
    v17 = 4123;
    v18 = 2148073486LL;
  }
  else
  {
    v14 = -2146893786;
    v17 = 4110;
    v18 = 2148073510LL;
  }
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v17);
LABEL_23:
  v23 = SrvDereferenceKey(v15);
  if ( v23 < 0 && v14 >= 0 )
    v14 = v23;
  if ( v16 )
  {
    v24 = SrvDereferenceKey(v16);
    if ( v24 < 0 && v14 >= 0 )
      v14 = v24;
  }
LABEL_30:
  v25 = DWORD1(v29[0]);
  if ( DWORD1(v29[0]) )
  {
    v26 = 0;
    v27 = *((_QWORD *)&v29[0] + 1);
    do
    {
      if ( *(_QWORD *)(v27 + 16LL * v26 + 8) )
      {
        (*(void (__fastcall **)(_QWORD))(v10 + 136))(*(_QWORD *)(v27 + 16LL * v26 + 8));
        v27 = *((_QWORD *)&v29[0] + 1);
        v25 = DWORD1(v29[0]);
      }
      ++v26;
    }
    while ( v26 < v25 );
  }
  else
  {
    v27 = *((_QWORD *)&v29[0] + 1);
  }
  if ( v27 )
    (*(void (**)(void))(v10 + 136))();
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000f250  push    rbx
0x18000f252  push    rbp
0x18000f253  push    rsi
0x18000f254  push    rdi
0x18000f255  push    r14
0x18000f257  sub     rsp, 60h
0x18000f25b  xor     r14d, r14d
0x18000f25e  xorps   xmm0, xmm0
0x18000f261  mov     rsi, r9
0x18000f264  mov     rax, r8
0x18000f267  mov     rbx, rcx
0x18000f26a  movups  [rsp+88h+var_38], xmm0
0x18000f26f  test    rcx, rcx
0x18000f272  jnz     short loc_18000F29C
0x18000f274  mov     r9d, 0FFAh
0x18000f27a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f281  mov     ecx, 80090026h
0x18000f286  lea     rdx, aStatus; "Status"
0x18000f28d  mov     ebx, 80090026h
0x18000f292  call    DebugTraceError
0x18000f297  jmp     loc_18000F42A
0x18000f29c  xor     r8d, r8d
0x18000f29f  mov     rdx, rax
0x18000f2a2  call    SrvLookupAndReferenceKey
0x18000f2a7  mov     rbp, rax
0x18000f2aa  test    rax, rax
0x18000f2ad  jnz     short loc_18000F2B7
0x18000f2af  mov     r9d, 1003h
0x18000f2b5  jmp     short loc_18000F27A
0x18000f2b7  xor     edi, edi
0x18000f2b9  test    rsi, rsi
0x18000f2bc  jz      short loc_18000F2FC
0x18000f2be  xor     r8d, r8d
0x18000f2c1  mov     rdx, rsi
0x18000f2c4  mov     rcx, rbx
0x18000f2c7  call    SrvLookupAndReferenceKey
0x18000f2cc  mov     rdi, rax
0x18000f2cf  test    rax, rax
0x18000f2d2  jnz     short loc_18000F2FC
0x18000f2d4  mov     ebx, 80090026h
0x18000f2d9  mov     r9d, 100Eh
0x18000f2df  mov     ecx, 80090026h
0x18000f2e4  lea     rdx, aStatus; "Status"
0x18000f2eb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f2f2  call    DebugTraceError
0x18000f2f7  jmp     loc_18000F403
0x18000f2fc  mov     rcx, [rsp+88h+arg_28]
0x18000f304  xor     esi, esi
0x18000f306  mov     r14, [rbp+20h]
0x18000f30a  test    rcx, rcx
0x18000f30d  jz      short loc_18000F32E
0x18000f30f  call    _MapRPCToBufferDesc
0x18000f314  mov     rsi, rax
0x18000f317  test    rax, rax
0x18000f31a  jnz     short loc_18000F32E
0x18000f31c  mov     ebx, 8009000Eh
0x18000f321  mov     r9d, 101Bh
0x18000f327  mov     ecx, 8009000Eh
0x18000f32c  jmp     short loc_18000F2E4
0x18000f32e  test    rdi, rdi
0x18000f331  jz      short loc_18000F339
0x18000f333  mov     r8, [rdi+28h]
0x18000f337  jmp     short loc_18000F33C
0x18000f339  xor     r8d, r8d
0x18000f33c  mov     eax, [rsp+88h+arg_48]
0x18000f343  mov     r9d, [rsp+88h+arg_20]
0x18000f34b  mov     rdx, [rbp+28h]
0x18000f34f  mov     rcx, [r14+128h]
0x18000f356  mov     [rsp+88h+var_48], eax
0x18000f35a  lea     rax, [rsp+88h+var_38]
0x18000f35f  mov     [rsp+88h+var_50], rax
0x18000f364  mov     eax, [rsp+88h+arg_38]
0x18000f36b  mov     [rsp+88h+var_58], eax
0x18000f36f  mov     rax, [rsp+88h+arg_30]
0x18000f377  mov     [rsp+88h+var_60], rax
0x18000f37c  mov     rax, [r14+110h]
0x18000f383  mov     [rsp+88h+var_68], rsi
0x18000f388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f38d  mov     ebx, eax
0x18000f38f  test    eax, eax
0x18000f391  jz      short loc_18000F3B9
0x18000f393  mov     r9d, 1031h
0x18000f399  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f3a0  lea     rdx, aStatus; "Status"
0x18000f3a7  mov     ecx, eax
0x18000f3a9  call    DebugTraceError
0x18000f3ae  mov     ecx, ebx
0x18000f3b0  call    NormalizeNteStatus
0x18000f3b5  mov     ebx, eax
0x18000f3b7  jmp     short loc_18000F3F6
0x18000f3b9  mov     rdx, [rsp+88h+arg_40]
0x18000f3c1  lea     rcx, [rsp+88h+var_38]
0x18000f3c6  call    _MapBufferDescToRPC
0x18000f3cb  test    eax, eax
0x18000f3cd  jnz     short loc_18000F3F4
0x18000f3cf  mov     r9d, 1039h
0x18000f3d5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f3dc  lea     rdx, aStatus; "Status"
0x18000f3e3  mov     ecx, 8009000Eh
0x18000f3e8  mov     ebx, 8009000Eh
0x18000f3ed  call    DebugTraceError
0x18000f3f2  jmp     short loc_18000F3F6
0x18000f3f4  xor     ebx, ebx
0x18000f3f6  test    rsi, rsi
0x18000f3f9  jz      short loc_18000F403
0x18000f3fb  mov     rcx, rsi
0x18000f3fe  call    _FreeBufferDesc
0x18000f403  mov     rcx, rbp
0x18000f406  call    SrvDereferenceKey
0x18000f40b  test    eax, eax
0x18000f40d  jns     short loc_18000F414
0x18000f40f  test    ebx, ebx
0x18000f411  cmovns  ebx, eax
0x18000f414  test    rdi, rdi
0x18000f417  jz      short loc_18000F42A
0x18000f419  mov     rcx, rdi
0x18000f41c  call    SrvDereferenceKey
0x18000f421  test    eax, eax
0x18000f423  jns     short loc_18000F42A
0x18000f425  test    ebx, ebx
0x18000f427  cmovns  ebx, eax
0x18000f42a  mov     edx, dword ptr [rsp+88h+var_38+4]
0x18000f42e  test    edx, edx
0x18000f430  jz      short loc_18000F46C
0x18000f432  xor     edi, edi
0x18000f434  test    edx, edx
0x18000f436  jz      short loc_18000F46C
0x18000f438  mov     rcx, qword ptr [rsp+88h+var_38+8]
0x18000f43d  mov     eax, edi
0x18000f43f  add     rax, rax
0x18000f442  mov     r8, [rcx+rax*8+8]
0x18000f447  test    r8, r8
0x18000f44a  jz      short loc_18000F464
0x18000f44c  mov     rax, [r14+88h]
0x18000f453  mov     rcx, r8
0x18000f456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f45b  mov     rcx, qword ptr [rsp+88h+var_38+8]
0x18000f460  mov     edx, dword ptr [rsp+88h+var_38+4]
0x18000f464  inc     edi
0x18000f466  cmp     edi, edx
0x18000f468  jb      short loc_18000F43D
0x18000f46a  jmp     short loc_18000F471
0x18000f46c  mov     rcx, qword ptr [rsp+88h+var_38+8]
0x18000f471  test    rcx, rcx
0x18000f474  jz      short loc_18000F482
0x18000f476  mov     rax, [r14+88h]
0x18000f47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f482  mov     eax, ebx
0x18000f484  add     rsp, 60h
0x18000f488  pop     r14
0x18000f48a  pop     rdi
0x18000f48b  pop     rsi
0x18000f48c  pop     rbp
0x18000f48d  pop     rbx
0x18000f48e  retn
```
