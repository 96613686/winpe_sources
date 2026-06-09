# FwOpenPort::get_Protocol(NET_FW_IP_PROTOCOL_ *)

- ea: `0x18003c310`
- end: `0x18003c3c7`
- name: `?get_Protocol@FwOpenPort@@UEAAJPEAW4NET_FW_IP_PROTOCOL_@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_IP_PROTOCOL_ *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003c310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c326`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c394`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c394`
- `fwbase!FwReportReturnError` at `0x18003c345`
- `fwbase!FwReportReturnError` at `0x18003c3ad`
- `fwbase!FwReportReturnError` at `0x18003c345`
- `fwbase!FwReportReturnError` at `0x18003c3ad`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x18003c383`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x18003c383`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c363`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c363`

## string_xrefs

- `0x18003c33e`: `FwOpenPort::get_Protocol`
- `0x18003c3a6`: `FwOpenPort::get_Protocol`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_Protocol(FwOpenPort *this, enum NET_FW_IP_PROTOCOL_ *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v5; // ebx
  __int64 v6; // rdx
  char *v7; // rdi
  int DefaultOpenPortRule; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v5 = -2147467261;
    v6 = 2147500035LL;
LABEL_3:
    FwReportReturnError("FwOpenPort::get_Protocol", v6);
    goto LABEL_8;
  }
  v7 = (char *)this + 72;
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v5 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
    {
      v6 = (unsigned int)DefaultOpenPortRule;
      goto LABEL_3;
    }
  }
  v5 = FwWfProtocolToICFProtocol(*(unsigned __int16 *)(*(_QWORD *)v7 + 48LL), a2);
LABEL_8:
  LeaveCriticalSection(v2);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_Protocol", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003c310  push    rbx
0x18003c312  push    rbp
0x18003c313  push    rsi
0x18003c314  push    rdi
0x18003c315  sub     rsp, 28h
0x18003c319  lea     rsi, [rcx+10h]
0x18003c31d  mov     rbx, rcx
0x18003c320  mov     rcx, rsi; lpCriticalSection
0x18003c323  mov     rbp, rdx
0x18003c326  call    cs:__imp_EnterCriticalSection
0x18003c32d  nop     dword ptr [rax+rax+00h]
0x18003c332  test    rbp, rbp
0x18003c335  jnz     short loc_18003C353
0x18003c337  mov     ebx, 80004003h
0x18003c33c  mov     edx, ebx
0x18003c33e  lea     rcx, aFwopenportGetP; "FwOpenPort::get_Protocol"
0x18003c345  call    cs:__imp_FwReportReturnError
0x18003c34c  nop     dword ptr [rax+rax+00h]
0x18003c351  jmp     short loc_18003C391
0x18003c353  lea     rdi, [rbx+48h]
0x18003c357  cmp     qword ptr [rdi], 0
0x18003c35b  jnz     short loc_18003C379
0x18003c35d  mov     edx, [rbx+40h]
0x18003c360  mov     rcx, rdi
0x18003c363  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c36a  nop     dword ptr [rax+rax+00h]
0x18003c36f  mov     ebx, eax
0x18003c371  test    eax, eax
0x18003c373  jns     short loc_18003C379
0x18003c375  mov     edx, eax
0x18003c377  jmp     short loc_18003C33E
0x18003c379  mov     rcx, [rdi]
0x18003c37c  mov     rdx, rbp
0x18003c37f  movzx   ecx, word ptr [rcx+30h]
0x18003c383  call    cs:__imp_FwWfProtocolToICFProtocol
0x18003c38a  nop     dword ptr [rax+rax+00h]
0x18003c38f  mov     ebx, eax
0x18003c391  mov     rcx, rsi; lpCriticalSection
0x18003c394  call    cs:__imp_LeaveCriticalSection
0x18003c39b  nop     dword ptr [rax+rax+00h]
0x18003c3a0  test    ebx, ebx
0x18003c3a2  jns     short loc_18003C3BB
0x18003c3a4  mov     edx, ebx
0x18003c3a6  lea     rcx, aFwopenportGetP; "FwOpenPort::get_Protocol"
0x18003c3ad  call    cs:__imp_FwReportReturnError
0x18003c3b4  nop     dword ptr [rax+rax+00h]
0x18003c3b9  mov     ebx, eax
0x18003c3bb  mov     eax, ebx
0x18003c3bd  add     rsp, 28h
0x18003c3c1  pop     rdi
0x18003c3c2  pop     rsi
0x18003c3c3  pop     rbp
0x18003c3c4  pop     rbx
0x18003c3c5  retn
```
