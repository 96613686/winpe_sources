# DrExchangeManager::Start(void)

- ea: `0x14001195c`
- end: `0x140011a23`
- name: `?Start@DrExchangeManager@@QEAAHXZ`
- size: `199`
- prototype: `__int64 __fastcall(DrExchangeManager *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14001bf2c`
- `0x140025c40`
- `0x140026380`

## callees

- `0x14000324c`
- `0x1400036c0`
- `0x14001195c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140011970`
- `ntoskrnl!ExAcquireFastMutex` at `0x140011970`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400119d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400119d7`
- `rdbss!RxCreateMidAtlas` at `0x1400119c0`
- `rdbss!RxCreateMidAtlas` at `0x1400119c0`

## pseudocode

```c
_BOOL8 __fastcall DrExchangeManager::Start(DrExchangeManager *this)
{
  int v2; // eax

  ExAcquireFastMutex(&DrMutex);
  v2 = *((_DWORD *)this + 10);
  *((_DWORD *)this + 10) = 1;
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_e59448592ec538b831cf1e49bf008190_Traceguids);
    *((_QWORD *)this + 4) = RxCreateMidAtlas(0x400u, 0x80u);
  }
  ExReleaseFastMutex(&DrMutex);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_e59448592ec538b831cf1e49bf008190_Traceguids,
      *((_QWORD *)this + 4));
  return *((_QWORD *)this + 4) != 0;
}

```

## disassembly

```asm
0x14001195c  mov     [rsp+arg_0], rbx
0x140011961  push    rdi
0x140011962  sub     rsp, 20h
0x140011966  mov     rbx, rcx
0x140011969  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140011970  call    cs:__imp_ExAcquireFastMutex
0x140011977  nop     dword ptr [rax+rax+00h]
0x14001197c  mov     eax, [rbx+28h]
0x14001197f  lea     rdi, WPP_GLOBAL_Control
0x140011986  mov     dword ptr [rbx+28h], 1
0x14001198d  test    eax, eax
0x14001198f  jnz     short loc_1400119D0
0x140011991  mov     rcx, cs:WPP_GLOBAL_Control
0x140011998  cmp     rcx, rdi
0x14001199b  jz      short loc_1400119B6
0x14001199d  cmp     byte ptr [rcx+29h], 5
0x1400119a1  jb      short loc_1400119B6
0x1400119a3  mov     rcx, [rcx+18h]
0x1400119a7  lea     edx, [rax+0Ah]
0x1400119aa  lea     r8, WPP_e59448592ec538b831cf1e49bf008190_Traceguids
0x1400119b1  call    WPP_SF_
0x1400119b6  mov     edx, 80h; InitialAllocation
0x1400119bb  mov     ecx, 400h; MaximumNumberOfEntries
0x1400119c0  call    cs:__imp_RxCreateMidAtlas
0x1400119c7  nop     dword ptr [rax+rax+00h]
0x1400119cc  mov     [rbx+20h], rax
0x1400119d0  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400119d7  call    cs:__imp_ExReleaseFastMutex
0x1400119de  nop     dword ptr [rax+rax+00h]
0x1400119e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119ea  cmp     rcx, rdi
0x1400119ed  jz      short loc_140011A0E
0x1400119ef  cmp     byte ptr [rcx+29h], 5
0x1400119f3  jb      short loc_140011A0E
0x1400119f5  mov     r9, [rbx+20h]
0x1400119f9  lea     r8, WPP_e59448592ec538b831cf1e49bf008190_Traceguids
0x140011a00  mov     rcx, [rcx+18h]
0x140011a04  mov     edx, 0Bh
0x140011a09  call    WPP_SF_q
0x140011a0e  xor     eax, eax
0x140011a10  cmp     [rbx+20h], rax
0x140011a14  mov     rbx, [rsp+28h+arg_0]
0x140011a19  setnz   al
0x140011a1c  add     rsp, 20h
0x140011a20  pop     rdi
0x140011a21  retn
```
