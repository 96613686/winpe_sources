# FwRule::CreateRule(void)

- ea: `0x180012dcc`
- end: `0x180012e89`
- name: `?CreateRule@FwRule@@AEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(FwRule *__hidden this)`
- caller_count: `40`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011a20`
- `0x180011cd0`
- `0x180011ed0`
- `0x180012120`
- `0x180012320`
- `0x1800124b0`
- `0x1800131a0`
- `0x1800133e0`
- `0x180013840`
- `0x180013a80`
- `0x180013c90`
- `0x1800158f0`
- `0x180015b00`
- `0x180015db0`
- `0x1800164a0`
- `0x1800178e0`
- `0x180018950`
- `0x180018cc0`
- `0x180018de0`
- `0x180018f10`
- `0x18001a170`
- `0x18001aba0`
- `0x18001bec0`
- `0x18001c550`
- `0x18001ed70`
- `0x1800221c0`
- `0x1800222c0`
- `0x1800228f0`
- `0x180041720`
- `0x180041b20`
- `0x180041d30`
- `0x180041f40`
- `0x180042190`
- `0x180042370`
- `0x180042550`
- `0x180042730`
- `0x180042980`
- `0x180042b60`
- `0x180042db0`
- `0x180042f90`

## callees

- `0x180012dcc`
- `0x18003336c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180012e64`
- `fwbase!FwReportReturnError` at `0x180012e79`
- `fwbase!FwReportReturnError` at `0x180012e64`
- `fwbase!FwReportReturnError` at `0x180012e79`
- `FWPolicyIOMgr!CreateDefaultRule` at `0x180012df5`
- `FWPolicyIOMgr!CreateDefaultRule` at `0x180012df5`

## string_xrefs

- `0x180012e5d`: `FwRule::CreateRule`
- `0x180012e72`: `FwRule::CreateRule`

## pseudocode

```c
__int64 __fastcall FwRule::CreateRule(FwRule *this)
{
  int DefaultRule; // eax
  unsigned int v3; // ebx

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  DefaultRule = CreateDefaultRule((char *)this + 80, 0x7FFFFFFF);
  v3 = DefaultRule;
  if ( DefaultRule < 0 )
  {
    FwReportReturnError("FwRule::CreateRule", (unsigned int)DefaultRule);
    return (unsigned int)FwReportReturnError("FwRule::CreateRule", v3);
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 10) + 288LL) = 3;
    *(_WORD *)(*((_QWORD *)this + 10) + 292LL) &= ~1u;
    *(_DWORD *)(*((_QWORD *)this + 10) + 44LL) = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180012dcc  mov     [rsp+arg_0], rbx
0x180012dd1  push    rdi
0x180012dd2  sub     rsp, 20h
0x180012dd6  mov     rdi, rcx
0x180012dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012de0  lea     rax, WPP_GLOBAL_Control
0x180012de7  cmp     rcx, rax
0x180012dea  jnz     short loc_180012E3E
0x180012dec  mov     edx, 7FFFFFFFh
0x180012df1  lea     rcx, [rdi+50h]
0x180012df5  call    cs:__imp_?CreateDefaultRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180012dfc  nop     dword ptr [rax+rax+00h]
0x180012e01  mov     ebx, eax
0x180012e03  test    eax, eax
0x180012e05  js      short loc_180012E5B
0x180012e07  mov     rax, [rdi+50h]
0x180012e0b  mov     ecx, 0FFFEh
0x180012e10  mov     dword ptr [rax+120h], 3
0x180012e1a  mov     rax, [rdi+50h]
0x180012e1e  and     [rax+124h], cx
0x180012e25  mov     rax, [rdi+50h]
0x180012e29  mov     dword ptr [rax+2Ch], 1
0x180012e30  mov     eax, ebx
0x180012e32  mov     rbx, [rsp+28h+arg_0]
0x180012e37  add     rsp, 20h
0x180012e3b  pop     rdi
0x180012e3c  retn
0x180012e3e  test    byte ptr [rcx+1Ch], 8
0x180012e42  jz      short loc_180012DEC
0x180012e44  mov     rcx, [rcx+10h]
0x180012e48  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180012e4f  mov     edx, 5Dh ; ']'
0x180012e54  call    WPP_SF_
0x180012e59  jmp     short loc_180012DEC
0x180012e5b  mov     edx, ebx
0x180012e5d  lea     rcx, aFwruleCreateru; "FwRule::CreateRule"
0x180012e64  call    cs:__imp_FwReportReturnError
0x180012e6b  nop     dword ptr [rax+rax+00h]
0x180012e70  mov     edx, ebx
0x180012e72  lea     rcx, aFwruleCreateru; "FwRule::CreateRule"
0x180012e79  call    cs:__imp_FwReportReturnError
0x180012e80  nop     dword ptr [rax+rax+00h]
0x180012e85  mov     ebx, eax
0x180012e87  jmp     short loc_180012E30
```
