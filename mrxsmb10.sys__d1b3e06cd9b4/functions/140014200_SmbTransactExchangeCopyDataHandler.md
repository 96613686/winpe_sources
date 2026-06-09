# SmbTransactExchangeCopyDataHandler

- ea: `0x140014200`
- end: `0x140014497`
- name: `SmbTransactExchangeCopyDataHandler`
- size: `663`
- prototype: `__int64 __fastcall(char *pContext, PMDL Mdl, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140006af0`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x140014200`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400143be`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400143be`
- `ntoskrnl!DbgPrint` at `0x1400142c8`
- `ntoskrnl!DbgPrint` at `0x1400142c8`
- `ntoskrnl!IoFreeMdl` at `0x140014445`
- `ntoskrnl!IoFreeMdl` at `0x140014445`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014278`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014278`

## string_xrefs

- `0x1400142c1`: `copyHandlerDiscard, st=%08lx\n`

## pseudocode

```c
__int64 __fastcall SmbTransactExchangeCopyDataHandler(char *pContext, PMDL Mdl, unsigned int a3)
{
  void *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v9; // esi
  PVOID MappedSystemVa; // rsi
  struct _MDL *v11; // rcx
  __int64 v12; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+20h] BYREF

  v12 = 0;
  LODWORD(v13) = 0;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
  v6 = (void *)*((_QWORD *)pContext + 91);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0);
    *((_QWORD *)pContext + 91) = 0;
    v7 = *((_DWORD *)pContext + 180);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v7);
    DbgPrint("copyHandlerDiscard, st=%08lx\n", v7);
    return v7;
  }
  else
  {
    v9 = 0;
    if ( *((_DWORD *)pContext + 90) == 3 || *((_DWORD *)pContext + 90) == 5 )
    {
      if ( (Mdl->MdlFlags & 5) != 0 )
        MappedSystemVa = Mdl->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000000u);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      }
      if ( MappedSystemVa )
        v9 = SmbTransactExchangeReceive(
               (unsigned int *)pContext,
               a3,
               a3,
               &v14,
               (__int64)MappedSystemVa,
               &v12,
               &v13,
               1024);
      else
        v9 = -1073741670;
    }
    else if ( *((_DWORD *)pContext + 90) == 6 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      }
      _InterlockedDecrement((volatile signed __int32 *)pContext + 126);
      if ( *((_DWORD *)pContext + 109) == *((_DWORD *)pContext + 108)
        && *((_DWORD *)pContext + 99) == *((_DWORD *)pContext + 98)
        && !*((_DWORD *)pContext + 126) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
        }
        *((_DWORD *)pContext + 12) = 0;
      }
    }
    else
    {
      *((_DWORD *)pContext + 12) = -1073741629;
    }
    while ( Mdl )
    {
      v11 = Mdl;
      Mdl = Mdl->Next;
      if ( v11 != (struct _MDL *)(pContext + 536) )
        IoFreeMdl(v11);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
    return v9;
  }
}

```

## disassembly

```asm
0x140014200  mov     rax, rsp
0x140014203  mov     [rax+10h], rbx
0x140014207  mov     [rax+18h], rbp
0x14001420b  push    rsi
0x14001420c  push    rdi
0x14001420d  push    r12
0x14001420f  push    r13
0x140014211  push    r14
0x140014213  sub     rsp, 50h
0x140014217  mov     ebp, r8d
0x14001421a  mov     qword ptr [rax-38h], 0
0x140014222  mov     rdi, rdx
0x140014225  mov     dword ptr [rax+8], 0
0x14001422c  mov     rbx, rcx
0x14001422f  mov     dword ptr [rax+20h], 0
0x140014236  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001423d  lea     r13, WPP_GLOBAL_Control
0x140014244  mov     r12d, 400h
0x14001424a  cmp     rcx, r13
0x14001424d  jz      short loc_14001426A
0x14001424f  test    [rcx+2Ch], r12d
0x140014253  jz      short loc_14001426A
0x140014255  mov     rcx, [rcx+18h]
0x140014259  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140014260  mov     edx, 38h ; '8'
0x140014265  call    WPP_SF_
0x14001426a  mov     rcx, [rbx+2D8h]; P
0x140014271  test    rcx, rcx
0x140014274  jz      short loc_1400142DB
0x140014276  xor     edx, edx; Tag
0x140014278  call    cs:__imp_ExFreePoolWithTag
0x14001427f  nop     dword ptr [rax+rax+00h]
0x140014284  mov     qword ptr [rbx+2D8h], 0
0x14001428f  mov     ebx, [rbx+2D0h]
0x140014295  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001429c  cmp     rcx, r13
0x14001429f  jz      short loc_1400142BF
0x1400142a1  test    [rcx+2Ch], r12d
0x1400142a5  jz      short loc_1400142BF
0x1400142a7  mov     rcx, [rcx+18h]
0x1400142ab  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x1400142b2  mov     edx, 39h ; '9'
0x1400142b7  mov     r9d, ebx
0x1400142ba  call    WPP_SF_d
0x1400142bf  mov     edx, ebx
0x1400142c1  lea     rcx, aCopyhandlerdis; "copyHandlerDiscard, st=%08lx\n"
0x1400142c8  call    cs:__imp_DbgPrint
0x1400142cf  nop     dword ptr [rax+rax+00h]
0x1400142d4  mov     eax, ebx
0x1400142d6  jmp     loc_14001447D
0x1400142db  mov     ecx, [rbx+168h]
0x1400142e1  lea     r14, [rbx+218h]
0x1400142e8  xor     esi, esi
0x1400142ea  sub     ecx, 3
0x1400142ed  jz      loc_14001439A
0x1400142f3  sub     ecx, 2
0x1400142f6  jz      loc_14001439A
0x1400142fc  cmp     ecx, 1
0x1400142ff  jz      short loc_14001430D
0x140014301  mov     dword ptr [rbx+30h], 0C00000C3h
0x140014308  jmp     loc_140014451
0x14001430d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014314  cmp     rcx, r13
0x140014317  jz      short loc_140014334
0x140014319  test    [rcx+2Ch], r12d
0x14001431d  jz      short loc_140014334
0x14001431f  mov     rcx, [rcx+18h]
0x140014323  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14001432a  mov     edx, 3Bh ; ';'
0x14001432f  call    WPP_SF_
0x140014334  lock dec dword ptr [rbx+1F8h]
0x14001433b  mov     eax, [rbx+1B0h]
0x140014341  cmp     [rbx+1B4h], eax
0x140014347  jnz     loc_140014451
0x14001434d  mov     eax, [rbx+188h]
0x140014353  cmp     [rbx+18Ch], eax
0x140014359  jnz     loc_140014451
0x14001435f  cmp     [rbx+1F8h], esi
0x140014365  jnz     loc_140014451
0x14001436b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014372  cmp     rcx, r13
0x140014375  jz      short loc_140014392
0x140014377  test    [rcx+2Ch], r12d
0x14001437b  jz      short loc_140014392
0x14001437d  mov     rcx, [rcx+18h]
0x140014381  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140014388  mov     edx, 3Ch ; '<'
0x14001438d  call    WPP_SF_
0x140014392  mov     [rbx+30h], esi
0x140014395  jmp     loc_140014451
0x14001439a  test    byte ptr [rdi+0Ah], 5
0x14001439e  jz      short loc_1400143A6
0x1400143a0  mov     rsi, [rdi+18h]
0x1400143a4  jmp     short loc_1400143CD
0x1400143a6  xor     r9d, r9d; RequestedAddress
0x1400143a9  mov     [rsp+78h+Priority], 40000000h; Priority
0x1400143b1  xor     edx, edx; AccessMode
0x1400143b3  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1400143b7  mov     rcx, rdi; MemoryDescriptorList
0x1400143ba  lea     r8d, [r9+1]; CacheType
0x1400143be  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400143c5  nop     dword ptr [rax+rax+00h]
0x1400143ca  mov     rsi, rax
0x1400143cd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400143d4  cmp     rcx, r13
0x1400143d7  jz      short loc_1400143F4
0x1400143d9  test    [rcx+2Ch], r12d
0x1400143dd  jz      short loc_1400143F4
0x1400143df  mov     rcx, [rcx+18h]
0x1400143e3  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x1400143ea  mov     edx, 3Ah ; ':'
0x1400143ef  call    WPP_SF_
0x1400143f4  test    rsi, rsi
0x1400143f7  jnz     short loc_140014400
0x1400143f9  mov     esi, 0C000009Ah
0x1400143fe  jmp     short loc_140014451
0x140014400  mov     [rsp+78h+var_40], r12d; int
0x140014405  lea     rax, [rsp+78h+arg_0]
0x14001440d  mov     [rsp+78h+var_48], rax; __int64
0x140014412  lea     r9, [rsp+78h+arg_18]
0x14001441a  lea     rax, [rsp+78h+var_38]
0x14001441f  mov     r8d, ebp
0x140014422  mov     qword ptr [rsp+78h+Priority], rax; __int64
0x140014427  mov     edx, ebp
0x140014429  mov     rcx, rbx; pContext
0x14001442c  mov     qword ptr [rsp+78h+BugCheckOnFailure], rsi; __int64
0x140014431  call    SmbTransactExchangeReceive
0x140014436  mov     esi, eax
0x140014438  jmp     short loc_140014451
0x14001443a  mov     rcx, rdi; Mdl
0x14001443d  mov     rdi, [rdi]
0x140014440  cmp     rcx, r14
0x140014443  jz      short loc_140014451
0x140014445  call    cs:__imp_IoFreeMdl
0x14001444c  nop     dword ptr [rax+rax+00h]
0x140014451  test    rdi, rdi
0x140014454  jnz     short loc_14001443A
0x140014456  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001445d  cmp     rcx, r13
0x140014460  jz      short loc_14001447B
0x140014462  test    [rcx+2Ch], r12d
0x140014466  jz      short loc_14001447B
0x140014468  mov     rcx, [rcx+18h]
0x14001446c  lea     edx, [rdi+3Dh]
0x14001446f  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140014476  call    WPP_SF_
0x14001447b  mov     eax, esi
0x14001447d  lea     r11, [rsp+78h+var_28]
0x140014482  mov     rbx, [r11+38h]
0x140014486  mov     rbp, [r11+40h]
0x14001448a  mov     rsp, r11
0x14001448d  pop     r14
0x14001448f  pop     r13
0x140014491  pop     r12
0x140014493  pop     rdi
0x140014494  pop     rsi
0x140014495  retn
```
