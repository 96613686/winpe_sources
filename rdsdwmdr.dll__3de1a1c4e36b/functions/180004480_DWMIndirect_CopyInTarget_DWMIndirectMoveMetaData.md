# DWMIndirect::CopyInTarget(_DWMIndirectMoveMetaData)

- ea: `0x180004480`
- end: `0x180004669`
- name: `?CopyInTarget@DWMIndirect@@IEAAJU_DWMIndirectMoveMetaData@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006240`

## callees

- `0x1800019fc`
- `0x180004480`
- `0x180006db4`
- `0x18002c010`

## import_xrefs

- `GDI32!BitBlt` at `0x1800045b4`
- `GDI32!BitBlt` at `0x1800045b4`
- `GDI32!SelectClipRgn` at `0x180004571`
- `GDI32!SelectClipRgn` at `0x18000464d`
- `GDI32!SelectClipRgn` at `0x180004571`
- `GDI32!SelectClipRgn` at `0x18000464d`

## string_xrefs

- `0x1800044da`: `DWMIndirect::CopyInTarget ptOffset=[%d, %d] dstRect=[%d, %d, %d, %d] srcRect=[%d, %d, %d %d]`

## pseudocode

```c
__int64 __fastcall DWMIndirect::CopyInTarget(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  int x1; // esi
  int y1; // r14d
  int v8; // r15d
  LONG v9; // r12d
  HRGN v10; // r13
  LONG top; // r13d
  __int64 v12; // rcx
  __int64 v13; // r8
  HDC v14; // rcx
  HPEN v15; // r8
  HDC hdcSrc; // [rsp+28h] [rbp-91h]
  LONG v18; // [rsp+80h] [rbp-39h] BYREF
  int v19; // [rsp+84h] [rbp-35h] BYREF
  int v20; // [rsp+88h] [rbp-31h] BYREF
  int v21; // [rsp+8Ch] [rbp-2Dh] BYREF
  int v22; // [rsp+90h] [rbp-29h] BYREF
  int v23[3]; // [rsp+94h] [rbp-25h] BYREF
  struct tagRECT v24; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-9h]
  int v26; // [rsp+B8h] [rbp-1h]
  int v27; // [rsp+BCh] [rbp+3h]
  const char *v28; // [rsp+C0h] [rbp+7h] BYREF
  LONG v29; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  int v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v4 = *(_QWORD *)(a2 + 16);
  x1 = *(_DWORD *)a2;
  y1 = *(_DWORD *)(a2 + 4);
  v8 = *(_DWORD *)(a2 + 8);
  v9 = *(_DWORD *)(a2 + 12);
  v10 = *(HRGN *)(a2 + 24);
  *(_QWORD *)&v24.left = v4;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v29 = v9;
    v22 = HIDWORD(v4);
    v28 = "DWMIndirect::CopyInTarget ptOffset=[%d, %d] dstRect=[%d, %d, %d, %d] srcRect=[%d, %d, %d %d]";
    v30 = v8;
    v31 = y1;
    v32 = x1;
    v18 = v9;
    v19 = v8;
    v20 = y1;
    v21 = x1;
    v23[0] = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_1800372DD,
      a3,
      a4,
      (const unsigned __int16 **)&v28,
      (__int64)v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29);
  }
  SelectClipRgn(*(HDC *)(a1 + 72), v10);
  top = v24.top;
  hdcSrc = *(HDC *)(a1 + 72);
  v29 = x1 + v4;
  BitBlt(hdcSrc, x1 + v4, y1 + v24.top, v8 - x1, v9 - y1, hdcSrc, x1, y1, 0xCC0020u);
  v12 = *(_QWORD *)(a1 + 912);
  if ( v12 )
  {
    *(_QWORD *)&v24.left = *(_QWORD *)(a1 + 900);
    v24.right = *(_DWORD *)(a1 + 908);
    v24.bottom = 0;
    v25 = *(_QWORD *)(a1 + 96);
    v26 = *(_DWORD *)(a1 + 104);
    v27 = *(_DWORD *)(a1 + 108);
    (*(void (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v12 + 64LL))(v12, &v24);
  }
  if ( (g_uiDwmDirectRenderingFlags & 1) != 0 )
  {
    v13 = *(unsigned int *)(a1 + 224);
    v14 = *(HDC *)(a1 + 72);
    v24.left = v29;
    v24.top = y1 + top;
    v15 = *(HPEN *)(a1 + 8 * v13 + 232);
    v24.right = v8 + v4;
    v24.bottom = v9 + top;
    DrawRectangleToDC(v14, &v24, v15, 2u);
  }
  SelectClipRgn(*(HDC *)(a1 + 72), 0);
  return 0;
}

```

## disassembly

```asm
0x180004480  push    rbp
0x180004482  push    rbx
0x180004483  push    rsi
0x180004484  push    rdi
0x180004485  push    r12
0x180004487  push    r13
0x180004489  push    r14
0x18000448b  push    r15
0x18000448d  lea     rbp, [rsp-1Fh]
0x180004492  sub     rsp, 0D8h
0x180004499  mov     rbx, [rdx+10h]
0x18000449d  mov     rdi, rcx
0x1800044a0  mov     eax, cs:dword_180044008
0x1800044a6  mov     esi, [rdx]
0x1800044a8  mov     r14d, [rdx+4]
0x1800044ac  mov     r15d, [rdx+8]
0x1800044b0  mov     r12d, [rdx+0Ch]
0x1800044b4  mov     r13, [rdx+18h]
0x1800044b8  mov     qword ptr [rbp+57h+var_70.left], rbx
0x1800044bc  cmp     eax, 5
0x1800044bf  jbe     loc_18000456A
0x1800044c5  mov     rax, rbx
0x1800044c8  mov     [rbp+57h+arg_0], r12d
0x1800044cc  shr     rax, 20h
0x1800044d0  lea     rdx, byte_1800372DD
0x1800044d7  mov     [rbp+57h+var_80], eax
0x1800044da  lea     rax, aDwmindirectCop; "DWMIndirect::CopyInTarget ptOffset=[%d,"...
0x1800044e1  mov     [rbp+57h+var_50], rax
0x1800044e5  lea     rax, [rbp+57h+arg_0]
0x1800044e9  mov     [rsp+110h+var_A0], rax
0x1800044ee  lea     rax, [rbp+57h+arg_8]
0x1800044f2  mov     [rsp+110h+var_A8], rax
0x1800044f7  lea     rax, [rbp+57h+arg_10]
0x1800044fb  mov     [rsp+110h+var_B0], rax
0x180004500  lea     rax, [rbp+57h+arg_18]
0x180004504  mov     [rsp+110h+var_B8], rax
0x180004509  lea     rax, [rbp+57h+var_90]
0x18000450d  mov     [rsp+110h+var_C0], rax
0x180004512  lea     rax, [rbp+57h+var_8C]
0x180004516  mov     [rsp+110h+var_C8], rax
0x18000451b  lea     rax, [rbp+57h+var_88]
0x18000451f  mov     qword ptr [rsp+110h+rop], rax
0x180004524  lea     rax, [rbp+57h+var_84]
0x180004528  mov     qword ptr [rsp+110h+y1], rax
0x18000452d  lea     rax, [rbp+57h+var_80]
0x180004531  mov     qword ptr [rsp+110h+x1], rax
0x180004536  lea     rax, [rbp+57h+var_7C]
0x18000453a  mov     [rsp+110h+hdcSrc], rax
0x18000453f  lea     rax, [rbp+57h+var_50]
0x180004543  mov     qword ptr [rsp+110h+cy], rax
0x180004548  mov     [rbp+57h+arg_8], r15d
0x18000454c  mov     [rbp+57h+arg_10], r14d
0x180004550  mov     [rbp+57h+arg_18], esi
0x180004553  mov     [rbp+57h+var_90], r12d
0x180004557  mov     [rbp+57h+var_8C], r15d
0x18000455b  mov     [rbp+57h+var_88], r14d
0x18000455f  mov     [rbp+57h+var_84], esi
0x180004562  mov     [rbp+57h+var_7C], ebx
0x180004565  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000456a  mov     rcx, [rdi+48h]; hdc
0x18000456e  mov     rdx, r13; hrgn
0x180004571  call    cs:__imp_SelectClipRgn
0x180004577  mov     rcx, [rdi+48h]; hdc
0x18000457b  lea     r10d, [rsi+rbx]
0x18000457f  mov     r13d, [rbp+57h+var_70.top]
0x180004583  mov     eax, r12d
0x180004586  mov     [rsp+110h+rop], 0CC0020h; rop
0x18000458e  mov     r9d, r15d
0x180004591  mov     [rsp+110h+y1], r14d; y1
0x180004596  sub     eax, r14d
0x180004599  mov     [rsp+110h+x1], esi; x1
0x18000459d  sub     r9d, esi; cx
0x1800045a0  mov     [rsp+110h+hdcSrc], rcx; hdcSrc
0x1800045a5  lea     r8d, [r14+r13]; y
0x1800045a9  mov     edx, r10d; x
0x1800045ac  mov     [rbp+57h+arg_0], r10d
0x1800045b0  mov     [rsp+110h+cy], eax; cy
0x1800045b4  call    cs:__imp_BitBlt
0x1800045ba  mov     rcx, [rdi+390h]
0x1800045c1  test    rcx, rcx
0x1800045c4  jz      short loc_180004603
0x1800045c6  mov     rax, [rdi+384h]
0x1800045cd  lea     rdx, [rbp+57h+var_70]
0x1800045d1  mov     qword ptr [rbp+57h+var_70.left], rax
0x1800045d5  mov     eax, [rdi+38Ch]
0x1800045db  mov     [rbp+57h+var_70.right], eax
0x1800045de  xor     eax, eax
0x1800045e0  mov     [rbp+57h+var_70.bottom], eax
0x1800045e3  mov     rax, [rdi+60h]
0x1800045e7  mov     [rbp+57h+var_60], rax
0x1800045eb  mov     eax, [rdi+68h]
0x1800045ee  mov     [rbp+57h+var_58], eax
0x1800045f1  mov     eax, [rdi+6Ch]
0x1800045f4  mov     [rbp+57h+var_54], eax
0x1800045f7  mov     rax, [rcx]
0x1800045fa  mov     rax, [rax+40h]
0x1800045fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004603  mov     eax, cs:?g_uiDwmDirectRenderingFlags@@3IA; uint g_uiDwmDirectRenderingFlags
0x180004609  test    al, 1
0x18000460b  jz      short loc_180004647
0x18000460d  mov     eax, [rbp+57h+arg_0]
0x180004610  lea     rdx, [rbp+57h+var_70]; struct tagRECT
0x180004614  mov     r8d, [rdi+0E0h]
0x18000461b  mov     r9b, 2; unsigned __int8
0x18000461e  mov     rcx, [rdi+48h]; hdc
0x180004622  mov     [rbp+57h+var_70.left], eax
0x180004625  lea     eax, [r14+r13]
0x180004629  mov     [rbp+57h+var_70.top], eax
0x18000462c  lea     eax, [r15+rbx]
0x180004630  mov     r8, [rdi+r8*8+0E8h]; HPEN
0x180004638  mov     [rbp+57h+var_70.right], eax
0x18000463b  lea     eax, [r12+r13]
0x18000463f  mov     [rbp+57h+var_70.bottom], eax
0x180004642  call    ?DrawRectangleToDC@@YAXPEAUHDC__@@UtagRECT@@PEAUHPEN__@@E@Z; DrawRectangleToDC(HDC__ *,tagRECT,HPEN__ *,uchar)
0x180004647  mov     rcx, [rdi+48h]; hdc
0x18000464b  xor     edx, edx; hrgn
0x18000464d  call    cs:__imp_SelectClipRgn
0x180004653  xor     eax, eax
0x180004655  add     rsp, 0D8h
0x18000465c  pop     r15
0x18000465e  pop     r14
0x180004660  pop     r13
0x180004662  pop     r12
0x180004664  pop     rdi
0x180004665  pop     rsi
0x180004666  pop     rbx
0x180004667  pop     rbp
0x180004668  retn
```
