# DockCache::MarkAllStale(void)

- ea: `0x180012568`
- end: `0x180012625`
- name: `?MarkAllStale@DockCache@@QEAAXXZ`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019900`

## callees

- `0x18000c308`
- `0x180012568`
- `0x180012b34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001261e`

## pseudocode

```c
void __fastcall DockCache::MarkAllStale(LPCRITICAL_SECTION lpCriticalSection)
{
  Dock *i; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      lpCriticalSection);
  }
  EnterCriticalSection(lpCriticalSection);
  for ( i = (Dock *)lpCriticalSection[1].DebugInfo;
        i != *(Dock **)&lpCriticalSection[1].LockCount;
        i = (Dock *)((char *)i + 2936) )
  {
    Dock::Stale(i);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      lpCriticalSection);
  }
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180012568  mov     [rsp+arg_8], rbx
0x18001256d  mov     [rsp+arg_10], rsi
0x180012572  push    rdi
0x180012573  sub     rsp, 20h
0x180012577  mov     rdi, rcx
0x18001257a  lea     rsi, WPP_GLOBAL_Control
0x180012581  mov     rcx, cs:WPP_GLOBAL_Control
0x180012588  cmp     rcx, rsi
0x18001258b  jz      short loc_1800125B1
0x18001258d  cmp     byte ptr [rcx+19h], 4
0x180012591  jb      short loc_1800125B1
0x180012593  test    byte ptr [rcx+1Ch], 1
0x180012597  jz      short loc_1800125B1
0x180012599  mov     edx, 3Ch ; '<'
0x18001259e  mov     r9, rdi
0x1800125a1  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x1800125a8  mov     rcx, [rcx+10h]
0x1800125ac  call    WPP_SF_q
0x1800125b1  mov     [rsp+28h+arg_0], rdi
0x1800125b6  mov     rcx, rdi; lpCriticalSection
0x1800125b9  call    cs:__imp_EnterCriticalSection
0x1800125bf  nop
0x1800125c0  mov     rbx, [rdi+28h]
0x1800125c4  cmp     rbx, [rdi+30h]
0x1800125c8  jz      short loc_1800125DB
0x1800125ca  mov     rcx, rbx; this
0x1800125cd  call    ?Stale@Dock@@QEAAXXZ; Dock::Stale(void)
0x1800125d2  add     rbx, 0B78h
0x1800125d9  jmp     short loc_1800125C4
0x1800125db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125e2  cmp     rcx, rsi
0x1800125e5  jz      short loc_18001260C
0x1800125e7  cmp     byte ptr [rcx+19h], 4
0x1800125eb  jb      short loc_18001260C
0x1800125ed  test    byte ptr [rcx+1Ch], 1
0x1800125f1  jz      short loc_18001260C
0x1800125f3  mov     edx, 3Dh ; '='
0x1800125f8  mov     r9, rdi
0x1800125fb  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180012602  mov     rcx, [rcx+10h]
0x180012606  call    WPP_SF_q
0x18001260b  nop
0x18001260c  mov     rcx, rdi
0x18001260f  mov     rbx, [rsp+28h+arg_8]
0x180012614  mov     rsi, [rsp+28h+arg_10]
0x180012619  add     rsp, 20h
0x18001261d  pop     rdi
0x18001261e  jmp     cs:__imp_LeaveCriticalSection
```
