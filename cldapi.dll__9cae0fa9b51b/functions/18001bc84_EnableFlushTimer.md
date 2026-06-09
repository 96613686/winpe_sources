# EnableFlushTimer

- ea: `0x18001bc84`
- end: `0x18001bcdc`
- name: `EnableFlushTimer`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001be60`
- `0x18001beb0`

## callees

- `0x18001bc84`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bcbd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bcbd`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18002AB98 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18001bc84  sub     rsp, 28h
0x18001bc88  test    rcx, rcx
0x18001bc8b  jz      short loc_18001BCD6
0x18001bc8d  mov     eax, cs:dword_18002AB98
0x18001bc93  test    eax, eax
0x18001bc95  jnz     short loc_18001BCD6
0x18001bc97  mov     eax, edx
0x18001bc99  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18001bca0  mov     rdx, rax
0x18001bca3  shr     rdx, 20h
0x18001bca7  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18001bcab  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001bcaf  mov     r9d, 1388h; msWindowLength
0x18001bcb5  xor     r8d, r8d; msPeriod
0x18001bcb8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001bcbd  call    cs:__imp_SetThreadpoolTimer
0x18001bcc4  nop     dword ptr [rax+rax+00h]
0x18001bcc9  jmp     short loc_18001BCD6
0x18001bccb  mov     eax, 1
0x18001bcd0  xchg    eax, cs:dword_18002AB98
0x18001bcd6  add     rsp, 28h
0x18001bcda  retn
0x18001d1d6  push    rbp
0x18001d1d8  sub     rsp, 20h
0x18001d1dc  mov     rbp, rdx
0x18001d1df  mov     rax, [rcx]
0x18001d1e2  xor     ecx, ecx
0x18001d1e4  cmp     dword ptr [rax], 0C000000Dh
0x18001d1ea  setz    cl
0x18001d1ed  mov     eax, ecx
0x18001d1ef  add     rsp, 20h
0x18001d1f3  pop     rbp
0x18001d1f4  retn
```
