# DebugPrintHR(long,char const *,char const *,int,char const *)

- ea: `0x18002c120`
- end: `0x18002c25e`
- name: `?DebugPrintHR@@YAJJPEBD0H0@Z`
- size: `318`
- prototype: `__int64 __fastcall(int, const char *, const char *, int, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18002c120`
- `0x18002e560`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18002c1f5`
- `msvcrt!sprintf_s` at `0x18002c1f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002c206`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002c226`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002c206`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002c226`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002c232`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002c232`

## string_xrefs

- `0x18002c21f`: `Breaking on configured error\n`

## pseudocode

```c
__int64 __fastcall DebugPrintHR(int a1, const char *a2, const char *a3, int a4, const char *a5)
{
  BOOL v8; // ecx
  __int64 i; // rdx
  int v10; // r8d
  __int64 j; // rdx
  int v12; // r8d
  char Buffer[400]; // [rsp+40h] [rbp-1C8h] BYREF

  if ( g_dwDebugPrintHR )
  {
    if ( (g_dwDebugPrintHR & 2) != 0 )
      goto LABEL_20;
    v8 = 0;
    if ( (g_dwDebugPrintHR & 1) != 0 )
      v8 = a1 < 0;
    if ( (_DWORD)g_NotifyOnErrors )
    {
      v8 = 0;
      for ( i = 0; (unsigned int)i < 0xA; i = (unsigned int)(i + 1) )
      {
        v10 = *((_DWORD *)&g_NotifyOnErrors + i);
        if ( !v10 )
          break;
        if ( a1 == v10 )
        {
          v8 = 1;
          break;
        }
      }
    }
    if ( (_DWORD)g_IgnoreOnErrors )
    {
      for ( j = 0; (unsigned int)j < 0xA; j = (unsigned int)(j + 1) )
      {
        v12 = *((_DWORD *)&g_IgnoreOnErrors + j);
        if ( !v12 )
          break;
        if ( a1 == v12 )
        {
          v8 = 0;
          break;
        }
      }
    }
    if ( v8 )
    {
LABEL_20:
      sprintf_s(Buffer, 0x190u, "hr = 0x%08x - %s (%s:%s:%d)\n", a1, a5, a2, a3, a4);
      OutputDebugStringA(Buffer);
      if ( (g_dwDebugPrintHR & 4) != 0 && a1 < 0 )
      {
        OutputDebugStringA("Breaking on configured error\n");
        DebugBreak();
      }
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18002c120  push    rbx
0x18002c122  push    rsi
0x18002c123  push    rdi
0x18002c124  push    r14
0x18002c126  sub     rsp, 1E8h
0x18002c12d  mov     rax, cs:__security_cookie
0x18002c134  xor     rax, rsp
0x18002c137  mov     [rsp+208h+var_38], rax
0x18002c13f  mov     eax, cs:?g_dwDebugPrintHR@@3KA; ulong g_dwDebugPrintHR
0x18002c145  mov     r11, r8
0x18002c148  mov     rdi, [rsp+208h+arg_20]
0x18002c150  mov     r10, rdx
0x18002c153  mov     ebx, ecx
0x18002c155  test    eax, eax
0x18002c157  jz      loc_18002C23E
0x18002c15d  test    al, 2
0x18002c15f  jnz     short loc_18002C1CD
0x18002c161  xor     ecx, ecx
0x18002c163  lea     esi, [rcx+1]
0x18002c166  test    sil, al
0x18002c169  jz      short loc_18002C170
0x18002c16b  test    ebx, ebx
0x18002c16d  cmovs   ecx, esi
0x18002c170  cmp     cs:?g_NotifyOnErrors@@3PAJA, 0; long near * g_NotifyOnErrors
0x18002c177  lea     r14, __ImageBase
0x18002c17e  jz      short loc_18002C1A1
0x18002c180  xor     ecx, ecx
0x18002c182  xor     edx, edx
0x18002c184  cmp     edx, 0Ah
0x18002c187  jnb     short loc_18002C1A1
0x18002c189  mov     r8d, rva ?g_NotifyOnErrors@@3PAJA[r14+rdx*4]; long near * g_NotifyOnErrors ...
0x18002c191  test    r8d, r8d
0x18002c194  jz      short loc_18002C1A1
0x18002c196  cmp     ebx, r8d
0x18002c199  jz      short loc_18002C19F
0x18002c19b  add     edx, esi
0x18002c19d  jmp     short loc_18002C184
0x18002c19f  mov     ecx, esi
0x18002c1a1  cmp     cs:?g_IgnoreOnErrors@@3PAJA, 0; long near * g_IgnoreOnErrors
0x18002c1a8  jz      short loc_18002C1C9
0x18002c1aa  xor     edx, edx
0x18002c1ac  cmp     edx, 0Ah
0x18002c1af  jnb     short loc_18002C1C9
0x18002c1b1  mov     r8d, rva ?g_IgnoreOnErrors@@3PAJA[r14+rdx*4]; long near * g_IgnoreOnErrors ...
0x18002c1b9  test    r8d, r8d
0x18002c1bc  jz      short loc_18002C1C9
0x18002c1be  cmp     ebx, r8d
0x18002c1c1  jz      short loc_18002C1C7
0x18002c1c3  add     edx, esi
0x18002c1c5  jmp     short loc_18002C1AC
0x18002c1c7  xor     ecx, ecx
0x18002c1c9  test    ecx, ecx
0x18002c1cb  jz      short loc_18002C23E
0x18002c1cd  mov     [rsp+208h+var_1D0], r9d
0x18002c1d2  lea     r8, aHr0x08xSSSD; "hr = 0x%08x - %s (%s:%s:%d)\n"
0x18002c1d9  mov     [rsp+208h+var_1D8], r11
0x18002c1de  lea     rcx, [rsp+208h+Buffer]; Buffer
0x18002c1e3  mov     [rsp+208h+var_1E0], r10
0x18002c1e8  mov     r9d, ebx
0x18002c1eb  mov     edx, 190h; BufferCount
0x18002c1f0  mov     [rsp+208h+var_1E8], rdi
0x18002c1f5  call    cs:__imp_sprintf_s
0x18002c1fc  nop     dword ptr [rax+rax+00h]
0x18002c201  lea     rcx, [rsp+208h+Buffer]; lpOutputString
0x18002c206  call    cs:__imp_OutputDebugStringA
0x18002c20d  nop     dword ptr [rax+rax+00h]
0x18002c212  test    byte ptr cs:?g_dwDebugPrintHR@@3KA, 4; ulong g_dwDebugPrintHR
0x18002c219  jz      short loc_18002C23E
0x18002c21b  test    ebx, ebx
0x18002c21d  jns     short loc_18002C23E
0x18002c21f  lea     rcx, aBreakingOnConf; "Breaking on configured error\n"
0x18002c226  call    cs:__imp_OutputDebugStringA
0x18002c22d  nop     dword ptr [rax+rax+00h]
0x18002c232  call    cs:__imp_DebugBreak
0x18002c239  nop     dword ptr [rax+rax+00h]
0x18002c23e  mov     eax, ebx
0x18002c240  mov     rcx, [rsp+208h+var_38]
0x18002c248  xor     rcx, rsp; StackCookie
0x18002c24b  call    __security_check_cookie
0x18002c250  add     rsp, 1E8h
0x18002c257  pop     r14
0x18002c259  pop     rdi
0x18002c25a  pop     rsi
0x18002c25b  pop     rbx
0x18002c25c  retn
```
