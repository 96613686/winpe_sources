# SrvCryptFinalizeKey

- ea: `0x180005bb0`
- end: `0x180005ced`
- name: `SrvCryptFinalizeKey`
- size: `317`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005bb0`
- `0x180005f00`
- `0x180019010`

## string_xrefs

- `0x180005c46`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005c8e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180005cc1`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptFinalizeKey(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  int v7; // edx
  int v8; // ebx
  int v9; // r8d
  int v10; // eax

  if ( a1 )
  {
    v5 = SrvLookupAndReferenceKey(a1, a3, 0);
    v6 = v5;
    if ( v5 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)(v5 + 32) + 104LL))(
             *(_QWORD *)(*(_QWORD *)(v5 + 32) + 296LL),
             *(_QWORD *)(v5 + 40),
             a4);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v7,
            v9,
            (unsigned int)"Status",
            v8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
            217);
        v8 = NormalizeNteStatus((unsigned int)v8);
      }
      v10 = SrvDereferenceKey(v6);
      if ( v10 < 0 && v8 >= 0 )
        return (unsigned int)v10;
    }
    else
    {
      v8 = -2146893786;
      DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 1736);
    }
  }
  else
  {
    v8 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        191);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005bb0  mov     [rsp+arg_0], rbx
0x180005bb5  push    rdi
0x180005bb6  sub     rsp, 40h
0x180005bba  mov     ebx, r9d
0x180005bbd  mov     rax, r8
0x180005bc0  test    rcx, rcx
0x180005bc3  jz      loc_180005C6C
0x180005bc9  xor     r8d, r8d
0x180005bcc  mov     rdx, rax
0x180005bcf  call    SrvLookupAndReferenceKey
0x180005bd4  mov     rdi, rax
0x180005bd7  test    rax, rax
0x180005bda  jz      loc_180005CBB
0x180005be0  mov     rcx, [rax+20h]
0x180005be4  mov     r8d, ebx
0x180005be7  mov     rdx, [rdi+28h]
0x180005beb  mov     rax, [rcx+68h]
0x180005bef  mov     rcx, [rcx+128h]
0x180005bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfb  mov     ebx, eax
0x180005bfd  test    eax, eax
0x180005bff  jnz     short loc_180005C1E
0x180005c01  mov     rcx, rdi
0x180005c04  call    SrvDereferenceKey
0x180005c09  test    eax, eax
0x180005c0b  js      loc_180005CE3
0x180005c11  mov     eax, ebx
0x180005c13  mov     rbx, [rsp+48h+arg_0]
0x180005c18  add     rsp, 40h
0x180005c1c  pop     rdi
0x180005c1d  retn
0x180005c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c25  lea     rax, WPP_GLOBAL_Control
0x180005c2c  cmp     rcx, rax
0x180005c2f  jz      short loc_180005C37
0x180005c31  test    byte ptr [rcx+1Ch], 1
0x180005c35  jnz     short loc_180005C42
0x180005c37  mov     ecx, ebx
0x180005c39  call    NormalizeNteStatus
0x180005c3e  mov     ebx, eax
0x180005c40  jmp     short loc_180005C01
0x180005c42  mov     rcx, [rcx+10h]
0x180005c46  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005c4d  mov     [rsp+48h+var_18], 6D9h
0x180005c55  lea     r9, aStatus; "Status"
0x180005c5c  mov     [rsp+48h+var_20], rax
0x180005c61  mov     [rsp+48h+var_28], ebx
0x180005c65  call    WPP_SF_sDsd
0x180005c6a  jmp     short loc_180005C37
0x180005c6c  mov     ebx, 80090026h
0x180005c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c78  lea     rax, WPP_GLOBAL_Control
0x180005c7f  cmp     rcx, rax
0x180005c82  jz      short loc_180005C11
0x180005c84  test    byte ptr [rcx+1Ch], 1
0x180005c88  jz      short loc_180005C11
0x180005c8a  mov     rcx, [rcx+10h]
0x180005c8e  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005c95  mov     [rsp+48h+var_18], 6BFh
0x180005c9d  lea     r9, aStatus; "Status"
0x180005ca4  mov     [rsp+48h+var_20], rax
0x180005ca9  mov     [rsp+48h+var_28], 80090026h
0x180005cb1  call    WPP_SF_sDsd
0x180005cb6  jmp     loc_180005C11
0x180005cbb  mov     r9d, 6C8h
0x180005cc1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005cc8  lea     rdx, aStatus; "Status"
0x180005ccf  mov     ecx, 80090026h
0x180005cd4  mov     ebx, 80090026h
0x180005cd9  call    DebugTraceError
0x180005cde  jmp     loc_180005C11
0x180005ce3  test    ebx, ebx
0x180005ce5  cmovns  ebx, eax
0x180005ce8  jmp     loc_180005C11
```
