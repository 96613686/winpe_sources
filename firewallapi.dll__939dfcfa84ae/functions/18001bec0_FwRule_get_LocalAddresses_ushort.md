# FwRule::get_LocalAddresses(ushort * *)

- ea: `0x18001bec0`
- end: `0x18001bfa6`
- name: `?get_LocalAddresses@FwRule@@UEAAJPEAPEAG@Z`
- size: `230`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180012dcc`
- `0x18001bec0`
- `0x18003336c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001beec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001beec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bf2c`
- `fwbase!FwReportReturnError` at `0x18001bf7f`
- `fwbase!FwReportReturnError` at `0x18001bf96`
- `fwbase!FwReportReturnError` at `0x18001bf7f`
- `fwbase!FwReportReturnError` at `0x18001bf96`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001bf16`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001bf16`

## pseudocode

```c
__int64 __fastcall FwRule::get_LocalAddresses(FwRule *this, unsigned __int16 **a2)
{
  int OpenPortorAuthAppAsBSTR; // eax
  int v5; // ebx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_QWORD *)this + 10)
      || (OpenPortorAuthAppAsBSTR = FwRule::CreateRule(this), v5 = OpenPortorAuthAppAsBSTR, OpenPortorAuthAppAsBSTR >= 0) )
    {
      OpenPortorAuthAppAsBSTR = GetOpenPortorAuthAppAsBSTR(*((_QWORD *)this + 10) + 104LL, a2);
      v5 = OpenPortorAuthAppAsBSTR;
      if ( OpenPortorAuthAppAsBSTR >= 0 )
        goto LABEL_7;
    }
    v7 = (unsigned int)OpenPortorAuthAppAsBSTR;
  }
  else
  {
    v5 = -2147467261;
    v7 = 2147500035LL;
  }
  FwReportReturnError("FwRule::get_LocalAddresses", v7);
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwRule::get_LocalAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001bec0  push    rbx
0x18001bec2  push    rbp
0x18001bec3  push    rsi
0x18001bec4  push    rdi
0x18001bec5  sub     rsp, 28h
0x18001bec9  mov     rsi, rdx
0x18001becc  mov     rdi, rcx
0x18001becf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bed6  lea     rax, WPP_GLOBAL_Control
0x18001bedd  cmp     rcx, rax
0x18001bee0  jz      short loc_18001BEE8
0x18001bee2  test    byte ptr [rcx+1Ch], 8
0x18001bee6  jnz     short loc_18001BF48
0x18001bee8  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001beec  call    cs:__imp_EnterCriticalSection
0x18001bef3  nop     dword ptr [rax+rax+00h]
0x18001bef8  test    rsi, rsi
0x18001befb  jz      short loc_18001BF5F
0x18001befd  mov     qword ptr [rsi], 0
0x18001bf04  cmp     qword ptr [rdi+50h], 0
0x18001bf09  jz      short loc_18001BF68
0x18001bf0b  mov     rcx, [rdi+50h]
0x18001bf0f  mov     rdx, rsi
0x18001bf12  add     rcx, 68h ; 'h'
0x18001bf16  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18001bf1d  nop     dword ptr [rax+rax+00h]
0x18001bf22  mov     ebx, eax
0x18001bf24  test    eax, eax
0x18001bf26  js      short loc_18001BF76
0x18001bf28  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001bf2c  call    cs:__imp_LeaveCriticalSection
0x18001bf33  nop     dword ptr [rax+rax+00h]
0x18001bf38  test    ebx, ebx
0x18001bf3a  js      short loc_18001BF8D
0x18001bf3c  mov     eax, ebx
0x18001bf3e  add     rsp, 28h
0x18001bf42  pop     rdi
0x18001bf43  pop     rsi
0x18001bf44  pop     rbp
0x18001bf45  pop     rbx
0x18001bf46  retn
0x18001bf48  mov     rcx, [rcx+10h]
0x18001bf4c  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18001bf53  mov     edx, 1Fh
0x18001bf58  call    WPP_SF_
0x18001bf5d  jmp     short loc_18001BEE8
0x18001bf5f  mov     ebx, 80004003h
0x18001bf64  mov     edx, ebx
0x18001bf66  jmp     short loc_18001BF78
0x18001bf68  mov     rcx, rdi; this
0x18001bf6b  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x18001bf70  mov     ebx, eax
0x18001bf72  test    eax, eax
0x18001bf74  jns     short loc_18001BF0B
0x18001bf76  mov     edx, eax
0x18001bf78  lea     rcx, aFwruleGetLocal; "FwRule::get_LocalAddresses"
0x18001bf7f  call    cs:__imp_FwReportReturnError
0x18001bf86  nop     dword ptr [rax+rax+00h]
0x18001bf8b  jmp     short loc_18001BF28
0x18001bf8d  mov     edx, ebx
0x18001bf8f  lea     rcx, aFwruleGetLocal; "FwRule::get_LocalAddresses"
0x18001bf96  call    cs:__imp_FwReportReturnError
0x18001bf9d  nop     dword ptr [rax+rax+00h]
0x18001bfa2  mov     ebx, eax
0x18001bfa4  jmp     short loc_18001BF3C
```
