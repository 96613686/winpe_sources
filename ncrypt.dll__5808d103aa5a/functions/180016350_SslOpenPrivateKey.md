# SslOpenPrivateKey

- ea: `0x180016350`
- end: `0x18001645b`
- name: `SslOpenPrivateKey`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x180016350`
- `0x180020010`

## string_xrefs

- `0x180016377`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180016431`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslOpenPrivateKey(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        BYTE *a5,
        DWORD a6,
        DWORD *a7)
{
  __int64 v10; // rsi
  unsigned int v11; // edi
  NCRYPT_KEY_HANDLE *v12; // rdx
  NCryptKeyName **v13; // r8
  NCryptAlgorithmName **v14; // r9
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r9
  int v19; // eax

  v10 = ValidateSslProvHandle(a1);
  if ( v10 )
  {
    if ( a2 && a3 )
    {
      v15 = SafeAllocaAllocateFromHeap(32);
      v16 = v15;
      if ( v15 )
      {
        v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD))(v10 + 192))(
                *(_QWORD *)(v10 + 424),
                v15 + 16,
                a3,
                a4);
        v11 = v19;
        if ( v19 >= 0 )
        {
          *(_DWORD *)v16 = 32;
          *(_QWORD *)(v16 + 4) = 1145324610;
          *(_DWORD *)(v16 + 12) = 1;
          *(_QWORD *)(v16 + 24) = v10;
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 16));
          *a2 = v16;
          v11 = 0;
          return NormalizeNteStatus(v11, v12, v13, v14, a5, a6, a7);
        }
        v17 = (unsigned int)v19;
        v18 = 2912;
      }
      else
      {
        v11 = -2146893810;
        v17 = 2148073486LL;
        v18 = 2896;
      }
    }
    else
    {
      v16 = 0;
      v11 = -2146893785;
      v17 = 2148073511LL;
      v18 = 2880;
    }
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v18);
    if ( v16 )
      MSCryptFree(v16);
  }
  else
  {
    v11 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 2873);
  }
  return NormalizeNteStatus(v11, v12, v13, v14, a5, a6, a7);
}

```

## disassembly

```asm
0x180016350  push    rbx
0x180016352  push    rbp
0x180016353  push    rsi
0x180016354  push    rdi
0x180016355  push    r14
0x180016357  sub     rsp, 30h
0x18001635b  mov     ebp, r9d
0x18001635e  mov     rdi, r8
0x180016361  mov     r14, rdx
0x180016364  call    ValidateSslProvHandle
0x180016369  mov     rsi, rax
0x18001636c  test    rax, rax
0x18001636f  jnz     short loc_180016399
0x180016371  mov     r9d, 0B39h
0x180016377  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001637e  lea     rdx, aStatus; "Status"
0x180016385  mov     ecx, 80090026h
0x18001638a  mov     edi, 80090026h
0x18001638f  call    DebugTraceError
0x180016394  jmp     loc_18001644A
0x180016399  test    r14, r14
0x18001639c  jz      short loc_180016418
0x18001639e  test    rdi, rdi
0x1800163a1  jz      short loc_180016418
0x1800163a3  mov     ecx, 20h ; ' '
0x1800163a8  call    SafeAllocaAllocateFromHeap
0x1800163ad  mov     rbx, rax
0x1800163b0  test    rax, rax
0x1800163b3  jnz     short loc_1800163C7
0x1800163b5  mov     edi, 8009000Eh
0x1800163ba  mov     ecx, 8009000Eh
0x1800163bf  mov     r9d, 0B50h
0x1800163c5  jmp     short loc_18001642A
0x1800163c7  mov     rcx, [rsi+1A8h]
0x1800163ce  lea     rdx, [rax+10h]
0x1800163d2  mov     rax, [rsi+0C0h]
0x1800163d9  mov     r9d, ebp
0x1800163dc  mov     r8, rdi
0x1800163df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e4  mov     edi, eax
0x1800163e6  test    eax, eax
0x1800163e8  jns     short loc_1800163F4
0x1800163ea  mov     ecx, eax
0x1800163ec  mov     r9d, 0B60h
0x1800163f2  jmp     short loc_18001642A
0x1800163f4  mov     dword ptr [rbx], 20h ; ' '
0x1800163fa  mov     qword ptr [rbx+4], 44444442h
0x180016402  mov     dword ptr [rbx+0Ch], 1
0x180016409  mov     [rbx+18h], rsi
0x18001640d  lock inc dword ptr [rsi+10h]
0x180016411  mov     [r14], rbx
0x180016414  xor     edi, edi
0x180016416  jmp     short loc_18001644A
0x180016418  xor     ebx, ebx
0x18001641a  mov     edi, 80090027h
0x18001641f  mov     ecx, 80090027h
0x180016424  mov     r9d, 0B40h
0x18001642a  lea     rdx, aStatus; "Status"
0x180016431  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180016438  call    DebugTraceError
0x18001643d  test    rbx, rbx
0x180016440  jz      short loc_18001644A
0x180016442  mov     rcx, rbx
0x180016445  call    MSCryptFree
0x18001644a  mov     ecx, edi
0x18001644c  add     rsp, 30h
0x180016450  pop     r14
0x180016452  pop     rdi
0x180016453  pop     rsi
0x180016454  pop     rbp
0x180016455  pop     rbx
0x180016456  jmp     NormalizeNteStatus
```
