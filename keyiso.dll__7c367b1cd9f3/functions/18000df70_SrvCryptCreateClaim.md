# SrvCryptCreateClaim

- ea: `0x18000df70`
- end: `0x18000e110`
- name: `SrvCryptCreateClaim`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x1800026e4`
- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x180006010`
- `0x18000df70`
- `0x180019010`

## string_xrefs

- `0x18000df8d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000dffe`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000e0af`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptCreateClaim(
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
  __int64 v12; // r9
  int v13; // ebx
  __int64 v14; // rbp
  __int64 v15; // rdi
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rsi
  __int64 v19; // rbx
  __int64 v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  int v24; // eax

  if ( !a1 )
  {
    v12 = 3961;
LABEL_3:
    v13 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v12);
    return (unsigned int)v13;
  }
  v14 = SrvLookupAndReferenceKey(a1, a3, 0);
  if ( !v14 )
  {
    v12 = 3970;
    goto LABEL_3;
  }
  v15 = 0;
  if ( !a4 || (v15 = SrvLookupAndReferenceKey(a1, a4, 0)) != 0 )
  {
    v18 = 0;
    v19 = *(_QWORD *)(v14 + 32);
    if ( !a6 || (v18 = MapRPCToBufferDesc(a6)) != 0 )
    {
      if ( v15 )
        v20 = *(_QWORD *)(v15 + 40);
      else
        v20 = 0;
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64, int, __int64, int))(v19 + 264))(
              *(_QWORD *)(v19 + 296),
              *(_QWORD *)(v14 + 40),
              v20,
              a5,
              v18,
              a7,
              a8,
              a9,
              a10);
      v22 = v21;
      if ( v21 )
      {
        DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 4016);
        v13 = NormalizeNteStatus(v22);
      }
      else
      {
        v13 = 0;
      }
      if ( v18 )
        FreeBufferDesc(v18);
      goto LABEL_21;
    }
    v13 = -2146893810;
    v16 = 3994;
    v17 = 2148073486LL;
  }
  else
  {
    v13 = -2146893786;
    v16 = 3981;
    v17 = 2148073510LL;
  }
  DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v16);
LABEL_21:
  v23 = SrvDereferenceKey(v14);
  if ( v23 < 0 && v13 >= 0 )
    v13 = v23;
  if ( v15 )
  {
    v24 = SrvDereferenceKey(v15);
    if ( v24 < 0 && v13 >= 0 )
      return (unsigned int)v24;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000df70  push    rbx
0x18000df72  push    rbp
0x18000df73  push    rsi
0x18000df74  push    rdi
0x18000df75  sub     rsp, 58h
0x18000df79  mov     rsi, r9
0x18000df7c  mov     rax, r8
0x18000df7f  mov     rbx, rcx
0x18000df82  test    rcx, rcx
0x18000df85  jnz     short loc_18000DFAF
0x18000df87  mov     r9d, 0F79h
0x18000df8d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000df94  mov     ecx, 80090026h
0x18000df99  lea     rdx, aStatus; "Status"
0x18000dfa0  mov     ebx, 80090026h
0x18000dfa5  call    DebugTraceError
0x18000dfaa  jmp     loc_18000E105
0x18000dfaf  xor     r8d, r8d
0x18000dfb2  mov     rdx, rax
0x18000dfb5  call    SrvLookupAndReferenceKey
0x18000dfba  mov     rbp, rax
0x18000dfbd  test    rax, rax
0x18000dfc0  jnz     short loc_18000DFCA
0x18000dfc2  mov     r9d, 0F82h
0x18000dfc8  jmp     short loc_18000DF8D
0x18000dfca  xor     edi, edi
0x18000dfcc  test    rsi, rsi
0x18000dfcf  jz      short loc_18000E00F
0x18000dfd1  xor     r8d, r8d
0x18000dfd4  mov     rdx, rsi
0x18000dfd7  mov     rcx, rbx
0x18000dfda  call    SrvLookupAndReferenceKey
0x18000dfdf  mov     rdi, rax
0x18000dfe2  test    rax, rax
0x18000dfe5  jnz     short loc_18000E00F
0x18000dfe7  mov     ebx, 80090026h
0x18000dfec  mov     r9d, 0F8Dh
0x18000dff2  mov     ecx, 80090026h
0x18000dff7  lea     rdx, aStatus; "Status"
0x18000dffe  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e005  call    DebugTraceError
0x18000e00a  jmp     loc_18000E0DE
0x18000e00f  mov     rcx, [rsp+78h+arg_28]
0x18000e017  xor     esi, esi
0x18000e019  mov     rbx, [rbp+20h]
0x18000e01d  test    rcx, rcx
0x18000e020  jz      short loc_18000E041
0x18000e022  call    _MapRPCToBufferDesc
0x18000e027  mov     rsi, rax
0x18000e02a  test    rax, rax
0x18000e02d  jnz     short loc_18000E041
0x18000e02f  mov     ebx, 8009000Eh
0x18000e034  mov     r9d, 0F9Ah
0x18000e03a  mov     ecx, 8009000Eh
0x18000e03f  jmp     short loc_18000DFF7
0x18000e041  test    rdi, rdi
0x18000e044  jz      short loc_18000E04C
0x18000e046  mov     r8, [rdi+28h]
0x18000e04a  jmp     short loc_18000E04F
0x18000e04c  xor     r8d, r8d
0x18000e04f  mov     eax, [rsp+78h+arg_48]
0x18000e056  mov     r9d, [rsp+78h+arg_20]
0x18000e05e  mov     rdx, [rbp+28h]
0x18000e062  mov     rcx, [rbx+128h]
0x18000e069  mov     [rsp+78h+var_38], eax
0x18000e06d  mov     rax, [rsp+78h+arg_40]
0x18000e075  mov     [rsp+78h+var_40], rax
0x18000e07a  mov     eax, [rsp+78h+arg_38]
0x18000e081  mov     [rsp+78h+var_48], eax
0x18000e085  mov     rax, [rsp+78h+arg_30]
0x18000e08d  mov     [rsp+78h+var_50], rax
0x18000e092  mov     rax, [rbx+108h]
0x18000e099  mov     [rsp+78h+var_58], rsi
0x18000e09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a3  mov     ebx, eax
0x18000e0a5  test    eax, eax
0x18000e0a7  jz      short loc_18000E0CF
0x18000e0a9  mov     r9d, 0FB0h
0x18000e0af  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e0b6  lea     rdx, aStatus; "Status"
0x18000e0bd  mov     ecx, eax
0x18000e0bf  call    DebugTraceError
0x18000e0c4  mov     ecx, ebx
0x18000e0c6  call    NormalizeNteStatus
0x18000e0cb  mov     ebx, eax
0x18000e0cd  jmp     short loc_18000E0D1
0x18000e0cf  xor     ebx, ebx
0x18000e0d1  test    rsi, rsi
0x18000e0d4  jz      short loc_18000E0DE
0x18000e0d6  mov     rcx, rsi
0x18000e0d9  call    _FreeBufferDesc
0x18000e0de  mov     rcx, rbp
0x18000e0e1  call    SrvDereferenceKey
0x18000e0e6  test    eax, eax
0x18000e0e8  jns     short loc_18000E0EF
0x18000e0ea  test    ebx, ebx
0x18000e0ec  cmovns  ebx, eax
0x18000e0ef  test    rdi, rdi
0x18000e0f2  jz      short loc_18000E105
0x18000e0f4  mov     rcx, rdi
0x18000e0f7  call    SrvDereferenceKey
0x18000e0fc  test    eax, eax
0x18000e0fe  jns     short loc_18000E105
0x18000e100  test    ebx, ebx
0x18000e102  cmovns  ebx, eax
0x18000e105  mov     eax, ebx
0x18000e107  add     rsp, 58h
0x18000e10b  pop     rdi
0x18000e10c  pop     rsi
0x18000e10d  pop     rbp
0x18000e10e  pop     rbx
0x18000e10f  retn
```
