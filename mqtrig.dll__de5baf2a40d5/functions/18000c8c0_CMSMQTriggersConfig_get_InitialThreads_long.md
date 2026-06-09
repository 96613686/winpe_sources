# CMSMQTriggersConfig::get_InitialThreads(long *)

- ea: `0x18000c8c0`
- end: `0x18000c92b`
- name: `?get_InitialThreads@CMSMQTriggersConfig@@UEAAJPEAJ@Z`
- size: `107`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000c8c0`
- `0x180016220`

## string_xrefs

- `0x18000c912`: `InitialThreads`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::get_InitialThreads(CMSMQTriggersConfig *this, unsigned int *a2)
{
  CMSMQTriggersConfig *v2; // rcx

  if ( a2 )
  {
    GetNumericConfigParm(&qword_18002D290, L"InitialThreads", a2, 5u);
    return 0;
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820735);
    return 3222146561LL;
  }
}

```

## disassembly

```asm
0x18000c8c0  sub     rsp, 28h
0x18000c8c4  test    rdx, rdx
0x18000c8c7  jnz     short loc_18000C908
0x18000c8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8d0  lea     rax, WPP_GLOBAL_Control
0x18000c8d7  cmp     rcx, rax
0x18000c8da  jz      short loc_18000C8F7
0x18000c8dc  test    byte ptr [rcx+1Ch], 1
0x18000c8e0  jz      short loc_18000C8F7
0x18000c8e2  mov     rcx, [rcx+10h]
0x18000c8e6  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000c8ed  mov     edx, 0Ch
0x18000c8f2  call    WPP_SF_
0x18000c8f7  mov     edx, 0C00E0E01h; int
0x18000c8fc  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000c901  mov     eax, 0C00E0E01h
0x18000c906  jmp     short loc_18000C926
0x18000c908  mov     r8, rdx; unsigned int *
0x18000c90b  lea     rcx, qword_18002D290; wchar_t *
0x18000c912  lea     rdx, aInitialthreads; "InitialThreads"
0x18000c919  mov     r9d, 5; unsigned int
0x18000c91f  call    ?GetNumericConfigParm@@YAXPEB_W0PEAKK@Z; GetNumericConfigParm(wchar_t const *,wchar_t const *,ulong *,ulong)
0x18000c924  xor     eax, eax
0x18000c926  add     rsp, 28h
0x18000c92a  retn
```
