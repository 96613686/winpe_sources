# SslCreateEphemeralKey

- ea: `0x18000b050`
- end: `0x18000b286`
- name: `SslCreateEphemeralKey`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000b050`
- `0x18000c8e0`
- `0x18000d02c`
- `0x180020010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b1e3`
- `ntdll!RtlFreeHeap` at `0x18000b1e3`
- `ntdll!RtlAllocateHeap` at `0x18000b0e8`
- `ntdll!RtlAllocateHeap` at `0x18000b0e8`

## string_xrefs

- `0x18000b0b1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b1ad`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b219`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b25d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslCreateEphemeralKey(
        __int64 a1,
        NCRYPT_KEY_HANDLE *a2,
        NCryptKeyName **a3,
        PVOID *a4,
        DWORD a5,
        int a6,
        __int64 a7,
        int a8,
        int a9)
{
  unsigned int v9; // ebp
  unsigned int v10; // r14d
  int v13; // ebp
  _OWORD *Heap; // rax
  _DWORD *v15; // rdi

  v9 = (unsigned int)a4;
  v10 = (unsigned int)a3;
  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v15 = Heap;
      if ( Heap )
      {
        *Heap = 0;
        Heap[1] = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD, _QWORD, DWORD, int, __int64, int, int))(a1 + 64))(
                *(_QWORD *)(a1 + 424),
                Heap + 1,
                v10,
                v9,
                a5,
                a6,
                a7,
                a8,
                a9);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              v13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              69);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        }
        else
        {
          *v15 = 32;
          *(_QWORD *)(v15 + 1) = 1145324610;
          v15[3] = 1;
          *((_QWORD *)v15 + 3) = a1;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
          *a2 = (NCRYPT_KEY_HANDLE)v15;
          v13 = 0;
        }
      }
      else
      {
        v13 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            47);
      }
    }
    else
    {
      v13 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          32);
    }
  }
  else
  {
    v13 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        25);
  }
  return NormalizeNteStatus((unsigned int)v13, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000b050  push    rbx
0x18000b052  push    rbp
0x18000b053  push    rsi
0x18000b054  push    rdi
0x18000b055  push    r14
0x18000b057  sub     rsp, 50h
0x18000b05b  mov     ebp, r9d
0x18000b05e  mov     r14d, r8d
0x18000b061  mov     rsi, rdx
0x18000b064  mov     rbx, rcx
0x18000b067  test    rcx, rcx
0x18000b06a  jz      short loc_18000B083
0x18000b06c  cmp     dword ptr [rcx], 1B0h
0x18000b072  jb      short loc_18000B083
0x18000b074  cmp     dword ptr [rcx+4], 44444441h
0x18000b07b  jnz     short loc_18000B083
0x18000b07d  cmp     dword ptr [rcx+0Ch], 0
0x18000b081  jz      short loc_18000B0CA
0x18000b083  mov     ebp, 80090026h
0x18000b088  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b08f  lea     rax, WPP_GLOBAL_Control
0x18000b096  cmp     rcx, rax
0x18000b099  jz      loc_18000B17F
0x18000b09f  test    byte ptr [rcx+1Ch], 1
0x18000b0a3  jz      loc_18000B17F
0x18000b0a9  mov     dword ptr [rsp+78h+var_48], 219h
0x18000b0b1  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b0b8  mov     [rsp+78h+var_50], rax
0x18000b0bd  mov     [rsp+78h+var_58], 80090026h
0x18000b0c5  jmp     loc_18000B271
0x18000b0ca  test    rsi, rsi
0x18000b0cd  jz      loc_18000B1EB
0x18000b0d3  mov     rcx, gs:60h
0x18000b0dc  xor     edx, edx; Flags
0x18000b0de  mov     r8d, 20h ; ' '; Size
0x18000b0e4  mov     rcx, [rcx+30h]; HeapHandle
0x18000b0e8  call    cs:__imp_RtlAllocateHeap
0x18000b0ee  mov     rdi, rax
0x18000b0f1  test    rax, rax
0x18000b0f4  jz      loc_18000B22F
0x18000b0fa  mov     ecx, [rsp+78h+arg_40]
0x18000b101  lea     rdx, [rax+10h]
0x18000b105  mov     [rsp+78h+var_38], ecx
0x18000b109  xorps   xmm0, xmm0
0x18000b10c  mov     ecx, [rsp+78h+arg_38]
0x18000b113  mov     r9d, ebp
0x18000b116  mov     [rsp+78h+var_40], ecx
0x18000b11a  mov     r8d, r14d
0x18000b11d  mov     rcx, [rsp+78h+arg_30]
0x18000b125  mov     [rsp+78h+var_48], rcx
0x18000b12a  mov     ecx, [rsp+78h+arg_28]
0x18000b131  mov     dword ptr [rsp+78h+var_50], ecx
0x18000b135  mov     ecx, [rsp+78h+arg_20]
0x18000b13c  movups  xmmword ptr [rax], xmm0
0x18000b13f  mov     [rsp+78h+var_58], ecx
0x18000b143  movups  xmmword ptr [rax+10h], xmm0
0x18000b147  mov     rcx, [rbx+1A8h]
0x18000b14e  mov     rax, [rbx+40h]
0x18000b152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b157  mov     ebp, eax
0x18000b159  test    eax, eax
0x18000b15b  js      short loc_18000B190
0x18000b15d  mov     dword ptr [rdi], 20h ; ' '
0x18000b163  mov     qword ptr [rdi+4], 44444442h
0x18000b16b  mov     dword ptr [rdi+0Ch], 1
0x18000b172  mov     [rdi+18h], rbx
0x18000b176  lock inc dword ptr [rbx+10h]
0x18000b17a  mov     [rsi], rdi
0x18000b17d  xor     ebp, ebp
0x18000b17f  mov     ecx, ebp
0x18000b181  add     rsp, 50h
0x18000b185  pop     r14
0x18000b187  pop     rdi
0x18000b188  pop     rsi
0x18000b189  pop     rbp
0x18000b18a  pop     rbx
0x18000b18b  jmp     NormalizeNteStatus
0x18000b190  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b197  lea     rax, WPP_GLOBAL_Control
0x18000b19e  cmp     rcx, rax
0x18000b1a1  jz      short loc_18000B1D1
0x18000b1a3  test    byte ptr [rcx+1Ch], 1
0x18000b1a7  jz      short loc_18000B1D1
0x18000b1a9  mov     rcx, [rcx+10h]
0x18000b1ad  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b1b4  mov     dword ptr [rsp+78h+var_48], 245h
0x18000b1bc  lea     r9, aStatus; "Status"
0x18000b1c3  mov     [rsp+78h+var_50], rax
0x18000b1c8  mov     [rsp+78h+var_58], ebp
0x18000b1cc  call    WPP_SF_sDsd
0x18000b1d1  mov     rcx, gs:60h
0x18000b1da  mov     r8, rdi; P
0x18000b1dd  xor     edx, edx; Flags
0x18000b1df  mov     rcx, [rcx+30h]; HeapHandle
0x18000b1e3  call    cs:__imp_RtlFreeHeap
0x18000b1e9  jmp     short loc_18000B17F
0x18000b1eb  mov     ebp, 80090027h
0x18000b1f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1f7  lea     rax, WPP_GLOBAL_Control
0x18000b1fe  cmp     rcx, rax
0x18000b201  jz      loc_18000B17F
0x18000b207  test    byte ptr [rcx+1Ch], 1
0x18000b20b  jz      loc_18000B17F
0x18000b211  mov     dword ptr [rsp+78h+var_48], 220h
0x18000b219  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b220  mov     [rsp+78h+var_50], rax
0x18000b225  mov     [rsp+78h+var_58], 80090027h
0x18000b22d  jmp     short loc_18000B271
0x18000b22f  mov     ebp, 8009000Eh
0x18000b234  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b23b  lea     rax, WPP_GLOBAL_Control
0x18000b242  cmp     rcx, rax
0x18000b245  jz      loc_18000B17F
0x18000b24b  test    byte ptr [rcx+1Ch], 1
0x18000b24f  jz      loc_18000B17F
0x18000b255  mov     dword ptr [rsp+78h+var_48], 22Fh
0x18000b25d  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b264  mov     [rsp+78h+var_50], rax
0x18000b269  mov     [rsp+78h+var_58], 8009000Eh
0x18000b271  mov     rcx, [rcx+10h]
0x18000b275  lea     r9, aStatus; "Status"
0x18000b27c  call    WPP_SF_sDsd
0x18000b281  jmp     loc_18000B17F
```
