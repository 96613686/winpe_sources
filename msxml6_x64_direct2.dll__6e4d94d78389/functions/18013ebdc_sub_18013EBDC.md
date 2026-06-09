# sub_18013EBDC

- ea: `0x18013ebdc`
- end: `0x18013ed0b`
- name: `sub_18013EBDC`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18013dd40`

## callees

- `0x18013de14`
- `0x18013ebdc`
- `0x180189008`
- `0x1801898b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013ec7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013ec7c`

## pseudocode

```c
__int64 __fastcall sub_18013EBDC(__int64 a1, __int128 *a2, int a3, int a4, _DWORD *a5, _QWORD *a6)
{
  __int128 *v10; // rax
  int v11; // ebx
  int v12; // ebx
  int v13; // r9d
  __int64 v14; // rcx

  if ( (xmmword_1801FAD20 & 2) != 0 )
  {
    v10 = a2;
    if ( !a2 )
      v10 = &xmmword_1801C8290;
    sub_1801898B4(1025, 165, (unsigned int)qword_1801DA730, a1, (__int64)v10);
  }
  if ( a5 && (*a5 = 0, a6) )
  {
    *a6 = 0;
    if ( a2 )
    {
      if ( !*(_DWORD *)(a1 + 48) || (v12 = *(_DWORD *)(a1 + 48), v12 == GetCurrentThreadId()) )
        v11 = sub_18013DE14(*(_QWORD *)(a1 + 40), (_DWORD)a2, a3, a4, (__int64)a5, (__int64)a6);
      else
        v11 = -2147417842;
    }
    else
    {
      v11 = -2147024809;
    }
  }
  else
  {
    v11 = -2147467261;
  }
  v13 = v11 >> 31;
  if ( (xmmword_1801FAD00[(v11 >> 31) + 2] & 2) != 0 )
  {
    v14 = (unsigned __int16)(v13 + 2) << 9;
    LOWORD(v14) = (((_WORD)v13 + 2) << 9) | 1;
    sub_180189008(v14, 166, qword_1801DA730, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18013ebdc  mov     r11, rsp
0x18013ebdf  push    rbx
0x18013ebe0  push    rbp
0x18013ebe1  push    rsi
0x18013ebe2  push    rdi
0x18013ebe3  push    r12
0x18013ebe5  push    r14
0x18013ebe7  push    r15
0x18013ebe9  sub     rsp, 50h
0x18013ebed  mov     r15, r9
0x18013ebf0  mov     r12d, r8d
0x18013ebf3  mov     r14, rdx
0x18013ebf6  mov     rbp, rcx
0x18013ebf9  mov     rdi, [rsp+88h+arg_28]
0x18013ec01  xor     ebx, ebx
0x18013ec03  test    byte ptr cs:xmmword_1801FAD20, 2
0x18013ec0a  mov     rsi, [rsp+88h+arg_20]
0x18013ec12  jz      short loc_18013EC52
0x18013ec14  mov     [r11-48h], rdi
0x18013ec18  lea     rcx, xmmword_1801C8290
0x18013ec1f  mov     [r11-50h], rsi
0x18013ec23  test    rdx, rdx
0x18013ec26  mov     [r11-58h], r9
0x18013ec2a  mov     rax, rdx
0x18013ec2d  cmovz   rax, rcx
0x18013ec31  mov     [r11-60h], r8d
0x18013ec35  mov     ecx, 401h
0x18013ec3a  mov     [r11-68h], rax
0x18013ec3e  lea     r8, qword_1801DA730
0x18013ec45  mov     edx, 0A5h
0x18013ec4a  mov     r9, rbp
0x18013ec4d  call    sub_1801898B4
0x18013ec52  test    rsi, rsi
0x18013ec55  jnz     short loc_18013EC5E
0x18013ec57  mov     ebx, 80004003h
0x18013ec5c  jmp     short loc_18013ECB1
0x18013ec5e  mov     [rsi], ebx
0x18013ec60  test    rdi, rdi
0x18013ec63  jz      short loc_18013EC57
0x18013ec65  mov     [rdi], rbx
0x18013ec68  test    r14, r14
0x18013ec6b  jnz     short loc_18013EC74
0x18013ec6d  mov     ebx, 80070057h
0x18013ec72  jmp     short loc_18013ECB1
0x18013ec74  cmp     [rbp+30h], ebx
0x18013ec77  jz      short loc_18013EC93
0x18013ec79  mov     ebx, [rbp+30h]
0x18013ec7c  call    cs:GetCurrentThreadId
0x18013ec83  nop     dword ptr [rax+rax+00h]
0x18013ec88  cmp     ebx, eax
0x18013ec8a  jz      short loc_18013EC93
0x18013ec8c  mov     ebx, 8001010Eh
0x18013ec91  jmp     short loc_18013ECB1
0x18013ec93  mov     rcx, [rbp+28h]
0x18013ec97  mov     r9, r15
0x18013ec9a  mov     [rsp+88h+var_60], rdi
0x18013ec9f  mov     r8d, r12d
0x18013eca2  mov     rdx, r14
0x18013eca5  mov     [rsp+88h+var_68], rsi
0x18013ecaa  call    sub_18013DE14
0x18013ecaf  mov     ebx, eax
0x18013ecb1  mov     r9d, ebx
0x18013ecb4  lea     rax, xmmword_1801FAD00
0x18013ecbb  sar     r9d, 1Fh
0x18013ecbf  lea     ecx, ds:4[r9*2]
0x18013ecc7  movsxd  rdx, ecx
0x18013ecca  test    byte ptr [rax+rdx*8], 2
0x18013ecce  jz      short loc_18013ECF9
0x18013ecd0  add     r9w, 2
0x18013ecd5  lea     r8, qword_1801DA730
0x18013ecdc  movzx   ecx, r9w
0x18013ece0  mov     eax, 200h
0x18013ece5  imul    ecx, eax
0x18013ece8  mov     edx, 0A6h
0x18013eced  mov     r9d, ebx
0x18013ecf0  or      cx, 1
0x18013ecf4  call    sub_180189008
0x18013ecf9  mov     eax, ebx
0x18013ecfb  add     rsp, 50h
0x18013ecff  pop     r15
0x18013ed01  pop     r14
0x18013ed03  pop     r12
0x18013ed05  pop     rdi
0x18013ed06  pop     rsi
0x18013ed07  pop     rbp
0x18013ed08  pop     rbx
0x18013ed09  retn
```
