# StringCchVPrintfA(char *,unsigned __int64,char const *,char *)

- ea: `0x1800076ac`
- end: `0x1800076f1`
- name: `?StringCchVPrintfA@@YAJPEAD_KPEBD0@Z`
- size: `69`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *, char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f7c`
- `0x1800089d0`

## callees

- `0x1800076ac`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800076ba`
- `msvcrt!_vsnprintf` at `0x1800076ba`

## pseudocode

```c
__int64 __fastcall StringCchVPrintfA(char *a1, __int64 a2, const char *a3, va_list a4)
{
  unsigned int v5; // ecx
  __int64 result; // rax

  v5 = _vsnprintf(a1, 0x3FFu, a3, a4);
  if ( v5 >= 0x400 )
  {
    a1[1023] = 0;
    return 2147942522LL;
  }
  else
  {
    result = 0;
    if ( v5 == 1023 )
      a1[1023] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800076ac  push    rbx
0x1800076ae  sub     rsp, 20h
0x1800076b2  mov     edx, 3FFh; BufferCount
0x1800076b7  mov     rbx, rcx
0x1800076ba  call    cs:__imp__vsnprintf
0x1800076c0  mov     ecx, eax
0x1800076c2  test    eax, eax
0x1800076c4  js      short loc_1800076DF
0x1800076c6  cmp     eax, 3FFh
0x1800076cb  ja      short loc_1800076DF
0x1800076cd  xor     eax, eax
0x1800076cf  cmp     ecx, 3FFh
0x1800076d5  jnz     short loc_1800076EB
0x1800076d7  mov     [rbx+3FFh], al
0x1800076dd  jmp     short loc_1800076EB
0x1800076df  mov     byte ptr [rbx+3FFh], 0
0x1800076e6  mov     eax, 8007007Ah
0x1800076eb  add     rsp, 20h
0x1800076ef  pop     rbx
0x1800076f0  retn
```
