# CBsString::ExtendBuffer(ulong)

- ea: `0x1800192b4`
- end: `0x180019350`
- name: `?ExtendBuffer@CBsString@@QEAAJK@Z`
- size: `156`
- prototype: `__int64 __fastcall(CBsString *__hidden this, unsigned int)`
- caller_count: `18`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf94`
- `0x180013c1c`
- `0x1800140bc`
- `0x1800157fc`
- `0x1800158a4`
- `0x1800164ac`
- `0x180016ea8`
- `0x180017f60`
- `0x180018ed8`
- `0x180019158`
- `0x180019228`
- `0x180019544`
- `0x1800197a8`
- `0x18001a6c0`
- `0x18001c17c`
- `0x18002af08`
- `0x18002cec0`
- `0x1800530b8`

## callees

- `0x1800192b4`
- `0x180019358`
- `0x180067af2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800192e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800192e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019348`

## pseudocode

```c
__int64 __fastcall CBsString::ExtendBuffer(const void **this, unsigned int a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ebp
  _WORD *v6; // r14
  unsigned __int16 *v7; // rdi

  v2 = 0;
  if ( *((_DWORD *)this + 3) < a2 )
  {
    v4 = CalculateRoundedUpBufferSize(a2);
    v5 = v4 - 1;
    if ( v4 - 1 > 0xFFFFFFE )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v6 = CoTaskMemAlloc(2LL * v4);
      if ( v6 )
      {
        *v6 = 0;
        v7 = (unsigned __int16 *)*this;
        memcpy_0(v6, *this, 2LL * *((unsigned int *)this + 2));
        v6[*((unsigned int *)this + 2)] = 0;
        *((_DWORD *)this + 3) = v5;
        *this = v6;
        if ( v7 && v7 != &qword_18006F470 )
          CoTaskMemFree(v7);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800192b4  push    rbx
0x1800192b6  push    rbp
0x1800192b7  push    rsi
0x1800192b8  push    rdi
0x1800192b9  push    r14
0x1800192bb  sub     rsp, 20h
0x1800192bf  xor     ebx, ebx
0x1800192c1  mov     rsi, rcx
0x1800192c4  cmp     [rcx+0Ch], edx
0x1800192c7  jnb     short loc_18001932A
0x1800192c9  mov     ecx, edx
0x1800192cb  call    _CalculateRoundedUpBufferSize
0x1800192d0  lea     ebp, [rax-1]
0x1800192d3  cmp     ebp, 0FFFFFFEh
0x1800192d9  ja      short loc_180019337
0x1800192db  mov     ecx, eax
0x1800192dd  add     rcx, rcx; cb
0x1800192e0  call    cs:__imp_CoTaskMemAlloc
0x1800192e6  mov     r14, rax
0x1800192e9  test    rax, rax
0x1800192ec  jz      short loc_18001933E
0x1800192ee  xor     eax, eax
0x1800192f0  mov     rcx, r14; void *
0x1800192f3  mov     [r14], ax
0x1800192f7  mov     rdi, [rsi]
0x1800192fa  mov     r8d, [rsi+8]
0x1800192fe  mov     rdx, rdi; Src
0x180019301  add     r8, r8; Size
0x180019304  call    memcpy_0
0x180019309  mov     edx, [rsi+8]
0x18001930c  xor     eax, eax
0x18001930e  mov     [r14+rdx*2], ax
0x180019313  mov     [rsi+0Ch], ebp
0x180019316  mov     [rsi], r14
0x180019319  test    rdi, rdi
0x18001931c  jz      short loc_18001932A
0x18001931e  lea     rax, qword_18006F470
0x180019325  cmp     rdi, rax
0x180019328  jnz     short loc_180019345
0x18001932a  mov     eax, ebx
0x18001932c  add     rsp, 20h
0x180019330  pop     r14
0x180019332  pop     rdi
0x180019333  pop     rsi
0x180019334  pop     rbp
0x180019335  pop     rbx
0x180019336  retn
0x180019337  mov     ebx, 80070057h
0x18001933c  jmp     short loc_18001932A
0x18001933e  mov     ebx, 8007000Eh
0x180019343  jmp     short loc_18001932A
0x180019345  mov     rcx, rdi; pv
0x180019348  call    cs:__imp_CoTaskMemFree
0x18001934e  jmp     short loc_18001932A
```
