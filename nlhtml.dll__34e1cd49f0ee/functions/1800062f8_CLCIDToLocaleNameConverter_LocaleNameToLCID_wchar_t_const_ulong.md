# CLCIDToLocaleNameConverter::LocaleNameToLCID(wchar_t const *,ulong *)

- ea: `0x1800062f8`
- end: `0x18000639a`
- name: `?LocaleNameToLCID@CLCIDToLocaleNameConverter@@QEAAJPEB_WPEAK@Z`
- size: `162`
- prototype: `__int64 __fastcall(CLCIDToLocaleNameConverter *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800063a0`

## callees

- `0x180006230`
- `0x1800062f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000638c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000638c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006349`

## pseudocode

```c
__int64 __fastcall CLCIDToLocaleNameConverter::LocaleNameToLCID(
        CLCIDToLocaleNameConverter *this,
        const wchar_t *a2,
        unsigned int *a3)
{
  int v6; // ebx
  __int64 v8; // rax
  unsigned int v9; // ebp
  wchar_t *v10; // rdi
  unsigned int i; // eax
  wchar_t v12; // dx

  v6 = CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(this, a2, a3);
  if ( v6 < 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = v8 + 1;
    v10 = (wchar_t *)CoTaskMemAlloc(2LL * (unsigned int)(v8 + 1));
    for ( i = 0; i < v9; ++i )
    {
      v12 = a2[i];
      if ( v12 == 45 )
      {
        v10[i] = 0;
        v6 = CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(this, v10, a3);
        break;
      }
      v10[i] = v12;
    }
    CoTaskMemFree(v10);
    if ( v6 >= 0 )
      return 1;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800062f8  push    rbx
0x1800062fa  push    rbp
0x1800062fb  push    rsi
0x1800062fc  push    rdi
0x1800062fd  push    r12
0x1800062ff  push    r13
0x180006301  push    r14
0x180006303  push    r15
0x180006305  sub     rsp, 28h
0x180006309  mov     r14, r8
0x18000630c  mov     rsi, rdx
0x18000630f  mov     r15, rcx
0x180006312  call    ?LocaleNameToLCIDHelper@CLCIDToLocaleNameConverter@@AEAAJPEB_WPEAK@Z; CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(wchar_t const *,ulong *)
0x180006317  xor     r12d, r12d
0x18000631a  mov     ebx, eax
0x18000631c  test    eax, eax
0x18000631e  js      short loc_180006333
0x180006320  mov     eax, ebx
0x180006322  add     rsp, 28h
0x180006326  pop     r15
0x180006328  pop     r14
0x18000632a  pop     r13
0x18000632c  pop     r12
0x18000632e  pop     rdi
0x18000632f  pop     rsi
0x180006330  pop     rbp
0x180006331  pop     rbx
0x180006332  retn
0x180006333  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006337  inc     rax
0x18000633a  cmp     [rsi+rax*2], r12w
0x18000633f  jnz     short loc_180006337
0x180006341  lea     ebp, [rax+1]
0x180006344  mov     ecx, ebp
0x180006346  add     rcx, rcx; cb
0x180006349  call    cs:__imp_CoTaskMemAlloc
0x18000634f  mov     rdi, rax
0x180006352  mov     r13d, 1
0x180006358  mov     eax, r12d
0x18000635b  cmp     eax, ebp
0x18000635d  jnb     short loc_180006389
0x18000635f  mov     ecx, eax
0x180006361  movzx   edx, word ptr [rsi+rcx*2]
0x180006365  cmp     dx, 2Dh ; '-'
0x180006369  jz      short loc_180006374
0x18000636b  mov     [rdi+rcx*2], dx
0x18000636f  add     eax, r13d
0x180006372  jmp     short loc_18000635B
0x180006374  mov     [rdi+rcx*2], r12w
0x180006379  mov     r8, r14; unsigned int *
0x18000637c  mov     rcx, r15; this
0x18000637f  mov     rdx, rdi; wchar_t *
0x180006382  call    ?LocaleNameToLCIDHelper@CLCIDToLocaleNameConverter@@AEAAJPEB_WPEAK@Z; CLCIDToLocaleNameConverter::LocaleNameToLCIDHelper(wchar_t const *,ulong *)
0x180006387  mov     ebx, eax
0x180006389  mov     rcx, rdi; pv
0x18000638c  call    cs:__imp_CoTaskMemFree
0x180006392  test    ebx, ebx
0x180006394  cmovns  ebx, r13d
0x180006398  jmp     short loc_180006320
```
