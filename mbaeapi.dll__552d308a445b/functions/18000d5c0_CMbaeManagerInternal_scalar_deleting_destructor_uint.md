# CMbaeManagerInternal::`scalar deleting destructor'(uint)

- ea: `0x18000d5c0`
- end: `0x18000d62d`
- name: `??_GCMbaeManagerInternal@@UEAAPEAXI@Z`
- size: `109`
- prototype: `CMbaeManagerInternal *__fastcall(CMbaeManagerInternal *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800028b0`
- `0x18000d5c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d5e2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d5e2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d606`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d606`

## pseudocode

```c
CMbaeManagerInternal *__fastcall CMbaeManagerInternal::`scalar deleting destructor'(
        CMbaeManagerInternal *this,
        char a2)
{
  void *v4; // rcx

  *(_QWORD *)this = &CMbaeManagerInternal::`vftable';
  v4 = (void *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 11) = 0;
  }
  *((_QWORD *)this + 12) = 0;
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d5c0  mov     [rsp+arg_0], rbx
0x18000d5c5  push    rdi
0x18000d5c6  sub     rsp, 20h
0x18000d5ca  lea     rax, ??_7CMbaeManagerInternal@@6B@; const CMbaeManagerInternal::`vftable'
0x18000d5d1  mov     rbx, rcx
0x18000d5d4  mov     [rcx], rax
0x18000d5d7  mov     edi, edx
0x18000d5d9  mov     rcx, [rcx+58h]; Block
0x18000d5dd  test    rcx, rcx
0x18000d5e0  jz      short loc_18000D5F0
0x18000d5e2  call    cs:__imp_free
0x18000d5e8  mov     qword ptr [rbx+58h], 0
0x18000d5f0  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000d5f4  mov     qword ptr [rbx+60h], 0
0x18000d5fc  cmp     byte ptr [rcx+28h], 0
0x18000d600  jz      short loc_18000D60C
0x18000d602  mov     byte ptr [rcx+28h], 0
0x18000d606  call    cs:__imp_DeleteCriticalSection
0x18000d60c  test    dil, 1
0x18000d610  jz      short loc_18000D61F
0x18000d612  mov     edx, 68h ; 'h'
0x18000d617  mov     rcx, rbx; Block
0x18000d61a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d61f  mov     rax, rbx
0x18000d622  mov     rbx, [rsp+28h+arg_0]
0x18000d627  add     rsp, 20h
0x18000d62b  pop     rdi
0x18000d62c  retn
```
