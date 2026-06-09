# SslExtractHandshakeKey

- ea: `0x18000a7e0`
- end: `0x18000aa80`
- name: `SslExtractHandshakeKey`
- size: `672`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000a7e0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000a91f`
- `ntdll!RtlAllocateHeap` at `0x18000a91f`

## string_xrefs

- `0x18000a8ba`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000a953`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000aa17`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000aa36`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000aa5e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExtractHandshakeKey(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        int a7)
{
  __int64 v7; // rbp
  __int64 v8; // rsi
  __int64 v9; // rdi
  _DWORD *v10; // rbx
  unsigned int v11; // edi
  _OWORD *Heap; // rax
  _OWORD *v14; // r15
  int v15; // eax

  v7 = a4;
  v8 = a3;
  v9 = a2;
  v10 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v10 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1145324610 )
    v9 = 0;
  if ( !a3 || *(_DWORD *)a3 < 0x20u || *(_DWORD *)(a3 + 4) != 1145324610 )
    v8 = 0;
  if ( !a4 || *(_DWORD *)a4 < 0x20u || *(_DWORD *)(a4 + 4) != 1145324610 )
    v7 = 0;
  if ( v10 && v9 && v8 && v7 )
  {
    if ( a5 )
    {
      if ( *((_WORD *)v10 + 16) < 4u )
      {
        v11 = -2146893783;
        DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3725);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v14 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v15 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _OWORD *, __int64, int))v10 + 36))(
                  *((_QWORD *)v10 + 53),
                  *(_QWORD *)(v9 + 16),
                  *(_QWORD *)(v8 + 16),
                  *(_QWORD *)(v7 + 16),
                  Heap + 1,
                  a6,
                  a7);
          v11 = v15;
          if ( v15 < 0 )
          {
            DebugTraceError(
              (unsigned int)v15,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              3756);
            MSCryptFree(v14);
          }
          else
          {
            *(_DWORD *)v14 = 32;
            *(_QWORD *)((char *)v14 + 4) = 1145324610;
            *((_DWORD *)v14 + 3) = 1;
            *((_QWORD *)v14 + 3) = v10;
            _InterlockedIncrement(v10 + 4);
            *a5 = v14;
            v11 = 0;
          }
        }
        else
        {
          v11 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              a2,
              a3,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              153);
        }
      }
    }
    else
    {
      v11 = -2146893785;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          130);
    }
  }
  else
  {
    v11 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        123);
  }
  return NormalizeNteStatus(v11, (NCRYPT_KEY_HANDLE *)a2, (NCryptKeyName **)a3, (PVOID *)a4, (DWORD)a5);
}

```

## disassembly

```asm
0x18000a7e0  mov     [rsp+arg_10], rbx
0x18000a7e5  push    rbp
0x18000a7e6  push    rsi
0x18000a7e7  push    rdi
0x18000a7e8  sub     rsp, 40h
0x18000a7ec  mov     rbp, r9
0x18000a7ef  mov     rsi, r8
0x18000a7f2  mov     rdi, rdx
0x18000a7f5  mov     rbx, rcx
0x18000a7f8  test    rcx, rcx
0x18000a7fb  jz      short loc_18000A814
0x18000a7fd  cmp     dword ptr [rcx], 1B0h
0x18000a803  jb      short loc_18000A814
0x18000a805  cmp     dword ptr [rcx+4], 44444441h
0x18000a80c  jnz     short loc_18000A814
0x18000a80e  cmp     dword ptr [rcx+0Ch], 0
0x18000a812  jz      short loc_18000A816
0x18000a814  xor     ebx, ebx
0x18000a816  test    rdx, rdx
0x18000a819  jz      short loc_18000A829
0x18000a81b  cmp     dword ptr [rdx], 20h ; ' '
0x18000a81e  jb      short loc_18000A829
0x18000a820  cmp     dword ptr [rdx+4], 44444442h
0x18000a827  jz      short loc_18000A82B
0x18000a829  xor     edi, edi
0x18000a82b  test    r8, r8
0x18000a82e  jz      short loc_18000A840
0x18000a830  cmp     dword ptr [r8], 20h ; ' '
0x18000a834  jb      short loc_18000A840
0x18000a836  cmp     dword ptr [r8+4], 44444442h
0x18000a83e  jz      short loc_18000A842
0x18000a840  xor     esi, esi
0x18000a842  test    r9, r9
0x18000a845  jz      short loc_18000A857
0x18000a847  cmp     dword ptr [r9], 20h ; ' '
0x18000a84b  jb      short loc_18000A857
0x18000a84d  cmp     dword ptr [r9+4], 44444442h
0x18000a855  jz      short loc_18000A859
0x18000a857  xor     ebp, ebp
0x18000a859  mov     [rsp+58h+arg_0], r14
0x18000a85e  mov     [rsp+58h+arg_8], r15
0x18000a863  test    rbx, rbx
0x18000a866  jz      loc_18000A9E9
0x18000a86c  test    rdi, rdi
0x18000a86f  jz      loc_18000A9E9
0x18000a875  test    rsi, rsi
0x18000a878  jz      loc_18000A9E9
0x18000a87e  test    rbp, rbp
0x18000a881  jz      loc_18000A9E9
0x18000a887  mov     r14, [rsp+58h+arg_20]
0x18000a88f  test    r14, r14
0x18000a892  jnz     short loc_18000A8FB
0x18000a894  mov     edi, 80090027h
0x18000a899  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8a0  lea     rax, WPP_GLOBAL_Control
0x18000a8a7  cmp     rcx, rax
0x18000a8aa  jz      short loc_18000A8DE
0x18000a8ac  test    byte ptr [rcx+1Ch], 1
0x18000a8b0  jz      short loc_18000A8DE
0x18000a8b2  mov     [rsp+58h+var_28], 0E82h
0x18000a8ba  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a8c1  mov     [rsp+58h+var_30], rax
0x18000a8c6  mov     dword ptr [rsp+58h+var_38], 80090027h
0x18000a8ce  mov     rcx, [rcx+10h]
0x18000a8d2  lea     r9, aStatus; "Status"
0x18000a8d9  call    WPP_SF_sDsd
0x18000a8de  mov     ecx, edi
0x18000a8e0  mov     r15, [rsp+58h+arg_8]
0x18000a8e5  mov     r14, [rsp+58h+arg_0]
0x18000a8ea  mov     rbx, [rsp+58h+arg_10]
0x18000a8ef  add     rsp, 40h
0x18000a8f3  pop     rdi
0x18000a8f4  pop     rsi
0x18000a8f5  pop     rbp
0x18000a8f6  jmp     NormalizeNteStatus
0x18000a8fb  mov     eax, 4
0x18000a900  cmp     ax, [rbx+20h]
0x18000a904  ja      loc_18000AA30
0x18000a90a  mov     rcx, gs:60h
0x18000a913  xor     edx, edx; Flags
0x18000a915  mov     r8d, 20h ; ' '; Size
0x18000a91b  mov     rcx, [rcx+30h]; HeapHandle
0x18000a91f  call    cs:__imp_RtlAllocateHeap
0x18000a925  mov     r15, rax
0x18000a928  test    rax, rax
0x18000a92b  jnz     short loc_18000A96C
0x18000a92d  mov     edi, 8009000Eh
0x18000a932  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a939  lea     rax, WPP_GLOBAL_Control
0x18000a940  cmp     rcx, rax
0x18000a943  jz      short loc_18000A8DE
0x18000a945  test    byte ptr [rcx+1Ch], 1
0x18000a949  jz      short loc_18000A8DE
0x18000a94b  mov     [rsp+58h+var_28], 0E99h
0x18000a953  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a95a  mov     [rsp+58h+var_30], rax
0x18000a95f  mov     dword ptr [rsp+58h+var_38], 8009000Eh
0x18000a967  jmp     loc_18000A8CE
0x18000a96c  mov     ecx, [rsp+58h+arg_30]
0x18000a973  lea     r10, [rax+10h]
0x18000a977  mov     [rsp+58h+var_28], ecx
0x18000a97b  xorps   xmm0, xmm0
0x18000a97e  mov     rcx, [rsp+58h+arg_28]
0x18000a986  movups  xmmword ptr [rax], xmm0
0x18000a989  mov     [rsp+58h+var_30], rcx
0x18000a98e  movups  xmmword ptr [rax+10h], xmm0
0x18000a992  mov     rcx, [rbx+1A8h]
0x18000a999  mov     r9, [rbp+10h]
0x18000a99d  mov     r8, [rsi+10h]
0x18000a9a1  mov     rdx, [rdi+10h]
0x18000a9a5  mov     rax, [rbx+120h]
0x18000a9ac  mov     [rsp+58h+var_38], r10
0x18000a9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b6  mov     edi, eax
0x18000a9b8  test    eax, eax
0x18000a9ba  js      loc_18000AA58
0x18000a9c0  mov     dword ptr [r15], 20h ; ' '
0x18000a9c7  mov     qword ptr [r15+4], 44444442h
0x18000a9cf  mov     dword ptr [r15+0Ch], 1
0x18000a9d7  mov     [r15+18h], rbx
0x18000a9db  lock inc dword ptr [rbx+10h]
0x18000a9df  mov     [r14], r15
0x18000a9e2  xor     edi, edi
0x18000a9e4  jmp     loc_18000A8DE
0x18000a9e9  mov     edi, 80090026h
0x18000a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9f5  lea     rax, WPP_GLOBAL_Control
0x18000a9fc  cmp     rcx, rax
0x18000a9ff  jz      loc_18000A8DE
0x18000aa05  test    byte ptr [rcx+1Ch], 1
0x18000aa09  jz      loc_18000A8DE
0x18000aa0f  mov     [rsp+58h+var_28], 0E7Bh
0x18000aa17  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000aa1e  mov     [rsp+58h+var_30], rax
0x18000aa23  mov     dword ptr [rsp+58h+var_38], 80090026h
0x18000aa2b  jmp     loc_18000A8CE
0x18000aa30  mov     r9d, 0E8Dh
0x18000aa36  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000aa3d  lea     rdx, aStatus; "Status"
0x18000aa44  mov     ecx, 80090029h
0x18000aa49  mov     edi, 80090029h
0x18000aa4e  call    DebugTraceError
0x18000aa53  jmp     loc_18000A8DE
0x18000aa58  mov     r9d, 0EACh
0x18000aa5e  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000aa65  lea     rdx, aStatus; "Status"
0x18000aa6c  mov     ecx, eax
0x18000aa6e  call    DebugTraceError
0x18000aa73  mov     rcx, r15
0x18000aa76  call    MSCryptFree
0x18000aa7b  jmp     loc_18000A8DE
```
