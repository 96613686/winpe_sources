# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x18000c460`
- end: `0x18000c622`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001270`

## callees

- `0x18000c460`
- `0x180029010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c553`
- `KERNEL32!DeleteCriticalSection` at `0x18000c560`
- `KERNEL32!DeleteCriticalSection` at `0x18000c5be`
- `KERNEL32!DeleteCriticalSection` at `0x18000c553`
- `KERNEL32!DeleteCriticalSection` at `0x18000c560`
- `KERNEL32!DeleteCriticalSection` at `0x18000c5be`
- `KERNEL32!InitializeCriticalSection` at `0x18000c4a5`
- `KERNEL32!InitializeCriticalSection` at `0x18000c4b3`
- `KERNEL32!InitializeCriticalSection` at `0x18000c4c1`
- `KERNEL32!InitializeCriticalSection` at `0x18000c4a5`
- `KERNEL32!InitializeCriticalSection` at `0x18000c4b3`
- `KERNEL32!InitializeCriticalSection` at `0x18000c4c1`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_180038600 = (__int64)&off_180037000;
  qword_1800385F0 = a3;
  qword_1800385F8 = a3;
  qword_1800385E8 = a3;
  dword_180038608 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_180038640);
  InitializeCriticalSection(&CriticalSection);
  qword_180038698 = 0;
  byte_1800386A0 = 1;
  dword_1800386B0 = 0;
  dword_1800386C0 = 0;
  qword_1800386B8 = 0;
  Block = 0;
  v4 = qword_180038600;
  if ( qword_180038600 )
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
  dword_1800386D0 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000c460  push    rbx
0x18000c462  sub     rsp, 20h
0x18000c466  lea     rax, off_180037000
0x18000c46d  mov     cs:qword_180038600, rax
0x18000c474  mov     cs:qword_1800385F0, r8
0x18000c47b  mov     cs:qword_1800385F8, r8
0x18000c482  mov     cs:qword_1800385E8, r8
0x18000c489  mov     cs:dword_180038608, 0
0x18000c493  mov     cs:hHeap, 0
0x18000c49e  lea     rcx, Buf1; lpCriticalSection
0x18000c4a5  call    cs:__imp_InitializeCriticalSection
0x18000c4ab  nop
0x18000c4ac  lea     rcx, stru_180038640; lpCriticalSection
0x18000c4b3  call    cs:__imp_InitializeCriticalSection
0x18000c4b9  nop
0x18000c4ba  lea     rcx, CriticalSection; lpCriticalSection
0x18000c4c1  call    cs:__imp_InitializeCriticalSection
0x18000c4c7  nop
0x18000c4c8  mov     cs:qword_180038698, 0
0x18000c4d3  mov     cs:byte_1800386A0, 1
0x18000c4da  mov     cs:dword_1800386B0, 0
0x18000c4e4  mov     cs:dword_1800386C0, 0
0x18000c4ee  mov     cs:qword_1800386B8, 0
0x18000c4f9  mov     cs:Block, 0
0x18000c504  mov     rbx, cs:qword_180038600
0x18000c50b  test    rbx, rbx
0x18000c50e  jz      short loc_18000C53B
0x18000c510  jmp     short loc_18000C535
0x18000c512  mov     cl, 1
0x18000c514  mov     rax, [rbx+40h]
0x18000c518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c51d  mov     eax, 48h ; 'H'
0x18000c522  lea     ecx, [rax-10h]
0x18000c525  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18000c52f  cmovz   eax, ecx
0x18000c532  add     rbx, rax
0x18000c535  cmp     qword ptr [rbx], 0
0x18000c539  jnz     short loc_18000C512
0x18000c53b  mov     cs:dword_1800386D0, 1
0x18000c545  xor     eax, eax
0x18000c547  jmp     loc_18000C61C
0x18000c54c  lea     rcx, stru_180038640; lpCriticalSection
0x18000c553  call    cs:__imp_DeleteCriticalSection
0x18000c559  lea     rcx, Buf1; lpCriticalSection
0x18000c560  call    cs:__imp_DeleteCriticalSection
0x18000c566  xorps   xmm0, xmm0
0x18000c569  xor     eax, eax
0x18000c56b  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x18000c572  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x18000c579  mov     cs:CriticalSection.SpinCount, rax
0x18000c580  xorps   xmm1, xmm1
0x18000c583  movups  xmmword ptr cs:stru_180038640.DebugInfo, xmm1
0x18000c58a  movups  xmmword ptr cs:stru_180038640.OwningThread, xmm1
0x18000c591  mov     cs:stru_180038640.SpinCount, rax
0x18000c598  xorps   xmm0, xmm0
0x18000c59b  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18000c5a2  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18000c5a9  mov     cs:Buf1.SpinCount, rax
0x18000c5b0  mov     eax, 0C0000017h
0x18000c5b5  jmp     short loc_18000C61C
0x18000c5b7  lea     rcx, Buf1; lpCriticalSection
0x18000c5be  call    cs:__imp_DeleteCriticalSection
0x18000c5c4  xorps   xmm0, xmm0
0x18000c5c7  xor     eax, eax
0x18000c5c9  movups  xmmword ptr cs:stru_180038640.DebugInfo, xmm0
0x18000c5d0  movups  xmmword ptr cs:stru_180038640.OwningThread, xmm0
0x18000c5d7  mov     cs:stru_180038640.SpinCount, rax
0x18000c5de  xorps   xmm1, xmm1
0x18000c5e1  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x18000c5e8  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x18000c5ef  mov     cs:Buf1.SpinCount, rax
0x18000c5f6  mov     eax, 0C0000017h
0x18000c5fb  jmp     short loc_18000C61C
0x18000c5fd  xorps   xmm0, xmm0
0x18000c600  xor     eax, eax
0x18000c602  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18000c609  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18000c610  mov     cs:Buf1.SpinCount, rax
0x18000c617  mov     eax, 0C0000017h
0x18000c61c  add     rsp, 20h
0x18000c620  pop     rbx
0x18000c621  retn
0x180027b19  push    rbp
0x180027b1b  sub     rsp, 20h
0x180027b1f  mov     rbp, rdx
0x180027b22  mov     rax, [rcx]
0x180027b25  xor     ecx, ecx
0x180027b27  cmp     dword ptr [rax], 0C0000017h
0x180027b2d  setz    cl
0x180027b30  mov     eax, ecx
0x180027b32  add     rsp, 20h
0x180027b36  pop     rbp
0x180027b37  retn
0x180027b39  push    rbp
0x180027b3b  sub     rsp, 20h
0x180027b3f  mov     rbp, rdx
0x180027b42  mov     rax, [rcx]
0x180027b45  xor     ecx, ecx
0x180027b47  cmp     dword ptr [rax], 0C0000017h
0x180027b4d  setz    cl
0x180027b50  mov     eax, ecx
0x180027b52  add     rsp, 20h
0x180027b56  pop     rbp
0x180027b57  retn
0x180027b59  push    rbp
0x180027b5b  sub     rsp, 20h
0x180027b5f  mov     rbp, rdx
0x180027b62  mov     rax, [rcx]
0x180027b65  xor     ecx, ecx
0x180027b67  cmp     dword ptr [rax], 0C0000017h
0x180027b6d  setz    cl
0x180027b70  mov     eax, ecx
0x180027b72  add     rsp, 20h
0x180027b76  pop     rbp
0x180027b77  retn
```
