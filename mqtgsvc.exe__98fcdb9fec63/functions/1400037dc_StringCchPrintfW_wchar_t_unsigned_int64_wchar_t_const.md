# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x1400037dc`
- end: `0x140003860`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `132`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140003630`
- `0x1400076a8`
- `0x1400108d0`
- `0x1400109e0`
- `0x140011f54`
- `0x140015aec`
- `0x140015c38`
- `0x140015dc8`
- `0x1400176a8`
- `0x140017810`
- `0x140017cf4`

## callees

- `0x1400037dc`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000381b`
- `msvcrt!_vsnwprintf` at `0x14000381b`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x1400037dc  mov     [rsp+arg_10], r8
0x1400037e1  mov     qword ptr [rsp+Args], r9
0x1400037e6  push    rbx
0x1400037e7  push    rdi
0x1400037e8  sub     rsp, 38h
0x1400037ec  mov     rax, rdx
0x1400037ef  mov     rdi, rcx
0x1400037f2  test    rdx, rdx
0x1400037f5  jz      short loc_140003848
0x1400037f7  cmp     rax, 7FFFFFFFh
0x1400037fd  jbe     short loc_140003806
0x1400037ff  mov     edx, 80070057h
0x140003804  jmp     short loc_140003852
0x140003806  lea     rbx, [rdx-1]
0x14000380a  mov     [rsp+48h+var_28], 0
0x140003813  mov     rdx, rbx; BufferCount
0x140003816  lea     r9, [rsp+48h+Args]; Args
0x14000381b  call    cs:__imp__vsnwprintf
0x140003821  test    eax, eax
0x140003823  js      short loc_14000383B
0x140003825  cdqe
0x140003827  cmp     rax, rbx
0x14000382a  ja      short loc_14000383B
0x14000382c  xor     edx, edx
0x14000382e  cmp     rax, rbx
0x140003831  jnz     short loc_140003857
0x140003833  xor     eax, eax
0x140003835  mov     [rdi+rbx*2], ax
0x140003839  jmp     short loc_140003857
0x14000383b  xor     eax, eax
0x14000383d  mov     edx, 8007007Ah
0x140003842  mov     [rdi+rbx*2], ax
0x140003846  jmp     short loc_140003857
0x140003848  mov     edx, 80070057h
0x14000384d  test    rax, rax
0x140003850  jz      short loc_140003857
0x140003852  xor     ecx, ecx
0x140003854  mov     [rdi], cx
0x140003857  mov     eax, edx
0x140003859  add     rsp, 38h
0x14000385d  pop     rdi
0x14000385e  pop     rbx
0x14000385f  retn
```
