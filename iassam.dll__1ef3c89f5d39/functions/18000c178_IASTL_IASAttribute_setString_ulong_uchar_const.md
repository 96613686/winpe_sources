# IASTL::IASAttribute::setString(ulong,uchar const *)

- ea: `0x18000c178`
- end: `0x18000c1f5`
- name: `?setString@IASAttribute@IASTL@@QEAAXKPEBE@Z`
- size: `125`
- prototype: `void __fastcall(IASTL::IASAttribute *__hidden this, size_t Size, const unsigned __int8 *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014d20`
- `0x18001c160`

## callees

- `0x180001f26`
- `0x18000b680`
- `0x18000b81c`
- `0x18000c178`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c19d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c19d`

## pseudocode

```c
void __fastcall IASTL::IASAttribute::setString(IASTL::IASAttribute *this, size_t Size, const unsigned __int8 *Src)
{
  size_t v3; // rbx
  _BYTE *v6; // rax
  int v7; // edx
  _BYTE *v8; // rdi

  v3 = (unsigned int)Size;
  if ( (int)Size + 1 < (unsigned int)Size )
    IASTL::issue_error((IASTL *)0x216, Size);
  v6 = CoTaskMemAlloc((unsigned int)(Size + 1));
  v8 = v6;
  if ( !v6 )
    IASTL::issue_error((IASTL *)0x8007000ELL, v7);
  memcpy_0(v6, Src, v3);
  v8[v3] = 0;
  IASTL::IASAttribute::clearValue(this);
  *(_QWORD *)(*(_QWORD *)this + 24LL) = v8;
  *(_QWORD *)(*(_QWORD *)this + 32LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 16LL) = 5;
}

```

## disassembly

```asm
0x18000c178  push    rbx
0x18000c17a  push    rbp
0x18000c17b  push    rsi
0x18000c17c  push    rdi
0x18000c17d  sub     rsp, 28h
0x18000c181  mov     ebx, edx
0x18000c183  mov     rbp, r8
0x18000c186  mov     rsi, rcx
0x18000c189  lea     eax, [rbx+1]
0x18000c18c  cmp     eax, edx
0x18000c18e  jnb     short loc_18000C19B
0x18000c190  mov     ecx, 216h; this
0x18000c195  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000c19b  mov     ecx, eax; cb
0x18000c19d  call    cs:__imp_CoTaskMemAlloc
0x18000c1a3  mov     rdi, rax
0x18000c1a6  test    rax, rax
0x18000c1a9  jnz     short loc_18000C1B6
0x18000c1ab  mov     ecx, 8007000Eh; this
0x18000c1b0  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000c1b6  mov     r8, rbx; Size
0x18000c1b9  mov     rdx, rbp; Src
0x18000c1bc  mov     rcx, rdi; void *
0x18000c1bf  call    memcpy_0
0x18000c1c4  mov     rcx, rsi; this
0x18000c1c7  mov     byte ptr [rbx+rdi], 0
0x18000c1cb  call    ?clearValue@IASAttribute@IASTL@@IEAAXXZ; IASTL::IASAttribute::clearValue(void)
0x18000c1d0  mov     rax, [rsi]
0x18000c1d3  mov     [rax+18h], rdi
0x18000c1d7  mov     rax, [rsi]
0x18000c1da  mov     qword ptr [rax+20h], 0
0x18000c1e2  mov     rax, [rsi]
0x18000c1e5  mov     dword ptr [rax+10h], 5
0x18000c1ec  add     rsp, 28h
0x18000c1f0  pop     rdi
0x18000c1f1  pop     rsi
0x18000c1f2  pop     rbp
0x18000c1f3  pop     rbx
0x18000c1f4  retn
```
