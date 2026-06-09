# WSTContextTableCompare(_RTL_GENERIC_TABLE *,void *,void *)

- ea: `0x18000be10`
- end: `0x18000be6a`
- name: `?WSTContextTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z`
- size: `90`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000be10`

## pseudocode

```c
__int64 __fastcall WSTContextTableCompare(
        struct _RTL_GENERIC_TABLE *Table,
        __int64 *FirstStruct,
        __int64 *SecondStruct)
{
  __int64 v3; // r9
  __int64 v4; // r8
  int v5; // edx
  __int64 i; // rcx
  int v7; // r10d
  int v8; // r11d
  __int64 result; // rax

  v3 = *SecondStruct;
  v4 = *FirstStruct;
  if ( *FirstStruct == v3 )
    return 2;
  v5 = *(_DWORD *)(v4 + 156) - *(_DWORD *)(v3 + 156);
  if ( !v5 )
  {
    for ( i = 0; (unsigned int)i < 0x10; i = (unsigned int)(i + 1) )
    {
      v7 = *(unsigned __int8 *)(i + v4 + 32);
      v8 = *(unsigned __int8 *)(i + v3 + 32);
      if ( (_BYTE)v7 != (_BYTE)v8 )
      {
        v5 = v7 - v8;
        break;
      }
    }
  }
  if ( v5 > 0 )
    return 1;
  result = 2;
  if ( v5 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000be10  mov     r9, [r8]
0x18000be13  mov     r8, [rdx]
0x18000be16  cmp     r8, r9
0x18000be19  jz      short loc_18000BE5A
0x18000be1b  mov     edx, [r8+9Ch]
0x18000be22  sub     edx, [r9+9Ch]
0x18000be29  jnz     short loc_18000BE49
0x18000be2b  xor     ecx, ecx
0x18000be2d  cmp     ecx, 10h
0x18000be30  jnb     short loc_18000BE49
0x18000be32  movzx   r10d, byte ptr [rcx+r8+20h]
0x18000be38  movzx   r11d, byte ptr [rcx+r9+20h]
0x18000be3e  cmp     r10b, r11b
0x18000be41  jz      short loc_18000BE66
0x18000be43  mov     edx, r10d
0x18000be46  sub     edx, r11d
0x18000be49  test    edx, edx
0x18000be4b  jg      short loc_18000BE60
0x18000be4d  xor     ecx, ecx
0x18000be4f  mov     eax, 2
0x18000be54  test    edx, edx
0x18000be56  cmovs   eax, ecx
0x18000be59  retn
0x18000be5a  mov     eax, 2
0x18000be5f  retn
0x18000be60  mov     eax, 1
0x18000be65  retn
0x18000be66  inc     ecx
0x18000be68  jmp     short loc_18000BE2D
```
