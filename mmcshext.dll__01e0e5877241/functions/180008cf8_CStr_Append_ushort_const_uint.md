# CStr::Append(ushort const *,uint)

- ea: `0x180008cf8`
- end: `0x180008f54`
- name: `?Append@CStr@@QEAAJPEBGI@Z`
- size: `604`
- prototype: `__int64 __fastcall(CStr *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008bb0`
- `0x180008c54`
- `0x180009148`

## callees

- `0x180002c80`
- `0x180008cf8`
- `0x180009450`
- `0x1800096e8`

## pseudocode

```c
__int64 __fastcall CStr::Append(CStr *this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // rbp
  const unsigned __int16 *v4; // rdi
  unsigned __int16 near **v6; // rcx
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // r9
  __int64 v11; // rdx
  _WORD *v12; // r10
  __int64 v13; // rcx
  _WORD *v14; // rax
  __int64 v15; // rax
  _WORD *v16; // r11
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // rdx
  _WORD *v19; // r9
  signed int v20; // ecx
  _WORD *v21; // rax
  __int64 v22; // r10
  _WORD *v23; // rcx
  __int64 v24; // rax
  _WORD *v25; // rdx

  v3 = a3;
  v4 = a2;
  if ( a2 )
  {
    v6 = (unsigned __int16 near **)*((_QWORD *)this + 1);
    if ( v6 != &CStr::s_rgwchEmptyStringBuffer
      && a2 >= (const unsigned __int16 *)v6
      && a2 <= (const unsigned __int16 *)v6 + *((unsigned int *)this + 5) )
    {
      v7 = -2147024809;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 29;
        v10 = v4;
LABEL_51:
        WPP_SF_q(v8[2], v9, WPP_46616a5bce583dfc538f214383f522c0_Traceguids, v10);
        return v7;
      }
      return v7;
    }
    v7 = CStr::GrowBuffer(this, a3);
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_46616a5bce583dfc538f214383f522c0_Traceguids,
          (unsigned int)v3,
          v7);
      return v7;
    }
    v11 = (unsigned int)(*((_DWORD *)this + 5) + 1);
    if ( (unsigned __int64)(v11 - 1) > 0x7FFFFFFE )
    {
      v7 = -2147024809;
    }
    else
    {
      v12 = (_WORD *)*((_QWORD *)this + 1);
      v13 = (unsigned int)v11;
      v14 = v12;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      if ( v13 )
        v15 = v11 - v13;
      else
        v15 = 0;
      if ( v13 )
      {
        v16 = &v12[v15];
        v17 = v3;
        if ( v3 >= 0x7FFFFFFF )
        {
LABEL_26:
          v20 = -2147024809;
          goto LABEL_38;
        }
        v18 = v11 - v15;
        v19 = &v12[v15];
        if ( v18 > 1 )
        {
          v21 = &v12[v15];
          v22 = 0;
          do
          {
            if ( !v17 )
              break;
            if ( !*v4 )
              break;
            *v21++ = *v4++;
            --v17;
            ++v22;
            --v18;
          }
          while ( v18 );
          v23 = v21 - 1;
          if ( v18 )
            v23 = v21;
          v24 = v22 - 1;
          *v23 = 0;
          v20 = v18 == 0 ? 0x8007007A : 0;
          if ( v18 )
            v24 = v22;
          v19 = &v16[v24];
        }
        else
        {
          v20 = 0;
          if ( !(_DWORD)v3 || !*v4 )
            goto LABEL_39;
          if ( !v12 )
            goto LABEL_26;
          v20 = -2147024774;
        }
        if ( v20 < 0 )
        {
LABEL_38:
          *v16 = 0;
          v25 = 0;
          v19 = v16;
          if ( v20 != -2147024774 )
            goto LABEL_40;
        }
LABEL_39:
        v25 = v19;
LABEL_40:
        v7 = v20;
        if ( v20 >= 0 )
        {
          *((_DWORD *)this + 4) = ((__int64)v25 - *((_QWORD *)this + 1)) >> 1;
          return v7;
        }
        goto LABEL_45;
      }
      v7 = -2147024809;
    }
    v20 = -2147024809;
LABEL_45:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        WPP_46616a5bce583dfc538f214383f522c0_Traceguids,
        (unsigned int)v3,
        v20);
    return v7;
  }
  v7 = -2147024809;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 28;
    v10 = 0;
    goto LABEL_51;
  }
  return v7;
}

```

## disassembly

```asm
0x180008cf8  push    rbx
0x180008cfa  push    rbp
0x180008cfb  push    rsi
0x180008cfc  push    rdi
0x180008cfd  push    r14
0x180008cff  sub     rsp, 30h
0x180008d03  xor     r14d, r14d
0x180008d06  mov     ebp, r8d
0x180008d09  mov     rdi, rdx
0x180008d0c  mov     rsi, rcx
0x180008d0f  test    rdx, rdx
0x180008d12  jz      loc_180008F11
0x180008d18  mov     rcx, [rcx+8]
0x180008d1c  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180008d23  cmp     rcx, rax
0x180008d26  jz      short loc_180008D6B
0x180008d28  cmp     rdx, rcx
0x180008d2b  jb      short loc_180008D6B
0x180008d2d  mov     eax, [rsi+14h]
0x180008d30  lea     rcx, [rcx+rax*2]
0x180008d34  cmp     rdx, rcx
0x180008d37  ja      short loc_180008D6B
0x180008d39  mov     ebx, 80070057h
0x180008d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d45  lea     rax, WPP_GLOBAL_Control
0x180008d4c  cmp     rcx, rax
0x180008d4f  jz      loc_180008F47
0x180008d55  cmp     byte ptr [rcx+19h], 2
0x180008d59  jb      loc_180008F47
0x180008d5f  lea     edx, [r14+1Dh]
0x180008d63  mov     r9, rdi
0x180008d66  jmp     loc_180008F37
0x180008d6b  mov     edx, ebp; unsigned int
0x180008d6d  mov     rcx, rsi; this
0x180008d70  call    ?GrowBuffer@CStr@@IEAAJI@Z; CStr::GrowBuffer(uint)
0x180008d75  mov     ebx, eax
0x180008d77  test    eax, eax
0x180008d79  jns     short loc_180008DBD
0x180008d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d82  lea     rax, WPP_GLOBAL_Control
0x180008d89  cmp     rcx, rax
0x180008d8c  jz      loc_180008F47
0x180008d92  cmp     byte ptr [rcx+19h], 2
0x180008d96  jb      loc_180008F47
0x180008d9c  mov     rcx, [rcx+10h]
0x180008da0  mov     edx, 1Eh
0x180008da5  mov     [rsp+58h+var_38], ebx
0x180008da9  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x180008db0  mov     r9d, ebp
0x180008db3  call    WPP_SF_dd
0x180008db8  jmp     loc_180008F47
0x180008dbd  mov     eax, [rsi+14h]
0x180008dc0  inc     eax
0x180008dc2  mov     edx, eax
0x180008dc4  dec     rax
0x180008dc7  cmp     rax, 7FFFFFFEh
0x180008dcd  ja      loc_180008EDE
0x180008dd3  mov     r10, [rsi+8]
0x180008dd7  mov     ecx, edx
0x180008dd9  mov     rax, r10
0x180008ddc  cmp     [rax], r14w
0x180008de0  jz      short loc_180008DEC
0x180008de2  add     rax, 2
0x180008de6  sub     rcx, 1
0x180008dea  jnz     short loc_180008DDC
0x180008dec  mov     rax, rcx
0x180008def  mov     ebx, 80070057h
0x180008df4  neg     rax
0x180008df7  sbb     r8d, r8d
0x180008dfa  not     r8d
0x180008dfd  and     r8d, ebx
0x180008e00  test    rcx, rcx
0x180008e03  jz      short loc_180008E0D
0x180008e05  mov     rax, rdx
0x180008e08  sub     rax, rcx
0x180008e0b  jmp     short loc_180008E10
0x180008e0d  mov     rax, r14
0x180008e10  test    rcx, rcx
0x180008e13  jz      loc_180008ED9
0x180008e19  lea     r11, [r10+rax*2]
0x180008e1d  mov     r8, rbp
0x180008e20  cmp     rbp, 7FFFFFFFh
0x180008e27  jnb     short loc_180008E4B
0x180008e29  sub     rdx, rax
0x180008e2c  mov     r9, r11
0x180008e2f  cmp     rdx, 1
0x180008e33  ja      short loc_180008E56
0x180008e35  mov     ecx, r14d
0x180008e38  test    ebp, ebp
0x180008e3a  jz      loc_180008EC4
0x180008e40  cmp     [rdi], r14w
0x180008e44  jz      short loc_180008EC4
0x180008e46  test    r10, r10
0x180008e49  jnz     short loc_180008E4F
0x180008e4b  mov     ecx, ebx
0x180008e4d  jmp     short loc_180008EB2
0x180008e4f  mov     ecx, 8007007Ah
0x180008e54  jmp     short loc_180008EAE
0x180008e56  mov     rax, r11
0x180008e59  mov     r10, r14
0x180008e5c  test    r8, r8
0x180008e5f  jz      short loc_180008E80
0x180008e61  movzx   ecx, word ptr [rdi]
0x180008e64  test    cx, cx
0x180008e67  jz      short loc_180008E80
0x180008e69  mov     [rax], cx
0x180008e6c  add     rdi, 2
0x180008e70  add     rax, 2
0x180008e74  dec     r8
0x180008e77  inc     r10
0x180008e7a  sub     rdx, 1
0x180008e7e  jnz     short loc_180008E5C
0x180008e80  lea     rcx, [rax-2]
0x180008e84  test    rdx, rdx
0x180008e87  cmovnz  rcx, rax
0x180008e8b  mov     rax, rdx
0x180008e8e  neg     rax
0x180008e91  lea     rax, [r10-1]
0x180008e95  mov     [rcx], r14w
0x180008e99  sbb     ecx, ecx
0x180008e9b  not     ecx
0x180008e9d  and     ecx, 8007007Ah
0x180008ea3  test    rdx, rdx
0x180008ea6  cmovnz  rax, r10
0x180008eaa  lea     r9, [r11+rax*2]
0x180008eae  test    ecx, ecx
0x180008eb0  jns     short loc_180008EC4
0x180008eb2  mov     [r11], r14w
0x180008eb6  mov     rdx, r14
0x180008eb9  mov     r9, r11
0x180008ebc  cmp     ecx, 8007007Ah
0x180008ec2  jnz     short loc_180008EC7
0x180008ec4  mov     rdx, r9
0x180008ec7  mov     ebx, ecx
0x180008ec9  test    ecx, ecx
0x180008ecb  js      short loc_180008EE5
0x180008ecd  sub     rdx, [rsi+8]
0x180008ed1  sar     rdx, 1
0x180008ed4  mov     [rsi+10h], edx
0x180008ed7  jmp     short loc_180008F47
0x180008ed9  mov     ebx, r8d
0x180008edc  jmp     short loc_180008EE3
0x180008ede  mov     ebx, 80070057h
0x180008ee3  mov     ecx, ebx
0x180008ee5  mov     r10, cs:WPP_GLOBAL_Control
0x180008eec  lea     rax, WPP_GLOBAL_Control
0x180008ef3  cmp     r10, rax
0x180008ef6  jz      short loc_180008F47
0x180008ef8  cmp     byte ptr [r10+19h], 2
0x180008efd  jb      short loc_180008F47
0x180008eff  mov     [rsp+58h+var_38], ecx
0x180008f03  mov     edx, 1Fh
0x180008f08  mov     rcx, [r10+10h]
0x180008f0c  jmp     loc_180008DA9
0x180008f11  mov     ebx, 80070057h
0x180008f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f1d  lea     rax, WPP_GLOBAL_Control
0x180008f24  cmp     rcx, rax
0x180008f27  jz      short loc_180008F47
0x180008f29  cmp     byte ptr [rcx+19h], 2
0x180008f2d  jb      short loc_180008F47
0x180008f2f  mov     edx, 1Ch
0x180008f34  xor     r9d, r9d
0x180008f37  mov     rcx, [rcx+10h]
0x180008f3b  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x180008f42  call    WPP_SF_q
0x180008f47  mov     eax, ebx
0x180008f49  add     rsp, 30h
0x180008f4d  pop     r14
0x180008f4f  pop     rdi
0x180008f50  pop     rsi
0x180008f51  pop     rbp
0x180008f52  pop     rbx
0x180008f53  retn
```
