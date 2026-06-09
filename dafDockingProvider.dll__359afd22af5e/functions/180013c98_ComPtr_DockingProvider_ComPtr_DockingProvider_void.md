# ComPtr<DockingProvider>::~ComPtr<DockingProvider>(void)

- ea: `0x180013c98`
- end: `0x180013cdb`
- name: `??1?$ComPtr@VDockingProvider@@@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(DockingProvider **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d817`

## callees

- `0x1800014d0`
- `0x180013c98`
- `0x180013d88`

## pseudocode

```c
void __fastcall ComPtr<DockingProvider>::~ComPtr<DockingProvider>(DockingProvider **a1)
{
  DockingProvider *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      DockingProvider::~DockingProvider(v1);
      operator delete(v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180013c98  mov     [rsp+arg_8], rbx
0x180013c9d  push    rdi
0x180013c9e  sub     rsp, 20h
0x180013ca2  mov     rbx, [rcx]
0x180013ca5  mov     rdi, rcx
0x180013ca8  test    rbx, rbx
0x180013cab  jz      short loc_180013CD0
0x180013cad  or      eax, 0FFFFFFFFh
0x180013cb0  lock xadd [rbx], eax
0x180013cb4  cmp     eax, 1
0x180013cb7  jnz     short loc_180013CC9
0x180013cb9  mov     rcx, rbx; this
0x180013cbc  call    ??1DockingProvider@@QEAA@XZ; DockingProvider::~DockingProvider(void)
0x180013cc1  mov     rcx, rbx; Block
0x180013cc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013cc9  mov     qword ptr [rdi], 0
0x180013cd0  mov     rbx, [rsp+28h+arg_8]
0x180013cd5  add     rsp, 20h
0x180013cd9  pop     rdi
0x180013cda  retn
```
