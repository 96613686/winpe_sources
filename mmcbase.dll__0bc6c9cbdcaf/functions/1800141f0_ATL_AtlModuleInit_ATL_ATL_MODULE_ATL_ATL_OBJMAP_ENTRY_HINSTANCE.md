# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x1800141f0`
- end: `0x1800143af`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ca8`

## callees

- `0x1800141f0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014232`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014240`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001424e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014232`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180014240`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001424e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001434b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800142ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001434b`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_18002C390 = 0;
  qword_18002C380 = a3;
  qword_18002C388 = a3;
  qword_18002C378 = a3;
  dword_18002C398 = 0;
  qword_18002C3A0 = 0;
  InitializeCriticalSection(&CriticalSection);
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_18002C3F8);
  qword_18002C428 = 0;
  byte_18002C430 = 1;
  dword_18002C440 = 0;
  dword_18002C450 = 0;
  qword_18002C448 = 0;
  qword_18002C458 = 0;
  v4 = qword_18002C390;
  if ( qword_18002C390 )
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
  dword_18002C460 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800141f0  push    rbx
0x1800141f2  sub     rsp, 20h
0x1800141f6  mov     cs:qword_18002C390, 0
0x180014201  mov     cs:qword_18002C380, r8
0x180014208  mov     cs:qword_18002C388, r8
0x18001420f  mov     cs:qword_18002C378, r8
0x180014216  mov     cs:dword_18002C398, 0
0x180014220  mov     cs:qword_18002C3A0, 0
0x18001422b  lea     rcx, CriticalSection; lpCriticalSection
0x180014232  call    cs:__imp_InitializeCriticalSection
0x180014238  nop
0x180014239  lea     rcx, Buf1; lpCriticalSection
0x180014240  call    cs:__imp_InitializeCriticalSection
0x180014246  nop
0x180014247  lea     rcx, stru_18002C3F8; lpCriticalSection
0x18001424e  call    cs:__imp_InitializeCriticalSection
0x180014254  nop
0x180014255  mov     cs:qword_18002C428, 0
0x180014260  mov     cs:byte_18002C430, 1
0x180014267  mov     cs:dword_18002C440, 0
0x180014271  mov     cs:dword_18002C450, 0
0x18001427b  mov     cs:qword_18002C448, 0
0x180014286  mov     cs:qword_18002C458, 0
0x180014291  mov     rbx, cs:qword_18002C390
0x180014298  test    rbx, rbx
0x18001429b  jz      short loc_1800142C8
0x18001429d  jmp     short loc_1800142C2
0x18001429f  mov     cl, 1
0x1800142a1  mov     rax, [rbx+40h]
0x1800142a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142aa  mov     eax, 48h ; 'H'
0x1800142af  lea     ecx, [rax-10h]
0x1800142b2  cmp     cs:?_Module@@3VCComModule@ATL@@A, 0B0h; ATL::CComModule _Module
0x1800142bc  cmovz   eax, ecx
0x1800142bf  add     rbx, rax
0x1800142c2  cmp     qword ptr [rbx], 0
0x1800142c6  jnz     short loc_18001429F
0x1800142c8  mov     cs:dword_18002C460, 1
0x1800142d2  xor     eax, eax
0x1800142d4  jmp     loc_1800143A9
0x1800142d9  lea     rcx, Buf1; lpCriticalSection
0x1800142e0  call    cs:__imp_DeleteCriticalSection
0x1800142e6  lea     rcx, CriticalSection; lpCriticalSection
0x1800142ed  call    cs:__imp_DeleteCriticalSection
0x1800142f3  xorps   xmm0, xmm0
0x1800142f6  xor     eax, eax
0x1800142f8  movups  xmmword ptr cs:stru_18002C3F8.DebugInfo, xmm0
0x1800142ff  movups  xmmword ptr cs:stru_18002C3F8.OwningThread, xmm0
0x180014306  mov     cs:stru_18002C3F8.SpinCount, rax
0x18001430d  xorps   xmm1, xmm1
0x180014310  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x180014317  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x18001431e  mov     cs:Buf1.SpinCount, rax
0x180014325  xorps   xmm0, xmm0
0x180014328  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x18001432f  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x180014336  mov     cs:CriticalSection.SpinCount, rax
0x18001433d  mov     eax, 0C0000017h
0x180014342  jmp     short loc_1800143A9
0x180014344  lea     rcx, CriticalSection; lpCriticalSection
0x18001434b  call    cs:__imp_DeleteCriticalSection
0x180014351  xorps   xmm0, xmm0
0x180014354  xor     eax, eax
0x180014356  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18001435d  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x180014364  mov     cs:Buf1.SpinCount, rax
0x18001436b  xorps   xmm1, xmm1
0x18001436e  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm1
0x180014375  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm1
0x18001437c  mov     cs:CriticalSection.SpinCount, rax
0x180014383  mov     eax, 0C0000017h
0x180014388  jmp     short loc_1800143A9
0x18001438a  xorps   xmm0, xmm0
0x18001438d  xor     eax, eax
0x18001438f  movups  xmmword ptr cs:CriticalSection.DebugInfo, xmm0
0x180014396  movups  xmmword ptr cs:CriticalSection.OwningThread, xmm0
0x18001439d  mov     cs:CriticalSection.SpinCount, rax
0x1800143a4  mov     eax, 0C0000017h
0x1800143a9  add     rsp, 20h
0x1800143ad  pop     rbx
0x1800143ae  retn
0x18001bf85  push    rbp
0x18001bf87  sub     rsp, 20h
0x18001bf8b  mov     rbp, rdx
0x18001bf8e  mov     rax, [rcx]
0x18001bf91  xor     ecx, ecx
0x18001bf93  cmp     dword ptr [rax], 0C0000017h
0x18001bf99  setz    cl
0x18001bf9c  mov     eax, ecx
0x18001bf9e  add     rsp, 20h
0x18001bfa2  pop     rbp
0x18001bfa3  retn
0x18001bfa5  push    rbp
0x18001bfa7  sub     rsp, 20h
0x18001bfab  mov     rbp, rdx
0x18001bfae  mov     rax, [rcx]
0x18001bfb1  xor     ecx, ecx
0x18001bfb3  cmp     dword ptr [rax], 0C0000017h
0x18001bfb9  setz    cl
0x18001bfbc  mov     eax, ecx
0x18001bfbe  add     rsp, 20h
0x18001bfc2  pop     rbp
0x18001bfc3  retn
0x18001bfc5  push    rbp
0x18001bfc7  sub     rsp, 20h
0x18001bfcb  mov     rbp, rdx
0x18001bfce  mov     rax, [rcx]
0x18001bfd1  xor     ecx, ecx
0x18001bfd3  cmp     dword ptr [rax], 0C0000017h
0x18001bfd9  setz    cl
0x18001bfdc  mov     eax, ecx
0x18001bfde  add     rsp, 20h
0x18001bfe2  pop     rbp
0x18001bfe3  retn
```
