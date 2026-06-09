# KerbGetContextToken

- ea: `0x140030100`
- end: `0x1400301dc`
- name: `KerbGetContextToken`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140025df0`
- `0x140025e28`
- `0x140030100`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14003016a`
- `ntoskrnl!ExGetPreviousMode` at `0x14003016a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003019a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003019a`

## pseudocode

```c
__int64 __fastcall KerbGetContextToken(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rbx
  __int64 v8; // rax
  NTSTATUS v9; // ebp
  KPROCESSOR_MODE PreviousMode; // al
  void *v11; // rcx
  PVOID Object; // [rsp+58h] [rbp+20h] BYREF

  v5 = KerbReferenceContext(a1, 0);
  v6 = (_QWORD *)v5;
  if ( !v5 )
    return 3221225480LL;
  v8 = *(_QWORD *)(v5 + 104);
  if ( v8 )
  {
    v9 = 0;
    if ( a2 )
      *a2 = v8;
    if ( a3 )
    {
      if ( !v6[13]
        || v6[12]
        || (PreviousMode = ExGetPreviousMode(),
            v11 = (void *)v6[13],
            Object = 0,
            v9 = ObReferenceObjectByHandle(v11, 4u, 0, PreviousMode, &Object, 0),
            v6[12] = Object,
            v9 >= 0) )
      {
        *a3 = v6[12];
      }
    }
  }
  else
  {
    v9 = -2146893045;
  }
  KerbDereferenceContext(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140030100  mov     [rsp+arg_8], rbx
0x140030105  mov     [rsp+arg_10], rsi
0x14003010a  push    rdi
0x14003010b  sub     rsp, 30h
0x14003010f  mov     rdi, rdx
0x140030112  mov     rsi, r8
0x140030115  xor     edx, edx
0x140030117  call    KerbReferenceContext
0x14003011c  mov     rbx, rax
0x14003011f  test    rax, rax
0x140030122  jnz     short loc_14003013A
0x140030124  mov     eax, 0C0000008h
0x140030129  mov     rbx, [rsp+38h+arg_8]
0x14003012e  mov     rsi, [rsp+38h+arg_10]
0x140030133  add     rsp, 30h
0x140030137  pop     rdi
0x140030138  retn
0x14003013a  mov     rax, [rax+68h]
0x14003013e  mov     [rsp+38h+arg_0], rbp
0x140030143  test    rax, rax
0x140030146  jnz     short loc_14003014F
0x140030148  mov     ebp, 8009030Bh
0x14003014d  jmp     short loc_1400301BC
0x14003014f  xor     ebp, ebp
0x140030151  test    rdi, rdi
0x140030154  jz      short loc_140030159
0x140030156  mov     [rdi], rax
0x140030159  test    rsi, rsi
0x14003015c  jz      short loc_1400301BC
0x14003015e  cmp     [rbx+68h], rbp
0x140030162  jz      short loc_1400301B5
0x140030164  cmp     [rbx+60h], rbp
0x140030168  jnz     short loc_1400301B5
0x14003016a  call    cs:__imp_ExGetPreviousMode
0x140030171  nop     dword ptr [rax+rax+00h]
0x140030176  lea     rcx, [rsp+38h+arg_18]
0x14003017b  mov     [rsp+38h+HandleInformation], rbp; HandleInformation
0x140030180  mov     [rsp+38h+Object], rcx; Object
0x140030185  movzx   r9d, al; AccessMode
0x140030189  mov     rcx, [rbx+68h]; Handle
0x14003018d  xor     r8d, r8d; ObjectType
0x140030190  mov     edx, 4; DesiredAccess
0x140030195  mov     [rsp+38h+arg_18], rbp
0x14003019a  call    cs:__imp_ObReferenceObjectByHandle
0x1400301a1  nop     dword ptr [rax+rax+00h]
0x1400301a6  mov     rcx, [rsp+38h+arg_18]
0x1400301ab  mov     ebp, eax
0x1400301ad  mov     [rbx+60h], rcx
0x1400301b1  test    eax, eax
0x1400301b3  js      short loc_1400301BC
0x1400301b5  mov     rcx, [rbx+60h]
0x1400301b9  mov     [rsi], rcx
0x1400301bc  mov     rcx, rbx; P
0x1400301bf  call    KerbDereferenceContext
0x1400301c4  mov     rbx, [rsp+38h+arg_8]
0x1400301c9  mov     eax, ebp
0x1400301cb  mov     rbp, [rsp+38h+arg_0]
0x1400301d0  mov     rsi, [rsp+38h+arg_10]
0x1400301d5  add     rsp, 30h
0x1400301d9  pop     rdi
0x1400301da  retn
```
