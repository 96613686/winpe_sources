# CCabEnum::StartEnum(void)

- ea: `0x180008a74`
- end: `0x180008af1`
- name: `?StartEnum@CCabEnum@@IEAAHXZ`
- size: `125`
- prototype: `__int64 __fastcall(CCabEnum *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008898`

## callees

- `0x180008a74`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x180008ad8`
- `Cabinet!__imp_FDICreate` at `0x180008ad8`

## pseudocode

```c
_BOOL8 __fastcall CCabEnum::StartEnum(CCabEnum *this)
{
  HFDI v3; // rax

  if ( *(_QWORD *)this )
    return 0;
  v3 = FDICreate(
         CCabEnum::CabAlloc,
         (PFNFREE)CCabEnum::CabFree,
         (PFNOPEN)CCabEnum::CabOpen,
         (PFNREAD)CCabEnum::CabRead,
         CCabEnum::CabWrite,
         CCabEnum::CabClose,
         CCabEnum::CabSeek,
         1,
         (PERF)((char *)this + 8));
  *(_QWORD *)this = v3;
  return v3 != 0;
}

```

## disassembly

```asm
0x180008a74  push    rbx
0x180008a76  sub     rsp, 50h
0x180008a7a  cmp     qword ptr [rcx], 0
0x180008a7e  mov     rbx, rcx
0x180008a81  jz      short loc_180008A87
0x180008a83  xor     eax, eax
0x180008a85  jmp     short loc_180008AEB
0x180008a87  lea     rax, [rcx+8]
0x180008a8b  mov     [rsp+58h+perf], rax; perf
0x180008a90  lea     r9, ?CabRead@CCabEnum@@KAI_JPEAXI@Z; pfnread
0x180008a97  mov     [rsp+58h+cpuType], 1; cpuType
0x180008a9f  lea     rax, ?CabSeek@CCabEnum@@KAJ_JJH@Z; CCabEnum::CabSeek(__int64,long,int)
0x180008aa6  mov     [rsp+58h+pfnseek], rax; pfnseek
0x180008aab  lea     r8, ?CabOpen@CCabEnum@@KA_JPEADHH@Z; pfnopen
0x180008ab2  lea     rax, ?CabClose@CCabEnum@@KAH_J@Z; CCabEnum::CabClose(__int64)
0x180008ab9  mov     [rsp+58h+pfnclose], rax; pfnclose
0x180008abe  lea     rdx, ?CabFree@CCabEnum@@KAXPEAX@Z; pfnfree
0x180008ac5  lea     rax, ?CabWrite@CCabEnum@@KAI_JPEAXI@Z; CCabEnum::CabWrite(__int64,void *,uint)
0x180008acc  lea     rcx, ?CabAlloc@CCabEnum@@KAPEAXK@Z; pfnalloc
0x180008ad3  mov     [rsp+58h+pfnwrite], rax; pfnwrite
0x180008ad8  call    cs:__imp_FDICreate
0x180008ade  xor     ecx, ecx
0x180008ae0  mov     [rbx], rax
0x180008ae3  test    rax, rax
0x180008ae6  setnz   cl
0x180008ae9  mov     eax, ecx
0x180008aeb  add     rsp, 50h
0x180008aef  pop     rbx
0x180008af0  retn
```
