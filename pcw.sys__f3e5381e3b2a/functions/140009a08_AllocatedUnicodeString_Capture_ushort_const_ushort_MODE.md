# AllocatedUnicodeString::Capture(ushort const *,ushort,_MODE)

- ea: `0x140009a08`
- end: `0x140009b18`
- name: `?Capture@AllocatedUnicodeString@@QEAAJPEBGGW4_MODE@@@Z`
- size: `272`
- prototype: `int(AllocatedUnicodeString *__hidden this, const unsigned __int16 *, unsigned __int16, enum _MODE)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140009d40`
- `0x14000a1e0`
- `0x14000a3c0`
- `0x14000a500`
- `0x14000a7e0`
- `0x14000a9b0`
- `0x14000aa80`
- `0x14000d0b8`

## callees

- `0x1400010c4`
- `0x1400014c0`
- `0x140009a08`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140009a68`
- `ntoskrnl!ExAllocatePool2` at `0x140009a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009abe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009abe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009aee`
- `ntoskrnl!ProbeForRead` at `0x140009a99`
- `ntoskrnl!ProbeForRead` at `0x140009a99`

## pseudocode

```c
__int64 __fastcall AllocatedUnicodeString::Capture(
        AllocatedUnicodeString *this,
        unsigned __int16 *a2,
        __int16 a3,
        enum _MODE a4)
{
  unsigned __int16 v7; // di
  unsigned __int64 v9; // r13
  __int64 v10; // rax
  void *Pool2; // rax
  void *v12; // rsi
  void *v13; // rcx

  v7 = a3 & 0xFFFE;
  if ( (a3 & 0xFFFE) == 0 )
    return 3221225990LL;
  v9 = (unsigned __int64)v7 >> 1;
  v10 = 2 * (v9 + 1);
  if ( !is_mul_ok(v9 + 1, 2u) )
    v10 = -1;
  Pool2 = (void *)ExAllocatePool2(257, v10, 1417110352);
  v12 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  if ( a4 )
  {
    ProbeForRead(a2, v7, 1u);
    RtlCopyFromUser(v12, a2, v7);
  }
  else
  {
    memmove(Pool2, a2, v7);
  }
  *((_WORD *)v12 + v9) = 0;
  v13 = (void *)*((_QWORD *)this + 1);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  *((_QWORD *)this + 1) = v12;
  *(_WORD *)this = v7;
  *((_WORD *)this + 1) = v7;
  return 0;
}

```

## disassembly

```asm
0x140009a08  push    rbx
0x140009a0a  push    rsi
0x140009a0b  push    rdi
0x140009a0c  push    r12
0x140009a0e  push    r13
0x140009a10  push    r14
0x140009a12  push    r15
0x140009a14  sub     rsp, 30h
0x140009a18  mov     r12d, r9d
0x140009a1b  movzx   edi, r8w
0x140009a1f  mov     r14, rdx
0x140009a22  mov     rbx, rcx
0x140009a25  mov     eax, 0FFFEh
0x140009a2a  and     di, ax
0x140009a2d  jnz     short loc_140009A39
0x140009a2f  mov     eax, 0C0000206h
0x140009a34  jmp     loc_140009B07
0x140009a39  movzx   r15d, di
0x140009a3d  mov     r13d, r15d
0x140009a40  shr     r13, 1
0x140009a43  lea     rcx, [r13+1]
0x140009a47  mov     eax, 2
0x140009a4c  mul     rcx
0x140009a4f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140009a56  cmovb   rax, rcx
0x140009a5a  mov     r8d, 54776350h
0x140009a60  mov     rdx, rax
0x140009a63  mov     ecx, 101h
0x140009a68  call    cs:__imp_ExAllocatePool2
0x140009a6f  nop     dword ptr [rax+rax+00h]
0x140009a74  mov     rsi, rax
0x140009a77  mov     [rsp+68h+P], rax
0x140009a7c  test    rax, rax
0x140009a7f  jnz     short loc_140009A88
0x140009a81  mov     eax, 0C000009Ah
0x140009a86  jmp     short loc_140009B07
0x140009a88  test    r12d, r12d
0x140009a8b  jz      short loc_140009ACE
0x140009a8d  mov     r8d, 1; Alignment
0x140009a93  mov     rdx, r15; Length
0x140009a96  mov     rcx, r14; Address
0x140009a99  call    cs:__imp_ProbeForRead
0x140009aa0  nop     dword ptr [rax+rax+00h]
0x140009aa5  mov     r8, r15; Size
0x140009aa8  mov     rdx, r14; Src
0x140009aab  mov     rcx, rsi; void *
0x140009aae  call    RtlCopyFromUser
0x140009ab3  jmp     short loc_140009ADC
0x140009ab5  mov     ebx, eax
0x140009ab7  xor     edx, edx; Tag
0x140009ab9  mov     rcx, [rsp+68h+P]; P
0x140009abe  call    cs:__imp_ExFreePoolWithTag
0x140009ac5  nop     dword ptr [rax+rax+00h]
0x140009aca  mov     eax, ebx
0x140009acc  jmp     short loc_140009B07
0x140009ace  mov     r8, r15; Size
0x140009ad1  mov     rdx, r14; Src
0x140009ad4  mov     rcx, rsi; void *
0x140009ad7  call    memmove
0x140009adc  xor     eax, eax
0x140009ade  mov     [rsi+r13*2], ax
0x140009ae3  mov     rcx, [rbx+8]; P
0x140009ae7  test    rcx, rcx
0x140009aea  jz      short loc_140009AFA
0x140009aec  xor     edx, edx; Tag
0x140009aee  call    cs:__imp_ExFreePoolWithTag
0x140009af5  nop     dword ptr [rax+rax+00h]
0x140009afa  mov     [rbx+8], rsi
0x140009afe  mov     [rbx], di
0x140009b01  mov     [rbx+2], di
0x140009b05  xor     eax, eax
0x140009b07  add     rsp, 30h
0x140009b0b  pop     r15
0x140009b0d  pop     r14
0x140009b0f  pop     r13
0x140009b11  pop     r12
0x140009b13  pop     rdi
0x140009b14  pop     rsi
0x140009b15  pop     rbx
0x140009b16  retn
```
