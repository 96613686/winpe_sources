# DockCache::FoundDock(ushort const *,_VISIBLE_DOCK const &)

- ea: `0x180011d84`
- end: `0x180011ee0`
- name: `?FoundDock@DockCache@@QEAAJPEBGAEBU_VISIBLE_DOCK@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, wchar_t *, const struct _VISIBLE_DOCK *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000c584`
- `0x18000c6e4`
- `0x180018be0`

## callees

- `0x180010f04`
- `0x1800112b4`
- `0x180011c2c`
- `0x180011d84`
- `0x180012330`
- `0x18001321c`
- `0x1800136a0`
- `0x180013b80`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011db9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011db9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ebd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ebd`

## pseudocode

```c
__int64 __fastcall DockCache::FoundDock(
        struct _RTL_CRITICAL_SECTION *this,
        wchar_t *a2,
        const struct _VISIBLE_DOCK *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  Dock *v6; // rsi
  unsigned int v7; // edi
  __int64 result; // rax
  const unsigned __int16 *v9; // [rsp+38h] [rbp-BD0h]
  struct Dock *v11; // [rsp+48h] [rbp-BC0h] BYREF
  const struct _VISIBLE_DOCK *v12; // [rsp+50h] [rbp-BB8h]
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
          38,
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
          39,
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
    Dock::Live(v6, a3);
  }
  v7 = 0;
  goto LABEL_14;
}

```

## disassembly

```asm
0x180011d84  push    rbx
0x180011d86  push    rsi
0x180011d87  push    rdi
0x180011d88  sub     rsp, 0BF0h
0x180011d8f  mov     rax, cs:__security_cookie
0x180011d96  xor     rax, rsp
0x180011d99  mov     [rsp+0C08h+var_28], rax
0x180011da1  mov     rdi, r8
0x180011da4  mov     rsi, rdx
0x180011da7  mov     rbx, rcx
0x180011daa  mov     [rsp+0C08h+var_BC8], rcx
0x180011daf  mov     [rsp+0C08h+var_BB8], r8
0x180011db4  mov     [rsp+0C08h+var_BB0], rcx
0x180011db9  call    cs:__imp_EnterCriticalSection
0x180011dbf  nop
0x180011dc0  mov     [rsp+0C08h+var_BC0], 0
0x180011dc9  lea     r8, [rsp+0C08h+var_BC0]; struct Dock **
0x180011dce  mov     rdx, rsi; unsigned __int16 *
0x180011dd1  mov     rcx, rbx; this
0x180011dd4  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x180011dd9  test    eax, eax
0x180011ddb  js      short loc_180011E3A
0x180011ddd  lea     rax, WPP_GLOBAL_Control
0x180011de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011deb  cmp     rcx, rax
0x180011dee  jz      short loc_180011E28
0x180011df0  cmp     byte ptr [rcx+19h], 3
0x180011df4  jb      short loc_180011E28
0x180011df6  test    byte ptr [rcx+1Ch], 1
0x180011dfa  jz      short loc_180011E28
0x180011dfc  mov     edx, 24h ; '$'
0x180011e01  mov     [rsp+0C08h+var_BD0], rsi; __int64
0x180011e06  mov     [rsp+0C08h+var_BD8], rdi; __int64
0x180011e0b  mov     qword ptr [rsp+0C08h+var_BE0], rdi; char
0x180011e10  mov     rsi, [rsp+0C08h+var_BC0]
0x180011e15  mov     qword ptr [rsp+0C08h+var_BE8], rsi; char
0x180011e1a  mov     r9, rbx
0x180011e1d  mov     rcx, [rcx+10h]; LoggerHandle
0x180011e21  call    WPP_SF_qqqSS
0x180011e26  jmp     short loc_180011E2D
0x180011e28  mov     rsi, [rsp+0C08h+var_BC0]
0x180011e2d  mov     rdx, rdi; struct _VISIBLE_DOCK *
0x180011e30  mov     rcx, rsi; this
0x180011e33  call    ?Live@Dock@@QEAAXPEBU_VISIBLE_DOCK@@@Z; Dock::Live(_VISIBLE_DOCK const *)
0x180011e38  jmp     short loc_180011EA5
0x180011e3a  lea     rax, WPP_GLOBAL_Control
0x180011e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e48  cmp     rcx, rax
0x180011e4b  jz      short loc_180011E7A
0x180011e4d  cmp     byte ptr [rcx+19h], 3
0x180011e51  jb      short loc_180011E7A
0x180011e53  test    byte ptr [rcx+1Ch], 1
0x180011e57  jz      short loc_180011E7A
0x180011e59  mov     edx, 25h ; '%'
0x180011e5e  mov     [rsp+0C08h+var_BD8], rsi; __int64
0x180011e63  mov     qword ptr [rsp+0C08h+var_BE0], rdi; __int64
0x180011e68  mov     qword ptr [rsp+0C08h+var_BE8], rdi; char
0x180011e6d  mov     r9, rbx
0x180011e70  mov     rcx, [rcx+10h]; LoggerHandle
0x180011e74  call    WPP_SF_qqSS
0x180011e79  nop
0x180011e7a  mov     r8, rdi; struct _VISIBLE_DOCK *
0x180011e7d  mov     rdx, rsi; Str
0x180011e80  lea     rcx, [rsp+0C08h+var_BA8]; this
0x180011e85  call    ??0Dock@@QEAA@PEBGAEBU_VISIBLE_DOCK@@@Z; Dock::Dock(ushort const *,_VISIBLE_DOCK const &)
0x180011e8a  nop
0x180011e8b  lea     rcx, [rbx+28h]
0x180011e8f  lea     rdx, [rsp+0C08h+var_BA8]
0x180011e94  call    ?push_back@?$vector@VDock@@V?$allocator@VDock@@@std@@@std@@QEAAXAEBVDock@@@Z; std::vector<Dock>::push_back(Dock const &)
0x180011e99  nop
0x180011e9a  lea     rcx, [rsp+0C08h+var_BA8]; this
0x180011e9f  call    ??1Dock@@QEAA@XZ; Dock::~Dock(void)
0x180011ea4  nop
0x180011ea5  xor     edi, edi
0x180011ea7  jmp     short loc_180011EBA
0x180011ea9  mov     edi, 8007000Eh
0x180011eae  jmp     short loc_180011EB5
0x180011eb0  mov     edi, 80004005h
0x180011eb5  mov     rbx, [rsp+0C08h+var_BC8]
0x180011eba  mov     rcx, rbx; lpCriticalSection
0x180011ebd  call    cs:__imp_LeaveCriticalSection
0x180011ec3  mov     eax, edi
0x180011ec5  mov     rcx, [rsp+0C08h+var_28]
0x180011ecd  xor     rcx, rsp; StackCookie
0x180011ed0  call    __security_check_cookie
0x180011ed5  add     rsp, 0BF0h
0x180011edc  pop     rdi
0x180011edd  pop     rsi
0x180011ede  pop     rbx
0x180011edf  retn
```
