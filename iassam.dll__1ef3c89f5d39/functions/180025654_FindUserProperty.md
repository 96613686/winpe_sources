# FindUserProperty

- ea: `0x180025654`
- end: `0x18002571c`
- name: `FindUserProperty`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025724`

## callees

- `0x180025654`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800256da`
- `ntdll!RtlCompareMemory` at `0x1800256da`

## pseudocode

```c
__int64 __fastcall FindUserProperty(_WORD *a1, _WORD *a2, unsigned __int16 **a3, unsigned __int16 *a4)
{
  unsigned int v8; // ebp
  __int64 v9; // rdi
  __int64 v10; // rax
  unsigned __int16 v11; // di
  unsigned __int16 i; // ax

  v8 = 0;
  if ( a1 )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( a1[v10] );
    if ( (unsigned __int64)(2 * v10) > 0x60 && a1[48] == 80 )
    {
      *a3 = a1 + 50;
      do
        ++v9;
      while ( a2[v9] );
      v11 = 2 * v9;
      *a4 = 1;
      for ( i = 1; i <= a1[49]; i = *a4 )
      {
        if ( v11 == **a3 && RtlCompareMemory(*a3 + 3, a2, v11) == v11 )
          return 1;
        *a3 = (unsigned __int16 *)((char *)*a3 + (*a3)[1] + **a3 + 6);
        ++*a4;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180025654  push    rbx
0x180025656  push    rbp
0x180025657  push    rsi
0x180025658  push    rdi
0x180025659  push    r12
0x18002565b  push    r13
0x18002565d  push    r14
0x18002565f  push    r15
0x180025661  sub     rsp, 28h
0x180025665  mov     rsi, rcx
0x180025668  mov     r15, r9
0x18002566b  xor     ecx, ecx
0x18002566d  mov     r14, r8
0x180025670  mov     r12, rdx
0x180025673  mov     ebp, ecx
0x180025675  test    rsi, rsi
0x180025678  jz      loc_180025709
0x18002567e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025682  mov     rax, rdi
0x180025685  inc     rax
0x180025688  cmp     [rsi+rax*2], cx
0x18002568c  jnz     short loc_180025685
0x18002568e  add     rax, rax
0x180025691  cmp     rax, 60h ; '`'
0x180025695  jbe     short loc_180025709
0x180025697  cmp     word ptr [rsi+60h], 50h ; 'P'
0x18002569c  jnz     short loc_180025709
0x18002569e  lea     rax, [rsi+64h]
0x1800256a2  mov     [r8], rax
0x1800256a5  inc     rdi
0x1800256a8  cmp     [rdx+rdi*2], cx
0x1800256ac  jnz     short loc_1800256A5
0x1800256ae  mov     r13d, 1
0x1800256b4  add     di, di
0x1800256b7  mov     [r9], r13w
0x1800256bb  movzx   eax, r13w
0x1800256bf  cmp     ax, [rsi+62h]
0x1800256c3  ja      short loc_180025709
0x1800256c5  mov     rcx, [r14]
0x1800256c8  cmp     di, [rcx]
0x1800256cb  jnz     short loc_1800256E5
0x1800256cd  movzx   ebx, di
0x1800256d0  add     rcx, 6; Source1
0x1800256d4  mov     r8d, ebx; Length
0x1800256d7  mov     rdx, r12; Source2
0x1800256da  call    cs:__imp_RtlCompareMemory
0x1800256e0  cmp     rax, rbx
0x1800256e3  jz      short loc_180025706
0x1800256e5  mov     rdx, [r14]
0x1800256e8  movzx   eax, word ptr [rdx+2]
0x1800256ec  movzx   ecx, word ptr [rdx]
0x1800256ef  add     rax, rdx
0x1800256f2  add     rcx, 6
0x1800256f6  add     rcx, rax
0x1800256f9  mov     [r14], rcx
0x1800256fc  add     [r15], r13w
0x180025700  movzx   eax, word ptr [r15]
0x180025704  jmp     short loc_1800256BF
0x180025706  mov     ebp, r13d
0x180025709  mov     eax, ebp
0x18002570b  add     rsp, 28h
0x18002570f  pop     r15
0x180025711  pop     r14
0x180025713  pop     r13
0x180025715  pop     r12
0x180025717  pop     rdi
0x180025718  pop     rsi
0x180025719  pop     rbp
0x18002571a  pop     rbx
0x18002571b  retn
```
