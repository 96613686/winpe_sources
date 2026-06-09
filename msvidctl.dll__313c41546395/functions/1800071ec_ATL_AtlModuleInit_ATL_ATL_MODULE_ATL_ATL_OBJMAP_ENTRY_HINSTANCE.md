# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x1800071ec`
- end: `0x1800073a7`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc34`

## callees

- `0x1800071ec`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800072d8`
- `KERNEL32!DeleteCriticalSection` at `0x1800072e5`
- `KERNEL32!DeleteCriticalSection` at `0x180007343`
- `KERNEL32!DeleteCriticalSection` at `0x1800072d8`
- `KERNEL32!DeleteCriticalSection` at `0x1800072e5`
- `KERNEL32!DeleteCriticalSection` at `0x180007343`
- `KERNEL32!InitializeCriticalSection` at `0x18000722a`
- `KERNEL32!InitializeCriticalSection` at `0x180007238`
- `KERNEL32!InitializeCriticalSection` at `0x180007246`
- `KERNEL32!InitializeCriticalSection` at `0x18000722a`
- `KERNEL32!InitializeCriticalSection` at `0x180007238`
- `KERNEL32!InitializeCriticalSection` at `0x180007246`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_18021CFF0 = (__int64)a2;
  hInstance = a3;
  hModule = a3;
  lpSource = a3;
  dword_18021CFF8 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_18021D030);
  InitializeCriticalSection(&stru_18021D058);
  qword_18021D088 = 0;
  byte_18021D090 = 1;
  dword_18021D0A0 = 0;
  dword_18021D0B0 = 0;
  qword_18021D0A8 = 0;
  qword_18021D0B8 = 0;
  v4 = qword_18021CFF0;
  if ( qword_18021CFF0 )
  {
    while ( *(_QWORD *)v4 )
    {
      LOBYTE(v3) = 1;
      (*(void (__fastcall **)(__int64))(v4 + 64))(v3);
      v5 = 72;
      v3 = 56;
      if ( (_DWORD)_Module == 176 )
        v5 = 56;
      v4 += v5;
    }
  }
  dword_18021D0C0 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800071ec  push    rbx
0x1800071ee  sub     rsp, 20h
0x1800071f2  mov     cs:qword_18021CFF0, rdx
0x1800071f9  mov     cs:hInstance, r8
0x180007200  mov     cs:hModule, r8
0x180007207  mov     cs:lpSource, r8
0x18000720e  mov     cs:dword_18021CFF8, 0
0x180007218  mov     cs:hHeap, 0
0x180007223  lea     rcx, Buf1; lpCriticalSection
0x18000722a  call    cs:__imp_InitializeCriticalSection
0x180007230  nop
0x180007231  lea     rcx, stru_18021D030; lpCriticalSection
0x180007238  call    cs:__imp_InitializeCriticalSection
0x18000723e  nop
0x18000723f  lea     rcx, stru_18021D058; lpCriticalSection
0x180007246  call    cs:__imp_InitializeCriticalSection
0x18000724c  nop
0x18000724d  mov     cs:qword_18021D088, 0
0x180007258  mov     cs:byte_18021D090, 1
0x18000725f  mov     cs:dword_18021D0A0, 0
0x180007269  mov     cs:dword_18021D0B0, 0
0x180007273  mov     cs:qword_18021D0A8, 0
0x18000727e  mov     cs:qword_18021D0B8, 0
0x180007289  mov     rbx, cs:qword_18021CFF0
0x180007290  test    rbx, rbx
0x180007293  jz      short loc_1800072C0
0x180007295  jmp     short loc_1800072BA
0x180007297  mov     cl, 1
0x180007299  mov     rax, [rbx+40h]
0x18000729d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072a2  mov     eax, 48h ; 'H'
0x1800072a7  lea     ecx, [rax-10h]
0x1800072aa  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x1800072b4  cmovz   eax, ecx
0x1800072b7  add     rbx, rax
0x1800072ba  cmp     qword ptr [rbx], 0
0x1800072be  jnz     short loc_180007297
0x1800072c0  mov     cs:dword_18021D0C0, 1
0x1800072ca  xor     eax, eax
0x1800072cc  jmp     loc_1800073A1
0x1800072d1  lea     rcx, stru_18021D030; lpCriticalSection
0x1800072d8  call    cs:__imp_DeleteCriticalSection
0x1800072de  lea     rcx, Buf1; lpCriticalSection
0x1800072e5  call    cs:__imp_DeleteCriticalSection
0x1800072eb  xorps   xmm0, xmm0
0x1800072ee  xor     eax, eax
0x1800072f0  movups  xmmword ptr cs:stru_18021D058.DebugInfo, xmm0
0x1800072f7  movups  xmmword ptr cs:stru_18021D058.OwningThread, xmm0
0x1800072fe  mov     cs:stru_18021D058.SpinCount, rax
0x180007305  xorps   xmm1, xmm1
0x180007308  movups  xmmword ptr cs:stru_18021D030.DebugInfo, xmm1
0x18000730f  movups  xmmword ptr cs:stru_18021D030.OwningThread, xmm1
0x180007316  mov     cs:stru_18021D030.SpinCount, rax
0x18000731d  xorps   xmm0, xmm0
0x180007320  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x180007327  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18000732e  mov     cs:Buf1.SpinCount, rax
0x180007335  mov     eax, 0C0000017h
0x18000733a  jmp     short loc_1800073A1
0x18000733c  lea     rcx, Buf1; lpCriticalSection
0x180007343  call    cs:__imp_DeleteCriticalSection
0x180007349  xorps   xmm0, xmm0
0x18000734c  xor     eax, eax
0x18000734e  movups  xmmword ptr cs:stru_18021D030.DebugInfo, xmm0
0x180007355  movups  xmmword ptr cs:stru_18021D030.OwningThread, xmm0
0x18000735c  mov     cs:stru_18021D030.SpinCount, rax
0x180007363  xorps   xmm1, xmm1
0x180007366  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x18000736d  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x180007374  mov     cs:Buf1.SpinCount, rax
0x18000737b  mov     eax, 0C0000017h
0x180007380  jmp     short loc_1800073A1
0x180007382  xorps   xmm0, xmm0
0x180007385  xor     eax, eax
0x180007387  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18000738e  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x180007395  mov     cs:Buf1.SpinCount, rax
0x18000739c  mov     eax, 0C0000017h
0x1800073a1  add     rsp, 20h
0x1800073a5  pop     rbx
0x1800073a6  retn
0x1800ef02e  push    rbp
0x1800ef030  sub     rsp, 20h
0x1800ef034  mov     rbp, rdx
0x1800ef037  mov     rax, [rcx]
0x1800ef03a  xor     ecx, ecx
0x1800ef03c  cmp     dword ptr [rax], 0C0000017h
0x1800ef042  setz    cl
0x1800ef045  mov     eax, ecx
0x1800ef047  add     rsp, 20h
0x1800ef04b  pop     rbp
0x1800ef04c  retn
0x1800ef04e  push    rbp
0x1800ef050  sub     rsp, 20h
0x1800ef054  mov     rbp, rdx
0x1800ef057  mov     rax, [rcx]
0x1800ef05a  xor     ecx, ecx
0x1800ef05c  cmp     dword ptr [rax], 0C0000017h
0x1800ef062  setz    cl
0x1800ef065  mov     eax, ecx
0x1800ef067  add     rsp, 20h
0x1800ef06b  pop     rbp
0x1800ef06c  retn
0x1800ef06e  push    rbp
0x1800ef070  sub     rsp, 20h
0x1800ef074  mov     rbp, rdx
0x1800ef077  mov     rax, [rcx]
0x1800ef07a  xor     ecx, ecx
0x1800ef07c  cmp     dword ptr [rax], 0C0000017h
0x1800ef082  setz    cl
0x1800ef085  mov     eax, ecx
0x1800ef087  add     rsp, 20h
0x1800ef08b  pop     rbp
0x1800ef08c  retn
```
