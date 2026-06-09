# AslpFileGetExeWrapper

- ea: `0x14000d420`
- end: `0x14000d647`
- name: `AslpFileGetExeWrapper`
- size: `551`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000d650`

## callees

- `0x140007074`
- `0x14000d420`
- `0x14000dc74`
- `0x14000f0e8`
- `0x1400115c2`

## string_xrefs

- `0x14000d46f`: `AslpFileGetImageNtHeader failed [%x]`

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
0x14000d420  mov     [rsp+arg_10], rbx
0x14000d425  push    rsi
0x14000d426  push    rdi
0x14000d427  push    r12
0x14000d429  push    r13
0x14000d42b  push    r15
0x14000d42d  sub     rsp, 40h
0x14000d431  mov     r15, rdx
0x14000d434  mov     rsi, rcx
0x14000d437  xor     eax, eax
0x14000d439  mov     [rsp+68h+arg_0], eax
0x14000d43d  mov     [rcx], eax
0x14000d43f  mov     [rsp+68h+arg_8], rax
0x14000d444  mov     rax, 100000000h
0x14000d44e  cmp     [rdx+18h], rax
0x14000d452  jb      short loc_14000D45B
0x14000d454  xor     eax, eax
0x14000d456  jmp     loc_14000D632
0x14000d45b  lea     rcx, [rsp+68h+arg_8]
0x14000d460  call    AslpFileGetImageNtHeader
0x14000d465  mov     ebx, eax
0x14000d467  test    eax, eax
0x14000d469  jns     short loc_14000D492
0x14000d46b  mov     dword ptr [rsp+68h+var_48], eax
0x14000d46f  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x14000d476  mov     r8d, 0EF9h
0x14000d47c  lea     rdx, aAslpfilegetexe_0; "AslpFileGetExeWrapper"
0x14000d483  mov     ecx, 1
0x14000d488  call    AslLogCallPrintf
0x14000d48d  jmp     loc_14000D630
0x14000d492  mov     eax, 10Bh
0x14000d497  mov     rdi, [rsp+68h+arg_8]
0x14000d49c  cmp     [rdi+18h], ax
0x14000d4a0  jz      short loc_14000D4A9
0x14000d4a2  xor     eax, eax
0x14000d4a4  jmp     loc_14000D632
0x14000d4a9  movzx   r13d, word ptr [rdi+14h]
0x14000d4ae  add     r13, 18h
0x14000d4b2  add     r13, rdi
0x14000d4b5  mov     [rsp+68h+var_38], 0
0x14000d4bd  xor     ebx, ebx
0x14000d4bf  mov     [rsp+68h+var_38], ebx
0x14000d4c3  movzx   r12d, word ptr [rdi+6]
0x14000d4c8  cmp     ebx, r12d
0x14000d4cb  jnb     short loc_14000D50F
0x14000d4cd  lea     rcx, [rbx+rbx*4]
0x14000d4d1  lea     rcx, ds:0[rcx*8]
0x14000d4d9  add     rcx, r13; Str1
0x14000d4dc  cmp     dword ptr [rcx+0Ch], 0
0x14000d4e0  jz      short loc_14000D50B
0x14000d4e2  cmp     dword ptr [rcx+8], 0
0x14000d4e6  jz      short loc_14000D50B
0x14000d4e8  mov     r8d, 8; MaxCount
0x14000d4ee  lea     rdx, Str2; ".securom"
0x14000d4f5  call    strncmp_0
0x14000d4fa  test    eax, eax
0x14000d4fc  jnz     short loc_14000D509
0x14000d4fe  mov     dword ptr [rsi], 1
0x14000d504  jmp     loc_14000D5FF
0x14000d509  jmp     short $+2
0x14000d50b  inc     ebx
0x14000d50d  jmp     short loc_14000D4BF
0x14000d50f  mov     r8, r15
0x14000d512  mov     rdx, rdi
0x14000d515  lea     rcx, [rsp+68h+arg_0]
0x14000d51a  call    AslpFileHasActiveMarkWrapper
0x14000d51f  mov     ebx, eax
0x14000d521  mov     [rsp+68h+var_30], eax
0x14000d525  test    eax, eax
0x14000d527  jns     short loc_14000D582
0x14000d529  mov     eax, 0C0000225h
0x14000d52e  lea     rdx, aAslpfilegetexe_0; "AslpFileGetExeWrapper"
0x14000d535  cmp     ebx, eax
0x14000d537  jnz     short loc_14000D562
0x14000d539  mov     [rsp+68h+var_40], eax
0x14000d53d  mov     rax, [r15+18h]
0x14000d541  mov     [rsp+68h+var_48], rax
0x14000d546  lea     r9, aAslpfilehasact; "AslpFileHasActiveMarkWrapper failed (Fi"...
0x14000d54d  mov     r8d, 0F35h
0x14000d553  mov     ecx, 2
0x14000d558  call    AslLogCallPrintf
0x14000d55d  jmp     loc_14000D605
0x14000d562  mov     dword ptr [rsp+68h+var_48], ebx
0x14000d566  lea     r9, aAslpfilehasact_0; "AslpFileHasActiveMarkWrapper failed [%x"...
0x14000d56d  mov     r8d, 0F37h
0x14000d573  mov     ecx, 1
0x14000d578  call    AslLogCallPrintf
0x14000d57d  jmp     loc_14000D605
0x14000d582  cmp     [rsp+68h+arg_0], 0
0x14000d587  jz      short loc_14000D591
0x14000d589  mov     dword ptr [rsi], 2
0x14000d58f  jmp     short loc_14000D5FF
0x14000d591  cmp     dword ptr [rdi], 4550h
0x14000d597  jnz     short loc_14000D5AD
0x14000d599  cmp     byte ptr [rdi+1Ah], 53h ; 'S'
0x14000d59d  jnz     short loc_14000D5AD
0x14000d59f  cmp     byte ptr [rdi+1Bh], 52h ; 'R'
0x14000d5a3  jnz     short loc_14000D5AD
0x14000d5a5  mov     dword ptr [rsi], 3
0x14000d5ab  jmp     short loc_14000D5FF
0x14000d5ad  mov     [rsp+68h+var_34], 0
0x14000d5b5  xor     ebx, ebx
0x14000d5b7  mov     [rsp+68h+var_34], ebx
0x14000d5bb  cmp     ebx, r12d
0x14000d5be  jnb     short loc_14000D5FF
0x14000d5c0  lea     rcx, [rbx+rbx*4]
0x14000d5c4  lea     rcx, ds:0[rcx*8]
0x14000d5cc  add     rcx, r13; Str1
0x14000d5cf  cmp     dword ptr [rcx+0Ch], 0
0x14000d5d3  jz      short loc_14000D5FB
0x14000d5d5  cmp     dword ptr [rcx+8], 0
0x14000d5d9  jz      short loc_14000D5FB
0x14000d5db  mov     r8d, 8; MaxCount
0x14000d5e1  lea     rdx, aPs4; ".ps4"
0x14000d5e8  call    strncmp_0
0x14000d5ed  test    eax, eax
0x14000d5ef  jnz     short loc_14000D5F9
0x14000d5f1  mov     dword ptr [rsi], 4
0x14000d5f7  jmp     short loc_14000D5FF
0x14000d5f9  jmp     short $+2
0x14000d5fb  inc     ebx
0x14000d5fd  jmp     short loc_14000D5B7
0x14000d5ff  xor     ebx, ebx
0x14000d601  mov     [rsp+68h+var_30], ebx
0x14000d605  jmp     short loc_14000D630
0x14000d607  mov     ebx, eax
0x14000d609  mov     [rsp+68h+var_30], eax
0x14000d60d  mov     dword ptr [rsp+68h+var_48], eax
0x14000d611  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x14000d618  mov     r8d, 0F4Bh
0x14000d61e  lea     rdx, aAslpfilegetexe_0; "AslpFileGetExeWrapper"
0x14000d625  mov     ecx, 1
0x14000d62a  call    AslLogCallPrintf
0x14000d62f  nop
0x14000d630  mov     eax, ebx
0x14000d632  mov     rbx, [rsp+68h+arg_10]
0x14000d63a  add     rsp, 40h
0x14000d63e  pop     r15
0x14000d640  pop     r13
0x14000d642  pop     r12
0x14000d644  pop     rdi
0x14000d645  pop     rsi
0x14000d646  retn
0x1400118b4  push    rbp
0x1400118b6  sub     rsp, 30h
0x1400118ba  mov     rbp, rdx
0x1400118bd  mov     rax, [rcx]
0x1400118c0  xor     ecx, ecx
0x1400118c2  cmp     dword ptr [rax], 0C00000FDh
0x1400118c8  setnz   cl
0x1400118cb  mov     [rbp+3Ch], ecx
0x1400118ce  mov     eax, [rbp+3Ch]
0x1400118d1  add     rsp, 30h
0x1400118d5  pop     rbp
0x1400118d6  retn
```
