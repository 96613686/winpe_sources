# SslImportKey

- ea: `0x18000b6c0`
- end: `0x18000b894`
- name: `SslImportKey`
- size: `468`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000b6c0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000b758`
- `ntdll!RtlAllocateHeap` at `0x18000b758`

## string_xrefs

- `0x18000b721`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b80a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b856`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b872`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslImportKey(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, int a5, int a6)
{
  unsigned int v10; // ebp
  _OWORD *Heap; // rax
  int v12; // edx
  int v13; // r8d
  _OWORD *v14; // rdi
  int v15; // eax

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v14 = Heap;
      if ( Heap )
      {
        *Heap = 0;
        Heap[1] = 0;
        v15 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, __int64, __int64, int, int))(a1 + 176))(
                *(_QWORD *)(a1 + 424),
                Heap + 1,
                a3,
                a4,
                a5,
                a6);
        v10 = v15;
        if ( v15 < 0 )
        {
          DebugTraceError(
            (unsigned int)v15,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            2619);
          MSCryptFree(v14);
        }
        else
        {
          *(_DWORD *)v14 = 32;
          *(_QWORD *)((char *)v14 + 4) = 1145324610;
          *((_DWORD *)v14 + 3) = 1;
          *((_QWORD *)v14 + 3) = a1;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
          *a2 = v14;
          v10 = 0;
        }
      }
      else
      {
        v10 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            40);
      }
    }
    else
    {
      v10 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          24);
    }
  }
  else
  {
    v10 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        17);
  }
  return NormalizeNteStatus(v10);
}

```

## disassembly

```asm
0x18000b6c0  push    rbx
0x18000b6c2  push    rbp
0x18000b6c3  push    rsi
0x18000b6c4  push    rdi
0x18000b6c5  push    r14
0x18000b6c7  sub     rsp, 40h
0x18000b6cb  mov     rbp, r9
0x18000b6ce  mov     r14, r8
0x18000b6d1  mov     rsi, rdx
0x18000b6d4  mov     rbx, rcx
0x18000b6d7  test    rcx, rcx
0x18000b6da  jz      short loc_18000B6F3
0x18000b6dc  cmp     dword ptr [rcx], 1B0h
0x18000b6e2  jb      short loc_18000B6F3
0x18000b6e4  cmp     dword ptr [rcx+4], 44444441h
0x18000b6eb  jnz     short loc_18000B6F3
0x18000b6ed  cmp     dword ptr [rcx+0Ch], 0
0x18000b6f1  jz      short loc_18000B73A
0x18000b6f3  mov     ebp, 80090026h
0x18000b6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6ff  lea     rax, WPP_GLOBAL_Control
0x18000b706  cmp     rcx, rax
0x18000b709  jz      loc_18000B7D3
0x18000b70f  test    byte ptr [rcx+1Ch], 1
0x18000b713  jz      loc_18000B7D3
0x18000b719  mov     [rsp+68h+var_38], 0A11h
0x18000b721  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b728  mov     [rsp+68h+var_40], rax
0x18000b72d  mov     [rsp+68h+var_48], 80090026h
0x18000b735  jmp     loc_18000B81E
0x18000b73a  test    rsi, rsi
0x18000b73d  jz      loc_18000B7E4
0x18000b743  mov     rcx, gs:60h
0x18000b74c  xor     edx, edx; Flags
0x18000b74e  mov     r8d, 20h ; ' '; Size
0x18000b754  mov     rcx, [rcx+30h]; HeapHandle
0x18000b758  call    cs:__imp_RtlAllocateHeap
0x18000b75e  mov     rdi, rax
0x18000b761  test    rax, rax
0x18000b764  jz      loc_18000B830
0x18000b76a  mov     ecx, [rsp+68h+arg_28]
0x18000b771  lea     rdx, [rax+10h]
0x18000b775  mov     dword ptr [rsp+68h+var_40], ecx
0x18000b779  xorps   xmm0, xmm0
0x18000b77c  mov     ecx, [rsp+68h+arg_20]
0x18000b783  mov     r9, rbp
0x18000b786  movups  xmmword ptr [rax], xmm0
0x18000b789  mov     [rsp+68h+var_48], ecx
0x18000b78d  mov     r8, r14
0x18000b790  movups  xmmword ptr [rax+10h], xmm0
0x18000b794  mov     rcx, [rbx+1A8h]
0x18000b79b  mov     rax, [rbx+0B0h]
0x18000b7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a7  mov     ebp, eax
0x18000b7a9  test    eax, eax
0x18000b7ab  js      loc_18000B86C
0x18000b7b1  mov     dword ptr [rdi], 20h ; ' '
0x18000b7b7  mov     qword ptr [rdi+4], 44444442h
0x18000b7bf  mov     dword ptr [rdi+0Ch], 1
0x18000b7c6  mov     [rdi+18h], rbx
0x18000b7ca  lock inc dword ptr [rbx+10h]
0x18000b7ce  mov     [rsi], rdi
0x18000b7d1  xor     ebp, ebp
0x18000b7d3  mov     ecx, ebp
0x18000b7d5  add     rsp, 40h
0x18000b7d9  pop     r14
0x18000b7db  pop     rdi
0x18000b7dc  pop     rsi
0x18000b7dd  pop     rbp
0x18000b7de  pop     rbx
0x18000b7df  jmp     NormalizeNteStatus
0x18000b7e4  mov     ebp, 80090027h
0x18000b7e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7f0  lea     rax, WPP_GLOBAL_Control
0x18000b7f7  cmp     rcx, rax
0x18000b7fa  jz      short loc_18000B7D3
0x18000b7fc  test    byte ptr [rcx+1Ch], 1
0x18000b800  jz      short loc_18000B7D3
0x18000b802  mov     [rsp+68h+var_38], 0A18h
0x18000b80a  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b811  mov     [rsp+68h+var_40], rax
0x18000b816  mov     [rsp+68h+var_48], 80090027h
0x18000b81e  mov     rcx, [rcx+10h]
0x18000b822  lea     r9, aStatus; "Status"
0x18000b829  call    WPP_SF_sDsd
0x18000b82e  jmp     short loc_18000B7D3
0x18000b830  mov     ebp, 8009000Eh
0x18000b835  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b83c  lea     rax, WPP_GLOBAL_Control
0x18000b843  cmp     rcx, rax
0x18000b846  jz      short loc_18000B7D3
0x18000b848  test    byte ptr [rcx+1Ch], 1
0x18000b84c  jz      short loc_18000B7D3
0x18000b84e  mov     [rsp+68h+var_38], 0A28h
0x18000b856  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b85d  mov     [rsp+68h+var_40], rax
0x18000b862  mov     [rsp+68h+var_48], 8009000Eh
0x18000b86a  jmp     short loc_18000B81E
0x18000b86c  mov     r9d, 0A3Bh
0x18000b872  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b879  lea     rdx, aStatus; "Status"
0x18000b880  mov     ecx, eax
0x18000b882  call    DebugTraceError
0x18000b887  mov     rcx, rdi
0x18000b88a  call    MSCryptFree
0x18000b88f  jmp     loc_18000B7D3
```
