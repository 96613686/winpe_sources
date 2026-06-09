# ReadAllocNameRecords

- ea: `0x18000ef20`
- end: `0x18000f0ec`
- name: `ReadAllocNameRecords`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800105d0`

## callees

- `0x18000ddc4`
- `0x18000ef20`
- `0x180011538`
- `0x180019e04`
- `0x180019e64`
- `0x18001a380`
- `0x18001a3bc`

## pseudocode

```c
__int64 ReadAllocNameRecords(__int64 a1, __int64 *a2, unsigned __int16 *a3, ...)
{
  unsigned __int16 v3; // r15
  unsigned int v7; // r13d
  __int64 result; // rax
  unsigned __int16 Generic; // bx
  unsigned __int16 v10; // si
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 v17; // [rsp+7Ch] [rbp+14h]
  __int64 v18; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  va_list va1; // [rsp+90h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v18 = va_arg(va1, _QWORD);
  v3 = 0;
  *a2 = 0;
  v16 = 0;
  v17 = 0;
  LOWORD(v18) = 0;
  *a3 = 0;
  v7 = TTTableOffset(a1, "name");
  if ( !v7 )
    return 1037;
  if ( !(unsigned int)TTTableLength(a1, "name") )
    return 1067;
  result = ReadGeneric(a1, (__int64)&v16, 6u, (unsigned __int8 *)&NAME_HEADER_CONTROL, v7, (__int64 *)va);
  Generic = result;
  if ( !(_WORD)result )
  {
    v10 = HIWORD(v16);
    v11 = Mem_Alloc(40LL * HIWORD(v16));
    *a2 = v11;
    v12 = v11;
    if ( v11 )
    {
      v13 = v7 + (unsigned __int16)v18;
      *a3 = v10;
      while ( v3 < *a3 )
      {
        Generic = ReadGeneric(a1, v12 + 40LL * v3, 0xCu, (unsigned __int8 *)&NAME_RECORD_CONTROL, v13, (__int64 *)va);
        if ( Generic )
          goto LABEL_17;
        v12 = *a2;
        if ( *(_WORD *)(*a2 + 40LL * v3 + 8) )
        {
          v14 = Mem_Alloc(*(unsigned __int16 *)(*a2 + 40LL * v3 + 8));
          v15 = *a2;
          *(_QWORD *)(*a2 + 40LL * v3 + 16) = v14;
          if ( !v14 )
          {
            Generic = 1005;
LABEL_17:
            FreeNameRecords(*a2, *a3);
            *a2 = 0;
            *a3 = 0;
            return Generic;
          }
          Generic = ReadBytes(
                      a1,
                      v14,
                      v7 + *(unsigned __int16 *)(v15 + 40LL * v3 + 10) + v17,
                      *(unsigned __int16 *)(v15 + 40LL * v3 + 8));
          if ( Generic )
            goto LABEL_17;
          v12 = *a2;
          *(_QWORD *)(v12 + 40LL * v3 + 24) = 0;
          *(_WORD *)(v12 + 40LL * v3 + 12) = 0;
          *(_DWORD *)(v12 + 40LL * v3 + 32) = 0;
        }
        v13 += (unsigned __int16)v18;
        ++v3;
      }
      return Generic;
    }
    else
    {
      return 1005;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ef20  mov     r11, rsp
0x18000ef23  mov     [r11+8], rbx
0x18000ef27  mov     [r11+20h], r9
0x18000ef2b  push    rbp
0x18000ef2c  push    rsi
0x18000ef2d  push    rdi
0x18000ef2e  push    r12
0x18000ef30  push    r13
0x18000ef32  push    r14
0x18000ef34  push    r15
0x18000ef36  sub     rsp, 30h
0x18000ef3a  xor     r15d, r15d
0x18000ef3d  xor     eax, eax
0x18000ef3f  mov     [rdx], r15
0x18000ef42  mov     rdi, rdx
0x18000ef45  lea     rdx, g_DirOptimizeTagArray+84h; "name"
0x18000ef4c  mov     [rsp+68h+arg_8], eax
0x18000ef50  mov     r14, r8
0x18000ef53  mov     [rsp+68h+arg_C], ax
0x18000ef58  mov     r12, rcx
0x18000ef5b  mov     [r11+20h], r15w
0x18000ef60  mov     [r8], r15w
0x18000ef64  call    TTTableOffset
0x18000ef69  mov     r13d, eax
0x18000ef6c  test    eax, eax
0x18000ef6e  jnz     short loc_18000EF7A
0x18000ef70  mov     eax, 40Dh
0x18000ef75  jmp     loc_18000F0D7
0x18000ef7a  lea     rdx, g_DirOptimizeTagArray+84h; "name"
0x18000ef81  mov     rcx, r12
0x18000ef84  call    TTTableLength
0x18000ef89  test    eax, eax
0x18000ef8b  jnz     short loc_18000EF97
0x18000ef8d  mov     eax, 42Bh
0x18000ef92  jmp     loc_18000F0D7
0x18000ef97  lea     rax, [rsp+68h+arg_18]
0x18000ef9f  mov     r8d, 6
0x18000efa5  mov     [rsp+68h+var_40], rax
0x18000efaa  lea     r9, NAME_HEADER_CONTROL
0x18000efb1  lea     rdx, [rsp+68h+arg_8]
0x18000efb6  mov     [rsp+68h+var_48], r13d
0x18000efbb  mov     rcx, r12
0x18000efbe  call    ReadGeneric
0x18000efc3  movzx   ebx, ax
0x18000efc6  test    ax, ax
0x18000efc9  jnz     loc_18000F0D7
0x18000efcf  movzx   esi, word ptr [rsp+68h+arg_8+2]
0x18000efd4  lea     rcx, [rsi+rsi*4]
0x18000efd8  shl     rcx, 3; Size
0x18000efdc  call    Mem_Alloc
0x18000efe1  mov     [rdi], rax
0x18000efe4  mov     rcx, rax
0x18000efe7  test    rax, rax
0x18000efea  jnz     short loc_18000EFF6
0x18000efec  mov     eax, 3EDh
0x18000eff1  jmp     loc_18000F0D7
0x18000eff6  movzx   ebp, word ptr [rsp+68h+arg_18]
0x18000effe  add     ebp, r13d
0x18000f001  mov     [r14], si
0x18000f005  cmp     r15w, [r14]
0x18000f009  jnb     loc_18000F0D4
0x18000f00f  movzx   eax, r15w
0x18000f013  lea     r9, NAME_RECORD_CONTROL
0x18000f01a  mov     r8d, 0Ch
0x18000f020  lea     rsi, [rax+rax*4]
0x18000f024  lea     rax, [rsp+68h+arg_18]
0x18000f02c  lea     rdx, [rcx+rsi*8]
0x18000f030  mov     [rsp+68h+var_40], rax
0x18000f035  mov     rcx, r12
0x18000f038  mov     [rsp+68h+var_48], ebp
0x18000f03c  call    ReadGeneric
0x18000f041  movzx   ebx, ax
0x18000f044  test    ax, ax
0x18000f047  jnz     short loc_18000F0BF
0x18000f049  mov     rcx, [rdi]
0x18000f04c  movzx   eax, word ptr [rcx+rsi*8+8]
0x18000f051  test    ax, ax
0x18000f054  jz      short loc_18000F0A7
0x18000f056  mov     ecx, eax; Size
0x18000f058  call    Mem_Alloc
0x18000f05d  mov     rcx, [rdi]
0x18000f060  mov     [rcx+rsi*8+10h], rax
0x18000f065  test    rax, rax
0x18000f068  jz      short loc_18000F0BA
0x18000f06a  movzx   r9d, word ptr [rcx+rsi*8+8]
0x18000f070  mov     rdx, rax
0x18000f073  movzx   ecx, word ptr [rcx+rsi*8+0Ah]
0x18000f078  movzx   r8d, [rsp+68h+arg_C]
0x18000f07e  add     ecx, r13d
0x18000f081  add     r8d, ecx
0x18000f084  mov     rcx, r12
0x18000f087  call    ReadBytes
0x18000f08c  xor     edx, edx
0x18000f08e  movzx   ebx, ax
0x18000f091  test    ax, ax
0x18000f094  jnz     short loc_18000F0BF
0x18000f096  mov     rcx, [rdi]
0x18000f099  mov     [rcx+rsi*8+18h], rdx
0x18000f09e  mov     [rcx+rsi*8+0Ch], dx
0x18000f0a3  mov     [rcx+rsi*8+20h], edx
0x18000f0a7  movzx   eax, word ptr [rsp+68h+arg_18]
0x18000f0af  add     ebp, eax
0x18000f0b1  inc     r15w
0x18000f0b5  jmp     loc_18000F005
0x18000f0ba  mov     ebx, 3EDh
0x18000f0bf  movzx   edx, word ptr [r14]
0x18000f0c3  mov     rcx, [rdi]
0x18000f0c6  call    FreeNameRecords
0x18000f0cb  xor     eax, eax
0x18000f0cd  mov     [rdi], rax
0x18000f0d0  mov     [r14], ax
0x18000f0d4  movzx   eax, bx
0x18000f0d7  mov     rbx, [rsp+68h+arg_0]
0x18000f0dc  add     rsp, 30h
0x18000f0e0  pop     r15
0x18000f0e2  pop     r14
0x18000f0e4  pop     r13
0x18000f0e6  pop     r12
0x18000f0e8  pop     rdi
0x18000f0e9  pop     rsi
0x18000f0ea  pop     rbp
0x18000f0eb  retn
```
