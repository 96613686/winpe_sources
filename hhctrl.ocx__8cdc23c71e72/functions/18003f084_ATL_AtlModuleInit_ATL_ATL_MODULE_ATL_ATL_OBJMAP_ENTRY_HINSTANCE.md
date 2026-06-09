# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x18003f084`
- end: `0x18003f226`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180041920`

## callees

- `0x18003f084`
- `0x180078010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18003f0cf`
- `KERNEL32!InitializeCriticalSection` at `0x18003f0da`
- `KERNEL32!InitializeCriticalSection` at `0x18003f0e8`
- `KERNEL32!InitializeCriticalSection` at `0x18003f0cf`
- `KERNEL32!InitializeCriticalSection` at `0x18003f0da`
- `KERNEL32!InitializeCriticalSection` at `0x18003f0e8`
- `KERNEL32!DeleteCriticalSection` at `0x18003f175`
- `KERNEL32!DeleteCriticalSection` at `0x18003f17f`
- `KERNEL32!DeleteCriticalSection` at `0x18003f1d0`
- `KERNEL32!DeleteCriticalSection` at `0x18003f175`
- `KERNEL32!DeleteCriticalSection` at `0x18003f17f`
- `KERNEL32!DeleteCriticalSection` at `0x18003f1d0`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax

  if ( !a1 )
    return 2147942487LL;
  *((_QWORD *)a1 + 4) = &off_18008B1B0;
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
0x18003f084  mov     [rsp+arg_8], rbx
0x18003f089  mov     [rsp+arg_0], rcx
0x18003f08e  push    rdi
0x18003f08f  sub     rsp, 20h
0x18003f093  mov     rbx, rcx
0x18003f096  test    rcx, rcx
0x18003f099  jnz     short loc_18003F0A5
0x18003f09b  mov     eax, 80070057h
0x18003f0a0  jmp     loc_18003F21B
0x18003f0a5  lea     rax, off_18008B1B0
0x18003f0ac  mov     [rcx+20h], rax
0x18003f0b0  mov     [rcx+10h], r8
0x18003f0b4  mov     [rcx+18h], r8
0x18003f0b8  mov     [rcx+8], r8
0x18003f0bc  mov     dword ptr [rcx+28h], 0
0x18003f0c3  mov     qword ptr [rcx+30h], 0
0x18003f0cb  add     rcx, 38h ; '8'; lpCriticalSection
0x18003f0cf  call    cs:__imp_InitializeCriticalSection
0x18003f0d5  nop
0x18003f0d6  lea     rcx, [rbx+60h]; lpCriticalSection
0x18003f0da  call    cs:__imp_InitializeCriticalSection
0x18003f0e0  nop
0x18003f0e1  lea     rcx, [rbx+88h]; lpCriticalSection
0x18003f0e8  call    cs:__imp_InitializeCriticalSection
0x18003f0ee  nop
0x18003f0ef  mov     qword ptr [rbx+0B8h], 0
0x18003f0fa  mov     byte ptr [rbx+0C0h], 1
0x18003f101  mov     dword ptr [rbx+0D0h], 0
0x18003f10b  mov     dword ptr [rbx+0E0h], 0
0x18003f115  mov     qword ptr [rbx+0D8h], 0
0x18003f120  mov     qword ptr [rbx+0E8h], 0
0x18003f12b  mov     rdi, [rbx+20h]
0x18003f12f  test    rdi, rdi
0x18003f132  jz      short loc_18003F15B
0x18003f134  jmp     short loc_18003F155
0x18003f136  mov     cl, 1
0x18003f138  mov     rax, [rdi+40h]
0x18003f13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f141  mov     eax, 38h ; '8'
0x18003f146  lea     ecx, [rax+10h]
0x18003f149  cmp     dword ptr [rbx], 0B0h
0x18003f14f  cmovnz  eax, ecx
0x18003f152  add     rdi, rax
0x18003f155  cmp     qword ptr [rdi], 0
0x18003f159  jnz     short loc_18003F136
0x18003f15b  mov     dword ptr [rbx+0F0h], 1
0x18003f165  xor     eax, eax
0x18003f167  jmp     loc_18003F21B
0x18003f16c  mov     rbx, [rsp+28h+arg_0]
0x18003f171  lea     rcx, [rbx+60h]; lpCriticalSection
0x18003f175  call    cs:__imp_DeleteCriticalSection
0x18003f17b  lea     rcx, [rbx+38h]; lpCriticalSection
0x18003f17f  call    cs:__imp_DeleteCriticalSection
0x18003f185  xorps   xmm0, xmm0
0x18003f188  xor     eax, eax
0x18003f18a  movups  xmmword ptr [rbx+88h], xmm0
0x18003f191  movups  xmmword ptr [rbx+98h], xmm0
0x18003f198  mov     [rbx+0A8h], rax
0x18003f19f  xorps   xmm0, xmm0
0x18003f1a2  movups  xmmword ptr [rbx+60h], xmm0
0x18003f1a6  movups  xmmword ptr [rbx+70h], xmm0
0x18003f1aa  mov     [rbx+80h], rax
0x18003f1b1  xorps   xmm0, xmm0
0x18003f1b4  movups  xmmword ptr [rbx+38h], xmm0
0x18003f1b8  movups  xmmword ptr [rbx+48h], xmm0
0x18003f1bc  mov     [rbx+58h], rax
0x18003f1c0  mov     eax, 0C0000017h
0x18003f1c5  jmp     short loc_18003F21B
0x18003f1c7  mov     rbx, [rsp+28h+arg_0]
0x18003f1cc  lea     rcx, [rbx+38h]; lpCriticalSection
0x18003f1d0  call    cs:__imp_DeleteCriticalSection
0x18003f1d6  xorps   xmm0, xmm0
0x18003f1d9  xor     eax, eax
0x18003f1db  movups  xmmword ptr [rbx+60h], xmm0
0x18003f1df  movups  xmmword ptr [rbx+70h], xmm0
0x18003f1e3  mov     [rbx+80h], rax
0x18003f1ea  xorps   xmm0, xmm0
0x18003f1ed  movups  xmmword ptr [rbx+38h], xmm0
0x18003f1f1  movups  xmmword ptr [rbx+48h], xmm0
0x18003f1f5  mov     [rbx+58h], rax
0x18003f1f9  mov     eax, 0C0000017h
0x18003f1fe  jmp     short loc_18003F21B
0x18003f200  mov     rax, [rsp+28h+arg_0]
0x18003f205  xorps   xmm0, xmm0
0x18003f208  xor     ecx, ecx
0x18003f20a  movups  xmmword ptr [rax+38h], xmm0
0x18003f20e  movups  xmmword ptr [rax+48h], xmm0
0x18003f212  mov     [rax+58h], rcx
0x18003f216  mov     eax, 0C0000017h
0x18003f21b  mov     rbx, [rsp+28h+arg_8]
0x18003f220  add     rsp, 20h
0x18003f224  pop     rdi
0x18003f225  retn
0x180076b47  push    rbp
0x180076b49  sub     rsp, 20h
0x180076b4d  mov     rbp, rdx
0x180076b50  mov     rax, [rcx]
0x180076b53  xor     ecx, ecx
0x180076b55  cmp     dword ptr [rax], 0C0000017h
0x180076b5b  setz    cl
0x180076b5e  mov     eax, ecx
0x180076b60  add     rsp, 20h
0x180076b64  pop     rbp
0x180076b65  retn
0x180076b67  push    rbp
0x180076b69  sub     rsp, 20h
0x180076b6d  mov     rbp, rdx
0x180076b70  mov     rax, [rcx]
0x180076b73  xor     ecx, ecx
0x180076b75  cmp     dword ptr [rax], 0C0000017h
0x180076b7b  setz    cl
0x180076b7e  mov     eax, ecx
0x180076b80  add     rsp, 20h
0x180076b84  pop     rbp
0x180076b85  retn
0x180076b87  push    rbp
0x180076b89  sub     rsp, 20h
0x180076b8d  mov     rbp, rdx
0x180076b90  mov     rax, [rcx]
0x180076b93  xor     ecx, ecx
0x180076b95  cmp     dword ptr [rax], 0C0000017h
0x180076b9b  setz    cl
0x180076b9e  mov     eax, ecx
0x180076ba0  add     rsp, 20h
0x180076ba4  pop     rbp
0x180076ba5  retn
```
