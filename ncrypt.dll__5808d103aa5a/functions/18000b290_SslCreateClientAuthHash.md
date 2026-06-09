# SslCreateClientAuthHash

- ea: `0x18000b290`
- end: `0x18000b4e2`
- name: `SslCreateClientAuthHash`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000b290`
- `0x18000c8e0`
- `0x18000d02c`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000b334`
- `ntdll!RtlAllocateHeap` at `0x18000b334`

## string_xrefs

- `0x18000b2f1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b368`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b423`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b482`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b4c9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslCreateClientAuthHash(
        __int64 a1,
        NCRYPT_KEY_HANDLE *a2,
        NCryptKeyName **a3,
        PVOID *a4,
        __int64 a5,
        int a6)
{
  unsigned int v6; // ebp
  unsigned int v7; // r14d
  int v10; // ebp
  _OWORD *Heap; // rax
  _OWORD *v12; // rdi

  v6 = (unsigned int)a4;
  v7 = (unsigned int)a3;
  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 )
    {
      if ( *(_WORD *)(a1 + 32) < 2u )
      {
        v10 = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            2);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v12 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v10 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD, _QWORD, __int64, int))(a1 + 232))(
                  *(_QWORD *)(a1 + 424),
                  Heap + 1,
                  v7,
                  v6,
                  a5,
                  a6);
          if ( v10 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (_DWORD)a2,
                (_DWORD)a3,
                (unsigned int)"Status",
                v10,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
                37);
            MSCryptFree(v12);
          }
          else
          {
            *(_DWORD *)v12 = 32;
            *(_QWORD *)((char *)v12 + 4) = 1145324611;
            *((_DWORD *)v12 + 3) = 1;
            *((_QWORD *)v12 + 3) = a1;
            _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
            *a2 = (NCRYPT_KEY_HANDLE)v12;
            v10 = 0;
          }
        }
        else
        {
          v10 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              18);
        }
      }
    }
    else
    {
      v10 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          244);
    }
  }
  else
  {
    v10 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        237);
  }
  return NormalizeNteStatus((unsigned int)v10, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000b290  push    rbx
0x18000b292  push    rbp
0x18000b293  push    rsi
0x18000b294  push    rdi
0x18000b295  push    r14
0x18000b297  sub     rsp, 40h
0x18000b29b  mov     ebp, r9d
0x18000b29e  mov     r14d, r8d
0x18000b2a1  mov     rsi, rdx
0x18000b2a4  mov     rbx, rcx
0x18000b2a7  test    rcx, rcx
0x18000b2aa  jz      short loc_18000B2C3
0x18000b2ac  cmp     dword ptr [rcx], 1B0h
0x18000b2b2  jb      short loc_18000B2C3
0x18000b2b4  cmp     dword ptr [rcx+4], 44444441h
0x18000b2bb  jnz     short loc_18000B2C3
0x18000b2bd  cmp     dword ptr [rcx+0Ch], 0
0x18000b2c1  jz      short loc_18000B307
0x18000b2c3  mov     ebp, 80090026h
0x18000b2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2cf  lea     rax, WPP_GLOBAL_Control
0x18000b2d6  cmp     rcx, rax
0x18000b2d9  jz      loc_18000B38C
0x18000b2df  test    byte ptr [rcx+1Ch], 1
0x18000b2e3  jz      loc_18000B38C
0x18000b2e9  mov     [rsp+68h+var_38], 2EDh
0x18000b2f1  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b2f8  mov     [rsp+68h+var_40], rax
0x18000b2fd  mov     dword ptr [rsp+68h+var_48], 80090026h
0x18000b305  jmp     short loc_18000B37C
0x18000b307  test    rsi, rsi
0x18000b30a  jz      loc_18000B49B
0x18000b310  mov     eax, 2
0x18000b315  cmp     ax, [rcx+20h]
0x18000b319  ja      loc_18000B454
0x18000b31f  mov     rcx, gs:60h
0x18000b328  xor     edx, edx; Flags
0x18000b32a  mov     r8d, 20h ; ' '; Size
0x18000b330  mov     rcx, [rcx+30h]; HeapHandle
0x18000b334  call    cs:__imp_RtlAllocateHeap
0x18000b33a  mov     rdi, rax
0x18000b33d  test    rax, rax
0x18000b340  jnz     short loc_18000B39D
0x18000b342  mov     ebp, 8009000Eh
0x18000b347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b34e  lea     rax, WPP_GLOBAL_Control
0x18000b355  cmp     rcx, rax
0x18000b358  jz      short loc_18000B38C
0x18000b35a  test    byte ptr [rcx+1Ch], 1
0x18000b35e  jz      short loc_18000B38C
0x18000b360  mov     [rsp+68h+var_38], 312h
0x18000b368  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b36f  mov     [rsp+68h+var_40], rax
0x18000b374  mov     dword ptr [rsp+68h+var_48], 8009000Eh
0x18000b37c  mov     rcx, [rcx+10h]
0x18000b380  lea     r9, aStatus; "Status"
0x18000b387  call    WPP_SF_sDsd
0x18000b38c  mov     ecx, ebp
0x18000b38e  add     rsp, 40h
0x18000b392  pop     r14
0x18000b394  pop     rdi
0x18000b395  pop     rsi
0x18000b396  pop     rbp
0x18000b397  pop     rbx
0x18000b398  jmp     NormalizeNteStatus
0x18000b39d  mov     ecx, [rsp+68h+arg_28]
0x18000b3a4  lea     rdx, [rax+10h]
0x18000b3a8  mov     dword ptr [rsp+68h+var_40], ecx
0x18000b3ac  xorps   xmm0, xmm0
0x18000b3af  mov     rcx, [rsp+68h+arg_20]
0x18000b3b7  mov     r9d, ebp
0x18000b3ba  movups  xmmword ptr [rax], xmm0
0x18000b3bd  mov     [rsp+68h+var_48], rcx
0x18000b3c2  mov     r8d, r14d
0x18000b3c5  movups  xmmword ptr [rax+10h], xmm0
0x18000b3c9  mov     rcx, [rbx+1A8h]
0x18000b3d0  mov     rax, [rbx+0E8h]
0x18000b3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3dc  mov     ebp, eax
0x18000b3de  test    eax, eax
0x18000b3e0  js      short loc_18000B406
0x18000b3e2  mov     dword ptr [rdi], 20h ; ' '
0x18000b3e8  mov     qword ptr [rdi+4], 44444443h
0x18000b3f0  mov     dword ptr [rdi+0Ch], 1
0x18000b3f7  mov     [rdi+18h], rbx
0x18000b3fb  lock inc dword ptr [rbx+10h]
0x18000b3ff  mov     [rsi], rdi
0x18000b402  xor     ebp, ebp
0x18000b404  jmp     short loc_18000B38C
0x18000b406  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b40d  lea     rax, WPP_GLOBAL_Control
0x18000b414  cmp     rcx, rax
0x18000b417  jz      short loc_18000B447
0x18000b419  test    byte ptr [rcx+1Ch], 1
0x18000b41d  jz      short loc_18000B447
0x18000b41f  mov     rcx, [rcx+10h]
0x18000b423  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b42a  mov     [rsp+68h+var_38], 325h
0x18000b432  lea     r9, aStatus; "Status"
0x18000b439  mov     [rsp+68h+var_40], rax
0x18000b43e  mov     dword ptr [rsp+68h+var_48], ebp
0x18000b442  call    WPP_SF_sDsd
0x18000b447  mov     rcx, rdi
0x18000b44a  call    MSCryptFree
0x18000b44f  jmp     loc_18000B38C
0x18000b454  mov     ebp, 80090029h
0x18000b459  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b460  lea     rax, WPP_GLOBAL_Control
0x18000b467  cmp     rcx, rax
0x18000b46a  jz      loc_18000B38C
0x18000b470  test    byte ptr [rcx+1Ch], 1
0x18000b474  jz      loc_18000B38C
0x18000b47a  mov     [rsp+68h+var_38], 302h
0x18000b482  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b489  mov     [rsp+68h+var_40], rax
0x18000b48e  mov     dword ptr [rsp+68h+var_48], 80090029h
0x18000b496  jmp     loc_18000B37C
0x18000b49b  mov     ebp, 80090027h
0x18000b4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4a7  lea     rax, WPP_GLOBAL_Control
0x18000b4ae  cmp     rcx, rax
0x18000b4b1  jz      loc_18000B38C
0x18000b4b7  test    byte ptr [rcx+1Ch], 1
0x18000b4bb  jz      loc_18000B38C
0x18000b4c1  mov     [rsp+68h+var_38], 2F4h
0x18000b4c9  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b4d0  mov     [rsp+68h+var_40], rax
0x18000b4d5  mov     dword ptr [rsp+68h+var_48], 80090027h
0x18000b4dd  jmp     loc_18000B37C
```
