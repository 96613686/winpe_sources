# CBody::UnloadAll(void)

- ea: `0x18007fa88`
- end: `0x18007fc92`
- name: `?UnloadAll@CBody@@QEAAJXZ`
- size: `522`
- prototype: `__int64 __fastcall(CBody *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x180069720`
- `0x180069ed0`
- `0x1800775e0`
- `0x18007a4e4`

## callees

- `0x180002098`
- `0x18001f838`
- `0x180022a98`
- `0x180022d4c`
- `0x180063e6c`
- `0x18007fa88`
- `0x1800cc9ba`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!FreeTempFileList` at `0x18007fb68`
- `MSOERT2!FreeTempFileList` at `0x18007fb68`
- `USER32!InvalidateRect` at `0x18007faca`
- `USER32!InvalidateRect` at `0x18007faca`
- `USER32!KillTimer` at `0x18007fab1`
- `USER32!KillTimer` at `0x18007fab1`
- `ole32!CoTaskMemFree` at `0x18007fb4b`
- `ole32!CoTaskMemFree` at `0x18007fb4b`

## pseudocode

```c
__int64 __fastcall CBody::UnloadAll(CBody *this)
{
  int v1; // eax
  HWND v3; // rcx
  struct IUnknown *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  HDC v7; // rdx

  v1 = *((_DWORD *)this + 68);
  if ( (v1 & 0x10) != 0 )
  {
    *((_DWORD *)this + 68) = v1 & 0xFFFFFFEF;
    KillTimer(*((HWND *)this + 13), 0x6Eu);
  }
  v3 = (HWND)*((_QWORD *)this + 13);
  if ( v3 )
    InvalidateRect(v3, 0, 1);
  if ( (*((_BYTE *)this + 272) & 1) == 0 )
  {
    v4 = (struct IUnknown *)*((_QWORD *)this + 11);
    if ( v4 )
      HrInitNew(v4);
    if ( (*((_DWORD *)this + 68) & 0x1000) == 0 )
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 624);
    OE_SafeReleaseAndNullPtr<CAttMenu>((char *)this + 560);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 280);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 288);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 536);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 632);
    v5 = (void *)*((_QWORD *)this + 38);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *((_QWORD *)this + 38) = 0;
    }
    if ( *((_QWORD *)this + 39) )
    {
      FreeTempFileList();
      *((_QWORD *)this + 39) = 0;
    }
    if ( *((_QWORD *)this + 64) )
    {
      ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
      *((_QWORD *)this + 64) = 0;
    }
    memset_0(*((void **)this + 57), 0, 2LL * *((unsigned int *)this + 112));
    *((_DWORD *)this + 112) = 0;
    memset_0(*((void **)this + 61), 0, 2LL * *((unsigned int *)this + 120));
    *((_DWORD *)this + 120) = 0;
    memset_0(*((void **)this + 53), 0, 2LL * *((unsigned int *)this + 104));
    *((_DWORD *)this + 104) = 0;
    if ( *((_DWORD *)this + 81) == 1 )
      CBody::UpdateBtnBar(this);
    *((_DWORD *)this + 68) &= ~0x40u;
    *((_DWORD *)this + 68) |= 1u;
    *((_DWORD *)this + 60) = 0;
    *((_QWORD *)this + 33) = 0;
    *(_QWORD *)((char *)this + 668) = 0;
  }
  v6 = *((_QWORD *)this + 82);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 56LL))(v6);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 656);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 648);
  CBody::RecalcPreviewHeight(this, v7);
  *((_DWORD *)this + 68) |= 0x100u;
  return 0;
}

```

## disassembly

```asm
0x18007fa88  mov     [rsp+arg_0], rbx
0x18007fa8d  push    rdi
0x18007fa8e  sub     rsp, 20h
0x18007fa92  mov     eax, [rcx+110h]
0x18007fa98  mov     rbx, rcx
0x18007fa9b  test    al, 10h
0x18007fa9d  jz      short loc_18007FAB7
0x18007fa9f  and     eax, 0FFFFFFEFh
0x18007faa2  mov     edx, 6Eh ; 'n'; uIDEvent
0x18007faa7  mov     [rcx+110h], eax
0x18007faad  mov     rcx, [rcx+68h]; hWnd
0x18007fab1  call    cs:__imp_KillTimer
0x18007fab7  mov     rcx, [rbx+68h]; hWnd
0x18007fabb  mov     edi, 1
0x18007fac0  test    rcx, rcx
0x18007fac3  jz      short loc_18007FAD0
0x18007fac5  mov     r8d, edi; bErase
0x18007fac8  xor     edx, edx; lpRect
0x18007faca  call    cs:__imp_InvalidateRect
0x18007fad0  test    [rbx+110h], dil
0x18007fad7  jnz     loc_18007FC46
0x18007fadd  mov     rcx, [rbx+58h]; struct IUnknown *
0x18007fae1  test    rcx, rcx
0x18007fae4  jz      short loc_18007FAEB
0x18007fae6  call    ?HrInitNew@@YAJPEAUIUnknown@@@Z; HrInitNew(IUnknown *)
0x18007faeb  test    dword ptr [rbx+110h], 1000h
0x18007faf5  jnz     short loc_18007FB03
0x18007faf7  lea     rcx, [rbx+270h]
0x18007fafe  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fb03  lea     rcx, [rbx+230h]
0x18007fb0a  call    ??$OE_SafeReleaseAndNullPtr@VCAttMenu@@@@YAXAEAPEAVCAttMenu@@@Z; OE_SafeReleaseAndNullPtr<CAttMenu>(CAttMenu * &)
0x18007fb0f  lea     rcx, [rbx+118h]
0x18007fb16  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fb1b  lea     rcx, [rbx+120h]
0x18007fb22  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fb27  lea     rcx, [rbx+218h]
0x18007fb2e  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fb33  lea     rcx, [rbx+278h]
0x18007fb3a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fb3f  mov     rcx, [rbx+130h]; pv
0x18007fb46  test    rcx, rcx
0x18007fb49  jz      short loc_18007FB5C
0x18007fb4b  call    cs:__imp_CoTaskMemFree
0x18007fb51  mov     qword ptr [rbx+130h], 0
0x18007fb5c  mov     rcx, [rbx+138h]
0x18007fb63  test    rcx, rcx
0x18007fb66  jz      short loc_18007FB79
0x18007fb68  call    cs:__imp_FreeTempFileList
0x18007fb6e  mov     qword ptr [rbx+138h], 0
0x18007fb79  mov     rdx, [rbx+200h]
0x18007fb80  test    rdx, rdx
0x18007fb83  jz      short loc_18007FBA3
0x18007fb85  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007fb8c  mov     rax, [rcx]
0x18007fb8f  mov     rax, [rax+28h]
0x18007fb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fb98  mov     qword ptr [rbx+200h], 0
0x18007fba3  mov     r8d, [rbx+1C0h]
0x18007fbaa  xor     edx, edx; Val
0x18007fbac  mov     rcx, [rbx+1C8h]; void *
0x18007fbb3  add     r8, r8; Size
0x18007fbb6  call    memset_0
0x18007fbbb  mov     dword ptr [rbx+1C0h], 0
0x18007fbc5  xor     edx, edx; Val
0x18007fbc7  mov     r8d, [rbx+1E0h]
0x18007fbce  mov     rcx, [rbx+1E8h]; void *
0x18007fbd5  add     r8, r8; Size
0x18007fbd8  call    memset_0
0x18007fbdd  mov     dword ptr [rbx+1E0h], 0
0x18007fbe7  xor     edx, edx; Val
0x18007fbe9  mov     r8d, [rbx+1A0h]
0x18007fbf0  mov     rcx, [rbx+1A8h]; void *
0x18007fbf7  add     r8, r8; Size
0x18007fbfa  call    memset_0
0x18007fbff  mov     dword ptr [rbx+1A0h], 0
0x18007fc09  cmp     [rbx+144h], edi
0x18007fc0f  jnz     short loc_18007FC19
0x18007fc11  mov     rcx, rbx; this
0x18007fc14  call    ?UpdateBtnBar@CBody@@AEAAJXZ; CBody::UpdateBtnBar(void)
0x18007fc19  and     dword ptr [rbx+110h], 0FFFFFFBFh
0x18007fc20  or      [rbx+110h], edi
0x18007fc26  mov     dword ptr [rbx+0F0h], 0
0x18007fc30  mov     qword ptr [rbx+108h], 0
0x18007fc3b  mov     qword ptr [rbx+29Ch], 0
0x18007fc46  lea     rdi, [rbx+290h]
0x18007fc4d  mov     rcx, [rdi]
0x18007fc50  test    rcx, rcx
0x18007fc53  jz      short loc_18007FC69
0x18007fc55  mov     rax, [rcx]
0x18007fc58  mov     rax, [rax+38h]
0x18007fc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007fc61  mov     rcx, rdi
0x18007fc64  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fc69  lea     rcx, [rbx+288h]
0x18007fc70  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007fc75  mov     rcx, rbx; this
0x18007fc78  call    ?RecalcPreviewHeight@CBody@@AEAAJPEAUHDC__@@@Z; CBody::RecalcPreviewHeight(HDC__ *)
0x18007fc7d  bts     dword ptr [rbx+110h], 8
0x18007fc85  mov     rbx, [rsp+28h+arg_0]
0x18007fc8a  xor     eax, eax
0x18007fc8c  add     rsp, 20h
0x18007fc90  pop     rdi
0x18007fc91  retn
```
