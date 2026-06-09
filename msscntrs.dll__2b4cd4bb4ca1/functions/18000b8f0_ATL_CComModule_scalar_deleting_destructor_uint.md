# ATL::CComModule::`scalar deleting destructor'(uint)

- ea: `0x18000b8f0`
- end: `0x18000b92e`
- name: `??_GCComModule@ATL@@UEAAPEAXI@Z`
- size: `62`
- prototype: `ATL::CComModule *__fastcall(ATL::CComModule *this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002984`
- `0x18000b4d8`
- `0x18000b8f0`

## pseudocode

```c
ATL::CComModule *__fastcall ATL::CComModule::`scalar deleting destructor'(ATL::CComModule *this, unsigned int a2)
{
  char v2; // bl

  v2 = a2;
  *(_QWORD *)this = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule(this, a2);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b8f0  mov     [rsp+arg_0], rbx
0x18000b8f5  push    rdi
0x18000b8f6  sub     rsp, 20h
0x18000b8fa  lea     rax, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x18000b901  mov     ebx, edx
0x18000b903  mov     [rcx], rax
0x18000b906  mov     rdi, rcx
0x18000b909  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x18000b90e  test    bl, 1
0x18000b911  jz      short loc_18000B920
0x18000b913  mov     edx, 50h ; 'P'
0x18000b918  mov     rcx, rdi; Block
0x18000b91b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b920  mov     rbx, [rsp+28h+arg_0]
0x18000b925  mov     rax, rdi
0x18000b928  add     rsp, 20h
0x18000b92c  pop     rdi
0x18000b92d  retn
```
