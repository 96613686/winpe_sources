# Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(HgBlob &)

- ea: `0x1800141f0`
- end: `0x180014243`
- name: `?FreeBlobData@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJAEAUHgBlob@@@Z`
- size: `83`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::HgServicePlugin *__hidden this, struct HgBlob *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bfc0`
- `0x18000c0a8`
- `0x18000c0f4`
- `0x18000d0b8`
- `0x18000d190`

## callees

- `0x1800064b4`
- `0x1800141f0`
- `0x180017010`

## string_xrefs

- `0x180014208`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::FreeBlobData(
        Microsoft::HostGuardian::Client::HgServicePlugin *this,
        struct HgBlob *a2)
{
  __int64 (__fastcall *v2)(__int64, __int128 *); // rax
  __int64 result; // rax
  __int64 v4; // rcx
  const char *v5; // r9
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (__int64 (__fastcall *)(__int64, __int128 *))*((_QWORD *)this + 12);
  if ( v2 )
  {
    v6 = *(_OWORD *)a2;
    v4 = *((_QWORD *)this + 2);
    try
    {
      result = v2(v4, &v6);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xB5,
                             (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                             v5);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL,
      v6);
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800141f0  sub     rsp, 38h
0x1800141f4  mov     rax, [rcx+60h]
0x1800141f8  test    rax, rax
0x1800141fb  jnz     short loc_180014220
0x1800141fd  mov     rcx, [rsp+38h]; this
0x180014202  mov     r9d, 80004001h; char *
0x180014208  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x18001420f  mov     edx, 0B2h; void *
0x180014214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014219  mov     eax, 80004001h
0x18001421e  jmp     short loc_18001423D
0x180014220  movups  xmm0, xmmword ptr [rdx]
0x180014223  movdqu  [rsp+38h+var_18], xmm0
0x180014229  lea     rdx, [rsp+38h+var_18]
0x18001422e  mov     rcx, [rcx+10h]
0x180014232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014237  jmp     short loc_18001423D
0x180014239  mov     eax, [rsp+38h+arg_0]
0x18001423d  add     rsp, 38h
0x180014241  retn
```
