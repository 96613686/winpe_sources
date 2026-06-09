# CDropTarget::DragEnter(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x18005ad80`
- end: `0x18005af46`
- name: `?DragEnter@CDropTarget@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `454`
- prototype: `int(CDropTarget *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x1800274a0`
- `0x18002a6f0`
- `0x18002c650`
- `0x18002dfac`
- `0x18003f11c`
- `0x18005ad24`
- `0x18005ad4c`
- `0x18005ad80`
- `0x18006de24`
- `0x180095010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18005ae6f`
- `GDI32!GetDeviceCaps` at `0x18005ae6f`

## pseudocode

```c
__int64 __fastcall CDropTarget::DragEnter(
        CDropTarget *this,
        struct IDataObject *a2,
        unsigned int a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  bool v5; // zf
  CCallMgr *v11; // rax
  unsigned int v12; // ebp
  unsigned int CanPaste; // eax
  unsigned int v14; // edx
  _QWORD *v15; // rax
  unsigned int v16; // edx
  _QWORD *v17; // rsi
  HDC DC; // rax
  int DeviceCaps; // eax
  HDC v20; // rdx
  CDropCaret *v21; // rcx
  struct CTxtSelection *Sel; // rax
  __int64 v23; // rax
  CCallMgr *v24; // rcx

  v5 = *((_QWORD *)this + 2) == 0;
  *((_DWORD *)this + 14) = -1;
  if ( v5 )
    return 2147746303LL;
  v11 = (CCallMgr *)CW32System::PvAlloc(0x20u, 0x40u);
  if ( v11 )
    v11 = CCallMgr::CCallMgr(v11, *((struct CTxtEdit **)this + 2));
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 2147942414LL;
  v12 = 1;
  CanPaste = CLightDTEngine::CanPaste((CLightDTEngine *)(*((_QWORD *)this + 2) + 96LL), a2, 0, 1u);
  if ( CanPaste )
  {
    if ( CanPaste == 0x80000000 )
      *((_DWORD *)this + 3) |= 0x80000000;
    v15 = CW32System::PvAlloc(0x48u, 0x40u);
    v17 = v15;
    if ( v15 )
    {
      *v15 = *((_QWORD *)this + 2);
      v15[1] = 0;
      *((_DWORD *)v15 + 5) = -1;
      v15[5] = 0;
    }
    else
    {
      v17 = 0;
    }
    *((_QWORD *)this + 8) = v17;
    if ( !v17
      || (DC = CDevDesc::GetDC((CDevDesc *)(*(_QWORD *)(*v17 + 64LL) + 16LL)), (v17[1] = DC) == 0)
      || (DeviceCaps = GetDeviceCaps(DC, 90),
          v20 = (HDC)v17[1],
          *((_DWORD *)v17 + 4) = DeviceCaps,
          *((_DWORD *)v17 + 6) = 32,
          !COffScreenDC::Init((COffScreenDC *)(v17 + 5), v20, 1, 32, 0xFFFFFFFF)) )
    {
      v21 = (CDropCaret *)*((_QWORD *)this + 8);
      if ( v21 )
        CDropCaret::`scalar deleting destructor'(v21, v16);
      *((_QWORD *)this + 8) = 0;
    }
    Sel = CTxtEdit::GetSel(*((CTxtEdit **)this + 2));
    if ( Sel )
    {
      *((_DWORD *)this + 12) = *((_DWORD *)Sel + 10);
      *((_DWORD *)this + 13) = *((_DWORD *)Sel + 22);
    }
    v23 = *(_QWORD *)this;
    *((_DWORD *)this + 3) |= 0x40000000u;
    v12 = (*(__int64 (__fastcall **)(CDropTarget *, _QWORD, struct _POINTL, unsigned int *))(v23 + 32))(
            this,
            a3,
            a4,
            a5);
    if ( !v12 )
      return v12;
    goto LABEL_22;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 180LL) & 0x8000000) == 0 )
  {
LABEL_22:
    v24 = (CCallMgr *)*((_QWORD *)this + 3);
    if ( v24 )
      CCallMgr::`scalar deleting destructor'(v24, v14);
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 3) = 0;
    return v12;
  }
  v12 = 0;
  *a5 = 0;
  return v12;
}

```

## disassembly

```asm
0x18005ad80  push    rbx
0x18005ad82  push    rbp
0x18005ad83  push    rsi
0x18005ad84  push    rdi
0x18005ad85  push    r14
0x18005ad87  sub     rsp, 30h
0x18005ad8b  cmp     qword ptr [rcx+10h], 0
0x18005ad90  mov     rbx, r9
0x18005ad93  mov     r14d, r8d
0x18005ad96  mov     dword ptr [rcx+38h], 0FFFFFFFFh
0x18005ad9d  mov     rsi, rdx
0x18005ada0  mov     rdi, rcx
0x18005ada3  jnz     short loc_18005ADAF
0x18005ada5  mov     eax, 800401FFh
0x18005adaa  jmp     loc_18005AF1C
0x18005adaf  mov     edx, 40h ; '@'; unsigned int
0x18005adb4  lea     ecx, [rdx-20h]; unsigned int
0x18005adb7  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005adbc  test    rax, rax
0x18005adbf  jz      short loc_18005ADCD
0x18005adc1  mov     rdx, [rdi+10h]; struct CTxtEdit *
0x18005adc5  mov     rcx, rax; this
0x18005adc8  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x18005adcd  mov     [rdi+18h], rax
0x18005add1  test    rax, rax
0x18005add4  jnz     short loc_18005ADE0
0x18005add6  mov     eax, 8007000Eh
0x18005addb  jmp     loc_18005AF1C
0x18005ade0  mov     rcx, [rdi+10h]
0x18005ade4  xor     r8d, r8d; unsigned __int16
0x18005ade7  add     rcx, 60h ; '`'; this
0x18005adeb  mov     rdx, rsi; struct IDataObject *
0x18005adee  lea     ebp, [r8+1]
0x18005adf2  mov     r9d, ebp; unsigned int
0x18005adf5  call    ?CanPaste@CLightDTEngine@@QEAAKPEAUIDataObject@@GK@Z; CLightDTEngine::CanPaste(IDataObject *,ushort,ulong)
0x18005adfa  test    eax, eax
0x18005adfc  jz      loc_18005AF28
0x18005ae02  mov     ecx, 80000000h
0x18005ae07  cmp     eax, ecx
0x18005ae09  jnz     short loc_18005AE0E
0x18005ae0b  or      [rdi+0Ch], ecx
0x18005ae0e  mov     edx, 40h ; '@'; unsigned int
0x18005ae13  lea     ecx, [rdx+8]; unsigned int
0x18005ae16  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005ae1b  mov     rsi, rax
0x18005ae1e  test    rax, rax
0x18005ae21  jz      short loc_18005AE43
0x18005ae23  mov     rcx, [rdi+10h]
0x18005ae27  mov     [rax], rcx
0x18005ae2a  mov     qword ptr [rax+8], 0
0x18005ae32  mov     dword ptr [rax+14h], 0FFFFFFFFh
0x18005ae39  mov     qword ptr [rax+28h], 0
0x18005ae41  jmp     short loc_18005AE45
0x18005ae43  xor     esi, esi
0x18005ae45  mov     [rdi+40h], rsi
0x18005ae49  test    rsi, rsi
0x18005ae4c  jz      short loc_18005AEA5
0x18005ae4e  mov     rax, [rsi]
0x18005ae51  mov     rcx, [rax+40h]
0x18005ae55  add     rcx, 10h; this
0x18005ae59  call    ?GetDC@CDevDesc@@QEBAPEAUHDC__@@XZ; CDevDesc::GetDC(void)
0x18005ae5e  mov     [rsi+8], rax
0x18005ae62  test    rax, rax
0x18005ae65  jz      short loc_18005AEA5
0x18005ae67  mov     edx, 5Ah ; 'Z'; index
0x18005ae6c  mov     rcx, rax; hdc
0x18005ae6f  call    cs:__imp_GetDeviceCaps
0x18005ae76  nop     dword ptr [rax+rax+00h]
0x18005ae7b  mov     rdx, [rsi+8]; hdc
0x18005ae7f  lea     rcx, [rsi+28h]; this
0x18005ae83  mov     r9d, 20h ; ' '; cy
0x18005ae89  mov     [rsi+10h], eax
0x18005ae8c  mov     r8d, ebp; cx
0x18005ae8f  mov     [rsi+18h], r9d
0x18005ae93  mov     [rsp+58h+color], 0FFFFFFFFh; color
0x18005ae9b  call    ?Init@COffScreenDC@@QEAAPEAUHDC__@@PEAU2@JJK@Z; COffScreenDC::Init(HDC__ *,long,long,ulong)
0x18005aea0  test    rax, rax
0x18005aea3  jnz     short loc_18005AEBB
0x18005aea5  mov     rcx, [rdi+40h]; this
0x18005aea9  test    rcx, rcx
0x18005aeac  jz      short loc_18005AEB3
0x18005aeae  call    ??_GCDropCaret@@QEAAPEAXI@Z; CDropCaret::`scalar deleting destructor'(uint)
0x18005aeb3  mov     qword ptr [rdi+40h], 0
0x18005aebb  mov     rcx, [rdi+10h]; this
0x18005aebf  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18005aec4  test    rax, rax
0x18005aec7  jz      short loc_18005AED5
0x18005aec9  mov     ecx, [rax+28h]
0x18005aecc  mov     [rdi+30h], ecx
0x18005aecf  mov     eax, [rax+58h]
0x18005aed2  mov     [rdi+34h], eax
0x18005aed5  mov     rax, [rdi]
0x18005aed8  mov     r8, rbx
0x18005aedb  mov     r9, [rsp+58h+arg_20]
0x18005aee3  mov     edx, r14d
0x18005aee6  bts     dword ptr [rdi+0Ch], 1Eh
0x18005aeeb  mov     rcx, rdi
0x18005aeee  mov     rax, [rax+20h]
0x18005aef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aef7  mov     ebp, eax
0x18005aef9  test    eax, eax
0x18005aefb  jz      short loc_18005AF1A
0x18005aefd  mov     rcx, [rdi+18h]; this
0x18005af01  test    rcx, rcx
0x18005af04  jz      short loc_18005AF0B
0x18005af06  call    ??_GCCallMgr@@QEAAPEAXI@Z; CCallMgr::`scalar deleting destructor'(uint)
0x18005af0b  mov     qword ptr [rdi+18h], 0
0x18005af13  mov     dword ptr [rdi+0Ch], 0
0x18005af1a  mov     eax, ebp
0x18005af1c  add     rsp, 30h
0x18005af20  pop     r14
0x18005af22  pop     rdi
0x18005af23  pop     rsi
0x18005af24  pop     rbp
0x18005af25  pop     rbx
0x18005af26  retn
0x18005af28  mov     rax, [rdi+10h]
0x18005af2c  test    dword ptr [rax+0B4h], 8000000h
0x18005af36  jz      short loc_18005AEFD
0x18005af38  mov     rax, [rsp+58h+arg_20]
0x18005af40  xor     ebp, ebp
0x18005af42  mov     [rax], ebp
0x18005af44  jmp     short loc_18005AF1A
```
