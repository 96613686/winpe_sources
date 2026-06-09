# TextLogInsertString

- ea: `0x18000512c`
- end: `0x1800051f2`
- name: `TextLogInsertString`
- size: `198`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180005bcc`
- `0x180005e5c`
- `0x180006590`

## callees

- `0x18000512c`
- `0x180005a5c`
- `0x180007c5c`
- `0x18000a156`

## pseudocode

```c
__int64 __fastcall TextLogInsertString(__int64 a1, unsigned int a2, _BYTE *a3)
{
  __int64 v4; // r14
  unsigned int v6; // edx
  __int64 v7; // rbx
  char v8; // r13
  unsigned int v9; // esi
  __int64 v10; // r8
  char *v11; // r15
  __int64 result; // rax

  v4 = a2;
  v6 = *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16);
  if ( (unsigned int)v4 > v6 )
    return 87;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  if ( !(_DWORD)v7 )
    return 87;
  v8 = a3[(unsigned int)(v7 - 1)];
  v9 = v7 + 2;
  if ( v8 == 10 )
    v9 = v7;
  v10 = *(_QWORD *)(a1 + 16);
  v11 = (char *)(v10 + v4);
  result = pSetupGrowMappedFileAtOffset(*(HANDLE *)a1, v6, v10, v4, v9);
  if ( !(_DWORD)result )
  {
    *(_QWORD *)(a1 + 24) += v9;
    memcpy_0(v11, a3, (unsigned int)v7);
    if ( v8 != 10 )
      *(_WORD *)&v11[(unsigned int)v7] = 2573;
    return TextLogUpdateFileOffsets(a1, v4, v9);
  }
  return result;
}

```

## disassembly

```asm
0x18000512c  push    rbx
0x18000512e  push    rsi
0x18000512f  push    rdi
0x180005130  push    r12
0x180005132  push    r13
0x180005134  push    r14
0x180005136  push    r15
0x180005138  sub     rsp, 40h
0x18000513c  mov     r12, r8
0x18000513f  mov     r14d, edx
0x180005142  mov     rdi, rcx
0x180005145  mov     eax, [rcx+18h]
0x180005148  sub     eax, [rcx+10h]
0x18000514b  mov     edx, eax
0x18000514d  cmp     r14d, eax
0x180005150  ja      loc_1800051DD
0x180005156  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000515a  inc     rbx
0x18000515d  cmp     byte ptr [r8+rbx], 0
0x180005162  jnz     short loc_18000515A
0x180005164  test    ebx, ebx
0x180005166  jz      short loc_1800051DD
0x180005168  lea     eax, [rbx-1]
0x18000516b  mov     r13b, [rax+r8]
0x18000516f  lea     esi, [rbx+2]
0x180005172  cmp     r13b, 0Ah
0x180005176  cmovz   esi, ebx
0x180005179  mov     r8, [rcx+10h]
0x18000517d  lea     r15, [r8+r14]
0x180005181  mov     [rsp+78h+var_58], esi; int
0x180005185  mov     r9d, r14d
0x180005188  mov     rcx, [rcx]; hFile
0x18000518b  call    pSetupGrowMappedFileAtOffset
0x180005190  mov     [rsp+78h+var_48], eax
0x180005194  test    eax, eax
0x180005196  jnz     short loc_1800051D0
0x180005198  mov     eax, esi
0x18000519a  add     [rdi+18h], rax
0x18000519e  mov     ebx, ebx
0x1800051a0  mov     r8d, ebx; Size
0x1800051a3  mov     rdx, r12; Src
0x1800051a6  mov     rcx, r15; void *
0x1800051a9  call    memcpy_0
0x1800051ae  cmp     r13b, 0Ah
0x1800051b2  jz      short loc_1800051BE
0x1800051b4  mov     eax, 0A0Dh
0x1800051b9  mov     [rbx+r15], ax
0x1800051be  mov     r8d, esi
0x1800051c1  mov     edx, r14d
0x1800051c4  mov     rcx, rdi
0x1800051c7  call    TextLogUpdateFileOffsets
0x1800051cc  mov     [rsp+78h+var_48], eax
0x1800051d0  jmp     short loc_1800051DB
0x1800051d2  mov     eax, 0Dh
0x1800051d7  mov     [rsp+78h+var_48], eax
0x1800051db  jmp     short loc_1800051E2
0x1800051dd  mov     eax, 57h ; 'W'
0x1800051e2  add     rsp, 40h
0x1800051e6  pop     r15
0x1800051e8  pop     r14
0x1800051ea  pop     r13
0x1800051ec  pop     r12
0x1800051ee  pop     rdi
0x1800051ef  pop     rsi
0x1800051f0  pop     rbx
0x1800051f1  retn
```
