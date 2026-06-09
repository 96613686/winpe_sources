# CMSMQTriggersConfig::put_MaxThreads(long)

- ea: `0x18000ccd0`
- end: `0x18000cd88`
- name: `?put_MaxThreads@CMSMQTriggersConfig@@UEAAJJ@Z`
- size: `184`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000ccd0`
- `0x18000cd90`
- `0x18001634c`

## string_xrefs

- `0x18000cceb`: `MaxThreads`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::put_MaxThreads(CMSMQTriggersConfig *this, unsigned int a2)
{
  CMSMQTriggersConfig *v2; // rcx
  CMSMQTriggersConfig *v4; // rcx

  if ( a2 > 0x64 || (int)a2 < 1 )
  {
    v4 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids, a2, 100);
    CMSMQTriggersConfig::SetComClassError(v4, -1072820735);
    return 3222146561LL;
  }
  else if ( SetNumericConfigParm(&qword_18002D290, L"MaxThreads", a2) )
  {
    return 0;
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820723);
    return 3222146573LL;
  }
}

```

## disassembly

```asm
0x18000ccd0  sub     rsp, 38h
0x18000ccd4  mov     r9d, edx
0x18000ccd7  cmp     edx, 64h ; 'd'
0x18000ccda  ja      short loc_18000CD3E
0x18000ccdc  cmp     edx, 1
0x18000ccdf  jl      short loc_18000CD3E
0x18000cce1  mov     r8d, edx; unsigned int
0x18000cce4  lea     rcx, qword_18002D290; wchar_t *
0x18000cceb  lea     rdx, aMaxthreads; "MaxThreads"
0x18000ccf2  call    ?SetNumericConfigParm@@YA_NPEB_W0K@Z; SetNumericConfigParm(wchar_t const *,wchar_t const *,ulong)
0x18000ccf7  test    al, al
0x18000ccf9  jnz     short loc_18000CD3A
0x18000ccfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd02  lea     rax, WPP_GLOBAL_Control
0x18000cd09  cmp     rcx, rax
0x18000cd0c  jz      short loc_18000CD29
0x18000cd0e  test    byte ptr [rcx+1Ch], 1
0x18000cd12  jz      short loc_18000CD29
0x18000cd14  mov     rcx, [rcx+10h]
0x18000cd18  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cd1f  mov     edx, 11h
0x18000cd24  call    WPP_SF_
0x18000cd29  mov     edx, 0C00E0E0Dh; int
0x18000cd2e  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000cd33  mov     eax, 0C00E0E0Dh
0x18000cd38  jmp     short loc_18000CD83
0x18000cd3a  xor     eax, eax
0x18000cd3c  jmp     short loc_18000CD83
0x18000cd3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd45  lea     rax, WPP_GLOBAL_Control
0x18000cd4c  cmp     rcx, rax
0x18000cd4f  jz      short loc_18000CD74
0x18000cd51  test    byte ptr [rcx+1Ch], 1
0x18000cd55  jz      short loc_18000CD74
0x18000cd57  mov     rcx, [rcx+10h]
0x18000cd5b  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cd62  mov     edx, 10h
0x18000cd67  mov     [rsp+38h+var_18], 64h ; 'd'
0x18000cd6f  call    WPP_SF_dd
0x18000cd74  mov     edx, 0C00E0E01h; int
0x18000cd79  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000cd7e  mov     eax, 0C00E0E01h
0x18000cd83  add     rsp, 38h
0x18000cd87  retn
```
