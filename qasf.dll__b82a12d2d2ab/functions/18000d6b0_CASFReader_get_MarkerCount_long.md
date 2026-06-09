# CASFReader::get_MarkerCount(long *)

- ea: `0x18000d6b0`
- end: `0x18000d75a`
- name: `?get_MarkerCount@CASFReader@@EEAAJPEAJ@Z`
- size: `170`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x18000d6b0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::get_MarkerCount(CASFReader *this, int *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  int v5; // ebx
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 v7; // [rsp+28h] [rbp-20h] BYREF

  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27);
  if ( !v2 )
    return 2147500037LL;
  v6 = 0;
  v5 = (**v2)(v2, &IID_IWMHeaderInfo, &v6);
  if ( v5 >= 0 )
  {
    v7 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v6 + 56LL))(v6, &v7);
    if ( v5 >= 0 )
      *a2 = v7;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d6b0  mov     [rsp+arg_10], rbx
0x18000d6b5  push    rdi
0x18000d6b6  sub     rsp, 40h
0x18000d6ba  mov     rax, cs:__security_cookie
0x18000d6c1  xor     rax, rsp
0x18000d6c4  mov     [rsp+48h+var_18], rax
0x18000d6c9  mov     rcx, [rcx+0D8h]
0x18000d6d0  mov     rdi, rdx
0x18000d6d3  test    rcx, rcx
0x18000d6d6  jnz     short loc_18000D6DF
0x18000d6d8  mov     eax, 80004005h
0x18000d6dd  jmp     short loc_18000D742
0x18000d6df  mov     [rsp+48h+var_28], 0
0x18000d6e8  lea     r8, [rsp+48h+var_28]
0x18000d6ed  mov     rax, [rcx]
0x18000d6f0  lea     rdx, IID_IWMHeaderInfo
0x18000d6f7  mov     rax, [rax]
0x18000d6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ff  mov     ebx, eax
0x18000d701  test    eax, eax
0x18000d703  js      short loc_18000D740
0x18000d705  mov     rcx, [rsp+48h+var_28]
0x18000d70a  lea     rdx, [rsp+48h+var_20]
0x18000d70f  xor     eax, eax
0x18000d711  mov     [rsp+48h+var_20], ax
0x18000d716  mov     rax, [rcx]
0x18000d719  mov     rax, [rax+38h]
0x18000d71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d722  mov     ebx, eax
0x18000d724  test    eax, eax
0x18000d726  js      short loc_18000D72F
0x18000d728  movzx   eax, [rsp+48h+var_20]
0x18000d72d  mov     [rdi], eax
0x18000d72f  mov     rcx, [rsp+48h+var_28]
0x18000d734  mov     rax, [rcx]
0x18000d737  mov     rax, [rax+10h]
0x18000d73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d740  mov     eax, ebx
0x18000d742  mov     rcx, [rsp+48h+var_18]
0x18000d747  xor     rcx, rsp; StackCookie
0x18000d74a  call    __security_check_cookie
0x18000d74f  mov     rbx, [rsp+48h+arg_10]
0x18000d754  add     rsp, 40h
0x18000d758  pop     rdi
0x18000d759  retn
```
