# SrvCryptOpenKey

- ea: `0x180009f20`
- end: `0x18000a0a0`
- name: `SrvCryptOpenKey`
- size: `384`
- prototype: ``
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
- `0x180009f20`
- `0x18000a638`
- `0x180019010`

## string_xrefs

- `0x180009f3f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180009f95`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000a014`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptOpenKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5, int a6)
{
  __int64 v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // rdi
  unsigned int v16; // eax
  int v17; // eax
  bool v18; // zf

  if ( !a1 )
  {
    v9 = 2224;
LABEL_3:
    v10 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v9);
    return (unsigned int)NormalizeNteStatus(v10);
  }
  v11 = SrvLookupAndReferenceProvider(a1, a2, 0);
  if ( !v11 )
  {
    v9 = 2233;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v10 = -2146893785;
    v12 = 2240;
    v13 = 2148073511LL;
LABEL_8:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v12);
    goto LABEL_15;
  }
  v14 = MSCryptAlloc(56);
  v15 = (_QWORD *)v14;
  if ( !v14 )
  {
    v10 = -2146893810;
    v12 = 2253;
    v13 = 2148073486LL;
    goto LABEL_8;
  }
  *(_OWORD *)v14 = 0;
  *(_OWORD *)(v14 + 16) = 0;
  *(_OWORD *)(v14 + 32) = 0;
  *(_QWORD *)(v14 + 48) = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, int))(v11 + 56))(
          *(_QWORD *)(v11 + 296),
          v14 + 40,
          a4,
          a5,
          a6);
  v10 = v16;
  if ( !v16 )
  {
    *v15 = 1145324615;
    v15[1] = 1;
    v15[4] = v11;
    SrvAddKeyToList(a1, v15, a3);
    return 0;
  }
  DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2273);
  if ( v15[5] )
    (*(void (__fastcall **)(_QWORD))(v11 + 128))(*(_QWORD *)(v11 + 296));
  SrvCryptLocalFree(v15);
LABEL_15:
  v17 = SrvDereferenceProvider(v11);
  if ( v17 >= 0 )
  {
    v18 = v10 == 0;
  }
  else
  {
    v18 = v10 == 0;
    if ( (v10 & 0x80000000) == 0 )
    {
      v10 = v17;
      return (unsigned int)NormalizeNteStatus(v10);
    }
  }
  if ( !v18 )
    return (unsigned int)NormalizeNteStatus(v10);
  return v10;
}

```

## disassembly

```asm
0x180009f20  push    rbx
0x180009f22  push    rbp
0x180009f23  push    rsi
0x180009f24  push    rdi
0x180009f25  push    r14
0x180009f27  sub     rsp, 30h
0x180009f2b  mov     rbx, r9
0x180009f2e  mov     r14, r8
0x180009f31  mov     rbp, rcx
0x180009f34  test    rcx, rcx
0x180009f37  jnz     short loc_180009F61
0x180009f39  mov     r9d, 8B0h
0x180009f3f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009f46  mov     ecx, 80090026h
0x180009f4b  lea     rdx, aStatus; "Status"
0x180009f52  mov     ebx, 80090026h
0x180009f57  call    DebugTraceError
0x180009f5c  jmp     loc_18000A065
0x180009f61  xor     r8d, r8d
0x180009f64  call    SrvLookupAndReferenceProvider
0x180009f69  mov     rsi, rax
0x180009f6c  test    rax, rax
0x180009f6f  jnz     short loc_180009F79
0x180009f71  mov     r9d, 8B9h
0x180009f77  jmp     short loc_180009F3F
0x180009f79  test    r14, r14
0x180009f7c  jnz     short loc_180009FA6
0x180009f7e  mov     ebx, 80090027h
0x180009f83  mov     r9d, 8C0h
0x180009f89  mov     ecx, 80090027h
0x180009f8e  lea     rdx, aStatus; "Status"
0x180009f95  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009f9c  call    DebugTraceError
0x180009fa1  jmp     loc_18000A04D
0x180009fa6  mov     ecx, 38h ; '8'
0x180009fab  call    MSCryptAlloc
0x180009fb0  mov     rdi, rax
0x180009fb3  test    rax, rax
0x180009fb6  jnz     short loc_180009FCA
0x180009fb8  mov     ebx, 8009000Eh
0x180009fbd  mov     r9d, 8CDh
0x180009fc3  mov     ecx, 8009000Eh
0x180009fc8  jmp     short loc_180009F8E
0x180009fca  mov     ecx, [rsp+58h+arg_28]
0x180009fd1  lea     rdx, [rdi+28h]
0x180009fd5  mov     r9d, [rsp+58h+arg_20]
0x180009fdd  xorps   xmm0, xmm0
0x180009fe0  movups  xmmword ptr [rdi], xmm0
0x180009fe3  xor     eax, eax
0x180009fe5  mov     [rsp+58h+var_38], ecx
0x180009fe9  movups  xmmword ptr [rdi+10h], xmm0
0x180009fed  mov     r8, rbx
0x180009ff0  movups  xmmword ptr [rdi+20h], xmm0
0x180009ff4  mov     [rdi+30h], rax
0x180009ff8  mov     rcx, [rsi+128h]
0x180009fff  mov     rax, [rsi+38h]
0x18000a003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a008  mov     ebx, eax
0x18000a00a  test    eax, eax
0x18000a00c  jz      short loc_18000A070
0x18000a00e  mov     r9d, 8E1h
0x18000a014  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a01b  lea     rdx, aStatus; "Status"
0x18000a022  mov     ecx, eax
0x18000a024  call    DebugTraceError
0x18000a029  mov     rdx, [rdi+28h]
0x18000a02d  test    rdx, rdx
0x18000a030  jz      short loc_18000A045
0x18000a032  mov     rcx, [rsi+128h]
0x18000a039  mov     rax, [rsi+80h]
0x18000a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a045  mov     rcx, rdi; P
0x18000a048  call    SrvCryptLocalFree
0x18000a04d  mov     rcx, rsi
0x18000a050  call    SrvDereferenceProvider
0x18000a055  test    eax, eax
0x18000a057  jns     short loc_18000A061
0x18000a059  test    ebx, ebx
0x18000a05b  js      short loc_18000A063
0x18000a05d  mov     ebx, eax
0x18000a05f  jmp     short loc_18000A065
0x18000a061  test    ebx, ebx
0x18000a063  jz      short loc_18000A093
0x18000a065  mov     ecx, ebx
0x18000a067  call    NormalizeNteStatus
0x18000a06c  mov     ebx, eax
0x18000a06e  jmp     short loc_18000A093
0x18000a070  mov     r8, r14
0x18000a073  mov     qword ptr [rdi], 44444447h
0x18000a07a  mov     rdx, rdi
0x18000a07d  mov     qword ptr [rdi+8], 1
0x18000a085  mov     rcx, rbp
0x18000a088  mov     [rdi+20h], rsi
0x18000a08c  call    SrvAddKeyToList
0x18000a091  xor     ebx, ebx
0x18000a093  mov     eax, ebx
0x18000a095  add     rsp, 30h
0x18000a099  pop     r14
0x18000a09b  pop     rdi
0x18000a09c  pop     rsi
0x18000a09d  pop     rbp
0x18000a09e  pop     rbx
0x18000a09f  retn
```
