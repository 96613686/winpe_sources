# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180014060`
- end: `0x1800140cc`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `108`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f4c`
- `0x180008cc4`
- `0x1800090b8`
- `0x180020ae4`
- `0x1800226c4`
- `0x1800227ec`
- `0x180022920`
- `0x180022993`
- `0x180023305`
- `0x180023361`
- `0x1800233bd`
- `0x180023562`
- `0x1800235be`
- `0x18002361a`
- `0x180023676`

## callees

- `0x18000338c`
- `0x180014060`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edi
  unsigned __int64 v5; // rsi
  int v6; // eax
  va_list Args; // [rsp+78h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v5 = a2 - 1;
    v4 = 0;
    v6 = vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147024774;
    }
    else if ( v6 != v5 )
    {
      return v4;
    }
    a1[v5] = 0;
    return v4;
  }
  v4 = -2147024809;
  if ( a2 )
    *a1 = 0;
  return v4;
}

```

## disassembly

```asm
0x180014060  mov     [rsp+arg_10], r8
0x180014065  mov     qword ptr [rsp+Args], r9
0x18001406a  push    rbx
0x18001406b  push    rsi
0x18001406c  push    rdi
0x18001406d  push    r14
0x18001406f  sub     rsp, 38h
0x180014073  lea     rax, [rdx-1]
0x180014077  xor     ebx, ebx
0x180014079  mov     r14, rcx
0x18001407c  cmp     rax, 7FFFFFFEh
0x180014082  jbe     short loc_180014093
0x180014084  mov     edi, 80070057h
0x180014089  test    rdx, rdx
0x18001408c  jz      short loc_1800140BF
0x18001408e  mov     [rcx], bx
0x180014091  jmp     short loc_1800140BF
0x180014093  lea     rsi, [rdx-1]
0x180014097  mov     edi, ebx
0x180014099  mov     rdx, rsi; BufferCount
0x18001409c  lea     r9, [rsp+58h+Args]; Args
0x1800140a1  call    _vsnwprintf
0x1800140a6  test    eax, eax
0x1800140a8  js      short loc_1800140B5
0x1800140aa  cdqe
0x1800140ac  cmp     rax, rsi
0x1800140af  ja      short loc_1800140B5
0x1800140b1  jnz     short loc_1800140BF
0x1800140b3  jmp     short loc_1800140BA
0x1800140b5  mov     edi, 8007007Ah
0x1800140ba  mov     [r14+rsi*2], bx
0x1800140bf  mov     eax, edi
0x1800140c1  add     rsp, 38h
0x1800140c5  pop     r14
0x1800140c7  pop     rdi
0x1800140c8  pop     rsi
0x1800140c9  pop     rbx
0x1800140ca  retn
```
