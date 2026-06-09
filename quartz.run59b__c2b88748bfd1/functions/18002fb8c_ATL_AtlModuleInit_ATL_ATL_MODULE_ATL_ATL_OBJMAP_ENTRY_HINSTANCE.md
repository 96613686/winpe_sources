# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x18002fb8c`
- end: `0x18002fc63`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180021470`

## callees

- `0x18002fb8c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002fc18`
- `KERNEL32!DeleteCriticalSection` at `0x18002fc2b`
- `KERNEL32!DeleteCriticalSection` at `0x18002fc45`
- `KERNEL32!DeleteCriticalSection` at `0x18002fc18`
- `KERNEL32!DeleteCriticalSection` at `0x18002fc2b`
- `KERNEL32!DeleteCriticalSection` at `0x18002fc45`
- `KERNEL32!InitializeCriticalSection` at `0x18002fbd8`
- `KERNEL32!InitializeCriticalSection` at `0x18002fbec`
- `KERNEL32!InitializeCriticalSection` at `0x18002fc00`
- `KERNEL32!InitializeCriticalSection` at `0x18002fbd8`
- `KERNEL32!InitializeCriticalSection` at `0x18002fbec`
- `KERNEL32!InitializeCriticalSection` at `0x18002fc00`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, __int64 a3)
{
  if ( _Module < 0xB0u )
    return 2147942487LL;
  qword_18019E7E0 = 0;
  qword_18019E7D0 = a3;
  qword_18019E7D8 = a3;
  *(_QWORD *)byte_18019E7C8 = a3;
  dword_18019E7E8 = 0;
  hHeap = 0;
  InitializeCriticalSection(&stru_18019E7F8);
  InitializeCriticalSection(&stru_18019E820);
  InitializeCriticalSection(&stru_18019E848);
  return 0;
}

```

## disassembly

```asm
0x18002fb8c  sub     rsp, 28h
0x18002fb90  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x18002fb9a  jnb     short loc_18002FBA6
0x18002fb9c  mov     eax, 80070057h
0x18002fba1  jmp     loc_18002FC5D
0x18002fba6  xor     eax, eax
0x18002fba8  mov     cs:qword_18019E7E0, rax
0x18002fbaf  mov     cs:qword_18019E7D0, r8
0x18002fbb6  mov     cs:qword_18019E7D8, r8
0x18002fbbd  mov     qword ptr cs:byte_18019E7C8, r8
0x18002fbc4  mov     cs:dword_18019E7E8, eax
0x18002fbca  mov     cs:hHeap, rax
0x18002fbd1  lea     rcx, stru_18019E7F8; lpCriticalSection
0x18002fbd8  call    cs:__imp_InitializeCriticalSection
0x18002fbdf  nop     dword ptr [rax+rax+00h]
0x18002fbe4  nop
0x18002fbe5  lea     rcx, stru_18019E820; lpCriticalSection
0x18002fbec  call    cs:__imp_InitializeCriticalSection
0x18002fbf3  nop     dword ptr [rax+rax+00h]
0x18002fbf8  nop
0x18002fbf9  lea     rcx, stru_18019E848; lpCriticalSection
0x18002fc00  call    cs:__imp_InitializeCriticalSection
0x18002fc07  nop     dword ptr [rax+rax+00h]
0x18002fc0c  nop
0x18002fc0d  xor     eax, eax
0x18002fc0f  jmp     short loc_18002FC5D
0x18002fc11  lea     rcx, stru_18019E7F8; lpCriticalSection
0x18002fc18  call    cs:__imp_DeleteCriticalSection
0x18002fc1f  nop     dword ptr [rax+rax+00h]
0x18002fc24  lea     rcx, stru_18019E820; lpCriticalSection
0x18002fc2b  call    cs:__imp_DeleteCriticalSection
0x18002fc32  nop     dword ptr [rax+rax+00h]
0x18002fc37  mov     eax, 8007000Eh
0x18002fc3c  jmp     short loc_18002FC5D
0x18002fc3e  lea     rcx, stru_18019E7F8; lpCriticalSection
0x18002fc45  call    cs:__imp_DeleteCriticalSection
0x18002fc4c  nop     dword ptr [rax+rax+00h]
0x18002fc51  mov     eax, 8007000Eh
0x18002fc56  jmp     short loc_18002FC5D
0x18002fc58  mov     eax, 8007000Eh
0x18002fc5d  add     rsp, 28h
0x18002fc61  retn
0x18015bd30  push    rbp
0x18015bd32  sub     rsp, 20h
0x18015bd36  mov     rbp, rdx
0x18015bd39  mov     rax, [rcx]
0x18015bd3c  xor     ecx, ecx
0x18015bd3e  cmp     dword ptr [rax], 0C0000017h
0x18015bd44  setz    cl
0x18015bd47  mov     eax, ecx
0x18015bd49  add     rsp, 20h
0x18015bd4d  pop     rbp
0x18015bd4e  retn
0x18015bd50  push    rbp
0x18015bd52  sub     rsp, 20h
0x18015bd56  mov     rbp, rdx
0x18015bd59  mov     rax, [rcx]
0x18015bd5c  xor     ecx, ecx
0x18015bd5e  cmp     dword ptr [rax], 0C0000017h
0x18015bd64  setz    cl
0x18015bd67  mov     eax, ecx
0x18015bd69  add     rsp, 20h
0x18015bd6d  pop     rbp
0x18015bd6e  retn
0x18015bd70  push    rbp
0x18015bd72  sub     rsp, 20h
0x18015bd76  mov     rbp, rdx
0x18015bd79  mov     rax, [rcx]
0x18015bd7c  xor     ecx, ecx
0x18015bd7e  cmp     dword ptr [rax], 0C0000017h
0x18015bd84  setz    cl
0x18015bd87  mov     eax, ecx
0x18015bd89  add     rsp, 20h
0x18015bd8d  pop     rbp
0x18015bd8e  retn
```
