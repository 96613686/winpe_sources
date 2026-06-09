# SslImportMasterKey

- ea: `0x180015cd0`
- end: `0x180015e85`
- name: `SslImportMasterKey`
- size: `437`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, unsigned int, int, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180015cd0`
- `0x180020010`

## string_xrefs

- `0x180015de7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180015e33`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180015e63`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslImportMasterKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  __int64 v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // rbx
  __int64 v14; // r8
  _OWORD *v15; // rax
  _OWORD *v16; // rdi
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v20; // r9
  __int64 v21; // rcx

  v12 = ValidateSslProvHandle();
  if ( v12 )
  {
    v13 = ValidateSslKeyHandle(v11);
    if ( v13 )
    {
      if ( v14 )
      {
        v15 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
        v16 = v15;
        if ( v15 )
        {
          *v15 = 0;
          v15[1] = 0;
          v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, _QWORD, int, __int64, __int64, int, int))(v12 + 168))(
                  *(_QWORD *)(v12 + 424),
                  *(_QWORD *)(v13 + 16),
                  v15 + 1,
                  a4,
                  a5,
                  a6,
                  a7,
                  a8,
                  a9);
          v18 = v17;
          if ( v17 < 0 )
          {
            DebugTraceError(
              (unsigned int)v17,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              2750);
            MSCryptFree(v16);
          }
          else
          {
            *(_DWORD *)v16 = 32;
            *(_QWORD *)((char *)v16 + 4) = 1145324610;
            *((_DWORD *)v16 + 3) = 1;
            *((_QWORD *)v16 + 3) = v12;
            _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
            *a3 = v16;
            v18 = 0;
          }
          return NormalizeNteStatus(v18);
        }
        v18 = -2146893810;
        v20 = 2728;
        v21 = 2148073486LL;
      }
      else
      {
        v18 = -2146893785;
        v20 = 2712;
        v21 = 2148073511LL;
      }
    }
    else
    {
      v18 = -2146893786;
      v20 = 2705;
      v21 = 2148073510LL;
    }
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v20);
    return NormalizeNteStatus(v18);
  }
  v18 = -2146893786;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      137);
  return NormalizeNteStatus(v18);
}

```

## disassembly

```asm
0x180015cd0  push    rbx
0x180015cd2  push    rbp
0x180015cd3  push    rsi
0x180015cd4  push    rdi
0x180015cd5  push    r14
0x180015cd7  sub     rsp, 50h
0x180015cdb  mov     ebp, r9d
0x180015cde  mov     r14, r8
0x180015ce1  call    ValidateSslProvHandle
0x180015ce6  mov     rsi, rax
0x180015ce9  test    rax, rax
0x180015cec  jz      loc_180015DC5
0x180015cf2  mov     rcx, rdx
0x180015cf5  call    ValidateSslKeyHandle
0x180015cfa  mov     rbx, rax
0x180015cfd  test    rax, rax
0x180015d00  jz      loc_180015E11
0x180015d06  test    r8, r8
0x180015d09  jz      loc_180015E4B
0x180015d0f  mov     ecx, 20h ; ' '
0x180015d14  call    SafeAllocaAllocateFromHeap
0x180015d19  mov     rdi, rax
0x180015d1c  test    rax, rax
0x180015d1f  jz      loc_180015E23
0x180015d25  mov     ecx, [rsp+78h+arg_40]
0x180015d2c  lea     r8, [rax+10h]
0x180015d30  mov     [rsp+78h+var_38], ecx
0x180015d34  xorps   xmm0, xmm0
0x180015d37  mov     ecx, [rsp+78h+arg_38]
0x180015d3e  mov     r9d, ebp
0x180015d41  mov     [rsp+78h+var_40], ecx
0x180015d45  mov     rcx, [rsp+78h+arg_30]
0x180015d4d  mov     [rsp+78h+var_48], rcx
0x180015d52  mov     rcx, [rsp+78h+arg_28]
0x180015d5a  movups  xmmword ptr [rax], xmm0
0x180015d5d  mov     [rsp+78h+var_50], rcx
0x180015d62  mov     ecx, [rsp+78h+arg_20]
0x180015d69  movups  xmmword ptr [rax+10h], xmm0
0x180015d6d  mov     rdx, [rbx+10h]
0x180015d71  mov     rax, [rsi+0A8h]
0x180015d78  mov     [rsp+78h+var_58], ecx
0x180015d7c  mov     rcx, [rsi+1A8h]
0x180015d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d88  mov     ebx, eax
0x180015d8a  test    eax, eax
0x180015d8c  js      loc_180015E5D
0x180015d92  mov     dword ptr [rdi], 20h ; ' '
0x180015d98  mov     qword ptr [rdi+4], 44444442h
0x180015da0  mov     dword ptr [rdi+0Ch], 1
0x180015da7  mov     [rdi+18h], rsi
0x180015dab  lock inc dword ptr [rsi+10h]
0x180015daf  mov     [r14], rdi
0x180015db2  xor     ebx, ebx
0x180015db4  mov     ecx, ebx
0x180015db6  add     rsp, 50h
0x180015dba  pop     r14
0x180015dbc  pop     rdi
0x180015dbd  pop     rsi
0x180015dbe  pop     rbp
0x180015dbf  pop     rbx
0x180015dc0  jmp     NormalizeNteStatus
0x180015dc5  mov     ebx, 80090026h
0x180015dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dd1  lea     rax, WPP_GLOBAL_Control
0x180015dd8  cmp     rcx, rax
0x180015ddb  jz      short loc_180015DB4
0x180015ddd  test    byte ptr [rcx+1Ch], 1
0x180015de1  jz      short loc_180015DB4
0x180015de3  mov     rcx, [rcx+10h]
0x180015de7  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015dee  mov     dword ptr [rsp+78h+var_48], 0A89h
0x180015df6  lea     r9, aStatus; "Status"
0x180015dfd  mov     [rsp+78h+var_50], r8
0x180015e02  mov     [rsp+78h+var_58], 80090026h
0x180015e0a  call    WPP_SF_sDsd
0x180015e0f  jmp     short loc_180015DB4
0x180015e11  mov     ebx, 80090026h
0x180015e16  mov     r9d, 0A91h
0x180015e1c  mov     ecx, 80090026h
0x180015e21  jmp     short loc_180015E33
0x180015e23  mov     ebx, 8009000Eh
0x180015e28  mov     r9d, 0AA8h
0x180015e2e  mov     ecx, 8009000Eh
0x180015e33  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015e3a  lea     rdx, aStatus; "Status"
0x180015e41  call    DebugTraceError
0x180015e46  jmp     loc_180015DB4
0x180015e4b  mov     ebx, 80090027h
0x180015e50  mov     r9d, 0A98h
0x180015e56  mov     ecx, 80090027h
0x180015e5b  jmp     short loc_180015E33
0x180015e5d  mov     r9d, 0ABEh
0x180015e63  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015e6a  lea     rdx, aStatus; "Status"
0x180015e71  mov     ecx, eax
0x180015e73  call    DebugTraceError
0x180015e78  mov     rcx, rdi
0x180015e7b  call    MSCryptFree
0x180015e80  jmp     loc_180015DB4
```
