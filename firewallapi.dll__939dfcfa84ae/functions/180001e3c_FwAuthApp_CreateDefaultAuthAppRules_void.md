# FwAuthApp::CreateDefaultAuthAppRules(void)

- ea: `0x180001e3c`
- end: `0x180001ed6`
- name: `?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ`
- size: `154`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800018e0`
- `0x180001b40`
- `0x1800218a0`
- `0x180044050`
- `0x180044110`
- `0x1800441d0`
- `0x180044490`
- `0x180044760`

## callees

- `0x180001e3c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180001ea0`
- `fwbase!FwReportReturnError` at `0x180001eb5`
- `fwbase!FwReportReturnError` at `0x180001ea0`
- `fwbase!FwReportReturnError` at `0x180001eb5`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001e60`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001e85`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001e60`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001e85`

## string_xrefs

- `0x180001e99`: `FwAuthApp::CreateDefaultAuthAppRules`
- `0x180001eae`: `FwAuthApp::CreateDefaultAuthAppRules`

## pseudocode

```c
__int64 __fastcall FwAuthApp::CreateDefaultAuthAppRules(FwAuthApp *this)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  int DefaultAuthAppRule; // eax

  v2 = 0;
  v3 = (_QWORD *)((char *)this + 72);
  if ( !*v3
    && (DefaultAuthAppRule = CreateDefaultAuthAppRule(v3, 6, *((unsigned int *)this + 16)),
        v2 = DefaultAuthAppRule,
        DefaultAuthAppRule < 0)
    || !*((_QWORD *)this + 10)
    && (DefaultAuthAppRule = CreateDefaultAuthAppRule((char *)this + 80, 17, *((unsigned int *)this + 16)),
        v2 = DefaultAuthAppRule,
        DefaultAuthAppRule < 0) )
  {
    FwReportReturnError("FwAuthApp::CreateDefaultAuthAppRules", (unsigned int)DefaultAuthAppRule);
    return (unsigned int)FwReportReturnError("FwAuthApp::CreateDefaultAuthAppRules", v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180001e3c  mov     [rsp+arg_0], rbx
0x180001e41  mov     [rsp+arg_8], rsi
0x180001e46  push    rdi
0x180001e47  sub     rsp, 20h
0x180001e4b  mov     rsi, rcx
0x180001e4e  xor     ebx, ebx
0x180001e50  add     rcx, 48h ; 'H'
0x180001e54  cmp     [rcx], rbx
0x180001e57  jnz     short loc_180001E72
0x180001e59  mov     r8d, [rsi+40h]
0x180001e5d  lea     edx, [rbx+6]
0x180001e60  call    cs:__imp_?CreateDefaultAuthAppRule@@YAJPEAPEAU_tag_FW_RULE@@GW4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultAuthAppRule(_tag_FW_RULE * *,ushort,_tag_FW_PROFILE_TYPE)
0x180001e67  nop     dword ptr [rax+rax+00h]
0x180001e6c  mov     ebx, eax
0x180001e6e  test    eax, eax
0x180001e70  js      short loc_180001E97
0x180001e72  lea     rcx, [rsi+50h]
0x180001e76  cmp     qword ptr [rcx], 0
0x180001e7a  jnz     short loc_180001EC3
0x180001e7c  mov     r8d, [rsi+40h]
0x180001e80  mov     edx, 11h
0x180001e85  call    cs:__imp_?CreateDefaultAuthAppRule@@YAJPEAPEAU_tag_FW_RULE@@GW4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultAuthAppRule(_tag_FW_RULE * *,ushort,_tag_FW_PROFILE_TYPE)
0x180001e8c  nop     dword ptr [rax+rax+00h]
0x180001e91  mov     ebx, eax
0x180001e93  test    eax, eax
0x180001e95  jns     short loc_180001EC3
0x180001e97  mov     edx, eax
0x180001e99  lea     rcx, aFwauthappCreat_0; "FwAuthApp::CreateDefaultAuthAppRules"
0x180001ea0  call    cs:__imp_FwReportReturnError
0x180001ea7  nop     dword ptr [rax+rax+00h]
0x180001eac  mov     edx, ebx
0x180001eae  lea     rcx, aFwauthappCreat_0; "FwAuthApp::CreateDefaultAuthAppRules"
0x180001eb5  call    cs:__imp_FwReportReturnError
0x180001ebc  nop     dword ptr [rax+rax+00h]
0x180001ec1  mov     ebx, eax
0x180001ec3  mov     rsi, [rsp+28h+arg_8]
0x180001ec8  mov     eax, ebx
0x180001eca  mov     rbx, [rsp+28h+arg_0]
0x180001ecf  add     rsp, 20h
0x180001ed3  pop     rdi
0x180001ed4  retn
```
