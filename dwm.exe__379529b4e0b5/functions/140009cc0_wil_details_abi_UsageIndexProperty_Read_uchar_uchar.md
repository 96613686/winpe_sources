# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140009cc0`
- end: `0x140009da6`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ee0`
- `0x140008660`
- `0x14000930c`
- `0x1400097a4`
- `0x14000ac60`

## callees

- `0x140009cc0`
- `0x14000bebc`

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
0x140009cc0  mov     rax, rsp
0x140009cc3  mov     [rax+10h], rbx
0x140009cc7  mov     [rax+18h], rbp
0x140009ccb  push    rsi
0x140009ccc  push    rdi
0x140009ccd  push    r12
0x140009ccf  push    r14
0x140009cd1  push    r15
0x140009cd3  sub     rsp, 20h
0x140009cd7  xor     r15d, r15d
0x140009cda  mov     rsi, r8
0x140009cdd  cmp     byte ptr [rcx+2], 1
0x140009ce1  mov     r12, rdx
0x140009ce4  mov     r8, [rdx]; Source
0x140009ce7  mov     rdi, rcx
0x140009cea  jnz     short loc_140009D1E
0x140009cec  lea     rbx, [r8+2]
0x140009cf0  cmp     rbx, rsi
0x140009cf3  ja      loc_140009D81
0x140009cf9  lea     ebp, [r15+2]
0x140009cfd  mov     [rcx+10h], r8
0x140009d01  mov     r9d, ebp; SourceSize
0x140009d04  mov     [rax+8], r15w
0x140009d09  mov     edx, ebp; DestinationSize
0x140009d0b  lea     rcx, [rax+8]; Destination
0x140009d0f  call    memcpy_s
0x140009d14  movzx   eax, [rsp+48h+arg_0]
0x140009d19  mov     [rdi+4], eax
0x140009d1c  jmp     short loc_140009D48
0x140009d1e  mov     ebp, 2
0x140009d23  mov     rbx, r8
0x140009d26  cmp     [rcx+2], bpl
0x140009d2a  jnz     short loc_140009D48
0x140009d2c  lea     rbx, [r8+4]
0x140009d30  cmp     rbx, rsi
0x140009d33  ja      short loc_140009D81
0x140009d35  lea     edx, [rbp+2]; DestinationSize
0x140009d38  mov     [rcx+10h], r8
0x140009d3c  mov     r9d, edx; SourceSize
0x140009d3f  add     rcx, 4; Destination
0x140009d43  call    memcpy_s
0x140009d48  movzx   eax, word ptr [rdi]
0x140009d4b  lea     r14, [rdi+8]
0x140009d4f  mov     [r14], ax
0x140009d53  test    ax, ax
0x140009d56  jnz     short loc_140009D75
0x140009d58  lea     r15, [rbx+2]
0x140009d5c  cmp     r15, rsi
0x140009d5f  ja      short loc_140009D81
0x140009d61  mov     r9, rbp; SourceSize
0x140009d64  mov     r8, rbx; Source
0x140009d67  mov     rdx, rbp; DestinationSize
0x140009d6a  mov     rcx, r14; Destination
0x140009d6d  call    memcpy_s
0x140009d72  mov     rbx, r15
0x140009d75  movzx   ecx, word ptr [r14]
0x140009d79  add     rcx, rbx
0x140009d7c  cmp     rcx, rsi
0x140009d7f  jbe     short loc_140009D85
0x140009d81  xor     al, al
0x140009d83  jmp     short loc_140009D8F
0x140009d85  mov     [rdi+18h], rbx
0x140009d89  mov     al, 1
0x140009d8b  mov     [r12], rcx
0x140009d8f  mov     rbx, [rsp+48h+arg_8]
0x140009d94  mov     rbp, [rsp+48h+arg_10]
0x140009d99  add     rsp, 20h
0x140009d9d  pop     r15
0x140009d9f  pop     r14
0x140009da1  pop     r12
0x140009da3  pop     rdi
0x140009da4  pop     rsi
0x140009da5  retn
```
