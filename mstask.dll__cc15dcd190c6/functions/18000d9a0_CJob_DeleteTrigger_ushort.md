# CJob::DeleteTrigger(ushort)

- ea: `0x18000d9a0`
- end: `0x18000da3e`
- name: `?DeleteTrigger@CJob@@UEAAJG@Z`
- size: `158`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800085d8`
- `0x18000d9a0`
- `0x18001aa8e`

## pseudocode

```c
__int64 __fastcall CJob::DeleteTrigger(CJob *this, unsigned __int16 a2)
{
  __int64 v2; // rdi
  __int64 v4; // rcx
  unsigned __int16 v5; // cx
  unsigned int v6; // eax

  v2 = a2;
  if ( !CJob::_GetTrigger(this, a2) )
    return 2147750665LL;
  if ( (_WORD)v2 != --*(_WORD *)(v4 + 32) )
    memmove_0(
      (void *)(*((_QWORD *)this + 3) + 48 * v2),
      (const void *)(*((_QWORD *)this + 3) + 48 * v2 + 48),
      48 * (*((unsigned __int16 *)this + 16) - v2));
  while ( 1 )
  {
    v5 = *((_WORD *)this + 16);
    if ( (unsigned __int16)v2 >= v5 )
      break;
    --*(_WORD *)(48LL * (unsigned __int16)v2 + *((_QWORD *)this + 3) + 2);
    LOWORD(v2) = v2 + 1;
  }
  v6 = *((_DWORD *)this + 22) & 0x4FFFFFFF | 0x90000000;
  *((_DWORD *)this + 22) = v6;
  if ( !v5 )
    *((_DWORD *)this + 22) = v6 & 0xFF7FFFFF;
  return 0;
}

```

## disassembly

```asm
0x18000d9a0  push    rbx
0x18000d9a2  push    rbp
0x18000d9a3  push    rsi
0x18000d9a4  push    rdi
0x18000d9a5  sub     rsp, 28h
0x18000d9a9  movzx   edi, dx
0x18000d9ac  mov     rbx, rcx
0x18000d9af  movzx   edx, di; unsigned __int16
0x18000d9b2  call    ?_GetTrigger@CJob@@AEAAPEAU_TASK_TRIGGER@@G@Z; CJob::_GetTrigger(ushort)
0x18000d9b7  test    rax, rax
0x18000d9ba  jz      short loc_18000DA30
0x18000d9bc  mov     ebp, 0FFFFh
0x18000d9c1  add     [rcx+20h], bp
0x18000d9c5  cmp     di, [rcx+20h]
0x18000d9c9  jz      short loc_18000DA08
0x18000d9cb  movzx   eax, word ptr [rbx+20h]
0x18000d9cf  lea     rcx, [rdi+rdi*2]
0x18000d9d3  shl     rcx, 4
0x18000d9d7  sub     rax, rdi
0x18000d9da  add     rcx, [rbx+18h]; void *
0x18000d9de  lea     r8, [rax+rax*2]
0x18000d9e2  shl     r8, 4; Size
0x18000d9e6  lea     rdx, [rcx+30h]; Src
0x18000d9ea  call    memmove_0
0x18000d9ef  jmp     short loc_18000DA08
0x18000d9f1  movzx   eax, di
0x18000d9f4  lea     rcx, [rax+rax*2]
0x18000d9f8  mov     rax, [rbx+18h]
0x18000d9fc  shl     rcx, 4
0x18000da00  add     [rcx+rax+2], bp
0x18000da05  inc     di
0x18000da08  movzx   ecx, word ptr [rbx+20h]
0x18000da0c  cmp     di, cx
0x18000da0f  jb      short loc_18000D9F1
0x18000da11  mov     eax, [rbx+58h]
0x18000da14  btr     eax, 1Dh
0x18000da18  or      eax, 90000000h
0x18000da1d  mov     [rbx+58h], eax
0x18000da20  test    cx, cx
0x18000da23  jnz     short loc_18000DA2C
0x18000da25  btr     eax, 17h
0x18000da29  mov     [rbx+58h], eax
0x18000da2c  xor     eax, eax
0x18000da2e  jmp     short loc_18000DA35
0x18000da30  mov     eax, 80041309h
0x18000da35  add     rsp, 28h
0x18000da39  pop     rdi
0x18000da3a  pop     rsi
0x18000da3b  pop     rbp
0x18000da3c  pop     rbx
0x18000da3d  retn
```
