# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800241c8`
- end: `0x1800242a1`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001b170`

## callees

- `0x1800241c8`

## import_xrefs

- `ntdll!memcpy_s` at `0x180024228`
- `ntdll!memcpy_s` at `0x180024253`
- `ntdll!memcpy_s` at `0x180024280`
- `ntdll!memcpy_s` at `0x180024228`
- `ntdll!memcpy_s` at `0x180024253`
- `ntdll!memcpy_s` at `0x180024280`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x1800241c8  push    rbx
0x1800241ca  push    rsi
0x1800241cb  push    rdi
0x1800241cc  push    r12
0x1800241ce  push    r14
0x1800241d0  push    r15
0x1800241d2  sub     rsp, 28h
0x1800241d6  mov     rsi, rcx
0x1800241d9  mov     rdi, r8
0x1800241dc  mov     rcx, [rdx]; Destination
0x1800241df  mov     r12, rdx
0x1800241e2  cmp     byte ptr [rsi+2], 1
0x1800241e6  jnz     short loc_18002420A
0x1800241e8  lea     rbx, [rcx+2]
0x1800241ec  cmp     rbx, r8
0x1800241ef  ja      short loc_18002426F
0x1800241f1  movzx   eax, word ptr [rsi+4]
0x1800241f5  lea     r8, [rsp+58h+arg_0]
0x1800241fa  mov     r9d, 2
0x180024200  mov     [rsp+58h+arg_0], ax
0x180024205  mov     edx, r9d
0x180024208  jmp     short loc_180024228
0x18002420a  cmp     byte ptr [rsi+2], 2
0x18002420e  mov     rbx, rcx
0x180024211  jnz     short loc_18002422E
0x180024213  lea     rbx, [rcx+4]
0x180024217  cmp     rbx, rdi
0x18002421a  ja      short loc_18002426F
0x18002421c  mov     edx, 4; DestinationSize
0x180024221  lea     r8, [rsi+4]; Source
0x180024225  mov     r9d, edx; SourceSize
0x180024228  call    cs:__imp_memcpy_s
0x18002422e  cmp     word ptr [rsi], 0
0x180024232  jnz     short loc_18002425E
0x180024234  lea     r15, [rbx+2]
0x180024238  cmp     r15, rdi
0x18002423b  ja      short loc_18002426F
0x18002423d  lea     r14, [rsi+8]
0x180024241  mov     rdx, rdi
0x180024244  sub     rdx, rbx; DestinationSize
0x180024247  mov     r8, r14; Source
0x18002424a  mov     r9d, 2; SourceSize
0x180024250  mov     rcx, rbx; Destination
0x180024253  call    cs:__imp_memcpy_s
0x180024259  mov     rbx, r15
0x18002425c  jmp     short loc_180024262
0x18002425e  lea     r14, [rsi+8]
0x180024262  movzx   r9d, word ptr [r14]; SourceSize
0x180024266  lea     rax, [r9+rbx]
0x18002426a  cmp     rax, rdi
0x18002426d  jbe     short loc_180024273
0x18002426f  xor     al, al
0x180024271  jmp     short loc_180024293
0x180024273  mov     r8, [rsi+18h]; Source
0x180024277  sub     rdi, rbx
0x18002427a  mov     rdx, rdi; DestinationSize
0x18002427d  mov     rcx, rbx; Destination
0x180024280  call    cs:__imp_memcpy_s
0x180024286  movzx   ecx, word ptr [r14]
0x18002428a  mov     al, 1
0x18002428c  add     rcx, rbx
0x18002428f  mov     [r12], rcx
0x180024293  add     rsp, 28h
0x180024297  pop     r15
0x180024299  pop     r14
0x18002429b  pop     r12
0x18002429d  pop     rdi
0x18002429e  pop     rsi
0x18002429f  pop     rbx
0x1800242a0  retn
```
