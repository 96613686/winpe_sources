# MszipCompress

- ea: `0x18000bf30`
- end: `0x18000bfa3`
- name: `MszipCompress`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bf30`
- `0x18000bfb0`

## pseudocode

```c
__int64 __fastcall MszipCompress(
        __int64 a1,
        const void *a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        __int64 *a6)
{
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  v7 = 0x8000;
  if ( a3 > 0x8000 )
  {
    v9 = 111;
LABEL_6:
    *a6 = v7;
    return v9;
  }
  v7 = a3 + 12;
  if ( a5 < a3 + 12 )
  {
    v9 = 122;
    goto LABEL_6;
  }
  v8 = NFMcompress(a1, a2, a3, a4, (int)a3 + 12, &v11);
  *a6 = v11;
  return v8 != 0 ? 0x65B : 0;
}

```

## disassembly

```asm
0x18000bf30  sub     rsp, 38h
0x18000bf34  mov     r10, rdx
0x18000bf37  mov     [rsp+38h+arg_10], 0
0x18000bf3f  mov     edx, 8000h
0x18000bf44  cmp     r8, rdx
0x18000bf47  ja      short loc_18000BF8D
0x18000bf49  lea     rdx, [r8+0Ch]
0x18000bf4d  cmp     [rsp+38h+arg_20], rdx
0x18000bf52  jb      short loc_18000BF9C
0x18000bf54  lea     rdx, [rsp+38h+arg_10]
0x18000bf59  mov     [rsp+38h+var_10], rdx
0x18000bf5e  lea     eax, [r8+0Ch]
0x18000bf62  mov     rdx, r10
0x18000bf65  mov     [rsp+38h+var_18], eax
0x18000bf69  call    NFMcompress
0x18000bf6e  mov     ecx, [rsp+38h+arg_10]
0x18000bf72  mov     edx, eax
0x18000bf74  mov     rax, [rsp+38h+arg_28]
0x18000bf79  neg     edx
0x18000bf7b  mov     [rax], rcx
0x18000bf7e  sbb     ecx, ecx
0x18000bf80  and     ecx, 65Bh
0x18000bf86  mov     eax, ecx
0x18000bf88  add     rsp, 38h
0x18000bf8c  retn
0x18000bf8d  mov     ecx, 6Fh ; 'o'
0x18000bf92  mov     rax, [rsp+38h+arg_28]
0x18000bf97  mov     [rax], rdx
0x18000bf9a  jmp     short loc_18000BF86
0x18000bf9c  mov     ecx, 7Ah ; 'z'
0x18000bfa1  jmp     short loc_18000BF92
```
