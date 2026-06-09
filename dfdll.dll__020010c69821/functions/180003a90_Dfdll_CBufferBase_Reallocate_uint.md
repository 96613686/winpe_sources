# Dfdll::CBufferBase::Reallocate(uint)

- ea: `0x180003a90`
- end: `0x180003b57`
- name: `?Reallocate@CBufferBase@Dfdll@@QEAAJI@Z`
- size: `199`
- prototype: `__int64 __fastcall(Dfdll::CBufferBase *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001f38`
- `0x180002238`
- `0x180003e88`
- `0x18000d500`

## callees

- `0x180003a90`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::Reallocate(Dfdll::CBufferBase *this, unsigned int a2)
{
  unsigned int *v2; // rsi
  __int64 v6; // rax
  unsigned int v7; // r9d
  __int64 v8; // rdx
  int v9; // ebp
  void (__fastcall *v10)(Dfdll::CBufferBase *, __int64 *, unsigned int *); // rax
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF

  v2 = (unsigned int *)((char *)this + 16);
  if ( a2 > *((_DWORD *)this + 4) )
  {
    v6 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *))(*(_QWORD *)this + 80LL))(this);
    if ( v6 )
    {
      v7 = *v2;
      v8 = *((_QWORD *)this + 1);
      *v2 = a2;
      v9 = 0;
      v12 = v8;
      v13 = v7;
      *((_QWORD *)this + 1) = v6;
      if ( v8 )
        v9 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, __int64, _QWORD))(*(_QWORD *)this + 96LL))(this, v8, 0);
      v10 = *(void (__fastcall **)(Dfdll::CBufferBase *, __int64 *, unsigned int *))(*(_QWORD *)this + 88LL);
      if ( v9 >= 0 )
      {
        v10(this, &v12, &v13);
      }
      else
      {
        v10(this, (__int64 *)this + 1, v2);
        *((_QWORD *)this + 1) = v12;
        *v2 = v13;
      }
      return (unsigned int)v9;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180003a90  mov     [rsp+arg_10], rbx
0x180003a95  mov     [rsp+arg_18], rbp
0x180003a9a  push    rsi
0x180003a9b  push    rdi
0x180003a9c  push    r14
0x180003a9e  sub     rsp, 30h
0x180003aa2  lea     rsi, [rcx+10h]
0x180003aa6  mov     ebp, edx
0x180003aa8  mov     rdi, rcx
0x180003aab  cmp     edx, [rsi]
0x180003aad  ja      short loc_180003AB6
0x180003aaf  xor     ebx, ebx
0x180003ab1  jmp     loc_180003B42
0x180003ab6  mov     rax, [rcx]
0x180003ab9  mov     rax, [rax+50h]
0x180003abd  call    cs:__guard_dispatch_icall_fptr
0x180003ac3  xor     ebx, ebx
0x180003ac5  test    rax, rax
0x180003ac8  jnz     short loc_180003AD1
0x180003aca  mov     ebx, 8007000Eh
0x180003acf  jmp     short loc_180003B42
0x180003ad1  mov     r9d, [rsi]
0x180003ad4  lea     r14, [rdi+8]
0x180003ad8  mov     rdx, [r14]
0x180003adb  mov     [rsi], ebp
0x180003add  mov     ebp, ebx
0x180003adf  mov     [rsp+48h+arg_0], rdx
0x180003ae4  mov     [rsp+48h+arg_8], r9d
0x180003ae9  mov     [r14], rax
0x180003aec  test    rdx, rdx
0x180003aef  jz      short loc_180003B06
0x180003af1  mov     rax, [rdi]
0x180003af4  xor     r8d, r8d
0x180003af7  mov     rcx, rdi
0x180003afa  mov     rax, [rax+60h]
0x180003afe  call    cs:__guard_dispatch_icall_fptr
0x180003b04  mov     ebp, eax
0x180003b06  mov     rax, [rdi]
0x180003b09  mov     rcx, rdi
0x180003b0c  mov     rax, [rax+58h]
0x180003b10  test    ebp, ebp
0x180003b12  jns     short loc_180003B30
0x180003b14  mov     r8, rsi
0x180003b17  mov     rdx, r14
0x180003b1a  call    cs:__guard_dispatch_icall_fptr
0x180003b20  mov     rax, [rsp+48h+arg_0]
0x180003b25  mov     [r14], rax
0x180003b28  mov     eax, [rsp+48h+arg_8]
0x180003b2c  mov     [rsi], eax
0x180003b2e  jmp     short loc_180003B40
0x180003b30  lea     r8, [rsp+48h+arg_8]
0x180003b35  lea     rdx, [rsp+48h+arg_0]
0x180003b3a  call    cs:__guard_dispatch_icall_fptr
0x180003b40  mov     ebx, ebp
0x180003b42  mov     rbp, [rsp+48h+arg_18]
0x180003b47  mov     eax, ebx
0x180003b49  mov     rbx, [rsp+48h+arg_10]
0x180003b4e  add     rsp, 30h
0x180003b52  pop     r14
0x180003b54  pop     rdi
0x180003b55  pop     rsi
0x180003b56  retn
```
