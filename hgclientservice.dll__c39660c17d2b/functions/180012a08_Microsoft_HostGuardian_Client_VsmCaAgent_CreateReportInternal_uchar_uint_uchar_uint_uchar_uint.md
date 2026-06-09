# Microsoft::HostGuardian::Client::VsmCaAgent::CreateReportInternal(uchar * *,uint *,uchar * *,uint *,uchar * *,uint *)

- ea: `0x180012a08`
- end: `0x180012b3b`
- name: `?CreateReportInternal@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEAPEAEPEAI0101@Z`
- size: `307`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *__hidden this, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dc5c`

## callees

- `0x180008760`
- `0x180012a08`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180012adb`
- `RPCRT4!NdrClientCall3` at `0x180012adb`

## string_xrefs

- `0x180012b0f`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x180012b29`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::CreateReportInternal(
        Microsoft::HostGuardian::Client::VsmCaAgent *this,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  int Pointer; // eax
  int v9; // [rsp+20h] [rbp-58h]
  __int64 v10; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)0x80070057LL,
      v9);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  v10 = *((_QWORD *)this + 2);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, *(_QWORD *)this).Pointer;
  if ( Pointer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x242,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)(unsigned int)Pointer,
      v10);
}

```

## disassembly

```asm
0x180012a08  push    rdi
0x180012a0a  sub     rsp, 70h
0x180012a0e  mov     r10, r9
0x180012a11  mov     r9, rcx
0x180012a14  test    rdx, rdx
0x180012a17  jz      short loc_180012A48
0x180012a19  test    r8, r8
0x180012a1c  jz      short loc_180012A48
0x180012a1e  test    r10, r10
0x180012a21  jz      short loc_180012A48
0x180012a23  cmp     [rsp+78h+arg_20], 0
0x180012a2c  jz      short loc_180012A48
0x180012a2e  cmp     [rsp+78h+arg_28], 0
0x180012a37  jz      short loc_180012A48
0x180012a39  cmp     [rsp+78h+arg_30], 0
0x180012a42  jz      short loc_180012A48
0x180012a44  xor     al, al
0x180012a46  jmp     short loc_180012A4A
0x180012a48  mov     al, 1
0x180012a4a  mov     rcx, [rsp+78h]; this
0x180012a4f  test    al, al
0x180012a51  jnz     loc_180012B09
0x180012a57  mov     qword ptr [rdx], 0
0x180012a5e  mov     dword ptr [r8], 0
0x180012a65  mov     qword ptr [r10], 0
0x180012a6c  mov     rcx, [rsp+78h+arg_20]
0x180012a74  mov     dword ptr [rcx], 0
0x180012a7a  mov     r11, [rsp+78h+arg_28]
0x180012a82  mov     qword ptr [r11], 0
0x180012a89  mov     rdi, [rsp+78h+arg_30]
0x180012a91  mov     dword ptr [rdi], 0
0x180012a97  mov     rax, [r9+10h]
0x180012a9b  mov     r9, [r9]
0x180012a9e  mov     [rsp+78h+arg_8], 0
0x180012aaa  mov     [rsp+78h+var_28], r11
0x180012aaf  mov     [rsp+78h+var_30], rdi
0x180012ab4  mov     [rsp+78h+var_38], r10
0x180012ab9  mov     [rsp+78h+var_40], rcx
0x180012abe  mov     [rsp+78h+var_48], rdx
0x180012ac3  mov     [rsp+78h+var_50], r8
0x180012ac8  mov     [rsp+78h+var_58], rax
0x180012acd  xor     r8d, r8d; pReturnValue
0x180012ad0  lea     edx, [r8+2]; nProcNum
0x180012ad4  lea     rcx, pProxyInfo; pProxyInfo
0x180012adb  call    cs:__imp_NdrClientCall3
0x180012ae1  mov     [rsp+78h+arg_8], rax
0x180012ae9  mov     [rsp+78h+var_18], eax
0x180012aed  jmp     short loc_180012AFF
0x180012aef  test    eax, eax
0x180012af1  jle     short loc_180012AFB
0x180012af3  movzx   eax, ax
0x180012af6  or      eax, 80070000h
0x180012afb  mov     [rsp+78h+var_18], eax
0x180012aff  test    eax, eax
0x180012b01  js      short loc_180012B21
0x180012b03  add     rsp, 70h
0x180012b07  pop     rdi
0x180012b08  retn
0x180012b09  mov     r9d, 80070057h; char *
0x180012b0f  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012b16  mov     edx, 22Eh; void *
0x180012b1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012b21  mov     rcx, [rsp+78h]; this
0x180012b26  mov     r9d, eax; char *
0x180012b29  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x180012b30  mov     edx, 242h; void *
0x180012b35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
