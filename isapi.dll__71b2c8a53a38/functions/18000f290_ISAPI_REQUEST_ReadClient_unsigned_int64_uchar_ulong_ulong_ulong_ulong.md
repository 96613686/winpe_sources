# ISAPI_REQUEST::ReadClient(unsigned __int64,uchar *,ulong,ulong,ulong *,ulong)

- ea: `0x18000f290`
- end: `0x18000f3b3`
- name: `?ReadClient@ISAPI_REQUEST@@UEAAJ_KPEAEKKPEAKK@Z`
- size: `291`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *this, __int64, unsigned __int8 *, __int64, unsigned int, unsigned int *, __int16)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f290`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::ReadClient(
        ISAPI_REQUEST *this,
        __int64 a2,
        unsigned __int8 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        __int16 a7)
{
  bool v7; // zf
  int v8; // esi
  BOOL v9; // ebx
  __int64 v12; // rax
  unsigned int *v13; // r14
  unsigned int *v14; // rdx
  int v15; // ebx
  __int64 v16; // rax
  int v18; // [rsp+80h] [rbp+8h] BYREF

  v7 = (a7 & 2) == 0;
  v8 = a7 & 2;
  v18 = 0;
  a7 = 0;
  v9 = !v7;
  if ( a2 )
    *((_QWORD *)this + 2) = a2;
  if ( v8 )
    *((_DWORD *)this + 10) = 1;
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
  v13 = a6;
  v14 = (unsigned int *)&v18;
  if ( !v8 )
    v14 = a6;
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD, BOOL, unsigned int *, _QWORD))(*(_QWORD *)v12 + 128LL))(
          v12,
          a3,
          a5,
          v9,
          v14,
          0);
  if ( v15 == -2147024858 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
    if ( (*(__int64 (__fastcall **)(__int64, __int64, __int16 *))(*(_QWORD *)v16 + 16LL))(v16, 6, &a7) && a7 )
    {
      v15 = 0;
      if ( v8 )
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 72LL))(*((_QWORD *)this + 3), 0);
      else
        *v13 = 0;
      return (unsigned int)v15;
    }
  }
  else if ( v15 >= 0 )
  {
    return (unsigned int)v15;
  }
  *((_DWORD *)this + 11) = v15;
  if ( v8 )
    *((_DWORD *)this + 10) = 0;
  return 2147952454LL;
}

```

## disassembly

```asm
0x18000f290  mov     rax, rsp
0x18000f293  push    rbx
0x18000f294  push    rbp
0x18000f295  push    rsi
0x18000f296  push    rdi
0x18000f297  push    r14
0x18000f299  push    r15
0x18000f29b  sub     rsp, 48h
0x18000f29f  mov     esi, [rsp+78h+arg_30]
0x18000f2a6  xor     r15d, r15d
0x18000f2a9  and     esi, 2
0x18000f2ac  mov     [rax+8], r15d
0x18000f2b0  mov     ebx, r15d
0x18000f2b3  mov     [rax+38h], r15w
0x18000f2b8  setnz   bl
0x18000f2bb  mov     rbp, r8
0x18000f2be  mov     rdi, rcx
0x18000f2c1  test    rdx, rdx
0x18000f2c4  jz      short loc_18000F2CA
0x18000f2c6  mov     [rcx+10h], rdx
0x18000f2ca  test    esi, esi
0x18000f2cc  jz      short loc_18000F2D5
0x18000f2ce  mov     dword ptr [rcx+28h], 1
0x18000f2d5  mov     rcx, [rcx+18h]
0x18000f2d9  mov     rax, [rcx]
0x18000f2dc  mov     rax, [rax+18h]
0x18000f2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2e5  mov     r14, [rsp+78h+arg_28]
0x18000f2ed  lea     rdx, [rsp+78h+arg_0]
0x18000f2f5  mov     r8d, [rsp+78h+arg_20]
0x18000f2fd  mov     r10, rax
0x18000f300  test    esi, esi
0x18000f302  mov     [rsp+78h+var_50], r15
0x18000f307  mov     rcx, [rax]
0x18000f30a  mov     r9d, ebx
0x18000f30d  cmovz   rdx, r14
0x18000f311  mov     [rsp+78h+var_58], rdx
0x18000f316  mov     rdx, rbp
0x18000f319  mov     rax, [rcx+80h]
0x18000f320  mov     rcx, r10
0x18000f323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f328  mov     ebx, eax
0x18000f32a  cmp     eax, 80070026h
0x18000f32f  jnz     short loc_18000F39D
0x18000f331  mov     rcx, [rdi+18h]
0x18000f335  mov     rdx, [rcx]
0x18000f338  mov     rax, [rdx+18h]
0x18000f33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f341  mov     r9, rax
0x18000f344  lea     r8, [rsp+78h+arg_30]
0x18000f34c  mov     edx, 6
0x18000f351  mov     rcx, [rax]
0x18000f354  mov     rax, [rcx+10h]
0x18000f358  mov     rcx, r9
0x18000f35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f360  test    rax, rax
0x18000f363  jz      short loc_18000F3A1
0x18000f365  cmp     word ptr [rsp+78h+arg_30], r15w
0x18000f36e  jz      short loc_18000F3A1
0x18000f370  mov     ebx, r15d
0x18000f373  test    esi, esi
0x18000f375  jz      short loc_18000F398
0x18000f377  mov     rcx, [rdi+18h]
0x18000f37b  xor     edx, edx
0x18000f37d  mov     rax, [rcx]
0x18000f380  mov     rax, [rax+48h]
0x18000f384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f389  mov     eax, ebx
0x18000f38b  add     rsp, 48h
0x18000f38f  pop     r15
0x18000f391  pop     r14
0x18000f393  pop     rdi
0x18000f394  pop     rsi
0x18000f395  pop     rbp
0x18000f396  pop     rbx
0x18000f397  retn
0x18000f398  mov     [r14], r15d
0x18000f39b  jmp     short loc_18000F389
0x18000f39d  test    ebx, ebx
0x18000f39f  jns     short loc_18000F389
0x18000f3a1  mov     [rdi+2Ch], ebx
0x18000f3a4  test    esi, esi
0x18000f3a6  jz      short loc_18000F3AC
0x18000f3a8  mov     [rdi+28h], r15d
0x18000f3ac  mov     eax, 80072746h
0x18000f3b1  jmp     short loc_18000F38B
```
