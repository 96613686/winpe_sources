# CImpIADOSecurity::SetSite(IUnknown *)

- ea: `0x18002a830`
- end: `0x18002a893`
- name: `?SetSite@CImpIADOSecurity@@UEAAJPEAUIUnknown@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015720`
- `0x18002a140`

## callees

- `0x18002a108`
- `0x18002a1a0`
- `0x18002a830`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::SetSite(struct CCriticalSection **this, struct IUnknown *a2)
{
  struct CCriticalSection *v4; // rcx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  CMPCSAutoBlock::CMPCSAutoBlock((CMPCSAutoBlock *)&v6, this + 5);
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
  v4 = this[4];
  if ( v4 )
    (*(void (__fastcall **)(struct CCriticalSection *))(*(_QWORD *)v4 + 16LL))(v4);
  this[4] = (struct CCriticalSection *)a2;
  CMPCSAutoBlock::~CMPCSAutoBlock((CMPCSAutoBlock *)&v6);
  return 0;
}

```

## disassembly

```asm
0x18002a830  mov     [rsp+arg_8], rbx
0x18002a835  push    rdi
0x18002a836  sub     rsp, 20h
0x18002a83a  mov     rbx, rdx
0x18002a83d  mov     rdi, rcx
0x18002a840  lea     rdx, [rcx+28h]; struct CCriticalSection **
0x18002a844  lea     rcx, [rsp+28h+arg_0]; this
0x18002a849  call    ??0CMPCSAutoBlock@@QEAA@PEAPEAVCCriticalSection@@@Z; CMPCSAutoBlock::CMPCSAutoBlock(CCriticalSection * *)
0x18002a84e  test    rbx, rbx
0x18002a851  jz      short loc_18002A862
0x18002a853  mov     rax, [rbx]
0x18002a856  mov     rcx, rbx
0x18002a859  mov     rax, [rax+8]
0x18002a85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a862  mov     rcx, [rdi+20h]
0x18002a866  test    rcx, rcx
0x18002a869  jz      short loc_18002A877
0x18002a86b  mov     rax, [rcx]
0x18002a86e  mov     rax, [rax+10h]
0x18002a872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a877  lea     rcx, [rsp+28h+arg_0]; this
0x18002a87c  mov     [rdi+20h], rbx
0x18002a880  call    ??1CMPCSAutoBlock@@QEAA@XZ; CMPCSAutoBlock::~CMPCSAutoBlock(void)
0x18002a885  mov     rbx, [rsp+28h+arg_8]
0x18002a88a  xor     eax, eax
0x18002a88c  add     rsp, 20h
0x18002a890  pop     rdi
0x18002a891  retn
```
