# CscOfflineLviewCacheCheckAndSetAlwaysOfflineEcp

- ea: `0x14007dee4`
- end: `0x14007e060`
- name: `CscOfflineLviewCacheCheckAndSetAlwaysOfflineEcp`
- size: `380`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140008610`

## callees

- `0x14000f8b0`
- `0x14001a624`
- `0x14001aae0`
- `0x14002f010`
- `0x14002f440`
- `0x140053278`
- `0x14006f270`
- `0x14007dee4`
- `0x14007e070`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007df56`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007df56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007dff1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007dff1`

## pseudocode

```c
void __fastcall CscOfflineLviewCacheCheckAndSetAlwaysOfflineEcp(__int64 a1, const UNICODE_STRING *a2)
{
  int v2; // edi
  char v5; // si
  __int64 LongestPrefixEntry; // rax
  __int64 v7; // rbx
  __int64 v8; // r9
  __int64 v9; // [rsp+48h] [rbp-80h] BYREF
  _DWORD v10[20]; // [rsp+50h] [rbp-78h] BYREF

  v2 = 0;
  v5 = 0;
  memset(v10, 0, sizeof(v10));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, a2);
  KeEnterCriticalRegion();
  LongestPrefixEntry = CscOfflineLviewCacheFindLongestPrefixEntry((PERESOURCE)(CscDevExtn + 384), a2);
  v9 = LongestPrefixEntry;
  v7 = LongestPrefixEntry;
  if ( LongestPrefixEntry )
  {
    if ( (int)CscStoreQueryInformationEntryEx(*(_QWORD *)(LongestPrefixEntry + 32), 0, (__int64)v10, 0, 0, 0, 0) >= 0 )
    {
      if ( (v10[1] & 0xC) != 0 || (v10[0] & 0x120000) != 0 )
      {
        v5 = 1;
        CscEcpSetType(a1, 3);
      }
    }
    else
    {
      v2 = 1408;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 4), 0xFFFFFFFF) == 1 )
      CscOfflineLviewCachepDeleteListEntry(&v9);
  }
  else
  {
    v2 = 1398;
  }
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v8) = v5 != 0 ? 89 : 78;
    WPP_SF_cD(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids, v8, v2);
  }
}

```

## disassembly

```asm
0x14007dee4  mov     [rsp+arg_10], rbx
0x14007dee9  mov     [rsp+arg_18], rbp
0x14007deee  push    rsi
0x14007deef  push    rdi
0x14007def0  push    r14
0x14007def2  sub     rsp, 0B0h
0x14007def9  mov     rax, cs:__security_cookie
0x14007df00  xor     rax, rsp
0x14007df03  mov     [rsp+0C8h+var_28], rax
0x14007df0b  xor     edi, edi
0x14007df0d  mov     rbx, rdx
0x14007df10  mov     rbp, rcx
0x14007df13  xor     edx, edx; Val
0x14007df15  lea     rcx, [rsp+0C8h+var_78]; void *
0x14007df1a  mov     sil, dil
0x14007df1d  lea     r8d, [rdi+50h]; Size
0x14007df21  call    memset
0x14007df26  mov     rcx, cs:WPP_GLOBAL_Control
0x14007df2d  lea     r14, WPP_GLOBAL_Control
0x14007df34  cmp     rcx, r14
0x14007df37  jz      short loc_14007DF56
0x14007df39  mov     eax, [rcx+2Ch]
0x14007df3c  test    al, 20h
0x14007df3e  jz      short loc_14007DF56
0x14007df40  mov     rcx, [rcx+18h]
0x14007df44  lea     edx, [rdi+1Ch]
0x14007df47  mov     r9, rbx
0x14007df4a  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x14007df51  call    WPP_SF_Z
0x14007df56  call    cs:__imp_KeEnterCriticalRegion
0x14007df5d  nop     dword ptr [rax+rax+00h]
0x14007df62  mov     rcx, cs:CscDevExtn
0x14007df69  mov     rdx, rbx; String2
0x14007df6c  add     rcx, 180h; Resource
0x14007df73  call    CscOfflineLviewCacheFindLongestPrefixEntry
0x14007df78  mov     [rsp+0C8h+var_80], rax
0x14007df7d  mov     rbx, rax
0x14007df80  test    rax, rax
0x14007df83  jnz     short loc_14007DF8C
0x14007df85  mov     edi, 576h
0x14007df8a  jmp     short loc_14007DFF1
0x14007df8c  mov     rcx, [rax+20h]
0x14007df90  lea     r8, [rsp+0C8h+var_78]
0x14007df95  mov     [rsp+0C8h+var_98], rdi
0x14007df9a  xor     r9d, r9d
0x14007df9d  mov     [rsp+0C8h+var_A0], rdi
0x14007dfa2  xor     edx, edx
0x14007dfa4  mov     [rsp+0C8h+var_A8], rdi
0x14007dfa9  call    CscStoreQueryInformationEntryEx
0x14007dfae  test    eax, eax
0x14007dfb0  jns     short loc_14007DFB9
0x14007dfb2  mov     edi, 580h
0x14007dfb7  jmp     short loc_14007DFDA
0x14007dfb9  test    [rsp+0C8h+var_74], 0Ch
0x14007dfbe  jnz     short loc_14007DFCA
0x14007dfc0  test    [rsp+0C8h+var_78], 120000h
0x14007dfc8  jz      short loc_14007DFDA
0x14007dfca  mov     edx, 3
0x14007dfcf  mov     rcx, rbp
0x14007dfd2  mov     sil, 1
0x14007dfd5  call    CscEcpSetType
0x14007dfda  or      eax, 0FFFFFFFFh
0x14007dfdd  lock xadd [rbx+4], eax
0x14007dfe2  cmp     eax, 1
0x14007dfe5  jnz     short loc_14007DFF1
0x14007dfe7  lea     rcx, [rsp+0C8h+var_80]
0x14007dfec  call    CscOfflineLviewCachepDeleteListEntry
0x14007dff1  call    cs:__imp_KeLeaveCriticalRegion
0x14007dff8  nop     dword ptr [rax+rax+00h]
0x14007dffd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e004  cmp     rcx, r14
0x14007e007  jz      short loc_14007E037
0x14007e009  mov     eax, [rcx+2Ch]
0x14007e00c  test    al, 20h
0x14007e00e  jz      short loc_14007E037
0x14007e010  mov     rcx, [rcx+18h]
0x14007e014  lea     r8, WPP_e56e5c7c71ce3fc5dce6d5b40435d5ff_Traceguids
0x14007e01b  neg     sil
0x14007e01e  mov     dword ptr [rsp+0C8h+var_A8], edi
0x14007e022  mov     edx, 1Dh
0x14007e027  sbb     r9b, r9b
0x14007e02a  and     r9b, 0Bh
0x14007e02e  add     r9b, 4Eh ; 'N'
0x14007e032  call    WPP_SF_cD
0x14007e037  mov     rcx, [rsp+0C8h+var_28]
0x14007e03f  xor     rcx, rsp; StackCookie
0x14007e042  call    __security_check_cookie
0x14007e047  lea     r11, [rsp+0C8h+var_18]
0x14007e04f  mov     rbx, [r11+30h]
0x14007e053  mov     rbp, [r11+38h]
0x14007e057  mov     rsp, r11
0x14007e05a  pop     r14
0x14007e05c  pop     rdi
0x14007e05d  pop     rsi
0x14007e05e  retn
```
