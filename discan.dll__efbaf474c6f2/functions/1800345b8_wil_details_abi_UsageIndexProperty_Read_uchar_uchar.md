# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800345b8`
- end: `0x1800346a1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180032bbc`
- `0x1800339c8`
- `0x180033e68`
- `0x180034b1c`
- `0x180035414`

## callees

- `0x1800345b8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180034607`
- `msvcrt!memcpy_s` at `0x18003463c`
- `msvcrt!memcpy_s` at `0x180034667`
- `msvcrt!memcpy_s` at `0x180034607`
- `msvcrt!memcpy_s` at `0x18003463c`
- `msvcrt!memcpy_s` at `0x180034667`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x1800345b8  mov     rax, rsp
0x1800345bb  mov     [rax+10h], rbx
0x1800345bf  mov     [rax+18h], rbp
0x1800345c3  push    rsi
0x1800345c4  push    rdi
0x1800345c5  push    r12
0x1800345c7  push    r14
0x1800345c9  push    r15
0x1800345cb  sub     rsp, 20h
0x1800345cf  xor     r15d, r15d
0x1800345d2  mov     rsi, r8
0x1800345d5  cmp     byte ptr [rcx+2], 1
0x1800345d9  mov     r12, rdx
0x1800345dc  mov     r8, [rdx]; Source
0x1800345df  mov     rdi, rcx
0x1800345e2  jnz     short loc_180034617
0x1800345e4  lea     rbx, [r8+2]
0x1800345e8  cmp     rbx, rsi
0x1800345eb  ja      loc_18003467C
0x1800345f1  lea     ebp, [r15+2]
0x1800345f5  mov     [rcx+10h], r8
0x1800345f9  mov     r9d, ebp; SourceSize
0x1800345fc  mov     [rax+8], r15w
0x180034601  mov     edx, ebp; DestinationSize
0x180034603  lea     rcx, [rax+8]; Destination
0x180034607  call    cs:__imp_memcpy_s
0x18003460d  movzx   eax, [rsp+48h+arg_0]
0x180034612  mov     [rdi+4], eax
0x180034615  jmp     short loc_180034642
0x180034617  mov     ebp, 2
0x18003461c  mov     rbx, r8
0x18003461f  cmp     [rcx+2], bpl
0x180034623  jnz     short loc_180034642
0x180034625  lea     rbx, [r8+4]
0x180034629  cmp     rbx, rsi
0x18003462c  ja      short loc_18003467C
0x18003462e  lea     edx, [rbp+2]; DestinationSize
0x180034631  mov     [rcx+10h], r8
0x180034635  mov     r9d, edx; SourceSize
0x180034638  add     rcx, 4; Destination
0x18003463c  call    cs:__imp_memcpy_s
0x180034642  movzx   eax, word ptr [rdi]
0x180034645  lea     r14, [rdi+8]
0x180034649  mov     [r14], ax
0x18003464d  test    ax, ax
0x180034650  jnz     short loc_180034670
0x180034652  lea     r15, [rbx+2]
0x180034656  cmp     r15, rsi
0x180034659  ja      short loc_18003467C
0x18003465b  mov     r9, rbp; SourceSize
0x18003465e  mov     r8, rbx; Source
0x180034661  mov     rdx, rbp; DestinationSize
0x180034664  mov     rcx, r14; Destination
0x180034667  call    cs:__imp_memcpy_s
0x18003466d  mov     rbx, r15
0x180034670  movzx   ecx, word ptr [r14]
0x180034674  add     rcx, rbx
0x180034677  cmp     rcx, rsi
0x18003467a  jbe     short loc_180034680
0x18003467c  xor     al, al
0x18003467e  jmp     short loc_18003468A
0x180034680  mov     [rdi+18h], rbx
0x180034684  mov     al, 1
0x180034686  mov     [r12], rcx
0x18003468a  mov     rbx, [rsp+48h+arg_8]
0x18003468f  mov     rbp, [rsp+48h+arg_10]
0x180034694  add     rsp, 20h
0x180034698  pop     r15
0x18003469a  pop     r14
0x18003469c  pop     r12
0x18003469e  pop     rdi
0x18003469f  pop     rsi
0x1800346a0  retn
```
