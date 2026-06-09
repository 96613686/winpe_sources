# CreateEdpToast(EdpToastType,uchar * const,ulong)

- ea: `0x180008310`
- end: `0x1800083fa`
- name: `?CreateEdpToast@@YAJW4EdpToastType@@QEAEK@Z`
- size: `234`
- prototype: `__int64 __fastcall(int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e44`

## callees

- `0x1800023e0`
- `0x180008310`
- `0x18000ac1c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CreateEdpToast(int a1, __int64 a2, unsigned int a3)
{
  int v5; // ecx
  int v6; // edi
  EdpToast *v7; // rax
  EdpToast *v8; // rbx
  void **v9; // rax
  EdpToast *v10; // rax

  v5 = a1 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      return (unsigned int)-2147024809;
    v7 = (EdpToast *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      *((_QWORD *)v7 + 1) = 0;
      v9 = &EdpMissingCredsToast::`vftable';
LABEL_8:
      *(_QWORD *)v8 = v9;
      goto LABEL_10;
    }
  }
  else
  {
    v10 = (EdpToast *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v10;
    if ( v10 )
    {
      *((_QWORD *)v10 + 1) = 0;
      v9 = &EdpAadReauthToast::`vftable';
      *((_QWORD *)v8 + 2) = 0;
      goto LABEL_8;
    }
  }
  v8 = 0;
LABEL_10:
  if ( v8 )
  {
    v6 = (*(__int64 (__fastcall **)(EdpToast *, __int64, _QWORD))(*(_QWORD *)v8 + 8LL))(v8, a2, a3);
    if ( v6 >= 0 )
      v6 = EdpToast::LaunchToast(v8);
    (**(void (__fastcall ***)(EdpToast *, __int64))v8)(v8, 1);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008310  mov     [rsp+arg_0], rbx
0x180008315  mov     [rsp+arg_8], rsi
0x18000831a  push    rdi
0x18000831b  sub     rsp, 20h
0x18000831f  mov     edi, r8d
0x180008322  mov     rsi, rdx
0x180008325  sub     ecx, 1
0x180008328  jz      short loc_180008368
0x18000832a  cmp     ecx, 1
0x18000832d  jz      short loc_180008339
0x18000832f  mov     edi, 80070057h
0x180008334  jmp     loc_1800083E8
0x180008339  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008340  mov     ecx, 10h; unsigned __int64
0x180008345  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000834a  mov     [rsp+28h+arg_18], rax
0x18000834f  mov     rbx, rax
0x180008352  test    rax, rax
0x180008355  jz      short loc_1800083A2
0x180008357  mov     qword ptr [rax+8], 0
0x18000835f  lea     rax, ??_7EdpMissingCredsToast@@6B@; const EdpMissingCredsToast::`vftable'
0x180008366  jmp     short loc_18000839D
0x180008368  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000836f  mov     ecx, 18h; unsigned __int64
0x180008374  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008379  mov     [rsp+28h+arg_18], rax
0x18000837e  mov     rbx, rax
0x180008381  test    rax, rax
0x180008384  jz      short loc_1800083A2
0x180008386  mov     qword ptr [rax+8], 0
0x18000838e  lea     rax, ??_7EdpAadReauthToast@@6B@; const EdpAadReauthToast::`vftable'
0x180008395  mov     qword ptr [rbx+10h], 0
0x18000839d  mov     [rbx], rax
0x1800083a0  jmp     short loc_1800083A4
0x1800083a2  xor     ebx, ebx
0x1800083a4  test    rbx, rbx
0x1800083a7  jnz     short loc_1800083B0
0x1800083a9  mov     edi, 8007000Eh
0x1800083ae  jmp     short loc_1800083E8
0x1800083b0  mov     rax, [rbx]
0x1800083b3  mov     r8d, edi
0x1800083b6  mov     rdx, rsi
0x1800083b9  mov     rcx, rbx
0x1800083bc  mov     rax, [rax+8]
0x1800083c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c5  mov     edi, eax
0x1800083c7  test    eax, eax
0x1800083c9  js      short loc_1800083D5
0x1800083cb  mov     rcx, rbx; this
0x1800083ce  call    ?LaunchToast@EdpToast@@QEAAJXZ; EdpToast::LaunchToast(void)
0x1800083d3  mov     edi, eax
0x1800083d5  mov     rax, [rbx]
0x1800083d8  mov     edx, 1
0x1800083dd  mov     rcx, rbx
0x1800083e0  mov     rax, [rax]
0x1800083e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e8  mov     rbx, [rsp+28h+arg_0]
0x1800083ed  mov     eax, edi
0x1800083ef  mov     rsi, [rsp+28h+arg_8]
0x1800083f4  add     rsp, 20h
0x1800083f8  pop     rdi
0x1800083f9  retn
```
