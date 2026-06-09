# DockCache::PairedDock(ushort const *,_DOCK_PROFILE const &)

- ea: `0x180012860`
- end: `0x1800129bc`
- name: `?PairedDock@DockCache@@QEAAJPEBGAEBU_DOCK_PROFILE@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, wchar_t *, const struct _DOCK_PROFILE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009660`

## callees

- `0x180010d58`
- `0x1800112b4`
- `0x180011c2c`
- `0x180012788`
- `0x180012860`
- `0x18001321c`
- `0x1800136a0`
- `0x180013b80`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012895`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012999`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012999`

## pseudocode

```c
__int64 __fastcall DockCache::PairedDock(
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
  if ( (int)DockCache::FindDock((DockCache *)v5, a2, &v11) < 0 )
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
          42,
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
          43,
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
    Dock::Paired(v6, a3);
  }
  v7 = 0;
  goto LABEL_14;
}

```

## disassembly

```asm
0x180012860  push    rbx
0x180012862  push    rsi
0x180012863  push    rdi
0x180012864  sub     rsp, 0BF0h
0x18001286b  mov     rax, cs:__security_cookie
0x180012872  xor     rax, rsp
0x180012875  mov     [rsp+0C08h+var_28], rax
0x18001287d  mov     rdi, r8
0x180012880  mov     rsi, rdx
0x180012883  mov     rbx, rcx
0x180012886  mov     [rsp+0C08h+var_BC8], rcx
0x18001288b  mov     [rsp+0C08h+var_BB8], r8
0x180012890  mov     [rsp+0C08h+var_BB0], rcx
0x180012895  call    cs:__imp_EnterCriticalSection
0x18001289b  nop
0x18001289c  mov     [rsp+0C08h+var_BC0], 0
0x1800128a5  lea     r8, [rsp+0C08h+var_BC0]; struct Dock **
0x1800128aa  mov     rdx, rsi; unsigned __int16 *
0x1800128ad  mov     rcx, rbx; this
0x1800128b0  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x1800128b5  test    eax, eax
0x1800128b7  js      short loc_180012916
0x1800128b9  lea     rax, WPP_GLOBAL_Control
0x1800128c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128c7  cmp     rcx, rax
0x1800128ca  jz      short loc_180012904
0x1800128cc  cmp     byte ptr [rcx+19h], 3
0x1800128d0  jb      short loc_180012904
0x1800128d2  test    byte ptr [rcx+1Ch], 1
0x1800128d6  jz      short loc_180012904
0x1800128d8  mov     edx, 28h ; '('
0x1800128dd  mov     [rsp+0C08h+var_BD0], rsi; __int64
0x1800128e2  mov     [rsp+0C08h+var_BD8], rdi; __int64
0x1800128e7  mov     qword ptr [rsp+0C08h+var_BE0], rdi; char
0x1800128ec  mov     rsi, [rsp+0C08h+var_BC0]
0x1800128f1  mov     qword ptr [rsp+0C08h+var_BE8], rsi; char
0x1800128f6  mov     r9, rbx
0x1800128f9  mov     rcx, [rcx+10h]; LoggerHandle
0x1800128fd  call    WPP_SF_qqqSS
0x180012902  jmp     short loc_180012909
0x180012904  mov     rsi, [rsp+0C08h+var_BC0]
0x180012909  mov     rdx, rdi; struct _DOCK_PROFILE *
0x18001290c  mov     rcx, rsi; this
0x18001290f  call    ?Paired@Dock@@QEAAXPEBU_DOCK_PROFILE@@@Z; Dock::Paired(_DOCK_PROFILE const *)
0x180012914  jmp     short loc_180012981
0x180012916  lea     rax, WPP_GLOBAL_Control
0x18001291d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012924  cmp     rcx, rax
0x180012927  jz      short loc_180012956
0x180012929  cmp     byte ptr [rcx+19h], 3
0x18001292d  jb      short loc_180012956
0x18001292f  test    byte ptr [rcx+1Ch], 1
0x180012933  jz      short loc_180012956
0x180012935  mov     edx, 29h ; ')'
0x18001293a  mov     [rsp+0C08h+var_BD8], rsi; __int64
0x18001293f  mov     qword ptr [rsp+0C08h+var_BE0], rdi; __int64
0x180012944  mov     qword ptr [rsp+0C08h+var_BE8], rdi; char
0x180012949  mov     r9, rbx
0x18001294c  mov     rcx, [rcx+10h]; LoggerHandle
0x180012950  call    WPP_SF_qqSS
0x180012955  nop
0x180012956  mov     r8, rdi; struct _DOCK_PROFILE *
0x180012959  mov     rdx, rsi; Str
0x18001295c  lea     rcx, [rsp+0C08h+var_BA8]; this
0x180012961  call    ??0Dock@@QEAA@PEBGAEBU_DOCK_PROFILE@@@Z; Dock::Dock(ushort const *,_DOCK_PROFILE const &)
0x180012966  nop
0x180012967  lea     rcx, [rbx+28h]
0x18001296b  lea     rdx, [rsp+0C08h+var_BA8]
0x180012970  call    ?push_back@?$vector@VDock@@V?$allocator@VDock@@@std@@@std@@QEAAXAEBVDock@@@Z; std::vector<Dock>::push_back(Dock const &)
0x180012975  nop
0x180012976  lea     rcx, [rsp+0C08h+var_BA8]; this
0x18001297b  call    ??1Dock@@QEAA@XZ; Dock::~Dock(void)
0x180012980  nop
0x180012981  xor     edi, edi
0x180012983  jmp     short loc_180012996
0x180012985  mov     edi, 8007000Eh
0x18001298a  jmp     short loc_180012991
0x18001298c  mov     edi, 80004005h
0x180012991  mov     rbx, [rsp+0C08h+var_BC8]
0x180012996  mov     rcx, rbx; lpCriticalSection
0x180012999  call    cs:__imp_LeaveCriticalSection
0x18001299f  mov     eax, edi
0x1800129a1  mov     rcx, [rsp+0C08h+var_28]
0x1800129a9  xor     rcx, rsp; StackCookie
0x1800129ac  call    __security_check_cookie
0x1800129b1  add     rsp, 0BF0h
0x1800129b8  pop     rdi
0x1800129b9  pop     rsi
0x1800129ba  pop     rbx
0x1800129bb  retn
```
