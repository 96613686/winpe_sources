# ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)

- ea: `0x1800037c4`
- end: `0x180003934`
- name: `?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ`
- size: `368`
- prototype: `unsigned __int16 *(HINSTANCE, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f00`
- `0x180003110`
- `0x18000b710`
- `0x18000bde4`

## callees

- `0x1800037c4`
- `0x18000cd10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000389b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000389b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003859`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003859`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038c4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003842`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003842`

## pseudocode

```c
unsigned __int16 *ShellConstructMessageString(HINSTANCE a1, unsigned __int16 *a2, ...)
{
  unsigned __int16 *v3; // rbx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  WCHAR *v9; // rdx
  unsigned __int16 *v10; // rcx
  WCHAR Buffer[4]; // [rsp+48h] [rbp-C0h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR v13[520]; // [rsp+58h] [rbp-B0h] BYREF
  va_list va; // [rsp+4B8h] [rbp+3B0h] BYREF

  va_start(va, a2);
  va_copy(Arguments, va);
  *(_QWORD *)Buffer = 0;
  if ( (unsigned __int64)a2 < 0x10000 )
  {
    v3 = 0;
    if ( (_WORD)a2 )
    {
      if ( LoadStringW(a1, (unsigned __int16)a2, v13, 514) )
      {
        v5 = -1;
        do
          ++v5;
        while ( v13[v5] );
        v6 = v5 + 1;
        v7 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v6);
        v3 = v7;
        if ( v7 )
        {
          if ( v6 )
          {
            if ( v6 <= 0x7FFFFFFF )
            {
              v8 = 2147483646;
              v9 = v13;
              do
              {
                if ( !v8 )
                  break;
                if ( !*v9 )
                  break;
                *v7++ = *v9++;
                --v8;
                --v6;
              }
              while ( v6 );
              v10 = v7 - 1;
              if ( v6 )
                v10 = v7;
              *v10 = 0;
            }
            else
            {
              *v7 = 0;
            }
          }
        }
      }
    }
    if ( !v3 )
      return 0;
  }
  else
  {
    v3 = a2;
  }
  if ( !FormatMessageW(0x500u, v3, 0, 0, Buffer, 0, &Arguments) )
    *(_QWORD *)Buffer = 0;
  if ( v3 != a2 )
    LocalFree(v3);
  return *(unsigned __int16 **)Buffer;
}

```

## disassembly

```asm
0x1800037c4  mov     rax, rsp
0x1800037c7  mov     [rax+10h], rdx
0x1800037cb  mov     [rax+18h], r8
0x1800037cf  mov     [rax+20h], r9
0x1800037d3  push    rbp
0x1800037d4  push    rbx
0x1800037d5  push    rsi
0x1800037d6  push    rdi
0x1800037d7  push    r14
0x1800037d9  lea     rbp, [rax-398h]
0x1800037e0  sub     rsp, 470h
0x1800037e7  mov     rax, cs:__security_cookie
0x1800037ee  xor     rax, rsp
0x1800037f1  mov     [rbp+390h+var_30], rax
0x1800037f8  xor     r14d, r14d
0x1800037fb  lea     rax, [rbp+390h+arg_10]
0x180003802  mov     [rsp+490h+Arguments], rax
0x180003807  mov     rsi, rdx
0x18000380a  mov     qword ptr [rsp+490h+Buffer], r14
0x18000380f  cmp     rdx, 10000h
0x180003816  jb      short loc_180003881
0x180003818  mov     rbx, rdx
0x18000381b  lea     rax, [rsp+490h+Arguments]
0x180003820  xor     r9d, r9d; dwLanguageId
0x180003823  mov     [rsp+30h], rax; Arguments
0x180003828  xor     r8d, r8d; dwMessageId
0x18000382b  lea     rax, [rsp+490h+Buffer]
0x180003830  mov     [rsp+490h+nSize], r14d; nSize
0x180003835  mov     rdx, rbx; lpSource
0x180003838  mov     [rsp+490h+lpBuffer], rax; lpBuffer
0x18000383d  mov     ecx, 500h; dwFlags
0x180003842  call    cs:__imp_FormatMessageW
0x180003848  test    eax, eax
0x18000384a  jnz     short loc_180003851
0x18000384c  mov     qword ptr [rsp+490h+Buffer], r14
0x180003851  cmp     rbx, rsi
0x180003854  jz      short loc_18000385F
0x180003856  mov     rcx, rbx; hMem
0x180003859  call    cs:__imp_LocalFree
0x18000385f  mov     rax, qword ptr [rsp+490h+Buffer]
0x180003864  mov     rcx, [rbp+390h+var_30]
0x18000386b  xor     rcx, rsp; StackCookie
0x18000386e  call    __security_check_cookie
0x180003873  add     rsp, 470h
0x18000387a  pop     r14
0x18000387c  pop     rdi
0x18000387d  pop     rsi
0x18000387e  pop     rbx
0x18000387f  pop     rbp
0x180003880  retn
0x180003881  mov     rbx, r14
0x180003884  test    si, si
0x180003887  jz      loc_180003923
0x18000388d  movzx   edx, si; uID
0x180003890  lea     r8, [rsp+490h+var_440]; lpBuffer
0x180003895  mov     r9d, 202h; cchBufferMax
0x18000389b  call    cs:__imp_LoadStringW
0x1800038a1  test    eax, eax
0x1800038a3  jz      short loc_180003923
0x1800038a5  lea     rax, [rsp+490h+var_440]
0x1800038aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800038ae  inc     rdi
0x1800038b1  cmp     [rax+rdi*2], r14w
0x1800038b6  jnz     short loc_1800038AE
0x1800038b8  inc     rdi
0x1800038bb  mov     ecx, 40h ; '@'; uFlags
0x1800038c0  lea     rdx, [rdi+rdi]; uBytes
0x1800038c4  call    cs:__imp_LocalAlloc
0x1800038ca  mov     rbx, rax
0x1800038cd  test    rax, rax
0x1800038d0  jz      short loc_180003923
0x1800038d2  test    rdi, rdi
0x1800038d5  jz      short loc_180003923
0x1800038d7  cmp     rdi, 7FFFFFFFh
0x1800038de  jbe     short loc_1800038E6
0x1800038e0  mov     [rax], r14w
0x1800038e4  jmp     short loc_180003923
0x1800038e6  mov     ecx, 7FFFFFFEh
0x1800038eb  lea     rdx, [rsp+490h+var_440]
0x1800038f0  test    rcx, rcx
0x1800038f3  jz      short loc_180003914
0x1800038f5  movzx   r8d, word ptr [rdx]
0x1800038f9  test    r8w, r8w
0x1800038fd  jz      short loc_180003914
0x1800038ff  mov     [rax], r8w
0x180003903  add     rdx, 2
0x180003907  add     rax, 2
0x18000390b  dec     rcx
0x18000390e  sub     rdi, 1
0x180003912  jnz     short loc_1800038F0
0x180003914  test    rdi, rdi
0x180003917  lea     rcx, [rax-2]
0x18000391b  cmovnz  rcx, rax
0x18000391f  mov     [rcx], r14w
0x180003923  test    rbx, rbx
0x180003926  jnz     loc_18000381B
0x18000392c  mov     rax, r14
0x18000392f  jmp     loc_180003864
```
