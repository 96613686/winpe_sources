# DockCache::ConnectedDock(ushort const *,_DOCK_PROFILE const &)

- ea: `0x180011550`
- end: `0x1800116b9`
- name: `?ConnectedDock@DockCache@@QEAAJPEBGAEBU_DOCK_PROFILE@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, wchar_t *, const struct _DOCK_PROFILE *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180009660`
- `0x18000f3ec`
- `0x180018be0`

## callees

- `0x180010d58`
- `0x1800112b4`
- `0x180011470`
- `0x180011550`
- `0x180011c2c`
- `0x18001321c`
- `0x1800136a0`
- `0x180013b80`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011585`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011696`

## pseudocode

```c
__int64 __fastcall DockCache::ConnectedDock(
        struct _RTL_CRITICAL_SECTION *this,
        wchar_t *a2,
        const struct _DOCK_PROFILE *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  Dock *v6; // rsi
  unsigned int v7; // edi
  __int64 result; // rax
  const unsigned __int16 *v9; // [rsp+38h] [rbp-BD0h]
  struct Dock *v11; // [rsp+48h] [rbp-BC0h] BYREF
  const struct _DOCK_PROFILE *v12; // [rsp+50h] [rbp-BB8h]
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+58h] [rbp-BB0h]
  _BYTE v14[2944]; // [rsp+60h] [rbp-BA8h] BYREF

  v5 = this;
  v12 = a3;
  v13 = this;
  EnterCriticalSection(this);
  v11 = 0;
  if ( DockCache::FindDock((DockCache *)v5, a2, &v11) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)a3, (__int64)a3, (__int64)a2);
    }
    try
    {
      Dock::Dock((Dock *)v14, a2, a3);
      Dock::Connected((Dock *)v14, a3);
      std::vector<Dock>::push_back(&v5[1], v14);
      Dock::~Dock((Dock *)v14);
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
          (_DWORD)this,
          (__int64)v12);
      }
      v7 = -2147024882;
      goto LABEL_13;
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
          (_DWORD)this,
          (__int64)v12);
      }
      v7 = -2147467259;
LABEL_13:
      v5 = this;
LABEL_14:
      LeaveCriticalSection(v5);
      result = v7;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v6 = v11;
    }
    else
    {
      v9 = a2;
      v6 = v11;
      WPP_SF_qqqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v11, (char)a3, (__int64)a3, (__int64)v9);
    }
    Dock::Connected(v6, a3);
  }
  v7 = 0;
  goto LABEL_14;
}

```

## disassembly

```asm
0x180011550  push    rbx
0x180011552  push    rsi
0x180011553  push    rdi
0x180011554  sub     rsp, 0BF0h
0x18001155b  mov     rax, cs:__security_cookie
0x180011562  xor     rax, rsp
0x180011565  mov     [rsp+0C08h+var_28], rax
0x18001156d  mov     rdi, r8
0x180011570  mov     rsi, rdx
0x180011573  mov     rbx, rcx
0x180011576  mov     [rsp+0C08h+var_BC8], rcx
0x18001157b  mov     [rsp+0C08h+var_BB8], r8
0x180011580  mov     [rsp+0C08h+var_BB0], rcx
0x180011585  call    cs:__imp_EnterCriticalSection
0x18001158b  nop
0x18001158c  mov     [rsp+0C08h+var_BC0], 0
0x180011595  lea     r8, [rsp+0C08h+var_BC0]; struct Dock **
0x18001159a  mov     rdx, rsi; unsigned __int16 *
0x18001159d  mov     rcx, rbx; this
0x1800115a0  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x1800115a5  test    eax, eax
0x1800115a7  js      short loc_180011606
0x1800115a9  lea     rax, WPP_GLOBAL_Control
0x1800115b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115b7  cmp     rcx, rax
0x1800115ba  jz      short loc_1800115F4
0x1800115bc  cmp     byte ptr [rcx+19h], 3
0x1800115c0  jb      short loc_1800115F4
0x1800115c2  test    byte ptr [rcx+1Ch], 1
0x1800115c6  jz      short loc_1800115F4
0x1800115c8  mov     edx, 2Dh ; '-'
0x1800115cd  mov     [rsp+0C08h+var_BD0], rsi; __int64
0x1800115d2  mov     [rsp+0C08h+var_BD8], rdi; __int64
0x1800115d7  mov     qword ptr [rsp+0C08h+var_BE0], rdi; char
0x1800115dc  mov     rsi, [rsp+0C08h+var_BC0]
0x1800115e1  mov     qword ptr [rsp+0C08h+var_BE8], rsi; char
0x1800115e6  mov     r9, rbx
0x1800115e9  mov     rcx, [rcx+10h]; LoggerHandle
0x1800115ed  call    WPP_SF_qqqSS
0x1800115f2  jmp     short loc_1800115F9
0x1800115f4  mov     rsi, [rsp+0C08h+var_BC0]
0x1800115f9  mov     rdx, rdi; struct _DOCK_PROFILE *
0x1800115fc  mov     rcx, rsi; this
0x1800115ff  call    ?Connected@Dock@@QEAAXPEBU_DOCK_PROFILE@@@Z; Dock::Connected(_DOCK_PROFILE const *)
0x180011604  jmp     short loc_18001167E
0x180011606  lea     rax, WPP_GLOBAL_Control
0x18001160d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011614  cmp     rcx, rax
0x180011617  jz      short loc_180011646
0x180011619  cmp     byte ptr [rcx+19h], 3
0x18001161d  jb      short loc_180011646
0x18001161f  test    byte ptr [rcx+1Ch], 1
0x180011623  jz      short loc_180011646
0x180011625  mov     edx, 2Eh ; '.'
0x18001162a  mov     [rsp+0C08h+var_BD8], rsi; __int64
0x18001162f  mov     qword ptr [rsp+0C08h+var_BE0], rdi; __int64
0x180011634  mov     qword ptr [rsp+0C08h+var_BE8], rdi; char
0x180011639  mov     r9, rbx
0x18001163c  mov     rcx, [rcx+10h]; LoggerHandle
0x180011640  call    WPP_SF_qqSS
0x180011645  nop
0x180011646  mov     r8, rdi; struct _DOCK_PROFILE *
0x180011649  mov     rdx, rsi; Str
0x18001164c  lea     rcx, [rsp+0C08h+var_BA8]; this
0x180011651  call    ??0Dock@@QEAA@PEBGAEBU_DOCK_PROFILE@@@Z; Dock::Dock(ushort const *,_DOCK_PROFILE const &)
0x180011656  nop
0x180011657  mov     rdx, rdi; struct _DOCK_PROFILE *
0x18001165a  lea     rcx, [rsp+0C08h+var_BA8]; this
0x18001165f  call    ?Connected@Dock@@QEAAXPEBU_DOCK_PROFILE@@@Z; Dock::Connected(_DOCK_PROFILE const *)
0x180011664  lea     rcx, [rbx+28h]
0x180011668  lea     rdx, [rsp+0C08h+var_BA8]
0x18001166d  call    ?push_back@?$vector@VDock@@V?$allocator@VDock@@@std@@@std@@QEAAXAEBVDock@@@Z; std::vector<Dock>::push_back(Dock const &)
0x180011672  nop
0x180011673  lea     rcx, [rsp+0C08h+var_BA8]; this
0x180011678  call    ??1Dock@@QEAA@XZ; Dock::~Dock(void)
0x18001167d  nop
0x18001167e  xor     edi, edi
0x180011680  jmp     short loc_180011693
0x180011682  mov     edi, 8007000Eh
0x180011687  jmp     short loc_18001168E
0x180011689  mov     edi, 80004005h
0x18001168e  mov     rbx, [rsp+0C08h+var_BC8]
0x180011693  mov     rcx, rbx; lpCriticalSection
0x180011696  call    cs:__imp_LeaveCriticalSection
0x18001169c  mov     eax, edi
0x18001169e  mov     rcx, [rsp+0C08h+var_28]
0x1800116a6  xor     rcx, rsp; StackCookie
0x1800116a9  call    __security_check_cookie
0x1800116ae  add     rsp, 0BF0h
0x1800116b5  pop     rdi
0x1800116b6  pop     rsi
0x1800116b7  pop     rbx
0x1800116b8  retn
```
