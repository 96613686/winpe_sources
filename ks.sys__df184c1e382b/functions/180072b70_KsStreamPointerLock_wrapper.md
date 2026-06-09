# KsStreamPointerLock_wrapper

- ea: `0x180072b70`
- end: `0x180072df9`
- name: `KsStreamPointerLock_wrapper`
- size: `649`
- prototype: `__int64 __fastcall(PKSSTREAM_POINTER StreamPointer, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000cb70`
- `0x180019cb0`
- `0x180072b70`
- `0x180075218`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180072bac`
- `ntoskrnl!KeGetCurrentIrql` at `0x180072bac`

## string_xrefs

- `0x180072bef`: `The miniport driver tries to lock a stream pointer that is already locked.`

## pseudocode

```c
__int64 __fastcall KsStreamPointerLock_wrapper(PKSSTREAM_POINTER StreamPointer, __int64 a2, __int64 a3, __int64 a4)
{
  PKSPIN Pin; // rax
  __int64 v5; // rbx
  __int64 v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // r9
  int v11; // [rsp+20h] [rbp-38h]
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  Pin = StreamPointer->Pin;
  v5 = 0;
  v12 = 0;
  v7 = *((_QWORD *)Pin[1].Context + 24);
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() > 2u )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsStreamPointerLock should only be called at IRQL <= DISPATCH_LEVEL.",
      528393);
  if ( (KsXdvExtLevel & 8) != 0 && LODWORD(StreamPointer[-1].Offset) == 1 )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "The miniport driver tries to lock a stream pointer that is already locked.",
      528387);
  if ( (KsXdvExtLevel & 0x18) != 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(KsVerifierUtilTable + 8))(v7);
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 72))(v7);
  }
  if ( (KsXdvExtLevel & 0x10) != 0 && v5 )
  {
    LOBYTE(a4) = 1;
    (*(void (__fastcall **)(__int64, __int64, PKSSTREAM_POINTER, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v5 + 192,
      128,
      StreamPointer,
      a4,
      &v12);
  }
  if ( (KsXdvExtLevel & 0x10) != 0 )
  {
    if ( v5 )
    {
      LOBYTE(a4) = 1;
      LOBYTE(v11) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, PKSSTREAM_POINTER, __int64, int, __int64 *))(KsVerifierUtilTable + 32))(
        *(_QWORD *)(v5 + 192),
        128,
        StreamPointer,
        a4,
        v11,
        &v12);
      if ( v12 )
        SLIC_KsStreamPointerLock_entry_KsInvalidStreamPointer(StreamPointer, v5, &v12);
    }
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 80))(v7);
  v8 = KsStreamPointerLock(StreamPointer);
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 72))(v7);
  if ( (KsXdvExtLevel & 8) != 0 && v5 )
  {
    LOBYTE(v9) = 1;
    (*(void (__fastcall **)(__int64, __int64, PKSSTREAM_POINTER, __int64, __int64 *))(KsVerifierUtilTable + 40))(
      v5 + 184,
      128,
      StreamPointer,
      v9,
      &v12);
  }
  if ( (KsXdvExtLevel & 8) != 0 )
  {
    if ( v5 )
    {
      LOBYTE(v9) = 1;
      LOBYTE(v11) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, PKSSTREAM_POINTER, __int64, int, __int64 *))(KsVerifierUtilTable + 32))(
        *(_QWORD *)(v5 + 184),
        128,
        StreamPointer,
        v9,
        v11,
        &v12);
      if ( v12 )
      {
        *(_QWORD *)(v12 + 112) = StreamPointer;
        if ( v8 )
          (*(void (__fastcall **)(__int64 *, __int64, __int64))(KsVerifierUtilTable + 64))(&v12, 128, v5 + 184);
        else
          *(_BYTE *)(v12 + 120) = 1;
      }
    }
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    (*(void (__fastcall **)(__int64))(KsVerifierUtilTable + 80))(v7);
  return v8;
}

```

## disassembly

```asm
0x180072b70  mov     [rsp+arg_8], rbx
0x180072b75  mov     [rsp+arg_10], rbp
0x180072b7a  push    rsi
0x180072b7b  push    rdi
0x180072b7c  push    r12
0x180072b7e  sub     rsp, 40h
0x180072b82  mov     rax, [rcx+8]
0x180072b86  xor     ebx, ebx
0x180072b88  mov     [rsp+58h+arg_0], 0
0x180072b91  mov     rdi, rcx
0x180072b94  mov     rdx, [rax+98h]
0x180072b9b  mov     eax, cs:KsXdvExtLevel
0x180072ba1  mov     rbp, [rdx+0C0h]
0x180072ba8  test    al, 8
0x180072baa  jz      short loc_180072BD8
0x180072bac  call    cs:__imp_KeGetCurrentIrql
0x180072bb3  nop     dword ptr [rax+rax+00h]
0x180072bb8  cmp     al, 2
0x180072bba  jbe     short loc_180072BD8
0x180072bbc  mov     rax, cs:KsVerifierUtilTable
0x180072bc3  lea     rcx, aKsstreampointe_9; "KsStreamPointerLock should only be call"...
0x180072bca  mov     edx, 81009h
0x180072bcf  mov     rax, [rax+60h]
0x180072bd3  call    _guard_dispatch_icall
0x180072bd8  mov     eax, cs:KsXdvExtLevel
0x180072bde  test    al, 8
0x180072be0  jz      short loc_180072C04
0x180072be2  cmp     dword ptr [rdi-28h], 1
0x180072be6  jnz     short loc_180072C04
0x180072be8  mov     rax, cs:KsVerifierUtilTable
0x180072bef  lea     rcx, aTheMiniportDri_12; "The miniport driver tries to lock a str"...
0x180072bf6  mov     edx, 81003h
0x180072bfb  mov     rax, [rax+60h]
0x180072bff  call    _guard_dispatch_icall
0x180072c04  mov     eax, cs:KsXdvExtLevel
0x180072c0a  test    al, 18h
0x180072c0c  jz      short loc_180072C37
0x180072c0e  mov     rax, cs:KsVerifierUtilTable
0x180072c15  mov     rcx, rbp
0x180072c18  mov     rax, [rax+8]
0x180072c1c  call    _guard_dispatch_icall
0x180072c21  mov     rcx, cs:KsVerifierUtilTable
0x180072c28  mov     rbx, rax
0x180072c2b  mov     rax, [rcx+48h]
0x180072c2f  mov     rcx, rbp
0x180072c32  call    _guard_dispatch_icall
0x180072c37  mov     ecx, cs:KsXdvExtLevel
0x180072c3d  mov     r12d, 80h
0x180072c43  test    cl, 10h
0x180072c46  jz      short loc_180072C77
0x180072c48  test    rbx, rbx
0x180072c4b  jz      short loc_180072C77
0x180072c4d  mov     rax, cs:KsVerifierUtilTable
0x180072c54  lea     rdx, [rsp+58h+arg_0]
0x180072c59  mov     [rsp+58h+var_38], rdx
0x180072c5e  lea     rcx, [rbx+0C0h]
0x180072c65  mov     r9b, 1
0x180072c68  mov     r8, rdi
0x180072c6b  mov     edx, r12d
0x180072c6e  mov     rax, [rax+28h]
0x180072c72  call    _guard_dispatch_icall
0x180072c77  mov     eax, cs:KsXdvExtLevel
0x180072c7d  test    al, 10h
0x180072c7f  jz      short loc_180072CCD
0x180072c81  test    rbx, rbx
0x180072c84  jz      short loc_180072CCD
0x180072c86  mov     rax, cs:KsVerifierUtilTable
0x180072c8d  lea     rcx, [rsp+58h+arg_0]
0x180072c92  mov     [rsp+58h+var_30], rcx
0x180072c97  mov     r9b, 1
0x180072c9a  mov     rcx, [rbx+0C0h]
0x180072ca1  mov     r8, rdi
0x180072ca4  mov     edx, r12d
0x180072ca7  mov     byte ptr [rsp+58h+var_38], 1
0x180072cac  mov     rax, [rax+20h]
0x180072cb0  call    _guard_dispatch_icall
0x180072cb5  cmp     [rsp+58h+arg_0], 0
0x180072cbb  jz      short loc_180072CCD
0x180072cbd  lea     r8, [rsp+58h+arg_0]
0x180072cc2  mov     rdx, rbx
0x180072cc5  mov     rcx, rdi
0x180072cc8  call    SLIC_KsStreamPointerLock_entry_KsInvalidStreamPointer
0x180072ccd  mov     eax, cs:KsXdvExtLevel
0x180072cd3  test    al, 18h
0x180072cd5  jz      short loc_180072CEA
0x180072cd7  mov     rax, cs:KsVerifierUtilTable
0x180072cde  mov     rcx, rbp
0x180072ce1  mov     rax, [rax+50h]
0x180072ce5  call    _guard_dispatch_icall
0x180072cea  mov     rcx, rdi; StreamPointer
0x180072ced  call    KsStreamPointerLock
0x180072cf2  mov     ecx, cs:KsXdvExtLevel
0x180072cf8  mov     esi, eax
0x180072cfa  test    cl, 18h
0x180072cfd  jz      short loc_180072D12
0x180072cff  mov     rcx, cs:KsVerifierUtilTable
0x180072d06  mov     rax, [rcx+48h]
0x180072d0a  mov     rcx, rbp
0x180072d0d  call    _guard_dispatch_icall
0x180072d12  mov     ecx, cs:KsXdvExtLevel
0x180072d18  test    cl, 8
0x180072d1b  jz      short loc_180072D4C
0x180072d1d  test    rbx, rbx
0x180072d20  jz      short loc_180072D4C
0x180072d22  mov     rax, cs:KsVerifierUtilTable
0x180072d29  lea     rdx, [rsp+58h+arg_0]
0x180072d2e  mov     [rsp+58h+var_38], rdx
0x180072d33  lea     rcx, [rbx+0B8h]
0x180072d3a  mov     r9b, 1
0x180072d3d  mov     r8, rdi
0x180072d40  mov     edx, r12d
0x180072d43  mov     rax, [rax+28h]
0x180072d47  call    _guard_dispatch_icall
0x180072d4c  mov     eax, cs:KsXdvExtLevel
0x180072d52  test    al, 8
0x180072d54  jz      short loc_180072DC6
0x180072d56  test    rbx, rbx
0x180072d59  jz      short loc_180072DC6
0x180072d5b  mov     rax, cs:KsVerifierUtilTable
0x180072d62  lea     rcx, [rsp+58h+arg_0]
0x180072d67  mov     [rsp+58h+var_30], rcx
0x180072d6c  mov     r9b, 1
0x180072d6f  mov     rcx, [rbx+0B8h]
0x180072d76  mov     r8, rdi
0x180072d79  mov     edx, r12d
0x180072d7c  mov     byte ptr [rsp+58h+var_38], 1
0x180072d81  mov     rax, [rax+20h]
0x180072d85  call    _guard_dispatch_icall
0x180072d8a  mov     rax, [rsp+58h+arg_0]
0x180072d8f  test    rax, rax
0x180072d92  jz      short loc_180072DC6
0x180072d94  mov     [rax+70h], rdi
0x180072d98  test    esi, esi
0x180072d9a  jnz     short loc_180072DA7
0x180072d9c  mov     rax, [rsp+58h+arg_0]
0x180072da1  mov     byte ptr [rax+78h], 1
0x180072da5  jmp     short loc_180072DC6
0x180072da7  mov     rax, cs:KsVerifierUtilTable
0x180072dae  lea     r8, [rbx+0B8h]
0x180072db5  mov     edx, r12d
0x180072db8  lea     rcx, [rsp+58h+arg_0]
0x180072dbd  mov     rax, [rax+40h]
0x180072dc1  call    _guard_dispatch_icall
0x180072dc6  mov     eax, cs:KsXdvExtLevel
0x180072dcc  test    al, 18h
0x180072dce  jz      short loc_180072DE3
0x180072dd0  mov     rax, cs:KsVerifierUtilTable
0x180072dd7  mov     rcx, rbp
0x180072dda  mov     rax, [rax+50h]
0x180072dde  call    _guard_dispatch_icall
0x180072de3  mov     rbx, [rsp+58h+arg_8]
0x180072de8  mov     eax, esi
0x180072dea  mov     rbp, [rsp+58h+arg_10]
0x180072def  add     rsp, 40h
0x180072df3  pop     r12
0x180072df5  pop     rdi
0x180072df6  pop     rsi
0x180072df7  retn
```
