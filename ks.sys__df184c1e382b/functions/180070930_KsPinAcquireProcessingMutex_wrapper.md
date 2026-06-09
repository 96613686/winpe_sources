# KsPinAcquireProcessingMutex_wrapper

- ea: `0x180070930`
- end: `0x180070c31`
- name: `KsPinAcquireProcessingMutex_wrapper`
- size: `769`
- prototype: `__int64 __fastcall(PKSPIN Pin, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019cb0`
- `0x18004d710`
- `0x180070930`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18007096a`
- `ntoskrnl!KeGetCurrentIrql` at `0x18007096a`

## string_xrefs

- `0x180070a3f`: `The driver attempts to acquire the processing mutex while holding it. This operation will cause a deadlock.`

## pseudocode

```c
__int64 __fastcall KsPinAcquireProcessingMutex_wrapper(PKSPIN Pin, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *Context; // rax
  __int64 v5; // rdi
  __int64 v7; // r14
  __int64 v8; // r9
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // rbx
  __int64 result; // rax
  __int64 v13; // [rsp+20h] [rbp-20h]
  char v14; // [rsp+20h] [rbp-20h]
  int v15; // [rsp+20h] [rbp-20h]
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF

  Context = Pin[1].Context;
  v5 = 0;
  v16 = 0;
  v7 = Context[24];
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsPinAcquireProcessingMutex should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 8))(v7);
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 72))(v7);
  }
  if ( (KsXdvExtLevel & 8) != 0 )
  {
    if ( v5 )
    {
      LOBYTE(a4) = 1;
      v14 = 1;
      (*(void (__fastcall **)(_QWORD, __int64, PKSPIN, __int64, char, __int64 *))(KsVerifierUtilTable + 32))(
        *(_QWORD *)(v5 + 160),
        136,
        Pin,
        a4,
        v14,
        &v16);
      if ( v16 )
      {
        if ( *(struct _KTHREAD **)(v16 + 112) == KeGetCurrentThread() && *(_BYTE *)(v16 + 128) == 1 )
        {
          v13 = v5 + 160;
          (*(void (__fastcall **)(const char *, __int64, __int64))(KsVerifierUtilTable + 88))(
            "The driver attempts to acquire the processing mutex while holding it. This operation will cause a deadlock.",
            528395,
            v5);
        }
      }
    }
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 80))(v7);
  KsPinAcquireProcessingMutex(Pin);
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 72))(v7);
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(v8) = 1;
    (*(void (__fastcall **)(__int64, __int64, PKSPIN, __int64, __int64 *))(KsVerifierUtilTable + 24))(
      v5 + 144,
      144,
      Pin,
      v8,
      &v16);
    LOBYTE(v9) = 1;
    (*(void (__fastcall **)(__int64, __int64, PKSPIN, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v5 + 160,
      136,
      Pin,
      v9,
      &v16);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(v8) = 1;
    LOBYTE(v13) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PKSPIN, __int64, __int64, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v5 + 144),
      144,
      Pin,
      v8,
      v13,
      &v16);
    if ( v16 )
    {
      *(_QWORD *)(v16 + 120) = Pin;
      *(_BYTE *)(v16 + 128) = 1;
      *(_QWORD *)(v16 + 112) = KeGetCurrentThread();
      *(_DWORD *)(v16 + 136) = XDV_KS_PROCESSING_MUTEX_TIMELIMIT;
      v11 = v16;
      *(_DWORD *)(v11 + 132) = (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 120))(3);
    }
    LOBYTE(v10) = 1;
    LOBYTE(v15) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PKSPIN, __int64, int, __int64 *))(KsVerifierUtilTable + 32))(
      *(_QWORD *)(v5 + 160),
      136,
      Pin,
      v10,
      v15,
      &v16);
    if ( v16 )
    {
      *(_QWORD *)(v16 + 120) = Pin;
      *(_BYTE *)(v16 + 128) = 1;
      *(_QWORD *)(v16 + 112) = KeGetCurrentThread();
    }
  }
  result = (unsigned int)KsXdvExtLevel;
  if ( (KsXdvExtLevel & 0x18) != 0 )
    return (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 80))(v7);
  return result;
}

```

## disassembly

```asm
0x180070930  mov     [rsp-18h+arg_8], rbx
0x180070935  mov     [rsp-18h+arg_10], rsi
0x18007093a  push    rbp
0x18007093b  push    rdi
0x18007093c  push    r14
0x18007093e  mov     rbp, rsp
0x180070941  sub     rsp, 40h
0x180070945  mov     rax, [rcx+98h]
0x18007094c  xor     edi, edi
0x18007094e  mov     [rbp+arg_0], 0
0x180070956  mov     rsi, rcx
0x180070959  mov     r14, [rax+0C0h]
0x180070960  mov     eax, cs:KsXdvExtLevel
0x180070966  test    al, 8
0x180070968  jz      short loc_180070996
0x18007096a  call    cs:__imp_KeGetCurrentIrql
0x180070971  nop     dword ptr [rax+rax+00h]
0x180070976  test    al, al
0x180070978  jz      short loc_180070996
0x18007097a  mov     rax, cs:KsVerifierUtilTable
0x180070981  lea     rcx, aKspinacquirepr; "KsPinAcquireProcessingMutex should only"...
0x180070988  mov     edx, 81009h
0x18007098d  mov     rax, [rax+60h]
0x180070991  call    _guard_dispatch_icall
0x180070996  mov     eax, cs:KsXdvExtLevel
0x18007099c  test    al, 18h
0x18007099e  jz      short loc_1800709C9
0x1800709a0  mov     rax, cs:KsVerifierUtilTable
0x1800709a7  mov     rcx, r14
0x1800709aa  mov     rax, [rax+8]
0x1800709ae  call    _guard_dispatch_icall
0x1800709b3  mov     rcx, cs:KsVerifierUtilTable
0x1800709ba  mov     rdi, rax
0x1800709bd  mov     rax, [rcx+48h]
0x1800709c1  mov     rcx, r14
0x1800709c4  call    _guard_dispatch_icall
0x1800709c9  mov     ecx, cs:KsXdvExtLevel
0x1800709cf  test    cl, 8
0x1800709d2  jz      loc_180070A64
0x1800709d8  test    rdi, rdi
0x1800709db  jz      loc_180070A64
0x1800709e1  mov     rax, cs:KsVerifierUtilTable
0x1800709e8  lea     rcx, [rbp+arg_0]
0x1800709ec  mov     [rsp+40h+var_18], rcx
0x1800709f1  lea     rbx, [rdi+0A0h]
0x1800709f8  mov     rcx, [rbx]
0x1800709fb  mov     r9b, 1
0x1800709fe  mov     r8, rsi
0x180070a01  mov     byte ptr [rsp+40h+var_20], 1
0x180070a06  mov     rax, [rax+20h]
0x180070a0a  mov     edx, 88h
0x180070a0f  call    _guard_dispatch_icall
0x180070a14  cmp     [rbp+arg_0], 0
0x180070a19  jz      short loc_180070A64
0x180070a1b  mov     rax, gs:188h
0x180070a24  mov     r9, [rbp+arg_0]
0x180070a28  cmp     [r9+70h], rax
0x180070a2c  jnz     short loc_180070A64
0x180070a2e  cmp     byte ptr [r9+80h], 1
0x180070a36  jnz     short loc_180070A64
0x180070a38  mov     rax, cs:KsVerifierUtilTable
0x180070a3f  lea     rcx, aTheDriverAttem_2; "The driver attempts to acquire the proc"...
0x180070a46  mov     dword ptr [rsp+40h+var_18], 88h
0x180070a4e  mov     r8, rdi
0x180070a51  mov     edx, 8100Bh
0x180070a56  mov     [rsp+40h+var_20], rbx
0x180070a5b  mov     rax, [rax+58h]
0x180070a5f  call    _guard_dispatch_icall
0x180070a64  mov     eax, cs:KsXdvExtLevel
0x180070a6a  test    al, 18h
0x180070a6c  jz      short loc_180070A81
0x180070a6e  mov     rax, cs:KsVerifierUtilTable
0x180070a75  mov     rcx, r14
0x180070a78  mov     rax, [rax+50h]
0x180070a7c  call    _guard_dispatch_icall
0x180070a81  mov     rcx, rsi; Pin
0x180070a84  call    KsPinAcquireProcessingMutex
0x180070a89  mov     eax, cs:KsXdvExtLevel
0x180070a8f  test    al, 18h
0x180070a91  jz      short loc_180070AA6
0x180070a93  mov     rax, cs:KsVerifierUtilTable
0x180070a9a  mov     rcx, r14
0x180070a9d  mov     rax, [rax+48h]
0x180070aa1  call    _guard_dispatch_icall
0x180070aa6  mov     eax, cs:KsXdvExtLevel
0x180070aac  mov     ebx, 90h
0x180070ab1  test    al, 8
0x180070ab3  jz      short loc_180070B0B
0x180070ab5  test    rdi, rdi
0x180070ab8  jz      short loc_180070B0B
0x180070aba  mov     rax, cs:KsVerifierUtilTable
0x180070ac1  lea     rdx, [rbp+arg_0]
0x180070ac5  mov     [rsp+40h+var_20], rdx
0x180070aca  lea     rcx, [rdi+90h]
0x180070ad1  mov     r9b, 1
0x180070ad4  mov     r8, rsi
0x180070ad7  mov     edx, ebx
0x180070ad9  mov     rax, [rax+18h]
0x180070add  call    _guard_dispatch_icall
0x180070ae2  mov     rax, cs:KsVerifierUtilTable
0x180070ae9  lea     rdx, [rbp+arg_0]
0x180070aed  mov     [rsp+40h+var_20], rdx
0x180070af2  lea     rcx, [rdi+0A0h]
0x180070af9  mov     r9b, 1
0x180070afc  lea     edx, [rbx-8]
0x180070aff  mov     r8, rsi
0x180070b02  mov     rax, [rax+28h]
0x180070b06  call    _guard_dispatch_icall
0x180070b0b  mov     eax, cs:KsXdvExtLevel
0x180070b11  test    al, 8
0x180070b13  jz      loc_180070C00
0x180070b19  test    rdi, rdi
0x180070b1c  jz      loc_180070C00
0x180070b22  mov     rax, cs:KsVerifierUtilTable
0x180070b29  lea     rcx, [rbp+arg_0]
0x180070b2d  mov     [rsp+40h+var_18], rcx
0x180070b32  mov     r9b, 1
0x180070b35  mov     rcx, [rdi+90h]
0x180070b3c  mov     r8, rsi
0x180070b3f  mov     edx, ebx
0x180070b41  mov     byte ptr [rsp+40h+var_20], 1
0x180070b46  mov     rax, [rax+20h]
0x180070b4a  call    _guard_dispatch_icall
0x180070b4f  mov     rax, [rbp+arg_0]
0x180070b53  test    rax, rax
0x180070b56  jz      short loc_180070BA7
0x180070b58  mov     [rax+78h], rsi
0x180070b5c  mov     rax, [rbp+arg_0]
0x180070b60  mov     byte ptr [rax+80h], 1
0x180070b67  mov     rcx, gs:188h
0x180070b70  mov     rax, [rbp+arg_0]
0x180070b74  mov     [rax+70h], rcx
0x180070b78  mov     rcx, [rbp+arg_0]
0x180070b7c  mov     eax, cs:XDV_KS_PROCESSING_MUTEX_TIMELIMIT
0x180070b82  mov     [rcx+88h], eax
0x180070b88  mov     ecx, 3
0x180070b8d  mov     rax, cs:KsVerifierUtilTable
0x180070b94  mov     rbx, [rbp+arg_0]
0x180070b98  mov     rax, [rax+78h]
0x180070b9c  call    _guard_dispatch_icall
0x180070ba1  mov     [rbx+84h], eax
0x180070ba7  mov     rax, cs:KsVerifierUtilTable
0x180070bae  lea     rcx, [rbp+arg_0]
0x180070bb2  mov     [rsp+40h+var_18], rcx
0x180070bb7  mov     r9b, 1
0x180070bba  mov     rcx, [rdi+0A0h]
0x180070bc1  mov     r8, rsi
0x180070bc4  mov     edx, 88h
0x180070bc9  mov     byte ptr [rsp+40h+var_20], 1
0x180070bce  mov     rax, [rax+20h]
0x180070bd2  call    _guard_dispatch_icall
0x180070bd7  mov     rax, [rbp+arg_0]
0x180070bdb  test    rax, rax
0x180070bde  jz      short loc_180070C00
0x180070be0  mov     [rax+78h], rsi
0x180070be4  mov     rax, [rbp+arg_0]
0x180070be8  mov     byte ptr [rax+80h], 1
0x180070bef  mov     rdx, gs:188h
0x180070bf8  mov     rax, [rbp+arg_0]
0x180070bfc  mov     [rax+70h], rdx
0x180070c00  mov     eax, cs:KsXdvExtLevel
0x180070c06  test    al, 18h
0x180070c08  jz      short loc_180070C1D
0x180070c0a  mov     rax, cs:KsVerifierUtilTable
0x180070c11  mov     rcx, r14
0x180070c14  mov     rax, [rax+50h]
0x180070c18  call    _guard_dispatch_icall
0x180070c1d  mov     rbx, [rsp+40h+arg_8]
0x180070c22  mov     rsi, [rsp+40h+arg_10]
0x180070c27  add     rsp, 40h
0x180070c2b  pop     r14
0x180070c2d  pop     rdi
0x180070c2e  pop     rbp
0x180070c2f  retn
```
