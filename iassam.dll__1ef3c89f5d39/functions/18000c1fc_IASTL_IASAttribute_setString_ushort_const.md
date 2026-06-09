# IASTL::IASAttribute::setString(ushort const *)

- ea: `0x18000c1fc`
- end: `0x18000c283`
- name: `?setString@IASAttribute@IASTL@@QEAAXPEBG@Z`
- size: `135`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this, const unsigned __int16 *Src)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b958`
- `0x1800206a8`
- `0x18002110c`
- `0x1800213d0`
- `0x1800276b0`

## callees

- `0x180001f26`
- `0x18000b680`
- `0x18000b81c`
- `0x18000c1fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c231`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setString(IASTL::IASAttribute *this, const unsigned __int16 *Src)
{
  void *v4; // rdi
  __int64 v5; // rax
  SIZE_T v6; // rbp
  void *v7; // rax
  int v8; // edx

  v4 = 0;
  if ( Src )
  {
    v5 = -1;
    do
      ++v5;
    while ( Src[v5] );
    v6 = 2 * v5 + 2;
    v7 = CoTaskMemAlloc(v6);
    v4 = v7;
    if ( !v7 )
      IASTL::issue_error((IASTL *)0x8007000ELL, v8);
    memcpy_0(v7, Src, v6);
  }
  IASTL::IASAttribute::clearValue(this);
  *(_QWORD *)(*(_QWORD *)this + 32LL) = v4;
  *(_QWORD *)(*(_QWORD *)this + 24LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = 5;
}

```

## disassembly

```asm
0x18000c1fc  push    rbx
0x18000c1fe  push    rbp
0x18000c1ff  push    rsi
0x18000c200  push    rdi
0x18000c201  push    r14
0x18000c203  sub     rsp, 20h
0x18000c207  xor     r14d, r14d
0x18000c20a  mov     rsi, rdx
0x18000c20d  mov     rbx, rcx
0x18000c210  mov     edi, r14d
0x18000c213  test    rdx, rdx
0x18000c216  jz      short loc_18000C258
0x18000c218  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c21c  inc     rax
0x18000c21f  cmp     [rdx+rax*2], r14w
0x18000c224  jnz     short loc_18000C21C
0x18000c226  lea     rbp, ds:2[rax*2]
0x18000c22e  mov     rcx, rbp; cb
0x18000c231  call    cs:__imp_CoTaskMemAlloc
0x18000c237  mov     rdi, rax
0x18000c23a  test    rax, rax
0x18000c23d  jnz     short loc_18000C24A
0x18000c23f  mov     ecx, 8007000Eh; this
0x18000c244  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000c24a  mov     r8, rbp; Size
0x18000c24d  mov     rdx, rsi; Src
0x18000c250  mov     rcx, rax; void *
0x18000c253  call    memcpy_0
0x18000c258  mov     rcx, rbx; this
0x18000c25b  call    ?clearValue@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::clearValue(void)
0x18000c260  mov     rax, [rbx]
0x18000c263  mov     [rax+20h], rdi
0x18000c267  mov     rax, [rbx]
0x18000c26a  mov     [rax+18h], r14
0x18000c26e  mov     rax, [rbx]
0x18000c271  mov     dword ptr [rax+10h], 5
0x18000c278  add     rsp, 20h
0x18000c27c  pop     r14
0x18000c27e  pop     rdi
0x18000c27f  pop     rsi
0x18000c280  pop     rbp
0x18000c281  pop     rbx
0x18000c282  retn
```
