# IDriverMessageId

- ea: `0x1800043d0`
- end: `0x180004463`
- name: `IDriverMessageId`
- size: `147`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180002540`
- `0x180002b00`
- `0x180003fc0`
- `0x1800040a0`
- `0x180004470`
- `0x1800045b0`
- `0x1800046f0`
- `0x180005530`
- `0x180006310`
- `0x180008160`
- `0x180008dd8`
- `0x18000acac`
- `0x18000ae04`
- `0x18000b420`
- `0x18000b6bc`
- `0x18000b8d0`

## callees

- `0x1800040a0`
- `0x1800043d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000440a`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000440a`

## pseudocode

```c
LRESULT __fastcall IDriverMessageId(__int64 a1, UINT a2, LPARAM a3, LPARAM a4)
{
  __int64 (__fastcall *v8)(_QWORD, __int64, _QWORD, LPARAM, LPARAM); // rax
  HDRVR v9; // rcx
  LRESULT result; // rax

  if ( !a1 )
    return 5;
  if ( (*(_DWORD *)(a1 + 56) & 1) != 0 || a2 - 1 <= 2 || (result = (unsigned int)IDriverLoad(a1), !(_DWORD)result) )
  {
    v8 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPARAM, LPARAM))(a1 + 96);
    if ( v8 )
    {
      if ( v8 == (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, LPARAM, LPARAM))-1LL )
        return 1;
      else
        return v8(*(_QWORD *)(a1 + 104), a1, a2, a3, a4);
    }
    v9 = *(HDRVR *)(a1 + 88);
    if ( v9 )
      return SendDriverMessage(v9, a2, a3, a4);
    return 5;
  }
  return result;
}

```

## disassembly

```asm
0x1800043d0  push    rbx
0x1800043d2  push    rbp
0x1800043d3  push    rsi
0x1800043d4  push    rdi
0x1800043d5  sub     rsp, 38h
0x1800043d9  mov     rsi, r9
0x1800043dc  mov     rbp, r8
0x1800043df  mov     edi, edx
0x1800043e1  mov     rbx, rcx
0x1800043e4  test    rcx, rcx
0x1800043e7  jz      short loc_180004419
0x1800043e9  mov     eax, [rcx+38h]
0x1800043ec  test    al, 1
0x1800043ee  jz      short loc_180004446
0x1800043f0  mov     rax, [rbx+60h]
0x1800043f4  test    rax, rax
0x1800043f7  jnz     short loc_180004420
0x1800043f9  mov     rcx, [rbx+58h]; hDriver
0x1800043fd  test    rcx, rcx
0x180004400  jz      short loc_180004419
0x180004402  mov     r9, rsi; lParam2
0x180004405  mov     r8, rbp; lParam1
0x180004408  mov     edx, edi; message
0x18000440a  call    cs:__imp_SendDriverMessage
0x180004410  add     rsp, 38h
0x180004414  pop     rdi
0x180004415  pop     rsi
0x180004416  pop     rbp
0x180004417  pop     rbx
0x180004418  retn
0x180004419  mov     eax, 5
0x18000441e  jmp     short loc_180004410
0x180004420  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004424  jz      short loc_18000445C
0x180004426  mov     rcx, [rbx+68h]
0x18000442a  mov     r9, rbp
0x18000442d  mov     r8d, edi
0x180004430  mov     [rsp+58h+var_38], rsi
0x180004435  mov     rdx, rbx
0x180004438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443d  add     rsp, 38h
0x180004441  pop     rdi
0x180004442  pop     rsi
0x180004443  pop     rbp
0x180004444  pop     rbx
0x180004445  retn
0x180004446  lea     eax, [rdx-1]
0x180004449  cmp     eax, 2
0x18000444c  jbe     short loc_1800043F0
0x18000444e  call    IDriverLoad
0x180004453  mov     eax, eax
0x180004455  test    rax, rax
0x180004458  jz      short loc_1800043F0
0x18000445a  jmp     short loc_180004410
0x18000445c  mov     eax, 1
0x180004461  jmp     short loc_180004410
```
