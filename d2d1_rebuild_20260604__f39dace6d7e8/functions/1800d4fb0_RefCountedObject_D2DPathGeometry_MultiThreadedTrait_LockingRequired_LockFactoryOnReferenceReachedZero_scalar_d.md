# RefCountedObject<D2DPathGeometry<MultiThreadedTrait>,LockingRequired,LockFactoryOnReferenceReachedZero>::`scalar deleting destructor'(uint)

- ea: `0x1800d4fb0`
- end: `0x1800d517c`
- name: `??_G?$RefCountedObject@V?$D2DPathGeometry@VMultiThreadedTrait@@@@ULockingRequired@@ULockFactoryOnReferenceReachedZero@@@@UEAAPEAXI@Z`
- size: `460`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800d4fb0`
- `0x1800d6140`
- `0x18025b148`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d5105`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d5117`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d5129`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d513b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d514a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d5105`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d5117`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d5129`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d513b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d514a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d5000`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d5000`

## pseudocode

```c
char *__fastcall RefCountedObject<D2DPathGeometry<MultiThreadedTrait>,LockingRequired,LockFactoryOnReferenceReachedZero>::`scalar deleting destructor'(
        char *Block,
        char a2)
{
  _QWORD *v4; // rdi
  unsigned int i; // esi
  __int64 v6; // rax
  _QWORD *v7; // rbp
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rcx

  *(_QWORD *)Block = &D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `ID2D1PathGeometry1'};
  *((_QWORD *)Block + 1) = &D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `IPathGeometryInternal'};
  *((_QWORD *)Block + 3) = &D2DRegionGeometry::`vftable';
  if ( Block[472] )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 432));
    Block[472] = 0;
  }
  v4 = Block + 144;
  *((_QWORD *)Block + 5) = &CShape::`vftable';
  for ( i = 0; i < *((_DWORD *)Block + 18); ++i )
  {
    v6 = *((_QWORD *)Block + 6);
    v7 = *(_QWORD **)(v6 + 8LL * i);
    if ( v7 != v4 && v7 )
    {
      CFigureData::~CFigureData(*(CFigureData **)(v6 + 8LL * i));
      operator delete(v7);
    }
  }
  *v4 = &CFigureData::`vftable';
  v8 = (void *)*((_QWORD *)Block + 45);
  if ( v8 != *((void **)Block + 46) )
  {
    free(v8);
    *((_QWORD *)Block + 45) = 0;
  }
  v9 = (void *)*((_QWORD *)Block + 41);
  if ( v9 != *((void **)Block + 42) )
  {
    free(v9);
    *((_QWORD *)Block + 41) = 0;
  }
  v10 = (void *)*((_QWORD *)Block + 36);
  if ( v10 != *((void **)Block + 37) )
  {
    free(v10);
    *((_QWORD *)Block + 36) = 0;
  }
  v11 = (void *)*((_QWORD *)Block + 19);
  if ( v11 != *((void **)Block + 20) )
  {
    free(v11);
    *((_QWORD *)Block + 19) = 0;
  }
  v12 = (void *)*((_QWORD *)Block + 6);
  if ( v12 != *((void **)Block + 7) )
  {
    free(v12);
    *((_QWORD *)Block + 6) = 0;
  }
  *((_QWORD *)Block + 5) = &CShapeBase::`vftable';
  v13 = *((_QWORD *)Block + 2);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)Block + 2) = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800d4fb0  push    rbx
0x1800d4fb2  sub     rsp, 30h
0x1800d4fb6  mov     [rsp+38h+arg_8], rsi
0x1800d4fbb  lea     rax, ??_7?$D2DPathGeometry@VMultiThreadedTrait@@@@6BID2D1PathGeometry1@@@; const D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `ID2D1PathGeometry1'}
0x1800d4fc2  mov     [rcx], rax
0x1800d4fc5  mov     rbx, rcx
0x1800d4fc8  lea     rax, ??_7?$D2DPathGeometry@VMultiThreadedTrait@@@@6BIPathGeometryInternal@@@; const D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `IPathGeometryInternal'}
0x1800d4fcf  mov     [rsp+38h+arg_10], rdi
0x1800d4fd4  mov     [rcx+8], rax
0x1800d4fd8  lea     rax, ??_7D2DRegionGeometry@@6B@; const D2DRegionGeometry::`vftable'
0x1800d4fdf  mov     [rsp+38h+var_10], r14
0x1800d4fe4  mov     r14d, edx
0x1800d4fe7  mov     [rcx+18h], rax
0x1800d4feb  cmp     byte ptr [rcx+1D8h], 0
0x1800d4ff2  mov     [rsp+38h+var_18], r15
0x1800d4ff7  jz      short loc_1800D500D
0x1800d4ff9  add     rcx, 1B0h; lpCriticalSection
0x1800d5000  call    cs:__imp_DeleteCriticalSection
0x1800d5006  mov     byte ptr [rbx+1D8h], 0
0x1800d500d  xor     r15d, r15d
0x1800d5010  lea     rax, ??_7CShape@@6B@; const CShape::`vftable'
0x1800d5017  lea     rdi, [rbx+90h]
0x1800d501e  mov     [rbx+28h], rax
0x1800d5022  mov     esi, r15d
0x1800d5025  cmp     [rbx+48h], r15d
0x1800d5029  jbe     short loc_1800D504F
0x1800d502b  mov     [rsp+38h+arg_0], rbp
0x1800d5030  mov     rax, [rbx+30h]
0x1800d5034  mov     ecx, esi
0x1800d5036  mov     rbp, [rax+rcx*8]
0x1800d503a  cmp     rbp, rdi
0x1800d503d  jnz     loc_1800D5159
0x1800d5043  inc     esi
0x1800d5045  cmp     esi, [rbx+48h]
0x1800d5048  jb      short loc_1800D5030
0x1800d504a  mov     rbp, [rsp+38h+arg_0]
0x1800d504f  mov     rsi, [rsp+38h+arg_8]
0x1800d5054  lea     rax, ??_7CFigureData@@6B@; const CFigureData::`vftable'
0x1800d505b  mov     [rdi], rax
0x1800d505e  mov     rcx, [rdi+0D8h]; Block
0x1800d5065  cmp     rcx, [rdi+0E0h]
0x1800d506c  jnz     loc_1800D5105
0x1800d5072  mov     rcx, [rdi+0B8h]; Block
0x1800d5079  cmp     rcx, [rdi+0C0h]
0x1800d5080  jnz     loc_1800D5117
0x1800d5086  mov     rcx, [rdi+90h]; Block
0x1800d508d  cmp     rcx, [rdi+98h]
0x1800d5094  jnz     loc_1800D5129
0x1800d509a  mov     rcx, [rdi+8]; Block
0x1800d509e  cmp     rcx, [rdi+10h]
0x1800d50a2  jnz     loc_1800D513B
0x1800d50a8  mov     rcx, [rbx+30h]; Block
0x1800d50ac  mov     rdi, [rsp+38h+arg_10]
0x1800d50b1  cmp     rcx, [rbx+38h]
0x1800d50b5  jnz     loc_1800D514A
0x1800d50bb  lea     rax, ??_7CShapeBase@@6B@; const CShapeBase::`vftable'
0x1800d50c2  mov     [rbx+28h], rax
0x1800d50c6  mov     rcx, [rbx+10h]
0x1800d50ca  test    rcx, rcx
0x1800d50cd  jz      short loc_1800D50DF
0x1800d50cf  mov     rax, [rcx]
0x1800d50d2  mov     rax, [rax+10h]
0x1800d50d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d50db  mov     [rbx+10h], r15
0x1800d50df  mov     r15, [rsp+38h+var_18]
0x1800d50e4  test    r14b, 1
0x1800d50e8  mov     r14, [rsp+38h+var_10]
0x1800d50ed  jz      short loc_1800D50FC
0x1800d50ef  mov     edx, 1E8h
0x1800d50f4  mov     rcx, rbx; Block
0x1800d50f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d50fc  mov     rax, rbx
0x1800d50ff  add     rsp, 30h
0x1800d5103  pop     rbx
0x1800d5104  retn
0x1800d5105  call    cs:__imp_free
0x1800d510b  mov     [rdi+0D8h], r15
0x1800d5112  jmp     loc_1800D5072
0x1800d5117  call    cs:__imp_free
0x1800d511d  mov     [rdi+0B8h], r15
0x1800d5124  jmp     loc_1800D5086
0x1800d5129  call    cs:__imp_free
0x1800d512f  mov     [rdi+90h], r15
0x1800d5136  jmp     loc_1800D509A
0x1800d513b  call    cs:__imp_free
0x1800d5141  mov     [rdi+8], r15
0x1800d5145  jmp     loc_1800D50A8
0x1800d514a  call    cs:__imp_free
0x1800d5150  mov     [rbx+30h], r15
0x1800d5154  jmp     loc_1800D50BB
0x1800d5159  test    rbp, rbp
0x1800d515c  jz      loc_1800D5043
0x1800d5162  mov     rcx, rbp; this
0x1800d5165  call    ??1CFigureData@@UEAA@XZ; CFigureData::~CFigureData(void)
0x1800d516a  mov     edx, 120h
0x1800d516f  mov     rcx, rbp; Block
0x1800d5172  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d5177  jmp     loc_1800D5043
```
