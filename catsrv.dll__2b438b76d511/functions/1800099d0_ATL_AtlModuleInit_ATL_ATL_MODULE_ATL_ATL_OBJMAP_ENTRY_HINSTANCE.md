# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x1800099d0`
- end: `0x180009b6b`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005fc0`
- `0x180006770`
- `0x180006fc0`

## callees

- `0x1800099d0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009aba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ac4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009aba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009ac4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b15`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009a14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009a1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009a2d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009a14`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009a1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009a2d`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax

  if ( !a1 )
    return 2147942487LL;
  *((_QWORD *)a1 + 4) = a2;
  *((_QWORD *)a1 + 2) = a3;
  *((_QWORD *)a1 + 3) = a3;
  *((_QWORD *)a1 + 1) = a3;
  *((_DWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 6) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  *((_QWORD *)a1 + 23) = 0;
  *((_BYTE *)a1 + 192) = 1;
  *((_DWORD *)a1 + 52) = 0;
  *((_DWORD *)a1 + 56) = 0;
  *((_QWORD *)a1 + 27) = 0;
  *((_QWORD *)a1 + 29) = 0;
  v6 = *((_QWORD *)a1 + 4);
  if ( v6 )
  {
    while ( *(_QWORD *)v6 )
    {
      LOBYTE(v5) = 1;
      (*(void (__fastcall **)(__int64))(v6 + 64))(v5);
      v7 = 56;
      v5 = 72;
      if ( *(_DWORD *)a1 != 176 )
        v7 = 72;
      v6 += v7;
    }
  }
  *((_DWORD *)a1 + 60) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800099d0  mov     [rsp+arg_8], rbx
0x1800099d5  mov     [rsp+arg_0], rcx
0x1800099da  push    rdi
0x1800099db  sub     rsp, 20h
0x1800099df  mov     rbx, rcx
0x1800099e2  test    rcx, rcx
0x1800099e5  jnz     short loc_1800099F1
0x1800099e7  mov     eax, 80070057h
0x1800099ec  jmp     loc_180009B60
0x1800099f1  mov     [rcx+20h], rdx
0x1800099f5  mov     [rcx+10h], r8
0x1800099f9  mov     [rcx+18h], r8
0x1800099fd  mov     [rcx+8], r8
0x180009a01  mov     dword ptr [rcx+28h], 0
0x180009a08  mov     qword ptr [rcx+30h], 0
0x180009a10  add     rcx, 38h ; '8'; lpCriticalSection
0x180009a14  call    cs:__imp_InitializeCriticalSection
0x180009a1a  nop
0x180009a1b  lea     rcx, [rbx+60h]; lpCriticalSection
0x180009a1f  call    cs:__imp_InitializeCriticalSection
0x180009a25  nop
0x180009a26  lea     rcx, [rbx+88h]; lpCriticalSection
0x180009a2d  call    cs:__imp_InitializeCriticalSection
0x180009a33  nop
0x180009a34  mov     qword ptr [rbx+0B8h], 0
0x180009a3f  mov     byte ptr [rbx+0C0h], 1
0x180009a46  mov     dword ptr [rbx+0D0h], 0
0x180009a50  mov     dword ptr [rbx+0E0h], 0
0x180009a5a  mov     qword ptr [rbx+0D8h], 0
0x180009a65  mov     qword ptr [rbx+0E8h], 0
0x180009a70  mov     rdi, [rbx+20h]
0x180009a74  test    rdi, rdi
0x180009a77  jz      short loc_180009AA0
0x180009a79  jmp     short loc_180009A9A
0x180009a7b  mov     cl, 1
0x180009a7d  mov     rax, [rdi+40h]
0x180009a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a86  mov     eax, 38h ; '8'
0x180009a8b  lea     ecx, [rax+10h]
0x180009a8e  cmp     dword ptr [rbx], 0B0h
0x180009a94  cmovnz  eax, ecx
0x180009a97  add     rdi, rax
0x180009a9a  cmp     qword ptr [rdi], 0
0x180009a9e  jnz     short loc_180009A7B
0x180009aa0  mov     dword ptr [rbx+0F0h], 1
0x180009aaa  xor     eax, eax
0x180009aac  jmp     loc_180009B60
0x180009ab1  mov     rbx, [rsp+28h+arg_0]
0x180009ab6  lea     rcx, [rbx+60h]; lpCriticalSection
0x180009aba  call    cs:__imp_DeleteCriticalSection
0x180009ac0  lea     rcx, [rbx+38h]; lpCriticalSection
0x180009ac4  call    cs:__imp_DeleteCriticalSection
0x180009aca  xorps   xmm0, xmm0
0x180009acd  xor     eax, eax
0x180009acf  movups  xmmword ptr [rbx+88h], xmm0
0x180009ad6  movups  xmmword ptr [rbx+98h], xmm0
0x180009add  mov     [rbx+0A8h], rax
0x180009ae4  xorps   xmm0, xmm0
0x180009ae7  movups  xmmword ptr [rbx+60h], xmm0
0x180009aeb  movups  xmmword ptr [rbx+70h], xmm0
0x180009aef  mov     [rbx+80h], rax
0x180009af6  xorps   xmm0, xmm0
0x180009af9  movups  xmmword ptr [rbx+38h], xmm0
0x180009afd  movups  xmmword ptr [rbx+48h], xmm0
0x180009b01  mov     [rbx+58h], rax
0x180009b05  mov     eax, 0C0000017h
0x180009b0a  jmp     short loc_180009B60
0x180009b0c  mov     rbx, [rsp+28h+arg_0]
0x180009b11  lea     rcx, [rbx+38h]; lpCriticalSection
0x180009b15  call    cs:__imp_DeleteCriticalSection
0x180009b1b  xorps   xmm0, xmm0
0x180009b1e  xor     eax, eax
0x180009b20  movups  xmmword ptr [rbx+60h], xmm0
0x180009b24  movups  xmmword ptr [rbx+70h], xmm0
0x180009b28  mov     [rbx+80h], rax
0x180009b2f  xorps   xmm0, xmm0
0x180009b32  movups  xmmword ptr [rbx+38h], xmm0
0x180009b36  movups  xmmword ptr [rbx+48h], xmm0
0x180009b3a  mov     [rbx+58h], rax
0x180009b3e  mov     eax, 0C0000017h
0x180009b43  jmp     short loc_180009B60
0x180009b45  mov     rax, [rsp+28h+arg_0]
0x180009b4a  xorps   xmm0, xmm0
0x180009b4d  xor     ecx, ecx
0x180009b4f  movups  xmmword ptr [rax+38h], xmm0
0x180009b53  movups  xmmword ptr [rax+48h], xmm0
0x180009b57  mov     [rax+58h], rcx
0x180009b5b  mov     eax, 0C0000017h
0x180009b60  mov     rbx, [rsp+28h+arg_8]
0x180009b65  add     rsp, 20h
0x180009b69  pop     rdi
0x180009b6a  retn
0x1800557cf  push    rbp
0x1800557d1  sub     rsp, 20h
0x1800557d5  mov     rbp, rdx
0x1800557d8  mov     rax, [rcx]
0x1800557db  xor     ecx, ecx
0x1800557dd  cmp     dword ptr [rax], 0C0000017h
0x1800557e3  setz    cl
0x1800557e6  mov     eax, ecx
0x1800557e8  add     rsp, 20h
0x1800557ec  pop     rbp
0x1800557ed  retn
0x1800557ef  push    rbp
0x1800557f1  sub     rsp, 20h
0x1800557f5  mov     rbp, rdx
0x1800557f8  mov     rax, [rcx]
0x1800557fb  xor     ecx, ecx
0x1800557fd  cmp     dword ptr [rax], 0C0000017h
0x180055803  setz    cl
0x180055806  mov     eax, ecx
0x180055808  add     rsp, 20h
0x18005580c  pop     rbp
0x18005580d  retn
0x18005580f  push    rbp
0x180055811  sub     rsp, 20h
0x180055815  mov     rbp, rdx
0x180055818  mov     rax, [rcx]
0x18005581b  xor     ecx, ecx
0x18005581d  cmp     dword ptr [rax], 0C0000017h
0x180055823  setz    cl
0x180055826  mov     eax, ecx
0x180055828  add     rsp, 20h
0x18005582c  pop     rbp
0x18005582d  retn
```
