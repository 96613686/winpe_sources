# SrvCryptIsAlgSupported

- ea: `0x180002270`
- end: `0x1800023a7`
- name: `SrvCryptIsAlgSupported`
- size: `311`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180002270`
- `0x1800025b0`
- `0x180004470`
- `0x1800048f0`
- `0x180005510`
- `0x180019010`

## string_xrefs

- `0x1800022b4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002345`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptIsAlgSupported(struct _RTL_CRITICAL_SECTION *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  int v6; // ebx
  volatile signed __int64 *v8; // rax
  int v9; // edx
  int v10; // r8d
  volatile signed __int64 *v11; // rdi
  int v12; // edx
  int v13; // r8d
  int v14; // eax

  if ( a1 )
  {
    v8 = SrvLookupAndReferenceProvider(a1, a2, 0);
    v11 = v8;
    if ( v8 )
    {
      v6 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD))v8 + 20))(*((_QWORD *)v8 + 37), a3, a4);
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            (unsigned int)"Status",
            v6,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            126);
        v6 = NormalizeNteStatus(v6);
      }
      v14 = SrvDereferenceProvider(v11);
      if ( v14 < 0 && v6 >= 0 )
        return (unsigned int)v14;
    }
    else
    {
      v6 = -2146893786;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          v10,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          110);
    }
  }
  else
  {
    v6 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        101);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002270  mov     [rsp+arg_0], rbx
0x180002275  mov     [rsp+arg_8], rsi
0x18000227a  push    rdi
0x18000227b  sub     rsp, 40h
0x18000227f  mov     ebx, r9d
0x180002282  mov     rsi, r8
0x180002285  test    rcx, rcx
0x180002288  jnz     short loc_1800022E6
0x18000228a  mov     ebx, 80090026h
0x18000228f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002296  lea     rax, WPP_GLOBAL_Control
0x18000229d  cmp     rcx, rax
0x1800022a0  jz      short loc_1800022D4
0x1800022a2  test    byte ptr [rcx+1Ch], 1
0x1800022a6  jz      short loc_1800022D4
0x1800022a8  mov     [rsp+48h+var_18], 865h
0x1800022b0  mov     rcx, [rcx+10h]
0x1800022b4  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800022bb  mov     [rsp+48h+var_20], rax
0x1800022c0  lea     r9, aStatus; "Status"
0x1800022c7  mov     [rsp+48h+var_28], 80090026h
0x1800022cf  call    WPP_SF_sDsd
0x1800022d4  mov     rsi, [rsp+48h+arg_8]
0x1800022d9  mov     eax, ebx
0x1800022db  mov     rbx, [rsp+48h+arg_0]
0x1800022e0  add     rsp, 40h
0x1800022e4  pop     rdi
0x1800022e5  retn
0x1800022e6  xor     r8d, r8d
0x1800022e9  call    SrvLookupAndReferenceProvider
0x1800022ee  mov     rdi, rax
0x1800022f1  test    rax, rax
0x1800022f4  jz      short loc_180002374
0x1800022f6  mov     rcx, [rax+128h]
0x1800022fd  mov     r8d, ebx
0x180002300  mov     rax, [rax+0A0h]
0x180002307  mov     rdx, rsi
0x18000230a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000230f  mov     ebx, eax
0x180002311  test    eax, eax
0x180002313  jnz     short loc_180002328
0x180002315  mov     rcx, rdi
0x180002318  call    SrvDereferenceProvider
0x18000231d  test    eax, eax
0x18000231f  jns     short loc_1800022D4
0x180002321  test    ebx, ebx
0x180002323  cmovns  ebx, eax
0x180002326  jmp     short loc_1800022D4
0x180002328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000232f  lea     rax, WPP_GLOBAL_Control
0x180002336  cmp     rcx, rax
0x180002339  jz      short loc_180002369
0x18000233b  test    byte ptr [rcx+1Ch], 1
0x18000233f  jz      short loc_180002369
0x180002341  mov     rcx, [rcx+10h]
0x180002345  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000234c  mov     [rsp+48h+var_18], 87Eh
0x180002354  lea     r9, aStatus; "Status"
0x18000235b  mov     [rsp+48h+var_20], rax
0x180002360  mov     [rsp+48h+var_28], ebx
0x180002364  call    WPP_SF_sDsd
0x180002369  mov     ecx, ebx
0x18000236b  call    NormalizeNteStatus
0x180002370  mov     ebx, eax
0x180002372  jmp     short loc_180002315
0x180002374  mov     ebx, 80090026h
0x180002379  mov     rcx, cs:WPP_GLOBAL_Control
0x180002380  lea     rax, WPP_GLOBAL_Control
0x180002387  cmp     rcx, rax
0x18000238a  jz      loc_1800022D4
0x180002390  test    byte ptr [rcx+1Ch], 1
0x180002394  jz      loc_1800022D4
0x18000239a  mov     [rsp+48h+var_18], 86Eh
0x1800023a2  jmp     loc_1800022B0
```
