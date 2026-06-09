# WDigestGetContextToken

- ea: `0x1400286c0`
- end: `0x14002877c`
- name: `WDigestGetContextToken`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000936c`
- `0x1400285b8`
- `0x1400286c0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14002870d`
- `ntoskrnl!ExGetPreviousMode` at `0x14002870d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140028743`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140028743`

## pseudocode

```c
__int64 __fastcall WDigestGetContextToken(unsigned __int64 a1, _QWORD *a2, _QWORD *a3)
{
  NTSTATUS v6; // edi
  __int64 v7; // rax
  KPROCESSOR_MODE PreviousMode; // al
  PVOID Object; // [rsp+78h] [rbp+20h] BYREF

  v6 = WDigestReferenceContext();
  if ( v6 >= 0 )
  {
    v7 = *(_QWORD *)(a1 + 56);
    if ( v7 )
    {
      if ( a2 )
        *a2 = v7;
      if ( a3 )
      {
        if ( !*(_QWORD *)(a1 + 56)
          || *(_QWORD *)(a1 + 64)
          || (PreviousMode = ExGetPreviousMode(),
              Object = 0,
              v6 = ObReferenceObjectByHandle(*(HANDLE *)(a1 + 56), 0xCu, 0, PreviousMode, &Object, 0),
              *(_QWORD *)(a1 + 64) = Object,
              v6 >= 0) )
        {
          *a3 = *(_QWORD *)(a1 + 64);
        }
      }
    }
    else
    {
      v6 = -2146893045;
    }
    WDigestDerefContext(a1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400286c0  push    rbx
0x1400286c2  push    rsi
0x1400286c3  push    rdi
0x1400286c4  push    r14
0x1400286c6  sub     rsp, 38h
0x1400286ca  mov     r14, r8
0x1400286cd  mov     rsi, rdx
0x1400286d0  mov     rbx, rcx
0x1400286d3  call    WDigestReferenceContext
0x1400286d8  mov     edi, eax
0x1400286da  test    eax, eax
0x1400286dc  js      loc_14002876F
0x1400286e2  mov     rax, [rbx+38h]
0x1400286e6  test    rax, rax
0x1400286e9  jnz     short loc_1400286F2
0x1400286eb  mov     edi, 8009030Bh
0x1400286f0  jmp     short loc_140028765
0x1400286f2  test    rsi, rsi
0x1400286f5  jz      short loc_1400286FA
0x1400286f7  mov     [rsi], rax
0x1400286fa  test    r14, r14
0x1400286fd  jz      short loc_140028765
0x1400286ff  cmp     qword ptr [rbx+38h], 0
0x140028704  jz      short loc_14002875E
0x140028706  cmp     qword ptr [rbx+40h], 0
0x14002870b  jnz     short loc_14002875E
0x14002870d  call    cs:__imp_ExGetPreviousMode
0x140028714  nop     dword ptr [rax+rax+00h]
0x140028719  xor     r8d, r8d; ObjectType
0x14002871c  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x140028725  lea     rcx, [rsp+58h+arg_18]
0x14002872a  mov     [rsp+58h+arg_18], 0
0x140028733  mov     [rsp+58h+Object], rcx; Object
0x140028738  mov     r9b, al; AccessMode
0x14002873b  mov     rcx, [rbx+38h]; Handle
0x14002873f  lea     edx, [r8+0Ch]; DesiredAccess
0x140028743  call    cs:__imp_ObReferenceObjectByHandle
0x14002874a  nop     dword ptr [rax+rax+00h]
0x14002874f  mov     edi, eax
0x140028751  mov     rax, [rsp+58h+arg_18]
0x140028756  mov     [rbx+40h], rax
0x14002875a  test    edi, edi
0x14002875c  js      short loc_140028765
0x14002875e  mov     rax, [rbx+40h]
0x140028762  mov     [r14], rax
0x140028765  xor     edx, edx
0x140028767  mov     rcx, rbx; unsigned __int64
0x14002876a  call    WDigestDerefContext
0x14002876f  mov     eax, edi
0x140028771  add     rsp, 38h
0x140028775  pop     r14
0x140028777  pop     rdi
0x140028778  pop     rsi
0x140028779  pop     rbx
0x14002877a  retn
```
