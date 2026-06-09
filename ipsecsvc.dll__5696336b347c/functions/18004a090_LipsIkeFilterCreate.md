# LipsIkeFilterCreate

- ea: `0x18004a090`
- end: `0x18004a181`
- name: `LipsIkeFilterCreate`
- size: `241`
- prototype: `__int64 __fastcall(__int64, _OWORD *, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800454f0`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004a090`
- `0x18004b410`
- `0x18004b5b8`

## string_xrefs

- `0x18004a16a`: `LipsIkeFilterCreate`

## pseudocode

```c
__int64 __fastcall LipsIkeFilterCreate(__int64 a1, _OWORD *a2, char **a3)
{
  unsigned int v3; // ebx
  bool v5; // zf
  char *v8; // rcx
  char *v10; // [rsp+80h] [rbp+8h] BYREF

  v3 = 0;
  v5 = *(_DWORD *)(a1 + 124) == 4;
  v10 = 0;
  *a3 = 0;
  if ( v5 )
  {
    v3 = LipsFilterCreate(68, a1 + 40, a1 + 80, 0, 0, 0, 0, 0, &v10);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1d90d54a4b85392af5c36886988171ed_Traceguids, v3);
    }
    else
    {
      v8 = v10;
      *a3 = v10;
      v10 = 0;
      *((_DWORD *)v8 + 8) |= 4u;
      *(_OWORD *)(v8 + 152) = *a2;
      *((_QWORD *)v8 + 2) = *(_QWORD *)(a1 + 24);
      *((_QWORD *)v8 + 3) = *(_QWORD *)(a1 + 24);
    }
  }
  LipsFilterDestroy((LPVOID *)&v10);
  if ( v3 )
    return LipsReportError(v3, "LipsIkeFilterCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004a090  mov     r11, rsp
0x18004a093  push    rbx
0x18004a094  push    rbp
0x18004a095  push    rsi
0x18004a096  push    rdi
0x18004a097  sub     rsp, 58h
0x18004a09b  xor     ebx, ebx
0x18004a09d  mov     rsi, r8
0x18004a0a0  cmp     dword ptr [rcx+7Ch], 4
0x18004a0a4  mov     rbp, rdx
0x18004a0a7  mov     rdi, rcx
0x18004a0aa  mov     [r11+8], rbx
0x18004a0ae  mov     [r8], rbx
0x18004a0b1  jnz     loc_18004A155
0x18004a0b7  xor     eax, eax
0x18004a0b9  lea     r8, [rcx+50h]
0x18004a0bd  lea     rdx, [rcx+28h]
0x18004a0c1  xor     r9d, r9d
0x18004a0c4  lea     rcx, [r11+8]
0x18004a0c8  mov     [r11-38h], rcx
0x18004a0cc  lea     ecx, [rbx+44h]
0x18004a0cf  mov     [r11-40h], rax
0x18004a0d3  mov     [rsp+78h+var_48], ax
0x18004a0d8  mov     [rsp+78h+var_50], al
0x18004a0dc  mov     [r11-58h], rax
0x18004a0e0  call    LipsFilterCreate
0x18004a0e5  mov     ebx, eax
0x18004a0e7  test    eax, eax
0x18004a0e9  jz      short loc_18004A11E
0x18004a0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0f2  lea     rax, WPP_GLOBAL_Control
0x18004a0f9  cmp     rcx, rax
0x18004a0fc  jz      short loc_18004A155
0x18004a0fe  test    byte ptr [rcx+1Ch], 10h
0x18004a102  jz      short loc_18004A155
0x18004a104  mov     rcx, [rcx+10h]
0x18004a108  lea     r8, WPP_1d90d54a4b85392af5c36886988171ed_Traceguids
0x18004a10f  mov     edx, 0Ah
0x18004a114  mov     r9d, ebx
0x18004a117  call    WPP_SF_d
0x18004a11c  jmp     short loc_18004A155
0x18004a11e  mov     rcx, [rsp+78h+arg_0]
0x18004a126  mov     [rsi], rcx
0x18004a129  mov     [rsp+78h+arg_0], 0
0x18004a135  or      dword ptr [rcx+20h], 4
0x18004a139  movups  xmm0, xmmword ptr [rbp+0]
0x18004a13d  movdqu  xmmword ptr [rcx+98h], xmm0
0x18004a145  mov     rax, [rdi+18h]
0x18004a149  mov     [rcx+10h], rax
0x18004a14d  mov     rax, [rdi+18h]
0x18004a151  mov     [rcx+18h], rax
0x18004a155  lea     rcx, [rsp+78h+arg_0]
0x18004a15d  call    LipsFilterDestroy
0x18004a162  test    ebx, ebx
0x18004a164  jnz     short loc_18004A16A
0x18004a166  xor     eax, eax
0x18004a168  jmp     short loc_18004A178
0x18004a16a  lea     rdx, aLipsikefilterc; "LipsIkeFilterCreate"
0x18004a171  mov     ecx, ebx
0x18004a173  call    LipsReportError
0x18004a178  add     rsp, 58h
0x18004a17c  pop     rdi
0x18004a17d  pop     rsi
0x18004a17e  pop     rbp
0x18004a17f  pop     rbx
0x18004a180  retn
```
