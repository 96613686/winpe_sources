# CMSMQTriggersConfig::put_InitialThreads(long)

- ea: `0x18000cc10`
- end: `0x18000ccc8`
- name: `?put_InitialThreads@CMSMQTriggersConfig@@UEAAJJ@Z`
- size: `184`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000cc10`
- `0x18000cd90`
- `0x18001634c`

## string_xrefs

- `0x18000cc2b`: `InitialThreads`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::put_InitialThreads(CMSMQTriggersConfig *this, unsigned int a2)
{
  CMSMQTriggersConfig *v2; // rcx
  CMSMQTriggersConfig *v4; // rcx

  if ( a2 > 0x64 || (int)a2 < 1 )
  {
    v4 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids, a2, 100);
    CMSMQTriggersConfig::SetComClassError(v4, -1072820735);
    return 3222146561LL;
  }
  else if ( SetNumericConfigParm(&qword_18002D290, L"InitialThreads", a2) )
  {
    return 0;
  }
  else
  {
    v2 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v2, -1072820723);
    return 3222146573LL;
  }
}

```

## disassembly

```asm
0x18000cc10  sub     rsp, 38h
0x18000cc14  mov     r9d, edx
0x18000cc17  cmp     edx, 64h ; 'd'
0x18000cc1a  ja      short loc_18000CC7E
0x18000cc1c  cmp     edx, 1
0x18000cc1f  jl      short loc_18000CC7E
0x18000cc21  mov     r8d, edx; unsigned int
0x18000cc24  lea     rcx, qword_18002D290; wchar_t *
0x18000cc2b  lea     rdx, aInitialthreads; "InitialThreads"
0x18000cc32  call    ?SetNumericConfigParm@@YA_NPEB_W0K@Z; SetNumericConfigParm(wchar_t const *,wchar_t const *,ulong)
0x18000cc37  test    al, al
0x18000cc39  jnz     short loc_18000CC7A
0x18000cc3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc42  lea     rax, WPP_GLOBAL_Control
0x18000cc49  cmp     rcx, rax
0x18000cc4c  jz      short loc_18000CC69
0x18000cc4e  test    byte ptr [rcx+1Ch], 1
0x18000cc52  jz      short loc_18000CC69
0x18000cc54  mov     rcx, [rcx+10h]
0x18000cc58  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cc5f  mov     edx, 0Eh
0x18000cc64  call    WPP_SF_
0x18000cc69  mov     edx, 0C00E0E0Dh; int
0x18000cc6e  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000cc73  mov     eax, 0C00E0E0Dh
0x18000cc78  jmp     short loc_18000CCC3
0x18000cc7a  xor     eax, eax
0x18000cc7c  jmp     short loc_18000CCC3
0x18000cc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc85  lea     rax, WPP_GLOBAL_Control
0x18000cc8c  cmp     rcx, rax
0x18000cc8f  jz      short loc_18000CCB4
0x18000cc91  test    byte ptr [rcx+1Ch], 1
0x18000cc95  jz      short loc_18000CCB4
0x18000cc97  mov     rcx, [rcx+10h]
0x18000cc9b  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000cca2  mov     edx, 0Dh
0x18000cca7  mov     [rsp+38h+var_18], 64h ; 'd'
0x18000ccaf  call    WPP_SF_dd
0x18000ccb4  mov     edx, 0C00E0E01h; int
0x18000ccb9  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000ccbe  mov     eax, 0C00E0E01h
0x18000ccc3  add     rsp, 38h
0x18000ccc7  retn
```
