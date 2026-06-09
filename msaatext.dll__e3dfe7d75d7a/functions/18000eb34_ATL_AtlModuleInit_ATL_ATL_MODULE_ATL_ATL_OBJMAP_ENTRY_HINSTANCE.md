# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x18000eb34`
- end: `0x18000ecf6`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012718`

## callees

- `0x18000eb34`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000ec27`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec34`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec92`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec27`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec34`
- `KERNEL32!DeleteCriticalSection` at `0x18000ec92`
- `KERNEL32!InitializeCriticalSection` at `0x18000eb79`
- `KERNEL32!InitializeCriticalSection` at `0x18000eb87`
- `KERNEL32!InitializeCriticalSection` at `0x18000eb95`
- `KERNEL32!InitializeCriticalSection` at `0x18000eb79`
- `KERNEL32!InitializeCriticalSection` at `0x18000eb87`
- `KERNEL32!InitializeCriticalSection` at `0x18000eb95`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_180024B20 = (__int64)&off_180023000;
  qword_180024B10 = (__int64)a3;
  hModule = a3;
  qword_180024B08 = (__int64)a3;
  dword_180024B28 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_180024B60);
  InitializeCriticalSection(&CriticalSection);
  qword_180024BB8 = 0;
  byte_180024BC0 = 1;
  dword_180024BD0 = 0;
  dword_180024BE0 = 0;
  qword_180024BD8 = 0;
  qword_180024BE8 = 0;
  v4 = qword_180024B20;
  if ( qword_180024B20 )
  {
    while ( *(_QWORD *)v4 )
    {
      LOBYTE(v3) = 1;
      (*(void (__fastcall **)(__int64))(v4 + 64))(v3);
      v5 = 72;
      v3 = 56;
      if ( _Module == 176 )
        v5 = 56;
      v4 += v5;
    }
  }
  dword_180024BF0 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000eb34  push    rbx
0x18000eb36  sub     rsp, 20h
0x18000eb3a  lea     rax, off_180023000
0x18000eb41  mov     cs:qword_180024B20, rax
0x18000eb48  mov     cs:qword_180024B10, r8
0x18000eb4f  mov     cs:hModule, r8
0x18000eb56  mov     cs:qword_180024B08, r8
0x18000eb5d  mov     cs:dword_180024B28, 0
0x18000eb67  mov     cs:hHeap, 0
0x18000eb72  lea     rcx, Buf1; lpCriticalSection
0x18000eb79  call    cs:__imp_InitializeCriticalSection
0x18000eb7f  nop
0x18000eb80  lea     rcx, stru_180024B60; lpCriticalSection
0x18000eb87  call    cs:__imp_InitializeCriticalSection
0x18000eb8d  nop
0x18000eb8e  lea     rcx, CriticalSection; lpCriticalSection
0x18000eb95  call    cs:__imp_InitializeCriticalSection
0x18000eb9b  nop
0x18000eb9c  mov     cs:qword_180024BB8, 0
0x18000eba7  mov     cs:byte_180024BC0, 1
0x18000ebae  mov     cs:dword_180024BD0, 0
0x18000ebb8  mov     cs:dword_180024BE0, 0
0x18000ebc2  mov     cs:qword_180024BD8, 0
0x18000ebcd  mov     cs:qword_180024BE8, 0
0x18000ebd8  mov     rbx, cs:qword_180024B20
0x18000ebdf  test    rbx, rbx
0x18000ebe2  jz      short loc_18000EC0F
0x18000ebe4  jmp     short loc_18000EC09
0x18000ebe6  mov     cl, 1
0x18000ebe8  mov     rax, [rbx+40h]
0x18000ebec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf1  mov     eax, 48h ; 'H'
0x18000ebf6  lea     ecx, [rax-10h]
0x18000ebf9  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18000ec03  cmovz   eax, ecx
0x18000ec06  add     rbx, rax
0x18000ec09  cmp     qword ptr [rbx], 0
0x18000ec0d  jnz     short loc_18000EBE6
0x18000ec0f  mov     cs:dword_180024BF0, 1
0x18000ec19  xor     eax, eax
0x18000ec1b  jmp     loc_18000ECF0
0x18000ec20  lea     rcx, stru_180024B60; lpCriticalSection
0x18000ec27  call    cs:__imp_DeleteCriticalSection
0x18000ec2d  lea     rcx, Buf1; lpCriticalSection
0x18000ec34  call    cs:__imp_DeleteCriticalSection
0x18000ec3a  xorps   xmm0, xmm0
0x18000ec3d  xor     eax, eax
0x18000ec3f  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x18000ec46  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x18000ec4d  mov     cs:CriticalSection.SpinCount, rax
0x18000ec54  xorps   xmm1, xmm1
0x18000ec57  movups  xmmword ptr cs:stru_180024B60.DebugInfo, xmm1
0x18000ec5e  movups  xmmword ptr cs:stru_180024B60.OwningThread, xmm1
0x18000ec65  mov     cs:stru_180024B60.SpinCount, rax
0x18000ec6c  xorps   xmm0, xmm0
0x18000ec6f  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18000ec76  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18000ec7d  mov     cs:Buf1.SpinCount, rax
0x18000ec84  mov     eax, 0C0000017h
0x18000ec89  jmp     short loc_18000ECF0
0x18000ec8b  lea     rcx, Buf1; lpCriticalSection
0x18000ec92  call    cs:__imp_DeleteCriticalSection
0x18000ec98  xorps   xmm0, xmm0
0x18000ec9b  xor     eax, eax
0x18000ec9d  movups  xmmword ptr cs:stru_180024B60.DebugInfo, xmm0
0x18000eca4  movups  xmmword ptr cs:stru_180024B60.OwningThread, xmm0
0x18000ecab  mov     cs:stru_180024B60.SpinCount, rax
0x18000ecb2  xorps   xmm1, xmm1
0x18000ecb5  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x18000ecbc  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x18000ecc3  mov     cs:Buf1.SpinCount, rax
0x18000ecca  mov     eax, 0C0000017h
0x18000eccf  jmp     short loc_18000ECF0
0x18000ecd1  xorps   xmm0, xmm0
0x18000ecd4  xor     eax, eax
0x18000ecd6  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18000ecdd  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18000ece4  mov     cs:Buf1.SpinCount, rax
0x18000eceb  mov     eax, 0C0000017h
0x18000ecf0  add     rsp, 20h
0x18000ecf4  pop     rbx
0x18000ecf5  retn
0x18001390f  push    rbp
0x180013911  sub     rsp, 20h
0x180013915  mov     rbp, rdx
0x180013918  mov     rax, [rcx]
0x18001391b  xor     ecx, ecx
0x18001391d  cmp     dword ptr [rax], 0C0000017h
0x180013923  setz    cl
0x180013926  mov     eax, ecx
0x180013928  add     rsp, 20h
0x18001392c  pop     rbp
0x18001392d  retn
0x18001392f  push    rbp
0x180013931  sub     rsp, 20h
0x180013935  mov     rbp, rdx
0x180013938  mov     rax, [rcx]
0x18001393b  xor     ecx, ecx
0x18001393d  cmp     dword ptr [rax], 0C0000017h
0x180013943  setz    cl
0x180013946  mov     eax, ecx
0x180013948  add     rsp, 20h
0x18001394c  pop     rbp
0x18001394d  retn
0x18001394f  push    rbp
0x180013951  sub     rsp, 20h
0x180013955  mov     rbp, rdx
0x180013958  mov     rax, [rcx]
0x18001395b  xor     ecx, ecx
0x18001395d  cmp     dword ptr [rax], 0C0000017h
0x180013963  setz    cl
0x180013966  mov     eax, ecx
0x180013968  add     rsp, 20h
0x18001396c  pop     rbp
0x18001396d  retn
```
