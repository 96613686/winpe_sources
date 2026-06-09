# DockCache::NotVisible(ushort const *,_VISIBLE_DOCK const &)

- ea: `0x180012698`
- end: `0x18001277f`
- name: `?NotVisible@DockCache@@QEAAXPEBGAEBU_VISIBLE_DOCK@@@Z`
- size: `231`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, const struct _VISIBLE_DOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018be0`

## callees

- `0x180011c2c`
- `0x180012698`
- `0x180012b34`
- `0x1800136a0`
- `0x180013b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012778`

## pseudocode

```c
void __fastcall DockCache::NotVisible(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        const struct _VISIBLE_DOCK *a3)
{
  Dock *v6; // rsi
  struct Dock *v7; // [rsp+60h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+78h] [rbp+20h]

  v8 = this;
  EnterCriticalSection(this);
  v7 = 0;
  if ( (int)DockCache::FindDock((DockCache *)this, a2, &v7) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)a3, (__int64)a3, (__int64)a2);
    }
  }
  else
  {
    v6 = v7;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v7, (char)a3, (__int64)a3, (__int64)a2);
    }
    Dock::Stale(v6);
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180012698  mov     [rsp+arg_8], rbx
0x18001269d  push    rbp
0x18001269e  push    rsi
0x18001269f  push    rdi
0x1800126a0  sub     rsp, 40h
0x1800126a4  mov     rdi, r8
0x1800126a7  mov     rbp, rdx
0x1800126aa  mov     rbx, rcx
0x1800126ad  mov     [rsp+58h+arg_18], rcx
0x1800126b2  call    cs:__imp_EnterCriticalSection
0x1800126b8  nop
0x1800126b9  mov     [rsp+58h+arg_0], 0
0x1800126c2  lea     r8, [rsp+58h+arg_0]; struct Dock **
0x1800126c7  mov     rdx, rbp; unsigned __int16 *
0x1800126ca  mov     rcx, rbx; this
0x1800126cd  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x1800126d2  test    eax, eax
0x1800126d4  js      short loc_180012729
0x1800126d6  lea     rax, WPP_GLOBAL_Control
0x1800126dd  mov     rsi, [rsp+58h+arg_0]
0x1800126e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126e9  cmp     rcx, rax
0x1800126ec  jz      short loc_18001271F
0x1800126ee  cmp     byte ptr [rcx+19h], 3
0x1800126f2  jb      short loc_18001271F
0x1800126f4  test    byte ptr [rcx+1Ch], 1
0x1800126f8  jz      short loc_18001271F
0x1800126fa  mov     edx, 3Eh ; '>'
0x1800126ff  mov     [rsp+58h+var_20], rbp; __int64
0x180012704  mov     [rsp+58h+var_28], rdi; __int64
0x180012709  mov     qword ptr [rsp+58h+var_30], rdi; char
0x18001270e  mov     qword ptr [rsp+58h+var_38], rsi; char
0x180012713  mov     r9, rbx
0x180012716  mov     rcx, [rcx+10h]; LoggerHandle
0x18001271a  call    WPP_SF_qqqSS
0x18001271f  mov     rcx, rsi; this
0x180012722  call    ?Stale@Dock@@QEAAXXZ; Dock::Stale(void)
0x180012727  jmp     short loc_180012769
0x180012729  lea     rax, WPP_GLOBAL_Control
0x180012730  mov     rcx, cs:WPP_GLOBAL_Control
0x180012737  cmp     rcx, rax
0x18001273a  jz      short loc_180012769
0x18001273c  cmp     byte ptr [rcx+19h], 3
0x180012740  jb      short loc_180012769
0x180012742  test    byte ptr [rcx+1Ch], 1
0x180012746  jz      short loc_180012769
0x180012748  mov     edx, 3Fh ; '?'
0x18001274d  mov     [rsp+58h+var_28], rbp; __int64
0x180012752  mov     qword ptr [rsp+58h+var_30], rdi; __int64
0x180012757  mov     qword ptr [rsp+58h+var_38], rdi; char
0x18001275c  mov     r9, rbx
0x18001275f  mov     rcx, [rcx+10h]; LoggerHandle
0x180012763  call    WPP_SF_qqSS
0x180012768  nop
0x180012769  mov     rcx, rbx
0x18001276c  mov     rbx, [rsp+58h+arg_8]
0x180012771  add     rsp, 40h
0x180012775  pop     rdi
0x180012776  pop     rsi
0x180012777  pop     rbp
0x180012778  jmp     cs:__imp_LeaveCriticalSection
```
