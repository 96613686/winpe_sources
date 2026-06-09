# CFwProfileViewRead::Initialize(DirectUI::Element *,DirectUI::DUIXmlParser *,CFwProfile *)

- ea: `0x180020c30`
- end: `0x180020e00`
- name: `?Initialize@CFwProfileViewRead@@QEAAJPEAVElement@DirectUI@@PEAVDUIXmlParser@3@PEAVCFwProfile@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CFwProfileViewRead *__hidden this, struct DirectUI::Element *, struct DirectUI::DUIXmlParser *, struct CFwProfile *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d060`

## callees

- `0x1800096a8`
- `0x180009924`
- `0x18000994c`
- `0x180018160`
- `0x180020c30`
- `0x180020e08`

## import_xrefs

- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020d13`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020d13`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180020cda`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180020cda`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020da2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020da2`

## pseudocode

```c
__int64 __fastcall CFwProfileViewRead::Initialize(
        CFwProfileViewRead *this,
        struct DirectUI::Element *a2,
        struct DirectUI::DUIXmlParser *a3,
        struct CFwProfile *a4)
{
  CFwCplLua *v8; // rcx
  struct DirectUI::Element *v9; // r9
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  struct DirectUI::Element *v14; // r8
  struct DirectUI::Element *v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 )
  {
    *((_QWORD *)this + 3) = a2;
    *((_QWORD *)this + 5) = a4;
    CRefObject::AddRef(a4);
    v9 = (struct DirectUI::Element *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 7) = a3;
    v10 = DirectUI::DUIXmlParser::CreateElement(a3, L"settingsExpandoContainer", 0, v9, 0, &v16);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v10 = DirectUI::Element::Add(*((DirectUI::Element **)this + 3), v16);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v14 = v16;
        *((_QWORD *)this + 4) = v16;
        *((_QWORD *)v14 + 25) = ((unsigned __int64)this + 16) & -(__int64)(this != 0);
        CFwProfileViewRead::InitializeUIElements(this, 0);
LABEL_25:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_26;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 13;
        goto LABEL_11;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 12;
LABEL_11:
        v13 = (unsigned int)v10;
LABEL_20:
        WPP_SF_d(*((_QWORD *)v8 + 2), v12, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids, v13);
        v8 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v11 = -2147024809;
    if ( v8 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      v12 = 11;
      v13 = 2147942487LL;
      goto LABEL_20;
    }
  }
  if ( v16 )
  {
    DirectUI::Element::Destroy(v16, 1);
    v8 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 5) )
  {
    CRefObject::Release(*((CRefObject **)this + 5));
    *((_QWORD *)this + 5) = 0;
    goto LABEL_25;
  }
LABEL_26:
  if ( v8 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v8 + 2), 14, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180020c30  push    rbx
0x180020c32  push    rbp
0x180020c33  push    rsi
0x180020c34  push    rdi
0x180020c35  push    r13
0x180020c37  push    r14
0x180020c39  sub     rsp, 38h
0x180020c3d  mov     rbx, r9
0x180020c40  mov     [rsp+68h+arg_8], 0
0x180020c49  mov     rsi, r8
0x180020c4c  mov     rbp, rdx
0x180020c4f  mov     rdi, rcx
0x180020c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c59  lea     r13, WPP_GLOBAL_Control
0x180020c60  cmp     rcx, r13
0x180020c63  jz      short loc_180020C87
0x180020c65  test    byte ptr [rcx+1Ch], 8
0x180020c69  jz      short loc_180020C87
0x180020c6b  mov     rcx, [rcx+10h]
0x180020c6f  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020c76  mov     edx, 0Ah
0x180020c7b  call    WPP_SF_
0x180020c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c87  test    rbp, rbp
0x180020c8a  jz      loc_180020D64
0x180020c90  test    rsi, rsi
0x180020c93  jz      loc_180020D64
0x180020c99  test    rbx, rbx
0x180020c9c  jz      loc_180020D64
0x180020ca2  mov     rcx, rbx; this
0x180020ca5  mov     [rdi+18h], rbp
0x180020ca9  mov     [rdi+28h], rbx
0x180020cad  call    ?AddRef@CRefObject@@QEAAKXZ; CRefObject::AddRef(void)
0x180020cb2  mov     r9, [rdi+18h]
0x180020cb6  lea     rax, [rsp+68h+arg_8]
0x180020cbb  mov     [rsp+68h+var_40], rax
0x180020cc0  lea     rdx, aSettingsexpand; "settingsExpandoContainer"
0x180020cc7  xor     r8d, r8d
0x180020cca  mov     [rsp+68h+var_48], 0
0x180020cd3  mov     rcx, rsi
0x180020cd6  mov     [rdi+38h], rsi
0x180020cda  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180020ce0  mov     ebx, eax
0x180020ce2  test    eax, eax
0x180020ce4  jns     short loc_180020D0A
0x180020ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ced  cmp     rcx, r13
0x180020cf0  jz      loc_180020D93
0x180020cf6  test    byte ptr [rcx+1Ch], 1
0x180020cfa  jz      loc_180020D93
0x180020d00  mov     edx, 0Ch
0x180020d05  mov     r9d, eax
0x180020d08  jmp     short loc_180020D7C
0x180020d0a  mov     rdx, [rsp+68h+arg_8]
0x180020d0f  mov     rcx, [rdi+18h]
0x180020d13  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180020d19  mov     ebx, eax
0x180020d1b  test    eax, eax
0x180020d1d  jns     short loc_180020D38
0x180020d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d26  cmp     rcx, r13
0x180020d29  jz      short loc_180020D93
0x180020d2b  test    byte ptr [rcx+1Ch], 1
0x180020d2f  jz      short loc_180020D93
0x180020d31  mov     edx, 0Dh
0x180020d36  jmp     short loc_180020D05
0x180020d38  mov     r8, [rsp+68h+arg_8]
0x180020d3d  lea     rdx, [rdi+10h]
0x180020d41  mov     [rdi+20h], r8
0x180020d45  mov     rax, rdi
0x180020d48  neg     rax
0x180020d4b  sbb     rcx, rcx
0x180020d4e  and     rcx, rdx
0x180020d51  xor     edx, edx; int
0x180020d53  mov     [r8+0C8h], rcx
0x180020d5a  mov     rcx, rdi; this
0x180020d5d  call    ?InitializeUIElements@CFwProfileViewRead@@AEAAXH@Z; CFwProfileViewRead::InitializeUIElements(int)
0x180020d62  jmp     short loc_180020DC7
0x180020d64  mov     ebx, 80070057h
0x180020d69  cmp     rcx, r13
0x180020d6c  jz      short loc_180020D93
0x180020d6e  test    byte ptr [rcx+1Ch], 1
0x180020d72  jz      short loc_180020D93
0x180020d74  mov     edx, 0Bh
0x180020d79  mov     r9d, ebx
0x180020d7c  mov     rcx, [rcx+10h]
0x180020d80  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020d87  call    WPP_SF_d
0x180020d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d93  mov     rax, [rsp+68h+arg_8]
0x180020d98  test    rax, rax
0x180020d9b  jz      short loc_180020DAF
0x180020d9d  mov     dl, 1
0x180020d9f  mov     rcx, rax
0x180020da2  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180020da8  mov     rcx, cs:WPP_GLOBAL_Control
0x180020daf  cmp     qword ptr [rdi+28h], 0
0x180020db4  jz      short loc_180020DCE
0x180020db6  mov     rcx, [rdi+28h]; this
0x180020dba  call    ?Release@CRefObject@@QEAAKXZ; CRefObject::Release(void)
0x180020dbf  mov     qword ptr [rdi+28h], 0
0x180020dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dce  cmp     rcx, r13
0x180020dd1  jz      short loc_180020DF1
0x180020dd3  test    byte ptr [rcx+1Ch], 8
0x180020dd7  jz      short loc_180020DF1
0x180020dd9  mov     rcx, [rcx+10h]
0x180020ddd  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020de4  mov     edx, 0Eh
0x180020de9  mov     r9d, ebx
0x180020dec  call    WPP_SF_d
0x180020df1  mov     eax, ebx
0x180020df3  add     rsp, 38h
0x180020df7  pop     r14
0x180020df9  pop     r13
0x180020dfb  pop     rdi
0x180020dfc  pop     rsi
0x180020dfd  pop     rbp
0x180020dfe  pop     rbx
0x180020dff  retn
```
