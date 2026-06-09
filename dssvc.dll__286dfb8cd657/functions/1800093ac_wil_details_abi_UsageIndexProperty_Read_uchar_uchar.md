# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800093ac`
- end: `0x180009495`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008720`
- `0x180008bc0`
- `0x180008cf8`
- `0x180009924`
- `0x18000a040`

## callees

- `0x1800093ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800093fb`
- `msvcrt!memcpy_s` at `0x180009430`
- `msvcrt!memcpy_s` at `0x18000945b`
- `msvcrt!memcpy_s` at `0x1800093fb`
- `msvcrt!memcpy_s` at `0x180009430`
- `msvcrt!memcpy_s` at `0x18000945b`

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
0x1800093ac  mov     rax, rsp
0x1800093af  mov     [rax+10h], rbx
0x1800093b3  mov     [rax+18h], rbp
0x1800093b7  push    rsi
0x1800093b8  push    rdi
0x1800093b9  push    r12
0x1800093bb  push    r14
0x1800093bd  push    r15
0x1800093bf  sub     rsp, 20h
0x1800093c3  xor     r15d, r15d
0x1800093c6  mov     rsi, r8
0x1800093c9  cmp     byte ptr [rcx+2], 1
0x1800093cd  mov     r12, rdx
0x1800093d0  mov     r8, [rdx]; Source
0x1800093d3  mov     rdi, rcx
0x1800093d6  jnz     short loc_18000940B
0x1800093d8  lea     rbx, [r8+2]
0x1800093dc  cmp     rbx, rsi
0x1800093df  ja      loc_180009470
0x1800093e5  lea     ebp, [r15+2]
0x1800093e9  mov     [rcx+10h], r8
0x1800093ed  mov     r9d, ebp; SourceSize
0x1800093f0  mov     [rax+8], r15w
0x1800093f5  mov     edx, ebp; DestinationSize
0x1800093f7  lea     rcx, [rax+8]; Destination
0x1800093fb  call    cs:__imp_memcpy_s
0x180009401  movzx   eax, [rsp+48h+arg_0]
0x180009406  mov     [rdi+4], eax
0x180009409  jmp     short loc_180009436
0x18000940b  mov     ebp, 2
0x180009410  mov     rbx, r8
0x180009413  cmp     [rcx+2], bpl
0x180009417  jnz     short loc_180009436
0x180009419  lea     rbx, [r8+4]
0x18000941d  cmp     rbx, rsi
0x180009420  ja      short loc_180009470
0x180009422  lea     edx, [rbp+2]; DestinationSize
0x180009425  mov     [rcx+10h], r8
0x180009429  mov     r9d, edx; SourceSize
0x18000942c  add     rcx, 4; Destination
0x180009430  call    cs:__imp_memcpy_s
0x180009436  movzx   eax, word ptr [rdi]
0x180009439  lea     r14, [rdi+8]
0x18000943d  mov     [r14], ax
0x180009441  test    ax, ax
0x180009444  jnz     short loc_180009464
0x180009446  lea     r15, [rbx+2]
0x18000944a  cmp     r15, rsi
0x18000944d  ja      short loc_180009470
0x18000944f  mov     r9, rbp; SourceSize
0x180009452  mov     r8, rbx; Source
0x180009455  mov     rdx, rbp; DestinationSize
0x180009458  mov     rcx, r14; Destination
0x18000945b  call    cs:__imp_memcpy_s
0x180009461  mov     rbx, r15
0x180009464  movzx   ecx, word ptr [r14]
0x180009468  add     rcx, rbx
0x18000946b  cmp     rcx, rsi
0x18000946e  jbe     short loc_180009474
0x180009470  xor     al, al
0x180009472  jmp     short loc_18000947E
0x180009474  mov     [rdi+18h], rbx
0x180009478  mov     al, 1
0x18000947a  mov     [r12], rcx
0x18000947e  mov     rbx, [rsp+48h+arg_8]
0x180009483  mov     rbp, [rsp+48h+arg_10]
0x180009488  add     rsp, 20h
0x18000948c  pop     r15
0x18000948e  pop     r14
0x180009490  pop     r12
0x180009492  pop     rdi
0x180009493  pop     rsi
0x180009494  retn
```
