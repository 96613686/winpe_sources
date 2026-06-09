# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180022808`
- end: `0x1800228f8`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800213f4`

## callees

- `0x180022808`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002286c`
- `msvcrt!memcpy_s` at `0x18002289d`
- `msvcrt!memcpy_s` at `0x1800228d0`
- `msvcrt!memcpy_s` at `0x18002286c`
- `msvcrt!memcpy_s` at `0x18002289d`
- `msvcrt!memcpy_s` at `0x1800228d0`

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
0x180022808  push    rbx
0x18002280a  push    rsi
0x18002280b  push    rdi
0x18002280c  push    r12
0x18002280e  push    r14
0x180022810  push    r15
0x180022812  sub     rsp, 28h
0x180022816  mov     rsi, rcx
0x180022819  mov     rdi, r8
0x18002281c  mov     rcx, [rdx]; Destination
0x18002281f  mov     r12, rdx
0x180022822  cmp     byte ptr [rsi+2], 1
0x180022826  jnz     short loc_18002284E
0x180022828  lea     rbx, [rcx+2]
0x18002282c  cmp     rbx, r8
0x18002282f  ja      loc_1800228BF
0x180022835  movzx   eax, word ptr [rsi+4]
0x180022839  lea     r8, [rsp+58h+arg_0]
0x18002283e  mov     r9d, 2
0x180022844  mov     [rsp+58h+arg_0], ax
0x180022849  mov     edx, r9d
0x18002284c  jmp     short loc_18002286C
0x18002284e  cmp     byte ptr [rsi+2], 2
0x180022852  mov     rbx, rcx
0x180022855  jnz     short loc_180022878
0x180022857  lea     rbx, [rcx+4]
0x18002285b  cmp     rbx, rdi
0x18002285e  ja      short loc_1800228BF
0x180022860  mov     edx, 4; DestinationSize
0x180022865  lea     r8, [rsi+4]; Source
0x180022869  mov     r9d, edx; SourceSize
0x18002286c  call    cs:__imp_memcpy_s
0x180022873  nop     dword ptr [rax+rax+00h]
0x180022878  cmp     word ptr [rsi], 0
0x18002287c  jnz     short loc_1800228AE
0x18002287e  lea     r15, [rbx+2]
0x180022882  cmp     r15, rdi
0x180022885  ja      short loc_1800228BF
0x180022887  lea     r14, [rsi+8]
0x18002288b  mov     rdx, rdi
0x18002288e  sub     rdx, rbx; DestinationSize
0x180022891  mov     r8, r14; Source
0x180022894  mov     r9d, 2; SourceSize
0x18002289a  mov     rcx, rbx; Destination
0x18002289d  call    cs:__imp_memcpy_s
0x1800228a4  nop     dword ptr [rax+rax+00h]
0x1800228a9  mov     rbx, r15
0x1800228ac  jmp     short loc_1800228B2
0x1800228ae  lea     r14, [rsi+8]
0x1800228b2  movzx   r9d, word ptr [r14]; SourceSize
0x1800228b6  lea     rax, [r9+rbx]
0x1800228ba  cmp     rax, rdi
0x1800228bd  jbe     short loc_1800228C3
0x1800228bf  xor     al, al
0x1800228c1  jmp     short loc_1800228E9
0x1800228c3  mov     r8, [rsi+18h]; Source
0x1800228c7  sub     rdi, rbx
0x1800228ca  mov     rdx, rdi; DestinationSize
0x1800228cd  mov     rcx, rbx; Destination
0x1800228d0  call    cs:__imp_memcpy_s
0x1800228d7  nop     dword ptr [rax+rax+00h]
0x1800228dc  movzx   ecx, word ptr [r14]
0x1800228e0  mov     al, 1
0x1800228e2  add     rcx, rbx
0x1800228e5  mov     [r12], rcx
0x1800228e9  add     rsp, 28h
0x1800228ed  pop     r15
0x1800228ef  pop     r14
0x1800228f1  pop     r12
0x1800228f3  pop     rdi
0x1800228f4  pop     rsi
0x1800228f5  pop     rbx
0x1800228f6  retn
```
