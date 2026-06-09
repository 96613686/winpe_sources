# CMSMQTriggersConfig::put_InitTimeout(long)

- ea: `0x18000cb50`
- end: `0x18000cbfb`
- name: `?put_InitTimeout@CMSMQTriggersConfig@@UEAAJJ@Z`
- size: `171`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000cb50`
- `0x18001634c`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::put_InitTimeout(CMSMQTriggersConfig *this, unsigned int a2)
{
  CMSMQTriggersConfig *v2; // rcx
  CMSMQTriggersConfig *v4; // rcx

  if ( a2 >= 0x493E0 )
  {
    if ( SetNumericConfigParm(&qword_18002D290, L"InitTimeout", a2) )
    {
      return 0;
    }
    else
    {
      v4 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
      CMSMQTriggersConfig::SetComClassError(v4, -1072820723);
      return 3222146573LL;
    }
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820735);
    return 3222146561LL;
  }
}

```

## disassembly

```asm
0x18000cb50  sub     rsp, 28h
0x18000cb54  cmp     edx, 493E0h
0x18000cb5a  jnb     short loc_18000CB9B
0x18000cb5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb63  lea     rax, WPP_GLOBAL_Control
0x18000cb6a  cmp     rcx, rax
0x18000cb6d  jz      short loc_18000CB8A
0x18000cb6f  test    byte ptr [rcx+1Ch], 1
0x18000cb73  jz      short loc_18000CB8A
0x18000cb75  mov     rcx, [rcx+10h]
0x18000cb79  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cb80  mov     edx, 16h
0x18000cb85  call    WPP_SF_
0x18000cb8a  mov     edx, 0C00E0E01h; int
0x18000cb8f  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000cb94  mov     eax, 0C00E0E01h
0x18000cb99  jmp     short loc_18000CBF6
0x18000cb9b  mov     r8d, edx; unsigned int
0x18000cb9e  lea     rcx, qword_18002D290; wchar_t *
0x18000cba5  lea     rdx, aInittimeout; "InitTimeout"
0x18000cbac  call    ?SetNumericConfigParm@@YA_NPEB_W0K@Z; SetNumericConfigParm(wchar_t const *,wchar_t const *,ulong)
0x18000cbb1  test    al, al
0x18000cbb3  jnz     short loc_18000CBF4
0x18000cbb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbbc  lea     rax, WPP_GLOBAL_Control
0x18000cbc3  cmp     rcx, rax
0x18000cbc6  jz      short loc_18000CBE3
0x18000cbc8  test    byte ptr [rcx+1Ch], 1
0x18000cbcc  jz      short loc_18000CBE3
0x18000cbce  mov     rcx, [rcx+10h]
0x18000cbd2  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cbd9  mov     edx, 17h
0x18000cbde  call    WPP_SF_
0x18000cbe3  mov     edx, 0C00E0E0Dh; int
0x18000cbe8  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000cbed  mov     eax, 0C00E0E0Dh
0x18000cbf2  jmp     short loc_18000CBF6
0x18000cbf4  xor     eax, eax
0x18000cbf6  add     rsp, 28h
0x18000cbfa  retn
```
