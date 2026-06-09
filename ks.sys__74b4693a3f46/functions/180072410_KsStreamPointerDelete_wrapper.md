# KsStreamPointerDelete_wrapper

- ea: `0x180072410`
- end: `0x180072705`
- name: `KsStreamPointerDelete_wrapper`
- size: `757`
- prototype: `__int64 __fastcall(PKSSTREAM_POINTER StreamPointer)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180007000`
- `0x180019c60`
- `0x180072410`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18007244d`
- `ntoskrnl!KeGetCurrentIrql` at `0x18007244d`

## string_xrefs

- `0x1800725ca`: `The miniport driver tries to delete a stream pointer that is not cloned.`
- `0x1800726b0`: `The miniport driver tries to delete a stream pointer that is not cloned.`
- `0x180072464`: `KsStreamPointerDelete should only be called at IRQL <= DISPATCH_LEVEL.`

## pseudocode

```c
void __fastcall KsStreamPointerDelete_wrapper(PKSSTREAM_POINTER StreamPointer, __int64 a2, __int64 a3, __int64 a4)
{
  PKSPIN Pin; // rax
  _QWORD *v5; // rbx
  __int64 v7; // r14
  __int64 v8; // r9
  _QWORD *v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+20h] [rbp-28h]
  __int64 v11; // [rsp+80h] [rbp+38h] BYREF

  Pin = StreamPointer->Pin;
  v5 = 0;
  v11 = 0;
  v7 = *((_QWORD *)Pin[1].Context + 24);
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() > 2u )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsStreamPointerDelete should only be called at IRQL <= DISPATCH_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v5 = (_QWORD *)(*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 8))(v7);
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 72))(v7);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(a4) = 1;
    (*(void (__fastcall **)(_QWORD *, __int64, PKSSTREAM_POINTER, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v5 + 22,
      128,
      StreamPointer,
      a4,
      &v11);
  }
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(a4) = 1;
    LOBYTE(v9) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PKSSTREAM_POINTER, __int64, _DWORD, __int64 *))(KsVerifierUtilTable + 32))(
      v5[23],
      128,
      StreamPointer,
      a4,
      (_DWORD)v9,
      &v11);
    if ( v11 )
      (*(void (__fastcall **)(__int64 *, __int64, _QWORD *))(KsVerifierUtilTable + 64))(&v11, 128, v5 + 23);
    LOBYTE(v8) = 1;
    LOBYTE(v10) = 1;
    (*(void (__fastcall **)(_QWORD, __int64, PKSSTREAM_POINTER, __int64, int, __int64 *))(KsVerifierUtilTable + 32))(
      v5[22],
      128,
      StreamPointer,
      v8,
      v10,
      &v11);
    a4 = v11;
    if ( v11 )
    {
      if ( *(_BYTE *)(v11 + 120) == 1 )
      {
        *(_BYTE *)(v11 + 120) = 0;
        *(_QWORD *)(v11 + 112) = 0;
        (*(void (__fastcall **)(__int64 *, __int64, _QWORD *))(KsVerifierUtilTable + 64))(&v11, 128, v5 + 22);
      }
      else
      {
        v9 = v5 + 22;
        (*(void (__fastcall **)(const char *, __int64, _QWORD *))(KsVerifierUtilTable + 88))(
          "The miniport driver tries to delete a stream pointer that is not cloned.",
          528386,
          v5);
      }
    }
  }
  if ( (KsXdvExtLevel & 0x10) != 0 && v5 )
  {
    LOBYTE(a4) = 1;
    (*(void (__fastcall **)(_QWORD *, __int64, PKSSTREAM_POINTER, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v5 + 24,
      128,
      StreamPointer,
      a4,
      &v11);
  }
  if ( (KsXdvExtLevel & 0x10) != 0 )
  {
    if ( v5 )
    {
      LOBYTE(a4) = 1;
      LOBYTE(v9) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, PKSSTREAM_POINTER, __int64, _QWORD *, __int64 *))(KsVerifierUtilTable + 32))(
        v5[24],
        128,
        StreamPointer,
        a4,
        v9,
        &v11);
      if ( v11 )
      {
        if ( *(_BYTE *)(v11 + 120) == 1 )
        {
          *(_BYTE *)(v11 + 120) = 0;
          *(_QWORD *)(v11 + 112) = 0;
          (*(void (__fastcall **)(__int64 *, __int64, _QWORD *))(KsVerifierUtilTable + 64))(&v11, 128, v5 + 24);
        }
        else
        {
          (*(void (__fastcall **)(const char *, __int64, _QWORD *))(KsVerifierUtilTable + 88))(
            "The miniport driver tries to delete a stream pointer that is not cloned.",
            528396,
            v5);
        }
      }
    }
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 80))(v7);
  KsStreamPointerDelete(StreamPointer);
}

```

## disassembly

```asm
0x180072410  push    rbp
0x180072412  push    rbx
0x180072413  push    rsi
0x180072414  push    rdi
0x180072415  push    r12
0x180072417  push    r14
0x180072419  mov     rbp, rsp
0x18007241c  sub     rsp, 48h
0x180072420  mov     rax, [rcx+8]
0x180072424  xor     ebx, ebx
0x180072426  mov     [rbp+arg_0], 0
0x18007242e  mov     sil, 8
0x180072431  mov     rdi, rcx
0x180072434  mov     rdx, [rax+98h]
0x18007243b  mov     eax, cs:KsXdvExtLevel
0x180072441  mov     r14, [rdx+0C0h]
0x180072448  test    sil, al
0x18007244b  jz      short loc_180072479
0x18007244d  call    cs:__imp_KeGetCurrentIrql
0x180072454  nop     dword ptr [rax+rax+00h]
0x180072459  cmp     al, 2
0x18007245b  jbe     short loc_180072479
0x18007245d  mov     rax, cs:KsVerifierUtilTable
0x180072464  lea     rcx, aKsstreampointe_1; "KsStreamPointerDelete should only be ca"...
0x18007246b  mov     edx, 81009h
0x180072470  mov     rax, [rax+60h]
0x180072474  call    _guard_dispatch_icall
0x180072479  mov     eax, cs:KsXdvExtLevel
0x18007247f  test    al, 18h
0x180072481  jz      short loc_1800724AC
0x180072483  mov     rax, cs:KsVerifierUtilTable
0x18007248a  mov     rcx, r14
0x18007248d  mov     rax, [rax+8]
0x180072491  call    _guard_dispatch_icall
0x180072496  mov     rcx, cs:KsVerifierUtilTable
0x18007249d  mov     rbx, rax
0x1800724a0  mov     rax, [rcx+48h]
0x1800724a4  mov     rcx, r14
0x1800724a7  call    _guard_dispatch_icall
0x1800724ac  mov     ecx, cs:KsXdvExtLevel
0x1800724b2  mov     r12d, 80h
0x1800724b8  test    sil, cl
0x1800724bb  jz      short loc_1800724EB
0x1800724bd  test    rbx, rbx
0x1800724c0  jz      short loc_1800724EB
0x1800724c2  mov     rax, cs:KsVerifierUtilTable
0x1800724c9  lea     rdx, [rbp+arg_0]
0x1800724cd  mov     [rsp+48h+var_28], rdx
0x1800724d2  lea     rcx, [rbx+0B0h]
0x1800724d9  mov     r9b, 1
0x1800724dc  mov     r8, rdi
0x1800724df  mov     edx, r12d
0x1800724e2  mov     rax, [rax+28h]
0x1800724e6  call    _guard_dispatch_icall
0x1800724eb  mov     eax, cs:KsXdvExtLevel
0x1800724f1  test    sil, al
0x1800724f4  jz      loc_1800725EC
0x1800724fa  test    rbx, rbx
0x1800724fd  jz      loc_1800725EC
0x180072503  mov     rax, cs:KsVerifierUtilTable
0x18007250a  lea     rcx, [rbp+arg_0]
0x18007250e  mov     [rsp+48h+var_20], rcx
0x180072513  lea     rsi, [rbx+0B8h]
0x18007251a  mov     rcx, [rsi]
0x18007251d  mov     r9b, 1
0x180072520  mov     r8, rdi
0x180072523  mov     byte ptr [rsp+48h+var_28], 1
0x180072528  mov     rax, [rax+20h]
0x18007252c  mov     edx, r12d
0x18007252f  call    _guard_dispatch_icall
0x180072534  cmp     [rbp+arg_0], 0
0x180072539  jz      short loc_180072555
0x18007253b  mov     rax, cs:KsVerifierUtilTable
0x180072542  lea     rcx, [rbp+arg_0]
0x180072546  mov     r8, rsi
0x180072549  mov     edx, r12d
0x18007254c  mov     rax, [rax+40h]
0x180072550  call    _guard_dispatch_icall
0x180072555  mov     rax, cs:KsVerifierUtilTable
0x18007255c  lea     rcx, [rbp+arg_0]
0x180072560  mov     [rsp+48h+var_20], rcx
0x180072565  lea     rsi, [rbx+0B0h]
0x18007256c  mov     rcx, [rsi]
0x18007256f  mov     r9b, 1
0x180072572  mov     r8, rdi
0x180072575  mov     byte ptr [rsp+48h+var_28], 1
0x18007257a  mov     rax, [rax+20h]
0x18007257e  mov     edx, r12d
0x180072581  call    _guard_dispatch_icall
0x180072586  mov     r9, [rbp+arg_0]
0x18007258a  test    r9, r9
0x18007258d  jz      short loc_1800725EC
0x18007258f  cmp     byte ptr [r9+78h], 1
0x180072594  jnz     short loc_1800725C3
0x180072596  mov     byte ptr [r9+78h], 0
0x18007259b  lea     rcx, [rbp+arg_0]
0x18007259f  mov     rax, [rbp+arg_0]
0x1800725a3  mov     r8, rsi
0x1800725a6  mov     edx, r12d
0x1800725a9  mov     qword ptr [rax+70h], 0
0x1800725b1  mov     rax, cs:KsVerifierUtilTable
0x1800725b8  mov     rax, [rax+40h]
0x1800725bc  call    _guard_dispatch_icall
0x1800725c1  jmp     short loc_1800725EC
0x1800725c3  mov     rax, cs:KsVerifierUtilTable
0x1800725ca  lea     rcx, aTheMiniportDri_4; "The miniport driver tries to delete a s"...
0x1800725d1  mov     dword ptr [rsp+48h+var_20], r12d
0x1800725d6  mov     r8, rbx
0x1800725d9  mov     edx, 81002h
0x1800725de  mov     [rsp+48h+var_28], rsi
0x1800725e3  mov     rax, [rax+58h]
0x1800725e7  call    _guard_dispatch_icall
0x1800725ec  mov     eax, cs:KsXdvExtLevel
0x1800725f2  test    al, 10h
0x1800725f4  jz      short loc_180072624
0x1800725f6  test    rbx, rbx
0x1800725f9  jz      short loc_180072624
0x1800725fb  mov     rax, cs:KsVerifierUtilTable
0x180072602  lea     rdx, [rbp+arg_0]
0x180072606  mov     [rsp+48h+var_28], rdx
0x18007260b  lea     rcx, [rbx+0C0h]
0x180072612  mov     r9b, 1
0x180072615  mov     r8, rdi
0x180072618  mov     edx, r12d
0x18007261b  mov     rax, [rax+28h]
0x18007261f  call    _guard_dispatch_icall
0x180072624  mov     eax, cs:KsXdvExtLevel
0x18007262a  test    al, 10h
0x18007262c  jz      loc_1800726D2
0x180072632  test    rbx, rbx
0x180072635  jz      loc_1800726D2
0x18007263b  mov     rax, cs:KsVerifierUtilTable
0x180072642  lea     rcx, [rbp+arg_0]
0x180072646  mov     [rsp+48h+var_20], rcx
0x18007264b  lea     rsi, [rbx+0C0h]
0x180072652  mov     rcx, [rsi]
0x180072655  mov     r9b, 1
0x180072658  mov     r8, rdi
0x18007265b  mov     byte ptr [rsp+48h+var_28], 1
0x180072660  mov     rax, [rax+20h]
0x180072664  mov     edx, r12d
0x180072667  call    _guard_dispatch_icall
0x18007266c  mov     r9, [rbp+arg_0]
0x180072670  test    r9, r9
0x180072673  jz      short loc_1800726D2
0x180072675  cmp     byte ptr [r9+78h], 1
0x18007267a  jnz     short loc_1800726A9
0x18007267c  mov     byte ptr [r9+78h], 0
0x180072681  lea     rcx, [rbp+arg_0]
0x180072685  mov     rax, [rbp+arg_0]
0x180072689  mov     r8, rsi
0x18007268c  mov     edx, r12d
0x18007268f  mov     qword ptr [rax+70h], 0
0x180072697  mov     rax, cs:KsVerifierUtilTable
0x18007269e  mov     rax, [rax+40h]
0x1800726a2  call    _guard_dispatch_icall
0x1800726a7  jmp     short loc_1800726D2
0x1800726a9  mov     rax, cs:KsVerifierUtilTable
0x1800726b0  lea     rcx, aTheMiniportDri_4; "The miniport driver tries to delete a s"...
0x1800726b7  mov     dword ptr [rsp+48h+var_20], r12d
0x1800726bc  mov     r8, rbx
0x1800726bf  mov     edx, 8100Ch
0x1800726c4  mov     [rsp+48h+var_28], rsi
0x1800726c9  mov     rax, [rax+58h]
0x1800726cd  call    _guard_dispatch_icall
0x1800726d2  mov     eax, cs:KsXdvExtLevel
0x1800726d8  test    al, 18h
0x1800726da  jz      short loc_1800726EF
0x1800726dc  mov     rax, cs:KsVerifierUtilTable
0x1800726e3  mov     rcx, r14
0x1800726e6  mov     rax, [rax+50h]
0x1800726ea  call    _guard_dispatch_icall
0x1800726ef  mov     rcx, rdi; StreamPointer
0x1800726f2  call    KsStreamPointerDelete
0x1800726f7  add     rsp, 48h
0x1800726fb  pop     r14
0x1800726fd  pop     r12
0x1800726ff  pop     rdi
0x180072700  pop     rsi
0x180072701  pop     rbx
0x180072702  pop     rbp
0x180072703  retn
```
