# Dfdll::CArrayBase::GrowArray(uint)

- ea: `0x18000d500`
- end: `0x18000d59a`
- name: `?GrowArray@CArrayBase@Dfdll@@QEAAJI@Z`
- size: `154`
- prototype: `__int64 __fastcall(Dfdll::CArrayBase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d8e0`

## callees

- `0x180003a90`
- `0x18000d500`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CArrayBase::GrowArray(Dfdll::CArrayBase *this, int a2)
{
  unsigned int v3; // ecx
  __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned int v7; // edx
  unsigned int v8; // ecx
  Dfdll::CBufferBase *v9; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 2);
  if ( v3 > ~a2 )
    return 2147942934LL;
  v5 = v3 + a2;
  v6 = *(_QWORD *)this;
  v9 = 0;
  result = (*(__int64 (__fastcall **)(Dfdll::CArrayBase *, Dfdll::CBufferBase **))(v6 + 40))(this, &v9);
  if ( (int)result >= 0 )
  {
    v7 = *((_DWORD *)v9 + 4);
    if ( v7 >= v5 )
    {
LABEL_12:
      *((_DWORD *)this + 2) = v5;
      return 0;
    }
    v8 = v5 & 0xFFFFFFFC;
    if ( (v5 & 0xFFFFFFFC) < v5 )
    {
      if ( v8 > 0xFFFFFFFB )
        return 2147942934LL;
      v8 += 4;
      if ( v8 < v5 )
        return 2147942413LL;
    }
    if ( v8 <= ~v7 )
    {
      result = Dfdll::CBufferBase::Reallocate(v9, v8 + v7);
      if ( (int)result < 0 )
        return result;
      if ( *((_DWORD *)v9 + 4) < v5 )
        return 2147942413LL;
      goto LABEL_12;
    }
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000d500  mov     [rsp+arg_8], rbx
0x18000d505  push    rdi
0x18000d506  sub     rsp, 20h
0x18000d50a  mov     eax, edx
0x18000d50c  mov     rdi, rcx
0x18000d50f  mov     ecx, [rcx+8]
0x18000d512  not     eax
0x18000d514  cmp     ecx, eax
0x18000d516  jbe     short loc_18000D51F
0x18000d518  mov     eax, 80070216h
0x18000d51d  jmp     short loc_18000D58F
0x18000d51f  lea     ebx, [rcx+rdx]
0x18000d522  mov     rax, [rdi]
0x18000d525  lea     rdx, [rsp+28h+arg_0]
0x18000d52a  and     [rsp+28h+arg_0], 0
0x18000d530  mov     rcx, rdi
0x18000d533  mov     rax, [rax+28h]
0x18000d537  call    cs:__guard_dispatch_icall_fptr
0x18000d53d  test    eax, eax
0x18000d53f  js      short loc_18000D58F
0x18000d541  mov     r8, [rsp+28h+arg_0]
0x18000d546  mov     edx, [r8+10h]
0x18000d54a  cmp     edx, ebx
0x18000d54c  jnb     short loc_18000D58A
0x18000d54e  mov     ecx, ebx
0x18000d550  and     ecx, 0FFFFFFFCh
0x18000d553  cmp     ecx, ebx
0x18000d555  jnb     short loc_18000D563
0x18000d557  cmp     ecx, 0FFFFFFFBh
0x18000d55a  ja      short loc_18000D518
0x18000d55c  add     ecx, 4
0x18000d55f  cmp     ecx, ebx
0x18000d561  jb      short loc_18000D583
0x18000d563  mov     eax, edx
0x18000d565  not     eax
0x18000d567  cmp     ecx, eax
0x18000d569  ja      short loc_18000D518
0x18000d56b  add     edx, ecx; unsigned int
0x18000d56d  mov     rcx, r8; this
0x18000d570  call    ?Reallocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Reallocate(uint)
0x18000d575  test    eax, eax
0x18000d577  js      short loc_18000D58F
0x18000d579  mov     rax, [rsp+28h+arg_0]
0x18000d57e  cmp     [rax+10h], ebx
0x18000d581  jnb     short loc_18000D58A
0x18000d583  mov     eax, 8007000Dh
0x18000d588  jmp     short loc_18000D58F
0x18000d58a  mov     [rdi+8], ebx
0x18000d58d  xor     eax, eax
0x18000d58f  mov     rbx, [rsp+28h+arg_8]
0x18000d594  add     rsp, 20h
0x18000d598  pop     rdi
0x18000d599  retn
```
