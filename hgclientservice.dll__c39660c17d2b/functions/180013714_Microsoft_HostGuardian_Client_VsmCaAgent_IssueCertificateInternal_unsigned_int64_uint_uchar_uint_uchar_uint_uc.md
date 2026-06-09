# Microsoft::HostGuardian::Client::VsmCaAgent::IssueCertificateInternal(unsigned __int64,uint,uchar *,uint,uchar *,uint,uchar *,uint *,uchar * *,uint *,uchar * *)

- ea: `0x180013714`
- end: `0x1800138ef`
- name: `?IssueCertificateInternal@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAX_KIPEAEI1I1PEAIPEAPEAE23@Z`
- size: `475`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *this, int, int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d348`

## callees

- `0x180008760`
- `0x180013714`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001385d`
- `RPCRT4!NdrClientCall3` at `0x18001385d`

## string_xrefs

- `0x1800138a2`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x1800138bd`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`
- `0x1800138dd`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::IssueCertificateInternal(
        Microsoft::HostGuardian::Client::VsmCaAgent *this,
        int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int *a9,
        unsigned __int8 **a10,
        unsigned int *a11,
        unsigned __int8 **a12)
{
  char v15; // cl
  char v16; // al
  int Pointer; // eax
  int v18; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a4 && a6 && a8 && a3 && a5 && a7 )
  {
    v15 = 0;
    v16 = 1;
  }
  else
  {
    v16 = 1;
    v15 = 1;
  }
  if ( v15 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x271,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)0x80070057LL,
      v18);
  if ( a10 && a9 && a12 && a11 )
    v16 = 0;
  if ( v16 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x272,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)0x80070057LL,
      v18);
  *a10 = 0;
  *a9 = 0;
  *a12 = 0;
  *a11 = 0;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180018A20, 0, 0, *((_QWORD *)this + 1)).Pointer;
  if ( Pointer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
      (const char *)(unsigned int)Pointer,
      a2);
}

```

## disassembly

```asm
0x180013714  mov     [rsp+arg_0], rsi
0x180013719  push    rdi
0x18001371a  sub     rsp, 90h
0x180013721  mov     rdi, r9
0x180013724  mov     r11d, r8d
0x180013727  mov     rsi, rdx
0x18001372a  mov     r9, rcx
0x18001372d  test    rdi, rdi
0x180013730  jz      short loc_180013767
0x180013732  cmp     [rsp+98h+arg_28], 0
0x18001373b  jz      short loc_180013767
0x18001373d  cmp     [rsp+98h+arg_38], 0
0x180013746  jz      short loc_180013767
0x180013748  test    r8d, r8d
0x18001374b  jz      short loc_180013767
0x18001374d  cmp     [rsp+98h+arg_20], 0
0x180013755  jz      short loc_180013767
0x180013757  cmp     [rsp+98h+arg_30], 0
0x18001375f  jz      short loc_180013767
0x180013761  xor     cl, cl
0x180013763  mov     al, 1
0x180013765  jmp     short loc_18001376B
0x180013767  mov     al, 1
0x180013769  mov     cl, al
0x18001376b  mov     r10, [rsp+98h]
0x180013773  test    cl, cl
0x180013775  jnz     loc_18001389C
0x18001377b  mov     rcx, [rsp+98h+arg_48]
0x180013783  test    rcx, rcx
0x180013786  jz      short loc_1800137AB
0x180013788  cmp     [rsp+98h+arg_40], 0
0x180013791  jz      short loc_1800137AB
0x180013793  cmp     [rsp+98h+arg_58], 0
0x18001379c  jz      short loc_1800137AB
0x18001379e  cmp     [rsp+98h+arg_50], 0
0x1800137a7  jz      short loc_1800137AB
0x1800137a9  xor     al, al
0x1800137ab  mov     r10, [rsp+98h]
0x1800137b3  test    al, al
0x1800137b5  jnz     loc_1800138B7
0x1800137bb  mov     qword ptr [rcx], 0
0x1800137c2  mov     rax, [rsp+98h+arg_40]
0x1800137ca  mov     dword ptr [rax], 0
0x1800137d0  mov     rdx, [rsp+98h+arg_58]
0x1800137d8  mov     qword ptr [rdx], 0
0x1800137df  mov     r8, [rsp+98h+arg_50]
0x1800137e7  mov     dword ptr [r8], 0
0x1800137ee  mov     r9, [r9+8]
0x1800137f2  mov     [rsp+98h+arg_18], 0
0x1800137fe  mov     [rsp+98h+var_28], rdx
0x180013803  mov     [rsp+98h+var_30], r8
0x180013808  mov     [rsp+98h+var_38], rcx
0x18001380d  mov     [rsp+98h+var_40], rax
0x180013812  mov     rax, [rsp+98h+arg_38]
0x18001381a  mov     [rsp+98h+var_48], rax
0x18001381f  mov     eax, [rsp+98h+arg_30]
0x180013826  mov     [rsp+98h+var_50], eax
0x18001382a  mov     rax, [rsp+98h+arg_28]
0x180013832  mov     [rsp+98h+var_58], rax
0x180013837  mov     eax, [rsp+98h+arg_20]
0x18001383e  mov     [rsp+98h+var_60], eax
0x180013842  mov     [rsp+98h+var_68], rdi
0x180013847  mov     [rsp+98h+var_70], r11d
0x18001384c  mov     [rsp+98h+var_78], rsi
0x180013851  xor     r8d, r8d; pReturnValue
0x180013854  xor     edx, edx; nProcNum
0x180013856  lea     rcx, stru_180018A20; pProxyInfo
0x18001385d  call    cs:__imp_NdrClientCall3
0x180013863  mov     [rsp+98h+arg_18], rax
0x18001386b  mov     [rsp+98h+var_18], eax
0x180013872  jmp     short loc_180013887
0x180013874  test    eax, eax
0x180013876  jle     short loc_180013880
0x180013878  movzx   eax, ax
0x18001387b  or      eax, 80070000h
0x180013880  mov     [rsp+98h+var_18], eax
0x180013887  test    eax, eax
0x180013889  js      short loc_1800138D2
0x18001388b  mov     rsi, [rsp+98h+arg_0]
0x180013893  add     rsp, 90h
0x18001389a  pop     rdi
0x18001389b  retn
0x18001389c  mov     r9d, 80070057h; char *
0x1800138a2  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x1800138a9  mov     edx, 271h; void *
0x1800138ae  mov     rcx, r10; this
0x1800138b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800138b7  mov     r9d, 80070057h; char *
0x1800138bd  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x1800138c4  mov     edx, 272h; void *
0x1800138c9  mov     rcx, r10; this
0x1800138cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800138d2  mov     rcx, [rsp+98h]; this
0x1800138da  mov     r9d, eax; char *
0x1800138dd  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x1800138e4  mov     edx, 288h; void *
0x1800138e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
