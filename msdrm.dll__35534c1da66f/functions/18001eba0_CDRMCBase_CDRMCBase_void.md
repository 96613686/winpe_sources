# CDRMCBase::~CDRMCBase(void)

- ea: `0x18001eba0`
- end: `0x18001ec18`
- name: `??1CDRMCBase@@UEAA@XZ`
- size: `120`
- prototype: `void __fastcall(CDRMCBase *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18000831c`
- `0x180008454`
- `0x1800087bc`
- `0x180008824`
- `0x180008908`
- `0x18000895c`
- `0x1800089e0`
- `0x180008a0c`
- `0x180008ae8`
- `0x180008bbc`
- `0x180008f70`
- `0x180008fb0`
- `0x18001ec20`
- `0x180020228`
- `0x180022928`

## callees

- `0x18001eba0`
- `0x18001ffd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ebd6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001ebd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ebfe`

## pseudocode

```c
void __fastcall CDRMCBase::~CDRMCBase(CDRMCBase *this)
{
  __int64 i; // rbx
  void *v3; // rcx
  CDRMCBase *v4; // rcx
  __int64 j; // rbx
  void *v6; // rcx

  *(_QWORD *)this = &CDRMCBase::`vftable';
  for ( i = 0; i != 4; ++i )
  {
    v3 = (void *)*((_QWORD *)this + i + 3);
    if ( v3 )
      CloseHandle(v3);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v4 = (CDRMCBase *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CDRMCBase::Release(v4);
    *((_QWORD *)this + 2) = 0;
  }
  for ( j = 0; j != 4; ++j )
  {
    v6 = (void *)*((_QWORD *)this + j + 7);
    if ( v6 )
      CloseHandle(v6);
  }
}

```

## disassembly

```asm
0x18001eba0  mov     [rsp+arg_0], rbx
0x18001eba5  push    rdi
0x18001eba6  sub     rsp, 20h
0x18001ebaa  lea     rax, ??_7CDRMCBase@@6B@; const CDRMCBase::`vftable'
0x18001ebb1  mov     rdi, rcx
0x18001ebb4  mov     [rcx], rax
0x18001ebb7  xor     ebx, ebx
0x18001ebb9  mov     rcx, [rdi+rbx*8+18h]; hObject
0x18001ebbe  test    rcx, rcx
0x18001ebc1  jz      short loc_18001EBC9
0x18001ebc3  call    cs:__imp_CloseHandle
0x18001ebc9  inc     rbx
0x18001ebcc  cmp     rbx, 4
0x18001ebd0  jnz     short loc_18001EBB9
0x18001ebd2  lea     rcx, [rdi+58h]; lpCriticalSection
0x18001ebd6  call    cs:__imp_DeleteCriticalSection
0x18001ebdc  mov     rcx, [rdi+10h]; this
0x18001ebe0  test    rcx, rcx
0x18001ebe3  jz      short loc_18001EBF2
0x18001ebe5  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18001ebea  mov     qword ptr [rdi+10h], 0
0x18001ebf2  xor     ebx, ebx
0x18001ebf4  mov     rcx, [rdi+rbx*8+38h]; hObject
0x18001ebf9  test    rcx, rcx
0x18001ebfc  jz      short loc_18001EC04
0x18001ebfe  call    cs:__imp_CloseHandle
0x18001ec04  inc     rbx
0x18001ec07  cmp     rbx, 4
0x18001ec0b  jnz     short loc_18001EBF4
0x18001ec0d  mov     rbx, [rsp+28h+arg_0]
0x18001ec12  add     rsp, 20h
0x18001ec16  pop     rdi
0x18001ec17  retn
```
