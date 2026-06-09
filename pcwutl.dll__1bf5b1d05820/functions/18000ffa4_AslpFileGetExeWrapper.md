# AslpFileGetExeWrapper

- ea: `0x18000ffa4`
- end: `0x1800101cb`
- name: `AslpFileGetExeWrapper`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800101d4`

## callees

- `0x18000e240`
- `0x18000ffa4`
- `0x1800107f8`
- `0x180011c6c`
- `0x1800191ae`

## string_xrefs

- `0x18000fff3`: `AslpFileGetImageNtHeader failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetExeWrapper(_DWORD *a1, __int64 a2)
{
  int ImageNtHeader; // eax
  int HasActiveMarkWrapper; // ebx
  __int64 v7; // rdi
  __int64 v8; // r13
  __int64 i; // rbx
  unsigned int v10; // r12d
  __int64 v11; // rcx
  __int64 j; // rbx
  __int64 v13; // rcx
  int v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 v15; // [rsp+78h] [rbp+10h] BYREF

  v14 = 0;
  *a1 = 0;
  v15 = 0;
  if ( *(_QWORD *)(a2 + 24) >= 0x100000000uLL )
    return 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v15, a2);
  HasActiveMarkWrapper = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v7 = v15;
    if ( *(_WORD *)(v15 + 24) != 267 )
      return 0;
    v8 = v15 + *(unsigned __int16 *)(v15 + 20) + 24LL;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v10 = *(unsigned __int16 *)(v7 + 6);
      if ( (unsigned int)i >= v10 )
        break;
      v11 = v8 + 40 * i;
      if ( *(_DWORD *)(v11 + 12) && *(_DWORD *)(v11 + 8) && !strncmp_0((const char *)v11, ".securom", 8u) )
      {
        *a1 = 1;
        return 0;
      }
    }
    HasActiveMarkWrapper = AslpFileHasActiveMarkWrapper(&v14, v7, a2);
    if ( HasActiveMarkWrapper >= 0 )
    {
      if ( v14 )
      {
        *a1 = 2;
      }
      else if ( *(_DWORD *)v7 == 17744 && *(_BYTE *)(v7 + 26) == 83 && *(_BYTE *)(v7 + 27) == 82 )
      {
        *a1 = 3;
      }
      else
      {
        for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
        {
          v13 = v8 + 40 * j;
          if ( *(_DWORD *)(v13 + 12) && *(_DWORD *)(v13 + 8) && !strncmp_0((const char *)v13, ".ps4", 8u) )
          {
            *a1 = 4;
            return 0;
          }
        }
      }
      return 0;
    }
    if ( HasActiveMarkWrapper == -1073741275 )
      AslLogCallPrintf(
        2,
        "AslpFileGetExeWrapper",
        3893,
        "AslpFileHasActiveMarkWrapper failed (FileSize: %I64u) [%x]",
        *(_QWORD *)(a2 + 24),
        -1073741275);
    else
      AslLogCallPrintf(
        1,
        "AslpFileGetExeWrapper",
        3895,
        "AslpFileHasActiveMarkWrapper failed [%x]",
        HasActiveMarkWrapper);
  }
  else
  {
    AslLogCallPrintf(1, "AslpFileGetExeWrapper", 3833, "AslpFileGetImageNtHeader failed [%x]", ImageNtHeader);
  }
  return (unsigned int)HasActiveMarkWrapper;
}

```

## disassembly

```asm
0x18000ffa4  mov     [rsp+arg_10], rbx
0x18000ffa9  push    rsi
0x18000ffaa  push    rdi
0x18000ffab  push    r12
0x18000ffad  push    r13
0x18000ffaf  push    r15
0x18000ffb1  sub     rsp, 40h
0x18000ffb5  mov     r15, rdx
0x18000ffb8  mov     rsi, rcx
0x18000ffbb  xor     eax, eax
0x18000ffbd  mov     [rsp+68h+arg_0], eax
0x18000ffc1  mov     [rcx], eax
0x18000ffc3  mov     [rsp+68h+arg_8], rax
0x18000ffc8  mov     rax, 100000000h
0x18000ffd2  cmp     [rdx+18h], rax
0x18000ffd6  jb      short loc_18000FFDF
0x18000ffd8  xor     eax, eax
0x18000ffda  jmp     loc_1800101B6
0x18000ffdf  lea     rcx, [rsp+68h+arg_8]
0x18000ffe4  call    AslpFileGetImageNtHeader
0x18000ffe9  mov     ebx, eax
0x18000ffeb  test    eax, eax
0x18000ffed  jns     short loc_180010016
0x18000ffef  mov     dword ptr [rsp+68h+var_48], eax
0x18000fff3  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x18000fffa  mov     r8d, 0EF9h
0x180010000  lea     rdx, aAslpfilegetexe_0; "AslpFileGetExeWrapper"
0x180010007  mov     ecx, 1
0x18001000c  call    AslLogCallPrintf
0x180010011  jmp     loc_1800101B4
0x180010016  mov     eax, 10Bh
0x18001001b  mov     rdi, [rsp+68h+arg_8]
0x180010020  cmp     [rdi+18h], ax
0x180010024  jz      short loc_18001002D
0x180010026  xor     eax, eax
0x180010028  jmp     loc_1800101B6
0x18001002d  movzx   r13d, word ptr [rdi+14h]
0x180010032  add     r13, 18h
0x180010036  add     r13, rdi
0x180010039  mov     [rsp+68h+var_38], 0
0x180010041  xor     ebx, ebx
0x180010043  mov     [rsp+68h+var_38], ebx
0x180010047  movzx   r12d, word ptr [rdi+6]
0x18001004c  cmp     ebx, r12d
0x18001004f  jnb     short loc_180010093
0x180010051  lea     rcx, [rbx+rbx*4]
0x180010055  lea     rcx, ds:0[rcx*8]
0x18001005d  add     rcx, r13; Str1
0x180010060  cmp     dword ptr [rcx+0Ch], 0
0x180010064  jz      short loc_18001008F
0x180010066  cmp     dword ptr [rcx+8], 0
0x18001006a  jz      short loc_18001008F
0x18001006c  mov     r8d, 8; MaxCount
0x180010072  lea     rdx, Str2; ".securom"
0x180010079  call    strncmp_0
0x18001007e  test    eax, eax
0x180010080  jnz     short loc_18001008D
0x180010082  mov     dword ptr [rsi], 1
0x180010088  jmp     loc_180010183
0x18001008d  jmp     short $+2
0x18001008f  inc     ebx
0x180010091  jmp     short loc_180010043
0x180010093  mov     r8, r15
0x180010096  mov     rdx, rdi
0x180010099  lea     rcx, [rsp+68h+arg_0]
0x18001009e  call    AslpFileHasActiveMarkWrapper
0x1800100a3  mov     ebx, eax
0x1800100a5  mov     [rsp+68h+var_30], eax
0x1800100a9  test    eax, eax
0x1800100ab  jns     short loc_180010106
0x1800100ad  mov     eax, 0C0000225h
0x1800100b2  lea     rdx, aAslpfilegetexe_0; "AslpFileGetExeWrapper"
0x1800100b9  cmp     ebx, eax
0x1800100bb  jnz     short loc_1800100E6
0x1800100bd  mov     [rsp+68h+var_40], eax
0x1800100c1  mov     rax, [r15+18h]
0x1800100c5  mov     [rsp+68h+var_48], rax
0x1800100ca  lea     r9, aAslpfilehasact; "AslpFileHasActiveMarkWrapper failed (Fi"...
0x1800100d1  mov     r8d, 0F35h
0x1800100d7  mov     ecx, 2
0x1800100dc  call    AslLogCallPrintf
0x1800100e1  jmp     loc_180010189
0x1800100e6  mov     dword ptr [rsp+68h+var_48], ebx
0x1800100ea  lea     r9, aAslpfilehasact_0; "AslpFileHasActiveMarkWrapper failed [%x"...
0x1800100f1  mov     r8d, 0F37h
0x1800100f7  mov     ecx, 1
0x1800100fc  call    AslLogCallPrintf
0x180010101  jmp     loc_180010189
0x180010106  cmp     [rsp+68h+arg_0], 0
0x18001010b  jz      short loc_180010115
0x18001010d  mov     dword ptr [rsi], 2
0x180010113  jmp     short loc_180010183
0x180010115  cmp     dword ptr [rdi], 4550h
0x18001011b  jnz     short loc_180010131
0x18001011d  cmp     byte ptr [rdi+1Ah], 53h ; 'S'
0x180010121  jnz     short loc_180010131
0x180010123  cmp     byte ptr [rdi+1Bh], 52h ; 'R'
0x180010127  jnz     short loc_180010131
0x180010129  mov     dword ptr [rsi], 3
0x18001012f  jmp     short loc_180010183
0x180010131  mov     [rsp+68h+var_34], 0
0x180010139  xor     ebx, ebx
0x18001013b  mov     [rsp+68h+var_34], ebx
0x18001013f  cmp     ebx, r12d
0x180010142  jnb     short loc_180010183
0x180010144  lea     rcx, [rbx+rbx*4]
0x180010148  lea     rcx, ds:0[rcx*8]
0x180010150  add     rcx, r13; Str1
0x180010153  cmp     dword ptr [rcx+0Ch], 0
0x180010157  jz      short loc_18001017F
0x180010159  cmp     dword ptr [rcx+8], 0
0x18001015d  jz      short loc_18001017F
0x18001015f  mov     r8d, 8; MaxCount
0x180010165  lea     rdx, aPs4; ".ps4"
0x18001016c  call    strncmp_0
0x180010171  test    eax, eax
0x180010173  jnz     short loc_18001017D
0x180010175  mov     dword ptr [rsi], 4
0x18001017b  jmp     short loc_180010183
0x18001017d  jmp     short $+2
0x18001017f  inc     ebx
0x180010181  jmp     short loc_18001013B
0x180010183  xor     ebx, ebx
0x180010185  mov     [rsp+68h+var_30], ebx
0x180010189  jmp     short loc_1800101B4
0x18001018b  mov     ebx, eax
0x18001018d  mov     [rsp+68h+var_30], eax
0x180010191  mov     dword ptr [rsp+68h+var_48], eax
0x180010195  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18001019c  mov     r8d, 0F4Bh
0x1800101a2  lea     rdx, aAslpfilegetexe_0; "AslpFileGetExeWrapper"
0x1800101a9  mov     ecx, 1
0x1800101ae  call    AslLogCallPrintf
0x1800101b3  nop
0x1800101b4  mov     eax, ebx
0x1800101b6  mov     rbx, [rsp+68h+arg_10]
0x1800101be  add     rsp, 40h
0x1800101c2  pop     r15
0x1800101c4  pop     r13
0x1800101c6  pop     r12
0x1800101c8  pop     rdi
0x1800101c9  pop     rsi
0x1800101ca  retn
0x180019740  push    rbp
0x180019742  sub     rsp, 30h
0x180019746  mov     rbp, rdx
0x180019749  mov     rax, [rcx]
0x18001974c  xor     ecx, ecx
0x18001974e  cmp     dword ptr [rax], 0C00000FDh
0x180019754  setnz   cl
0x180019757  mov     [rbp+3Ch], ecx
0x18001975a  mov     eax, [rbp+3Ch]
0x18001975d  add     rsp, 30h
0x180019761  pop     rbp
0x180019762  retn
```
