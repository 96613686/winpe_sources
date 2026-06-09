# std::_Copy_memmove<winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *>(winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *)

- ea: `0x180002844`
- end: `0x180002874`
- name: `??$_Copy_memmove@PEAURectInt32@Graphics@Windows@winrt@@PEAU1234@@std@@YAPEAURectInt32@Graphics@Windows@winrt@@PEAU1234@00@Z`
- size: `48`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180004420`
- `0x1800044b0`
- `0x180004540`
- `0x1800045d0`
- `0x1800046e0`
- `0x1800109c0`
- `0x180010a60`
- `0x180014ab0`
- `0x18001ba60`
- `0x18001e77c`
- `0x1800224fc`

## callees

- `0x1800022da`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove<winrt::Windows::Graphics::RectInt32 *,winrt::Windows::Graphics::RectInt32 *>(
        void *Src,
        __int64 a2,
        void *a3)
{
  __int64 v4; // rbx

  v4 = a2 - (_QWORD)Src;
  memmove_0(a3, Src, a2 - (_QWORD)Src);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180002844  mov     [rsp+arg_0], rbx
0x180002849  push    rdi
0x18000284a  sub     rsp, 20h
0x18000284e  mov     rbx, rdx
0x180002851  mov     rdi, r8
0x180002854  sub     rbx, rcx
0x180002857  mov     rdx, rcx; Src
0x18000285a  mov     r8, rbx; Size
0x18000285d  mov     rcx, rdi; void *
0x180002860  call    memmove_0
0x180002865  lea     rax, [rbx+rdi]
0x180002869  mov     rbx, [rsp+28h+arg_0]
0x18000286e  add     rsp, 20h
0x180002872  pop     rdi
0x180002873  retn
```
