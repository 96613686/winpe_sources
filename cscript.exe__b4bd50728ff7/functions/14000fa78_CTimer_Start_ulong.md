# CTimer::Start(ulong)

- ea: `0x14000fa78`
- end: `0x14000fab4`
- name: `?Start@CTimer@@QEAAJK@Z`
- size: `60`
- prototype: `int(CTimer *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001090`
- `0x1400069d0`
- `0x140012c70`

## callees

- `0x14000fa78`

## import_xrefs

- `USER32!SendMessageA` at `0x14000fa99`
- `USER32!SendMessageA` at `0x14000fa99`

## pseudocode

```c
__int64 __fastcall CTimer::Start(HWND *this, unsigned int a2)
{
  HWND v3; // rcx
  __int64 result; // rax

  v3 = *this;
  if ( !v3 )
    return 1;
  SendMessageA(v3, 0x401u, a2, 0);
  result = *((unsigned int *)this + 6);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000fa78  push    rbx
0x14000fa7a  sub     rsp, 20h
0x14000fa7e  mov     rbx, rcx
0x14000fa81  mov     rcx, [rcx]; hWnd
0x14000fa84  test    rcx, rcx
0x14000fa87  jnz     short loc_14000FA8E
0x14000fa89  lea     eax, [rcx+1]
0x14000fa8c  jmp     short loc_14000FAAE
0x14000fa8e  mov     r8d, edx; wParam
0x14000fa91  xor     r9d, r9d; lParam
0x14000fa94  mov     edx, 401h; Msg
0x14000fa99  call    cs:__imp_SendMessageA
0x14000fa9f  mov     eax, [rbx+18h]
0x14000faa2  test    eax, eax
0x14000faa4  jle     short loc_14000FAAE
0x14000faa6  movzx   eax, ax
0x14000faa9  or      eax, 80070000h
0x14000faae  add     rsp, 20h
0x14000fab2  pop     rbx
0x14000fab3  retn
```
