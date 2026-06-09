# SslExtractMasterKey

- ea: `0x18000e170`
- end: `0x18000e3a2`
- name: `SslExtractMasterKey`
- size: `562`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x18000e170`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000e1fd`
- `ntdll!RtlAllocateHeap` at `0x18000e1fd`

## string_xrefs

- `0x18000e2a9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e2f5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e339`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e358`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e380`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExtractMasterKey(_DWORD *a1, __int64 a2, NCryptKeyName **a3, PVOID *a4, DWORD a5)
{
  __int64 v7; // rsi
  _DWORD *v8; // rbx
  _OWORD *Heap; // rax
  _OWORD *v10; // rdi
  int v11; // eax
  unsigned int v12; // esi

  v7 = a2;
  v8 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v8 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324610 )
    v7 = 0;
  if ( v8 && v7 )
  {
    if ( a3 )
    {
      if ( *((_WORD *)v8 + 16) < 4u )
      {
        v12 = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            (_DWORD)a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            253);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v10 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v11 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, PVOID *, DWORD))v8 + 37))(
                  *((_QWORD *)v8 + 53),
                  *(_QWORD *)(v7 + 16),
                  Heap + 1,
                  a4,
                  a5);
          v12 = v11;
          if ( v11 < 0 )
          {
            DebugTraceError(
              (unsigned int)v11,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              3866);
            MSCryptFree(v10);
          }
          else
          {
            *(_DWORD *)v10 = 32;
            *(_QWORD *)((char *)v10 + 4) = 1145324610;
            *((_DWORD *)v10 + 3) = 1;
            *((_QWORD *)v10 + 3) = v8;
            _InterlockedIncrement(v8 + 4);
            *a3 = (NCryptKeyName *)v10;
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
              (_DWORD)a3,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              9);
        }
      }
    }
    else
    {
      v12 = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3826);
    }
  }
  else
  {
    v12 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        235);
  }
  return NormalizeNteStatus(v12, (NCRYPT_KEY_HANDLE *)a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000e170  push    rbx
0x18000e172  push    rbp
0x18000e173  push    rsi
0x18000e174  push    r14
0x18000e176  sub     rsp, 48h
0x18000e17a  mov     rbp, r9
0x18000e17d  mov     r14, r8
0x18000e180  mov     rsi, rdx
0x18000e183  mov     rbx, rcx
0x18000e186  test    rcx, rcx
0x18000e189  jz      short loc_18000E1A2
0x18000e18b  cmp     dword ptr [rcx], 1B0h
0x18000e191  jb      short loc_18000E1A2
0x18000e193  cmp     dword ptr [rcx+4], 44444441h
0x18000e19a  jnz     short loc_18000E1A2
0x18000e19c  cmp     dword ptr [rcx+0Ch], 0
0x18000e1a0  jz      short loc_18000E1A4
0x18000e1a2  xor     ebx, ebx
0x18000e1a4  test    rdx, rdx
0x18000e1a7  jz      short loc_18000E1B7
0x18000e1a9  cmp     dword ptr [rdx], 20h ; ' '
0x18000e1ac  jb      short loc_18000E1B7
0x18000e1ae  cmp     dword ptr [rdx+4], 44444442h
0x18000e1b5  jz      short loc_18000E1B9
0x18000e1b7  xor     esi, esi
0x18000e1b9  mov     [rsp+68h+arg_0], rdi
0x18000e1be  test    rbx, rbx
0x18000e1c1  jz      loc_18000E2CF
0x18000e1c7  test    rsi, rsi
0x18000e1ca  jz      loc_18000E2CF
0x18000e1d0  test    r14, r14
0x18000e1d3  jz      loc_18000E352
0x18000e1d9  mov     eax, 4
0x18000e1de  cmp     ax, [rbx+20h]
0x18000e1e2  ja      loc_18000E283
0x18000e1e8  mov     rcx, gs:60h
0x18000e1f1  xor     edx, edx; Flags
0x18000e1f3  mov     r8d, 20h ; ' '; Size
0x18000e1f9  mov     rcx, [rcx+30h]; HeapHandle
0x18000e1fd  call    cs:__imp_RtlAllocateHeap
0x18000e203  mov     rdi, rax
0x18000e206  test    rax, rax
0x18000e209  jz      loc_18000E30B
0x18000e20f  mov     ecx, [rsp+68h+arg_20]
0x18000e216  lea     r8, [rax+10h]
0x18000e21a  xorps   xmm0, xmm0
0x18000e21d  mov     [rsp+68h+var_48], ecx
0x18000e221  movups  xmmword ptr [rax], xmm0
0x18000e224  mov     r9, rbp
0x18000e227  movups  xmmword ptr [rax+10h], xmm0
0x18000e22b  mov     rdx, [rsi+10h]
0x18000e22f  mov     rcx, [rbx+1A8h]
0x18000e236  mov     rax, [rbx+128h]
0x18000e23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e242  mov     esi, eax
0x18000e244  test    eax, eax
0x18000e246  js      loc_18000E37A
0x18000e24c  mov     dword ptr [rdi], 20h ; ' '
0x18000e252  mov     qword ptr [rdi+4], 44444442h
0x18000e25a  mov     dword ptr [rdi+0Ch], 1
0x18000e261  mov     [rdi+18h], rbx
0x18000e265  lock inc dword ptr [rbx+10h]
0x18000e269  mov     [r14], rdi
0x18000e26c  xor     esi, esi
0x18000e26e  mov     ecx, esi
0x18000e270  mov     rdi, [rsp+68h+arg_0]
0x18000e275  add     rsp, 48h
0x18000e279  pop     r14
0x18000e27b  pop     rsi
0x18000e27c  pop     rbp
0x18000e27d  pop     rbx
0x18000e27e  jmp     NormalizeNteStatus
0x18000e283  mov     esi, 80090029h
0x18000e288  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e28f  lea     rax, WPP_GLOBAL_Control
0x18000e296  cmp     rcx, rax
0x18000e299  jz      short loc_18000E26E
0x18000e29b  test    byte ptr [rcx+1Ch], 1
0x18000e29f  jz      short loc_18000E26E
0x18000e2a1  mov     [rsp+68h+var_38], 0EFDh
0x18000e2a9  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e2b0  mov     [rsp+68h+var_40], rax
0x18000e2b5  mov     [rsp+68h+var_48], 80090029h
0x18000e2bd  mov     rcx, [rcx+10h]
0x18000e2c1  lea     r9, aStatus; "Status"
0x18000e2c8  call    WPP_SF_sDsd
0x18000e2cd  jmp     short loc_18000E26E
0x18000e2cf  mov     esi, 80090026h
0x18000e2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2db  lea     rax, WPP_GLOBAL_Control
0x18000e2e2  cmp     rcx, rax
0x18000e2e5  jz      short loc_18000E26E
0x18000e2e7  test    byte ptr [rcx+1Ch], 1
0x18000e2eb  jz      short loc_18000E26E
0x18000e2ed  mov     [rsp+68h+var_38], 0EEBh
0x18000e2f5  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e2fc  mov     [rsp+68h+var_40], rax
0x18000e301  mov     [rsp+68h+var_48], 80090026h
0x18000e309  jmp     short loc_18000E2BD
0x18000e30b  mov     esi, 8009000Eh
0x18000e310  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e317  lea     rax, WPP_GLOBAL_Control
0x18000e31e  cmp     rcx, rax
0x18000e321  jz      loc_18000E26E
0x18000e327  test    byte ptr [rcx+1Ch], 1
0x18000e32b  jz      loc_18000E26E
0x18000e331  mov     [rsp+68h+var_38], 0F09h
0x18000e339  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e340  mov     [rsp+68h+var_40], rax
0x18000e345  mov     [rsp+68h+var_48], 8009000Eh
0x18000e34d  jmp     loc_18000E2BD
0x18000e352  mov     r9d, 0EF2h
0x18000e358  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e35f  lea     rdx, aStatus; "Status"
0x18000e366  mov     ecx, 80090027h
0x18000e36b  mov     esi, 80090027h
0x18000e370  call    DebugTraceError
0x18000e375  jmp     loc_18000E26E
0x18000e37a  mov     r9d, 0F1Ah
0x18000e380  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e387  lea     rdx, aStatus; "Status"
0x18000e38e  mov     ecx, eax
0x18000e390  call    DebugTraceError
0x18000e395  mov     rcx, rdi
0x18000e398  call    MSCryptFree
0x18000e39d  jmp     loc_18000E26E
```
