# DllMain2

- ea: `0x18001ab7c`
- end: `0x18001abf9`
- name: `DllMain2`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180001050`

## callees

- `0x180001db8`
- `0x1800199e0`
- `0x18001ab7c`
- `0x180031010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18001abb2`
- `MSDART!MPDeleteCriticalSection` at `0x18001abb2`

## pseudocode

```c
__int64 __fastcall DllMain2(HMODULE a1, int a2)
{
  unsigned int v2; // ebx
  void *v3; // rdi

  v2 = 1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      g_hInstancePersistMain = a1;
      return (unsigned int)MSPersistInit();
    }
  }
  else
  {
    v3 = g_pcsDataConvert;
    if ( g_pcsDataConvert )
    {
      MPDeleteCriticalSection(g_pcsDataConvert);
      operator delete(v3);
    }
    try
    {
      g_pcsDataConvert = 0;
      ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    catch ( ... )
    {
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001ab7c  mov     [rsp+arg_0], rbx
0x18001ab81  push    rdi
0x18001ab82  sub     rsp, 20h
0x18001ab86  mov     ebx, 1
0x18001ab8b  test    edx, edx
0x18001ab8d  jz      short loc_18001ABA3
0x18001ab8f  cmp     edx, ebx
0x18001ab91  jnz     short loc_18001ABEB
0x18001ab93  mov     cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstancePersistMain
0x18001ab9a  call    ?MSPersistInit@@YAHXZ; MSPersistInit(void)
0x18001ab9f  mov     ebx, eax
0x18001aba1  jmp     short loc_18001ABEB
0x18001aba3  mov     rdi, cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA; CFoxCriticalSection * g_pcsDataConvert
0x18001abaa  test    rdi, rdi
0x18001abad  jz      short loc_18001ABC6
0x18001abaf  mov     rcx, rdi
0x18001abb2  call    cs:__imp_MPDeleteCriticalSection
0x18001abb9  nop     dword ptr [rax+rax+00h]
0x18001abbe  mov     rcx, rdi; void *
0x18001abc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001abc6  mov     cs:?g_pcsDataConvert@@3PEAVCFoxCriticalSection@@EA, 0; CFoxCriticalSection * g_pcsDataConvert
0x18001abd1  mov     rcx, cs:ppMalloc
0x18001abd8  mov     rax, [rcx]
0x18001abdb  mov     rax, [rax+10h]
0x18001abdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abe4  nop
0x18001abe5  jmp     short loc_18001ABEB
0x18001abe7  mov     ebx, [rsp+28h+arg_8]
0x18001abeb  mov     eax, ebx
0x18001abed  mov     rbx, [rsp+28h+arg_0]
0x18001abf2  add     rsp, 20h
0x18001abf6  pop     rdi
0x18001abf7  retn
```
