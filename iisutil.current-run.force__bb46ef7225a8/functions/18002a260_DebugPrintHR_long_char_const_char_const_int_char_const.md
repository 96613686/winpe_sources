# DebugPrintHR(long,char const *,char const *,int,char const *)

- ea: `0x18002a260`
- end: `0x18002a385`
- name: `?DebugPrintHR@@YAJJPEBD0H0@Z`
- size: `293`
- prototype: `__int64 __fastcall(int, const char *, const char *, int, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18002a260`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18002a335`
- `msvcrt!sprintf_s` at `0x18002a335`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002a340`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002a35a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002a340`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002a35a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002a360`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002a360`

## string_xrefs

- `0x18002a353`: `Breaking on configured error\n`

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
0x18002a260  push    rbx
0x18002a262  push    rsi
0x18002a263  push    rdi
0x18002a264  push    r14
0x18002a266  sub     rsp, 1E8h
0x18002a26d  mov     rax, cs:__security_cookie
0x18002a274  xor     rax, rsp
0x18002a277  mov     [rsp+208h+var_38], rax
0x18002a27f  mov     eax, cs:?g_dwDebugPrintHR@@3KA; ulong g_dwDebugPrintHR
0x18002a285  mov     r11, r8
0x18002a288  mov     rdi, [rsp+208h+arg_20]
0x18002a290  mov     r10, rdx
0x18002a293  mov     ebx, ecx
0x18002a295  test    eax, eax
0x18002a297  jz      loc_18002A366
0x18002a29d  test    al, 2
0x18002a29f  jnz     short loc_18002A30D
0x18002a2a1  xor     ecx, ecx
0x18002a2a3  lea     esi, [rcx+1]
0x18002a2a6  test    sil, al
0x18002a2a9  jz      short loc_18002A2B0
0x18002a2ab  test    ebx, ebx
0x18002a2ad  cmovs   ecx, esi
0x18002a2b0  cmp     cs:?g_NotifyOnErrors@@3PAJA, 0; long near * g_NotifyOnErrors
0x18002a2b7  lea     r14, __ImageBase
0x18002a2be  jz      short loc_18002A2E1
0x18002a2c0  xor     ecx, ecx
0x18002a2c2  xor     edx, edx
0x18002a2c4  cmp     edx, 0Ah
0x18002a2c7  jnb     short loc_18002A2E1
0x18002a2c9  mov     r8d, rva ?g_NotifyOnErrors@@3PAJA[r14+rdx*4]; long near * g_NotifyOnErrors ...
0x18002a2d1  test    r8d, r8d
0x18002a2d4  jz      short loc_18002A2E1
0x18002a2d6  cmp     ebx, r8d
0x18002a2d9  jz      short loc_18002A2DF
0x18002a2db  add     edx, esi
0x18002a2dd  jmp     short loc_18002A2C4
0x18002a2df  mov     ecx, esi
0x18002a2e1  cmp     cs:?g_IgnoreOnErrors@@3PAJA, 0; long near * g_IgnoreOnErrors
0x18002a2e8  jz      short loc_18002A309
0x18002a2ea  xor     edx, edx
0x18002a2ec  cmp     edx, 0Ah
0x18002a2ef  jnb     short loc_18002A309
0x18002a2f1  mov     r8d, rva ?g_IgnoreOnErrors@@3PAJA[r14+rdx*4]; long near * g_IgnoreOnErrors ...
0x18002a2f9  test    r8d, r8d
0x18002a2fc  jz      short loc_18002A309
0x18002a2fe  cmp     ebx, r8d
0x18002a301  jz      short loc_18002A307
0x18002a303  add     edx, esi
0x18002a305  jmp     short loc_18002A2EC
0x18002a307  xor     ecx, ecx
0x18002a309  test    ecx, ecx
0x18002a30b  jz      short loc_18002A366
0x18002a30d  mov     [rsp+208h+var_1D0], r9d
0x18002a312  lea     r8, aHr0x08xSSSD; "hr = 0x%08x - %s (%s:%s:%d)\n"
0x18002a319  mov     [rsp+208h+var_1D8], r11
0x18002a31e  lea     rcx, [rsp+208h+Buffer]; Buffer
0x18002a323  mov     [rsp+208h+var_1E0], r10
0x18002a328  mov     r9d, ebx
0x18002a32b  mov     edx, 190h; BufferCount
0x18002a330  mov     [rsp+208h+var_1E8], rdi
0x18002a335  call    cs:__imp_sprintf_s
0x18002a33b  lea     rcx, [rsp+208h+Buffer]; lpOutputString
0x18002a340  call    cs:__imp_OutputDebugStringA
0x18002a346  test    byte ptr cs:?g_dwDebugPrintHR@@3KA, 4; ulong g_dwDebugPrintHR
0x18002a34d  jz      short loc_18002A366
0x18002a34f  test    ebx, ebx
0x18002a351  jns     short loc_18002A366
0x18002a353  lea     rcx, aBreakingOnConf; "Breaking on configured error\n"
0x18002a35a  call    cs:__imp_OutputDebugStringA
0x18002a360  call    cs:__imp_DebugBreak
0x18002a366  mov     eax, ebx
0x18002a368  mov     rcx, [rsp+208h+var_38]
0x18002a370  xor     rcx, rsp; StackCookie
0x18002a373  call    __security_check_cookie
0x18002a378  add     rsp, 1E8h
0x18002a37f  pop     r14
0x18002a381  pop     rdi
0x18002a382  pop     rsi
0x18002a383  pop     rbx
0x18002a384  retn
```
