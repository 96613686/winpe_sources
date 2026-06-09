# NativeMsh::PwrshCommon::PwrshCommon(void)

- ea: `0x180007428`
- end: `0x180007483`
- name: `??0PwrshCommon@NativeMsh@@QEAA@XZ`
- size: `91`
- prototype: `NativeMsh::PwrshCommon *__fastcall(NativeMsh::PwrshCommon *this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x180002fac`
- `0x180003158`
- `0x1800050b0`

## callees

- `0x180001098`
- `0x180007428`

## pseudocode

```c
NativeMsh::PwrshCommon *__fastcall NativeMsh::PwrshCommon::PwrshCommon(NativeMsh::PwrshCommon *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax

  *(_QWORD *)this = &NativeMsh::PwrshCommon::`vftable';
  v2 = operator new(8u);
  if ( v2 )
    *v2 = &NativeMsh::PwrshCommonOutputDefault::`vftable';
  *((_QWORD *)this + 1) = v2;
  v3 = operator new(8u);
  if ( v3 )
    *v3 = &NativeMsh::WinSystemCallFacade::`vftable';
  *((_QWORD *)this + 2) = v3;
  return this;
}

```

## disassembly

```asm
0x180007428  push    rbx
0x18000742a  sub     rsp, 20h
0x18000742e  lea     rax, ??_7PwrshCommon@NativeMsh@@6B@; const NativeMsh::PwrshCommon::`vftable'
0x180007435  mov     rbx, rcx
0x180007438  mov     [rcx], rax
0x18000743b  mov     ecx, 8; Size
0x180007440  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007445  test    rax, rax
0x180007448  jz      short loc_180007454
0x18000744a  lea     rcx, ??_7PwrshCommonOutputDefault@NativeMsh@@6B@; const NativeMsh::PwrshCommonOutputDefault::`vftable'
0x180007451  mov     [rax], rcx
0x180007454  mov     ecx, 8; Size
0x180007459  mov     [rbx+8], rax
0x18000745d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007462  mov     [rsp+28h+arg_0], rax
0x180007467  test    rax, rax
0x18000746a  jz      short loc_180007476
0x18000746c  lea     rcx, ??_7WinSystemCallFacade@NativeMsh@@6B@; const NativeMsh::WinSystemCallFacade::`vftable'
0x180007473  mov     [rax], rcx
0x180007476  mov     [rbx+10h], rax
0x18000747a  mov     rax, rbx
0x18000747d  add     rsp, 20h
0x180007481  pop     rbx
0x180007482  retn
```
