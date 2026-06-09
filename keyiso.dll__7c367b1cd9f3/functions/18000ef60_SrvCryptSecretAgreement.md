# SrvCryptSecretAgreement

- ea: `0x18000ef60`
- end: `0x18000f131`
- name: `SrvCryptSecretAgreement`
- size: `465`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180002d20`
- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x180006e60`
- `0x18000a484`
- `0x18000ef60`
- `0x180019010`

## string_xrefs

- `0x18000ef81`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000efdc`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f01f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f0a3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptSecretAgreement(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // rsi
  _QWORD *v11; // rdi
  __int64 v12; // r15
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rbp
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // r12d
  int v19; // eax
  int v20; // eax

  if ( !a1 )
  {
    v8 = 2790;
LABEL_3:
    v9 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v8);
    return (unsigned int)v9;
  }
  v10 = SrvLookupAndReferenceKey(a1, a3, 0);
  if ( !v10 )
  {
    v8 = 2799;
    goto LABEL_3;
  }
  v11 = 0;
  v12 = SrvLookupAndReferenceKey(a1, a4, 0);
  if ( v12 )
  {
    if ( a5 )
    {
      v15 = *(_QWORD *)(v10 + 32);
      v16 = MSCryptAlloc(56);
      v11 = (_QWORD *)v16;
      if ( v16 )
      {
        *(_OWORD *)v16 = 0;
        *(_OWORD *)(v16 + 16) = 0;
        *(_OWORD *)(v16 + 32) = 0;
        *(_QWORD *)(v16 + 48) = 0;
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(v15 + 232))(
                *(_QWORD *)(v15 + 296),
                *(_QWORD *)(v10 + 40),
                *(_QWORD *)(v12 + 40),
                v16 + 40,
                a6);
        v18 = v17;
        if ( v17 )
        {
          DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2848);
          v9 = NormalizeNteStatus(v18);
        }
        else
        {
          *v11 = 1145324617;
          v11[1] = 1;
          _InterlockedIncrement64((volatile signed __int64 *)(v15 + 8));
          v11[4] = v15;
          SrvAddSecretToList(a1, v11, a5);
          v11 = 0;
          v9 = 0;
        }
LABEL_16:
        v19 = SrvDereferenceKey(v12);
        if ( v19 < 0 && v9 >= 0 )
          v9 = v19;
        goto LABEL_19;
      }
      v9 = -2146893810;
      v13 = 2829;
      v14 = 2148073486LL;
    }
    else
    {
      v9 = -2146893785;
      v13 = 2816;
      v14 = 2148073511LL;
    }
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v13);
    goto LABEL_16;
  }
  v9 = -2146893786;
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2808);
LABEL_19:
  v20 = SrvDereferenceKey(v10);
  if ( v20 < 0 && v9 >= 0 )
    v9 = v20;
  if ( v11 )
    SrvCryptLocalFree(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ef60  push    rbx
0x18000ef62  push    rbp
0x18000ef63  push    rsi
0x18000ef64  push    rdi
0x18000ef65  push    r12
0x18000ef67  push    r15
0x18000ef69  sub     rsp, 38h
0x18000ef6d  mov     rbp, r9
0x18000ef70  mov     rax, r8
0x18000ef73  mov     rbx, rcx
0x18000ef76  test    rcx, rcx
0x18000ef79  jnz     short loc_18000EFA3
0x18000ef7b  mov     r9d, 0AE6h
0x18000ef81  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ef88  mov     ecx, 80090026h
0x18000ef8d  lea     rdx, aStatus; "Status"
0x18000ef94  mov     ebx, 80090026h
0x18000ef99  call    DebugTraceError
0x18000ef9e  jmp     loc_18000F122
0x18000efa3  xor     r8d, r8d
0x18000efa6  mov     rdx, rax
0x18000efa9  call    SrvLookupAndReferenceKey
0x18000efae  mov     rsi, rax
0x18000efb1  test    rax, rax
0x18000efb4  jnz     short loc_18000EFBE
0x18000efb6  mov     r9d, 0AEFh
0x18000efbc  jmp     short loc_18000EF81
0x18000efbe  xor     r8d, r8d
0x18000efc1  mov     rdx, rbp
0x18000efc4  mov     rcx, rbx
0x18000efc7  xor     edi, edi
0x18000efc9  call    SrvLookupAndReferenceKey
0x18000efce  mov     r15, rax
0x18000efd1  test    rax, rax
0x18000efd4  jnz     short loc_18000EFFE
0x18000efd6  mov     r9d, 0AF8h
0x18000efdc  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000efe3  lea     rdx, aStatus; "Status"
0x18000efea  mov     ecx, 80090026h
0x18000efef  mov     ebx, 80090026h
0x18000eff4  call    DebugTraceError
0x18000eff9  jmp     loc_18000F104
0x18000effe  cmp     [rsp+68h+arg_20], rdi
0x18000f006  jnz     short loc_18000F030
0x18000f008  mov     ebx, 80090027h
0x18000f00d  mov     r9d, 0B00h
0x18000f013  mov     ecx, 80090027h
0x18000f018  lea     rdx, aStatus; "Status"
0x18000f01f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f026  call    DebugTraceError
0x18000f02b  jmp     loc_18000F0F3
0x18000f030  mov     rbp, [rsi+20h]
0x18000f034  mov     ecx, 38h ; '8'
0x18000f039  call    MSCryptAlloc
0x18000f03e  mov     rdi, rax
0x18000f041  test    rax, rax
0x18000f044  jnz     short loc_18000F058
0x18000f046  mov     ebx, 8009000Eh
0x18000f04b  mov     r9d, 0B0Dh
0x18000f051  mov     ecx, 8009000Eh
0x18000f056  jmp     short loc_18000F018
0x18000f058  xorps   xmm0, xmm0
0x18000f05b  lea     r9, [rdi+28h]
0x18000f05f  movups  xmmword ptr [rdi], xmm0
0x18000f062  xor     eax, eax
0x18000f064  movups  xmmword ptr [rdi+10h], xmm0
0x18000f068  movups  xmmword ptr [rdi+20h], xmm0
0x18000f06c  mov     [rdi+30h], rax
0x18000f070  mov     eax, [rsp+68h+arg_28]
0x18000f077  mov     r8, [r15+28h]
0x18000f07b  mov     rdx, [rsi+28h]
0x18000f07f  mov     rcx, [rbp+128h]
0x18000f086  mov     [rsp+68h+var_48], eax
0x18000f08a  mov     rax, [rbp+0E8h]
0x18000f091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f096  mov     r12d, eax
0x18000f099  test    eax, eax
0x18000f09b  jz      short loc_18000F0C4
0x18000f09d  mov     r9d, 0B20h
0x18000f0a3  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f0aa  lea     rdx, aStatus; "Status"
0x18000f0b1  mov     ecx, eax
0x18000f0b3  call    DebugTraceError
0x18000f0b8  mov     ecx, r12d
0x18000f0bb  call    NormalizeNteStatus
0x18000f0c0  mov     ebx, eax
0x18000f0c2  jmp     short loc_18000F0F3
0x18000f0c4  mov     qword ptr [rdi], 44444449h
0x18000f0cb  mov     qword ptr [rdi+8], 1
0x18000f0d3  lock inc qword ptr [rbp+8]
0x18000f0d8  mov     r8, [rsp+68h+arg_20]
0x18000f0e0  mov     rdx, rdi
0x18000f0e3  mov     rcx, rbx
0x18000f0e6  mov     [rdi+20h], rbp
0x18000f0ea  call    SrvAddSecretToList
0x18000f0ef  xor     edi, edi
0x18000f0f1  xor     ebx, ebx
0x18000f0f3  mov     rcx, r15
0x18000f0f6  call    SrvDereferenceKey
0x18000f0fb  test    eax, eax
0x18000f0fd  jns     short loc_18000F104
0x18000f0ff  test    ebx, ebx
0x18000f101  cmovns  ebx, eax
0x18000f104  mov     rcx, rsi
0x18000f107  call    SrvDereferenceKey
0x18000f10c  test    eax, eax
0x18000f10e  jns     short loc_18000F115
0x18000f110  test    ebx, ebx
0x18000f112  cmovns  ebx, eax
0x18000f115  test    rdi, rdi
0x18000f118  jz      short loc_18000F122
0x18000f11a  mov     rcx, rdi; P
0x18000f11d  call    SrvCryptLocalFree
0x18000f122  mov     eax, ebx
0x18000f124  add     rsp, 38h
0x18000f128  pop     r15
0x18000f12a  pop     r12
0x18000f12c  pop     rdi
0x18000f12d  pop     rsi
0x18000f12e  pop     rbp
0x18000f12f  pop     rbx
0x18000f130  retn
```
