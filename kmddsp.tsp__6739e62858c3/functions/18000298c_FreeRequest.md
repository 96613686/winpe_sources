# FreeRequest

- ea: `0x18000298c`
- end: `0x1800029d5`
- name: `FreeRequest`
- size: `73`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b6c`
- `0x180002d40`
- `0x180003488`
- `0x180003ba8`
- `0x180004520`
- `0x180004670`
- `0x180004880`
- `0x1800049a0`
- `0x180004bc0`
- `0x180004fe0`
- `0x1800051d0`
- `0x180005320`
- `0x180005440`
- `0x180005550`
- `0x1800058b0`
- `0x180005bc0`
- `0x180005d00`
- `0x180005db0`
- `0x180006140`
- `0x1800063b0`
- `0x180006820`
- `0x180006a20`
- `0x180006d40`
- `0x180006e30`
- `0x180006fb0`
- `0x1800070c0`
- `0x1800071b0`
- `0x1800072e0`
- `0x1800073b0`
- `0x1800074c0`
- `0x1800075b0`

## callees

- `0x180001c7e`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800029c9`
- `KERNEL32!EnterCriticalSection` at `0x18000299c`
- `KERNEL32!EnterCriticalSection` at `0x18000299c`

## pseudocode

```c
void __fastcall FreeRequest(_DWORD *a1)
{
  size_t v2; // r8

  EnterCriticalSection(&stru_18000E350);
  v2 = (unsigned int)*(a1 - 6);
  *(a1 - 5) = 0;
  memset_0(a1, 0, v2);
  LeaveCriticalSection(&stru_18000E350);
}

```

## disassembly

```asm
0x18000298c  push    rbx
0x18000298e  sub     rsp, 20h
0x180002992  mov     rbx, rcx
0x180002995  lea     rcx, stru_18000E350; lpCriticalSection
0x18000299c  call    cs:__imp_EnterCriticalSection
0x1800029a3  nop     dword ptr [rax+rax+00h]
0x1800029a8  mov     r8d, [rbx-18h]; Size
0x1800029ac  xor     edx, edx; Val
0x1800029ae  mov     rcx, rbx; void *
0x1800029b1  mov     dword ptr [rbx-14h], 0
0x1800029b8  call    memset_0
0x1800029bd  lea     rcx, stru_18000E350
0x1800029c4  add     rsp, 20h
0x1800029c8  pop     rbx
0x1800029c9  jmp     cs:__imp_LeaveCriticalSection
```
