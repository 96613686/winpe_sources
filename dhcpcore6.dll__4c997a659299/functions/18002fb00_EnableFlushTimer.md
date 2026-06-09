# EnableFlushTimer

- ea: `0x18002fb00`
- end: `0x18002fb58`
- name: `EnableFlushTimer`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002fd50`
- `0x18002fda0`

## callees

- `0x18002fb00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fb39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002fb39`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180042728 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18002fb00  sub     rsp, 28h
0x18002fb04  test    rcx, rcx
0x18002fb07  jz      short loc_18002FB52
0x18002fb09  mov     eax, cs:dword_180042728
0x18002fb0f  test    eax, eax
0x18002fb11  jnz     short loc_18002FB52
0x18002fb13  mov     eax, edx
0x18002fb15  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18002fb1c  mov     rdx, rax
0x18002fb1f  shr     rdx, 20h
0x18002fb23  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18002fb27  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18002fb2b  mov     r9d, 1388h; msWindowLength
0x18002fb31  xor     r8d, r8d; msPeriod
0x18002fb34  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002fb39  call    cs:__imp_SetThreadpoolTimer
0x18002fb40  nop     dword ptr [rax+rax+00h]
0x18002fb45  jmp     short loc_18002FB52
0x18002fb47  mov     eax, 1
0x18002fb4c  xchg    eax, cs:dword_180042728
0x18002fb52  add     rsp, 28h
0x18002fb56  retn
0x180030a36  push    rbp
0x180030a38  sub     rsp, 20h
0x180030a3c  mov     rbp, rdx
0x180030a3f  mov     rax, [rcx]
0x180030a42  xor     ecx, ecx
0x180030a44  cmp     dword ptr [rax], 0C000000Dh
0x180030a4a  setz    cl
0x180030a4d  mov     eax, ecx
0x180030a4f  add     rsp, 20h
0x180030a53  pop     rbp
0x180030a54  retn
```
