# CPacketRadius::FillClientName(_IASATTRIBUTE *)

- ea: `0x18001312c`
- end: `0x1800131b0`
- name: `?FillClientName@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(CPacketRadius *__hidden this, struct _IASATTRIBUTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012c68`

## callees

- `0x180002106`
- `0x18001312c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013181`

## pseudocode

```c
__int64 __fastcall CPacketRadius::FillClientName(CPacketRadius *this, struct _IASATTRIBUTE *a2)
{
  __int64 v3; // rax
  const void *v4; // rdi
  __int64 v5; // rcx
  SIZE_T v6; // rbx
  void *v7; // rax

  *((_DWORD *)a2 + 2) = 4128;
  *((_QWORD *)a2 + 3) = 0;
  *((_DWORD *)a2 + 4) = 5;
  *((_DWORD *)a2 + 1) = 16;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 56LL))(*((_QWORD *)this + 16));
  v4 = (const void *)v3;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v3 + 2 * v5) );
  v6 = 2 * v5 + 2;
  v7 = CoTaskMemAlloc(v6);
  *((_QWORD *)a2 + 4) = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, v4, v6);
  return 0;
}

```

## disassembly

```asm
0x18001312c  push    rbx
0x18001312e  push    rbp
0x18001312f  push    rsi
0x180013130  push    rdi
0x180013131  sub     rsp, 28h
0x180013135  mov     dword ptr [rdx+8], 1020h
0x18001313c  xor     ebp, ebp
0x18001313e  mov     [rdx+18h], rbp
0x180013142  mov     rsi, rdx
0x180013145  mov     dword ptr [rdx+10h], 5
0x18001314c  mov     dword ptr [rdx+4], 10h
0x180013153  mov     rcx, [rcx+80h]
0x18001315a  mov     rax, [rcx]
0x18001315d  mov     rax, [rax+38h]
0x180013161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013166  mov     rdi, rax
0x180013169  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001316d  inc     rcx
0x180013170  cmp     [rax+rcx*2], bp
0x180013174  jnz     short loc_18001316D
0x180013176  lea     rbx, ds:2[rcx*2]
0x18001317e  mov     rcx, rbx; cb
0x180013181  call    cs:__imp_CoTaskMemAlloc
0x180013187  mov     [rsi+20h], rax
0x18001318b  test    rax, rax
0x18001318e  jnz     short loc_180013197
0x180013190  mov     eax, 8007000Eh
0x180013195  jmp     short loc_1800131A7
0x180013197  mov     r8, rbx; Size
0x18001319a  mov     rdx, rdi; Src
0x18001319d  mov     rcx, rax; void *
0x1800131a0  call    memcpy_0
0x1800131a5  xor     eax, eax
0x1800131a7  add     rsp, 28h
0x1800131ab  pop     rdi
0x1800131ac  pop     rsi
0x1800131ad  pop     rbp
0x1800131ae  pop     rbx
0x1800131af  retn
```
