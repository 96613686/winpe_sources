# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000881c`
- end: `0x140008902`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140007778`
- `0x140007bb0`
- `0x140007d0c`
- `0x140008dc8`
- `0x140009610`

## callees

- `0x1400069a8`
- `0x14000881c`

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
0x14000881c  mov     rax, rsp
0x14000881f  mov     [rax+10h], rbx
0x140008823  mov     [rax+18h], rbp
0x140008827  push    rsi
0x140008828  push    rdi
0x140008829  push    r12
0x14000882b  push    r14
0x14000882d  push    r15
0x14000882f  sub     rsp, 20h
0x140008833  xor     r15d, r15d
0x140008836  mov     rsi, r8
0x140008839  cmp     byte ptr [rcx+2], 1
0x14000883d  mov     r12, rdx
0x140008840  mov     r8, [rdx]; Source
0x140008843  mov     rdi, rcx
0x140008846  jnz     short loc_14000887A
0x140008848  lea     rbx, [r8+2]
0x14000884c  cmp     rbx, rsi
0x14000884f  ja      loc_1400088DD
0x140008855  lea     ebp, [r15+2]
0x140008859  mov     [rcx+10h], r8
0x14000885d  mov     r9d, ebp; SourceSize
0x140008860  mov     [rax+8], r15w
0x140008865  mov     edx, ebp; DestinationSize
0x140008867  lea     rcx, [rax+8]; Destination
0x14000886b  call    memcpy_s
0x140008870  movzx   eax, [rsp+48h+arg_0]
0x140008875  mov     [rdi+4], eax
0x140008878  jmp     short loc_1400088A4
0x14000887a  mov     ebp, 2
0x14000887f  mov     rbx, r8
0x140008882  cmp     [rcx+2], bpl
0x140008886  jnz     short loc_1400088A4
0x140008888  lea     rbx, [r8+4]
0x14000888c  cmp     rbx, rsi
0x14000888f  ja      short loc_1400088DD
0x140008891  lea     edx, [rbp+2]; DestinationSize
0x140008894  mov     [rcx+10h], r8
0x140008898  mov     r9d, edx; SourceSize
0x14000889b  add     rcx, 4; Destination
0x14000889f  call    memcpy_s
0x1400088a4  movzx   eax, word ptr [rdi]
0x1400088a7  lea     r14, [rdi+8]
0x1400088ab  mov     [r14], ax
0x1400088af  test    ax, ax
0x1400088b2  jnz     short loc_1400088D1
0x1400088b4  lea     r15, [rbx+2]
0x1400088b8  cmp     r15, rsi
0x1400088bb  ja      short loc_1400088DD
0x1400088bd  mov     r9, rbp; SourceSize
0x1400088c0  mov     r8, rbx; Source
0x1400088c3  mov     rdx, rbp; DestinationSize
0x1400088c6  mov     rcx, r14; Destination
0x1400088c9  call    memcpy_s
0x1400088ce  mov     rbx, r15
0x1400088d1  movzx   ecx, word ptr [r14]
0x1400088d5  add     rcx, rbx
0x1400088d8  cmp     rcx, rsi
0x1400088db  jbe     short loc_1400088E1
0x1400088dd  xor     al, al
0x1400088df  jmp     short loc_1400088EB
0x1400088e1  mov     [rdi+18h], rbx
0x1400088e5  mov     al, 1
0x1400088e7  mov     [r12], rcx
0x1400088eb  mov     rbx, [rsp+48h+arg_8]
0x1400088f0  mov     rbp, [rsp+48h+arg_10]
0x1400088f5  add     rsp, 20h
0x1400088f9  pop     r15
0x1400088fb  pop     r14
0x1400088fd  pop     r12
0x1400088ff  pop     rdi
0x140008900  pop     rsi
0x140008901  retn
```
