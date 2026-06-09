# CMSMQTriggersConfig::put_DefaultMsgBodySize(long)

- ea: `0x18000ca90`
- end: `0x18000cb4a`
- name: `?put_DefaultMsgBodySize@CMSMQTriggersConfig@@UEAAJJ@Z`
- size: `186`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000ca90`
- `0x18000cd90`
- `0x18001634c`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::put_DefaultMsgBodySize(CMSMQTriggersConfig *this, unsigned int a2)
{
  CMSMQTriggersConfig *v2; // rcx
  CMSMQTriggersConfig *v4; // rcx

  if ( a2 > 0x3FFAE8 )
  {
    v4 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids, a2, 4193000);
    CMSMQTriggersConfig::SetComClassError(v4, -1072820735);
    return 3222146561LL;
  }
  else if ( SetNumericConfigParm(&qword_18002D290, L"DefaultMsgBodySize", a2) )
  {
    return 0;
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820723);
    return 3222146573LL;
  }
}

```

## disassembly

```asm
0x18000ca90  sub     rsp, 38h
0x18000ca94  mov     r8d, 3FFAE8h
0x18000ca9a  mov     r9d, edx
0x18000ca9d  cmp     edx, r8d
0x18000caa0  ja      short loc_18000CB03
0x18000caa2  test    edx, edx
0x18000caa4  js      short loc_18000CB03
0x18000caa6  mov     r8d, edx; unsigned int
0x18000caa9  lea     rcx, qword_18002D290; wchar_t *
0x18000cab0  lea     rdx, aDefaultmsgbody; "DefaultMsgBodySize"
0x18000cab7  call    ?SetNumericConfigParm@@YA_NPEB_W0K@Z; SetNumericConfigParm(wchar_t const *,wchar_t const *,ulong)
0x18000cabc  test    al, al
0x18000cabe  jnz     short loc_18000CAFF
0x18000cac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cac7  lea     rax, WPP_GLOBAL_Control
0x18000cace  cmp     rcx, rax
0x18000cad1  jz      short loc_18000CAEE
0x18000cad3  test    byte ptr [rcx+1Ch], 1
0x18000cad7  jz      short loc_18000CAEE
0x18000cad9  mov     rcx, [rcx+10h]
0x18000cadd  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cae4  mov     edx, 14h
0x18000cae9  call    WPP_SF_
0x18000caee  mov     edx, 0C00E0E0Dh; int
0x18000caf3  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000caf8  mov     eax, 0C00E0E0Dh
0x18000cafd  jmp     short loc_18000CB45
0x18000caff  xor     eax, eax
0x18000cb01  jmp     short loc_18000CB45
0x18000cb03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb0a  lea     rax, WPP_GLOBAL_Control
0x18000cb11  cmp     rcx, rax
0x18000cb14  jz      short loc_18000CB36
0x18000cb16  test    byte ptr [rcx+1Ch], 1
0x18000cb1a  jz      short loc_18000CB36
0x18000cb1c  mov     rcx, [rcx+10h]
0x18000cb20  mov     edx, 13h
0x18000cb25  mov     [rsp+38h+var_18], r8d
0x18000cb2a  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cb31  call    WPP_SF_dd
0x18000cb36  mov     edx, 0C00E0E01h; int
0x18000cb3b  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000cb40  mov     eax, 0C00E0E01h
0x18000cb45  add     rsp, 38h
0x18000cb49  retn
```
