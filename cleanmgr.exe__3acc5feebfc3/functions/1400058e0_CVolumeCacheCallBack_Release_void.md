# CVolumeCacheCallBack::Release(void)

- ea: `0x1400058e0`
- end: `0x140005912`
- name: `?Release@CVolumeCacheCallBack@@UEAAKXZ`
- size: `50`
- prototype: `__int64 __fastcall(CVolumeCacheCallBack *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1400029c4`
- `0x1400058e0`

## pseudocode

```c
__int64 __fastcall CVolumeCacheCallBack::Release(CVolumeCacheCallBack *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &CVolumeCacheCallBack::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x1400058e0  push    rbx
0x1400058e2  sub     rsp, 20h
0x1400058e6  or      ebx, 0FFFFFFFFh
0x1400058e9  lock xadd [rcx+8], ebx
0x1400058ee  sub     ebx, 1
0x1400058f1  jnz     short loc_14000590A
0x1400058f3  test    rcx, rcx
0x1400058f6  jz      short loc_14000590A
0x1400058f8  lea     rax, ??_7CVolumeCacheCallBack@@6B@; const CVolumeCacheCallBack::`vftable'
0x1400058ff  lea     edx, [rbx+10h]; unsigned __int64
0x140005902  mov     [rcx], rax
0x140005905  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000590a  mov     eax, ebx
0x14000590c  add     rsp, 20h
0x140005910  pop     rbx
0x140005911  retn
```
