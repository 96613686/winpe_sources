# SrvCryptDeleteKey

- ea: `0x180009ca0`
- end: `0x180009dcf`
- name: `SrvCryptDeleteKey`
- size: `303`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x180007140`
- `0x180009ca0`
- `0x180019010`

## string_xrefs

- `0x180009ce7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180009d63`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180009daa`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptDeleteKey(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  _DWORD *v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // esi
  int v13; // eax

  if ( a1 )
  {
    v7 = SrvLookupAndReferenceKey(a1, a3, 1);
    v8 = (_DWORD *)v7;
    if ( v7 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)(v7 + 32) + 112LL))(
              *(_QWORD *)(*(_QWORD *)(v7 + 32) + 296LL),
              *(_QWORD *)(v7 + 40),
              a4);
      v12 = v11;
      if ( v11 < 0 )
      {
        DebugTraceError(
          (unsigned int)v11,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          786);
        v6 = NormalizeNteStatus(v12);
        *v8 = 1145324615;
        return v6;
      }
      SrvRemoveKeyFromList(a1, v8);
      v13 = SrvDereferenceKey(v8);
      v6 = v13;
      if ( v13 >= 0 )
        return v6;
      v9 = 817;
      v10 = (unsigned int)v13;
    }
    else
    {
      v6 = -2146893786;
      v9 = 775;
      v10 = 2148073510LL;
    }
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v9);
    return v6;
  }
  v6 = -2146893786;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      248);
  return v6;
}

```

## disassembly

```asm
0x180009ca0  mov     [rsp+arg_0], rbx
0x180009ca5  mov     [rsp+arg_8], rsi
0x180009caa  push    rdi
0x180009cab  sub     rsp, 40h
0x180009caf  mov     esi, r9d
0x180009cb2  mov     rax, r8
0x180009cb5  mov     rbx, rcx
0x180009cb8  test    rcx, rcx
0x180009cbb  jnz     short loc_180009D14
0x180009cbd  mov     ebx, 80090026h
0x180009cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cc9  lea     rax, WPP_GLOBAL_Control
0x180009cd0  cmp     rcx, rax
0x180009cd3  jz      loc_180009DBD
0x180009cd9  test    byte ptr [rcx+1Ch], 1
0x180009cdd  jz      loc_180009DBD
0x180009ce3  mov     rcx, [rcx+10h]
0x180009ce7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009cee  mov     [rsp+48h+var_18], 2F8h
0x180009cf6  lea     r9, aStatus; "Status"
0x180009cfd  mov     [rsp+48h+var_20], r8
0x180009d02  mov     [rsp+48h+var_28], 80090026h
0x180009d0a  call    WPP_SF_sDsd
0x180009d0f  jmp     loc_180009DBD
0x180009d14  mov     r8d, 1
0x180009d1a  mov     rdx, rax
0x180009d1d  call    SrvLookupAndReferenceKey
0x180009d22  mov     rdi, rax
0x180009d25  test    rax, rax
0x180009d28  jnz     short loc_180009D3C
0x180009d2a  mov     ebx, 80090026h
0x180009d2f  mov     r9d, 307h
0x180009d35  mov     ecx, 80090026h
0x180009d3a  jmp     short loc_180009DAA
0x180009d3c  mov     rcx, [rax+20h]
0x180009d40  mov     r8d, esi
0x180009d43  mov     rdx, [rdi+28h]
0x180009d47  mov     rax, [rcx+70h]
0x180009d4b  mov     rcx, [rcx+128h]
0x180009d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d57  mov     esi, eax
0x180009d59  test    eax, eax
0x180009d5b  jns     short loc_180009D89
0x180009d5d  mov     r9d, 312h
0x180009d63  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009d6a  lea     rdx, aStatus; "Status"
0x180009d71  mov     ecx, eax
0x180009d73  call    DebugTraceError
0x180009d78  mov     ecx, esi
0x180009d7a  call    NormalizeNteStatus
0x180009d7f  mov     ebx, eax
0x180009d81  mov     dword ptr [rdi], 44444447h
0x180009d87  jmp     short loc_180009DBD
0x180009d89  mov     rdx, rdi
0x180009d8c  mov     rcx, rbx
0x180009d8f  call    SrvRemoveKeyFromList
0x180009d94  mov     rcx, rdi
0x180009d97  call    SrvDereferenceKey
0x180009d9c  mov     ebx, eax
0x180009d9e  test    eax, eax
0x180009da0  jns     short loc_180009DBD
0x180009da2  mov     r9d, 331h
0x180009da8  mov     ecx, eax
0x180009daa  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009db1  lea     rdx, aStatus; "Status"
0x180009db8  call    DebugTraceError
0x180009dbd  mov     rsi, [rsp+48h+arg_8]
0x180009dc2  mov     eax, ebx
0x180009dc4  mov     rbx, [rsp+48h+arg_0]
0x180009dc9  add     rsp, 40h
0x180009dcd  pop     rdi
0x180009dce  retn
```
