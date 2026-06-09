# ConfigReadRegistryOne

- ea: `0x14000ab10`
- end: `0x14000acca`
- name: `ConfigReadRegistryOne`
- size: `442`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000a9fc`

## callees

- `0x140003dc0`
- `0x14000ab10`
- `0x14000ae34`

## pseudocode

```c
__int64 __fastcall ConfigReadRegistryOne(HANDLE KeyHandle, _WORD *a2, unsigned int a3)
{
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 result; // rax
  _WORD *v9; // r8
  __int64 v10; // rdx
  _WORD *v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // rax
  __int64 v14; // r8
  wchar_t *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  _WORD *v18; // rcx
  __int64 v19; // r8
  unsigned int i; // edx
  unsigned int v21; // eax
  unsigned __int64 v22; // rcx
  _WORD v23[64]; // [rsp+30h] [rbp-C8h] BYREF

  v6 = 0;
  while ( dword_140006064[4 * v6] < 0 )
  {
LABEL_28:
    result = 2LL * ++v6;
    if ( !ConfigSetting[4 * v6] )
      return result;
  }
  v7 = 2147483646;
  result = (__int64)v23;
  v9 = a2;
  v10 = 64;
  do
  {
    if ( !v7 )
      break;
    if ( !*v9 )
      break;
    *(_WORD *)result = *v9++;
    result += 2;
    --v7;
    --v10;
  }
  while ( v10 );
  v11 = (_WORD *)(result - 2);
  if ( v10 )
    v11 = (_WORD *)result;
  *v11 = 0;
  if ( v10 )
  {
    v12 = 64;
    v13 = v23;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    result = -v12;
    v14 = (64 - v12) & -(__int64)(v12 != 0);
    if ( v12 )
    {
      v15 = (&off_140006068)[2 * v6];
      result = (__int64)&v23[v14];
      v16 = 2147483646;
      v17 = 64 - v14;
      if ( v14 != 64 )
      {
        do
        {
          if ( !v16 )
            break;
          if ( !*v15 )
            break;
          *(_WORD *)result = *v15++;
          result += 2;
          --v16;
          --v17;
        }
        while ( v17 );
      }
      v18 = (_WORD *)(result - 2);
      if ( v17 )
        v18 = (_WORD *)result;
      *v18 = 0;
      if ( v17 )
      {
        if ( (int)ReadDwordRegValue(KeyHandle) >= 0 )
        {
          v19 = dword_140006064[4 * v6];
          if ( (int)v19 >= 0 )
          {
            for ( i = a3; ; ++i )
            {
              v21 = 3;
              if ( a3 )
                v21 = a3 + 1;
              if ( i >= v21 )
                break;
              v22 = (unsigned __int64)i << 6;
              *(int *)((char *)g_config + v19 + v22) = 0;
            }
          }
        }
        goto LABEL_28;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ab10  mov     [rsp+arg_8], rbx
0x14000ab15  push    rbp
0x14000ab16  push    rsi
0x14000ab17  push    rdi
0x14000ab18  push    r12
0x14000ab1a  push    r13
0x14000ab1c  push    r14
0x14000ab1e  push    r15
0x14000ab20  sub     rsp, 0C0h
0x14000ab27  mov     rax, cs:__security_cookie
0x14000ab2e  xor     rax, rsp
0x14000ab31  mov     [rsp+0F8h+var_48], rax
0x14000ab39  xor     r15d, r15d
0x14000ab3c  lea     r12, cs:140000000h
0x14000ab43  mov     esi, r8d
0x14000ab46  mov     [rsp+0F8h+var_D8], r15d
0x14000ab4b  mov     rbp, rdx
0x14000ab4e  mov     r14, rcx
0x14000ab51  mov     edi, r15d
0x14000ab54  lea     r13d, [r15+40h]
0x14000ab58  mov     ebx, edi
0x14000ab5a  add     rbx, rbx
0x14000ab5d  cmp     ds:rva dword_140006064[r12+rbx*8], r15d
0x14000ab65  jl      loc_14000AC89
0x14000ab6b  mov     ecx, 7FFFFFFEh
0x14000ab70  lea     rax, [rsp+0F8h+var_C8]
0x14000ab75  mov     r8, rbp
0x14000ab78  mov     rdx, r13
0x14000ab7b  test    rcx, rcx
0x14000ab7e  jz      short loc_14000AB9F
0x14000ab80  movzx   r9d, word ptr [r8]
0x14000ab84  test    r9w, r9w
0x14000ab88  jz      short loc_14000AB9F
0x14000ab8a  mov     [rax], r9w
0x14000ab8e  add     r8, 2
0x14000ab92  add     rax, 2
0x14000ab96  dec     rcx
0x14000ab99  sub     rdx, 1
0x14000ab9d  jnz     short loc_14000AB7B
0x14000ab9f  test    rdx, rdx
0x14000aba2  lea     rcx, [rax-2]
0x14000aba6  cmovnz  rcx, rax
0x14000abaa  mov     [rcx], r15w
0x14000abae  jz      loc_14000AC9E
0x14000abb4  mov     rdx, r13
0x14000abb7  lea     rax, [rsp+0F8h+var_C8]
0x14000abbc  cmp     [rax], r15w
0x14000abc0  jz      short loc_14000ABCC
0x14000abc2  add     rax, 2
0x14000abc6  sub     rdx, 1
0x14000abca  jnz     short loc_14000ABBC
0x14000abcc  mov     rcx, r13
0x14000abcf  mov     rax, rdx
0x14000abd2  sub     rcx, rdx
0x14000abd5  neg     rax
0x14000abd8  sbb     r8, r8
0x14000abdb  and     r8, rcx
0x14000abde  test    rdx, rdx
0x14000abe1  jz      loc_14000AC9E
0x14000abe7  mov     r9, ds:rva off_140006068[r12+rbx*8]; "nHwThreads" ...
0x14000abef  lea     rax, [rsp+0F8h+var_C8]
0x14000abf4  mov     rdx, r13
0x14000abf7  lea     rax, [rax+r8*2]
0x14000abfb  mov     ecx, 7FFFFFFEh
0x14000ac00  sub     rdx, r8
0x14000ac03  jz      short loc_14000AC29
0x14000ac05  test    rcx, rcx
0x14000ac08  jz      short loc_14000AC29
0x14000ac0a  movzx   r8d, word ptr [r9]
0x14000ac0e  test    r8w, r8w
0x14000ac12  jz      short loc_14000AC29
0x14000ac14  mov     [rax], r8w
0x14000ac18  add     r9, 2
0x14000ac1c  add     rax, 2
0x14000ac20  dec     rcx
0x14000ac23  sub     rdx, 1
0x14000ac27  jnz     short loc_14000AC05
0x14000ac29  test    rdx, rdx
0x14000ac2c  lea     rcx, [rax-2]
0x14000ac30  cmovnz  rcx, rax
0x14000ac34  mov     [rcx], r15w
0x14000ac38  jz      short loc_14000AC9E
0x14000ac3a  lea     r8, [rsp+0F8h+var_D8]
0x14000ac3f  mov     rcx, r14; KeyHandle
0x14000ac42  lea     rdx, [rsp+0F8h+var_C8]
0x14000ac47  call    ReadDwordRegValue
0x14000ac4c  test    eax, eax
0x14000ac4e  js      short loc_14000AC89
0x14000ac50  movsxd  r8, ds:rva dword_140006064[r12+rbx*8]
0x14000ac58  test    r8d, r8d
0x14000ac5b  js      short loc_14000AC89
0x14000ac5d  mov     r9d, [rsp+0F8h+var_D8]
0x14000ac62  mov     edx, esi
0x14000ac64  mov     eax, 3
0x14000ac69  test    esi, esi
0x14000ac6b  jz      short loc_14000AC70
0x14000ac6d  lea     eax, [rsi+1]
0x14000ac70  cmp     edx, eax
0x14000ac72  jnb     short loc_14000AC89
0x14000ac74  mov     ecx, edx
0x14000ac76  shl     rcx, 6
0x14000ac7a  add     rcx, r8
0x14000ac7d  inc     edx
0x14000ac7f  mov     [rcx+r12+77E0h], r9d
0x14000ac87  jmp     short loc_14000AC64
0x14000ac89  inc     edi
0x14000ac8b  mov     eax, edi
0x14000ac8d  add     rax, rax
0x14000ac90  cmp     ds:rva ConfigSetting[r12+rax*8], r15d
0x14000ac98  jnz     loc_14000AB58
0x14000ac9e  mov     rcx, [rsp+0F8h+var_48]
0x14000aca6  xor     rcx, rsp; StackCookie
0x14000aca9  call    __security_check_cookie
0x14000acae  mov     rbx, [rsp+0F8h+arg_8]
0x14000acb6  add     rsp, 0C0h
0x14000acbd  pop     r15
0x14000acbf  pop     r14
0x14000acc1  pop     r13
0x14000acc3  pop     r12
0x14000acc5  pop     rdi
0x14000acc6  pop     rsi
0x14000acc7  pop     rbp
0x14000acc8  retn
```
