# UpdateDirectoryCacheEntry

- ea: `0x140015ce0`
- end: `0x140016012`
- name: `UpdateDirectoryCacheEntry`
- size: `818`
- prototype: `__int16 __fastcall(__int64, __int64 *, char, __int64, int, PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140015780`

## callees

- `0x140015ce0`

## import_xrefs

- `ntoskrnl!RtlFindMostSignificantBit` at `0x140015d5f`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140015f12`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140015d5f`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x140015f12`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015e33`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015fbc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015e33`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015fbc`

## pseudocode

```c
__int16 __fastcall UpdateDirectoryCacheEntry(
        __int64 a1,
        __int64 *a2,
        char a3,
        __int64 a4,
        int a5,
        PCUNICODE_STRING String1)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  int v11; // ecx
  unsigned int v13; // ebp
  CCHAR MostSignificantBit; // al
  __int64 v15; // rbx
  unsigned int v16; // ecx
  __int64 v17; // rdx
  __int16 v18; // cx
  unsigned int v19; // ebp
  CCHAR v20; // al
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING v23; // [rsp+30h] [rbp-18h] BYREF

  v6 = *a2;
  v7 = HIDWORD(*a2);
  String2 = 0;
  v23 = 0;
  if ( (_DWORD)v7 != *(_DWORD *)(a1 + 40) || (int)v6 >= 0 )
    return v6;
  v11 = v6;
  if ( !(((unsigned int)v6 >> 30) & 1) )
  {
    LOWORD(v6) = v11;
    if ( (v11 & 0x3FFFFFFFu) < *(_DWORD *)(a1 + 124) )
    {
      v13 = *(_DWORD *)(*(_QWORD *)(a1 + 136) + 4LL * (v11 & 0x3FFFFFFF));
      MostSignificantBit = RtlFindMostSignificantBit(v13);
      v15 = 0;
      if ( MostSignificantBit <= 4 )
      {
        v6 = 0;
      }
      else
      {
        v6 = (unsigned int)(MostSignificantBit - 3) >> 1;
        if ( (unsigned int)v6 >= 8 )
          goto LABEL_32;
      }
      _mm_lfence();
      if ( (_DWORD)v6 )
        v16 = v13 - (32 << (2 * v6 - 2));
      else
        v16 = v13;
      v17 = *(_QWORD *)(a1 + 8 * v6 + 152);
      if ( v17 && v13 < *(_DWORD *)(a1 + 216) )
      {
LABEL_11:
        v15 = v17 + (v16 << 7);
        goto LABEL_12;
      }
      goto LABEL_32;
    }
LABEL_40:
    __int2c();
    return v6;
  }
  LOWORD(v6) = v11;
  if ( (v11 & 0x3FFFFFFFu) >= *(_DWORD *)(a1 + 128) )
    goto LABEL_40;
  v19 = *(_DWORD *)(*(_QWORD *)(a1 + 144) + 4LL * (v11 & 0x3FFFFFFF));
  v20 = RtlFindMostSignificantBit(v19);
  v15 = 0;
  if ( v20 <= 4 )
  {
    v6 = 0;
  }
  else
  {
    v6 = (unsigned int)(v20 - 3) >> 1;
    if ( (unsigned int)v6 >= 8 )
      goto LABEL_32;
  }
  _mm_lfence();
  if ( (_DWORD)v6 )
    v16 = v19 - (32 << (2 * v6 - 2));
  else
    v16 = v19;
  v17 = *(_QWORD *)(a1 + 8 * v6 + 152);
  if ( v17 && v19 < *(_DWORD *)(a1 + 216) )
    goto LABEL_11;
LABEL_32:
  __int2c();
LABEL_12:
  if ( !v15 )
    return v6;
  if ( String1 )
  {
    if ( (*(_BYTE *)(v15 + 84) & 5) == 0 )
    {
      String2.MaximumLength = 2 * (*(_WORD *)(v15 + 86) >> 4);
      String2.Length = String2.MaximumLength;
      String2.Buffer = (PWSTR)(v15 + 2 * ((*(_WORD *)(v15 + 86) & 0xF) + 44LL));
      v23.MaximumLength = 2 * (*(_WORD *)(v15 + 86) & 0xF);
      v23.Length = v23.MaximumLength;
      v23.Buffer = (PWSTR)(v15 + 88);
      if ( !RtlEqualUnicodeString(String1, &String2, 1u) && !RtlEqualUnicodeString(String1, &v23, 1u) )
        __int2c();
    }
  }
  LOWORD(v6) = *(_WORD *)(v15 + 84);
  if ( a3 )
  {
    if ( (v6 & 4) != 0 && (v6 & 1) == 0 )
    {
      LOWORD(v6) = v6 & 0xFFFB;
      *(_WORD *)(v15 + 84) = v6;
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 56));
    }
    v18 = *(_WORD *)(v15 + 84);
    if ( (v18 & 4) != 0 || (v18 & 1) == 0 )
      goto LABEL_20;
    *(_WORD *)(v15 + 84) = v18 | 4;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 56));
  }
  else
  {
    if ( (v6 & 4) != 0 )
    {
      LOWORD(v6) = v6 & 0xFFFB;
      *(_WORD *)(v15 + 84) = v6;
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 56));
    }
    v18 = *(_WORD *)(v15 + 84);
    if ( (v18 & 1) == 0 )
      goto LABEL_20;
    LOWORD(v6) = -2;
    *(_WORD *)(v15 + 84) = v18 & 0xFFFE;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 60));
  }
  v18 = *(_WORD *)(v15 + 84);
LABEL_20:
  if ( a4 )
  {
    *(_QWORD *)(v15 + 40) = *(_QWORD *)(a4 + 32);
    *(_QWORD *)(v15 + 24) = *(_QWORD *)(a4 + 24);
    *(_QWORD *)v15 = *(_QWORD *)a4;
    *(_QWORD *)(v15 + 32) = *(_QWORD *)(a4 + 40);
    *(_DWORD *)(v15 + 72) = *(_DWORD *)(a4 + 48);
    *(_QWORD *)(v15 + 8) = *(_QWORD *)(a4 + 8);
    v6 = *(_QWORD *)(a4 + 16);
    *(_QWORD *)(v15 + 16) = v6;
  }
  if ( (v18 & 2) == 0 )
  {
    *(_WORD *)(v15 + 84) = v18 | 2;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 64));
  }
  return v6;
}

```

## disassembly

```asm
0x140015ce0  mov     [rsp+arg_10], rsi
0x140015ce5  mov     [rsp+arg_18], rdi
0x140015cea  push    r14
0x140015cec  sub     rsp, 40h
0x140015cf0  mov     rax, [rdx]
0x140015cf3  xorps   xmm0, xmm0
0x140015cf6  mov     rdx, rax
0x140015cf9  xorps   xmm1, xmm1
0x140015cfc  shr     rdx, 20h
0x140015d00  mov     rsi, r9
0x140015d03  movzx   r14d, r8b
0x140015d07  mov     rdi, rcx
0x140015d0a  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x140015d0f  movups  xmmword ptr [rsp+48h+var_18.Length], xmm1
0x140015d14  cmp     edx, [rcx+28h]
0x140015d17  jnz     loc_140015EC1
0x140015d1d  test    eax, eax
0x140015d1f  jns     loc_140015EC1
0x140015d25  mov     ecx, eax
0x140015d27  mov     [rsp+48h+arg_0], rbx
0x140015d2c  shr     eax, 1Eh
0x140015d2f  mov     [rsp+48h+arg_8], rbp
0x140015d34  and     eax, 1
0x140015d37  jnz     loc_140015EE8
0x140015d3d  mov     eax, ecx
0x140015d3f  and     eax, 3FFFFFFFh
0x140015d44  cmp     eax, [rdi+7Ch]
0x140015d47  jnb     loc_140015FA3
0x140015d4d  mov     rax, [rdi+88h]
0x140015d54  and     ecx, 3FFFFFFFh
0x140015d5a  mov     ebp, [rax+rcx*4]
0x140015d5d  mov     ecx, ebp; Set
0x140015d5f  call    cs:__imp_RtlFindMostSignificantBit
0x140015d66  nop     dword ptr [rax+rax+00h]
0x140015d6b  xor     ebx, ebx
0x140015d6d  cmp     al, 4
0x140015d6f  jle     loc_140015F6A
0x140015d75  movsx   eax, al
0x140015d78  sub     eax, 3
0x140015d7b  shr     eax, 1
0x140015d7d  cmp     eax, 8
0x140015d80  jnb     loc_140015FAA
0x140015d86  lfence
0x140015d89  test    eax, eax
0x140015d8b  jz      loc_140015F71
0x140015d91  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140015d98  mov     edx, 20h ; ' '
0x140015d9d  shl     edx, cl
0x140015d9f  mov     ecx, ebp
0x140015da1  sub     ecx, edx
0x140015da3  mov     rdx, [rdi+rax*8+98h]
0x140015dab  test    rdx, rdx
0x140015dae  jz      loc_140015F87
0x140015db4  cmp     ebp, [rdi+0D8h]
0x140015dba  jnb     loc_140015F8E
0x140015dc0  shl     ecx, 7
0x140015dc3  mov     ebx, ecx
0x140015dc5  add     rbx, rdx
0x140015dc8  test    rbx, rbx
0x140015dcb  jz      loc_140015EB7
0x140015dd1  mov     rbp, [rsp+48h+String1]
0x140015dd6  test    rbp, rbp
0x140015dd9  jz      short loc_140015E47
0x140015ddb  test    byte ptr [rbx+54h], 5
0x140015ddf  jnz     short loc_140015E47
0x140015de1  movzx   eax, word ptr [rbx+56h]
0x140015de5  lea     rdx, [rsp+48h+String2]; String2
0x140015dea  shr     ax, 4
0x140015dee  mov     r8b, 1; CaseInSensitive
0x140015df1  add     ax, ax
0x140015df4  mov     rcx, rbp; String1
0x140015df7  mov     [rsp+48h+String2.MaximumLength], ax
0x140015dfc  mov     [rsp+48h+String2.Length], ax
0x140015e01  movzx   eax, word ptr [rbx+56h]
0x140015e05  and     eax, 0Fh
0x140015e08  add     rax, 2Ch ; ','
0x140015e0c  lea     rax, [rbx+rax*2]
0x140015e10  mov     [rsp+48h+String2.Buffer], rax
0x140015e15  movzx   eax, word ptr [rbx+56h]
0x140015e19  and     ax, 0Fh
0x140015e1d  add     ax, ax
0x140015e20  mov     [rsp+48h+var_18.MaximumLength], ax
0x140015e25  mov     [rsp+48h+var_18.Length], ax
0x140015e2a  lea     rax, [rbx+58h]
0x140015e2e  mov     [rsp+48h+var_18.Buffer], rax
0x140015e33  call    cs:__imp_RtlEqualUnicodeString
0x140015e3a  nop     dword ptr [rax+rax+00h]
0x140015e3f  test    al, al
0x140015e41  jz      loc_140015FB1
0x140015e47  movzx   eax, word ptr [rbx+54h]
0x140015e4b  movzx   ecx, ax
0x140015e4e  and     cx, 4
0x140015e52  test    r14b, r14b
0x140015e55  jnz     loc_140015FD7
0x140015e5b  test    cx, cx
0x140015e5e  jnz     short loc_140015ED3
0x140015e60  movzx   ecx, word ptr [rbx+54h]
0x140015e64  test    cl, 1
0x140015e67  jnz     loc_140015FFD
0x140015e6d  test    rsi, rsi
0x140015e70  jz      short loc_140015EA6
0x140015e72  mov     rax, [rsi+20h]
0x140015e76  mov     [rbx+28h], rax
0x140015e7a  mov     rax, [rsi+18h]
0x140015e7e  mov     [rbx+18h], rax
0x140015e82  mov     rax, [rsi]
0x140015e85  mov     [rbx], rax
0x140015e88  mov     rax, [rsi+28h]
0x140015e8c  mov     [rbx+20h], rax
0x140015e90  mov     eax, [rsi+30h]
0x140015e93  mov     [rbx+48h], eax
0x140015e96  mov     rax, [rsi+8]
0x140015e9a  mov     [rbx+8], rax
0x140015e9e  mov     rax, [rsi+10h]
0x140015ea2  mov     [rbx+10h], rax
0x140015ea6  test    cl, 2
0x140015ea9  jnz     short loc_140015EB7
0x140015eab  or      cx, 2
0x140015eaf  mov     [rbx+54h], cx
0x140015eb3  lock inc dword ptr [rdi+40h]
0x140015eb7  mov     rbx, [rsp+48h+arg_0]
0x140015ebc  mov     rbp, [rsp+48h+arg_8]
0x140015ec1  mov     rsi, [rsp+48h+arg_10]
0x140015ec6  mov     rdi, [rsp+48h+arg_18]
0x140015ecb  add     rsp, 40h
0x140015ecf  pop     r14
0x140015ed1  retn
0x140015ed3  mov     ecx, 0FFFBh
0x140015ed8  and     ax, cx
0x140015edb  mov     [rbx+54h], ax
0x140015edf  lock dec dword ptr [rdi+38h]
0x140015ee3  jmp     loc_140015E60
0x140015ee8  cmp     eax, 1
0x140015eeb  jnz     short loc_140015EB7
0x140015eed  mov     eax, ecx
0x140015eef  and     eax, 3FFFFFFFh
0x140015ef4  cmp     eax, [rdi+80h]
0x140015efa  jnb     loc_140015F95
0x140015f00  mov     rax, [rdi+90h]
0x140015f07  and     ecx, 3FFFFFFFh
0x140015f0d  mov     ebp, [rax+rcx*4]
0x140015f10  mov     ecx, ebp; Set
0x140015f12  call    cs:__imp_RtlFindMostSignificantBit
0x140015f19  nop     dword ptr [rax+rax+00h]
0x140015f1e  xor     ebx, ebx
0x140015f20  cmp     al, 4
0x140015f22  jle     short loc_140015F78
0x140015f24  movsx   eax, al
0x140015f27  sub     eax, 3
0x140015f2a  shr     eax, 1
0x140015f2c  cmp     eax, 8
0x140015f2f  jnb     short loc_140015F9C
0x140015f31  lfence
0x140015f34  test    eax, eax
0x140015f36  jz      short loc_140015F7C
0x140015f38  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140015f3f  mov     edx, 20h ; ' '
0x140015f44  shl     edx, cl
0x140015f46  mov     ecx, ebp
0x140015f48  sub     ecx, edx
0x140015f4a  mov     rdx, [rdi+rax*8+98h]
0x140015f52  test    rdx, rdx
0x140015f55  jz      short loc_140015F80
0x140015f57  cmp     ebp, [rdi+0D8h]
0x140015f5d  jb      loc_140015DC0
0x140015f63  int     2Ch; Windows NT - assertion failure
0x140015f65  jmp     loc_140015DC8
0x140015f6a  mov     eax, ebx
0x140015f6c  jmp     loc_140015D86
0x140015f71  mov     ecx, ebp
0x140015f73  jmp     loc_140015DA3
0x140015f78  mov     eax, ebx
0x140015f7a  jmp     short loc_140015F31
0x140015f7c  mov     ecx, ebp
0x140015f7e  jmp     short loc_140015F4A
0x140015f80  int     2Ch; Windows NT - assertion failure
0x140015f82  jmp     loc_140015DC8
0x140015f87  int     2Ch; Windows NT - assertion failure
0x140015f89  jmp     loc_140015DC8
0x140015f8e  int     2Ch; Windows NT - assertion failure
0x140015f90  jmp     loc_140015DC8
0x140015f95  int     2Ch; Windows NT - assertion failure
0x140015f97  jmp     loc_140015EB7
0x140015f9c  int     2Ch; Windows NT - assertion failure
0x140015f9e  jmp     loc_140015DC8
0x140015fa3  int     2Ch; Windows NT - assertion failure
0x140015fa5  jmp     loc_140015EB7
0x140015faa  int     2Ch; Windows NT - assertion failure
0x140015fac  jmp     loc_140015DC8
0x140015fb1  mov     r8b, 1; CaseInSensitive
0x140015fb4  lea     rdx, [rsp+48h+var_18]; String2
0x140015fb9  mov     rcx, rbp; String1
0x140015fbc  call    cs:__imp_RtlEqualUnicodeString
0x140015fc3  nop     dword ptr [rax+rax+00h]
0x140015fc8  test    al, al
0x140015fca  jnz     loc_140015E47
0x140015fd0  int     2Ch; Windows NT - assertion failure
0x140015fd2  jmp     loc_140015E47
0x140015fd7  test    cx, cx
0x140015fda  jz      loc_14003B550
0x140015fe0  test    al, 1
0x140015fe2  jnz     loc_14003B550
0x140015fe8  mov     ecx, 0FFFBh
0x140015fed  and     ax, cx
0x140015ff0  mov     [rbx+54h], ax
0x140015ff4  lock dec dword ptr [rdi+38h]
0x140015ff8  jmp     loc_14003B550
0x140015ffd  mov     eax, 0FFFEh
0x140016002  and     cx, ax
0x140016005  mov     [rbx+54h], cx
0x140016009  lock dec dword ptr [rdi+3Ch]
0x14001600d  jmp     loc_14003B572
0x14003b550  movzx   ecx, word ptr [rbx+54h]
0x14003b554  test    cl, 4
0x14003b557  jnz     loc_140015E6D
0x14003b55d  test    cl, 1
0x14003b560  jz      loc_140015E6D
0x14003b566  or      cx, 4
0x14003b56a  mov     [rbx+54h], cx
0x14003b56e  lock inc dword ptr [rdi+38h]
0x14003b572  movzx   ecx, word ptr [rbx+54h]
0x14003b576  jmp     loc_140015E6D
```
