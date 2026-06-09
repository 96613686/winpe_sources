# SslExpandBinderKey

- ea: `0x180013190`
- end: `0x1800133c2`
- name: `SslExpandBinderKey`
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
- `0x180013190`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001321d`
- `ntdll!RtlAllocateHeap` at `0x18001321d`

## string_xrefs

- `0x1800132c9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180013315`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180013359`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180013378`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800133a0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExpandBinderKey(_DWORD *a1, __int64 a2, NCryptKeyName **a3, PVOID *a4, DWORD a5)
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
      if ( *((_WORD *)v8 + 16) < 5u )
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
            213);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v10 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v11 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, PVOID *, DWORD))v8 + 44))(
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
              4594);
            MSCryptFree(v10);
          }
          else
          {
            *(_DWORD *)v10 = 32;
            *(_QWORD *)((char *)v10 + 4) = 1145324610;
            *((_DWORD *)v10 + 3) = 1;
            *((_QWORD *)v10 + 3) = v8;
            *a3 = (NCryptKeyName *)v10;
            _InterlockedIncrement(v8 + 4);
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
              225);
        }
      }
    }
    else
    {
      v12 = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4554);
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
        195);
  }
  return NormalizeNteStatus(v12, (NCRYPT_KEY_HANDLE *)a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180013190  push    rbx
0x180013192  push    rbp
0x180013193  push    rsi
0x180013194  push    r14
0x180013196  sub     rsp, 48h
0x18001319a  mov     rbp, r9
0x18001319d  mov     r14, r8
0x1800131a0  mov     rsi, rdx
0x1800131a3  mov     rbx, rcx
0x1800131a6  test    rcx, rcx
0x1800131a9  jz      short loc_1800131C2
0x1800131ab  cmp     dword ptr [rcx], 1B0h
0x1800131b1  jb      short loc_1800131C2
0x1800131b3  cmp     dword ptr [rcx+4], 44444441h
0x1800131ba  jnz     short loc_1800131C2
0x1800131bc  cmp     dword ptr [rcx+0Ch], 0
0x1800131c0  jz      short loc_1800131C4
0x1800131c2  xor     ebx, ebx
0x1800131c4  test    rdx, rdx
0x1800131c7  jz      short loc_1800131D7
0x1800131c9  cmp     dword ptr [rdx], 20h ; ' '
0x1800131cc  jb      short loc_1800131D7
0x1800131ce  cmp     dword ptr [rdx+4], 44444442h
0x1800131d5  jz      short loc_1800131D9
0x1800131d7  xor     esi, esi
0x1800131d9  mov     [rsp+68h+arg_0], rdi
0x1800131de  test    rbx, rbx
0x1800131e1  jz      loc_1800132EF
0x1800131e7  test    rsi, rsi
0x1800131ea  jz      loc_1800132EF
0x1800131f0  test    r14, r14
0x1800131f3  jz      loc_180013372
0x1800131f9  mov     eax, 5
0x1800131fe  cmp     ax, [rbx+20h]
0x180013202  ja      loc_1800132A3
0x180013208  mov     rcx, gs:60h
0x180013211  xor     edx, edx; Flags
0x180013213  mov     r8d, 20h ; ' '; Size
0x180013219  mov     rcx, [rcx+30h]; HeapHandle
0x18001321d  call    cs:__imp_RtlAllocateHeap
0x180013223  mov     rdi, rax
0x180013226  test    rax, rax
0x180013229  jz      loc_18001332B
0x18001322f  mov     ecx, [rsp+68h+arg_20]
0x180013236  lea     r8, [rax+10h]
0x18001323a  xorps   xmm0, xmm0
0x18001323d  mov     [rsp+68h+var_48], ecx
0x180013241  movups  xmmword ptr [rax], xmm0
0x180013244  mov     r9, rbp
0x180013247  movups  xmmword ptr [rax+10h], xmm0
0x18001324b  mov     rdx, [rsi+10h]
0x18001324f  mov     rcx, [rbx+1A8h]
0x180013256  mov     rax, [rbx+160h]
0x18001325d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013262  mov     esi, eax
0x180013264  test    eax, eax
0x180013266  js      loc_18001339A
0x18001326c  mov     dword ptr [rdi], 20h ; ' '
0x180013272  mov     qword ptr [rdi+4], 44444442h
0x18001327a  mov     dword ptr [rdi+0Ch], 1
0x180013281  mov     [rdi+18h], rbx
0x180013285  mov     [r14], rdi
0x180013288  lock inc dword ptr [rbx+10h]
0x18001328c  xor     esi, esi
0x18001328e  mov     ecx, esi
0x180013290  mov     rdi, [rsp+68h+arg_0]
0x180013295  add     rsp, 48h
0x180013299  pop     r14
0x18001329b  pop     rsi
0x18001329c  pop     rbp
0x18001329d  pop     rbx
0x18001329e  jmp     NormalizeNteStatus
0x1800132a3  mov     esi, 80090029h
0x1800132a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132af  lea     rax, WPP_GLOBAL_Control
0x1800132b6  cmp     rcx, rax
0x1800132b9  jz      short loc_18001328E
0x1800132bb  test    byte ptr [rcx+1Ch], 1
0x1800132bf  jz      short loc_18001328E
0x1800132c1  mov     [rsp+68h+var_38], 11D5h
0x1800132c9  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800132d0  mov     [rsp+68h+var_40], rax
0x1800132d5  mov     [rsp+68h+var_48], 80090029h
0x1800132dd  mov     rcx, [rcx+10h]
0x1800132e1  lea     r9, aStatus; "Status"
0x1800132e8  call    WPP_SF_sDsd
0x1800132ed  jmp     short loc_18001328E
0x1800132ef  mov     esi, 80090026h
0x1800132f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132fb  lea     rax, WPP_GLOBAL_Control
0x180013302  cmp     rcx, rax
0x180013305  jz      short loc_18001328E
0x180013307  test    byte ptr [rcx+1Ch], 1
0x18001330b  jz      short loc_18001328E
0x18001330d  mov     [rsp+68h+var_38], 11C3h
0x180013315  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001331c  mov     [rsp+68h+var_40], rax
0x180013321  mov     [rsp+68h+var_48], 80090026h
0x180013329  jmp     short loc_1800132DD
0x18001332b  mov     esi, 8009000Eh
0x180013330  mov     rcx, cs:WPP_GLOBAL_Control
0x180013337  lea     rax, WPP_GLOBAL_Control
0x18001333e  cmp     rcx, rax
0x180013341  jz      loc_18001328E
0x180013347  test    byte ptr [rcx+1Ch], 1
0x18001334b  jz      loc_18001328E
0x180013351  mov     [rsp+68h+var_38], 11E1h
0x180013359  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013360  mov     [rsp+68h+var_40], rax
0x180013365  mov     [rsp+68h+var_48], 8009000Eh
0x18001336d  jmp     loc_1800132DD
0x180013372  mov     r9d, 11CAh
0x180013378  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001337f  lea     rdx, aStatus; "Status"
0x180013386  mov     ecx, 80090027h
0x18001338b  mov     esi, 80090027h
0x180013390  call    DebugTraceError
0x180013395  jmp     loc_18001328E
0x18001339a  mov     r9d, 11F2h
0x1800133a0  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800133a7  lea     rdx, aStatus; "Status"
0x1800133ae  mov     ecx, eax
0x1800133b0  call    DebugTraceError
0x1800133b5  mov     rcx, rdi
0x1800133b8  call    MSCryptFree
0x1800133bd  jmp     loc_18001328E
```
