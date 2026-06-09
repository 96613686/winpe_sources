# ATL::CAtlExeModuleT<CcttunesvrModule>::~CAtlExeModuleT<CcttunesvrModule>(void)

- ea: `0x140005244`
- end: `0x140005319`
- name: `??1?$CAtlExeModuleT@VCcttunesvrModule@@@ATL@@UEAA@XZ`
- size: `213`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140005320`
- `0x1400067a0`

## callees

- `0x140005244`
- `0x1400060fc`
- `0x140007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400052e6`
- `KERNEL32!DeleteCriticalSection` at `0x1400052e6`
- `ole32!CoUninitialize` at `0x1400052fc`
- `ole32!CoUninitialize` at `0x1400052fc`

## pseudocode

```c
void __fastcall ATL::CAtlExeModuleT<CcttunesvrModule>::~CAtlExeModuleT<CcttunesvrModule>(ATL::CAtlModule *this)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v1; // rbx
  __int64 *v3; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  __int64 v7; // rcx

  v1 = off_14000B100;
  v3 = off_14000B108;
  while ( v1 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v1 )
    {
      (*((void (__fastcall **)(_QWORD))*v1 + 8))(0);
      v3 = off_14000B108;
    }
    ++v1;
  }
  ATL::CAtlModule::Term(this);
  if ( ATL::_AtlComModule )
  {
    v4 = off_14000B100;
    v5 = off_14000B108;
    while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = *((_QWORD *)v6 + 4);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        *((_QWORD *)v6 + 4) = 0;
        v5 = off_14000B108;
      }
      ++v4;
    }
    DeleteCriticalSection(&CriticalSection);
    ATL::_AtlComModule = 0;
  }
  if ( *((_BYTE *)this + 98) )
    CoUninitialize();
  ATL::CAtlModule::Term(this);
}

```

## disassembly

```asm
0x140005244  mov     [rsp+arg_0], rbx
0x140005249  mov     [rsp+arg_8], rsi
0x14000524e  push    rdi
0x14000524f  sub     rsp, 20h
0x140005253  mov     rbx, cs:off_14000B100
0x14000525a  mov     rdi, rcx
0x14000525d  mov     rax, cs:off_14000B108
0x140005264  jmp     short loc_140005284
0x140005266  mov     rdx, [rbx]
0x140005269  test    rdx, rdx
0x14000526c  jz      short loc_140005280
0x14000526e  mov     rax, [rdx+40h]
0x140005272  xor     ecx, ecx
0x140005274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005279  mov     rax, cs:off_14000B108
0x140005280  add     rbx, 8
0x140005284  cmp     rbx, rax
0x140005287  jb      short loc_140005266
0x140005289  mov     rcx, rdi; this
0x14000528c  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x140005291  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x140005298  jz      short loc_1400052F6
0x14000529a  mov     rbx, cs:off_14000B100
0x1400052a1  mov     rax, cs:off_14000B108
0x1400052a8  jmp     short loc_1400052DA
0x1400052aa  mov     rsi, [rbx]
0x1400052ad  test    rsi, rsi
0x1400052b0  jz      short loc_1400052D6
0x1400052b2  mov     rcx, [rsi+20h]
0x1400052b6  test    rcx, rcx
0x1400052b9  jz      short loc_1400052C7
0x1400052bb  mov     rax, [rcx]
0x1400052be  mov     rax, [rax+10h]
0x1400052c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052c7  mov     qword ptr [rsi+20h], 0
0x1400052cf  mov     rax, cs:off_14000B108
0x1400052d6  add     rbx, 8
0x1400052da  cmp     rbx, rax
0x1400052dd  jb      short loc_1400052AA
0x1400052df  lea     rcx, CriticalSection; lpCriticalSection
0x1400052e6  call    cs:__imp_DeleteCriticalSection
0x1400052ec  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x1400052f6  cmp     byte ptr [rdi+62h], 0
0x1400052fa  jz      short loc_140005302
0x1400052fc  call    cs:__imp_CoUninitialize
0x140005302  mov     rcx, rdi; this
0x140005305  mov     rbx, [rsp+28h+arg_0]
0x14000530a  mov     rsi, [rsp+28h+arg_8]
0x14000530f  add     rsp, 20h
0x140005313  pop     rdi
0x140005314  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
