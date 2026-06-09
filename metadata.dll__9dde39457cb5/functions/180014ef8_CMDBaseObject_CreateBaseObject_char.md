# CMDBaseObject::CreateBaseObject(char *)

- ea: `0x180014ef8`
- end: `0x180014f5a`
- name: `?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAD@Z`
- size: `98`
- prototype: `struct CMDBaseObject *__fastcall(char *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001aeb4`
- `0x18001fa58`
- `0x1800209e8`
- `0x180020be8`
- `0x180022c20`

## callees

- `0x1800089c8`
- `0x180014c40`
- `0x180014ef8`
- `0x18001531c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180014f49`
- `KERNEL32!SetLastError` at `0x180014f49`

## pseudocode

```c
struct CMDBaseObject *__fastcall CMDBaseObject::CreateBaseObject(char *a1)
{
  CMDBaseObject *v2; // rax
  CMDBaseObject *v3; // rax
  CMDBaseObject *v4; // rbx

  v2 = (CMDBaseObject *)operator new(0x118u);
  if ( !v2 || (v3 = CMDBaseObject::CMDBaseObject(v2, a1), (v4 = v3) == 0) )
  {
    SetLastError(0xEu);
    return 0;
  }
  if ( !(unsigned int)CMDBaseObject::Init(v3) )
  {
    (**(void (__fastcall ***)(CMDBaseObject *, __int64))v4)(v4, 1);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180014ef8  push    rbx
0x180014efa  sub     rsp, 20h
0x180014efe  mov     rbx, rcx
0x180014f01  mov     ecx, 118h; Size
0x180014f06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014f0b  test    rax, rax
0x180014f0e  jz      short loc_180014F44
0x180014f10  mov     rdx, rbx; char *
0x180014f13  mov     rcx, rax; this
0x180014f16  call    ??0CMDBaseObject@@AEAA@PEAD@Z; CMDBaseObject::CMDBaseObject(char *)
0x180014f1b  mov     rbx, rax
0x180014f1e  test    rax, rax
0x180014f21  jz      short loc_180014F44
0x180014f23  mov     rcx, rax; this
0x180014f26  call    ?Init@CMDBaseObject@@AEAAHXZ; CMDBaseObject::Init(void)
0x180014f2b  test    eax, eax
0x180014f2d  jnz     short loc_180014F51
0x180014f2f  mov     rax, [rbx]
0x180014f32  mov     edx, 1
0x180014f37  mov     rcx, rbx
0x180014f3a  mov     rax, [rax]
0x180014f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f42  jmp     short loc_180014F4F
0x180014f44  mov     ecx, 0Eh; dwErrCode
0x180014f49  call    cs:__imp_SetLastError
0x180014f4f  xor     ebx, ebx
0x180014f51  mov     rax, rbx
0x180014f54  add     rsp, 20h
0x180014f58  pop     rbx
0x180014f59  retn
```
