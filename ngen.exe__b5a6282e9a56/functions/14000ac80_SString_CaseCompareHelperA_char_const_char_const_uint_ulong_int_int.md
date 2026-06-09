# SString::CaseCompareHelperA(char const *,char const *,uint,ulong,int,int)

- ea: `0x14000ac80`
- end: `0x14000ad7e`
- name: `?CaseCompareHelperA@SString@@CAHPEBD0IKHH@Z`
- size: `254`
- prototype: `__int64 __fastcall(const char *, const char *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001374`
- `0x14000b898`

## callees

- `0x14000abe4`
- `0x14000ac80`

## import_xrefs

- `KERNEL32!IsDBCSLeadByte` at `0x14000ad09`
- `KERNEL32!IsDBCSLeadByte` at `0x14000ad16`
- `KERNEL32!IsDBCSLeadByte` at `0x14000ad09`
- `KERNEL32!IsDBCSLeadByte` at `0x14000ad16`

## pseudocode

```c
__int64 __fastcall SString::CaseCompareHelperA(const char *a1, const char *a2, int a3)
{
  const char *v4; // rbp
  const char *v5; // r14
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  int v8; // edi
  unsigned int v9; // ebx
  int v10; // eax
  bool v11; // zf
  unsigned int v12; // esi
  int CaseInsensitiveValueA; // ebx
  unsigned int v14; // ecx
  __int64 v15; // rax

  v4 = &a1[a3];
  v5 = a1;
  v6 = 0;
  while ( v5 < v4 )
  {
    v7 = *v5;
    v8 = *a2;
    if ( !*v5 || !(_BYTE)v8 )
    {
      v11 = v7 == v8;
      v6 = v7 - v8;
LABEL_21:
      if ( !v11 )
        return v6;
LABEL_22:
      v15 = 1;
      goto LABEL_23;
    }
    if ( (char)v7 >= 32 && (char)v8 >= 32 )
    {
      v6 = v7 - v8;
      if ( v7 != v8 )
      {
        v9 = v7 - 32;
        if ( (unsigned __int8)(v7 - 97) > 0x19u )
          v9 = *v5;
        v10 = v8 - 32;
        if ( (unsigned __int8)(v8 - 97) > 0x19u )
          v10 = *a2;
        v6 = v9 - v10;
        v11 = v6 == 0;
        goto LABEL_21;
      }
      goto LABEL_22;
    }
    v12 = 1;
    if ( SString::s_IsANSIMultibyte )
    {
      if ( IsDBCSLeadByte(v7) )
      {
        if ( IsDBCSLeadByte(v8) )
        {
          v7 = 2;
          if ( v5 + 1 < v4 )
            v12 = 2;
        }
      }
    }
    CaseInsensitiveValueA = GetCaseInsensitiveValueA(v7, v5, v12);
    v6 = CaseInsensitiveValueA - GetCaseInsensitiveValueA(v14, a2, v12);
    if ( v6 )
      return v6;
    v15 = v12;
LABEL_23:
    a2 += v15;
    v5 += v15;
  }
  return v6;
}

```

## disassembly

```asm
0x14000ac80  mov     [rsp+arg_0], rbx
0x14000ac85  mov     [rsp+arg_8], rbp
0x14000ac8a  mov     [rsp+arg_10], rsi
0x14000ac8f  push    rdi
0x14000ac90  push    r14
0x14000ac92  push    r15
0x14000ac94  sub     rsp, 20h
0x14000ac98  mov     ebp, r8d
0x14000ac9b  mov     r15, rdx
0x14000ac9e  add     rbp, rcx
0x14000aca1  mov     r14, rcx
0x14000aca4  xor     ebx, ebx
0x14000aca6  cmp     r14, rbp
0x14000aca9  jnb     loc_14000AD63
0x14000acaf  movsx   ecx, byte ptr [r14]; TestChar
0x14000acb3  movsx   edi, byte ptr [r15]
0x14000acb7  test    cl, cl
0x14000acb9  jz      loc_14000AD4D
0x14000acbf  test    dil, dil
0x14000acc2  jz      loc_14000AD4D
0x14000acc8  cmp     cl, 20h ; ' '
0x14000accb  jl      short loc_14000ACFB
0x14000accd  cmp     dil, 20h ; ' '
0x14000acd1  jl      short loc_14000ACFB
0x14000acd3  mov     ebx, ecx
0x14000acd5  mov     edx, edi
0x14000acd7  mov     eax, ecx
0x14000acd9  sub     ebx, edi
0x14000acdb  jz      short loc_14000AD53
0x14000acdd  sub     cl, 61h ; 'a'
0x14000ace0  lea     ebx, [rax-20h]
0x14000ace3  cmp     cl, 19h
0x14000ace6  cmova   ebx, eax
0x14000ace9  sub     dil, 61h ; 'a'
0x14000aced  cmp     dil, 19h
0x14000acf1  lea     eax, [rdx-20h]
0x14000acf4  cmova   eax, edx
0x14000acf7  sub     ebx, eax
0x14000acf9  jmp     short loc_14000AD51
0x14000acfb  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, 0; int SString::s_IsANSIMultibyte
0x14000ad02  mov     esi, 1
0x14000ad07  jz      short loc_14000AD2D
0x14000ad09  call    cs:__imp_IsDBCSLeadByte
0x14000ad0f  test    eax, eax
0x14000ad11  jz      short loc_14000AD2D
0x14000ad13  mov     cl, dil; TestChar
0x14000ad16  call    cs:__imp_IsDBCSLeadByte
0x14000ad1c  test    eax, eax
0x14000ad1e  jz      short loc_14000AD2D
0x14000ad20  lea     rax, [r14+1]
0x14000ad24  cmp     rax, rbp
0x14000ad27  lea     ecx, [rsi+1]; unsigned int
0x14000ad2a  cmovb   esi, ecx
0x14000ad2d  mov     r8d, esi; int
0x14000ad30  mov     rdx, r14; char *
0x14000ad33  call    ?GetCaseInsensitiveValueA@@YAHKPEBDH@Z; GetCaseInsensitiveValueA(ulong,char const *,int)
0x14000ad38  mov     r8d, esi; int
0x14000ad3b  mov     rdx, r15; char *
0x14000ad3e  mov     ebx, eax
0x14000ad40  call    ?GetCaseInsensitiveValueA@@YAHKPEBDH@Z; GetCaseInsensitiveValueA(ulong,char const *,int)
0x14000ad45  sub     ebx, eax
0x14000ad47  jnz     short loc_14000AD63
0x14000ad49  mov     eax, esi
0x14000ad4b  jmp     short loc_14000AD58
0x14000ad4d  mov     ebx, ecx
0x14000ad4f  sub     ebx, edi
0x14000ad51  jnz     short loc_14000AD63
0x14000ad53  mov     eax, 1
0x14000ad58  add     r15, rax
0x14000ad5b  add     r14, rax
0x14000ad5e  jmp     loc_14000ACA6
0x14000ad63  mov     rbp, [rsp+38h+arg_8]
0x14000ad68  mov     eax, ebx
0x14000ad6a  mov     rbx, [rsp+38h+arg_0]
0x14000ad6f  mov     rsi, [rsp+38h+arg_10]
0x14000ad74  add     rsp, 20h
0x14000ad78  pop     r15
0x14000ad7a  pop     r14
0x14000ad7c  pop     rdi
0x14000ad7d  retn
```
