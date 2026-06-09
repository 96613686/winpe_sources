# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x14003601c`
- end: `0x1400361c0`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `420`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400361c0`

## callees

- `0x140001020`
- `0x1400020d0`
- `0x14003465c`
- `0x140035594`
- `0x140035738`
- `0x14003601c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1400360a3`
- `KERNEL32!lstrcmpiW` at `0x1400360a3`
- `USER32!CharNextW` at `0x1400361a5`
- `USER32!CharNextW` at `0x1400361a5`
- `ole32!CoTaskMemFree` at `0x1400360c2`
- `ole32!CoTaskMemFree` at `0x1400360c2`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  unsigned __int64 v8; // rbx
  LPCWSTR *v9; // rsi
  HKEY v10; // rsi
  LPCWSTR v11; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        v9 = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map;
        while ( lstrcmpiW(String1, *v9) )
        {
          ++v8;
          v9 += 2;
          if ( v8 >= 0xE )
            goto LABEL_7;
        }
        v10 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v10 )
          goto LABEL_7;
        _mm_lfence();
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        _mm_lfence();
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v11 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v10, a3, 0);
          if ( Token < 0 )
          {
            _mm_lfence();
            *this = v11;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v10, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v10, 0, 0);
          if ( Token < 0 )
            break;
        }
        _mm_lfence();
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x14003601c  mov     [rsp+arg_18], rbx
0x140036021  push    rbp
0x140036022  push    rsi
0x140036023  push    rdi
0x140036024  push    r12
0x140036026  push    r13
0x140036028  push    r14
0x14003602a  push    r15
0x14003602c  mov     eax, 2050h
0x140036031  call    _alloca_probe
0x140036036  sub     rsp, rax
0x140036039  mov     rax, cs:__security_cookie
0x140036040  xor     rax, rsp
0x140036043  mov     [rsp+2088h+var_48], rax
0x14003604b  mov     r15d, r8d
0x14003604e  xor     r12d, r12d
0x140036051  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x140036056  mov     [rsp+2088h+pv], r12
0x14003605b  mov     rdi, rcx
0x14003605e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140036063  mov     ebx, eax
0x140036065  lfence
0x140036068  test    eax, eax
0x14003606a  js      short loc_1400360CA
0x14003606c  mov     rbp, [rsp+2088h+pv]
0x140036071  mov     [rdi], rbp
0x140036074  cmp     r12w, [rbp+0]
0x140036079  jz      short loc_1400360BF
0x14003607b  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140036082  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140036087  mov     rcx, rdi; this
0x14003608a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14003608f  mov     ebx, eax
0x140036091  test    eax, eax
0x140036093  js      short loc_1400360BF
0x140036095  mov     rbx, r12
0x140036098  mov     rsi, r13
0x14003609b  mov     rdx, [rsi]; lpString2
0x14003609e  lea     rcx, [rsp+2088h+String1]; lpString1
0x1400360a3  call    cs:__imp_lstrcmpiW
0x1400360a9  test    eax, eax
0x1400360ab  jz      short loc_1400360F5
0x1400360ad  inc     rbx
0x1400360b0  add     rsi, 10h
0x1400360b4  cmp     rbx, 0Eh
0x1400360b8  jb      short loc_14003609B
0x1400360ba  mov     ebx, 80020009h
0x1400360bf  mov     rcx, rbp; pv
0x1400360c2  call    cs:__imp_CoTaskMemFree
0x1400360c8  mov     eax, ebx
0x1400360ca  mov     rcx, [rsp+2088h+var_48]
0x1400360d2  xor     rcx, rsp; StackCookie
0x1400360d5  call    __security_check_cookie
0x1400360da  mov     rbx, [rsp+2088h+arg_18]
0x1400360e2  add     rsp, 2050h
0x1400360e9  pop     r15
0x1400360eb  pop     r14
0x1400360ed  pop     r13
0x1400360ef  pop     r12
0x1400360f1  pop     rdi
0x1400360f2  pop     rsi
0x1400360f3  pop     rbp
0x1400360f4  retn
0x1400360f5  add     rbx, rbx
0x1400360f8  mov     rsi, [r13+rbx*8+8]
0x1400360fd  test    rsi, rsi
0x140036100  jz      short loc_1400360BA
0x140036102  lfence
0x140036105  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14003610a  mov     rcx, rdi; this
0x14003610d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140036112  mov     ebx, eax
0x140036114  test    eax, eax
0x140036116  js      short loc_1400360BF
0x140036118  lfence
0x14003611b  mov     eax, 7Bh ; '{'
0x140036120  cmp     ax, [rsp+2088h+String1]
0x140036125  jnz     short loc_1400360BA
0x140036127  mov     [rsp+2088h+var_2068], r12d; int
0x14003612c  mov     r8, rsi; HKEY
0x14003612f  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140036134  mov     rcx, rdi; this
0x140036137  test    r15d, r15d
0x14003613a  jz      short loc_140036170
0x14003613c  mov     r14, [rdi]
0x14003613f  mov     r9d, r15d; int
0x140036142  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140036147  mov     ebx, eax
0x140036149  test    eax, eax
0x14003614b  jns     short loc_140036182
0x14003614d  lfence
0x140036150  xor     r9d, r9d; int
0x140036153  mov     [rdi], r14
0x140036156  mov     r8, rsi; HKEY
0x140036159  mov     [rsp+2088h+var_2068], r12d; int
0x14003615e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140036163  mov     rcx, rdi; this
0x140036166  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14003616b  jmp     loc_1400360BF
0x140036170  xor     r9d, r9d; int
0x140036173  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140036178  mov     ebx, eax
0x14003617a  test    eax, eax
0x14003617c  js      loc_1400360BF
0x140036182  lfence
0x140036185  mov     r8, [rdi]
0x140036188  movzx   edx, word ptr [r8]
0x14003618c  mov     ecx, edx
0x14003618e  sub     ecx, 9
0x140036191  jz      short loc_1400361A2
0x140036193  sub     ecx, 1
0x140036196  jz      short loc_1400361A2
0x140036198  sub     ecx, 3
0x14003619b  jz      short loc_1400361A2
0x14003619d  cmp     ecx, 13h
0x1400361a0  jnz     short loc_1400361B0
0x1400361a2  mov     rcx, r8; lpsz
0x1400361a5  call    cs:__imp_CharNextW
0x1400361ab  mov     [rdi], rax
0x1400361ae  jmp     short loc_140036185
0x1400361b0  cmp     r12w, dx
0x1400361b4  jnz     loc_140036082
0x1400361ba  jmp     loc_1400360BF
```
