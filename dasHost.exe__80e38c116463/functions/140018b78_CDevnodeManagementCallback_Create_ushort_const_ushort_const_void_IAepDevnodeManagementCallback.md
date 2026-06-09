# CDevnodeManagementCallback::Create(ushort const *,ushort const *,void *,IAepDevnodeManagementCallback * *)

- ea: `0x140018b78`
- end: `0x140018ce1`
- name: `?Create@CDevnodeManagementCallback@@SAJPEBG0PEAXPEAPEAUIAepDevnodeManagementCallback@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, const unsigned __int16 *, void *, RTL_SRWLOCK **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000fea4`

## callees

- `0x14000190c`
- `0x140009060`
- `0x140009090`
- `0x140018b78`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140018c92`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x140018c92`

## pseudocode

```c
__int64 __fastcall CDevnodeManagementCallback::Create(
        const unsigned __int16 *Src,
        const unsigned __int16 *a2,
        void *a3,
        RTL_SRWLOCK **a4)
{
  __int64 v6; // rdi
  __int64 v7; // rcx
  void *v8; // rax
  void *v9; // r15
  unsigned int v10; // r14d
  void *v11; // rsi
  __int64 v12; // r8
  __int64 v13; // rcx
  void *v14; // rax
  RTL_SRWLOCK *v15; // rdi
  void *v17; // [rsp+20h] [rbp-38h]
  void *v18; // [rsp+28h] [rbp-30h]

  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( Src[v7] );
  v8 = (void *)DAF_user_alloc(2 * v7 + 2);
  v9 = v8;
  v18 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  v10 = 0;
  v11 = 0;
  v17 = 0;
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  memcpy_0(v8, Src, 2 * v12 + 2);
  if ( a2 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    v14 = (void *)DAF_user_alloc(2 * v13 + 2);
    v11 = v14;
    v17 = v14;
    if ( !v14 )
    {
      v10 = -2147024882;
LABEL_14:
      MIDL_user_free(v9);
      if ( v11 )
        MIDL_user_free(v11);
      return v10;
    }
    do
      ++v6;
    while ( a2[v6] );
    memcpy_0(v14, a2, 2 * v6 + 2);
  }
  try
  {
    v15 = (RTL_SRWLOCK *)operator new(0x40u);
    v15->Ptr = &CDevnodeManagementCallback::`vftable'{for `IAepDevnodeManagementCallback'};
    v15[1].Ptr = &CDevnodeManagementCallback::`vftable'{for `IServiceProvider'};
    LODWORD(v15[2].Ptr) = 1;
    v15[3].Ptr = v9;
    v15[4].Ptr = v11;
    v15[5].Ptr = 0;
    LODWORD(v15[7].Ptr) = 1;
    InitializeSRWLock(v15 + 6);
    *a4 = v15;
  }
  catch ( std::bad_alloc )
  {
    v10 = -2147024882;
    v9 = v18;
    v11 = v17;
    goto LABEL_14;
  }
  v15 = (RTL_SRWLOCK *)operator new(0x40u);
}

```

## disassembly

```asm
0x140018b78  mov     rax, rsp
0x140018b7b  mov     [rax+8], rbx
0x140018b7f  mov     [rax+10h], rsi
0x140018b83  mov     [rax+20h], r9
0x140018b87  mov     [rax+18h], r8
0x140018b8b  push    rdi
0x140018b8c  push    r12
0x140018b8e  push    r13
0x140018b90  push    r14
0x140018b92  push    r15
0x140018b94  sub     rsp, 30h
0x140018b98  mov     r13, rdx
0x140018b9b  mov     r12, rcx
0x140018b9e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140018ba2  mov     rcx, rdi
0x140018ba5  xor     ebx, ebx
0x140018ba7  inc     rcx
0x140018baa  cmp     [r12+rcx*2], bx
0x140018baf  jnz     short loc_140018BA7
0x140018bb1  lea     rcx, ds:2[rcx*2]
0x140018bb9  call    DAF_user_alloc
0x140018bbe  mov     r15, rax
0x140018bc1  mov     [rsp+58h+var_30], rax
0x140018bc6  test    rax, rax
0x140018bc9  jnz     short loc_140018BD6
0x140018bcb  mov     r14d, 8007000Eh
0x140018bd1  jmp     loc_140018CC6
0x140018bd6  mov     r14d, ebx
0x140018bd9  mov     rsi, rbx
0x140018bdc  mov     [rsp+58h+var_38], rbx
0x140018be1  mov     r8, rdi
0x140018be4  inc     r8
0x140018be7  cmp     [r12+r8*2], bx
0x140018bec  jnz     short loc_140018BE4
0x140018bee  lea     r8, ds:2[r8*2]; Size
0x140018bf6  mov     rdx, r12; Src
0x140018bf9  mov     rcx, r15; void *
0x140018bfc  call    memcpy_0
0x140018c01  test    r13, r13
0x140018c04  jz      short loc_140018C55
0x140018c06  mov     rcx, rdi
0x140018c09  inc     rcx
0x140018c0c  cmp     [r13+rcx*2+0], bx
0x140018c12  jnz     short loc_140018C09
0x140018c14  lea     rcx, ds:2[rcx*2]
0x140018c1c  call    DAF_user_alloc
0x140018c21  mov     rsi, rax
0x140018c24  mov     [rsp+58h+var_38], rax
0x140018c29  test    rax, rax
0x140018c2c  jnz     short loc_140018C36
0x140018c2e  mov     r14d, 8007000Eh
0x140018c34  jmp     short loc_140018CB1
0x140018c36  inc     rdi
0x140018c39  cmp     [r13+rdi*2+0], bx
0x140018c3f  jnz     short loc_140018C36
0x140018c41  lea     r8, ds:2[rdi*2]; Size
0x140018c49  mov     rdx, r13; Src
0x140018c4c  mov     rcx, rax; void *
0x140018c4f  call    memcpy_0
0x140018c54  nop
0x140018c55  mov     ecx, 40h ; '@'; Size
0x140018c5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018c5f  mov     rdi, rax
0x140018c62  lea     rax, ??_7CDevnodeManagementCallback@@6BIAepDevnodeManagementCallback@@@; const CDevnodeManagementCallback::`vftable'{for `IAepDevnodeManagementCallback'}
0x140018c69  mov     [rdi], rax
0x140018c6c  lea     rax, ??_7CDevnodeManagementCallback@@6BIServiceProvider@@@; const CDevnodeManagementCallback::`vftable'{for `IServiceProvider'}
0x140018c73  mov     [rdi+8], rax
0x140018c77  mov     eax, 1
0x140018c7c  mov     [rdi+10h], eax
0x140018c7f  mov     [rdi+18h], r15
0x140018c83  mov     [rdi+20h], rsi
0x140018c87  mov     [rdi+28h], rbx
0x140018c8b  mov     [rdi+38h], eax
0x140018c8e  lea     rcx, [rdi+30h]; SRWLock
0x140018c92  call    cs:__imp_InitializeSRWLock
0x140018c98  mov     rax, [rsp+58h+arg_18]
0x140018c9d  mov     [rax], rdi
0x140018ca0  jmp     short loc_140018CC6
0x140018ca2  mov     r14d, [rsp+58h+arg_10]
0x140018ca7  mov     r15, [rsp+58h+var_30]
0x140018cac  mov     rsi, [rsp+58h+var_38]
0x140018cb1  mov     rcx, r15; void *
0x140018cb4  call    MIDL_user_free
0x140018cb9  test    rsi, rsi
0x140018cbc  jz      short loc_140018CC6
0x140018cbe  mov     rcx, rsi; void *
0x140018cc1  call    MIDL_user_free
0x140018cc6  mov     eax, r14d
0x140018cc9  mov     rbx, [rsp+58h+arg_0]
0x140018cce  mov     rsi, [rsp+58h+arg_8]
0x140018cd3  add     rsp, 30h
0x140018cd7  pop     r15
0x140018cd9  pop     r14
0x140018cdb  pop     r13
0x140018cdd  pop     r12
0x140018cdf  pop     rdi
0x140018ce0  retn
```
