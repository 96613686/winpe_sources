# PrjfConvertFullPathToRelative

- ea: `0x140037ac0`
- end: `0x140037b86`
- name: `PrjfConvertFullPathToRelative`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400037e0`
- `0x140042eac`

## callees

- `0x14000bb80`
- `0x140037ac0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140037af9`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x140037af9`

## pseudocode

```c
__int64 __fastcall PrjfConvertFullPathToRelative(PCWCH *a1, PCWCH *a2, __int64 a3)
{
  PCWCH v6; // rdx
  unsigned __int16 v7; // r9
  unsigned __int64 v8; // rax
  unsigned __int16 v9; // bx
  __int64 result; // rax

  if ( *(_WORD *)a1 > *(_WORD *)a2
    || RtlCompareUnicodeStrings(
         a1[1],
         (unsigned __int64)*(unsigned __int16 *)a1 >> 1,
         a2[1],
         (unsigned __int64)*(unsigned __int16 *)a1 >> 1,
         1u) )
  {
    return 3221225485LL;
  }
  v6 = a2[1];
  v7 = *(_WORD *)a1 + 2;
  v8 = *(unsigned __int16 *)a2;
  if ( a1[1][((unsigned __int64)*(unsigned __int16 *)a1 >> 1) - 1] == 92 )
    v7 = *(_WORD *)a1;
  v9 = v8 - v7 - 2;
  if ( v6[(v8 >> 1) - 1] != 92 )
    v9 = v8 - v7;
  if ( *(_WORD *)(a3 + 2) < v9 )
    return 2147483653LL;
  memmove(*(void **)(a3 + 8), &v6[(unsigned __int64)v7 >> 1], v9);
  result = 0;
  *(_WORD *)a3 = v9;
  return result;
}

```

## disassembly

```asm
0x140037ac0  mov     [rsp+arg_0], rbx
0x140037ac5  mov     [rsp+arg_8], rsi
0x140037aca  push    rdi
0x140037acb  sub     rsp, 30h
0x140037acf  movzx   eax, word ptr [rcx]
0x140037ad2  mov     rsi, r8
0x140037ad5  mov     rbx, rdx
0x140037ad8  mov     rdi, rcx
0x140037adb  cmp     ax, [rdx]
0x140037ade  ja      loc_140037B70
0x140037ae4  mov     r8, [rbx+8]; String2
0x140037ae8  mov     edx, eax
0x140037aea  mov     rcx, [rcx+8]; String1
0x140037aee  shr     rdx, 1; String1Length
0x140037af1  mov     r9, rdx; String2Length
0x140037af4  mov     [rsp+38h+CaseInSensitive], 1; CaseInSensitive
0x140037af9  call    cs:__imp_RtlCompareUnicodeStrings
0x140037b00  nop     dword ptr [rax+rax+00h]
0x140037b05  test    eax, eax
0x140037b07  jnz     short loc_140037B70
0x140037b09  movzx   r8d, word ptr [rdi]
0x140037b0d  mov     rdx, [rbx+8]
0x140037b11  mov     ecx, r8d
0x140037b14  mov     rax, [rdi+8]
0x140037b18  shr     rcx, 1
0x140037b1b  lea     r9d, [r8+2]
0x140037b1f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140037b25  movzx   eax, word ptr [rbx]
0x140037b28  cmovz   r9w, r8w
0x140037b2d  movzx   ecx, ax
0x140037b30  sub     cx, r9w
0x140037b34  shr     rax, 1
0x140037b37  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x140037b3d  lea     ebx, [rcx-2]
0x140037b40  cmovnz  bx, cx
0x140037b44  cmp     [rsi+2], bx
0x140037b48  jnb     short loc_140037B51
0x140037b4a  mov     eax, 80000005h
0x140037b4f  jmp     short loc_140037B75
0x140037b51  mov     rcx, [rsi+8]; void *
0x140037b55  movzx   eax, r9w
0x140037b59  shr     rax, 1
0x140037b5c  movzx   r8d, bx; Size
0x140037b60  lea     rdx, [rdx+rax*2]; Src
0x140037b64  call    memmove
0x140037b69  xor     eax, eax
0x140037b6b  mov     [rsi], bx
0x140037b6e  jmp     short loc_140037B75
0x140037b70  mov     eax, 0C000000Dh
0x140037b75  mov     rbx, [rsp+38h+arg_0]
0x140037b7a  mov     rsi, [rsp+38h+arg_8]
0x140037b7f  add     rsp, 30h
0x140037b83  pop     rdi
0x140037b84  retn
```
