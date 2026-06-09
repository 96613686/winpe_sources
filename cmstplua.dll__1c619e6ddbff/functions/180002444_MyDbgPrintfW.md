# MyDbgPrintfW

- ea: `0x180002444`
- end: `0x18000261b`
- name: `MyDbgPrintfW`
- size: `471`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001af0`
- `0x180001d70`
- `0x1800021e8`
- `0x180002284`

## callees

- `0x180002350`
- `0x180002444`
- `0x1800026b6`
- `0x1800026e0`
- `0x180003010`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180002595`
- `msvcrt!_vsnprintf` at `0x180002595`
- `KERNEL32!lstrlenA` at `0x1800025b2`
- `KERNEL32!lstrlenA` at `0x1800025b2`
- `KERNEL32!LocalAlloc` at `0x1800024dc`
- `KERNEL32!LocalAlloc` at `0x1800024dc`
- `KERNEL32!LocalFree` at `0x1800025c5`
- `KERNEL32!LocalFree` at `0x1800025c5`
- `KERNEL32!WideCharToMultiByte` at `0x1800024c7`
- `KERNEL32!WideCharToMultiByte` at `0x180002517`
- `KERNEL32!WideCharToMultiByte` at `0x1800024c7`
- `KERNEL32!WideCharToMultiByte` at `0x180002517`

## pseudocode

```c
HLOCAL MyDbgPrintfW(unsigned int a1, const WCHAR *a2, ...)
{
  char *v4; // rdi
  unsigned int v5; // eax
  int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  char v8; // al
  char *v9; // rdx
  BOOL v10; // ecx
  unsigned int v11; // eax
  HLOCAL result; // rax
  __int64 (__fastcall *v13)(_QWORD, __int64, char *); // rbx
  char Buffer[1535]; // [rsp+50h] [rbp-638h] BYREF
  char v15; // [rsp+64Fh] [rbp-39h]
  va_list ArgList; // [rsp+6A0h] [rbp+18h] BYREF

  va_start(ArgList, a2);
  memset_0(Buffer, 0, 0x600u);
  v4 = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v5 = WideCharToMultiByte(0, 0x400u, a2, -1, 0, 0, 0, 0);
      cbMultiByte = v5;
      if ( v5 )
      {
        lpMultiByteStr = (CHAR *)LocalAlloc(0x40u, v5);
        v4 = lpMultiByteStr;
        if ( lpMultiByteStr )
        {
          if ( WideCharToMultiByte(0, 0x400u, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
          {
            v8 = *v4;
            if ( *v4 )
            {
              v9 = v4;
              v10 = 0;
              do
              {
                switch ( v8 )
                {
                  case '%':
                    v10 = !v10;
                    break;
                  case 'C':
                    if ( v10 )
                      *v9 = 99;
                    break;
                  case 'S':
                    if ( v10 )
                      *v9 = 115;
                    break;
                  case 'c':
                    if ( v10 )
                      *v9 = 67;
                    break;
                  case 's':
                    if ( v10 )
                      *v9 = 83;
                    break;
                  default:
                    v10 = 0;
                    break;
                }
                v8 = *++v9;
              }
              while ( *v9 );
            }
            v11 = _vsnprintf(Buffer, 0x5FFu, v4, ArgList);
            if ( v11 >= 0x600 )
            {
              v15 = 0;
            }
            else
            {
              if ( v11 == 1535 )
                v15 = 0;
              lstrlenA(Buffer);
            }
          }
        }
      }
    }
  }
  result = LocalFree(v4);
  if ( a1 != -1 )
  {
    v13 = (__int64 (__fastcall *)(_QWORD, __int64, char *))g_pTracePrintfEx;
    if ( g_pTracePrintfEx )
    {
      DuplicatePercentileSymbol(Buffer, 1536);
      return (HLOCAL)v13(a1, 12, Buffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002444  mov     [rsp+arg_8], rdx
0x180002449  mov     qword ptr [rsp+ArgList], r8
0x18000244e  mov     [rsp+arg_18], r9
0x180002453  push    rbx
0x180002454  push    rbp
0x180002455  push    rsi
0x180002456  push    rdi
0x180002457  sub     rsp, 668h
0x18000245e  mov     rax, cs:__security_cookie
0x180002465  xor     rax, rsp
0x180002468  mov     [rsp+688h+var_38], rax
0x180002470  mov     rbx, rdx
0x180002473  mov     [rsp+688h+var_648], 0
0x18000247c  mov     ebp, ecx
0x18000247e  xor     edx, edx; Val
0x180002480  lea     rcx, [rsp+688h+Buffer]; void *
0x180002485  mov     r8d, 600h; Size
0x18000248b  call    memset_0
0x180002490  xor     edi, edi
0x180002492  test    rbx, rbx
0x180002495  jz      loc_1800025C2
0x18000249b  xor     eax, eax
0x18000249d  cmp     ax, [rbx]
0x1800024a0  jz      loc_1800025C2
0x1800024a6  mov     [rsp+688h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800024ab  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800024af  mov     [rsp+688h+lpDefaultChar], rax; lpDefaultChar
0x1800024b4  mov     r8, rbx; lpWideCharStr
0x1800024b7  mov     [rsp+688h+cbMultiByte], eax; cbMultiByte
0x1800024bb  mov     edx, 400h; dwFlags
0x1800024c0  xor     ecx, ecx; CodePage
0x1800024c2  mov     [rsp+688h+lpMultiByteStr], rax; lpMultiByteStr
0x1800024c7  call    cs:__imp_WideCharToMultiByte
0x1800024cd  mov     esi, eax
0x1800024cf  test    eax, eax
0x1800024d1  jz      loc_1800025C2
0x1800024d7  mov     edx, esi; uBytes
0x1800024d9  lea     ecx, [rdi+40h]; uFlags
0x1800024dc  call    cs:__imp_LocalAlloc
0x1800024e2  mov     rdi, rax
0x1800024e5  test    rax, rax
0x1800024e8  jz      loc_1800025C2
0x1800024ee  mov     [rsp+688h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800024f7  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800024fb  mov     [rsp+688h+lpDefaultChar], 0; lpDefaultChar
0x180002504  mov     r8, rbx; lpWideCharStr
0x180002507  mov     [rsp+688h+cbMultiByte], esi; cbMultiByte
0x18000250b  mov     edx, 400h; dwFlags
0x180002510  xor     ecx, ecx; CodePage
0x180002512  mov     [rsp+688h+lpMultiByteStr], rax; lpMultiByteStr
0x180002517  call    cs:__imp_WideCharToMultiByte
0x18000251d  test    eax, eax
0x18000251f  jz      loc_1800025C2
0x180002525  mov     al, [rdi]
0x180002527  test    al, al
0x180002529  jz      short loc_18000257E
0x18000252b  mov     rdx, rdi
0x18000252e  xor     ecx, ecx
0x180002530  cmp     al, 25h ; '%'
0x180002532  jz      short loc_18000256C
0x180002534  cmp     al, 43h ; 'C'
0x180002536  jz      short loc_180002563
0x180002538  cmp     al, 53h ; 'S'
0x18000253a  jz      short loc_18000255A
0x18000253c  cmp     al, 63h ; 'c'
0x18000253e  jz      short loc_180002551
0x180002540  cmp     al, 73h ; 's'
0x180002542  jz      short loc_180002548
0x180002544  xor     ecx, ecx
0x180002546  jmp     short loc_180002575
0x180002548  test    ecx, ecx
0x18000254a  jz      short loc_180002575
0x18000254c  mov     byte ptr [rdx], 53h ; 'S'
0x18000254f  jmp     short loc_180002575
0x180002551  test    ecx, ecx
0x180002553  jz      short loc_180002575
0x180002555  mov     byte ptr [rdx], 43h ; 'C'
0x180002558  jmp     short loc_180002575
0x18000255a  test    ecx, ecx
0x18000255c  jz      short loc_180002575
0x18000255e  mov     byte ptr [rdx], 73h ; 's'
0x180002561  jmp     short loc_180002575
0x180002563  test    ecx, ecx
0x180002565  jz      short loc_180002575
0x180002567  mov     byte ptr [rdx], 63h ; 'c'
0x18000256a  jmp     short loc_180002575
0x18000256c  xor     eax, eax
0x18000256e  test    ecx, ecx
0x180002570  setz    al
0x180002573  mov     ecx, eax
0x180002575  inc     rdx
0x180002578  mov     al, [rdx]
0x18000257a  test    al, al
0x18000257c  jnz     short loc_180002530
0x18000257e  mov     ebx, 5FFh
0x180002583  lea     r9, [rsp+688h+ArgList]; ArgList
0x18000258b  mov     edx, ebx; BufferCount
0x18000258d  lea     rcx, [rsp+688h+Buffer]; Buffer
0x180002592  mov     r8, rdi; Format
0x180002595  call    cs:__imp__vsnprintf
0x18000259b  test    eax, eax
0x18000259d  js      short loc_1800025BA
0x18000259f  cmp     eax, ebx
0x1800025a1  ja      short loc_1800025BA
0x1800025a3  jnz     short loc_1800025AD
0x1800025a5  mov     [rsp+688h+var_39], 0
0x1800025ad  lea     rcx, [rsp+688h+Buffer]; lpString
0x1800025b2  call    cs:__imp_lstrlenA
0x1800025b8  jmp     short loc_1800025C2
0x1800025ba  mov     [rsp+688h+var_39], 0
0x1800025c2  mov     rcx, rdi; hMem
0x1800025c5  call    cs:__imp_LocalFree
0x1800025cb  cmp     ebp, 0FFFFFFFFh
0x1800025ce  jz      short loc_1800025FF
0x1800025d0  mov     rbx, cs:g_pTracePrintfEx
0x1800025d7  test    rbx, rbx
0x1800025da  jz      short loc_1800025FF
0x1800025dc  mov     edx, 600h
0x1800025e1  lea     rcx, [rsp+688h+Buffer]
0x1800025e6  call    DuplicatePercentileSymbol
0x1800025eb  lea     r8, [rsp+688h+Buffer]
0x1800025f0  mov     edx, 0Ch
0x1800025f5  mov     ecx, ebp
0x1800025f7  mov     rax, rbx
0x1800025fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ff  mov     rcx, [rsp+688h+var_38]
0x180002607  xor     rcx, rsp; StackCookie
0x18000260a  call    __security_check_cookie
0x18000260f  add     rsp, 668h
0x180002616  pop     rdi
0x180002617  pop     rsi
0x180002618  pop     rbp
0x180002619  pop     rbx
0x18000261a  retn
```
