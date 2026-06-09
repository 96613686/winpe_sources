# xdr_replymsg

- ea: `0x14000c724`
- end: `0x14000c806`
- name: `xdr_replymsg`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001b5c`
- `0x14000d820`
- `0x14000e320`

## callees

- `0x14000c3ec`
- `0x14000c654`
- `0x14000c724`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall xdr_replymsg(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebp
  unsigned int (*v5)(void); // rax
  int v6; // eax
  _DWORD *v7; // rdi
  int v8; // eax

  v2 = 0;
  if ( *(_DWORD *)a1 == 1 )
  {
    v5 = **(unsigned int (***)(void))(a1 + 8);
  }
  else
  {
    if ( *(_DWORD *)a1 )
    {
      if ( *(_DWORD *)a1 != 2 )
        return v2;
      goto LABEL_8;
    }
    v5 = *(unsigned int (**)(void))(*(_QWORD *)(a1 + 8) + 8LL);
  }
  if ( !v5() )
    return v2;
LABEL_8:
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
    {
      if ( *(_DWORD *)a1 != 2 )
        return v2;
      goto LABEL_15;
    }
    v6 = (**(__int64 (__fastcall ***)(__int64, __int64))(a1 + 8))(a1, a2 + 4);
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 8) + 8LL))(a1, a2 + 4);
  }
  if ( !v6 )
    return v2;
LABEL_15:
  if ( *(_DWORD *)(a2 + 4) != 1 )
    return v2;
  v7 = (_DWORD *)(a2 + 8);
  if ( !*(_DWORD *)a1 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 8) + 8LL))(a1, a2 + 8);
    goto LABEL_20;
  }
  if ( *(_DWORD *)a1 == 1 )
  {
    v8 = (**(__int64 (__fastcall ***)(__int64, __int64))(a1 + 8))(a1, a2 + 8);
LABEL_20:
    if ( !v8 )
      return v2;
    goto LABEL_23;
  }
  if ( *(_DWORD *)a1 != 2 )
    return v2;
LABEL_23:
  if ( !*v7 )
    return (unsigned int)xdr_accepted_reply(a1, a2 + 16);
  if ( *v7 == 1 )
    return (unsigned int)xdr_rejected_reply(a1, a2 + 16);
  return v2;
}

```

## disassembly

```asm
0x14000c724  push    rbx
0x14000c726  push    rbp
0x14000c727  push    rsi
0x14000c728  push    rdi
0x14000c729  sub     rsp, 28h
0x14000c72d  xor     ebp, ebp
0x14000c72f  mov     rsi, rdx
0x14000c732  cmp     dword ptr [rcx], 1
0x14000c735  mov     rbx, rcx
0x14000c738  jnz     short loc_14000C743
0x14000c73a  mov     rax, [rcx+8]
0x14000c73e  mov     rax, [rax]
0x14000c741  jmp     short loc_14000C74F
0x14000c743  cmp     [rcx], ebp
0x14000c745  jnz     short loc_14000C75E
0x14000c747  mov     rax, [rcx+8]
0x14000c74b  mov     rax, [rax+8]
0x14000c74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c754  test    eax, eax
0x14000c756  jz      loc_14000C7FB
0x14000c75c  jmp     short loc_14000C767
0x14000c75e  cmp     dword ptr [rcx], 2
0x14000c761  jnz     loc_14000C7FB
0x14000c767  lea     rdi, [rsi+4]
0x14000c76b  cmp     [rbx], ebp
0x14000c76d  jnz     short loc_14000C779
0x14000c76f  mov     rax, [rbx+8]
0x14000c773  mov     rax, [rax+8]
0x14000c777  jmp     short loc_14000C785
0x14000c779  cmp     dword ptr [rbx], 1
0x14000c77c  jnz     short loc_14000C796
0x14000c77e  mov     rax, [rbx+8]
0x14000c782  mov     rax, [rax]
0x14000c785  mov     rdx, rdi
0x14000c788  mov     rcx, rbx
0x14000c78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c790  test    eax, eax
0x14000c792  jz      short loc_14000C7FB
0x14000c794  jmp     short loc_14000C79B
0x14000c796  cmp     dword ptr [rbx], 2
0x14000c799  jnz     short loc_14000C7FB
0x14000c79b  cmp     dword ptr [rdi], 1
0x14000c79e  jnz     short loc_14000C7FB
0x14000c7a0  lea     rdi, [rsi+8]
0x14000c7a4  cmp     [rbx], ebp
0x14000c7a6  jnz     short loc_14000C7B2
0x14000c7a8  mov     rax, [rbx+8]
0x14000c7ac  mov     rax, [rax+8]
0x14000c7b0  jmp     short loc_14000C7BE
0x14000c7b2  cmp     dword ptr [rbx], 1
0x14000c7b5  jnz     short loc_14000C7CF
0x14000c7b7  mov     rax, [rbx+8]
0x14000c7bb  mov     rax, [rax]
0x14000c7be  mov     rdx, rdi
0x14000c7c1  mov     rcx, rbx
0x14000c7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7c9  test    eax, eax
0x14000c7cb  jz      short loc_14000C7FB
0x14000c7cd  jmp     short loc_14000C7D4
0x14000c7cf  cmp     dword ptr [rbx], 2
0x14000c7d2  jnz     short loc_14000C7FB
0x14000c7d4  mov     ecx, [rdi]
0x14000c7d6  test    ecx, ecx
0x14000c7d8  jz      short loc_14000C7ED
0x14000c7da  cmp     ecx, 1
0x14000c7dd  jnz     short loc_14000C7FB
0x14000c7df  lea     rdx, [rsi+10h]
0x14000c7e3  mov     rcx, rbx
0x14000c7e6  call    xdr_rejected_reply
0x14000c7eb  jmp     short loc_14000C7F9
0x14000c7ed  lea     rdx, [rsi+10h]
0x14000c7f1  mov     rcx, rbx
0x14000c7f4  call    xdr_accepted_reply
0x14000c7f9  mov     ebp, eax
0x14000c7fb  mov     eax, ebp
0x14000c7fd  add     rsp, 28h
0x14000c801  pop     rdi
0x14000c802  pop     rsi
0x14000c803  pop     rbp
0x14000c804  pop     rbx
0x14000c805  retn
```
