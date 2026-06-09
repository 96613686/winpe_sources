# OSKDuiFrame::Create(DirectUI::NativeHWNDHost *,DirectUI::Element * *,HINSTANCE__ *,uint,DirectUI::Element *,ulong *)

- ea: `0x14000ecc8`
- end: `0x14000ed51`
- name: `?Create@OSKDuiFrame@@SAJPEAVNativeHWNDHost@DirectUI@@PEAPEAVElement@3@PEAUHINSTANCE__@@IPEAV43@PEAK@Z`
- size: `137`
- prototype: `__int64 __fastcall(struct DirectUI::NativeHWNDHost *, struct DirectUI::Element **, HINSTANCE, unsigned int, struct DirectUI::Element *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007f54`

## callees

- `0x14000eb90`
- `0x14000ecc8`
- `0x14000f098`

## import_xrefs

- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x14000ed29`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x14000ed29`

## pseudocode

```c
__int64 __fastcall OSKDuiFrame::Create(
        struct DirectUI::NativeHWNDHost *a1,
        struct DirectUI::Element **a2,
        HINSTANCE a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        unsigned int *a6)
{
  bool v6; // zf
  HINSTANCE v9; // rdi
  OSKDuiFrame *v10; // rbx
  __int64 v11; // r9
  int v12; // edi
  struct DirectUI::Element *v14; // [rsp+20h] [rbp-38h]

  v6 = OSKDuiFrame::s_pThis == 0;
  *a2 = 0;
  if ( v6 )
  {
    v9 = g_hInstance;
    v10 = (OSKDuiFrame *)DirectUI::HNew<OSKDuiFrame>(a1, a2, a3);
    if ( v10 )
    {
      v12 = OSKDuiFrame::Initialize(v10, a1, v9, v11, v14, a6);
      if ( v12 >= 0 )
        OSKDuiFrame::s_pThis = v10;
      else
        DirectUI::Element::Destroy(v10, 1);
    }
    else
    {
      v12 = -2147024882;
    }
  }
  else
  {
    v12 = 0;
  }
  *a2 = OSKDuiFrame::s_pThis;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000ecc8  push    rbx
0x14000ecca  push    rbp
0x14000eccb  push    rsi
0x14000eccc  push    rdi
0x14000eccd  sub     rsp, 38h
0x14000ecd1  cmp     cs:?s_pThis@OSKDuiFrame@@1PEAV1@EA, 0; OSKDuiFrame * OSKDuiFrame::s_pThis
0x14000ecd9  mov     rsi, rdx
0x14000ecdc  mov     rbp, rcx
0x14000ecdf  mov     qword ptr [rdx], 0
0x14000ece6  jnz     short loc_14000ED3A
0x14000ece8  mov     rdi, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14000ecef  call    ??$HNew@VOSKDuiFrame@@@DirectUI@@YAPEAVOSKDuiFrame@@XZ; DirectUI::HNew<OSKDuiFrame>(void)
0x14000ecf4  mov     rbx, rax
0x14000ecf7  test    rax, rax
0x14000ecfa  jnz     short loc_14000ED03
0x14000ecfc  mov     edi, 8007000Eh
0x14000ed01  jmp     short loc_14000ED3C
0x14000ed03  mov     rax, [rsp+58h+arg_28]
0x14000ed0b  mov     r8, rdi; HINSTANCE
0x14000ed0e  mov     rdx, rbp; struct DirectUI::NativeHWNDHost *
0x14000ed11  mov     [rsp+58h+var_30], rax; unsigned int *
0x14000ed16  mov     rcx, rbx; this
0x14000ed19  call    ?Initialize@OSKDuiFrame@@QEAAJPEAVNativeHWNDHost@DirectUI@@PEAUHINSTANCE__@@HPEAVElement@3@PEAK@Z; OSKDuiFrame::Initialize(DirectUI::NativeHWNDHost *,HINSTANCE__ *,int,DirectUI::Element *,ulong *)
0x14000ed1e  mov     edi, eax
0x14000ed20  test    eax, eax
0x14000ed22  jns     short loc_14000ED31
0x14000ed24  mov     dl, 1
0x14000ed26  mov     rcx, rbx
0x14000ed29  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x14000ed2f  jmp     short loc_14000ED3C
0x14000ed31  mov     cs:?s_pThis@OSKDuiFrame@@1PEAV1@EA, rbx; OSKDuiFrame * OSKDuiFrame::s_pThis
0x14000ed38  jmp     short loc_14000ED3C
0x14000ed3a  xor     edi, edi
0x14000ed3c  mov     rax, cs:?s_pThis@OSKDuiFrame@@1PEAV1@EA; OSKDuiFrame * OSKDuiFrame::s_pThis
0x14000ed43  mov     [rsi], rax
0x14000ed46  mov     eax, edi
0x14000ed48  add     rsp, 38h
0x14000ed4c  pop     rdi
0x14000ed4d  pop     rsi
0x14000ed4e  pop     rbp
0x14000ed4f  pop     rbx
0x14000ed50  retn
```
