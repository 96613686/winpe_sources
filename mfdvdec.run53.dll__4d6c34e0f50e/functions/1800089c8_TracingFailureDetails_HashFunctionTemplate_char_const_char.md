# TracingFailureDetails::HashFunctionTemplate(char const *,char *)

- ea: `0x1800089c8`
- end: `0x180008ade`
- name: `?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z`
- size: `278`
- prototype: `bool __fastcall(const char *Src, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008b64`

## callees

- `0x1800089c8`
- `0x180008ae4`
- `0x18001d369`

## pseudocode

```c
char __fastcall TracingFailureDetails::HashFunctionTemplate(const char *Src, char *a2)
{
  char v2; // bp
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  unsigned int v8; // edi
  const char *v9; // r15
  unsigned int v10; // ecx
  const char *v11; // r8
  __int64 v12; // rax
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  if ( Src )
  {
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( Src[v5] );
      v6 = 0;
      if ( (_DWORD)v5 )
      {
        while ( 1 )
        {
          v7 = (unsigned int)(v6 + 1);
          if ( Src[v6] == 60 )
            break;
          v6 = (unsigned int)v7;
          if ( (unsigned int)v7 >= (unsigned int)v5 )
            return v2;
        }
        v8 = v5;
        do
          v9 = &Src[--v8];
        while ( *v9 != 62 && v8 > (unsigned int)v7 );
        if ( (_DWORD)v7 != v8 )
        {
          v10 = v8 - v7;
          if ( v8 - (unsigned int)v7 > 0x10 && (unsigned int)v5 - v10 + 17 < 0x100 )
          {
            v11 = &Src[v7];
            v12 = 0xCBF29CE484222325uLL;
            v2 = 1;
            while ( v11 < &Src[v7 + v10] )
              v12 = 0x100000001B3LL * (*(unsigned __int8 *)v11++ ^ (unsigned __int64)v12);
            v15 = v12;
            memcpy_0(a2, Src, (unsigned int)v7);
            HashToString((unsigned __int8 *)&v15, &a2[v7], v13);
            memcpy_0(&a2[(unsigned int)(v7 + 16)], v9, (unsigned int)v5 - v8 + 1);
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800089c8  mov     [rsp+arg_8], rbx
0x1800089cd  mov     [rsp+arg_10], rbp
0x1800089d2  push    rsi
0x1800089d3  push    rdi
0x1800089d4  push    r12
0x1800089d6  push    r14
0x1800089d8  push    r15
0x1800089da  sub     rsp, 20h
0x1800089de  xor     bpl, bpl
0x1800089e1  mov     r14, rdx
0x1800089e4  mov     rdx, rcx; Src
0x1800089e7  test    rcx, rcx
0x1800089ea  jz      loc_180008AC4
0x1800089f0  test    r14, r14
0x1800089f3  jz      loc_180008AC4
0x1800089f9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800089fd  inc     rbx
0x180008a00  cmp     [rcx+rbx], bpl
0x180008a04  jnz     short loc_1800089FD
0x180008a06  xor     eax, eax
0x180008a08  test    ebx, ebx
0x180008a0a  jz      loc_180008AC4
0x180008a10  cmp     byte ptr [rax+rcx], 3Ch ; '<'
0x180008a14  lea     esi, [rax+1]
0x180008a17  jz      short loc_180008A24
0x180008a19  mov     eax, esi
0x180008a1b  cmp     esi, ebx
0x180008a1d  jb      short loc_180008A10
0x180008a1f  jmp     loc_180008AC4
0x180008a24  mov     edi, ebx
0x180008a26  dec     edi
0x180008a28  mov     r15d, edi
0x180008a2b  add     r15, rdx
0x180008a2e  cmp     byte ptr [r15], 3Eh ; '>'
0x180008a32  jz      short loc_180008A38
0x180008a34  cmp     edi, esi
0x180008a36  ja      short loc_180008A26
0x180008a38  cmp     esi, edi
0x180008a3a  jz      loc_180008AC4
0x180008a40  mov     ecx, edi
0x180008a42  sub     ecx, esi
0x180008a44  cmp     ecx, 10h
0x180008a47  jbe     short loc_180008AC4
0x180008a49  mov     eax, ebx
0x180008a4b  sub     eax, ecx
0x180008a4d  add     eax, 11h
0x180008a50  cmp     eax, 100h
0x180008a55  jnb     short loc_180008AC4
0x180008a57  lea     r8, [rsi+rdx]
0x180008a5b  mov     r9d, ecx
0x180008a5e  add     r9, r8
0x180008a61  mov     r12d, esi
0x180008a64  mov     rax, 0CBF29CE484222325h
0x180008a6e  mov     ebp, 1
0x180008a73  jmp     short loc_180008A8D
0x180008a75  movzx   ecx, byte ptr [r8]
0x180008a79  mov     r10, 100000001B3h
0x180008a83  xor     rax, rcx
0x180008a86  imul    rax, r10
0x180008a8a  add     r8, rbp
0x180008a8d  cmp     r8, r9
0x180008a90  jb      short loc_180008A75
0x180008a92  mov     r8, r12; Size
0x180008a95  mov     [rsp+48h+arg_0], rax
0x180008a9a  mov     rcx, r14; void *
0x180008a9d  call    memcpy_0
0x180008aa2  lea     rdx, [rsi+r14]; char *
0x180008aa6  lea     rcx, [rsp+48h+arg_0]; unsigned __int8 *
0x180008aab  call    ?HashToString@@YA_NPEAEPEADK@Z; HashToString(uchar *,char *,ulong)
0x180008ab0  sub     ebx, edi
0x180008ab2  lea     ecx, [rsi+10h]
0x180008ab5  add     rcx, r14; void *
0x180008ab8  mov     rdx, r15; Src
0x180008abb  lea     r8d, [rbx+rbp]; Size
0x180008abf  call    memcpy_0
0x180008ac4  mov     rbx, [rsp+48h+arg_8]
0x180008ac9  mov     al, bpl
0x180008acc  mov     rbp, [rsp+48h+arg_10]
0x180008ad1  add     rsp, 20h
0x180008ad5  pop     r15
0x180008ad7  pop     r14
0x180008ad9  pop     r12
0x180008adb  pop     rdi
0x180008adc  pop     rsi
0x180008add  retn
```
