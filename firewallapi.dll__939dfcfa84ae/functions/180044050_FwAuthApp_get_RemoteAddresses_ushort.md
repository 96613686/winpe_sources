# FwAuthApp::get_RemoteAddresses(ushort * *)

- ea: `0x180044050`
- end: `0x180044107`
- name: `?get_RemoteAddresses@FwAuthApp@@UEAAJPEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180001e3c`
- `0x180044050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044063`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800440d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800440d4`
- `fwbase!FwReportReturnError` at `0x1800440c4`
- `fwbase!FwReportReturnError` at `0x1800440ed`
- `fwbase!FwReportReturnError` at `0x1800440c4`
- `fwbase!FwReportReturnError` at `0x1800440ed`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x1800440a9`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x1800440a9`

## pseudocode

```c
__int64 __fastcall FwAuthApp::get_RemoteAddresses(FwAuthApp *this, unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int DefaultAuthAppRules; // eax
  __int64 v7; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_8:
    FwReportReturnError("FwAuthApp::get_RemoteAddresses", v5);
    goto LABEL_9;
  }
  *a2 = 0;
  DefaultAuthAppRules = FwAuthApp::CreateDefaultAuthAppRules(this);
  v4 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
    goto LABEL_7;
  v7 = *((_QWORD *)this + 9);
  if ( !v7 )
    v7 = *((_QWORD *)this + 10);
  DefaultAuthAppRules = GetOpenPortorAuthAppAsBSTR(v7 + 176, a2);
  v4 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
  {
LABEL_7:
    v5 = (unsigned int)DefaultAuthAppRules;
    goto LABEL_8;
  }
LABEL_9:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::get_RemoteAddresses", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180044050  push    rbx
0x180044052  push    rbp
0x180044053  push    rsi
0x180044054  push    rdi
0x180044055  sub     rsp, 28h
0x180044059  mov     rdi, rcx
0x18004405c  mov     rsi, rdx
0x18004405f  add     rcx, 10h; lpCriticalSection
0x180044063  call    cs:__imp_EnterCriticalSection
0x18004406a  nop     dword ptr [rax+rax+00h]
0x18004406f  test    rsi, rsi
0x180044072  jnz     short loc_18004407D
0x180044074  mov     ebx, 80004003h
0x180044079  mov     edx, ebx
0x18004407b  jmp     short loc_1800440BD
0x18004407d  mov     rcx, rdi; this
0x180044080  mov     qword ptr [rsi], 0
0x180044087  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x18004408c  mov     ebx, eax
0x18004408e  test    eax, eax
0x180044090  js      short loc_1800440BB
0x180044092  mov     rcx, [rdi+48h]
0x180044096  test    rcx, rcx
0x180044099  jnz     short loc_18004409F
0x18004409b  mov     rcx, [rdi+50h]
0x18004409f  add     rcx, 0B0h
0x1800440a6  mov     rdx, rsi
0x1800440a9  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x1800440b0  nop     dword ptr [rax+rax+00h]
0x1800440b5  mov     ebx, eax
0x1800440b7  test    eax, eax
0x1800440b9  jns     short loc_1800440D0
0x1800440bb  mov     edx, eax
0x1800440bd  lea     rcx, aFwauthappGetRe; "FwAuthApp::get_RemoteAddresses"
0x1800440c4  call    cs:__imp_FwReportReturnError
0x1800440cb  nop     dword ptr [rax+rax+00h]
0x1800440d0  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800440d4  call    cs:__imp_LeaveCriticalSection
0x1800440db  nop     dword ptr [rax+rax+00h]
0x1800440e0  test    ebx, ebx
0x1800440e2  jns     short loc_1800440FB
0x1800440e4  mov     edx, ebx
0x1800440e6  lea     rcx, aFwauthappGetRe; "FwAuthApp::get_RemoteAddresses"
0x1800440ed  call    cs:__imp_FwReportReturnError
0x1800440f4  nop     dword ptr [rax+rax+00h]
0x1800440f9  mov     ebx, eax
0x1800440fb  mov     eax, ebx
0x1800440fd  add     rsp, 28h
0x180044101  pop     rdi
0x180044102  pop     rsi
0x180044103  pop     rbp
0x180044104  pop     rbx
0x180044105  retn
```
