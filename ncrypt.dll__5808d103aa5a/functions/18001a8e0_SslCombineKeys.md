# SslCombineKeys

- ea: `0x18001a8e0`
- end: `0x18001aa59`
- name: `SslCombineKeys`
- size: `377`
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
- `0x18001a8e0`
- `0x180020010`

## string_xrefs

- `0x18001a915`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001aa2d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslCombineKeys(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD a6,
        DWORD *a7)
{
  __int64 v8; // rsi
  __int64 v9; // r8
  unsigned int v10; // edi
  __int64 v11; // r9
  __int64 v12; // rcx
  NCRYPT_KEY_HANDLE *v13; // rdx
  NCryptKeyName **v14; // r8
  NCryptAlgorithmName **v15; // r9
  __int64 v16; // rbp
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rdi
  _OWORD *v20; // rax
  _OWORD *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r9
  int v24; // eax

  v8 = ValidateSslProvHandle(a1);
  if ( !v8 )
  {
    v10 = -2146893786;
    v11 = 5165;
    v12 = 2148073510LL;
LABEL_3:
    DebugTraceError(v12, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v11);
    return NormalizeNteStatus(v10, v13, v14, v15, a5, a6, a7);
  }
  v16 = ValidateSslKeyHandle(v9);
  v18 = ValidateSslKeyHandle(v17);
  v19 = v18;
  if ( v16 && v18 && a5 )
  {
    if ( *(_WORD *)(v8 + 32) < 8u )
    {
      v10 = -2146893783;
      v11 = 5184;
      v12 = 2148073513LL;
      goto LABEL_3;
    }
    v20 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
    v21 = v20;
    if ( v20 )
    {
      *v20 = 0;
      v20[1] = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _OWORD *, DWORD))(v8 + 408))(
              *(_QWORD *)(v8 + 424),
              a2,
              *(_QWORD *)(v16 + 16),
              *(_QWORD *)(v19 + 16),
              v20 + 1,
              a6);
      v10 = v24;
      if ( v24 >= 0 )
      {
        *(_DWORD *)v21 = 32;
        *(_QWORD *)((char *)v21 + 4) = 1145324610;
        *((_DWORD *)v21 + 3) = 1;
        *((_QWORD *)v21 + 3) = v8;
        _InterlockedIncrement((volatile signed __int32 *)(v8 + 16));
        *(_QWORD *)a5 = v21;
        v10 = 0;
        return NormalizeNteStatus(v10, v13, v14, v15, a5, a6, a7);
      }
      v22 = (unsigned int)v24;
      v23 = 5207;
    }
    else
    {
      v10 = -2146893810;
      v22 = 2148073486LL;
      v23 = 5192;
    }
  }
  else
  {
    v21 = 0;
    v10 = -2146893785;
    v22 = 2148073511LL;
    v23 = 5176;
  }
  DebugTraceError(v22, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v23);
  if ( v21 )
    MSCryptFree(v21);
  return NormalizeNteStatus(v10, v13, v14, v15, a5, a6, a7);
}

```

## disassembly

```asm
0x18001a8e0  push    rbx
0x18001a8e2  push    rbp
0x18001a8e3  push    rsi
0x18001a8e4  push    rdi
0x18001a8e5  push    r14
0x18001a8e7  push    r15
0x18001a8e9  sub     rsp, 48h
0x18001a8ed  movzx   r15d, dx
0x18001a8f1  call    ValidateSslProvHandle
0x18001a8f6  mov     rsi, rax
0x18001a8f9  test    rax, rax
0x18001a8fc  jnz     short loc_18001A926
0x18001a8fe  mov     edi, 80090026h
0x18001a903  mov     r9d, 142Dh
0x18001a909  mov     ecx, 80090026h
0x18001a90e  lea     rdx, aStatus_0; "status"
0x18001a915  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a91c  call    DebugTraceError
0x18001a921  jmp     loc_18001AA46
0x18001a926  mov     rcx, r8
0x18001a929  call    ValidateSslKeyHandle
0x18001a92e  mov     rcx, r9
0x18001a931  mov     rbp, rax
0x18001a934  call    ValidateSslKeyHandle
0x18001a939  mov     rdi, rax
0x18001a93c  test    rbp, rbp
0x18001a93f  jz      loc_18001AA14
0x18001a945  test    rax, rax
0x18001a948  jz      loc_18001AA14
0x18001a94e  mov     r14, [rsp+78h+arg_20]
0x18001a956  test    r14, r14
0x18001a959  jz      loc_18001AA14
0x18001a95f  mov     eax, 8
0x18001a964  cmp     ax, [rsi+20h]
0x18001a968  jbe     short loc_18001A97C
0x18001a96a  mov     edi, 80090029h
0x18001a96f  mov     r9d, 1440h
0x18001a975  mov     ecx, 80090029h
0x18001a97a  jmp     short loc_18001A90E
0x18001a97c  mov     ecx, 20h ; ' '
0x18001a981  call    SafeAllocaAllocateFromHeap
0x18001a986  mov     rbx, rax
0x18001a989  test    rax, rax
0x18001a98c  jnz     short loc_18001A9A3
0x18001a98e  mov     edi, 8009000Eh
0x18001a993  mov     ecx, 8009000Eh
0x18001a998  mov     r9d, 1448h
0x18001a99e  jmp     loc_18001AA26
0x18001a9a3  mov     ecx, [rsp+78h+arg_28]
0x18001a9aa  lea     rdx, [rax+10h]
0x18001a9ae  xorps   xmm0, xmm0
0x18001a9b1  mov     [rsp+78h+var_50], ecx
0x18001a9b5  movups  xmmword ptr [rax], xmm0
0x18001a9b8  mov     [rsp+78h+var_58], rdx
0x18001a9bd  movzx   edx, r15w
0x18001a9c1  movups  xmmword ptr [rax+10h], xmm0
0x18001a9c5  mov     r9, [rdi+10h]
0x18001a9c9  mov     r8, [rbp+10h]
0x18001a9cd  mov     rcx, [rsi+1A8h]
0x18001a9d4  mov     rax, [rsi+198h]
0x18001a9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9e0  mov     edi, eax
0x18001a9e2  test    eax, eax
0x18001a9e4  jns     short loc_18001A9F0
0x18001a9e6  mov     ecx, eax
0x18001a9e8  mov     r9d, 1457h
0x18001a9ee  jmp     short loc_18001AA26
0x18001a9f0  mov     dword ptr [rbx], 20h ; ' '
0x18001a9f6  mov     qword ptr [rbx+4], 44444442h
0x18001a9fe  mov     dword ptr [rbx+0Ch], 1
0x18001aa05  mov     [rbx+18h], rsi
0x18001aa09  lock inc dword ptr [rsi+10h]
0x18001aa0d  mov     [r14], rbx
0x18001aa10  xor     edi, edi
0x18001aa12  jmp     short loc_18001AA46
0x18001aa14  xor     ebx, ebx
0x18001aa16  mov     edi, 80090027h
0x18001aa1b  mov     ecx, 80090027h
0x18001aa20  mov     r9d, 1438h
0x18001aa26  lea     rdx, aStatus_0; "status"
0x18001aa2d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001aa34  call    DebugTraceError
0x18001aa39  test    rbx, rbx
0x18001aa3c  jz      short loc_18001AA46
0x18001aa3e  mov     rcx, rbx
0x18001aa41  call    MSCryptFree
0x18001aa46  mov     ecx, edi
0x18001aa48  add     rsp, 48h
0x18001aa4c  pop     r15
0x18001aa4e  pop     r14
0x18001aa50  pop     rdi
0x18001aa51  pop     rsi
0x18001aa52  pop     rbp
0x18001aa53  pop     rbx
0x18001aa54  jmp     NormalizeNteStatus
```
