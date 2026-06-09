# TracingFailureDetails::HashFunctionTemplate(char const *,char *)

- ea: `0x180004d20`
- end: `0x180004e08`
- name: `?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z`
- size: `232`
- prototype: `static bool(const char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800026d8`

## callees

- `0x180004ce8`
- `0x180004d20`
- `0x180004e10`
- `0x180005039`

## pseudocode

```c
char __fastcall TracingFailureDetails::HashFunctionTemplate(const char *a1, char *a2)
{
  char v2; // bl
  __int64 v4; // rdi
  __int64 i; // rax
  __int64 v6; // rbp
  unsigned int v7; // esi
  const char *v8; // r15
  unsigned int v9; // r8d
  const void *v10; // r11
  unsigned int v11; // r8d
  unsigned __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  v13 = 0xCBF29CE484222325uLL;
  if ( a1 && a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
    for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)v6 )
    {
      v6 = (unsigned int)(i + 1);
      if ( a1[i] == 60 )
      {
        v7 = v4;
        do
          v8 = &a1[--v7];
        while ( *v8 != 62 && v7 > (unsigned int)v6 );
        if ( (_DWORD)v6 != v7 )
        {
          v9 = v7 - v6;
          if ( v7 - (unsigned int)v6 > 0x10 && (unsigned int)v4 - v9 + 17 < 0x100 )
          {
            HashFNV::HashData((HashFNV *)&v13, (unsigned __int8 *)&a1[v6], v9);
            memcpy_0(a2, v10, (unsigned int)v6);
            HashToString((unsigned __int8 *)&v13, &a2[v6], v11);
            v2 = 1;
            memcpy_0(&a2[(unsigned int)(v6 + 16)], v8, (unsigned int)v4 - v7 + 1);
          }
        }
        return v2;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180004d20  push    rbx
0x180004d22  push    rbp
0x180004d23  push    rsi
0x180004d24  push    rdi
0x180004d25  push    r14
0x180004d27  push    r15
0x180004d29  sub     rsp, 28h
0x180004d2d  xor     bl, bl
0x180004d2f  mov     rax, 0CBF29CE484222325h
0x180004d39  mov     [rsp+58h+arg_0], rax
0x180004d3e  mov     r14, rdx
0x180004d41  mov     r11, rcx
0x180004d44  test    rcx, rcx
0x180004d47  jz      loc_180004DF9
0x180004d4d  test    rdx, rdx
0x180004d50  jz      loc_180004DF9
0x180004d56  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004d5a  inc     rdi
0x180004d5d  cmp     [rcx+rdi], bl
0x180004d60  jnz     short loc_180004D5A
0x180004d62  xor     eax, eax
0x180004d64  cmp     eax, edi
0x180004d66  jnb     loc_180004DF9
0x180004d6c  cmp     byte ptr [rax+rcx], 3Ch ; '<'
0x180004d70  lea     ebp, [rax+1]
0x180004d73  jz      short loc_180004D79
0x180004d75  mov     eax, ebp
0x180004d77  jmp     short loc_180004D64
0x180004d79  mov     esi, edi
0x180004d7b  dec     esi
0x180004d7d  mov     r15d, esi
0x180004d80  add     r15, r11
0x180004d83  cmp     byte ptr [r15], 3Eh ; '>'
0x180004d87  jz      short loc_180004D8D
0x180004d89  cmp     esi, ebp
0x180004d8b  ja      short loc_180004D7B
0x180004d8d  cmp     ebp, esi
0x180004d8f  jz      short loc_180004DF9
0x180004d91  mov     r8d, esi
0x180004d94  sub     r8d, ebp; unsigned int
0x180004d97  cmp     r8d, 10h
0x180004d9b  jbe     short loc_180004DF9
0x180004d9d  mov     eax, edi
0x180004d9f  sub     eax, r8d
0x180004da2  add     eax, 11h
0x180004da5  cmp     eax, 100h
0x180004daa  jnb     short loc_180004DF9
0x180004dac  lea     rdx, [rcx+rbp]; unsigned __int8 *
0x180004db0  lea     rcx, [rsp+58h+arg_0]; this
0x180004db5  call    ?HashData@HashFNV@@QEAA_KPEAEK@Z; HashFNV::HashData(uchar *,ulong)
0x180004dba  mov     rcx, [rsp+58h+arg_0]
0x180004dbf  mov     rdx, r11; Src
0x180004dc2  mov     [rsp+58h+arg_0], rcx
0x180004dc7  mov     rcx, r14; void *
0x180004dca  mov     r8d, ebp; Size
0x180004dcd  call    memcpy_0
0x180004dd2  lea     rdx, [r14+rbp]; char *
0x180004dd6  lea     rcx, [rsp+58h+arg_0]; unsigned __int8 *
0x180004ddb  call    ?HashToString@@YA_NPEAEPEADK@Z; HashToString(uchar *,char *,ulong)
0x180004de0  sub     edi, esi
0x180004de2  lea     ecx, [rbp+10h]
0x180004de5  mov     ebx, 1
0x180004dea  add     rcx, r14; void *
0x180004ded  mov     rdx, r15; Src
0x180004df0  lea     r8d, [rbx+rdi]; Size
0x180004df4  call    memcpy_0
0x180004df9  mov     al, bl
0x180004dfb  add     rsp, 28h
0x180004dff  pop     r15
0x180004e01  pop     r14
0x180004e03  pop     rdi
0x180004e04  pop     rsi
0x180004e05  pop     rbp
0x180004e06  pop     rbx
0x180004e07  retn
```
