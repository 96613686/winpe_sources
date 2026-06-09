# SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)

- ea: `0x14000ab08`
- end: `0x14000abe2`
- name: `?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z`
- size: `218`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, __int64, int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001374`
- `0x140002090`
- `0x140002168`
- `0x140004694`
- `0x14000b898`

## callees

- `0x14000aabc`
- `0x14000ab08`

## pseudocode

```c
__int64 __fastcall SString::CaseCompareHelper(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        int a5,
        int a6)
{
  const unsigned __int16 *v7; // r14
  unsigned int v8; // ebx
  const unsigned __int16 *v9; // rbp
  int v10; // ecx
  int v11; // edi
  int v12; // ebx
  int v13; // eax

  v7 = a1;
  v8 = 0;
  v9 = &a1[a3];
  while ( !a6 || v7 < v9 )
  {
    v10 = *v7++;
    v11 = *a2;
    v8 = v10 - v11;
    ++a2;
    if ( (_WORD)v10 && (_WORD)v11 )
    {
      if ( v8 )
      {
        if ( (v10 & 0xFFFFFF80) != 0 )
        {
          v12 = (unsigned __int16)((__int64 (*)(void))MapChar)();
        }
        else
        {
          v12 = v10 - 32;
          if ( (unsigned __int16)(v10 - 97) > 0x19u )
            v12 = v10;
        }
        if ( (v11 & 0xFFFFFF80) != 0 )
        {
          v13 = (unsigned __int16)MapChar((unsigned __int16)v11);
        }
        else
        {
          v13 = v11 - 32;
          if ( (unsigned __int16)(v11 - 97) > 0x19u )
            v13 = v11;
        }
        v8 = v12 - v13;
        if ( v8 )
          return v8;
      }
    }
    else if ( v8 || a5 )
    {
      return v8;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14000ab08  mov     rax, rsp
0x14000ab0b  mov     [rax+8], rbx
0x14000ab0f  mov     [rax+10h], rbp
0x14000ab13  mov     [rax+18h], rsi
0x14000ab17  mov     [rax+20h], rdi
0x14000ab1b  push    r12
0x14000ab1d  push    r14
0x14000ab1f  push    r15
0x14000ab21  sub     rsp, 20h
0x14000ab25  mov     eax, r8d
0x14000ab28  xor     r12d, r12d
0x14000ab2b  mov     r15, rdx
0x14000ab2e  mov     r14, rcx
0x14000ab31  mov     ebx, r12d
0x14000ab34  lea     rbp, [rcx+rax*2]
0x14000ab38  cmp     [rsp+38h+arg_28], r12d
0x14000ab3d  jz      short loc_14000AB44
0x14000ab3f  cmp     r14, rbp
0x14000ab42  jnb     short loc_14000ABC1
0x14000ab44  movzx   ecx, word ptr [r14]
0x14000ab48  add     r14, 2
0x14000ab4c  movzx   edi, word ptr [r15]
0x14000ab50  mov     ebx, ecx
0x14000ab52  sub     ebx, edi
0x14000ab54  add     r15, 2
0x14000ab58  mov     esi, edi
0x14000ab5a  mov     eax, ecx
0x14000ab5c  test    cx, cx
0x14000ab5f  jz      short loc_14000ABB2
0x14000ab61  test    di, di
0x14000ab64  jz      short loc_14000ABB2
0x14000ab66  test    ebx, ebx
0x14000ab68  jz      short loc_14000AB38
0x14000ab6a  test    eax, 0FFFFFF80h
0x14000ab6f  jnz     short loc_14000AB81
0x14000ab71  sub     cx, 61h ; 'a'
0x14000ab75  lea     ebx, [rax-20h]
0x14000ab78  cmp     cx, 19h
0x14000ab7c  cmova   ebx, eax
0x14000ab7f  jmp     short loc_14000AB89
0x14000ab81  call    MapChar
0x14000ab86  movzx   ebx, ax
0x14000ab89  test    esi, 0FFFFFF80h
0x14000ab8f  jnz     short loc_14000ABA1
0x14000ab91  sub     di, 61h ; 'a'
0x14000ab95  lea     eax, [rsi-20h]
0x14000ab98  cmp     di, 19h
0x14000ab9c  cmova   eax, esi
0x14000ab9f  jmp     short loc_14000ABAC
0x14000aba1  movzx   ecx, di
0x14000aba4  call    MapChar
0x14000aba9  movzx   eax, ax
0x14000abac  sub     ebx, eax
0x14000abae  jnz     short loc_14000ABC1
0x14000abb0  jmp     short loc_14000AB38
0x14000abb2  test    ebx, ebx
0x14000abb4  jnz     short loc_14000ABC1
0x14000abb6  cmp     [rsp+38h+arg_20], r12d
0x14000abbb  jz      loc_14000AB38
0x14000abc1  mov     rbp, [rsp+38h+arg_8]
0x14000abc6  mov     eax, ebx
0x14000abc8  mov     rbx, [rsp+38h+arg_0]
0x14000abcd  mov     rsi, [rsp+38h+arg_10]
0x14000abd2  mov     rdi, [rsp+38h+arg_18]
0x14000abd7  add     rsp, 20h
0x14000abdb  pop     r15
0x14000abdd  pop     r14
0x14000abdf  pop     r12
0x14000abe1  retn
```
