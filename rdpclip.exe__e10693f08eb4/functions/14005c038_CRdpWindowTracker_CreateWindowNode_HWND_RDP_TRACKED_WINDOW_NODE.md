# CRdpWindowTracker::CreateWindowNode(HWND__ *,RDP_TRACKED_WINDOW_NODE * *)

- ea: `0x14005c038`
- end: `0x14005c270`
- name: `?CreateWindowNode@CRdpWindowTracker@@AEAAJPEAUHWND__@@PEAPEAURDP_TRACKED_WINDOW_NODE@@@Z`
- size: `568`
- prototype: `int(CRdpWindowTracker *__hidden this, HWND, struct RDP_TRACKED_WINDOW_NODE **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005f1c0`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x140011054`
- `0x14005c038`
- `0x14005c278`
- `0x14005c788`
- `0x14005fe84`
- `0x14006b010`

## import_xrefs

- `USER32!IsWindowVisible` at `0x14005c0fb`
- `USER32!IsWindowVisible` at `0x14005c0fb`
- `USER32!GetParent` at `0x14005c0e2`
- `USER32!GetParent` at `0x14005c0e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005c067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005c067`
- `GDI32!CreateRectRgn` at `0x14005c1e2`
- `GDI32!CreateRectRgn` at `0x14005c1e2`

## string_xrefs

- `0x14005c220`: `CreateRectRgn() failed`
- `0x14005c099`: `"CoTaskMemAlloc( RDP_TRACKED_WINDOW_NODE )"`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::CreateWindowNode(
        CRdpWindowTracker *this,
        HWND a2,
        struct RDP_TRACKED_WINDOW_NODE **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  unsigned int v8; // eax
  int v9; // edi
  CRdpWindowTracker *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  CRdpWindowTracker *v13; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v15; // r15d
  __int64 v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // r8
  HRGN RectRgn; // rax
  unsigned int v20; // eax
  __int64 v22; // [rsp+28h] [rbp-40h]
  int v23; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = CoTaskMemAlloc(0x70u);
  v7 = v6;
  if ( v6 )
  {
    v9 = 0;
    memset_0(v6, 0, 0x70u);
    v7[2] = a2;
    v7[3] = GetParent(a2);
    v7[4] = CRdpWindowTracker::GetTopLevelParent(v10, a2);
    *((_DWORD *)v7 + 10) = IsWindowVisible(a2);
    *((_DWORD *)v7 + 26) = 1;
    v11 = *((_QWORD *)this + 10);
    if ( v11 )
    {
      v12 = v7[4];
      v23 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v11 + 24LL))(v11, v12, &v23);
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            113,
            (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"IsWindowOnCurrentVirtualDesktop() failed",
            v9);
        }
        goto LABEL_24;
      }
      v15 = v23;
      *((_DWORD *)v7 + 26) = v23;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v16 = v7[4];
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Diid(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, v18, v17, a2, v16, v15);
      }
    }
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    v7[12] = RectRgn;
    if ( RectRgn )
    {
      *a3 = (struct RDP_TRACKED_WINDOW_NODE *)v7;
      return (unsigned int)v9;
    }
    v9 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v22) = -2147467259;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        115,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v20,
        (__int64)"CreateRectRgn() failed",
        v22);
    }
LABEL_24:
    CRdpWindowTracker::DeleteWindowNode(v13, (struct RDP_TRACKED_WINDOW_NODE *)v7);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v8,
      (__int64)"\"CoTaskMemAlloc( RDP_TRACKED_WINDOW_NODE )\"");
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x14005c038  mov     [rsp+arg_0], rbx
0x14005c03d  mov     [rsp+arg_8], rbp
0x14005c042  push    rsi
0x14005c043  push    rdi
0x14005c044  push    r12
0x14005c046  push    r14
0x14005c048  push    r15
0x14005c04a  sub     rsp, 40h
0x14005c04e  mov     rbx, rcx
0x14005c051  mov     qword ptr [r8], 0
0x14005c058  mov     r15d, 70h ; 'p'
0x14005c05e  mov     r14, r8
0x14005c061  mov     ecx, r15d; cb
0x14005c064  mov     r12, rdx
0x14005c067  call    cs:__imp_CoTaskMemAlloc
0x14005c06d  mov     rsi, rax
0x14005c070  test    rax, rax
0x14005c073  jnz     short loc_14005C0CC
0x14005c075  mov     rax, cs:WPP_GLOBAL_Control
0x14005c07c  lea     rbp, WPP_GLOBAL_Control
0x14005c083  cmp     rax, rbp
0x14005c086  jz      short loc_14005C0C2
0x14005c088  test    byte ptr [rax+1Ch], 8
0x14005c08c  jz      short loc_14005C0C2
0x14005c08e  cmp     byte ptr [rax+19h], 2
0x14005c092  jb      short loc_14005C0C2
0x14005c094  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c099  lea     rcx, aCotaskmemalloc_0; "\"CoTaskMemAlloc( RDP_TRACKED_WINDOW_NO"...
0x14005c0a0  mov     edx, r15d
0x14005c0a3  mov     [rsp+68h+var_48], rcx
0x14005c0a8  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c0af  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c0b6  mov     r9d, eax
0x14005c0b9  mov     rcx, [rcx+10h]
0x14005c0bd  call    WPP_SF_Ds
0x14005c0c2  mov     edi, 8007000Eh
0x14005c0c7  jmp     loc_14005C257
0x14005c0cc  mov     r8, r15; Size
0x14005c0cf  xor     edx, edx; Val
0x14005c0d1  mov     rcx, rsi; void *
0x14005c0d4  xor     edi, edi
0x14005c0d6  call    memset_0
0x14005c0db  mov     rcx, r12; hWnd
0x14005c0de  mov     [rsi+10h], r12
0x14005c0e2  call    cs:__imp_GetParent
0x14005c0e8  mov     rdx, r12; HWND
0x14005c0eb  mov     [rsi+18h], rax
0x14005c0ef  call    ?GetTopLevelParent@CRdpWindowTracker@@AEAAPEAUHWND__@@PEAU2@@Z; CRdpWindowTracker::GetTopLevelParent(HWND__ *)
0x14005c0f4  mov     rcx, r12; hWnd
0x14005c0f7  mov     [rsi+20h], rax
0x14005c0fb  call    cs:__imp_IsWindowVisible
0x14005c101  mov     [rsi+28h], eax
0x14005c104  lea     rbp, WPP_GLOBAL_Control
0x14005c10b  lea     eax, [rdi+1]
0x14005c10e  mov     [rsi+68h], eax
0x14005c111  mov     rcx, [rbx+50h]
0x14005c115  test    rcx, rcx
0x14005c118  jz      loc_14005C1D8
0x14005c11e  mov     rdx, [rsi+20h]
0x14005c122  lea     r8, [rsp+68h+arg_10]
0x14005c12a  mov     [rsp+68h+arg_10], eax
0x14005c131  mov     rax, [rcx]
0x14005c134  mov     rax, [rax+18h]
0x14005c138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005c13d  mov     edi, eax
0x14005c13f  test    eax, eax
0x14005c141  jns     short loc_14005C181
0x14005c143  mov     rax, cs:WPP_GLOBAL_Control
0x14005c14a  cmp     rax, rbp
0x14005c14d  jz      loc_14005C24F
0x14005c153  test    byte ptr [rax+1Ch], 8
0x14005c157  jz      loc_14005C24F
0x14005c15d  cmp     byte ptr [rax+19h], 2
0x14005c161  jb      loc_14005C24F
0x14005c167  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c16c  mov     edx, 71h ; 'q'
0x14005c171  mov     dword ptr [rsp+68h+var_40], edi
0x14005c175  lea     rcx, aIswindowoncurr; "IsWindowOnCurrentVirtualDesktop() faile"...
0x14005c17c  jmp     loc_14005C227
0x14005c181  mov     r15d, [rsp+68h+arg_10]
0x14005c189  mov     [rsi+68h], r15d
0x14005c18d  mov     rax, cs:WPP_GLOBAL_Control
0x14005c194  cmp     rax, rbp
0x14005c197  jz      short loc_14005C1D8
0x14005c199  test    dword ptr [rax+1Ch], 200h
0x14005c1a0  jz      short loc_14005C1D8
0x14005c1a2  cmp     byte ptr [rax+19h], 5
0x14005c1a6  jb      short loc_14005C1D8
0x14005c1a8  mov     rbx, [rsi+20h]
0x14005c1ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c1b8  mov     edx, 72h ; 'r'
0x14005c1bd  mov     [rsp+68h+var_38], r15d
0x14005c1c2  mov     r9d, eax
0x14005c1c5  mov     [rsp+68h+var_40], rbx
0x14005c1ca  mov     [rsp+68h+var_48], r12
0x14005c1cf  mov     rcx, [rcx+10h]
0x14005c1d3  call    WPP_SF_Diid
0x14005c1d8  xor     r9d, r9d; y2
0x14005c1db  xor     r8d, r8d; x2
0x14005c1de  xor     edx, edx; y1
0x14005c1e0  xor     ecx, ecx; x1
0x14005c1e2  call    cs:__imp_CreateRectRgn
0x14005c1e8  mov     [rsi+60h], rax
0x14005c1ec  test    rax, rax
0x14005c1ef  jnz     short loc_14005C248
0x14005c1f1  mov     edi, 80004005h
0x14005c1f6  mov     rax, cs:WPP_GLOBAL_Control
0x14005c1fd  cmp     rax, rbp
0x14005c200  jz      short loc_14005C24F
0x14005c202  test    byte ptr [rax+1Ch], 8
0x14005c206  jz      short loc_14005C24F
0x14005c208  cmp     byte ptr [rax+19h], 2
0x14005c20c  jb      short loc_14005C24F
0x14005c20e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c213  mov     edx, 73h ; 's'
0x14005c218  mov     dword ptr [rsp+68h+var_40], 80004005h
0x14005c220  lea     rcx, aCreaterectrgnF; "CreateRectRgn() failed"
0x14005c227  mov     [rsp+68h+var_48], rcx
0x14005c22c  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c233  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c23a  mov     r9d, eax
0x14005c23d  mov     rcx, [rcx+10h]
0x14005c241  call    WPP_SF_DsD
0x14005c246  jmp     short loc_14005C24F
0x14005c248  mov     [r14], rsi
0x14005c24b  test    edi, edi
0x14005c24d  jns     short loc_14005C257
0x14005c24f  mov     rdx, rsi; struct RDP_TRACKED_WINDOW_NODE *
0x14005c252  call    ?DeleteWindowNode@CRdpWindowTracker@@AEAAXPEAURDP_TRACKED_WINDOW_NODE@@@Z; CRdpWindowTracker::DeleteWindowNode(RDP_TRACKED_WINDOW_NODE *)
0x14005c257  mov     rbx, [rsp+68h+arg_0]
0x14005c25c  mov     eax, edi
0x14005c25e  mov     rbp, [rsp+68h+arg_8]
0x14005c263  add     rsp, 40h
0x14005c267  pop     r15
0x14005c269  pop     r14
0x14005c26b  pop     r12
0x14005c26d  pop     rdi
0x14005c26e  pop     rsi
0x14005c26f  retn
```
