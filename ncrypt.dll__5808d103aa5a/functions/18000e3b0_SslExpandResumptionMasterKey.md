# SslExpandResumptionMasterKey

- ea: `0x18000e3b0`
- end: `0x18000e636`
- name: `SslExpandResumptionMasterKey`
- size: `646`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x18000e3b0`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000e45d`
- `ntdll!RtlAllocateHeap` at `0x18000e45d`

## string_xrefs

- `0x18000e517`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e563`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e596`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e5f5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e614`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExpandResumptionMasterKey(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        PVOID *a4,
        __int64 a5,
        int a6)
{
  __int64 v7; // rbp
  __int64 v8; // rsi
  _DWORD *v9; // rbx
  _OWORD *Heap; // rax
  _OWORD *v11; // rdi
  int v12; // esi

  v7 = a3;
  v8 = a2;
  v9 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v9 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324610 )
    v8 = 0;
  if ( !a3 || *(_DWORD *)a3 < 0x20u || *(_DWORD *)(a3 + 4) != 1145324611 )
    v7 = 0;
  if ( v9 && v8 && v7 )
  {
    if ( a4 )
    {
      if ( *((_WORD *)v9 + 16) < 5u )
      {
        v12 = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            246);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v11 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _OWORD *, __int64, int))v9 + 42))(
                  *((_QWORD *)v9 + 53),
                  *(_QWORD *)(v8 + 16),
                  *(_QWORD *)(v7 + 16),
                  Heap + 1,
                  a5,
                  a6);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                a2,
                a3,
                (unsigned int)"Status",
                v12,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
                20);
            MSCryptFree(v11);
          }
          else
          {
            *(_DWORD *)v11 = 32;
            *(_QWORD *)((char *)v11 + 4) = 1145324610;
            *((_DWORD *)v11 + 3) = 1;
            *((_QWORD *)v11 + 3) = v9;
            *a4 = v11;
            _InterlockedIncrement(v9 + 4);
            v12 = 0;
          }
        }
        else
        {
          v12 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              a2,
              a3,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              2);
        }
      }
    }
    else
    {
      v12 = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4331);
    }
  }
  else
  {
    v12 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        228);
  }
  return NormalizeNteStatus((unsigned int)v12, (NCRYPT_KEY_HANDLE *)a2, (NCryptKeyName **)a3, a4, a5);
}

```

## disassembly

```asm
0x18000e3b0  push    rbx
0x18000e3b2  push    rbp
0x18000e3b3  push    rsi
0x18000e3b4  push    r14
0x18000e3b6  sub     rsp, 48h
0x18000e3ba  mov     r14, r9
0x18000e3bd  mov     rbp, r8
0x18000e3c0  mov     rsi, rdx
0x18000e3c3  mov     rbx, rcx
0x18000e3c6  test    rcx, rcx
0x18000e3c9  jz      short loc_18000E3E2
0x18000e3cb  cmp     dword ptr [rcx], 1B0h
0x18000e3d1  jb      short loc_18000E3E2
0x18000e3d3  cmp     dword ptr [rcx+4], 44444441h
0x18000e3da  jnz     short loc_18000E3E2
0x18000e3dc  cmp     dword ptr [rcx+0Ch], 0
0x18000e3e0  jz      short loc_18000E3E4
0x18000e3e2  xor     ebx, ebx
0x18000e3e4  test    rdx, rdx
0x18000e3e7  jz      short loc_18000E3F7
0x18000e3e9  cmp     dword ptr [rdx], 20h ; ' '
0x18000e3ec  jb      short loc_18000E3F7
0x18000e3ee  cmp     dword ptr [rdx+4], 44444442h
0x18000e3f5  jz      short loc_18000E3F9
0x18000e3f7  xor     esi, esi
0x18000e3f9  test    r8, r8
0x18000e3fc  jz      short loc_18000E40E
0x18000e3fe  cmp     dword ptr [r8], 20h ; ' '
0x18000e402  jb      short loc_18000E40E
0x18000e404  cmp     dword ptr [r8+4], 44444443h
0x18000e40c  jz      short loc_18000E410
0x18000e40e  xor     ebp, ebp
0x18000e410  mov     [rsp+68h+arg_0], rdi
0x18000e415  test    rbx, rbx
0x18000e418  jz      loc_18000E5C7
0x18000e41e  test    rsi, rsi
0x18000e421  jz      loc_18000E5C7
0x18000e427  test    rbp, rbp
0x18000e42a  jz      loc_18000E5C7
0x18000e430  test    r14, r14
0x18000e433  jz      loc_18000E60E
0x18000e439  mov     eax, 5
0x18000e43e  cmp     ax, [rbx+20h]
0x18000e442  ja      loc_18000E4F1
0x18000e448  mov     rcx, gs:60h
0x18000e451  xor     edx, edx; Flags
0x18000e453  mov     r8d, 20h ; ' '; Size
0x18000e459  mov     rcx, [rcx+30h]; HeapHandle
0x18000e45d  call    cs:__imp_RtlAllocateHeap
0x18000e463  mov     rdi, rax
0x18000e466  test    rax, rax
0x18000e469  jz      loc_18000E53D
0x18000e46f  mov     ecx, [rsp+68h+arg_28]
0x18000e476  lea     r9, [rax+10h]
0x18000e47a  mov     dword ptr [rsp+68h+var_40], ecx
0x18000e47e  xorps   xmm0, xmm0
0x18000e481  mov     rcx, [rsp+68h+arg_20]
0x18000e489  movups  xmmword ptr [rax], xmm0
0x18000e48c  mov     [rsp+68h+var_48], rcx
0x18000e491  movups  xmmword ptr [rax+10h], xmm0
0x18000e495  mov     rcx, [rbx+1A8h]
0x18000e49c  mov     r8, [rbp+10h]
0x18000e4a0  mov     rdx, [rsi+10h]
0x18000e4a4  mov     rax, [rbx+150h]
0x18000e4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b0  mov     esi, eax
0x18000e4b2  test    eax, eax
0x18000e4b4  js      loc_18000E579
0x18000e4ba  mov     dword ptr [rdi], 20h ; ' '
0x18000e4c0  mov     qword ptr [rdi+4], 44444442h
0x18000e4c8  mov     dword ptr [rdi+0Ch], 1
0x18000e4cf  mov     [rdi+18h], rbx
0x18000e4d3  mov     [r14], rdi
0x18000e4d6  lock inc dword ptr [rbx+10h]
0x18000e4da  xor     esi, esi
0x18000e4dc  mov     ecx, esi
0x18000e4de  mov     rdi, [rsp+68h+arg_0]
0x18000e4e3  add     rsp, 48h
0x18000e4e7  pop     r14
0x18000e4e9  pop     rsi
0x18000e4ea  pop     rbp
0x18000e4eb  pop     rbx
0x18000e4ec  jmp     NormalizeNteStatus
0x18000e4f1  mov     esi, 80090029h
0x18000e4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4fd  lea     rax, WPP_GLOBAL_Control
0x18000e504  cmp     rcx, rax
0x18000e507  jz      short loc_18000E4DC
0x18000e509  test    byte ptr [rcx+1Ch], 1
0x18000e50d  jz      short loc_18000E4DC
0x18000e50f  mov     [rsp+68h+var_38], 10F6h
0x18000e517  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e51e  mov     [rsp+68h+var_40], rax
0x18000e523  mov     dword ptr [rsp+68h+var_48], 80090029h
0x18000e52b  mov     rcx, [rcx+10h]
0x18000e52f  lea     r9, aStatus; "Status"
0x18000e536  call    WPP_SF_sDsd
0x18000e53b  jmp     short loc_18000E4DC
0x18000e53d  mov     esi, 8009000Eh
0x18000e542  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e549  lea     rax, WPP_GLOBAL_Control
0x18000e550  cmp     rcx, rax
0x18000e553  jz      short loc_18000E4DC
0x18000e555  test    byte ptr [rcx+1Ch], 1
0x18000e559  jz      short loc_18000E4DC
0x18000e55b  mov     [rsp+68h+var_38], 1102h
0x18000e563  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e56a  mov     [rsp+68h+var_40], rax
0x18000e56f  mov     dword ptr [rsp+68h+var_48], 8009000Eh
0x18000e577  jmp     short loc_18000E52B
0x18000e579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e580  lea     rax, WPP_GLOBAL_Control
0x18000e587  cmp     rcx, rax
0x18000e58a  jz      short loc_18000E5BA
0x18000e58c  test    byte ptr [rcx+1Ch], 1
0x18000e590  jz      short loc_18000E5BA
0x18000e592  mov     rcx, [rcx+10h]
0x18000e596  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e59d  mov     [rsp+68h+var_38], 1114h
0x18000e5a5  lea     r9, aStatus; "Status"
0x18000e5ac  mov     [rsp+68h+var_40], rax
0x18000e5b1  mov     dword ptr [rsp+68h+var_48], esi
0x18000e5b5  call    WPP_SF_sDsd
0x18000e5ba  mov     rcx, rdi
0x18000e5bd  call    MSCryptFree
0x18000e5c2  jmp     loc_18000E4DC
0x18000e5c7  mov     esi, 80090026h
0x18000e5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5d3  lea     rax, WPP_GLOBAL_Control
0x18000e5da  cmp     rcx, rax
0x18000e5dd  jz      loc_18000E4DC
0x18000e5e3  test    byte ptr [rcx+1Ch], 1
0x18000e5e7  jz      loc_18000E4DC
0x18000e5ed  mov     [rsp+68h+var_38], 10E4h
0x18000e5f5  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e5fc  mov     [rsp+68h+var_40], rax
0x18000e601  mov     dword ptr [rsp+68h+var_48], 80090026h
0x18000e609  jmp     loc_18000E52B
0x18000e60e  mov     r9d, 10EBh
0x18000e614  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e61b  lea     rdx, aStatus; "Status"
0x18000e622  mov     ecx, 80090027h
0x18000e627  mov     esi, 80090027h
0x18000e62c  call    DebugTraceError
0x18000e631  jmp     loc_18000E4DC
```
