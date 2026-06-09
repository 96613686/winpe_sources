# Dfdll::CSynchronizationObject::~CSynchronizationObject(void)

- ea: `0x180008fd0`
- end: `0x180009021`
- name: `??1CSynchronizationObject@Dfdll@@UEAA@XZ`
- size: `81`
- prototype: `void __fastcall(Dfdll::CSynchronizationObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f212`

## callees

- `0x180008fd0`
- `0x18001efd0`

## pseudocode

```c
void __fastcall Dfdll::CSynchronizationObject::~CSynchronizationObject(Dfdll::CSynchronizationObject *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &Dfdll::CSynchronizationObject::`vftable';
  *((_QWORD *)this + 1) = &Dfdll::CPointerHolder<Dfdll::CString>::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v2 )
    (**v2)(v2, 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = &Dfdll::CObject::`vftable';
  *(_QWORD *)this = &Dfdll::CObject::`vftable';
}

```

## disassembly

```asm
0x180008fd0  push    rbx
0x180008fd2  sub     rsp, 20h
0x180008fd6  lea     rax, ??_7CSynchronizationObject@Dfdll@@6B@; const Dfdll::CSynchronizationObject::`vftable'
0x180008fdd  mov     rbx, rcx
0x180008fe0  mov     [rcx], rax
0x180008fe3  lea     rax, ??_7?$CPointerHolder@VCString@Dfdll@@@Dfdll@@6B@; const Dfdll::CPointerHolder<Dfdll::CString>::`vftable'
0x180008fea  mov     [rcx+8], rax
0x180008fee  mov     rcx, [rcx+10h]
0x180008ff2  test    rcx, rcx
0x180008ff5  jz      short loc_180009008
0x180008ff7  mov     rax, [rcx]
0x180008ffa  mov     edx, 1
0x180008fff  mov     rax, [rax]
0x180009002  call    cs:__guard_dispatch_icall_fptr
0x180009008  and     qword ptr [rbx+10h], 0
0x18000900d  lea     rax, ??_7CObject@Dfdll@@6B@; const Dfdll::CObject::`vftable'
0x180009014  mov     [rbx+8], rax
0x180009018  mov     [rbx], rax
0x18000901b  add     rsp, 20h
0x18000901f  pop     rbx
0x180009020  retn
```
