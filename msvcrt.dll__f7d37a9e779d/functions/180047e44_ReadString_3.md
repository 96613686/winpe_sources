# ReadString_3

- ea: `0x180047e44`
- end: `0x180047ff7`
- name: `ReadString_3`
- size: `435`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180048000`
- `0x180048248`

## callees

- `0x180005d70`
- `0x180020434`
- `0x1800204c8`
- `0x18002f05c`
- `0x180047e44`

## pseudocode

```c
__int64 __fastcall ReadString_3(char a1, __int64 a2, wint_t *a3, _DWORD *a4, char **a5, int a6, int a7, _DWORD *a8)
{
  char **v8; // rdi
  char *v12; // r14
  int v13; // r12d
  int v14; // esi
  wint_t v15; // ax
  unsigned int v16; // ecx
  char *v17; // rdx
  errno_t v18; // eax
  char *v19; // rcx
  int SizeConverted; // [rsp+70h] [rbp+8h] BYREF
  __int64 v22; // [rsp+78h] [rbp+10h]

  v22 = a2;
  v8 = a5;
  v12 = *a5;
  --*a4;
  LODWORD(a5) = -((a1 & 8) != 0);
  if ( *a3 != 0xFFFF )
    ungetwch_nolock(*a3);
  v13 = a6;
  v14 = a1 & 0x10;
  while ( 1 )
  {
    if ( (a1 & 1) != 0 )
    {
      if ( !v13 )
        goto LABEL_25;
      --v13;
    }
    ++*a4;
    v15 = getwche_nolock();
    *a3 = v15;
    if ( (a1 & 0x10) == 0 && ((a1 & 0x20) == 0 || (unsigned __int16)(v15 - 9) <= 4u || v15 == 32) )
    {
      if ( (a1 & 0x40) == 0 )
        break;
      if ( v15 < (unsigned __int16)(v15 >> 3) )
        break;
      v16 = (unsigned int)a5 ^ *(char *)((v15 >> 3) + v22);
      if ( !_bittest((const int *)&v16, v15 & 7) )
        break;
    }
    if ( (a1 & 4) != 0 )
    {
      v12 += 2;
    }
    else
    {
      v17 = *v8;
      if ( (a1 & 2) != 0 )
      {
        *(_WORD *)v17 = v15;
        *v8 += 2;
      }
      else
      {
        SizeConverted = 0;
        v18 = wctomb_s(&SizeConverted, v17, 5u, v15);
        if ( v18 )
        {
          if ( v18 == 22 || v18 == 34 )
            invoke_watson(0, 0, 0, 0, 0);
        }
        else
        {
          *v8 += SizeConverted;
        }
      }
    }
  }
  --*a4;
  v14 = 0;
  if ( *a3 != 0xFFFF )
    ungetwch_nolock(*a3);
LABEL_25:
  if ( v12 == *v8 )
    return 0xFFFFFFFFLL;
  if ( (a1 & 4) == 0 )
  {
    ++*a8;
    if ( !v14 )
    {
      v19 = *v8;
      if ( (a1 & 2) != 0 )
        *(_WORD *)v19 = 0;
      else
        *v19 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180047e44  mov     [rsp+arg_10], rbx
0x180047e49  mov     [rsp+arg_8], rdx
0x180047e4e  push    rbp
0x180047e4f  push    rsi
0x180047e50  push    rdi
0x180047e51  push    r12
0x180047e53  push    r13
0x180047e55  push    r14
0x180047e57  push    r15
0x180047e59  sub     rsp, 30h
0x180047e5d  mov     rdi, [rsp+68h+arg_20]
0x180047e65  mov     eax, ecx
0x180047e67  and     al, 8
0x180047e69  mov     rbp, r9
0x180047e6c  neg     al
0x180047e6e  mov     r15, r8
0x180047e71  mov     ebx, ecx
0x180047e73  mov     r14, [rdi]
0x180047e76  sbb     eax, eax
0x180047e78  dec     dword ptr [r9]
0x180047e7b  mov     dword ptr [rsp+68h+arg_20], eax
0x180047e82  mov     eax, 0FFFFh
0x180047e87  cmp     ax, [r8]
0x180047e8b  jz      short loc_180047E96
0x180047e8d  movzx   ecx, word ptr [r8]; Character
0x180047e91  call    _ungetwch_nolock
0x180047e96  mov     r12d, [rsp+68h+arg_28]
0x180047e9e  mov     esi, ebx
0x180047ea0  and     esi, 10h
0x180047ea3  mov     r13d, ebx
0x180047ea6  and     r13d, 1
0x180047eaa  test    r13d, r13d
0x180047ead  jz      short loc_180047EBB
0x180047eaf  test    r12d, r12d
0x180047eb2  jz      loc_180047FAE
0x180047eb8  dec     r12d
0x180047ebb  inc     dword ptr [rbp+0]
0x180047ebe  call    _getwche_nolock
0x180047ec3  mov     [r15], ax
0x180047ec7  movzx   r9d, ax; WCh
0x180047ecb  test    esi, esi
0x180047ecd  jnz     short loc_180047F1E
0x180047ecf  test    bl, 20h
0x180047ed2  jz      short loc_180047EE5
0x180047ed4  lea     eax, [r9-9]
0x180047ed8  cmp     ax, 4
0x180047edc  jbe     short loc_180047EE5
0x180047ede  cmp     r9w, 20h ; ' '
0x180047ee3  jnz     short loc_180047F1E
0x180047ee5  test    bl, 40h
0x180047ee8  jz      loc_180047F95
0x180047eee  movzx   ecx, r9w
0x180047ef2  shr     cx, 3
0x180047ef6  cmp     r9w, cx
0x180047efa  jb      loc_180047F95
0x180047f00  movzx   eax, cx
0x180047f03  mov     edx, r9d
0x180047f06  mov     rcx, [rsp+68h+arg_8]
0x180047f0b  and     edx, 7
0x180047f0e  movsx   ecx, byte ptr [rax+rcx]
0x180047f12  xor     ecx, dword ptr [rsp+68h+arg_20]
0x180047f19  bt      ecx, edx
0x180047f1c  jnb     short loc_180047F95
0x180047f1e  test    bl, 4
0x180047f21  jnz     short loc_180047F8C
0x180047f23  mov     rdx, [rdi]; MbCh
0x180047f26  test    bl, 2
0x180047f29  jz      short loc_180047F38
0x180047f2b  mov     [rdx], r9w
0x180047f2f  add     qword ptr [rdi], 2
0x180047f33  jmp     loc_180047EAA
0x180047f38  mov     r8d, 5; SizeInBytes
0x180047f3e  mov     [rsp+68h+SizeConverted], 0
0x180047f46  lea     rcx, [rsp+68h+SizeConverted]; SizeConverted
0x180047f4b  call    wctomb_s
0x180047f50  test    eax, eax
0x180047f52  jz      short loc_180047F7F
0x180047f54  cmp     eax, 16h
0x180047f57  jz      short loc_180047F62
0x180047f59  cmp     eax, 22h ; '"'
0x180047f5c  jnz     loc_180047EAA
0x180047f62  xor     r9d, r9d; LineNo
0x180047f65  mov     [rsp+68h+Reserved], 0; Reserved
0x180047f6e  xor     r8d, r8d; FileName
0x180047f71  xor     edx, edx; FunctionName
0x180047f73  xor     ecx, ecx; Expression
0x180047f75  call    _invoke_watson
0x180047f7a  jmp     loc_180047EAA
0x180047f7f  movsxd  rax, [rsp+68h+SizeConverted]
0x180047f84  add     [rdi], rax
0x180047f87  jmp     loc_180047EAA
0x180047f8c  add     r14, 2
0x180047f90  jmp     loc_180047EAA
0x180047f95  dec     dword ptr [rbp+0]
0x180047f98  xor     esi, esi
0x180047f9a  mov     eax, 0FFFFh
0x180047f9f  cmp     ax, [r15]
0x180047fa3  jz      short loc_180047FAE
0x180047fa5  movzx   ecx, word ptr [r15]; Character
0x180047fa9  call    _ungetwch_nolock
0x180047fae  cmp     r14, [rdi]
0x180047fb1  jz      short loc_180047FDC
0x180047fb3  test    bl, 4
0x180047fb6  jnz     short loc_180047FD8
0x180047fb8  mov     rax, [rsp+68h+arg_38]
0x180047fc0  inc     dword ptr [rax]
0x180047fc2  test    esi, esi
0x180047fc4  jnz     short loc_180047FD8
0x180047fc6  mov     rcx, [rdi]
0x180047fc9  test    bl, 2
0x180047fcc  jz      short loc_180047FD5
0x180047fce  xor     eax, eax
0x180047fd0  mov     [rcx], ax
0x180047fd3  jmp     short loc_180047FD8
0x180047fd5  mov     byte ptr [rcx], 0
0x180047fd8  xor     eax, eax
0x180047fda  jmp     short loc_180047FDF
0x180047fdc  or      eax, 0FFFFFFFFh
0x180047fdf  mov     rbx, [rsp+68h+arg_10]
0x180047fe7  add     rsp, 30h
0x180047feb  pop     r15
0x180047fed  pop     r14
0x180047fef  pop     r13
0x180047ff1  pop     r12
0x180047ff3  pop     rdi
0x180047ff4  pop     rsi
0x180047ff5  pop     rbp
0x180047ff6  retn
```
