# FreeCommandLineOptions

- ea: `0x180002110`
- end: `0x180002174`
- name: `FreeCommandLineOptions`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000214b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000214b`

## pseudocode

```c
HLOCAL __fastcall FreeCommandLineOptions(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v4; // r15
  __int64 v8; // rbx
  __int64 v9; // rdi
  HLOCAL result; // rax

  if ( a2 > 0 )
  {
    v4 = a4;
    v8 = 0;
    do
    {
      if ( *(_DWORD *)(a1 + 24 * v8 + 8) == 2 )
      {
        v9 = *(_QWORD *)(a1 + 24 * v8 + 16);
        if ( v9 + 16 <= v4 )
        {
          result = LocalFree(*(HLOCAL *)(v9 + a3 + 8));
          *(_QWORD *)(v9 + a3 + 8) = 0;
        }
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (int)v8 < a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180002110  test    edx, edx
0x180002112  jle     short locret_180002172
0x180002114  push    rbx
0x180002115  push    rbp
0x180002116  push    rsi
0x180002117  push    rdi
0x180002118  push    r14
0x18000211a  push    r15
0x18000211c  sub     rsp, 28h
0x180002120  mov     r15d, r9d
0x180002123  mov     r14, r8
0x180002126  mov     esi, edx
0x180002128  mov     rbp, rcx
0x18000212b  xor     ebx, ebx
0x18000212d  lea     rdi, [rbx+rbx*2]
0x180002131  cmp     dword ptr [rbp+rdi*8+8], 2
0x180002136  jnz     short loc_180002160
0x180002138  mov     rdi, [rbp+rdi*8+10h]
0x18000213d  lea     rcx, [rdi+10h]
0x180002141  cmp     rcx, r15
0x180002144  ja      short loc_180002160
0x180002146  mov     rcx, [rdi+r14+8]; hMem
0x18000214b  call    cs:__imp_LocalFree
0x180002152  nop     dword ptr [rax+rax+00h]
0x180002157  mov     qword ptr [rdi+r14+8], 0
0x180002160  inc     ebx
0x180002162  cmp     ebx, esi
0x180002164  jl      short loc_18000212D
0x180002166  add     rsp, 28h
0x18000216a  pop     r15
0x18000216c  pop     r14
0x18000216e  pop     rdi
0x18000216f  pop     rsi
0x180002170  pop     rbp
0x180002171  pop     rbx
0x180002172  retn
```
