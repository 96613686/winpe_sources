# Dfdll::CLock::~CLock(void)

- ea: `0x180008c2c`
- end: `0x180008c6b`
- name: `??1CLock@Dfdll@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(Dfdll::CLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f242`

## callees

- `0x180008c2c`
- `0x18001efd0`

## pseudocode

```c
void __fastcall Dfdll::CLock::~CLock(Dfdll::CLock *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &Dfdll::CLock::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
  }
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180008c2c  push    rbx
0x180008c2e  sub     rsp, 20h
0x180008c32  mov     rbx, rcx
0x180008c35  lea     rax, ??_7CLock@Dfdll@@6B@; const Dfdll::CLock::`vftable'
0x180008c3c  mov     [rcx], rax
0x180008c3f  cmp     byte ptr [rcx+10h], 0
0x180008c43  jz      short loc_180008C5B
0x180008c45  mov     rcx, [rcx+8]
0x180008c49  test    rcx, rcx
0x180008c4c  jz      short loc_180008C5B
0x180008c4e  mov     rax, [rcx]
0x180008c51  mov     rax, [rax+30h]
0x180008c55  call    cs:__guard_dispatch_icall_fptr
0x180008c5b  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180008c62  mov     [rbx], rax
0x180008c65  add     rsp, 20h
0x180008c69  pop     rbx
0x180008c6a  retn
```
