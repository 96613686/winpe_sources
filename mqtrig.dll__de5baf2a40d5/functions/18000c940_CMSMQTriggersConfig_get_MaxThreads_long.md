# CMSMQTriggersConfig::get_MaxThreads(long *)

- ea: `0x18000c940`
- end: `0x18000c9ab`
- name: `?get_MaxThreads@CMSMQTriggersConfig@@UEAAJPEAJ@Z`
- size: `107`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000c940`
- `0x180016220`

## string_xrefs

- `0x18000c992`: `MaxThreads`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::get_MaxThreads(CMSMQTriggersConfig *this, unsigned int *a2)
{
  CMSMQTriggersConfig *v2; // rcx

  if ( a2 )
  {
    GetNumericConfigParm(&qword_18002D290, L"MaxThreads", a2, 0x14u);
    return 0;
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820735);
    return 3222146561LL;
  }
}

```

## disassembly

```asm
0x18000c940  sub     rsp, 28h
0x18000c944  test    rdx, rdx
0x18000c947  jnz     short loc_18000C988
0x18000c949  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c950  lea     rax, WPP_GLOBAL_Control
0x18000c957  cmp     rcx, rax
0x18000c95a  jz      short loc_18000C977
0x18000c95c  test    byte ptr [rcx+1Ch], 1
0x18000c960  jz      short loc_18000C977
0x18000c962  mov     rcx, [rcx+10h]
0x18000c966  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000c96d  mov     edx, 0Fh
0x18000c972  call    WPP_SF_
0x18000c977  mov     edx, 0C00E0E01h; int
0x18000c97c  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000c981  mov     eax, 0C00E0E01h
0x18000c986  jmp     short loc_18000C9A6
0x18000c988  mov     r8, rdx; unsigned int *
0x18000c98b  lea     rcx, qword_18002D290; wchar_t *
0x18000c992  lea     rdx, aMaxthreads; "MaxThreads"
0x18000c999  mov     r9d, 14h; unsigned int
0x18000c99f  call    ?GetNumericConfigParm@@YAXPEB_W0PEAKK@Z; GetNumericConfigParm(wchar_t const *,wchar_t const *,ulong *,ulong)
0x18000c9a4  xor     eax, eax
0x18000c9a6  add     rsp, 28h
0x18000c9aa  retn
```
