# DockCache::LivenessUnknown(ushort const *,_DOCK_PROFILE const &)

- ea: `0x1800123fc`
- end: `0x18001255f`
- name: `?LivenessUnknown@DockCache@@QEAAJPEBGAEBU_DOCK_PROFILE@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, wchar_t *, const struct _DOCK_PROFILE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f3ec`

## callees

- `0x180010d58`
- `0x1800112b4`
- `0x180011c2c`
- `0x1800123fc`
- `0x180012b34`
- `0x18001321c`
- `0x1800136a0`
- `0x180013b80`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012431`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001253c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001253c`

## pseudocode

```c
__int64 __fastcall DockCache::LivenessUnknown(
        struct _RTL_CRITICAL_SECTION *this,
        wchar_t *a2,
        const struct _DOCK_PROFILE *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  Dock *v6; // rdi
  unsigned int v7; // edi
  __int64 result; // rax
  char v9; // [rsp+28h] [rbp-BF0h]
  const struct _DOCK_PROFILE *v10; // [rsp+30h] [rbp-BE8h]
  struct Dock *v12; // [rsp+48h] [rbp-BD0h] BYREF
  const struct _DOCK_PROFILE *v13; // [rsp+50h] [rbp-BC8h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+60h] [rbp-BB8h]
  _BYTE v15[2944]; // [rsp+70h] [rbp-BA8h] BYREF

  v5 = this;
  v13 = a3;
  v14 = this;
  EnterCriticalSection(this);
  v12 = 0;
  if ( (int)DockCache::FindDock((DockCache *)v5, a2, &v12) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)a3, (__int64)a3, (__int64)a2);
    }
    try
    {
      Dock::Dock((Dock *)v15, a2, a3);
      Dock::Stale((Dock *)v15);
      std::vector<Dock>::push_back(&v5[1], v15);
      Dock::~Dock((Dock *)v15);
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
          (_DWORD)this,
          (__int64)v13);
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
          55,
          (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
          (_DWORD)this,
          (__int64)v13);
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
      v6 = v12;
    }
    else
    {
      v10 = a3;
      v9 = (char)a3;
      v6 = v12;
      WPP_SF_qqqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v12, v9, (__int64)v10, (__int64)a2);
    }
    Dock::Stale(v6);
  }
  v7 = 0;
  goto LABEL_14;
}

```

## disassembly

```asm
0x1800123fc  push    rbx
0x1800123fe  push    rsi
0x1800123ff  push    rdi
0x180012400  sub     rsp, 0C00h
0x180012407  mov     rax, cs:__security_cookie
0x18001240e  xor     rax, rsp
0x180012411  mov     [rsp+0C18h+var_28], rax
0x180012419  mov     rdi, r8
0x18001241c  mov     rsi, rdx
0x18001241f  mov     rbx, rcx
0x180012422  mov     [rsp+0C18h+var_BD8], rcx
0x180012427  mov     [rsp+0C18h+var_BC8], r8
0x18001242c  mov     [rsp+0C18h+var_BB8], rcx
0x180012431  call    cs:__imp_EnterCriticalSection
0x180012437  nop
0x180012438  mov     [rsp+0C18h+var_BD0], 0
0x180012441  lea     r8, [rsp+0C18h+var_BD0]; struct Dock **
0x180012446  mov     rdx, rsi; unsigned __int16 *
0x180012449  mov     rcx, rbx; this
0x18001244c  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x180012451  test    eax, eax
0x180012453  js      short loc_1800124AF
0x180012455  lea     rax, WPP_GLOBAL_Control
0x18001245c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012463  cmp     rcx, rax
0x180012466  jz      short loc_1800124A0
0x180012468  cmp     byte ptr [rcx+19h], 3
0x18001246c  jb      short loc_1800124A0
0x18001246e  test    byte ptr [rcx+1Ch], 1
0x180012472  jz      short loc_1800124A0
0x180012474  mov     edx, 34h ; '4'
0x180012479  mov     [rsp+0C18h+var_BE0], rsi; __int64
0x18001247e  mov     [rsp+0C18h+var_BE8], rdi; __int64
0x180012483  mov     qword ptr [rsp+0C18h+var_BF0], rdi; char
0x180012488  mov     rdi, [rsp+0C18h+var_BD0]
0x18001248d  mov     qword ptr [rsp+0C18h+var_BF8], rdi; char
0x180012492  mov     r9, rbx
0x180012495  mov     rcx, [rcx+10h]; LoggerHandle
0x180012499  call    WPP_SF_qqqSS
0x18001249e  jmp     short loc_1800124A5
0x1800124a0  mov     rdi, [rsp+0C18h+var_BD0]
0x1800124a5  mov     rcx, rdi; this
0x1800124a8  call    ?Stale@Dock@@QEAAXXZ; Dock::Stale(void)
0x1800124ad  jmp     short loc_180012524
0x1800124af  lea     rax, WPP_GLOBAL_Control
0x1800124b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124bd  cmp     rcx, rax
0x1800124c0  jz      short loc_1800124EF
0x1800124c2  cmp     byte ptr [rcx+19h], 3
0x1800124c6  jb      short loc_1800124EF
0x1800124c8  test    byte ptr [rcx+1Ch], 1
0x1800124cc  jz      short loc_1800124EF
0x1800124ce  mov     edx, 35h ; '5'
0x1800124d3  mov     [rsp+0C18h+var_BE8], rsi; __int64
0x1800124d8  mov     qword ptr [rsp+0C18h+var_BF0], rdi; __int64
0x1800124dd  mov     qword ptr [rsp+0C18h+var_BF8], rdi; char
0x1800124e2  mov     r9, rbx
0x1800124e5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800124e9  call    WPP_SF_qqSS
0x1800124ee  nop
0x1800124ef  mov     r8, rdi; struct _DOCK_PROFILE *
0x1800124f2  mov     rdx, rsi; Str
0x1800124f5  lea     rcx, [rsp+0C18h+var_BA8]; this
0x1800124fa  call    ??0Dock@@QEAA@PEBGAEBU_DOCK_PROFILE@@@Z; Dock::Dock(ushort const *,_DOCK_PROFILE const &)
0x1800124ff  nop
0x180012500  lea     rcx, [rsp+0C18h+var_BA8]; this
0x180012505  call    ?Stale@Dock@@QEAAXXZ; Dock::Stale(void)
0x18001250a  lea     rcx, [rbx+28h]
0x18001250e  lea     rdx, [rsp+0C18h+var_BA8]
0x180012513  call    ?push_back@?$vector@VDock@@V?$allocator@VDock@@@std@@@std@@QEAAXAEBVDock@@@Z; std::vector<Dock>::push_back(Dock const &)
0x180012518  nop
0x180012519  lea     rcx, [rsp+0C18h+var_BA8]; this
0x18001251e  call    ??1Dock@@QEAA@XZ; Dock::~Dock(void)
0x180012523  nop
0x180012524  xor     edi, edi
0x180012526  jmp     short loc_180012539
0x180012528  mov     edi, 8007000Eh
0x18001252d  jmp     short loc_180012534
0x18001252f  mov     edi, 80004005h
0x180012534  mov     rbx, [rsp+0C18h+var_BD8]
0x180012539  mov     rcx, rbx; lpCriticalSection
0x18001253c  call    cs:__imp_LeaveCriticalSection
0x180012542  mov     eax, edi
0x180012544  mov     rcx, [rsp+0C18h+var_28]
0x18001254c  xor     rcx, rsp; StackCookie
0x18001254f  call    __security_check_cookie
0x180012554  add     rsp, 0C00h
0x18001255b  pop     rdi
0x18001255c  pop     rsi
0x18001255d  pop     rbx
0x18001255e  retn
```
