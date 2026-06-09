# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a44c`
- end: `0x18000a532`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008778`
- `0x18000966c`
- `0x180009b0c`
- `0x18000aa88`
- `0x18000b78c`

## callees

- `0x18000a44c`
- `0x18000d014`

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
0x18000a44c  mov     rax, rsp
0x18000a44f  mov     [rax+10h], rbx
0x18000a453  mov     [rax+18h], rbp
0x18000a457  push    rsi
0x18000a458  push    rdi
0x18000a459  push    r12
0x18000a45b  push    r14
0x18000a45d  push    r15
0x18000a45f  sub     rsp, 20h
0x18000a463  xor     r15d, r15d
0x18000a466  mov     rsi, r8
0x18000a469  cmp     byte ptr [rcx+2], 1
0x18000a46d  mov     r12, rdx
0x18000a470  mov     r8, [rdx]; Source
0x18000a473  mov     rdi, rcx
0x18000a476  jnz     short loc_18000A4AA
0x18000a478  lea     rbx, [r8+2]
0x18000a47c  cmp     rbx, rsi
0x18000a47f  ja      loc_18000A50D
0x18000a485  lea     ebp, [r15+2]
0x18000a489  mov     [rcx+10h], r8
0x18000a48d  mov     r9d, ebp; SourceSize
0x18000a490  mov     [rax+8], r15w
0x18000a495  mov     edx, ebp; DestinationSize
0x18000a497  lea     rcx, [rax+8]; Destination
0x18000a49b  call    memcpy_s
0x18000a4a0  movzx   eax, [rsp+48h+arg_0]
0x18000a4a5  mov     [rdi+4], eax
0x18000a4a8  jmp     short loc_18000A4D4
0x18000a4aa  mov     ebp, 2
0x18000a4af  mov     rbx, r8
0x18000a4b2  cmp     [rcx+2], bpl
0x18000a4b6  jnz     short loc_18000A4D4
0x18000a4b8  lea     rbx, [r8+4]
0x18000a4bc  cmp     rbx, rsi
0x18000a4bf  ja      short loc_18000A50D
0x18000a4c1  lea     edx, [rbp+2]; DestinationSize
0x18000a4c4  mov     [rcx+10h], r8
0x18000a4c8  mov     r9d, edx; SourceSize
0x18000a4cb  add     rcx, 4; Destination
0x18000a4cf  call    memcpy_s
0x18000a4d4  movzx   eax, word ptr [rdi]
0x18000a4d7  lea     r14, [rdi+8]
0x18000a4db  mov     [r14], ax
0x18000a4df  test    ax, ax
0x18000a4e2  jnz     short loc_18000A501
0x18000a4e4  lea     r15, [rbx+2]
0x18000a4e8  cmp     r15, rsi
0x18000a4eb  ja      short loc_18000A50D
0x18000a4ed  mov     r9, rbp; SourceSize
0x18000a4f0  mov     r8, rbx; Source
0x18000a4f3  mov     rdx, rbp; DestinationSize
0x18000a4f6  mov     rcx, r14; Destination
0x18000a4f9  call    memcpy_s
0x18000a4fe  mov     rbx, r15
0x18000a501  movzx   ecx, word ptr [r14]
0x18000a505  add     rcx, rbx
0x18000a508  cmp     rcx, rsi
0x18000a50b  jbe     short loc_18000A511
0x18000a50d  xor     al, al
0x18000a50f  jmp     short loc_18000A51B
0x18000a511  mov     [rdi+18h], rbx
0x18000a515  mov     al, 1
0x18000a517  mov     [r12], rcx
0x18000a51b  mov     rbx, [rsp+48h+arg_8]
0x18000a520  mov     rbp, [rsp+48h+arg_10]
0x18000a525  add     rsp, 20h
0x18000a529  pop     r15
0x18000a52b  pop     r14
0x18000a52d  pop     r12
0x18000a52f  pop     rdi
0x18000a530  pop     rsi
0x18000a531  retn
```
