# CMDBaseObject::CreateBaseObject(ushort *)

- ea: `0x180014f60`
- end: `0x180014fc2`
- name: `?CreateBaseObject@CMDBaseObject@@SAPEAV1@PEAG@Z`
- size: `98`
- prototype: `struct CMDBaseObject *__fastcall(unsigned __int16 *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180012ec0`
- `0x180013790`
- `0x18001aeb4`
- `0x1800209e8`
- `0x180020be8`
- `0x180022ab8`
- `0x180022c20`

## callees

- `0x1800089c8`
- `0x180014cd0`
- `0x180014f60`
- `0x18001531c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180014fb1`
- `KERNEL32!SetLastError` at `0x180014fb1`

## pseudocode

```c
struct CMDBaseObject *__fastcall CMDBaseObject::CreateBaseObject(unsigned __int16 *a1)
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
0x180014f60  push    rbx
0x180014f62  sub     rsp, 20h
0x180014f66  mov     rbx, rcx
0x180014f69  mov     ecx, 118h; Size
0x180014f6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014f73  test    rax, rax
0x180014f76  jz      short loc_180014FAC
0x180014f78  mov     rdx, rbx; unsigned __int16 *
0x180014f7b  mov     rcx, rax; this
0x180014f7e  call    ??0CMDBaseObject@@AEAA@PEAG@Z; CMDBaseObject::CMDBaseObject(ushort *)
0x180014f83  mov     rbx, rax
0x180014f86  test    rax, rax
0x180014f89  jz      short loc_180014FAC
0x180014f8b  mov     rcx, rax; this
0x180014f8e  call    ?Init@CMDBaseObject@@AEAAHXZ; CMDBaseObject::Init(void)
0x180014f93  test    eax, eax
0x180014f95  jnz     short loc_180014FB9
0x180014f97  mov     rax, [rbx]
0x180014f9a  mov     edx, 1
0x180014f9f  mov     rcx, rbx
0x180014fa2  mov     rax, [rax]
0x180014fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014faa  jmp     short loc_180014FB7
0x180014fac  mov     ecx, 0Eh; dwErrCode
0x180014fb1  call    cs:__imp_SetLastError
0x180014fb7  xor     ebx, ebx
0x180014fb9  mov     rax, rbx
0x180014fbc  add     rsp, 20h
0x180014fc0  pop     rbx
0x180014fc1  retn
```
