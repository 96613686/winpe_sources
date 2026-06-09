# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x1800029b4`
- end: `0x180002b76`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a74`

## callees

- `0x1800029b4`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002aa7`
- `KERNEL32!DeleteCriticalSection` at `0x180002ab4`
- `KERNEL32!DeleteCriticalSection` at `0x180002b12`
- `KERNEL32!DeleteCriticalSection` at `0x180002aa7`
- `KERNEL32!DeleteCriticalSection` at `0x180002ab4`
- `KERNEL32!DeleteCriticalSection` at `0x180002b12`
- `KERNEL32!InitializeCriticalSection` at `0x1800029f9`
- `KERNEL32!InitializeCriticalSection` at `0x180002a07`
- `KERNEL32!InitializeCriticalSection` at `0x180002a15`
- `KERNEL32!InitializeCriticalSection` at `0x1800029f9`
- `KERNEL32!InitializeCriticalSection` at `0x180002a07`
- `KERNEL32!InitializeCriticalSection` at `0x180002a15`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_18001EB50 = (__int64)&off_18001E000;
  qword_18001EB40 = a3;
  qword_18001EB48 = a3;
  qword_18001EB38 = a3;
  dword_18001EB58 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_18001EB90);
  InitializeCriticalSection(&stru_18001EBB8);
  qword_18001EBE8 = 0;
  byte_18001EBF0 = 1;
  dword_18001EC00 = 0;
  dword_18001EC10 = 0;
  qword_18001EC08 = 0;
  Block = 0;
  v4 = qword_18001EB50;
  if ( qword_18001EB50 )
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
  dword_18001EC20 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800029b4  push    rbx
0x1800029b6  sub     rsp, 20h
0x1800029ba  lea     rax, off_18001E000
0x1800029c1  mov     cs:qword_18001EB50, rax
0x1800029c8  mov     cs:qword_18001EB40, r8
0x1800029cf  mov     cs:qword_18001EB48, r8
0x1800029d6  mov     cs:qword_18001EB38, r8
0x1800029dd  mov     cs:dword_18001EB58, 0
0x1800029e7  mov     cs:hHeap, 0
0x1800029f2  lea     rcx, Buf1; lpCriticalSection
0x1800029f9  call    cs:__imp_InitializeCriticalSection
0x1800029ff  nop
0x180002a00  lea     rcx, stru_18001EB90; lpCriticalSection
0x180002a07  call    cs:__imp_InitializeCriticalSection
0x180002a0d  nop
0x180002a0e  lea     rcx, stru_18001EBB8; lpCriticalSection
0x180002a15  call    cs:__imp_InitializeCriticalSection
0x180002a1b  nop
0x180002a1c  mov     cs:qword_18001EBE8, 0
0x180002a27  mov     cs:byte_18001EBF0, 1
0x180002a2e  mov     cs:dword_18001EC00, 0
0x180002a38  mov     cs:dword_18001EC10, 0
0x180002a42  mov     cs:qword_18001EC08, 0
0x180002a4d  mov     cs:Block, 0
0x180002a58  mov     rbx, cs:qword_18001EB50
0x180002a5f  test    rbx, rbx
0x180002a62  jz      short loc_180002A8F
0x180002a64  jmp     short loc_180002A89
0x180002a66  mov     cl, 1
0x180002a68  mov     rax, [rbx+40h]
0x180002a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a71  mov     eax, 48h ; 'H'
0x180002a76  lea     ecx, [rax-10h]
0x180002a79  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x180002a83  cmovz   eax, ecx
0x180002a86  add     rbx, rax
0x180002a89  cmp     qword ptr [rbx], 0
0x180002a8d  jnz     short loc_180002A66
0x180002a8f  mov     cs:dword_18001EC20, 1
0x180002a99  xor     eax, eax
0x180002a9b  jmp     loc_180002B70
0x180002aa0  lea     rcx, stru_18001EB90; lpCriticalSection
0x180002aa7  call    cs:__imp_DeleteCriticalSection
0x180002aad  lea     rcx, Buf1; lpCriticalSection
0x180002ab4  call    cs:__imp_DeleteCriticalSection
0x180002aba  xorps   xmm0, xmm0
0x180002abd  xor     eax, eax
0x180002abf  movups  xmmword ptr cs:stru_18001EBB8.DebugInfo, xmm0
0x180002ac6  movups  xmmword ptr cs:stru_18001EBB8.OwningThread, xmm0
0x180002acd  mov     cs:stru_18001EBB8.SpinCount, rax
0x180002ad4  xorps   xmm1, xmm1
0x180002ad7  movups  xmmword ptr cs:stru_18001EB90.DebugInfo, xmm1
0x180002ade  movups  xmmword ptr cs:stru_18001EB90.OwningThread, xmm1
0x180002ae5  mov     cs:stru_18001EB90.SpinCount, rax
0x180002aec  xorps   xmm0, xmm0
0x180002aef  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x180002af6  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x180002afd  mov     cs:Buf1.SpinCount, rax
0x180002b04  mov     eax, 0C0000017h
0x180002b09  jmp     short loc_180002B70
0x180002b0b  lea     rcx, Buf1; lpCriticalSection
0x180002b12  call    cs:__imp_DeleteCriticalSection
0x180002b18  xorps   xmm0, xmm0
0x180002b1b  xor     eax, eax
0x180002b1d  movups  xmmword ptr cs:stru_18001EB90.DebugInfo, xmm0
0x180002b24  movups  xmmword ptr cs:stru_18001EB90.OwningThread, xmm0
0x180002b2b  mov     cs:stru_18001EB90.SpinCount, rax
0x180002b32  xorps   xmm1, xmm1
0x180002b35  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x180002b3c  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x180002b43  mov     cs:Buf1.SpinCount, rax
0x180002b4a  mov     eax, 0C0000017h
0x180002b4f  jmp     short loc_180002B70
0x180002b51  xorps   xmm0, xmm0
0x180002b54  xor     eax, eax
0x180002b56  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x180002b5d  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x180002b64  mov     cs:Buf1.SpinCount, rax
0x180002b6b  mov     eax, 0C0000017h
0x180002b70  add     rsp, 20h
0x180002b74  pop     rbx
0x180002b75  retn
0x180016133  push    rbp
0x180016135  sub     rsp, 20h
0x180016139  mov     rbp, rdx
0x18001613c  mov     rax, [rcx]
0x18001613f  xor     ecx, ecx
0x180016141  cmp     dword ptr [rax], 0C0000017h
0x180016147  setz    cl
0x18001614a  mov     eax, ecx
0x18001614c  add     rsp, 20h
0x180016150  pop     rbp
0x180016151  retn
0x180016153  push    rbp
0x180016155  sub     rsp, 20h
0x180016159  mov     rbp, rdx
0x18001615c  mov     rax, [rcx]
0x18001615f  xor     ecx, ecx
0x180016161  cmp     dword ptr [rax], 0C0000017h
0x180016167  setz    cl
0x18001616a  mov     eax, ecx
0x18001616c  add     rsp, 20h
0x180016170  pop     rbp
0x180016171  retn
0x180016173  push    rbp
0x180016175  sub     rsp, 20h
0x180016179  mov     rbp, rdx
0x18001617c  mov     rax, [rcx]
0x18001617f  xor     ecx, ecx
0x180016181  cmp     dword ptr [rax], 0C0000017h
0x180016187  setz    cl
0x18001618a  mov     eax, ecx
0x18001618c  add     rsp, 20h
0x180016190  pop     rbp
0x180016191  retn
```
