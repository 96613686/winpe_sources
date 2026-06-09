# CSimpEnumSTATSTG::Next(ulong,tagSTATSTG *,ulong *)

- ea: `0x18004fa90`
- end: `0x18004fb81`
- name: `?Next@CSimpEnumSTATSTG@@UEAAJKPEAUtagSTATSTG@@PEAK@Z`
- size: `241`
- prototype: `int(CSimpEnumSTATSTG *__hidden this, unsigned int, struct tagSTATSTG *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180043100`
- `0x18004fa90`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004fafd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004fafd`

## pseudocode

```c
__int64 __fastcall CSimpEnumSTATSTG::Next(CSimpEnumSTATSTG *this, int a2, struct tagSTATSTG *a3, unsigned int *a4)
{
  __int64 v7; // rax
  void *v8; // rax
  unsigned int v9; // edi

  if ( a2 != 1 || !a3 )
    return 2147680343LL;
  if ( a4 )
    *a4 = 0;
  v7 = *((_QWORD *)this + 3);
  if ( v7 == *((_QWORD *)this + 2) && *((_QWORD *)this + 2) )
  {
    v7 = *(_QWORD *)(v7 + 80);
    *((_QWORD *)this + 3) = v7;
  }
  if ( v7 )
  {
    memset_0(a3, 0, 0x50u);
    v8 = CoTaskMemAlloc(*(unsigned __int16 *)(*((_QWORD *)this + 3) + 64LL) + 2LL);
    *(_QWORD *)a3 = v8;
    if ( v8 )
    {
      v9 = 0;
      memcpy_0(v8, *((const void **)this + 3), *(unsigned __int16 *)(*((_QWORD *)this + 3) + 64LL));
      *(_WORD *)(*(_QWORD *)a3 + 2 * ((unsigned __int64)*(unsigned __int16 *)(*((_QWORD *)this + 3) + 64LL) >> 1)) = 0;
      *((_DWORD *)a3 + 4) = *(_DWORD *)(*((_QWORD *)this + 3) + 72LL);
      *((_DWORD *)a3 + 5) = 0;
      *((_DWORD *)a3 + 2) = 2;
      *((_QWORD *)this + 3) = *(_QWORD *)(*((_QWORD *)this + 3) + 80LL);
      if ( a4 )
        *a4 = 1;
    }
    else
    {
      return (unsigned int)-2147287032;
    }
  }
  else
  {
    return 1;
  }
  return v9;
}

```

## disassembly

```asm
0x18004fa90  push    rbx
0x18004fa92  push    rsi
0x18004fa93  push    rdi
0x18004fa94  push    r14
0x18004fa96  sub     rsp, 28h
0x18004fa9a  mov     rsi, r9
0x18004fa9d  mov     r14, r8
0x18004faa0  mov     rbx, rcx
0x18004faa3  cmp     edx, 1
0x18004faa6  jnz     loc_18004FB72
0x18004faac  test    r8, r8
0x18004faaf  jz      loc_18004FB72
0x18004fab5  test    r9, r9
0x18004fab8  jz      short loc_18004FAC1
0x18004faba  mov     dword ptr [r9], 0
0x18004fac1  mov     rax, [rcx+18h]
0x18004fac5  cmp     rax, [rcx+10h]
0x18004fac9  jnz     short loc_18004FADA
0x18004facb  cmp     qword ptr [rcx+10h], 0
0x18004fad0  jz      short loc_18004FADA
0x18004fad2  mov     rax, [rax+50h]
0x18004fad6  mov     [rcx+18h], rax
0x18004fada  test    rax, rax
0x18004fadd  jz      loc_18004FB69
0x18004fae3  xor     edx, edx; Val
0x18004fae5  mov     rcx, r14; void *
0x18004fae8  lea     r8d, [rdx+50h]; Size
0x18004faec  call    memset_0
0x18004faf1  mov     rax, [rbx+18h]
0x18004faf5  movzx   ecx, word ptr [rax+40h]
0x18004faf9  add     rcx, 2; cb
0x18004fafd  call    cs:__imp_CoTaskMemAlloc
0x18004fb03  mov     [r14], rax
0x18004fb06  test    rax, rax
0x18004fb09  jz      short loc_18004FB62
0x18004fb0b  mov     rdx, [rbx+18h]; Src
0x18004fb0f  mov     rcx, rax; void *
0x18004fb12  xor     edi, edi
0x18004fb14  movzx   r8d, word ptr [rdx+40h]; Size
0x18004fb19  call    memcpy_0
0x18004fb1e  mov     rax, [rbx+18h]
0x18004fb22  mov     rcx, [r14]
0x18004fb25  movzx   edx, word ptr [rax+40h]
0x18004fb29  xor     eax, eax
0x18004fb2b  shr     rdx, 1
0x18004fb2e  mov     [rcx+rdx*2], ax
0x18004fb32  mov     rax, [rbx+18h]
0x18004fb36  mov     ecx, [rax+48h]
0x18004fb39  mov     [r14+10h], ecx
0x18004fb3d  mov     [r14+14h], edi
0x18004fb41  mov     dword ptr [r14+8], 2
0x18004fb49  mov     rax, [rbx+18h]
0x18004fb4d  mov     rcx, [rax+50h]
0x18004fb51  mov     [rbx+18h], rcx
0x18004fb55  test    rsi, rsi
0x18004fb58  jz      short loc_18004FB6E
0x18004fb5a  mov     dword ptr [rsi], 1
0x18004fb60  jmp     short loc_18004FB6E
0x18004fb62  mov     edi, 80030008h
0x18004fb67  jmp     short loc_18004FB6E
0x18004fb69  mov     edi, 1
0x18004fb6e  mov     eax, edi
0x18004fb70  jmp     short loc_18004FB77
0x18004fb72  mov     eax, 80030057h
0x18004fb77  add     rsp, 28h
0x18004fb7b  pop     r14
0x18004fb7d  pop     rdi
0x18004fb7e  pop     rsi
0x18004fb7f  pop     rbx
0x18004fb80  retn
```
