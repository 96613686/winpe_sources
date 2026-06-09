# CFwProfileViewUpdate::Initialize(DirectUI::Element *,DirectUI::DUIXmlParser *,CFwProfile *)

- ea: `0x18001fc84`
- end: `0x18001fe4e`
- name: `?Initialize@CFwProfileViewUpdate@@QEAAJPEAVElement@DirectUI@@PEAVDUIXmlParser@3@PEAVCFwProfile@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(CFwProfileViewUpdate *__hidden this, struct DirectUI::Element *, struct DirectUI::DUIXmlParser *, struct CFwProfile *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180016d44`

## callees

- `0x1800096a8`
- `0x180009924`
- `0x18000994c`
- `0x180018160`
- `0x18001fc84`
- `0x18001fe54`

## import_xrefs

- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001fd63`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001fd63`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001fd2a`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001fd2a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001fdf0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001fdf0`

## pseudocode

```c
__int64 __fastcall CFwProfileViewUpdate::Initialize(
        CFwProfileViewUpdate *this,
        struct DirectUI::Element *a2,
        struct DirectUI::DUIXmlParser *a3,
        struct CFwProfile *a4)
{
  CFwCplLua *v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9
  struct DirectUI::Element *v13; // r8
  struct DirectUI::Element *v15; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4a589502d135308541a166db9771a95e_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && a3 && a4 )
  {
    *((_QWORD *)this + 3) = a2;
    *((_QWORD *)this + 5) = a4;
    CRefObject::AddRef(a4);
    v9 = DirectUI::DUIXmlParser::CreateElement(
           a3,
           L"resProfileSettingsExpando",
           0,
           *((struct DirectUI::Element **)this + 3),
           0,
           &v15);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v9 = DirectUI::Element::Add(*((DirectUI::Element **)this + 3), v15);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v13 = v15;
        *((_QWORD *)this + 4) = v15;
        *((_QWORD *)v13 + 25) = ((unsigned __int64)this + 16) & -(__int64)(this != 0);
        CFwProfileViewUpdate::InitializeUIElements(this);
LABEL_25:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_26;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 13;
        goto LABEL_11;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 12;
LABEL_11:
        v12 = (unsigned int)v9;
LABEL_20:
        WPP_SF_d(*((_QWORD *)v8 + 2), v11, WPP_4a589502d135308541a166db9771a95e_Traceguids, v12);
        v8 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v10 = -2147024809;
    if ( v8 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
    {
      v11 = 11;
      v12 = 2147942487LL;
      goto LABEL_20;
    }
  }
  if ( v15 )
  {
    DirectUI::Element::Destroy(v15, 1);
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
    WPP_SF_d(*((_QWORD *)v8 + 2), 14, WPP_4a589502d135308541a166db9771a95e_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18001fc84  push    rbx
0x18001fc86  push    rbp
0x18001fc87  push    rsi
0x18001fc88  push    rdi
0x18001fc89  push    r13
0x18001fc8b  push    r14
0x18001fc8d  sub     rsp, 38h
0x18001fc91  mov     rbx, r9
0x18001fc94  mov     [rsp+68h+arg_8], 0
0x18001fc9d  mov     rsi, r8
0x18001fca0  mov     rbp, rdx
0x18001fca3  mov     rdi, rcx
0x18001fca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcad  lea     r13, WPP_GLOBAL_Control
0x18001fcb4  cmp     rcx, r13
0x18001fcb7  jz      short loc_18001FCDB
0x18001fcb9  test    byte ptr [rcx+1Ch], 8
0x18001fcbd  jz      short loc_18001FCDB
0x18001fcbf  mov     rcx, [rcx+10h]
0x18001fcc3  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x18001fcca  mov     edx, 0Ah
0x18001fccf  call    WPP_SF_
0x18001fcd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcdb  test    rbp, rbp
0x18001fcde  jz      loc_18001FDB2
0x18001fce4  test    rsi, rsi
0x18001fce7  jz      loc_18001FDB2
0x18001fced  test    rbx, rbx
0x18001fcf0  jz      loc_18001FDB2
0x18001fcf6  mov     rcx, rbx; this
0x18001fcf9  mov     [rdi+18h], rbp
0x18001fcfd  mov     [rdi+28h], rbx
0x18001fd01  call    ?AddRef@CRefObject@@QEAAKXZ; CRefObject::AddRef(void)
0x18001fd06  mov     r9, [rdi+18h]
0x18001fd0a  lea     rcx, [rsp+68h+arg_8]
0x18001fd0f  mov     [rsp+68h+var_40], rcx
0x18001fd14  lea     rdx, aResprofilesett; "resProfileSettingsExpando"
0x18001fd1b  mov     rcx, rsi
0x18001fd1e  mov     [rsp+68h+var_48], 0
0x18001fd27  xor     r8d, r8d
0x18001fd2a  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18001fd30  mov     ebx, eax
0x18001fd32  test    eax, eax
0x18001fd34  jns     short loc_18001FD5A
0x18001fd36  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd3d  cmp     rcx, r13
0x18001fd40  jz      loc_18001FDE1
0x18001fd46  test    byte ptr [rcx+1Ch], 1
0x18001fd4a  jz      loc_18001FDE1
0x18001fd50  mov     edx, 0Ch
0x18001fd55  mov     r9d, eax
0x18001fd58  jmp     short loc_18001FDCA
0x18001fd5a  mov     rdx, [rsp+68h+arg_8]
0x18001fd5f  mov     rcx, [rdi+18h]
0x18001fd63  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18001fd69  mov     ebx, eax
0x18001fd6b  test    eax, eax
0x18001fd6d  jns     short loc_18001FD88
0x18001fd6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd76  cmp     rcx, r13
0x18001fd79  jz      short loc_18001FDE1
0x18001fd7b  test    byte ptr [rcx+1Ch], 1
0x18001fd7f  jz      short loc_18001FDE1
0x18001fd81  mov     edx, 0Dh
0x18001fd86  jmp     short loc_18001FD55
0x18001fd88  mov     r8, [rsp+68h+arg_8]
0x18001fd8d  lea     rdx, [rdi+10h]
0x18001fd91  mov     [rdi+20h], r8
0x18001fd95  mov     rax, rdi
0x18001fd98  neg     rax
0x18001fd9b  sbb     rcx, rcx
0x18001fd9e  and     rcx, rdx
0x18001fda1  mov     [r8+0C8h], rcx
0x18001fda8  mov     rcx, rdi; this
0x18001fdab  call    ?InitializeUIElements@CFwProfileViewUpdate@@AEAAXXZ; CFwProfileViewUpdate::InitializeUIElements(void)
0x18001fdb0  jmp     short loc_18001FE15
0x18001fdb2  mov     ebx, 80070057h
0x18001fdb7  cmp     rcx, r13
0x18001fdba  jz      short loc_18001FDE1
0x18001fdbc  test    byte ptr [rcx+1Ch], 1
0x18001fdc0  jz      short loc_18001FDE1
0x18001fdc2  mov     edx, 0Bh
0x18001fdc7  mov     r9d, ebx
0x18001fdca  mov     rcx, [rcx+10h]
0x18001fdce  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x18001fdd5  call    WPP_SF_d
0x18001fdda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fde1  mov     rax, [rsp+68h+arg_8]
0x18001fde6  test    rax, rax
0x18001fde9  jz      short loc_18001FDFD
0x18001fdeb  mov     dl, 1
0x18001fded  mov     rcx, rax
0x18001fdf0  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18001fdf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdfd  cmp     qword ptr [rdi+28h], 0
0x18001fe02  jz      short loc_18001FE1C
0x18001fe04  mov     rcx, [rdi+28h]; this
0x18001fe08  call    ?Release@CRefObject@@QEAAKXZ; CRefObject::Release(void)
0x18001fe0d  mov     qword ptr [rdi+28h], 0
0x18001fe15  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe1c  cmp     rcx, r13
0x18001fe1f  jz      short loc_18001FE3F
0x18001fe21  test    byte ptr [rcx+1Ch], 8
0x18001fe25  jz      short loc_18001FE3F
0x18001fe27  mov     rcx, [rcx+10h]
0x18001fe2b  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x18001fe32  mov     edx, 0Eh
0x18001fe37  mov     r9d, ebx
0x18001fe3a  call    WPP_SF_d
0x18001fe3f  mov     eax, ebx
0x18001fe41  add     rsp, 38h
0x18001fe45  pop     r14
0x18001fe47  pop     r13
0x18001fe49  pop     rdi
0x18001fe4a  pop     rsi
0x18001fe4b  pop     rbp
0x18001fe4c  pop     rbx
0x18001fe4d  retn
```
