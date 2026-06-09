# CStackBuffer::Init(ulong)

- ea: `0x18003e690`
- end: `0x18003e708`
- name: `?Init@CStackBuffer@@QEAAJK@Z`
- size: `120`
- prototype: `int(CStackBuffer *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035e8c`
- `0x1800564a0`

## callees

- `0x18003e690`
- `0x180043100`
- `0x1800570f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e6cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e6cb`

## pseudocode

```c
__int64 __fastcall CStackBuffer::Init(CStackBuffer *this, unsigned int a2)
{
  unsigned int v2; // eax
  unsigned __int64 v5; // rdx
  __int64 result; // rax
  LPVOID v7; // rax
  SIZE_T cb; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 2);
  if ( a2 > v2 )
  {
    v5 = *((unsigned int *)this + 6);
    cb = 0;
    result = ULongLongMult(a2, v5, &cb);
    if ( (int)result < 0 )
      return result;
    v7 = CoTaskMemAlloc(cb);
    *(_QWORD *)this = v7;
    if ( !v7 )
      return 2147680264LL;
    *((_DWORD *)this + 2) = a2;
    v2 = a2;
  }
  memset_0(*(void **)this, 0, *((_DWORD *)this + 6) * v2);
  return 0;
}

```

## disassembly

```asm
0x18003e690  mov     r11, rsp
0x18003e693  mov     [r11+10h], rbx
0x18003e697  mov     [r11+18h], rsi
0x18003e69b  push    rdi
0x18003e69c  sub     rsp, 20h
0x18003e6a0  mov     eax, [rcx+8]
0x18003e6a3  mov     rbx, rcx
0x18003e6a6  mov     esi, edx
0x18003e6a8  cmp     edx, eax
0x18003e6aa  jbe     short loc_18003E6E5
0x18003e6ac  mov     edx, [rcx+18h]; unsigned __int64
0x18003e6af  lea     r8, [r11+8]; unsigned __int64 *
0x18003e6b3  mov     ecx, esi; unsigned __int64
0x18003e6b5  mov     qword ptr [r11+8], 0
0x18003e6bd  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003e6c2  test    eax, eax
0x18003e6c4  js      short loc_18003E6F8
0x18003e6c6  mov     rcx, [rsp+28h+cb]; cb
0x18003e6cb  call    cs:__imp_CoTaskMemAlloc
0x18003e6d1  mov     [rbx], rax
0x18003e6d4  test    rax, rax
0x18003e6d7  jnz     short loc_18003E6E0
0x18003e6d9  mov     eax, 80030008h
0x18003e6de  jmp     short loc_18003E6F8
0x18003e6e0  mov     [rbx+8], esi
0x18003e6e3  mov     eax, esi
0x18003e6e5  imul    eax, [rbx+18h]
0x18003e6e9  xor     edx, edx; Val
0x18003e6eb  mov     rcx, [rbx]; void *
0x18003e6ee  mov     r8d, eax; Size
0x18003e6f1  call    memset_0
0x18003e6f6  xor     eax, eax
0x18003e6f8  mov     rbx, [rsp+28h+arg_8]
0x18003e6fd  mov     rsi, [rsp+28h+arg_10]
0x18003e702  add     rsp, 20h
0x18003e706  pop     rdi
0x18003e707  retn
```
