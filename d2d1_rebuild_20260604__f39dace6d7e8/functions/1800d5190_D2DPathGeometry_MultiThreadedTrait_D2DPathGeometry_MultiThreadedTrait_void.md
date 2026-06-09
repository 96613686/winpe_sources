# D2DPathGeometry<MultiThreadedTrait>::~D2DPathGeometry<MultiThreadedTrait>(void)

- ea: `0x1800d5190`
- end: `0x1800d5317`
- name: `??1?$D2DPathGeometry@VMultiThreadedTrait@@@@MEAA@XZ`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1802608c0`

## callees

- `0x1800d5190`
- `0x1800d6140`
- `0x18025b148`
- `0x180307010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d52e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d51d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800d51d8`

## pseudocode

```c
void **__fastcall D2DPathGeometry<MultiThreadedTrait>::~D2DPathGeometry<MultiThreadedTrait>(__int64 a1)
{
  _QWORD *v2; // rdi
  unsigned int i; // esi
  __int64 v4; // rax
  _QWORD *v5; // rbp
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void **result; // rax
  __int64 v12; // rcx

  *(_QWORD *)a1 = &D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `ID2D1PathGeometry1'};
  *(_QWORD *)(a1 + 8) = &D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `IPathGeometryInternal'};
  *(_QWORD *)(a1 + 24) = &D2DRegionGeometry::`vftable';
  if ( *(_BYTE *)(a1 + 472) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 432));
    *(_BYTE *)(a1 + 472) = 0;
  }
  v2 = (_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 40) = &CShape::`vftable';
  for ( i = 0; i < *(_DWORD *)(a1 + 72); ++i )
  {
    v4 = *(_QWORD *)(a1 + 48);
    v5 = *(_QWORD **)(v4 + 8LL * i);
    if ( v5 != v2 && v5 )
    {
      CFigureData::~CFigureData(*(CFigureData **)(v4 + 8LL * i));
      operator delete(v5);
    }
  }
  *v2 = &CFigureData::`vftable';
  v6 = *(void **)(a1 + 360);
  if ( v6 != *(void **)(a1 + 368) )
  {
    free(v6);
    *(_QWORD *)(a1 + 360) = 0;
  }
  v7 = *(void **)(a1 + 328);
  if ( v7 != *(void **)(a1 + 336) )
  {
    free(v7);
    *(_QWORD *)(a1 + 328) = 0;
  }
  v8 = *(void **)(a1 + 288);
  if ( v8 != *(void **)(a1 + 296) )
  {
    free(v8);
    *(_QWORD *)(a1 + 288) = 0;
  }
  v9 = *(void **)(a1 + 152);
  if ( v9 != *(void **)(a1 + 160) )
  {
    free(v9);
    *(_QWORD *)(a1 + 152) = 0;
  }
  v10 = *(void **)(a1 + 48);
  if ( v10 != *(void **)(a1 + 56) )
  {
    free(v10);
    *(_QWORD *)(a1 + 48) = 0;
  }
  result = &CShapeBase::`vftable';
  *(_QWORD *)(a1 + 40) = &CShapeBase::`vftable';
  v12 = *(_QWORD *)(a1 + 16);
  if ( v12 )
  {
    result = (void **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800d5190  mov     [rsp+arg_18], rbx
0x1800d5195  push    r14
0x1800d5197  sub     rsp, 20h
0x1800d519b  lea     rax, ??_7?$D2DPathGeometry@VMultiThreadedTrait@@@@6BID2D1PathGeometry1@@@; const D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `ID2D1PathGeometry1'}
0x1800d51a2  mov     [rsp+28h+arg_8], rsi
0x1800d51a7  mov     [rcx], rax
0x1800d51aa  mov     rbx, rcx
0x1800d51ad  lea     rax, ??_7?$D2DPathGeometry@VMultiThreadedTrait@@@@6BIPathGeometryInternal@@@; const D2DPathGeometry<MultiThreadedTrait>::`vftable'{for `IPathGeometryInternal'}
0x1800d51b4  mov     [rsp+28h+arg_10], rdi
0x1800d51b9  mov     [rcx+8], rax
0x1800d51bd  lea     rax, ??_7D2DRegionGeometry@@6B@; const D2DRegionGeometry::`vftable'
0x1800d51c4  mov     [rcx+18h], rax
0x1800d51c8  cmp     byte ptr [rcx+1D8h], 0
0x1800d51cf  jz      short loc_1800D51E5
0x1800d51d1  add     rcx, 1B0h; lpCriticalSection
0x1800d51d8  call    cs:__imp_DeleteCriticalSection
0x1800d51de  mov     byte ptr [rbx+1D8h], 0
0x1800d51e5  xor     r14d, r14d
0x1800d51e8  lea     rax, ??_7CShape@@6B@; const CShape::`vftable'
0x1800d51ef  lea     rdi, [rbx+90h]
0x1800d51f6  mov     [rbx+28h], rax
0x1800d51fa  mov     esi, r14d
0x1800d51fd  cmp     [rbx+48h], r14d
0x1800d5201  jbe     short loc_1800D5227
0x1800d5203  mov     [rsp+28h+arg_0], rbp
0x1800d5208  mov     rax, [rbx+30h]
0x1800d520c  mov     ecx, esi
0x1800d520e  mov     rbp, [rax+rcx*8]
0x1800d5212  cmp     rbp, rdi
0x1800d5215  jnz     loc_1800D52F4
0x1800d521b  inc     esi
0x1800d521d  cmp     esi, [rbx+48h]
0x1800d5220  jb      short loc_1800D5208
0x1800d5222  mov     rbp, [rsp+28h+arg_0]
0x1800d5227  mov     rsi, [rsp+28h+arg_8]
0x1800d522c  lea     rax, ??_7CFigureData@@6B@; const CFigureData::`vftable'
0x1800d5233  mov     [rdi], rax
0x1800d5236  mov     rcx, [rdi+0D8h]; Block
0x1800d523d  cmp     rcx, [rdi+0E0h]
0x1800d5244  jnz     short loc_1800D52AF
0x1800d5246  mov     rcx, [rdi+0B8h]; Block
0x1800d524d  cmp     rcx, [rdi+0C0h]
0x1800d5254  jnz     short loc_1800D52BE
0x1800d5256  mov     rcx, [rdi+90h]; Block
0x1800d525d  cmp     rcx, [rdi+98h]
0x1800d5264  jnz     short loc_1800D52CD
0x1800d5266  mov     rcx, [rdi+8]; Block
0x1800d526a  cmp     rcx, [rdi+10h]
0x1800d526e  jnz     short loc_1800D52DC
0x1800d5270  mov     rcx, [rbx+30h]; Block
0x1800d5274  mov     rdi, [rsp+28h+arg_10]
0x1800d5279  cmp     rcx, [rbx+38h]
0x1800d527d  jnz     short loc_1800D52E8
0x1800d527f  lea     rax, ??_7CShapeBase@@6B@; const CShapeBase::`vftable'
0x1800d5286  mov     [rbx+28h], rax
0x1800d528a  mov     rcx, [rbx+10h]
0x1800d528e  test    rcx, rcx
0x1800d5291  jz      short loc_1800D52A3
0x1800d5293  mov     rax, [rcx]
0x1800d5296  mov     rax, [rax+10h]
0x1800d529a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d529f  mov     [rbx+10h], r14
0x1800d52a3  mov     rbx, [rsp+28h+arg_18]
0x1800d52a8  add     rsp, 20h
0x1800d52ac  pop     r14
0x1800d52ae  retn
0x1800d52af  call    cs:__imp_free
0x1800d52b5  mov     [rdi+0D8h], r14
0x1800d52bc  jmp     short loc_1800D5246
0x1800d52be  call    cs:__imp_free
0x1800d52c4  mov     [rdi+0B8h], r14
0x1800d52cb  jmp     short loc_1800D5256
0x1800d52cd  call    cs:__imp_free
0x1800d52d3  mov     [rdi+90h], r14
0x1800d52da  jmp     short loc_1800D5266
0x1800d52dc  call    cs:__imp_free
0x1800d52e2  mov     [rdi+8], r14
0x1800d52e6  jmp     short loc_1800D5270
0x1800d52e8  call    cs:__imp_free
0x1800d52ee  mov     [rbx+30h], r14
0x1800d52f2  jmp     short loc_1800D527F
0x1800d52f4  test    rbp, rbp
0x1800d52f7  jz      loc_1800D521B
0x1800d52fd  mov     rcx, rbp; this
0x1800d5300  call    ??1CFigureData@@UEAA@XZ; CFigureData::~CFigureData(void)
0x1800d5305  mov     edx, 120h
0x1800d530a  mov     rcx, rbp; Block
0x1800d530d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d5312  jmp     loc_1800D521B
```
