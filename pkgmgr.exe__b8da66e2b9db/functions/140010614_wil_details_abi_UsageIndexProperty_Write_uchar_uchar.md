# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140010614`
- end: `0x1400106ea`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fa98`

## callees

- `0x140010614`
- `0x140011fb8`

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
  memcpy_s_0(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s_0(v7, a3 - v7, (char *)this + 8, 2u);
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
  memcpy_s_0(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x140010614  push    rbx
0x140010616  push    rsi
0x140010617  push    rdi
0x140010618  push    r12
0x14001061a  push    r14
0x14001061c  push    r15
0x14001061e  sub     rsp, 28h
0x140010622  mov     rsi, rcx
0x140010625  mov     rdi, r8
0x140010628  mov     rcx, [rdx]; Destination
0x14001062b  mov     r12, rdx
0x14001062e  cmp     byte ptr [rsi+2], 1
0x140010632  jnz     short loc_140010656
0x140010634  lea     rbx, [rcx+2]
0x140010638  cmp     rbx, r8
0x14001063b  ja      short loc_1400106B9
0x14001063d  movzx   eax, word ptr [rsi+4]
0x140010641  lea     r8, [rsp+58h+arg_0]
0x140010646  mov     r9d, 2
0x14001064c  mov     [rsp+58h+arg_0], ax
0x140010651  mov     edx, r9d
0x140010654  jmp     short loc_140010674
0x140010656  cmp     byte ptr [rsi+2], 2
0x14001065a  mov     rbx, rcx
0x14001065d  jnz     short loc_140010679
0x14001065f  lea     rbx, [rcx+4]
0x140010663  cmp     rbx, rdi
0x140010666  ja      short loc_1400106B9
0x140010668  mov     edx, 4; DestinationSize
0x14001066d  lea     r8, [rsi+4]; Source
0x140010671  mov     r9d, edx; SourceSize
0x140010674  call    memcpy_s_0
0x140010679  cmp     word ptr [rsi], 0
0x14001067d  jnz     short loc_1400106A8
0x14001067f  lea     r15, [rbx+2]
0x140010683  cmp     r15, rdi
0x140010686  ja      short loc_1400106B9
0x140010688  lea     r14, [rsi+8]
0x14001068c  mov     rdx, rdi
0x14001068f  sub     rdx, rbx; DestinationSize
0x140010692  mov     r8, r14; Source
0x140010695  mov     r9d, 2; SourceSize
0x14001069b  mov     rcx, rbx; Destination
0x14001069e  call    memcpy_s_0
0x1400106a3  mov     rbx, r15
0x1400106a6  jmp     short loc_1400106AC
0x1400106a8  lea     r14, [rsi+8]
0x1400106ac  movzx   r9d, word ptr [r14]; SourceSize
0x1400106b0  lea     rax, [r9+rbx]
0x1400106b4  cmp     rax, rdi
0x1400106b7  jbe     short loc_1400106BD
0x1400106b9  xor     al, al
0x1400106bb  jmp     short loc_1400106DC
0x1400106bd  mov     r8, [rsi+18h]; Source
0x1400106c1  sub     rdi, rbx
0x1400106c4  mov     rdx, rdi; DestinationSize
0x1400106c7  mov     rcx, rbx; Destination
0x1400106ca  call    memcpy_s_0
0x1400106cf  movzx   ecx, word ptr [r14]
0x1400106d3  mov     al, 1
0x1400106d5  add     rcx, rbx
0x1400106d8  mov     [r12], rcx
0x1400106dc  add     rsp, 28h
0x1400106e0  pop     r15
0x1400106e2  pop     r14
0x1400106e4  pop     r12
0x1400106e6  pop     rdi
0x1400106e7  pop     rsi
0x1400106e8  pop     rbx
0x1400106e9  retn
```
