# CSynth::SetGainAdjust(long)

- ea: `0x180006e50`
- end: `0x180006eba`
- name: `?SetGainAdjust@CSynth@@QEAAXJ@Z`
- size: `106`
- prototype: `void __fastcall(CSynth *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012180`
- `0x1800121d0`
- `0x180012460`

## callees

- `0x180006e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006eb3`

## pseudocode

```c
void __fastcall CSynth::SetGainAdjust(CSynth *this, int a2)
{
  __int64 i; // rax
  __int64 v4; // r9

  *((_DWORD *)this + 44) = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 260); *(_DWORD *)(v4 + 3436) = *((_DWORD *)this + 44) )
  {
    v4 = *(_QWORD *)(*((_QWORD *)this + 129) + 8 * i);
    i = (unsigned int)(i + 1);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
}

```

## disassembly

```asm
0x180006e50  mov     [rsp+arg_0], rbx
0x180006e55  push    rdi
0x180006e56  sub     rsp, 20h
0x180006e5a  mov     rbx, rcx
0x180006e5d  mov     [rcx+0B0h], edx
0x180006e63  add     rcx, 418h; lpCriticalSection
0x180006e6a  call    cs:__imp_EnterCriticalSection
0x180006e70  xor     eax, eax
0x180006e72  cmp     [rbx+410h], eax
0x180006e78  jbe     short loc_180006EA2
0x180006e7a  nop     word ptr [rax+rax+00h]
0x180006e80  mov     rdx, [rbx+408h]
0x180006e87  mov     r9, [rdx+rax*8]
0x180006e8b  inc     eax
0x180006e8d  mov     edx, [rbx+0B0h]
0x180006e93  mov     [r9+0D6Ch], edx
0x180006e9a  cmp     eax, [rbx+410h]
0x180006ea0  jb      short loc_180006E80
0x180006ea2  lea     rcx, [rbx+418h]
0x180006ea9  mov     rbx, [rsp+28h+arg_0]
0x180006eae  add     rsp, 20h
0x180006eb2  pop     rdi
0x180006eb3  jmp     cs:__imp_LeaveCriticalSection
```
