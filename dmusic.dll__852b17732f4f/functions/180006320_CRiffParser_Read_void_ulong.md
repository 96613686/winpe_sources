# CRiffParser::Read(void *,ulong)

- ea: `0x180006320`
- end: `0x1800063a2`
- name: `?Read@CRiffParser@@QEAAJPEAXK@Z`
- size: `130`
- prototype: `__int64 __fastcall(CRiffParser *__hidden this, void *, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180009b30`
- `0x18000b730`
- `0x18000b918`
- `0x18000baf0`
- `0x18000c5f8`
- `0x18000c8b0`
- `0x18000cd90`
- `0x18000db7c`
- `0x18000dbf0`
- `0x18000e178`
- `0x180010938`
- `0x180014834`

## callees

- `0x180006320`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CRiffParser::Read(CRiffParser *this, void *a2, unsigned int a3)
{
  __int64 v3; // rax
  unsigned int v4; // ebx
  int v6; // r9d
  unsigned int v7; // r8d
  __int64 result; // rax
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // edx

  v3 = *((_QWORD *)this + 2);
  v4 = a3;
  if ( !v3 )
    return 2147500037LL;
  v6 = *(_DWORD *)(v3 + 12);
  v7 = v6 + a3;
  if ( v7 < v4 )
    return 2147942934LL;
  if ( v7 > *(_DWORD *)(v3 + 4) )
    v4 = *(_DWORD *)(v3 + 4) - v6;
  result = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
             *((_QWORD *)this + 1),
             a2,
             v4,
             0);
  if ( (int)result >= 0 )
  {
    v9 = *((_QWORD *)this + 2);
    v10 = -1;
    v11 = *(_DWORD *)(v9 + 12);
    if ( v11 + v4 >= v11 )
      v10 = v11 + v4;
    *(_DWORD *)(v9 + 12) = v10;
    return v11 + v4 < v11 ? 0x80070216 : 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006320  mov     [rsp+arg_0], rbx
0x180006325  push    rdi
0x180006326  sub     rsp, 30h
0x18000632a  mov     rax, [rcx+10h]
0x18000632e  mov     ebx, r8d
0x180006331  mov     rdi, rcx
0x180006334  test    rax, rax
0x180006337  jz      short loc_180006392
0x180006339  mov     r9d, [rax+0Ch]
0x18000633d  add     r8d, r9d
0x180006340  cmp     r8d, ebx
0x180006343  jb      short loc_18000638B
0x180006345  cmp     r8d, [rax+4]
0x180006349  jbe     short loc_180006351
0x18000634b  mov     ebx, [rax+4]
0x18000634e  sub     ebx, r9d
0x180006351  mov     rcx, [rcx+8]
0x180006355  xor     r9d, r9d
0x180006358  mov     r8d, ebx
0x18000635b  mov     rax, [rcx]
0x18000635e  mov     rax, [rax+18h]
0x180006362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006367  test    eax, eax
0x180006369  js      short loc_180006397
0x18000636b  mov     r8, [rdi+10h]
0x18000636f  or      eax, 0FFFFFFFFh
0x180006372  mov     edx, [r8+0Ch]
0x180006376  lea     ecx, [rdx+rbx]
0x180006379  cmp     ecx, edx
0x18000637b  cmovnb  eax, ecx
0x18000637e  mov     [r8+0Ch], eax
0x180006382  sbb     eax, eax
0x180006384  and     eax, 80070216h
0x180006389  jmp     short loc_180006397
0x18000638b  mov     eax, 80070216h
0x180006390  jmp     short loc_180006397
0x180006392  mov     eax, 80004005h
0x180006397  mov     rbx, [rsp+38h+arg_0]
0x18000639c  add     rsp, 30h
0x1800063a0  pop     rdi
0x1800063a1  retn
```
