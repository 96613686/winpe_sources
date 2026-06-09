# Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults(wchar_t * const,uint,AttestationResultType *,ShsAttestationFlag *,wchar_t * *,uint *,AttestationResult * *)

- ea: `0x180014298`
- end: `0x180014312`
- name: `?QueryAttestationResults@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJQEA_WIPEAW4AttestationResultType@@PEAW4ShsAttestationFlag@@PEAPEA_WPEAIPEAPEAUAttestationResult@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgServicePlugin *this, wchar_t *const, __int64, enum AttestationResultType *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ca70`
- `0x18000dc5c`

## callees

- `0x1800064b4`
- `0x180014298`
- `0x180017010`

## string_xrefs

- `0x1800142b3`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::QueryAttestationResults(
        Microsoft::HostGuardian::Client::HgServicePlugin *this,
        wchar_t *const a2,
        __int64 a3,
        enum AttestationResultType *a4)
{
  __int64 (__fastcall *v4)(__int64, wchar_t *const, __int64, enum AttestationResultType *); // rax
  __int64 result; // rax
  __int64 v6; // rcx
  const char *v7; // r9
  int v8; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (__int64 (__fastcall *)(__int64, wchar_t *const, __int64, enum AttestationResultType *))*((_QWORD *)this + 6);
  if ( v4 )
  {
    v6 = *((_QWORD *)this + 2);
    try
    {
      result = v4(v6, a2, a3, a4);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x51,
                             (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                             v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL,
      v8);
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014298  sub     rsp, 58h
0x18001429c  mov     r10, rcx
0x18001429f  mov     rax, [rcx+30h]
0x1800142a3  test    rax, rax
0x1800142a6  jnz     short loc_1800142C9
0x1800142a8  mov     rcx, [rsp+58h]; this
0x1800142ad  mov     r9d, 80004001h; char *
0x1800142b3  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x1800142ba  lea     edx, [rax+47h]; void *
0x1800142bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142c2  mov     eax, 80004001h
0x1800142c7  jmp     short loc_18001430C
0x1800142c9  mov     rcx, [rsp+58h+arg_38]
0x1800142d1  mov     [rsp+58h+var_20], rcx
0x1800142d6  mov     rcx, [rsp+58h+arg_30]
0x1800142de  mov     [rsp+58h+var_28], rcx
0x1800142e3  mov     rcx, [rsp+58h+arg_28]
0x1800142eb  mov     [rsp+58h+var_30], rcx
0x1800142f0  mov     rcx, [rsp+58h+arg_20]
0x1800142f8  mov     [rsp+58h+var_38], rcx
0x1800142fd  mov     rcx, [r10+10h]
0x180014301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014306  jmp     short loc_18001430C
0x180014308  mov     eax, [rsp+58h+arg_0]
0x18001430c  add     rsp, 58h
0x180014310  retn
```
