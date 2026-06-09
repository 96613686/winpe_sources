# MouseCopyWheelIDs

- ea: `0x14001b830`
- end: `0x14001b91d`
- name: `MouseCopyWheelIDs`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001aa98`

## callees

- `0x14000a67c`
- `0x14000db80`
- `0x14001b830`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001b868`
- `ntoskrnl!ExAllocatePool2` at `0x14001b868`
- `ntoskrnl!_wcsupr` at `0x14001b8e6`
- `ntoskrnl!_wcsupr` at `0x14001b8e6`

## pseudocode

```c
__int64 __fastcall MouseCopyWheelIDs(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  int v7; // edx
  wchar_t *i; // rbx

  *(_OWORD *)a1 = 0;
  result = *(unsigned __int16 *)(a2 + 2);
  if ( (unsigned int)result > 4 )
  {
    result = ExAllocatePool2(64, 2LL * *(unsigned __int16 *)(a2 + 2), 842281016, a4);
    *(_QWORD *)(a1 + 8) = result;
    if ( result )
    {
      memmove((void *)result, *(const void **)(a2 + 8), 2LL * *(unsigned __int16 *)(a2 + 2));
      result = *(unsigned __int16 *)(a2 + 2);
      *(_WORD *)(a1 + 2) = result;
      *(_WORD *)a1 = result;
      for ( i = *(wchar_t **)(a1 + 8); *i; i += result + 1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_S(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            14,
            95,
            (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
            (__int64)i);
        _wcsupr(i);
        result = -1;
        do
          ++result;
        while ( i[result] );
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001b830  mov     [rsp+arg_0], rbx
0x14001b835  mov     [rsp+arg_8], rsi
0x14001b83a  push    rdi
0x14001b83b  sub     rsp, 30h
0x14001b83f  xorps   xmm0, xmm0
0x14001b842  mov     rdi, rdx
0x14001b845  movups  xmmword ptr [rcx], xmm0
0x14001b848  movzx   eax, word ptr [rdx+2]
0x14001b84c  mov     rbx, rcx
0x14001b84f  cmp     eax, 4
0x14001b852  jbe     loc_14001B90C
0x14001b858  mov     edx, eax
0x14001b85a  mov     ecx, 40h ; '@'
0x14001b85f  add     rdx, rdx
0x14001b862  mov     r8d, 32343038h
0x14001b868  call    cs:__imp_ExAllocatePool2
0x14001b86f  nop     dword ptr [rax+rax+00h]
0x14001b874  xor     esi, esi
0x14001b876  mov     [rbx+8], rax
0x14001b87a  test    rax, rax
0x14001b87d  jz      loc_14001B90C
0x14001b883  movzx   r8d, word ptr [rdi+2]
0x14001b888  mov     rcx, rax; void *
0x14001b88b  mov     rdx, [rdi+8]; Src
0x14001b88f  add     r8, r8; Size
0x14001b892  call    memmove
0x14001b897  movzx   eax, word ptr [rdi+2]
0x14001b89b  mov     [rbx+2], ax
0x14001b89f  mov     [rbx], ax
0x14001b8a2  mov     rbx, [rbx+8]
0x14001b8a6  jmp     short loc_14001B907
0x14001b8a8  lea     rax, WPP_RECORDER_INITIALIZED
0x14001b8af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b8b6  jz      short loc_14001B8E3
0x14001b8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8bf  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001b8c6  mov     r9d, 5Fh ; '_'
0x14001b8cc  mov     [rsp+38h+var_10], rbx
0x14001b8d1  mov     [rsp+38h+var_18], rax
0x14001b8d6  mov     rcx, [rcx+40h]
0x14001b8da  lea     r8d, [r9-51h]
0x14001b8de  call    WPP_RECORDER_SF_S
0x14001b8e3  mov     rcx, rbx; String
0x14001b8e6  call    cs:__imp__wcsupr
0x14001b8ed  nop     dword ptr [rax+rax+00h]
0x14001b8f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b8f6  inc     rax
0x14001b8f9  cmp     [rbx+rax*2], si
0x14001b8fd  jnz     short loc_14001B8F6
0x14001b8ff  lea     rbx, [rbx+rax*2]
0x14001b903  add     rbx, 2
0x14001b907  cmp     [rbx], si
0x14001b90a  jnz     short loc_14001B8A8
0x14001b90c  mov     rbx, [rsp+38h+arg_0]
0x14001b911  mov     rsi, [rsp+38h+arg_8]
0x14001b916  add     rsp, 30h
0x14001b91a  pop     rdi
0x14001b91b  retn
```
