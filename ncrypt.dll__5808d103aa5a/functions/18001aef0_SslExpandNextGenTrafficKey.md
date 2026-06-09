# SslExpandNextGenTrafficKey

- ea: `0x18001aef0`
- end: `0x18001b03e`
- name: `SslExpandNextGenTrafficKey`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001aef0`
- `0x180020010`

## string_xrefs

- `0x18001af42`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001b014`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExpandNextGenTrafficKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdi
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx
  NCRYPT_KEY_HANDLE *v17; // rdx
  NCryptKeyName **v18; // r8
  NCryptAlgorithmName **v19; // r9
  _OWORD *v20; // rax
  _OWORD *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // eax

  v9 = ValidateSslProvHandle(a1);
  v11 = ValidateSslKeyHandle(v10);
  v13 = v11;
  if ( v9 && v11 )
  {
    if ( !v12 )
    {
      v14 = -2146893785;
      v15 = 4668;
      v16 = 2148073511LL;
LABEL_5:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v15);
      return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
    }
    if ( *(_WORD *)(v9 + 32) < 6u )
    {
      v14 = -2146893783;
      v15 = 4679;
      v16 = 2148073513LL;
      goto LABEL_5;
    }
    v20 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
    v21 = v20;
    if ( v20 )
    {
      *v20 = 0;
      v20[1] = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, __int64, _DWORD))(v9 + 368))(
              *(_QWORD *)(v9 + 424),
              *(_QWORD *)(v13 + 16),
              v20 + 1,
              a4,
              (_DWORD)a5);
      v14 = v24;
      if ( v24 >= 0 )
      {
        *(_DWORD *)v21 = 32;
        *(_QWORD *)((char *)v21 + 4) = 1145324610;
        *((_DWORD *)v21 + 3) = 1;
        *((_QWORD *)v21 + 3) = v9;
        *a3 = v21;
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 16));
        v14 = 0;
        return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
      }
      v22 = (unsigned int)v24;
      v23 = 4708;
    }
    else
    {
      v14 = -2146893810;
      v22 = 2148073486LL;
      v23 = 4691;
    }
  }
  else
  {
    v21 = 0;
    v14 = -2146893786;
    v22 = 2148073510LL;
    v23 = 4661;
  }
  DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v23);
  if ( v21 )
    MSCryptFree(v21);
  return NormalizeNteStatus(v14, v17, v18, v19, a5, a6, a7);
}

```

## disassembly

```asm
0x18001aef0  push    rbx
0x18001aef2  push    rbp
0x18001aef3  push    rsi
0x18001aef4  push    rdi
0x18001aef5  push    r14
0x18001aef7  sub     rsp, 30h
0x18001aefb  mov     rbp, r9
0x18001aefe  mov     r14, r8
0x18001af01  call    ValidateSslProvHandle
0x18001af06  mov     rcx, rdx
0x18001af09  mov     rsi, rax
0x18001af0c  call    ValidateSslKeyHandle
0x18001af11  mov     rdi, rax
0x18001af14  test    rsi, rsi
0x18001af17  jz      loc_18001AFFB
0x18001af1d  test    rax, rax
0x18001af20  jz      loc_18001AFFB
0x18001af26  test    r8, r8
0x18001af29  jnz     short loc_18001AF53
0x18001af2b  mov     edi, 80090027h
0x18001af30  mov     r9d, 123Ch
0x18001af36  mov     ecx, 80090027h
0x18001af3b  lea     rdx, aStatus; "Status"
0x18001af42  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001af49  call    DebugTraceError
0x18001af4e  jmp     loc_18001B02D
0x18001af53  mov     eax, 6
0x18001af58  cmp     ax, [rsi+20h]
0x18001af5c  jbe     short loc_18001AF70
0x18001af5e  mov     edi, 80090029h
0x18001af63  mov     r9d, 1247h
0x18001af69  mov     ecx, 80090029h
0x18001af6e  jmp     short loc_18001AF3B
0x18001af70  mov     ecx, 20h ; ' '
0x18001af75  call    SafeAllocaAllocateFromHeap
0x18001af7a  mov     rbx, rax
0x18001af7d  test    rax, rax
0x18001af80  jnz     short loc_18001AF94
0x18001af82  mov     edi, 8009000Eh
0x18001af87  mov     ecx, 8009000Eh
0x18001af8c  mov     r9d, 1253h
0x18001af92  jmp     short loc_18001B00D
0x18001af94  mov     ecx, [rsp+58h+arg_20]
0x18001af9b  lea     r8, [rax+10h]
0x18001af9f  xorps   xmm0, xmm0
0x18001afa2  mov     [rsp+58h+var_38], ecx
0x18001afa6  movups  xmmword ptr [rax], xmm0
0x18001afa9  mov     r9, rbp
0x18001afac  movups  xmmword ptr [rax+10h], xmm0
0x18001afb0  mov     rdx, [rdi+10h]
0x18001afb4  mov     rcx, [rsi+1A8h]
0x18001afbb  mov     rax, [rsi+170h]
0x18001afc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afc7  mov     edi, eax
0x18001afc9  test    eax, eax
0x18001afcb  jns     short loc_18001AFD7
0x18001afcd  mov     ecx, eax
0x18001afcf  mov     r9d, 1264h
0x18001afd5  jmp     short loc_18001B00D
0x18001afd7  mov     dword ptr [rbx], 20h ; ' '
0x18001afdd  mov     qword ptr [rbx+4], 44444442h
0x18001afe5  mov     dword ptr [rbx+0Ch], 1
0x18001afec  mov     [rbx+18h], rsi
0x18001aff0  mov     [r14], rbx
0x18001aff3  lock inc dword ptr [rsi+10h]
0x18001aff7  xor     edi, edi
0x18001aff9  jmp     short loc_18001B02D
0x18001affb  xor     ebx, ebx
0x18001affd  mov     edi, 80090026h
0x18001b002  mov     ecx, 80090026h
0x18001b007  mov     r9d, 1235h
0x18001b00d  lea     rdx, aStatus; "Status"
0x18001b014  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b01b  call    DebugTraceError
0x18001b020  test    rbx, rbx
0x18001b023  jz      short loc_18001B02D
0x18001b025  mov     rcx, rbx
0x18001b028  call    MSCryptFree
0x18001b02d  mov     ecx, edi
0x18001b02f  add     rsp, 30h
0x18001b033  pop     r14
0x18001b035  pop     rdi
0x18001b036  pop     rsi
0x18001b037  pop     rbp
0x18001b038  pop     rbx
0x18001b039  jmp     NormalizeNteStatus
```
