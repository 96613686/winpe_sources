# HacDereference

- ea: `0x140005c90`
- end: `0x140005dd5`
- name: `HacDereference`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `25`
- callee_count: `8`
- tags: ``

## callers

- `0x1400022c0`
- `0x1400029d0`
- `0x140003bd0`
- `0x140004530`
- `0x140005de0`
- `0x1400070a0`
- `0x140009dd0`
- `0x14000be20`
- `0x14000c370`
- `0x14000fbc0`
- `0x1400146a0`
- `0x140014ea0`
- `0x140018a7c`
- `0x140019044`
- `0x14001bbbc`
- `0x14001c694`
- `0x140020154`
- `0x140020884`
- `0x140020af4`
- `0x140025484`
- `0x140025be0`
- `0x140027244`
- `0x140030934`
- `0x140030ef0`
- `0x1400316d0`

## callees

- `0x140003440`
- `0x140005c90`
- `0x140014ea0`
- `0x140015a40`
- `0x14001837c`
- `0x14001fad0`
- `0x140020234`
- `0x1400206e4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140005cbd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005cbd`
- `ntoskrnl!KeReleaseMutex` at `0x140005d8f`
- `ntoskrnl!KeReleaseMutex` at `0x140005db8`
- `ntoskrnl!KeReleaseMutex` at `0x140005d8f`
- `ntoskrnl!KeReleaseMutex` at `0x140005db8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d78`

## pseudocode

```c
LONG __fastcall HacDereference(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  bool v5; // zf
  void *v6; // rcx

  v2 = *(_QWORD *)(a2 + 40);
  KeWaitForSingleObject((PVOID)v2, Executive, 0, 0, 0);
  v5 = (*(_DWORD *)(a2 + 52))-- == 1;
  if ( v5 && !*(_DWORD *)(a2 + 56) )
  {
    if ( (*(_BYTE *)(a2 + 48) & 1) != 0 )
    {
      if ( (unsigned __int8)HacIsEntryFake(a2) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids, a2 + 64);
      }
      else
      {
        HacpRemoveEntry((__int64 *)a2);
        HacRemoveEntryFromLRUList(a2);
        *(_DWORD *)(v2 + 80) += -288 - *(unsigned __int16 *)(a2 + 66);
        DeleteDirCache(a1, a2);
        v6 = *(void **)(a2 + 96);
        if ( v6 )
          ExFreePoolWithTag(v6, 0);
        ExFreePoolWithTag((PVOID)a2, 0);
        v5 = (*(_DWORD *)(v2 + 76))-- == 1;
        if ( v5 )
        {
          KeReleaseMutex((PRKMUTEX)v2, 0);
          return HacFreeTable(a1, v2);
        }
      }
    }
    else
    {
      HacPruneHashTable(a1, v2);
    }
  }
  return KeReleaseMutex((PRKMUTEX)v2, 0);
}

```

## disassembly

```asm
0x140005c90  mov     [rsp+arg_0], rbx
0x140005c95  mov     [rsp+arg_10], rsi
0x140005c9a  push    rdi
0x140005c9b  sub     rsp, 30h
0x140005c9f  mov     rbx, [rdx+28h]
0x140005ca3  mov     rdi, rdx
0x140005ca6  mov     rsi, rcx
0x140005ca9  mov     [rsp+38h+Timeout], 0; Timeout
0x140005cb2  mov     rcx, rbx; Object
0x140005cb5  xor     r9d, r9d; Alertable
0x140005cb8  xor     r8d, r8d; WaitMode
0x140005cbb  xor     edx, edx; WaitReason
0x140005cbd  call    cs:__imp_KeWaitForSingleObject
0x140005cc4  nop     dword ptr [rax+rax+00h]
0x140005cc9  add     dword ptr [rdi+34h], 0FFFFFFFFh
0x140005ccd  jnz     loc_140005DB3
0x140005cd3  cmp     dword ptr [rdi+38h], 0
0x140005cd7  jnz     loc_140005DB3
0x140005cdd  test    byte ptr [rdi+30h], 1
0x140005ce1  jz      loc_140005DA8
0x140005ce7  mov     rcx, rdi
0x140005cea  call    HacIsEntryFake
0x140005cef  test    al, al
0x140005cf1  jz      short loc_140005D33
0x140005cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140005cfa  lea     rax, WPP_GLOBAL_Control
0x140005d01  cmp     rcx, rax
0x140005d04  jz      loc_140005DB3
0x140005d0a  mov     eax, [rcx+2Ch]
0x140005d0d  test    al, 1
0x140005d0f  jz      loc_140005DB3
0x140005d15  mov     rcx, [rcx+18h]
0x140005d19  lea     r9, [rdi+40h]
0x140005d1d  mov     edx, 22h ; '"'
0x140005d22  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140005d29  call    WPP_SF_Z
0x140005d2e  jmp     loc_140005DB3
0x140005d33  mov     rcx, rdi
0x140005d36  call    HacpRemoveEntry
0x140005d3b  mov     rcx, rdi
0x140005d3e  call    HacRemoveEntryFromLRUList
0x140005d43  movzx   eax, word ptr [rdi+42h]
0x140005d47  mov     ecx, 0FFFFFEE0h
0x140005d4c  sub     ecx, eax
0x140005d4e  mov     rdx, rdi
0x140005d51  add     [rbx+50h], ecx
0x140005d54  mov     rcx, rsi
0x140005d57  call    DeleteDirCache
0x140005d5c  mov     rcx, [rdi+60h]; P
0x140005d60  test    rcx, rcx
0x140005d63  jz      short loc_140005D73
0x140005d65  xor     edx, edx; Tag
0x140005d67  call    cs:__imp_ExFreePoolWithTag
0x140005d6e  nop     dword ptr [rax+rax+00h]
0x140005d73  xor     edx, edx; Tag
0x140005d75  mov     rcx, rdi; P
0x140005d78  call    cs:__imp_ExFreePoolWithTag
0x140005d7f  nop     dword ptr [rax+rax+00h]
0x140005d84  add     dword ptr [rbx+4Ch], 0FFFFFFFFh
0x140005d88  jnz     short loc_140005DB3
0x140005d8a  xor     edx, edx; Wait
0x140005d8c  mov     rcx, rbx; Mutex
0x140005d8f  call    cs:__imp_KeReleaseMutex
0x140005d96  nop     dword ptr [rax+rax+00h]
0x140005d9b  mov     rdx, rbx
0x140005d9e  mov     rcx, rsi
0x140005da1  call    HacFreeTable
0x140005da6  jmp     short loc_140005DC4
0x140005da8  mov     rdx, rbx
0x140005dab  mov     rcx, rsi
0x140005dae  call    HacPruneHashTable
0x140005db3  xor     edx, edx; Wait
0x140005db5  mov     rcx, rbx; Mutex
0x140005db8  call    cs:__imp_KeReleaseMutex
0x140005dbf  nop     dword ptr [rax+rax+00h]
0x140005dc4  mov     rbx, [rsp+38h+arg_0]
0x140005dc9  mov     rsi, [rsp+38h+arg_10]
0x140005dce  add     rsp, 30h
0x140005dd2  pop     rdi
0x140005dd3  retn
```
