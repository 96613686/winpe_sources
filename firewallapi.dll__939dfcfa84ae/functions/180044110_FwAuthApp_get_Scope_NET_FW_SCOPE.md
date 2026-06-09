# FwAuthApp::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x180044110`
- end: `0x1800441be`
- name: `?get_Scope@FwAuthApp@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180001e3c`
- `0x180044110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044124`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004418a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004418a`
- `fwbase!FwReportReturnError` at `0x180044143`
- `fwbase!FwReportReturnError` at `0x1800441a3`
- `fwbase!FwReportReturnError` at `0x180044143`
- `fwbase!FwReportReturnError` at `0x1800441a3`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180044177`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180044177`

## pseudocode

```c
__int64 __fastcall FwAuthApp::get_Scope(FwAuthApp *this, enum NET_FW_SCOPE_ *a2)
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
LABEL_3:
    FwReportReturnError("FwAuthApp::get_Scope", v5);
    goto LABEL_9;
  }
  DefaultAuthAppRules = FwAuthApp::CreateDefaultAuthAppRules(this);
  v4 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
  {
    v5 = (unsigned int)DefaultAuthAppRules;
    goto LABEL_3;
  }
  v7 = *((_QWORD *)this + 9);
  if ( !v7 )
    v7 = *((_QWORD *)this + 10);
  *a2 = GetOpenPortOrAuthAppAddrScope(v7 + 176);
LABEL_9:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::get_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180044110  push    rbx
0x180044112  push    rsi
0x180044113  push    rdi
0x180044114  push    r14
0x180044116  sub     rsp, 28h
0x18004411a  mov     rdi, rcx
0x18004411d  mov     r14, rdx
0x180044120  add     rcx, 10h; lpCriticalSection
0x180044124  call    cs:__imp_EnterCriticalSection
0x18004412b  nop     dword ptr [rax+rax+00h]
0x180044130  test    r14, r14
0x180044133  jnz     short loc_180044151
0x180044135  mov     ebx, 80004003h
0x18004413a  mov     edx, ebx
0x18004413c  lea     rcx, aFwauthappGetSc; "FwAuthApp::get_Scope"
0x180044143  call    cs:__imp_FwReportReturnError
0x18004414a  nop     dword ptr [rax+rax+00h]
0x18004414f  jmp     short loc_180044186
0x180044151  mov     rcx, rdi; this
0x180044154  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x180044159  mov     ebx, eax
0x18004415b  test    eax, eax
0x18004415d  jns     short loc_180044163
0x18004415f  mov     edx, eax
0x180044161  jmp     short loc_18004413C
0x180044163  mov     rcx, [rdi+48h]
0x180044167  test    rcx, rcx
0x18004416a  jnz     short loc_180044170
0x18004416c  mov     rcx, [rdi+50h]
0x180044170  add     rcx, 0B0h
0x180044177  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x18004417e  nop     dword ptr [rax+rax+00h]
0x180044183  mov     [r14], eax
0x180044186  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004418a  call    cs:__imp_LeaveCriticalSection
0x180044191  nop     dword ptr [rax+rax+00h]
0x180044196  test    ebx, ebx
0x180044198  jns     short loc_1800441B1
0x18004419a  mov     edx, ebx
0x18004419c  lea     rcx, aFwauthappGetSc; "FwAuthApp::get_Scope"
0x1800441a3  call    cs:__imp_FwReportReturnError
0x1800441aa  nop     dword ptr [rax+rax+00h]
0x1800441af  mov     ebx, eax
0x1800441b1  mov     eax, ebx
0x1800441b3  add     rsp, 28h
0x1800441b7  pop     r14
0x1800441b9  pop     rdi
0x1800441ba  pop     rsi
0x1800441bb  pop     rbx
0x1800441bc  retn
```
