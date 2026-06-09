# CMSMQTriggersConfig::get_InitTimeout(long *)

- ea: `0x18000c830`
- end: `0x18000c8ac`
- name: `?get_InitTimeout@CMSMQTriggersConfig@@UEAAJPEAJ@Z`
- size: `124`
- prototype: `__int64 __fastcall(CMSMQTriggersConfig *this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18000c830`
- `0x180016220`

## pseudocode

```c
__int64 __fastcall CMSMQTriggersConfig::get_InitTimeout(CMSMQTriggersConfig *this, unsigned int *a2)
{
  CMSMQTriggersConfig *v3; // rcx

  if ( a2 )
  {
    GetNumericConfigParm(&qword_18002D290, L"InitTimeout", a2, 0x493E0u);
    if ( *a2 < 0x493E0 )
      *a2 = 300000;
    return 0;
  }
  else
  {
    v3 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
    CMSMQTriggersConfig::SetComClassError(v3, -1072820735);
    return 3222146561LL;
  }
}

```

## disassembly

```asm
0x18000c830  push    rbx
0x18000c832  sub     rsp, 20h
0x18000c836  mov     rbx, rdx
0x18000c839  test    rdx, rdx
0x18000c83c  jnz     short loc_18000C87A
0x18000c83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c845  lea     rax, WPP_GLOBAL_Control
0x18000c84c  cmp     rcx, rax
0x18000c84f  jz      short loc_18000C86A
0x18000c851  test    byte ptr [rcx+1Ch], 1
0x18000c855  jz      short loc_18000C86A
0x18000c857  mov     rcx, [rcx+10h]
0x18000c85b  lea     edx, [rbx+15h]
0x18000c85e  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18000c865  call    WPP_SF_
0x18000c86a  mov     ebx, 0C00E0E01h
0x18000c86f  mov     edx, ebx; int
0x18000c871  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18000c876  mov     eax, ebx
0x18000c878  jmp     short loc_18000C8A6
0x18000c87a  mov     r9d, 493E0h; unsigned int
0x18000c880  lea     rdx, aInittimeout; "InitTimeout"
0x18000c887  mov     r8, rbx; unsigned int *
0x18000c88a  lea     rcx, qword_18002D290; wchar_t *
0x18000c891  call    ?GetNumericConfigParm@@YAXPEB_W0PEAKK@Z; GetNumericConfigParm(wchar_t const *,wchar_t const *,ulong *,ulong)
0x18000c896  cmp     dword ptr [rbx], 493E0h
0x18000c89c  jnb     short loc_18000C8A4
0x18000c89e  mov     dword ptr [rbx], 493E0h
0x18000c8a4  xor     eax, eax
0x18000c8a6  add     rsp, 20h
0x18000c8aa  pop     rbx
0x18000c8ab  retn
```
