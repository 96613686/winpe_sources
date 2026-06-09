# CClfsLogCcb::~CClfsLogCcb(void)

- ea: `0x140033ac0`
- end: `0x140033bad`
- name: `??1CClfsLogCcb@@QEAA@XZ`
- size: `237`
- prototype: `void __fastcall(CClfsLogCcb *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140055440`
- `0x140057980`
- `0x140059e80`
- `0x1400699d0`
- `0x14006bd40`

## callees

- `0x140005840`
- `0x140016504`
- `0x140033ac0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140033b95`
- `ntoskrnl!ExDeleteResourceLite` at `0x140033b95`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140033b51`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140033b51`
- `ntoskrnl!ObfDereferenceObject` at `0x140033b7a`
- `ntoskrnl!ObfDereferenceObject` at `0x140033b7a`
- `ntoskrnl!KeBugCheckEx` at `0x140033af9`
- `ntoskrnl!KeBugCheckEx` at `0x140033b28`
- `ntoskrnl!KeBugCheckEx` at `0x140033af9`
- `ntoskrnl!KeBugCheckEx` at `0x140033b28`

## pseudocode

```c
void __fastcall CClfsLogCcb::~CClfsLogCcb(CClfsLogCcb *this)
{
  ULONG_PTR v2; // rax
  ULONG_PTR v3; // r8
  __int64 v4; // rbx
  void *v5; // rcx

  if ( (*((_DWORD *)this + 7) & 4) == 0 )
  {
    v2 = *((int *)this + 10);
    if ( (_DWORD)v2 )
      KeBugCheckEx(0xC1F5u, 0x16u, v2, (ULONG_PTR)this, 0);
    v3 = *((_QWORD *)this + 32);
    if ( v3 )
      KeBugCheckEx(0xC1F5u, 0x17u, v3, (ULONG_PTR)this, 0);
    if ( (*((_DWORD *)this + 7) & 0x80u) != 0 )
    {
      v4 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 24LL) + 120LL);
      ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 200), 1u);
      CClfsLogCcb::Unlink(this);
      ClfsReleaseResourceLite((struct _ERESOURCE *)(v4 + 200));
    }
  }
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    ObfDereferenceObject(v5);
    *((_QWORD *)this + 10) = 0;
  }
  ExDeleteResourceLite((PERESOURCE)((char *)this + 152));
}

```

## disassembly

```asm
0x140033ac0  mov     [rsp+arg_0], rbx
0x140033ac5  push    rdi
0x140033ac6  sub     rsp, 30h
0x140033aca  mov     eax, [rcx+1Ch]
0x140033acd  mov     rdi, rcx
0x140033ad0  test    al, 4
0x140033ad2  jnz     loc_140033B71
0x140033ad8  movsxd  rax, dword ptr [rcx+28h]
0x140033adc  test    eax, eax
0x140033ade  jz      short loc_140033B06
0x140033ae0  mov     r9, rcx; BugCheckParameter3
0x140033ae3  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140033aec  mov     ecx, 0C1F5h; BugCheckCode
0x140033af1  mov     r8, rax; BugCheckParameter2
0x140033af4  mov     edx, 16h; BugCheckParameter1
0x140033af9  call    cs:__imp_KeBugCheckEx
0x140033b06  mov     r8, [rcx+100h]; BugCheckParameter2
0x140033b0d  test    r8, r8
0x140033b10  jz      short loc_140033B35
0x140033b12  mov     r9, rdi; BugCheckParameter3
0x140033b15  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140033b1e  mov     edx, 17h; BugCheckParameter1
0x140033b23  mov     ecx, 0C1F5h; BugCheckCode
0x140033b28  call    cs:__imp_KeBugCheckEx
0x140033b35  mov     eax, [rcx+1Ch]
0x140033b38  test    al, al
0x140033b3a  jns     short loc_140033B71
0x140033b3c  mov     rax, [rcx+48h]
0x140033b40  mov     dl, 1; Wait
0x140033b42  mov     rcx, [rax+18h]
0x140033b46  mov     rbx, [rcx+78h]
0x140033b4a  lea     rcx, [rbx+0C8h]; Resource
0x140033b51  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140033b58  nop     dword ptr [rax+rax+00h]
0x140033b5d  mov     rcx, rdi; this
0x140033b60  call    ?Unlink@CClfsLogCcb@@QEAAXXZ; CClfsLogCcb::Unlink(void)
0x140033b65  lea     rcx, [rbx+0C8h]
0x140033b6c  call    ClfsReleaseResourceLite
0x140033b71  mov     rcx, [rdi+50h]; Object
0x140033b75  test    rcx, rcx
0x140033b78  jz      short loc_140033B8E
0x140033b7a  call    cs:__imp_ObfDereferenceObject
0x140033b81  nop     dword ptr [rax+rax+00h]
0x140033b86  mov     qword ptr [rdi+50h], 0
0x140033b8e  lea     rcx, [rdi+98h]; Resource
0x140033b95  call    cs:__imp_ExDeleteResourceLite
0x140033b9c  nop     dword ptr [rax+rax+00h]
0x140033ba1  mov     rbx, [rsp+38h+arg_0]
0x140033ba6  add     rsp, 30h
0x140033baa  pop     rdi
0x140033bab  retn
```
