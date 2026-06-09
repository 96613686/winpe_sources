# HidpCallDriver

- ea: `0x18000a020`
- end: `0x18000a156`
- name: `HidpCallDriver`
- size: `310`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180009d00`
- `0x180009ef8`
- `0x180009fdc`
- `0x18000a264`
- `0x180015b98`
- `0x18001c924`
- `0x180025f64`
- `0x18003b444`
- `0x18003de60`
- `0x18003f2b4`

## callees

- `0x18000a020`
- `0x1800163bc`
- `0x180027c80`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x18000a0ee`
- `ntoskrnl!KeBugCheckEx` at `0x18000a0ee`

## pseudocode

```c
__int64 __fastcall HidpCallDriver(__int64 a1, ULONG_PTR a2)
{
  char v2; // bl
  unsigned __int8 *v3; // rax
  __int64 v4; // rbp
  __int64 v5; // rsi
  int v6; // edx
  unsigned int v7; // edi
  int v8; // r8d

  --*(_BYTE *)(a2 + 67);
  v2 = a2;
  if ( *(char *)(a2 + 67) <= 0 )
    KeBugCheckEx(0x35u, a2, 0, 0, 0);
  *(_QWORD *)(a2 + 184) -= 72LL;
  v3 = *(unsigned __int8 **)(a2 + 184);
  v4 = *v3;
  *((_QWORD *)v3 + 5) = a1;
  v5 = *(_QWORD *)(a1 + 64);
  v7 = (*(__int64 (**)(void))(*(_QWORD *)(v5 + 40) + 8 * v4 + 32))();
  if ( *(_BYTE *)(v5 + 24) )
    v5 = *(_QWORD *)(v5 + 96);
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType);
  if ( (_BYTE)v6 || (_BYTE)v8 )
    WPP_RECORDER_AND_TRACE_SF_qqcd(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v8,
      *(_QWORD *)(v5 + 704),
      5,
      4,
      10,
      (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
      *(_QWORD *)(v5 + 32),
      v2,
      v4,
      v7);
  return v7;
}

```

## disassembly

```asm
0x18000a020  push    rbx
0x18000a022  sub     rsp, 60h
0x18000a026  dec     byte ptr [rdx+43h]
0x18000a029  mov     rbx, rdx
0x18000a02c  movzx   eax, byte ptr [rdx+43h]
0x18000a030  test    al, al
0x18000a032  jle     loc_18000A0DA
0x18000a038  add     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFB8h
0x18000a040  mov     rax, [rdx+0B8h]
0x18000a047  mov     [rsp+68h+arg_0], rbp
0x18000a04c  mov     [rsp+68h+arg_8], rsi
0x18000a051  mov     [rsp+68h+arg_10], rdi
0x18000a059  movzx   ebp, byte ptr [rax]
0x18000a05c  mov     [rax+28h], rcx
0x18000a060  mov     rsi, [rcx+40h]
0x18000a064  mov     rax, [rsi+28h]
0x18000a068  mov     rax, [rax+rbp*8+20h]
0x18000a06d  call    _guard_dispatch_icall
0x18000a072  cmp     byte ptr [rsi+18h], 0
0x18000a076  mov     edi, eax
0x18000a078  jnz     short loc_18000A0D4
0x18000a07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a081  lea     rax, WPP_GLOBAL_Control
0x18000a088  cmp     rcx, rax
0x18000a08b  jz      short loc_18000A094
0x18000a08d  mov     eax, [rcx+2Ch]
0x18000a090  test    al, 8
0x18000a092  jnz     short loc_18000A0FB
0x18000a094  xor     dl, dl; BugCheckParameter1
0x18000a096  lea     rax, WPP_RECORDER_INITIALIZED
0x18000a09d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000a0a4  jz      short loc_18000A0AD
0x18000a0a6  cmp     word ptr [rcx+48h], 0
0x18000a0ab  jnz     short loc_18000A105
0x18000a0ad  xor     r8b, r8b
0x18000a0b0  test    dl, dl
0x18000a0b2  jnz     short loc_18000A10A
0x18000a0b4  test    r8b, r8b
0x18000a0b7  jnz     short loc_18000A10A
0x18000a0b9  mov     rsi, [rsp+68h+arg_8]
0x18000a0be  mov     eax, edi
0x18000a0c0  mov     rdi, [rsp+68h+arg_10]
0x18000a0c8  mov     rbp, [rsp+68h+arg_0]
0x18000a0cd  add     rsp, 60h
0x18000a0d1  pop     rbx
0x18000a0d2  retn
0x18000a0d4  mov     rsi, [rsi+60h]
0x18000a0d8  jmp     short loc_18000A07A
0x18000a0da  xor     r9d, r9d; BugCheckParameter3
0x18000a0dd  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x18000a0e6  xor     r8d, r8d; BugCheckParameter2
0x18000a0e9  mov     ecx, 35h ; '5'; BugCheckCode
0x18000a0ee  call    cs:__imp_KeBugCheckEx
0x18000a0fb  cmp     byte ptr [rcx+29h], 5
0x18000a0ff  jb      short loc_18000A094
0x18000a101  mov     dl, 1
0x18000a103  jmp     short loc_18000A096
0x18000a105  mov     r8b, 1
0x18000a108  jmp     short loc_18000A0B0
0x18000a10a  mov     rax, [rsi+20h]
0x18000a10e  mov     r9, [rsi+2C0h]
0x18000a115  mov     rcx, [rcx+18h]
0x18000a119  mov     [rsp+68h+var_10], edi
0x18000a11d  mov     [rsp+68h+var_18], bpl
0x18000a122  mov     [rsp+68h+var_20], rbx
0x18000a127  mov     [rsp+68h+var_28], rax
0x18000a12c  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18000a133  mov     [rsp+68h+var_30], rax
0x18000a138  mov     [rsp+68h+var_38], 0Ah
0x18000a13f  mov     [rsp+68h+var_40], 4
0x18000a147  mov     byte ptr [rsp+68h+BugCheckParameter4], 5
0x18000a14c  call    WPP_RECORDER_AND_TRACE_SF_qqcd
0x18000a151  jmp     loc_18000A0B9
```
