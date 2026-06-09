# Dfdll::CBufferBase::RawCopyFrom(void const *,uint,uint)

- ea: `0x1800039e8`
- end: `0x180003a8e`
- name: `?RawCopyFrom@CBufferBase@Dfdll@@IEAAJPEBXII@Z`
- size: `166`
- prototype: `int(Dfdll::CBufferBase *__hidden this, const void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800028b0`

## callees

- `0x1800039e8`
- `0x1800140a0`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBufferBase::RawCopyFrom(
        Dfdll::CBufferBase *this,
        const void *a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 result; // rax
  unsigned int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // ecx
  void *v11; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 0;
  v8 = *((_DWORD *)this + 4);
  if ( a3 >= v8 || v8 - a3 < a4 )
    return 2147942487LL;
  v9 = *(_QWORD *)this;
  v11 = 0;
  result = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *, _QWORD, void **))(v9 + 64))(this, a3, &v11);
  if ( (int)result >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(Dfdll::CBufferBase *))(*(_QWORD *)this + 72LL))(this);
    if ( v10 )
    {
      if ( a4 > 0xFFFFFFFF / v10 )
        return 2147942934LL;
      v10 *= a4;
    }
    memmove(v11, a2, v10);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800039e8  mov     [rsp+arg_0], rbx
0x1800039ed  mov     [rsp+arg_10], rsi
0x1800039f2  push    rdi
0x1800039f3  sub     rsp, 20h
0x1800039f7  mov     ebx, r9d
0x1800039fa  mov     r9d, r8d
0x1800039fd  mov     rsi, rdx
0x180003a00  mov     rdi, rcx
0x180003a03  test    rdx, rdx
0x180003a06  jnz     short loc_180003A0F
0x180003a08  mov     eax, 80070057h
0x180003a0d  jmp     short loc_180003A7E
0x180003a0f  test    ebx, ebx
0x180003a11  jz      short loc_180003A7C
0x180003a13  mov     eax, [rcx+10h]
0x180003a16  cmp     r9d, eax
0x180003a19  jnb     short loc_180003A08
0x180003a1b  sub     eax, r9d
0x180003a1e  cmp     eax, ebx
0x180003a20  jb      short loc_180003A08
0x180003a22  mov     rax, [rcx]
0x180003a25  lea     r8, [rsp+28h+arg_8]
0x180003a2a  and     [rsp+28h+arg_8], 0
0x180003a30  mov     edx, r9d
0x180003a33  mov     rax, [rax+40h]
0x180003a37  call    cs:__guard_dispatch_icall_fptr
0x180003a3d  test    eax, eax
0x180003a3f  js      short loc_180003A7E
0x180003a41  mov     rax, [rdi]
0x180003a44  mov     rcx, rdi
0x180003a47  mov     rax, [rax+48h]
0x180003a4b  call    cs:__guard_dispatch_icall_fptr
0x180003a51  mov     ecx, eax
0x180003a53  test    eax, eax
0x180003a55  jz      short loc_180003A6C
0x180003a57  xor     edx, edx
0x180003a59  or      eax, 0FFFFFFFFh
0x180003a5c  div     ecx
0x180003a5e  cmp     ebx, eax
0x180003a60  jbe     short loc_180003A69
0x180003a62  mov     eax, 80070216h
0x180003a67  jmp     short loc_180003A7E
0x180003a69  imul    ecx, ebx
0x180003a6c  mov     r8d, ecx; Size
0x180003a6f  mov     rdx, rsi; Src
0x180003a72  mov     rcx, [rsp+28h+arg_8]; void *
0x180003a77  call    memmove
0x180003a7c  xor     eax, eax
0x180003a7e  mov     rbx, [rsp+28h+arg_0]
0x180003a83  mov     rsi, [rsp+28h+arg_10]
0x180003a88  add     rsp, 20h
0x180003a8c  pop     rdi
0x180003a8d  retn
```
