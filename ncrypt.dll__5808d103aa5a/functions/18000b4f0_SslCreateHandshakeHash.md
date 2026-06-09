# SslCreateHandshakeHash

- ea: `0x18000b4f0`
- end: `0x18000b6b6`
- name: `SslCreateHandshakeHash`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000b4f0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000b588`
- `ntdll!RtlAllocateHeap` at `0x18000b588`

## string_xrefs

- `0x18000b551`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b62c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b678`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000b694`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslCreateHandshakeHash(
        __int64 a1,
        NCRYPT_KEY_HANDLE *a2,
        NCryptKeyName **a3,
        PVOID *a4,
        DWORD a5)
{
  unsigned int v5; // ebp
  unsigned int v6; // r14d
  unsigned int v9; // ebp
  _OWORD *Heap; // rax
  _OWORD *v11; // rdi
  int v12; // eax

  v5 = (unsigned int)a4;
  v6 = (unsigned int)a3;
  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v11 = Heap;
      if ( Heap )
      {
        *Heap = 0;
        Heap[1] = 0;
        v12 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD, _QWORD, DWORD))(a1 + 72))(
                *(_QWORD *)(a1 + 424),
                Heap + 1,
                v6,
                v5,
                a5);
        v9 = v12;
        if ( v12 < 0 )
        {
          DebugTraceError(
            (unsigned int)v12,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            684);
          MSCryptFree(v11);
        }
        else
        {
          *(_DWORD *)v11 = 32;
          *(_QWORD *)((char *)v11 + 4) = 1145324611;
          *((_DWORD *)v11 + 3) = 1;
          *((_QWORD *)v11 + 3) = a1;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
          *a2 = (NCRYPT_KEY_HANDLE)v11;
          v9 = 0;
        }
      }
      else
      {
        v9 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            154);
      }
    }
    else
    {
      v9 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          138);
    }
  }
  else
  {
    v9 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        131);
  }
  return NormalizeNteStatus(v9, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000b4f0  push    rbx
0x18000b4f2  push    rbp
0x18000b4f3  push    rsi
0x18000b4f4  push    rdi
0x18000b4f5  push    r14
0x18000b4f7  sub     rsp, 40h
0x18000b4fb  mov     ebp, r9d
0x18000b4fe  mov     r14d, r8d
0x18000b501  mov     rsi, rdx
0x18000b504  mov     rbx, rcx
0x18000b507  test    rcx, rcx
0x18000b50a  jz      short loc_18000B523
0x18000b50c  cmp     dword ptr [rcx], 1B0h
0x18000b512  jb      short loc_18000B523
0x18000b514  cmp     dword ptr [rcx+4], 44444441h
0x18000b51b  jnz     short loc_18000B523
0x18000b51d  cmp     dword ptr [rcx+0Ch], 0
0x18000b521  jz      short loc_18000B56A
0x18000b523  mov     ebp, 80090026h
0x18000b528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b52f  lea     rax, WPP_GLOBAL_Control
0x18000b536  cmp     rcx, rax
0x18000b539  jz      loc_18000B5F5
0x18000b53f  test    byte ptr [rcx+1Ch], 1
0x18000b543  jz      loc_18000B5F5
0x18000b549  mov     [rsp+68h+var_38], 283h
0x18000b551  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b558  mov     [rsp+68h+var_40], rax
0x18000b55d  mov     [rsp+68h+var_48], 80090026h
0x18000b565  jmp     loc_18000B640
0x18000b56a  test    rsi, rsi
0x18000b56d  jz      loc_18000B606
0x18000b573  mov     rcx, gs:60h
0x18000b57c  xor     edx, edx; Flags
0x18000b57e  mov     r8d, 20h ; ' '; Size
0x18000b584  mov     rcx, [rcx+30h]; HeapHandle
0x18000b588  call    cs:__imp_RtlAllocateHeap
0x18000b58e  mov     rdi, rax
0x18000b591  test    rax, rax
0x18000b594  jz      loc_18000B652
0x18000b59a  mov     ecx, [rsp+68h+arg_20]
0x18000b5a1  lea     rdx, [rax+10h]
0x18000b5a5  xorps   xmm0, xmm0
0x18000b5a8  mov     [rsp+68h+var_48], ecx
0x18000b5ac  movups  xmmword ptr [rax], xmm0
0x18000b5af  mov     r9d, ebp
0x18000b5b2  mov     r8d, r14d
0x18000b5b5  movups  xmmword ptr [rax+10h], xmm0
0x18000b5b9  mov     rcx, [rbx+1A8h]
0x18000b5c0  mov     rax, [rbx+48h]
0x18000b5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c9  mov     ebp, eax
0x18000b5cb  test    eax, eax
0x18000b5cd  js      loc_18000B68E
0x18000b5d3  mov     dword ptr [rdi], 20h ; ' '
0x18000b5d9  mov     qword ptr [rdi+4], 44444443h
0x18000b5e1  mov     dword ptr [rdi+0Ch], 1
0x18000b5e8  mov     [rdi+18h], rbx
0x18000b5ec  lock inc dword ptr [rbx+10h]
0x18000b5f0  mov     [rsi], rdi
0x18000b5f3  xor     ebp, ebp
0x18000b5f5  mov     ecx, ebp
0x18000b5f7  add     rsp, 40h
0x18000b5fb  pop     r14
0x18000b5fd  pop     rdi
0x18000b5fe  pop     rsi
0x18000b5ff  pop     rbp
0x18000b600  pop     rbx
0x18000b601  jmp     NormalizeNteStatus
0x18000b606  mov     ebp, 80090027h
0x18000b60b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b612  lea     rax, WPP_GLOBAL_Control
0x18000b619  cmp     rcx, rax
0x18000b61c  jz      short loc_18000B5F5
0x18000b61e  test    byte ptr [rcx+1Ch], 1
0x18000b622  jz      short loc_18000B5F5
0x18000b624  mov     [rsp+68h+var_38], 28Ah
0x18000b62c  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b633  mov     [rsp+68h+var_40], rax
0x18000b638  mov     [rsp+68h+var_48], 80090027h
0x18000b640  mov     rcx, [rcx+10h]
0x18000b644  lea     r9, aStatus; "Status"
0x18000b64b  call    WPP_SF_sDsd
0x18000b650  jmp     short loc_18000B5F5
0x18000b652  mov     ebp, 8009000Eh
0x18000b657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b65e  lea     rax, WPP_GLOBAL_Control
0x18000b665  cmp     rcx, rax
0x18000b668  jz      short loc_18000B5F5
0x18000b66a  test    byte ptr [rcx+1Ch], 1
0x18000b66e  jz      short loc_18000B5F5
0x18000b670  mov     [rsp+68h+var_38], 29Ah
0x18000b678  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b67f  mov     [rsp+68h+var_40], rax
0x18000b684  mov     [rsp+68h+var_48], 8009000Eh
0x18000b68c  jmp     short loc_18000B640
0x18000b68e  mov     r9d, 2ACh
0x18000b694  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b69b  lea     rdx, aStatus; "Status"
0x18000b6a2  mov     ecx, eax
0x18000b6a4  call    DebugTraceError
0x18000b6a9  mov     rcx, rdi
0x18000b6ac  call    MSCryptFree
0x18000b6b1  jmp     loc_18000B5F5
```
