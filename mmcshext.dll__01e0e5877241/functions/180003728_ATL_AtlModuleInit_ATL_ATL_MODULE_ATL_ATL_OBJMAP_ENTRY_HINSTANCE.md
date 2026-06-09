# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x180003728`
- end: `0x1800038ea`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800066f4`

## callees

- `0x180003728`
- `0x18000b010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000376d`
- `KERNEL32!InitializeCriticalSection` at `0x18000377b`
- `KERNEL32!InitializeCriticalSection` at `0x180003789`
- `KERNEL32!InitializeCriticalSection` at `0x18000376d`
- `KERNEL32!InitializeCriticalSection` at `0x18000377b`
- `KERNEL32!InitializeCriticalSection` at `0x180003789`
- `KERNEL32!DeleteCriticalSection` at `0x18000381b`
- `KERNEL32!DeleteCriticalSection` at `0x180003828`
- `KERNEL32!DeleteCriticalSection` at `0x180003886`
- `KERNEL32!DeleteCriticalSection` at `0x18000381b`
- `KERNEL32!DeleteCriticalSection` at `0x180003828`
- `KERNEL32!DeleteCriticalSection` at `0x180003886`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_180012EE0 = (__int64)&off_180012000;
  qword_180012ED0 = (__int64)a3;
  qword_180012ED8 = (__int64)a3;
  hModule = a3;
  dword_180012EE8 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_180012F20);
  InitializeCriticalSection(&CriticalSection);
  qword_180012F78 = 0;
  byte_180012F80 = 1;
  dword_180012F90 = 0;
  dword_180012FA0 = 0;
  qword_180012F98 = 0;
  qword_180012FA8 = 0;
  v4 = qword_180012EE0;
  if ( qword_180012EE0 )
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
  dword_180012FB0 = 1;
  return 0;
}

```

## disassembly

```asm
0x180003728  push    rbx
0x18000372a  sub     rsp, 20h
0x18000372e  lea     rax, off_180012000
0x180003735  mov     cs:qword_180012EE0, rax
0x18000373c  mov     cs:qword_180012ED0, r8
0x180003743  mov     cs:qword_180012ED8, r8
0x18000374a  mov     cs:hModule, r8
0x180003751  mov     cs:dword_180012EE8, 0
0x18000375b  mov     cs:hHeap, 0
0x180003766  lea     rcx, Buf1; lpCriticalSection
0x18000376d  call    cs:__imp_InitializeCriticalSection
0x180003773  nop
0x180003774  lea     rcx, stru_180012F20; lpCriticalSection
0x18000377b  call    cs:__imp_InitializeCriticalSection
0x180003781  nop
0x180003782  lea     rcx, CriticalSection; lpCriticalSection
0x180003789  call    cs:__imp_InitializeCriticalSection
0x18000378f  nop
0x180003790  mov     cs:qword_180012F78, 0
0x18000379b  mov     cs:byte_180012F80, 1
0x1800037a2  mov     cs:dword_180012F90, 0
0x1800037ac  mov     cs:dword_180012FA0, 0
0x1800037b6  mov     cs:qword_180012F98, 0
0x1800037c1  mov     cs:qword_180012FA8, 0
0x1800037cc  mov     rbx, cs:qword_180012EE0
0x1800037d3  test    rbx, rbx
0x1800037d6  jz      short loc_180003803
0x1800037d8  jmp     short loc_1800037FD
0x1800037da  mov     cl, 1
0x1800037dc  mov     rax, [rbx+40h]
0x1800037e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e5  mov     eax, 48h ; 'H'
0x1800037ea  lea     ecx, [rax-10h]
0x1800037ed  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x1800037f7  cmovz   eax, ecx
0x1800037fa  add     rbx, rax
0x1800037fd  cmp     qword ptr [rbx], 0
0x180003801  jnz     short loc_1800037DA
0x180003803  mov     cs:dword_180012FB0, 1
0x18000380d  xor     eax, eax
0x18000380f  jmp     loc_1800038E4
0x180003814  lea     rcx, stru_180012F20; lpCriticalSection
0x18000381b  call    cs:__imp_DeleteCriticalSection
0x180003821  lea     rcx, Buf1; lpCriticalSection
0x180003828  call    cs:__imp_DeleteCriticalSection
0x18000382e  xorps   xmm0, xmm0
0x180003831  xor     eax, eax
0x180003833  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x18000383a  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x180003841  mov     cs:CriticalSection.SpinCount, rax
0x180003848  xorps   xmm1, xmm1
0x18000384b  movups  xmmword ptr cs:stru_180012F20.DebugInfo, xmm1
0x180003852  movups  xmmword ptr cs:stru_180012F20.OwningThread, xmm1
0x180003859  mov     cs:stru_180012F20.SpinCount, rax
0x180003860  xorps   xmm0, xmm0
0x180003863  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18000386a  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x180003871  mov     cs:Buf1.SpinCount, rax
0x180003878  mov     eax, 0C0000017h
0x18000387d  jmp     short loc_1800038E4
0x18000387f  lea     rcx, Buf1; lpCriticalSection
0x180003886  call    cs:__imp_DeleteCriticalSection
0x18000388c  xorps   xmm0, xmm0
0x18000388f  xor     eax, eax
0x180003891  movups  xmmword ptr cs:stru_180012F20.DebugInfo, xmm0
0x180003898  movups  xmmword ptr cs:stru_180012F20.OwningThread, xmm0
0x18000389f  mov     cs:stru_180012F20.SpinCount, rax
0x1800038a6  xorps   xmm1, xmm1
0x1800038a9  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x1800038b0  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x1800038b7  mov     cs:Buf1.SpinCount, rax
0x1800038be  mov     eax, 0C0000017h
0x1800038c3  jmp     short loc_1800038E4
0x1800038c5  xorps   xmm0, xmm0
0x1800038c8  xor     eax, eax
0x1800038ca  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x1800038d1  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x1800038d8  mov     cs:Buf1.SpinCount, rax
0x1800038df  mov     eax, 0C0000017h
0x1800038e4  add     rsp, 20h
0x1800038e8  pop     rbx
0x1800038e9  retn
0x18000aa6a  push    rbp
0x18000aa6c  sub     rsp, 20h
0x18000aa70  mov     rbp, rdx
0x18000aa73  mov     rax, [rcx]
0x18000aa76  xor     ecx, ecx
0x18000aa78  cmp     dword ptr [rax], 0C0000017h
0x18000aa7e  setz    cl
0x18000aa81  mov     eax, ecx
0x18000aa83  add     rsp, 20h
0x18000aa87  pop     rbp
0x18000aa88  retn
0x18000aa8a  push    rbp
0x18000aa8c  sub     rsp, 20h
0x18000aa90  mov     rbp, rdx
0x18000aa93  mov     rax, [rcx]
0x18000aa96  xor     ecx, ecx
0x18000aa98  cmp     dword ptr [rax], 0C0000017h
0x18000aa9e  setz    cl
0x18000aaa1  mov     eax, ecx
0x18000aaa3  add     rsp, 20h
0x18000aaa7  pop     rbp
0x18000aaa8  retn
0x18000aaaa  push    rbp
0x18000aaac  sub     rsp, 20h
0x18000aab0  mov     rbp, rdx
0x18000aab3  mov     rax, [rcx]
0x18000aab6  xor     ecx, ecx
0x18000aab8  cmp     dword ptr [rax], 0C0000017h
0x18000aabe  setz    cl
0x18000aac1  mov     eax, ecx
0x18000aac3  add     rsp, 20h
0x18000aac7  pop     rbp
0x18000aac8  retn
```
