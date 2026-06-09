# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180019880`
- end: `0x18001997c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180016df8`
- `0x180018e64`
- `0x180019308`
- `0x180019ef4`
- `0x18001ada4`

## callees

- `0x180019880`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800198cf`
- `msvcrt!memcpy_s` at `0x18001990a`
- `msvcrt!memcpy_s` at `0x18001993b`
- `msvcrt!memcpy_s` at `0x1800198cf`
- `msvcrt!memcpy_s` at `0x18001990a`
- `msvcrt!memcpy_s` at `0x18001993b`

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
0x180019880  mov     rax, rsp
0x180019883  mov     [rax+10h], rbx
0x180019887  mov     [rax+18h], rbp
0x18001988b  push    rsi
0x18001988c  push    rdi
0x18001988d  push    r12
0x18001988f  push    r14
0x180019891  push    r15
0x180019893  sub     rsp, 20h
0x180019897  xor     r15d, r15d
0x18001989a  mov     rsi, r8
0x18001989d  cmp     byte ptr [rcx+2], 1
0x1800198a1  mov     r12, rdx
0x1800198a4  mov     r8, [rdx]; Source
0x1800198a7  mov     rdi, rcx
0x1800198aa  jnz     short loc_1800198E5
0x1800198ac  lea     rbx, [r8+2]
0x1800198b0  cmp     rbx, rsi
0x1800198b3  ja      loc_180019956
0x1800198b9  lea     ebp, [r15+2]
0x1800198bd  mov     [rcx+10h], r8
0x1800198c1  mov     r9d, ebp; SourceSize
0x1800198c4  mov     [rax+8], r15w
0x1800198c9  mov     edx, ebp; DestinationSize
0x1800198cb  lea     rcx, [rax+8]; Destination
0x1800198cf  call    cs:__imp_memcpy_s
0x1800198d6  nop     dword ptr [rax+rax+00h]
0x1800198db  movzx   eax, [rsp+48h+arg_0]
0x1800198e0  mov     [rdi+4], eax
0x1800198e3  jmp     short loc_180019916
0x1800198e5  mov     ebp, 2
0x1800198ea  mov     rbx, r8
0x1800198ed  cmp     [rcx+2], bpl
0x1800198f1  jnz     short loc_180019916
0x1800198f3  lea     rbx, [r8+4]
0x1800198f7  cmp     rbx, rsi
0x1800198fa  ja      short loc_180019956
0x1800198fc  lea     edx, [rbp+2]; DestinationSize
0x1800198ff  mov     [rcx+10h], r8
0x180019903  mov     r9d, edx; SourceSize
0x180019906  add     rcx, 4; Destination
0x18001990a  call    cs:__imp_memcpy_s
0x180019911  nop     dword ptr [rax+rax+00h]
0x180019916  movzx   eax, word ptr [rdi]
0x180019919  lea     r14, [rdi+8]
0x18001991d  mov     [r14], ax
0x180019921  test    ax, ax
0x180019924  jnz     short loc_18001994A
0x180019926  lea     r15, [rbx+2]
0x18001992a  cmp     r15, rsi
0x18001992d  ja      short loc_180019956
0x18001992f  mov     r9, rbp; SourceSize
0x180019932  mov     r8, rbx; Source
0x180019935  mov     rdx, rbp; DestinationSize
0x180019938  mov     rcx, r14; Destination
0x18001993b  call    cs:__imp_memcpy_s
0x180019942  nop     dword ptr [rax+rax+00h]
0x180019947  mov     rbx, r15
0x18001994a  movzx   ecx, word ptr [r14]
0x18001994e  add     rcx, rbx
0x180019951  cmp     rcx, rsi
0x180019954  jbe     short loc_18001995A
0x180019956  xor     al, al
0x180019958  jmp     short loc_180019964
0x18001995a  mov     [rdi+18h], rbx
0x18001995e  mov     al, 1
0x180019960  mov     [r12], rcx
0x180019964  mov     rbx, [rsp+48h+arg_8]
0x180019969  mov     rbp, [rsp+48h+arg_10]
0x18001996e  add     rsp, 20h
0x180019972  pop     r15
0x180019974  pop     r14
0x180019976  pop     r12
0x180019978  pop     rdi
0x180019979  pop     rsi
0x18001997a  retn
```
