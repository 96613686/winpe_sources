# CServicingSession::Initialize(IFhConfigMgrPriv *,IFhCatalog *)

- ea: `0x1800235e0`
- end: `0x18002368b`
- name: `?Initialize@CServicingSession@@UEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(struct _FILETIME *this, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180007818`
- `0x1800093a8`
- `0x18000eed8`
- `0x1800235e0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800235ff`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800235ff`

## pseudocode

```c
__int64 __fastcall CServicingSession::Initialize(struct _FILETIME *this, struct IUnknown *a2, struct IUnknown *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx

  GetSystemTimeAsFileTime(this + 44);
  v6 = CSessionBaseRW::Initialize((CSessionBaseRW *)&this[1], a2, a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids,
          (unsigned int)v6);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
        WPP_SF_s(v8[2], 12, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids, "SUCCEEDED(hr)");
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800235e0  mov     [rsp+arg_0], rbx
0x1800235e5  mov     [rsp+arg_8], rsi
0x1800235ea  push    rdi
0x1800235eb  sub     rsp, 20h
0x1800235ef  mov     rbx, rcx
0x1800235f2  mov     rdi, r8
0x1800235f5  add     rcx, 160h; lpSystemTimeAsFileTime
0x1800235fc  mov     rsi, rdx
0x1800235ff  call    cs:__imp_GetSystemTimeAsFileTime
0x180023605  lea     rcx, [rbx+8]; this
0x180023609  mov     r8, rdi; struct IFhCatalog *
0x18002360c  mov     rdx, rsi; struct IFhConfigMgrPriv *
0x18002360f  call    ?Initialize@CSessionBaseRW@@IEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z; CSessionBaseRW::Initialize(IFhConfigMgrPriv *,IFhCatalog *)
0x180023614  mov     ebx, eax
0x180023616  test    eax, eax
0x180023618  jns     short loc_180023679
0x18002361a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023621  lea     rdi, WPP_GLOBAL_Control
0x180023628  cmp     rcx, rdi
0x18002362b  jz      short loc_180023679
0x18002362d  test    byte ptr [rcx+1Ch], 1
0x180023631  jz      short loc_180023652
0x180023633  mov     rcx, [rcx+10h]
0x180023637  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x18002363e  mov     edx, 0Bh
0x180023643  mov     r9d, eax
0x180023646  call    WPP_SF_d
0x18002364b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023652  cmp     rcx, rdi
0x180023655  jz      short loc_180023679
0x180023657  test    byte ptr [rcx+1Ch], 4
0x18002365b  jz      short loc_180023679
0x18002365d  mov     rcx, [rcx+10h]
0x180023661  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x180023668  mov     edx, 0Ch
0x18002366d  lea     r8, WPP_33a96c68fe793a20e8db406eb7bb3a3d_Traceguids
0x180023674  call    WPP_SF_s
0x180023679  mov     rsi, [rsp+28h+arg_8]
0x18002367e  mov     eax, ebx
0x180023680  mov     rbx, [rsp+28h+arg_0]
0x180023685  add     rsp, 20h
0x180023689  pop     rdi
0x18002368a  retn
```
