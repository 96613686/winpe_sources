# CMSMQTriggersConfig::get_TriggerStoreMachineName(wchar_t * *)

- ea: `0x18000c9c0`
- end: `0x18000ca7c`
- name: `?get_TriggerStoreMachineName@CMSMQTriggersConfig@@UEAAJPEAPEA_W@Z`
- size: `188`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009ab0`
- `0x18000c654`
- `0x18000c720`
- `0x18000c9c0`
- `0x1800161a8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c9f9`
- `KERNEL32!GetLastError` at `0x18000c9f9`
- `OLEAUT32!__imp_SysReAllocString` at `0x18000ca52`
- `OLEAUT32!__imp_SysReAllocString` at `0x18000ca52`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::get_TriggerStoreMachineName(CMSMQTriggersConfig *this, wchar_t **a2)
{
  CMSMQTriggersConfig *v3; // rcx
  DWORD LastError; // eax
  __int64; // rax
  const OLECHAR *v6; // rdx
  CMSMQTriggersConfig *v7; // rcx
  const OLECHAR **v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  if ( GetLocalMachineName((struct _bstr_t *)&v8) )
  {
    v3 = (CMSMQTriggersConfig *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids, LastError);
    }
    ((void (__stdcall *)(CMSMQTriggersConfig *, int))CMSMQTriggersConfig::SetComClassError)(v3, -1072820736);
    _bstr_t::_Free((_bstr_t *)&v8);
     = 3222146560LL;
    goto LABEL_21;
  }
  if ( a2 )
  {
    if ( v8 )
      v6 = *v8;
    else
      v6 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      SysReAllocString(a2, v6);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v7 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
        ((void (__stdcall *)(CMSMQTriggersConfig *, int))CMSMQTriggersConfig::SetComClassError)(v7, -1072820730);
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000CA67);
        _bstr_t::_Free((_bstr_t *)&v8);
         = 3222146566LL;
LABEL_21:
        ;
      }
    }
  }
  _bstr_t::_Free((_bstr_t *)&v8);
   = 0;
  goto LABEL_21;
}

```

## disassembly

```asm
0x18000c9c0  push    rbx
0x18000c9c2  sub     rsp, 20h
0x18000c9c6  mov     rbx, rdx
0x18000c9c9  mov     [rsp+28h+arg_10], 0
0x18000c9d2  lea     rcx, [rsp+28h+arg_10]; struct _bstr_t *
0x18000c9d7  call    ?GetLocalMachineName@@YAKPEAV_bstr_t@@@Z; GetLocalMachineName(_bstr_t *)
0x18000c9dc  test    eax, eax
0x18000c9de  jz      short loc_18000CA39
0x18000c9e0  lea     rcx, WPP_GLOBAL_Control
0x18000c9e7  mov     rax, cs:WPP_GLOBAL_Control
0x18000c9ee  cmp     rax, rcx
0x18000c9f1  jz      short loc_18000CA1E
0x18000c9f3  test    byte ptr [rax+1Ch], 1
0x18000c9f7  jz      short loc_18000CA1E
0x18000c9f9  call    cs:__imp_GetLastError
0x18000c9ff  mov     edx, 0Ah
0x18000ca04  mov     r9d, eax
0x18000ca07  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000ca0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca15  mov     rcx, [rcx+10h]
0x18000ca19  call    WPP_SF_d
0x18000ca1e  mov     ebx, 0C00E0E00h
0x18000ca23  mov     edx, ebx; int
0x18000ca25  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000ca2a  nop
0x18000ca2b  lea     rcx, [rsp+28h+arg_10]; this
0x18000ca30  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ca35  mov     eax, ebx
0x18000ca37  jmp     short loc_18000CA76
0x18000ca39  test    rbx, rbx
0x18000ca3c  jz      short loc_18000CA59
0x18000ca3e  mov     rax, [rsp+28h+arg_10]
0x18000ca43  test    rax, rax
0x18000ca46  jz      short loc_18000CA4D
0x18000ca48  mov     rdx, [rax]
0x18000ca4b  jmp     short loc_18000CA4F
0x18000ca4d  xor     edx, edx; psz
0x18000ca4f  mov     rcx, rbx; pbstr
0x18000ca52  call    cs:__imp_SysReAllocString
0x18000ca58  nop
0x18000ca59  lea     rcx, [rsp+28h+arg_10]; this
0x18000ca5e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ca63  xor     eax, eax
0x18000ca65  jmp     short loc_18000CA76
0x18000ca67  lea     rcx, [rsp+28h+arg_10]; this
0x18000ca6c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000ca71  mov     eax, 0C00E0E06h
0x18000ca76  add     rsp, 20h
0x18000ca7a  pop     rbx
0x18000ca7b  retn
```
