# CMSMQTriggersConfig::get_DefaultMsgBodySize(long *)

- ea: `0x18000c7b0`
- end: `0x18000c81b`
- name: `?get_DefaultMsgBodySize@CMSMQTriggersConfig@@UEAAJPEAJ@Z`
- size: `107`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000c7b0`
- `0x180016220`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::get_DefaultMsgBodySize(CMSMQTriggersConfig *this, unsigned int *a2)
{
  CMSMQTriggersConfig *v2; // rcx

  if ( a2 )
  {
    GetNumericConfigParm(&qword_18002D290, L"DefaultMsgBodySize", a2, 0x800u);
    return 0;
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820735);
    return 3222146561LL;
  }
}

```

## disassembly

```asm
0x18000c7b0  sub     rsp, 28h
0x18000c7b4  test    rdx, rdx
0x18000c7b7  jnz     short loc_18000C7F8
0x18000c7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7c0  lea     rax, WPP_GLOBAL_Control
0x18000c7c7  cmp     rcx, rax
0x18000c7ca  jz      short loc_18000C7E7
0x18000c7cc  test    byte ptr [rcx+1Ch], 1
0x18000c7d0  jz      short loc_18000C7E7
0x18000c7d2  mov     rcx, [rcx+10h]
0x18000c7d6  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000c7dd  mov     edx, 12h
0x18000c7e2  call    WPP_SF_
0x18000c7e7  mov     edx, 0C00E0E01h; int
0x18000c7ec  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000c7f1  mov     eax, 0C00E0E01h
0x18000c7f6  jmp     short loc_18000C816
0x18000c7f8  mov     r8, rdx; unsigned int *
0x18000c7fb  lea     rcx, qword_18002D290; wchar_t *
0x18000c802  lea     rdx, aDefaultmsgbody; "DefaultMsgBodySize"
0x18000c809  mov     r9d, 800h; unsigned int
0x18000c80f  call    ?GetNumericConfigParm@@YAXPEB_W0PEAKK@Z; GetNumericConfigParm(wchar_t const *,wchar_t const *,ulong *,ulong)
0x18000c814  xor     eax, eax
0x18000c816  add     rsp, 28h
0x18000c81a  retn
```
