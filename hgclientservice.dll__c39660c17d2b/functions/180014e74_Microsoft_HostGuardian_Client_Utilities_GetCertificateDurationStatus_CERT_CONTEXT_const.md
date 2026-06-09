# Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(_CERT_CONTEXT const *)

- ea: `0x180014e74`
- end: `0x180014ecf`
- name: `?GetCertificateDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@PEBU_CERT_CONTEXT@@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dab8`
- `0x18000efe0`
- `0x180016198`

## callees

- `0x180009cec`
- `0x180014e74`
- `0x180014ed8`

## string_xrefs

- `0x180014e8c`: `servercommon\base\securehostingservice\common\service\lib\utilities.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::Utilities::GetCertificateDurationStatus(__int64 a1)
{
  const char *v1; // rax
  __int64 v2; // rdx
  __int64 v4; // rcx
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a1 )
  {
    v1 = "context is nullptr";
    v2 = 59;
LABEL_3:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v2,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\utilities.cpp",
      (const char *)0x80070057LL,
      (int)v1,
      v5);
    return 3;
  }
  v4 = *(_QWORD *)(a1 + 24);
  if ( !v4 )
  {
    v1 = "context->pCertInfo is nullptr";
    v2 = 65;
    goto LABEL_3;
  }
  return Microsoft::HostGuardian::Client::Utilities::GetDurationStatus(*(_QWORD *)(v4 + 72));
}

```

## disassembly

```asm
0x180014e74  sub     rsp, 38h
0x180014e78  test    rcx, rcx
0x180014e7b  jnz     short loc_180014EAD
0x180014e7d  lea     rax, aContextIsNullp; "context is nullptr"
0x180014e84  lea     edx, [rcx+3Bh]; void *
0x180014e87  mov     rcx, [rsp+38h]; this
0x180014e8c  lea     r8, aServercommonBa_2; "servercommon\\base\\securehostingservic"...
0x180014e93  mov     r9d, 80070057h; char *
0x180014e99  mov     qword ptr [rsp+38h+var_18], rax; int
0x180014e9e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180014ea3  mov     eax, 3
0x180014ea8  add     rsp, 38h
0x180014eac  retn
0x180014ead  mov     rcx, [rcx+18h]
0x180014eb1  test    rcx, rcx
0x180014eb4  jnz     short loc_180014EC2
0x180014eb6  lea     rax, aContextPcertin; "context->pCertInfo is nullptr"
0x180014ebd  lea     edx, [rcx+41h]
0x180014ec0  jmp     short loc_180014E87
0x180014ec2  mov     rcx, [rcx+48h]
0x180014ec6  add     rsp, 38h
0x180014eca  jmp     ?GetDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@U_FILETIME@@@Z; Microsoft::HostGuardian::Client::Utilities::GetDurationStatus(_FILETIME)
```
