# CSchedule::Init(void)

- ea: `0x180006ec0`
- end: `0x180006f88`
- name: `?Init@CSchedule@@QEAAJXZ`
- size: `200`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006dd0`
- `0x180009490`
- `0x18000bb50`

## callees

- `0x180006ec0`
- `0x180009ef8`

## pseudocode

```c
__int64 __fastcall CSchedule::Init(CSchedule *this)
{
  __int64 v2; // rbx
  unsigned __int64 v3; // rbx
  _WORD *v4; // rax
  _WORD *v5; // r8
  unsigned __int16 *v6; // rdx
  __int64 v7; // rax

  if ( !g_TasksFolderInfo )
    return 2147500037LL;
  v2 = -1;
  do
    ++v2;
  while ( g_TasksFolderInfo[v2] );
  v3 = v2 + 1;
  v4 = operator new(saturated_mul(v3, 2u));
  *((_QWORD *)this + 8) = v4;
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  if ( v3 )
  {
    if ( v3 <= 0x7FFFFFFF )
    {
      v6 = g_TasksFolderInfo;
      v7 = 2147483646;
      do
      {
        if ( !v7 )
          break;
        if ( !*v6 )
          break;
        *v5++ = *v6++;
        --v7;
        --v3;
      }
      while ( v3 );
      v4 = v5 - 1;
      if ( v3 )
        v4 = v5;
    }
    *v4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180006ec0  push    rdi
0x180006ec2  sub     rsp, 20h
0x180006ec6  mov     rax, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180006ecd  mov     rdi, rcx
0x180006ed0  test    rax, rax
0x180006ed3  jz      loc_180006F76
0x180006ed9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006ee0  mov     [rsp+28h+arg_0], rbx
0x180006ee5  mov     rbx, rcx
0x180006ee8  nop     dword ptr [rax+rax+00000000h]
0x180006ef0  inc     rbx
0x180006ef3  cmp     word ptr [rax+rbx*2], 0
0x180006ef8  jnz     short loc_180006EF0
0x180006efa  inc     rbx
0x180006efd  mov     eax, 2
0x180006f02  mul     rbx
0x180006f05  cmovb   rax, rcx
0x180006f09  mov     rcx, rax; Size
0x180006f0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006f11  mov     [rdi+40h], rax
0x180006f15  mov     r8, rax
0x180006f18  test    rax, rax
0x180006f1b  jz      short loc_180006F81
0x180006f1d  test    rbx, rbx
0x180006f20  jz      short loc_180006F69
0x180006f22  cmp     rbx, 7FFFFFFFh
0x180006f29  ja      short loc_180006F64
0x180006f2b  mov     rdx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180006f32  mov     eax, 7FFFFFFEh
0x180006f37  test    rax, rax
0x180006f3a  jz      short loc_180006F59
0x180006f3c  movzx   ecx, word ptr [rdx]
0x180006f3f  test    cx, cx
0x180006f42  jz      short loc_180006F59
0x180006f44  mov     [r8], cx
0x180006f48  add     rdx, 2
0x180006f4c  add     r8, 2
0x180006f50  dec     rax
0x180006f53  sub     rbx, 1
0x180006f57  jnz     short loc_180006F37
0x180006f59  test    rbx, rbx
0x180006f5c  lea     rax, [r8-2]
0x180006f60  cmovnz  rax, r8
0x180006f64  xor     ecx, ecx
0x180006f66  mov     [rax], cx
0x180006f69  xor     eax, eax
0x180006f6b  mov     rbx, [rsp+28h+arg_0]
0x180006f70  add     rsp, 20h
0x180006f74  pop     rdi
0x180006f75  retn
0x180006f76  mov     eax, 80004005h
0x180006f7b  add     rsp, 20h
0x180006f7f  pop     rdi
0x180006f80  retn
0x180006f81  mov     eax, 8007000Eh
0x180006f86  jmp     short loc_180006F6B
```
