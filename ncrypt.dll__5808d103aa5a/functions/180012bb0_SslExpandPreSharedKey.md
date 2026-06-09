# SslExpandPreSharedKey

- ea: `0x180012bb0`
- end: `0x180012df9`
- name: `SslExpandPreSharedKey`
- size: `585`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, __int64, unsigned int, _QWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180012bb0`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180012c4d`
- `ntdll!RtlAllocateHeap` at `0x180012c4d`

## string_xrefs

- `0x180012d17`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012d6b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012d87`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012daf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012dd7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslExpandPreSharedKey(
        _DWORD *a1,
        _DWORD *a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        __int64 a6,
        int a7)
{
  _DWORD *v9; // rdi
  _DWORD *v10; // rbx
  _OWORD *Heap; // rax
  int v12; // edx
  int v13; // r8d
  _OWORD *v14; // rsi
  int v15; // eax
  unsigned int v16; // edi

  v9 = a2;
  v10 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v10 = 0;
  if ( !a2 || *a2 < 0x20u || a2[1] != 1145324610 )
    v9 = 0;
  if ( v10 && v9 )
  {
    if ( a5 )
    {
      if ( *((_WORD *)v10 + 16) < 5u )
      {
        v16 = -2146893783;
        DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4794);
      }
      else
      {
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
        v14 = Heap;
        if ( Heap )
        {
          *Heap = 0;
          Heap[1] = 0;
          v15 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, _OWORD *, __int64, int))v10 + 45))(
                  *((_QWORD *)v10 + 53),
                  *((_QWORD *)v9 + 2),
                  a3,
                  a4,
                  Heap + 1,
                  a6,
                  a7);
          v16 = v15;
          if ( v15 < 0 )
          {
            DebugTraceError(
              (unsigned int)v15,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              4825);
            MSCryptFree(v14);
          }
          else
          {
            *(_DWORD *)v14 = 32;
            *(_QWORD *)((char *)v14 + 4) = 1145324610;
            *((_DWORD *)v14 + 3) = 1;
            *((_QWORD *)v14 + 3) = v10;
            *a5 = v14;
            _InterlockedIncrement(v10 + 4);
            v16 = 0;
          }
        }
        else
        {
          v16 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              v13,
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              198);
        }
      }
    }
    else
    {
      v16 = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4783);
    }
  }
  else
  {
    v16 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        168);
  }
  return NormalizeNteStatus(v16);
}

```

## disassembly

```asm
0x180012bb0  mov     [rsp+arg_10], rbx
0x180012bb5  push    rbp
0x180012bb6  push    rdi
0x180012bb7  push    r15
0x180012bb9  sub     rsp, 40h
0x180012bbd  mov     ebp, r9d
0x180012bc0  mov     r15, r8
0x180012bc3  mov     rdi, rdx
0x180012bc6  mov     rbx, rcx
0x180012bc9  test    rcx, rcx
0x180012bcc  jz      short loc_180012BE5
0x180012bce  cmp     dword ptr [rcx], 1B0h
0x180012bd4  jb      short loc_180012BE5
0x180012bd6  cmp     dword ptr [rcx+4], 44444441h
0x180012bdd  jnz     short loc_180012BE5
0x180012bdf  cmp     dword ptr [rcx+0Ch], 0
0x180012be3  jz      short loc_180012BE7
0x180012be5  xor     ebx, ebx
0x180012be7  test    rdx, rdx
0x180012bea  jz      short loc_180012BFA
0x180012bec  cmp     dword ptr [rdx], 20h ; ' '
0x180012bef  jb      short loc_180012BFA
0x180012bf1  cmp     dword ptr [rdx+4], 44444442h
0x180012bf8  jz      short loc_180012BFC
0x180012bfa  xor     edi, edi
0x180012bfc  mov     [rsp+58h+arg_0], rsi
0x180012c01  mov     [rsp+58h+arg_8], r14
0x180012c06  test    rbx, rbx
0x180012c09  jz      loc_180012CF1
0x180012c0f  test    rdi, rdi
0x180012c12  jz      loc_180012CF1
0x180012c18  mov     r14, [rsp+58h+arg_20]
0x180012c20  test    r14, r14
0x180012c23  jz      loc_180012D81
0x180012c29  mov     eax, 5
0x180012c2e  cmp     ax, [rbx+20h]
0x180012c32  ja      loc_180012DA9
0x180012c38  mov     rcx, gs:60h
0x180012c41  xor     edx, edx; Flags
0x180012c43  mov     r8d, 20h ; ' '; Size
0x180012c49  mov     rcx, [rcx+30h]; HeapHandle
0x180012c4d  call    cs:__imp_RtlAllocateHeap
0x180012c53  mov     rsi, rax
0x180012c56  test    rax, rax
0x180012c59  jz      loc_180012D3D
0x180012c5f  mov     ecx, [rsp+58h+arg_30]
0x180012c66  lea     r8, [rax+10h]
0x180012c6a  mov     [rsp+58h+var_28], ecx
0x180012c6e  xorps   xmm0, xmm0
0x180012c71  mov     rcx, [rsp+58h+arg_28]
0x180012c79  mov     r9d, ebp
0x180012c7c  movups  xmmword ptr [rax], xmm0
0x180012c7f  mov     [rsp+58h+var_30], rcx
0x180012c84  movups  xmmword ptr [rax+10h], xmm0
0x180012c88  mov     rdx, [rdi+10h]
0x180012c8c  mov     rcx, [rbx+1A8h]
0x180012c93  mov     rax, [rbx+168h]
0x180012c9a  mov     [rsp+58h+var_38], r8
0x180012c9f  mov     r8, r15
0x180012ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ca7  mov     edi, eax
0x180012ca9  test    eax, eax
0x180012cab  js      loc_180012DD1
0x180012cb1  mov     dword ptr [rsi], 20h ; ' '
0x180012cb7  mov     qword ptr [rsi+4], 44444442h
0x180012cbf  mov     dword ptr [rsi+0Ch], 1
0x180012cc6  mov     [rsi+18h], rbx
0x180012cca  mov     [r14], rsi
0x180012ccd  lock inc dword ptr [rbx+10h]
0x180012cd1  xor     edi, edi
0x180012cd3  mov     ecx, edi
0x180012cd5  mov     r14, [rsp+58h+arg_8]
0x180012cda  mov     rsi, [rsp+58h+arg_0]
0x180012cdf  mov     rbx, [rsp+58h+arg_10]
0x180012ce4  add     rsp, 40h
0x180012ce8  pop     r15
0x180012cea  pop     rdi
0x180012ceb  pop     rbp
0x180012cec  jmp     NormalizeNteStatus
0x180012cf1  mov     edi, 80090026h
0x180012cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cfd  lea     rax, WPP_GLOBAL_Control
0x180012d04  cmp     rcx, rax
0x180012d07  jz      short loc_180012CD3
0x180012d09  test    byte ptr [rcx+1Ch], 1
0x180012d0d  jz      short loc_180012CD3
0x180012d0f  mov     [rsp+58h+var_28], 12A8h
0x180012d17  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012d1e  mov     [rsp+58h+var_30], rax
0x180012d23  mov     dword ptr [rsp+58h+var_38], 80090026h
0x180012d2b  mov     rcx, [rcx+10h]
0x180012d2f  lea     r9, aStatus; "Status"
0x180012d36  call    WPP_SF_sDsd
0x180012d3b  jmp     short loc_180012CD3
0x180012d3d  mov     edi, 8009000Eh
0x180012d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d49  lea     rax, WPP_GLOBAL_Control
0x180012d50  cmp     rcx, rax
0x180012d53  jz      loc_180012CD3
0x180012d59  test    byte ptr [rcx+1Ch], 1
0x180012d5d  jz      loc_180012CD3
0x180012d63  mov     [rsp+58h+var_28], 12C6h
0x180012d6b  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012d72  mov     [rsp+58h+var_30], rax
0x180012d77  mov     dword ptr [rsp+58h+var_38], 8009000Eh
0x180012d7f  jmp     short loc_180012D2B
0x180012d81  mov     r9d, 12AFh
0x180012d87  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012d8e  lea     rdx, aStatus; "Status"
0x180012d95  mov     ecx, 80090027h
0x180012d9a  mov     edi, 80090027h
0x180012d9f  call    DebugTraceError
0x180012da4  jmp     loc_180012CD3
0x180012da9  mov     r9d, 12BAh
0x180012daf  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012db6  lea     rdx, aStatus; "Status"
0x180012dbd  mov     ecx, 80090029h
0x180012dc2  mov     edi, 80090029h
0x180012dc7  call    DebugTraceError
0x180012dcc  jmp     loc_180012CD3
0x180012dd1  mov     r9d, 12D9h
0x180012dd7  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012dde  lea     rdx, aStatus; "Status"
0x180012de5  mov     ecx, eax
0x180012de7  call    DebugTraceError
0x180012dec  mov     rcx, rsi
0x180012def  call    MSCryptFree
0x180012df4  jmp     loc_180012CD3
```
