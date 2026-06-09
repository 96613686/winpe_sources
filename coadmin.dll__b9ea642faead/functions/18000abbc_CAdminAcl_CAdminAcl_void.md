# CAdminAcl::~CAdminAcl(void)

- ea: `0x18000abbc`
- end: `0x18000ac09`
- name: `??1CAdminAcl@@QEAA@XZ`
- size: `77`
- prototype: `void __fastcall(CAdminAcl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000bddc`

## callees

- `0x18000abbc`
- `0x180010010`

## pseudocode

```c
void __fastcall CAdminAcl::~CAdminAcl(CAdminAcl *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 70);
  if ( v2 )
  {
    if ( *((_DWORD *)this + 136) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 352LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 70) + 16LL))(*((_QWORD *)this + 70));
  }
  *(_DWORD *)this = 1735208393;
}

```

## disassembly

```asm
0x18000abbc  push    rbx
0x18000abbe  sub     rsp, 20h
0x18000abc2  mov     rbx, rcx
0x18000abc5  mov     rcx, [rcx+230h]
0x18000abcc  test    rcx, rcx
0x18000abcf  jz      short loc_18000ABFD
0x18000abd1  mov     edx, [rbx+220h]
0x18000abd7  test    edx, edx
0x18000abd9  jz      short loc_18000ABEA
0x18000abdb  mov     rax, [rcx]
0x18000abde  mov     rax, [rax+160h]
0x18000abe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abea  mov     rcx, [rbx+230h]
0x18000abf1  mov     rax, [rcx]
0x18000abf4  mov     rax, [rax+10h]
0x18000abf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abfd  mov     dword ptr [rbx], 676D2DC9h
0x18000ac03  add     rsp, 20h
0x18000ac07  pop     rbx
0x18000ac08  retn
```
