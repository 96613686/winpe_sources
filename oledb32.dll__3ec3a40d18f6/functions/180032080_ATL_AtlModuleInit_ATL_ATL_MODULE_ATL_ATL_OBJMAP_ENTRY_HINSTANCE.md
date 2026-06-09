# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x180032080`
- end: `0x180032138`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011370`

## callees

- `0x180032080`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800320f9`
- `KERNEL32!DeleteCriticalSection` at `0x180032103`
- `KERNEL32!DeleteCriticalSection` at `0x180032119`
- `KERNEL32!DeleteCriticalSection` at `0x1800320f9`
- `KERNEL32!DeleteCriticalSection` at `0x180032103`
- `KERNEL32!DeleteCriticalSection` at `0x180032119`
- `KERNEL32!InitializeCriticalSection` at `0x1800320cc`
- `KERNEL32!InitializeCriticalSection` at `0x1800320d7`
- `KERNEL32!InitializeCriticalSection` at `0x1800320e5`
- `KERNEL32!InitializeCriticalSection` at `0x1800320cc`
- `KERNEL32!InitializeCriticalSection` at `0x1800320d7`
- `KERNEL32!InitializeCriticalSection` at `0x1800320e5`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  if ( !a1 || *(_DWORD *)a1 < 0xB0u )
    return 2147942487LL;
  *((_QWORD *)a1 + 4) = &off_1800BC150;
  *((_QWORD *)a1 + 2) = a3;
  *((_QWORD *)a1 + 3) = a3;
  *((_QWORD *)a1 + 1) = a3;
  *((_DWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 6) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  return 0;
}

```

## disassembly

```asm
0x180032080  mov     [rsp+arg_0], rcx
0x180032085  push    rbx
0x180032086  sub     rsp, 20h
0x18003208a  mov     rbx, rcx
0x18003208d  test    rcx, rcx
0x180032090  jz      loc_18003212D
0x180032096  cmp     dword ptr [rcx], 0B0h
0x18003209c  jb      loc_18003212D
0x1800320a2  lea     rax, off_1800BC150
0x1800320a9  mov     [rcx+20h], rax
0x1800320ad  mov     [rcx+10h], r8
0x1800320b1  mov     [rcx+18h], r8
0x1800320b5  mov     [rcx+8], r8
0x1800320b9  mov     dword ptr [rcx+28h], 0
0x1800320c0  mov     qword ptr [rcx+30h], 0
0x1800320c8  add     rcx, 38h ; '8'; lpCriticalSection
0x1800320cc  call    cs:__imp_InitializeCriticalSection
0x1800320d2  nop
0x1800320d3  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800320d7  call    cs:__imp_InitializeCriticalSection
0x1800320dd  nop
0x1800320de  lea     rcx, [rbx+88h]; lpCriticalSection
0x1800320e5  call    cs:__imp_InitializeCriticalSection
0x1800320eb  nop
0x1800320ec  xor     eax, eax
0x1800320ee  jmp     short loc_180032132
0x1800320f0  mov     rbx, [rsp+28h+arg_0]
0x1800320f5  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800320f9  call    cs:__imp_DeleteCriticalSection
0x1800320ff  lea     rcx, [rbx+60h]; lpCriticalSection
0x180032103  call    cs:__imp_DeleteCriticalSection
0x180032109  mov     eax, 8007000Eh
0x18003210e  jmp     short loc_180032132
0x180032110  mov     rcx, [rsp+28h+arg_0]
0x180032115  add     rcx, 38h ; '8'; lpCriticalSection
0x180032119  call    cs:__imp_DeleteCriticalSection
0x18003211f  mov     eax, 8007000Eh
0x180032124  jmp     short loc_180032132
0x180032126  mov     eax, 8007000Eh
0x18003212b  jmp     short loc_180032132
0x18003212d  mov     eax, 80070057h
0x180032132  add     rsp, 20h
0x180032136  pop     rbx
0x180032137  retn
0x180080afa  push    rbp
0x180080afc  sub     rsp, 20h
0x180080b00  mov     rbp, rdx
0x180080b03  mov     rax, [rcx]
0x180080b06  xor     ecx, ecx
0x180080b08  cmp     dword ptr [rax], 0C0000017h
0x180080b0e  setz    cl
0x180080b11  mov     eax, ecx
0x180080b13  add     rsp, 20h
0x180080b17  pop     rbp
0x180080b18  retn
0x180080b1a  push    rbp
0x180080b1c  sub     rsp, 20h
0x180080b20  mov     rbp, rdx
0x180080b23  mov     rax, [rcx]
0x180080b26  xor     ecx, ecx
0x180080b28  cmp     dword ptr [rax], 0C0000017h
0x180080b2e  setz    cl
0x180080b31  mov     eax, ecx
0x180080b33  add     rsp, 20h
0x180080b37  pop     rbp
0x180080b38  retn
0x180080b3a  push    rbp
0x180080b3c  sub     rsp, 20h
0x180080b40  mov     rbp, rdx
0x180080b43  mov     rax, [rcx]
0x180080b46  xor     ecx, ecx
0x180080b48  cmp     dword ptr [rax], 0C0000017h
0x180080b4e  setz    cl
0x180080b51  mov     eax, ecx
0x180080b53  add     rsp, 20h
0x180080b57  pop     rbp
0x180080b58  retn
```
