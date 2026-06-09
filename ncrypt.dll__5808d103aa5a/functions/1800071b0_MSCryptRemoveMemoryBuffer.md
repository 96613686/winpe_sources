# MSCryptRemoveMemoryBuffer

- ea: `0x1800071b0`
- end: `0x18000722d`
- name: `MSCryptRemoveMemoryBuffer`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007120`

## callees

- `0x1800071b0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800071df`
- `ntdll!RtlLeaveCriticalSection` at `0x1800071df`
- `ntdll!RtlEnterCriticalSection` at `0x1800071ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800071ca`

## pseudocode

```c
_QWORD *__fastcall MSCryptRemoveMemoryBuffer(_QWORD **a1, __int64 a2)
{
  _QWORD *v3; // rdi
  int v4; // esi
  _QWORD *v6; // rax
  _QWORD *result; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rdx
  _QWORD *v10; // rax

  v3 = 0;
  v4 = 0;
  RtlEnterCriticalSection(&CriticalSection);
  v6 = *a1;
  while ( v6 != a1 )
  {
    v3 = v6 - 2;
    v8 = (_QWORD *)*v6;
    v9 = v6;
    v6 = (_QWORD *)*v6;
    if ( v3[1] == a2 )
    {
      if ( (_QWORD *)v8[1] != v9 || (v10 = (_QWORD *)v9[1], (_QWORD *)*v10 != v9) )
        __fastfail(3u);
      *v10 = v8;
      v4 = 1;
      v8[1] = v10;
      break;
    }
  }
  RtlLeaveCriticalSection(&CriticalSection);
  result = 0;
  if ( v4 )
    return v3;
  return result;
}

```

## disassembly

```asm
0x1800071b0  push    rbx
0x1800071b2  push    rbp
0x1800071b3  push    rsi
0x1800071b4  push    rdi
0x1800071b5  sub     rsp, 28h
0x1800071b9  mov     rbx, rcx
0x1800071bc  xor     edi, edi
0x1800071be  lea     rcx, CriticalSection; CriticalSection
0x1800071c5  xor     esi, esi
0x1800071c7  mov     rbp, rdx
0x1800071ca  call    cs:__imp_RtlEnterCriticalSection
0x1800071d0  mov     rax, [rbx]
0x1800071d3  cmp     rax, rbx
0x1800071d6  jnz     short loc_1800071F6
0x1800071d8  lea     rcx, CriticalSection; CriticalSection
0x1800071df  call    cs:__imp_RtlLeaveCriticalSection
0x1800071e5  xor     eax, eax
0x1800071e7  test    esi, esi
0x1800071e9  cmovnz  rax, rdi
0x1800071ed  add     rsp, 28h
0x1800071f1  pop     rdi
0x1800071f2  pop     rsi
0x1800071f3  pop     rbp
0x1800071f4  pop     rbx
0x1800071f5  retn
0x1800071f6  lea     rdi, [rax-10h]
0x1800071fa  mov     rcx, [rax]
0x1800071fd  mov     rdx, rax
0x180007200  mov     rax, rcx
0x180007203  cmp     [rdi+8], rbp
0x180007207  jnz     short loc_1800071D3
0x180007209  cmp     [rcx+8], rdx
0x18000720d  jnz     short loc_180007226
0x18000720f  mov     rax, [rdx+8]
0x180007213  cmp     [rax], rdx
0x180007216  jnz     short loc_180007226
0x180007218  mov     [rax], rcx
0x18000721b  mov     esi, 1
0x180007220  mov     [rcx+8], rax
0x180007224  jmp     short loc_1800071D8
0x180007226  mov     ecx, 3
0x18000722b  int     29h; Win8: RtlFailFast(ecx)
```
