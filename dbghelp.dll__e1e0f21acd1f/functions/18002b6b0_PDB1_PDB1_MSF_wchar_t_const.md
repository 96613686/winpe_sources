# PDB1::PDB1(MSF *,wchar_t const *)

- ea: `0x18002b6b0`
- end: `0x18002b8de`
- name: `??0PDB1@@IEAA@PEAUMSF@@PEB_W@Z`
- size: `558`
- prototype: `PDB1 *(PDB1 *__hidden this, struct MSF *, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800321b0`
- `0x180032c30`

## callees

- `0x180027680`
- `0x18002b6b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18002b881`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x18002b881`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002b89f`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002b89f`

## pseudocode

```c
PDB1 *__fastcall PDB1::PDB1(PDB1 *this, struct MSF *a2, const wchar_t *a3)
{
  char *v3; // rsi
  unsigned int i; // edx
  __int64 v7; // rcx
  unsigned int j; // edx
  __int64 v9; // rcx
  PDB1 *result; // rax

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &PDB1::`vftable';
  v3 = (char *)this + 576;
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_DWORD *)this + 138) = 0;
  *(_OWORD *)((char *)this + 556) = 0;
  pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>((char *)this + 576, 1);
  pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(v3 + 24, 1);
  pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(v3 + 48, 1);
  for ( i = 0; i < *((_DWORD *)v3 + 16); *(_DWORD *)(*((_QWORD *)v3 + 7) + 4 * v7) = 0 )
    v7 = i++;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 9) = &pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable';
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_DWORD *)v3 + 24) = 0;
  pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(v3 + 112, 1);
  pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(v3 + 136, 1);
  pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(v3 + 160, 1);
  for ( j = 0; j < *((_DWORD *)v3 + 44); *(_DWORD *)(*((_QWORD *)v3 + 21) + 4 * v9) = 0 )
    v9 = j++;
  *((_QWORD *)v3 + 23) = &pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable';
  *((_QWORD *)v3 + 24) = 0;
  *((_QWORD *)v3 + 25) = 0;
  *((_QWORD *)v3 + 27) = 0;
  *((_DWORD *)v3 + 52) = 0;
  *((_QWORD *)v3 + 28) = &pdb_internal::Buffer::`vftable';
  *((_DWORD *)v3 + 62) = 0;
  *((_QWORD *)v3 + 29) = 0;
  *((_QWORD *)v3 + 30) = 0;
  *((_QWORD *)v3 + 32) = 0;
  *((_QWORD *)v3 + 33) = 0;
  *((_WORD *)v3 + 136) = 257;
  *((_QWORD *)v3 + 35) = PDB1::niForNextFreeSn;
  *((_QWORD *)v3 + 36) = this;
  *((_DWORD *)v3 + 74) = 0;
  *((_QWORD *)v3 + 13) = v3 + 224;
  *((_QWORD *)this + 110) = 0;
  *((_QWORD *)this + 111) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 113) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 115) = 0;
  *((_QWORD *)this + 116) = 0;
  *((_QWORD *)this + 117) = 0;
  *((_DWORD *)this + 238) = 0;
  if ( !_wfullpath((wchar_t *)this + 8, a3, 0x104u) )
    _o_wcsncpy_s((char *)this + 16, 260, a3, -1);
  *((_BYTE *)this + 946) &= 0xC0u;
  result = this;
  *(_WORD *)((char *)this + 947) = 0;
  *((_WORD *)this + 472) = 0;
  return result;
}

```

## disassembly

```asm
0x18002b6b0  mov     [rsp+arg_0], rbx
0x18002b6b5  mov     [rsp+arg_8], rbp
0x18002b6ba  mov     [rsp+arg_10], rsi
0x18002b6bf  mov     [rsp+arg_18], rdi
0x18002b6c4  push    r12
0x18002b6c6  push    r14
0x18002b6c8  push    r15
0x18002b6ca  sub     rsp, 20h
0x18002b6ce  mov     [rcx+8], rdx
0x18002b6d2  lea     rax, ??_7PDB1@@6B@; const PDB1::`vftable'
0x18002b6d9  mov     [rcx], rax
0x18002b6dc  lea     rsi, [rcx+240h]
0x18002b6e3  xor     r15d, r15d
0x18002b6e6  xorps   xmm0, xmm0
0x18002b6e9  mov     [rcx+218h], r15
0x18002b6f0  mov     rbx, rcx
0x18002b6f3  mov     [rcx+220h], r15
0x18002b6fa  mov     edx, 1
0x18002b6ff  mov     [rcx+228h], r15d
0x18002b706  mov     r14, r8
0x18002b709  movups  xmmword ptr [rcx+22Ch], xmm0
0x18002b710  mov     rcx, rsi
0x18002b713  call    ??0?$Array@USZO@NMTNI@@@pdb_internal@@QEAA@I@Z; pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(uint)
0x18002b718  lea     rcx, [rsi+18h]
0x18002b71c  mov     edx, 1
0x18002b721  call    ??0?$Array@USZO@NMTNI@@@pdb_internal@@QEAA@I@Z; pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(uint)
0x18002b726  mov     edx, 1
0x18002b72b  lea     rcx, [rsi+30h]
0x18002b72f  call    ??0?$Array@USZO@NMTNI@@@pdb_internal@@QEAA@I@Z; pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(uint)
0x18002b734  mov     edx, r15d
0x18002b737  cmp     [rsi+40h], r15d
0x18002b73b  jbe     short loc_18002B751
0x18002b73d  nop     dword ptr [rax]
0x18002b740  mov     rax, [rsi+38h]
0x18002b744  mov     ecx, edx
0x18002b746  inc     edx
0x18002b748  mov     [rax+rcx*4], r15d
0x18002b74c  cmp     edx, [rsi+40h]
0x18002b74f  jb      short loc_18002B740
0x18002b751  lea     r12, ??_7?$Array@VReadOnlySafeSpanPtr@@@pdb_internal@@6B@; const pdb_internal::Array<ReadOnlySafeSpanPtr>::`vftable'
0x18002b758  mov     [rsi+50h], r15
0x18002b75c  mov     edx, 1
0x18002b761  mov     [rsi+48h], r12
0x18002b765  lea     rcx, [rsi+70h]
0x18002b769  mov     [rsi+58h], r15
0x18002b76d  mov     [rsi+68h], r15
0x18002b771  mov     [rsi+60h], r15d
0x18002b775  call    ??0?$Array@USZO@NMTNI@@@pdb_internal@@QEAA@I@Z; pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(uint)
0x18002b77a  lea     rcx, [rsi+88h]
0x18002b781  mov     edx, 1
0x18002b786  call    ??0?$Array@USZO@NMTNI@@@pdb_internal@@QEAA@I@Z; pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(uint)
0x18002b78b  mov     edx, 1
0x18002b790  lea     rcx, [rsi+0A0h]
0x18002b797  call    ??0?$Array@USZO@NMTNI@@@pdb_internal@@QEAA@I@Z; pdb_internal::Array<NMTNI::SZO>::Array<NMTNI::SZO>(uint)
0x18002b79c  mov     edx, r15d
0x18002b79f  cmp     [rsi+0B0h], r15d
0x18002b7a6  jbe     short loc_18002B7C7
0x18002b7a8  nop     dword ptr [rax+rax+00000000h]
0x18002b7b0  mov     rax, [rsi+0A8h]
0x18002b7b7  mov     ecx, edx
0x18002b7b9  inc     edx
0x18002b7bb  mov     [rax+rcx*4], r15d
0x18002b7bf  cmp     edx, [rsi+0B0h]
0x18002b7c5  jb      short loc_18002B7B0
0x18002b7c7  mov     [rsi+0B8h], r12
0x18002b7ce  lea     rax, [rsi+0E0h]
0x18002b7d5  mov     [rsi+0C0h], r15
0x18002b7dc  lea     rcx, ??_7Buffer@pdb_internal@@6B@; const pdb_internal::Buffer::`vftable'
0x18002b7e3  mov     [rsi+0C8h], r15
0x18002b7ea  mov     r8d, 104h; BufferCount
0x18002b7f0  mov     [rsi+0D8h], r15
0x18002b7f7  mov     rdx, r14; Path
0x18002b7fa  mov     [rsi+0D0h], r15d
0x18002b801  mov     [rax], rcx
0x18002b804  lea     rcx, ?niForNextFreeSn@PDB1@@CAHPEAXPEAK@Z; PDB1::niForNextFreeSn(void *,ulong *)
0x18002b80b  mov     [rax+18h], r15d
0x18002b80f  mov     [rax+8], r15
0x18002b813  mov     [rax+10h], r15
0x18002b817  mov     [rax+20h], r15
0x18002b81b  mov     [rax+28h], r15
0x18002b81f  mov     word ptr [rax+30h], 101h
0x18002b825  mov     [rsi+118h], rcx
0x18002b82c  lea     rcx, [rbx+10h]; Buffer
0x18002b830  mov     [rsi+120h], rbx
0x18002b837  mov     [rsi+128h], r15d
0x18002b83e  mov     [rsi+68h], rax
0x18002b842  mov     [rbx+370h], r15
0x18002b849  mov     [rbx+378h], r15
0x18002b850  mov     [rbx+380h], r15
0x18002b857  mov     [rbx+388h], r15
0x18002b85e  mov     [rbx+390h], r15
0x18002b865  mov     [rbx+398h], r15
0x18002b86c  mov     [rbx+3A0h], r15
0x18002b873  mov     [rbx+3A8h], r15
0x18002b87a  mov     [rbx+3B8h], r15d
0x18002b881  call    cs:__imp__wfullpath
0x18002b887  test    rax, rax
0x18002b88a  jnz     short loc_18002B8A5
0x18002b88c  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002b893  lea     rcx, [rbx+10h]
0x18002b897  mov     r8, r14
0x18002b89a  mov     edx, 104h
0x18002b89f  call    cs:__imp__o_wcsncpy_s
0x18002b8a5  and     byte ptr [rbx+3B2h], 0C0h
0x18002b8ac  mov     rax, rbx
0x18002b8af  mov     rbp, [rsp+38h+arg_8]
0x18002b8b4  mov     rsi, [rsp+38h+arg_10]
0x18002b8b9  mov     rdi, [rsp+38h+arg_18]
0x18002b8be  mov     [rbx+3B3h], r15w
0x18002b8c6  mov     [rbx+3B0h], r15w
0x18002b8ce  mov     rbx, [rsp+38h+arg_0]
0x18002b8d3  add     rsp, 20h
0x18002b8d7  pop     r15
0x18002b8d9  pop     r14
0x18002b8db  pop     r12
0x18002b8dd  retn
```
