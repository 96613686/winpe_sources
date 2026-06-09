# CRestoreSession::FinalRelease(void)

- ea: `0x180023fcc`
- end: `0x1800240d1`
- name: `?FinalRelease@CRestoreSession@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(CRestoreSession *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003008`
- `0x1800030f4`

## callees

- `0x180004308`
- `0x180006300`
- `0x18000801c`
- `0x18000a184`
- `0x180023fcc`

## import_xrefs

- `msvcrt!free` at `0x180024026`
- `msvcrt!free` at `0x18002406b`
- `msvcrt!free` at `0x180024026`
- `msvcrt!free` at `0x18002406b`
- `KERNEL32!DeleteCriticalSection` at `0x180023fe0`
- `KERNEL32!DeleteCriticalSection` at `0x180023fe0`
- `KERNEL32!CloseHandle` at `0x180023ff3`
- `KERNEL32!CloseHandle` at `0x180023ff3`

## pseudocode

```c
void __fastcall CRestoreSession::FinalRelease(CRestoreSession *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  _QWORD *v6; // rdi

  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  v2 = (void *)*((_QWORD *)this + 30);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 30) = -1;
  }
  v3 = *((_QWORD *)this + 31);
  v4 = (_QWORD *)((char *)this + 256);
  if ( v3 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      v3,
      *v4);
    free(*((void **)this + 31));
    *((_QWORD *)this + 31) = 0;
  }
  *v4 = 0;
  *((_QWORD *)this + 33) = 0;
  v5 = *((_QWORD *)this + 35);
  v6 = (_QWORD *)((char *)this + 288);
  if ( v5 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      v5,
      *v6);
    free(*((void **)this + 35));
    *((_QWORD *)this + 35) = 0;
  }
  *v6 = 0;
  *((_QWORD *)this + 37) = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty((_QWORD *)this + 43);
  ATL::CSimpleStringT<unsigned short,0>::Empty((_QWORD *)this + 44);
  ATL::CSimpleStringT<unsigned short,0>::Empty((_QWORD *)this + 45);
  ATL::CRBTree<long,int,ATL::CElementTraits<long>,ATL::CElementTraits<int>>::RemoveAll((char *)this + 384);
  CSessionBaseRO::FinalRelease((CRestoreSession *)((char *)this + 64));
}

```

## disassembly

```asm
0x180023fcc  mov     [rsp+arg_0], rbx
0x180023fd1  push    rdi
0x180023fd2  sub     rsp, 20h
0x180023fd6  mov     rbx, rcx
0x180023fd9  add     rcx, 0C8h; lpCriticalSection
0x180023fe0  call    cs:__imp_DeleteCriticalSection
0x180023fe6  mov     rcx, [rbx+0F0h]; hObject
0x180023fed  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180023ff1  jz      short loc_180024004
0x180023ff3  call    cs:__imp_CloseHandle
0x180023ff9  mov     qword ptr [rbx+0F0h], 0FFFFFFFFFFFFFFFFh
0x180024004  mov     rcx, [rbx+0F8h]
0x18002400b  lea     rdi, [rbx+100h]
0x180024012  test    rcx, rcx
0x180024015  jz      short loc_180024037
0x180024017  mov     rdx, [rdi]
0x18002401a  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18002401f  mov     rcx, [rbx+0F8h]; Block
0x180024026  call    cs:__imp_free
0x18002402c  mov     qword ptr [rbx+0F8h], 0
0x180024037  mov     qword ptr [rdi], 0
0x18002403e  mov     qword ptr [rbx+108h], 0
0x180024049  mov     rcx, [rbx+118h]
0x180024050  lea     rdi, [rbx+120h]
0x180024057  test    rcx, rcx
0x18002405a  jz      short loc_18002407C
0x18002405c  mov     rdx, [rdi]
0x18002405f  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x180024064  mov     rcx, [rbx+118h]; Block
0x18002406b  call    cs:__imp_free
0x180024071  mov     qword ptr [rbx+118h], 0
0x18002407c  mov     qword ptr [rdi], 0
0x180024083  mov     qword ptr [rbx+128h], 0
0x18002408e  lea     rcx, [rbx+158h]
0x180024095  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18002409a  lea     rcx, [rbx+160h]
0x1800240a1  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800240a6  lea     rcx, [rbx+168h]
0x1800240ad  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800240b2  lea     rcx, [rbx+180h]
0x1800240b9  call    ?RemoveAll@?$CRBTree@JHV?$CElementTraits@J@ATL@@V?$CElementTraits@H@2@@ATL@@QEAAXXZ; ATL::CRBTree<long,int,ATL::CElementTraits<long>,ATL::CElementTraits<int>>::RemoveAll(void)
0x1800240be  lea     rcx, [rbx+40h]; this
0x1800240c2  mov     rbx, [rsp+28h+arg_0]
0x1800240c7  add     rsp, 20h
0x1800240cb  pop     rdi
0x1800240cc  jmp     ?FinalRelease@CSessionBaseRO@@IEAAXXZ; CSessionBaseRO::FinalRelease(void)
```
