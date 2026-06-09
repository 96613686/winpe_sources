# NCoreLibrary::TString::Update(ushort const *)

- ea: `0x180017ab0`
- end: `0x180017b98`
- name: `?Update@TString@NCoreLibrary@@QEAAJPEBG@Z`
- size: `232`
- prototype: `__int64 __fastcall(NCoreLibrary::TString *this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180011514`
- `0x180014870`
- `0x180015cc8`

## callees

- `0x180001334`
- `0x18000134c`
- `0x180009f80`
- `0x180017ab0`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TString::Update(NCoreLibrary::TString *this, unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdi
  int v8; // esi
  __int16 *v9; // rcx
  __int16 *v10; // rcx

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = v4 + 1;
    v6 = (unsigned __int16 *)operator new(saturated_mul(v4 + 1, 2u));
    v7 = v6;
    if ( v6 )
    {
      v8 = StringCchCopyW(v6, v5, a2);
      if ( v8 >= 0 )
      {
        v9 = (__int16 *)*((_QWORD *)this + 1);
        if ( v9 != (__int16 *)&NCoreLibrary::TString::gszNullState && v9 != &word_180021DD6 )
          operator delete(v9);
        *((_QWORD *)this + 1) = v7;
        v7 = 0;
        goto LABEL_8;
      }
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v7 != &NCoreLibrary::TString::gszNullState && v7 != (unsigned __int16 *)&word_180021DD6 )
LABEL_8:
      operator delete(v7);
  }
  else
  {
    v10 = (__int16 *)*((_QWORD *)this + 1);
    v8 = 0;
    if ( v10 != (__int16 *)&NCoreLibrary::TString::gszNullState && v10 != &word_180021DD6 )
      operator delete(v10);
    *((_QWORD *)this + 1) = &NCoreLibrary::TString::gszNullState;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180017ab0  push    rbx
0x180017ab2  push    rbp
0x180017ab3  push    rsi
0x180017ab4  push    rdi
0x180017ab5  push    r14
0x180017ab7  sub     rsp, 20h
0x180017abb  xor     r14d, r14d
0x180017abe  mov     rbx, rdx
0x180017ac1  mov     rbp, rcx
0x180017ac4  test    rdx, rdx
0x180017ac7  jz      loc_180017B63
0x180017acd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017ad1  mov     rax, rcx
0x180017ad4  inc     rax
0x180017ad7  cmp     [rdx+rax*2], r14w
0x180017adc  jnz     short loc_180017AD4
0x180017ade  lea     rsi, [rax+1]
0x180017ae2  mov     eax, 2
0x180017ae7  mul     rsi
0x180017aea  cmovb   rax, rcx
0x180017aee  mov     rcx, rax; Size
0x180017af1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017af6  mov     rdi, rax
0x180017af9  test    rax, rax
0x180017afc  jnz     short loc_180017B25
0x180017afe  mov     esi, 8007000Eh
0x180017b03  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180017b0a  cmp     rdi, rbx
0x180017b0d  jz      short loc_180017B8B
0x180017b0f  lea     rdx, word_180021DD6
0x180017b16  cmp     rdi, rdx
0x180017b19  jz      short loc_180017B8B
0x180017b1b  mov     rcx, rdi; Block
0x180017b1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017b23  jmp     short loc_180017B8B
0x180017b25  mov     r8, rbx; unsigned __int16 *
0x180017b28  mov     rdx, rsi; unsigned __int64
0x180017b2b  mov     rcx, rdi; unsigned __int16 *
0x180017b2e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017b33  mov     esi, eax
0x180017b35  test    eax, eax
0x180017b37  js      short loc_180017B03
0x180017b39  mov     rcx, [rbp+8]; Block
0x180017b3d  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180017b44  cmp     rcx, rbx
0x180017b47  jz      short loc_180017B5A
0x180017b49  lea     rdx, word_180021DD6
0x180017b50  cmp     rcx, rdx
0x180017b53  jz      short loc_180017B5A
0x180017b55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017b5a  mov     [rbp+8], rdi
0x180017b5e  mov     rdi, r14
0x180017b61  jmp     short loc_180017B1B
0x180017b63  mov     rcx, [rcx+8]; Block
0x180017b67  lea     rbx, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180017b6e  mov     esi, r14d
0x180017b71  cmp     rcx, rbx
0x180017b74  jz      short loc_180017B87
0x180017b76  lea     rdx, word_180021DD6
0x180017b7d  cmp     rcx, rdx
0x180017b80  jz      short loc_180017B87
0x180017b82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017b87  mov     [rbp+8], rbx
0x180017b8b  mov     eax, esi
0x180017b8d  add     rsp, 20h
0x180017b91  pop     r14
0x180017b93  pop     rdi
0x180017b94  pop     rsi
0x180017b95  pop     rbp
0x180017b96  pop     rbx
0x180017b97  retn
```
