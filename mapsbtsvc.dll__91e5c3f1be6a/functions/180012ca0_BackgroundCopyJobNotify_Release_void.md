# BackgroundCopyJobNotify::Release(void)

- ea: `0x180012ca0`
- end: `0x180012cec`
- name: `?Release@BackgroundCopyJobNotify@@UEAAKXZ`
- size: `76`
- prototype: `__int64 __fastcall(BackgroundCopyJobNotify *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000aff4`
- `0x18000cfec`

## callees

- `0x180001e54`
- `0x180005b9c`
- `0x180012ca0`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::Release(BackgroundCopyJobNotify *this)
{
  unsigned __int32 v2; // edi
  std::_Ref_count_base *v3; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &BackgroundCopyJobNotify::`vftable';
    v3 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
    if ( v3 )
      std::_Ref_count_base::_Decwref(v3);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180012ca0  mov     [rsp+arg_0], rbx
0x180012ca5  push    rdi
0x180012ca6  sub     rsp, 20h
0x180012caa  mov     rbx, rcx
0x180012cad  or      edi, 0FFFFFFFFh
0x180012cb0  lock xadd [rcx+18h], edi
0x180012cb5  sub     edi, 1
0x180012cb8  jnz     short loc_180012CDF
0x180012cba  test    rcx, rcx
0x180012cbd  jz      short loc_180012CDF
0x180012cbf  lea     rax, ??_7BackgroundCopyJobNotify@@6B@; const BackgroundCopyJobNotify::`vftable'
0x180012cc6  mov     [rcx], rax
0x180012cc9  mov     rcx, [rcx+10h]; this
0x180012ccd  test    rcx, rcx
0x180012cd0  jz      short loc_180012CD7
0x180012cd2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180012cd7  mov     rcx, rbx; Block
0x180012cda  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012cdf  mov     rbx, [rsp+28h+arg_0]
0x180012ce4  mov     eax, edi
0x180012ce6  add     rsp, 20h
0x180012cea  pop     rdi
0x180012ceb  retn
```
