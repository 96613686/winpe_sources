# Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetMessageIdFromCimError(_MI_Instance const *,unsigned __int64,wchar_t *,uint &)

- ea: `0x180009e50`
- end: `0x180009f3b`
- name: `?GetMessageIdFromCimError@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@_KPEA_WAEAI@Z`
- size: `235`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::CimUtilities *this, const struct _MI_Instance *, __int64, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a070`

## callees

- `0x180001520`
- `0x18000200c`
- `0x180009cfc`
- `0x18000a6b4`

## string_xrefs

- `0x180009ee3`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetMessageIdFromCimError(
        Microsoft::HostGuardian::Client::Plugin::CimUtilities *this,
        const struct _MI_Instance *a2,
        __int64 a3,
        wchar_t *a4)
{
  int v6; // [rsp+20h] [rbp-78h]
  wchar_t **v7; // [rsp+40h] [rbp-58h] BYREF
  int v8; // [rsp+48h] [rbp-50h]
  int v9; // [rsp+50h] [rbp-48h]
  const wchar_t *v10; // [rsp+58h] [rbp-40h]
  wchar_t *Buffer[2]; // [rsp+60h] [rbp-38h] BYREF
  __int128 v12; // [rsp+70h] [rbp-28h]
  __int64 v13; // [rsp+80h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_OWORD *)Buffer = 0;
  v12 = 0;
  v13 = 0;
  v7 = Buffer;
  v8 = 0;
  v9 = 13;
  v10 = L"MessageID";
  Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties((__int64)this, (__int64)&v7, 1u);
  LOBYTE(v6) = swscanf_s(Buffer[0], L"%s %x", a3, 20, a4) == 2;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xF0,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
    (const char *)0x8000FFFFLL,
    v6,
    (bool)"Unexpected MessageID string '%ws'.",
    (const char *)Buffer[0]);
}

```

## disassembly

```asm
0x180009e50  mov     r11, rsp
0x180009e53  mov     [r11+10h], rbx
0x180009e57  push    rdi
0x180009e58  sub     rsp, 90h
0x180009e5f  mov     rax, cs:__security_cookie
0x180009e66  xor     rax, rsp
0x180009e69  mov     [rsp+98h+var_10], rax
0x180009e71  xor     eax, eax
0x180009e73  lea     rdx, [r11-58h]
0x180009e77  xorps   xmm0, xmm0
0x180009e7a  mov     rdi, r8
0x180009e7d  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x180009e82  mov     r8d, 1
0x180009e88  mov     rbx, r9
0x180009e8b  movups  [rsp+98h+var_28], xmm0
0x180009e90  mov     [r11-18h], rax
0x180009e94  lea     rax, [r11-38h]
0x180009e98  mov     [r11-58h], rax
0x180009e9c  lea     rax, aMessageid; "MessageID"
0x180009ea3  mov     [rsp+98h+var_50], 0
0x180009eab  mov     [rsp+98h+var_48], 0Dh
0x180009eb3  mov     [r11-40h], rax
0x180009eb7  call    ?GetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(_MI_Instance const *,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)
0x180009ebc  mov     rcx, [rsp+98h+Buffer]; Buffer
0x180009ec1  lea     rdx, aSX; "%s %x"
0x180009ec8  mov     r9d, 14h
0x180009ece  mov     qword ptr [rsp+98h+var_78], rbx
0x180009ed3  mov     r8, rdi
0x180009ed6  call    swscanf_s
0x180009edb  mov     rcx, [rsp+98h]; this
0x180009ee3  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180009eea  cmp     eax, 2
0x180009eed  mov     r9d, 8000FFFFh; char *
0x180009ef3  mov     rax, [rsp+98h+Buffer]
0x180009ef8  mov     [rsp+98h+var_68], rax; char *
0x180009efd  setz    dl
0x180009f00  lea     rax, aUnexpectedMess; "Unexpected MessageID string '%ws'."
0x180009f07  mov     qword ptr [rsp+98h+var_70], rax; bool
0x180009f0c  mov     byte ptr [rsp+98h+var_78], dl; int
0x180009f10  mov     edx, 0F0h; void *
0x180009f15  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180009f1a  mov     rcx, [rsp+98h+var_10]
0x180009f22  xor     rcx, rsp; StackCookie
0x180009f25  call    __security_check_cookie
0x180009f2a  mov     rbx, [rsp+98h+arg_8]
0x180009f32  add     rsp, 90h
0x180009f39  pop     rdi
0x180009f3a  retn
```
