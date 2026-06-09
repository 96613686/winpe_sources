# Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector(HgBlob,uint,HgBlob,int,HgBlob *,HgBlob *)

- ea: `0x180014114`
- end: `0x18001419e`
- name: `?EncryptWithKeyProtector@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJUHgBlob@@I0HPEAU5@1@Z`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d190`

## callees

- `0x1800064b4`
- `0x180014114`
- `0x180017010`

## string_xrefs

- `0x18001412f`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::EncryptWithKeyProtector(
        __int64 a1,
        __int128 *a2,
        __int64 a3)
{
  __int64 (__fastcall *v3)(__int64, __int128 *, __int64); // rax
  __int64 result; // rax
  __int64 v5; // rcx
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-48h]
  __int128 v8; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(a1 + 80);
  if ( v3 )
  {
    v8 = *a2;
    v5 = *(_QWORD *)(a1 + 16);
    try
    {
      result = v3(v5, &v8, a3);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x9F,
                             (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                             v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL,
      v7);
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014114  sub     rsp, 68h
0x180014118  mov     r10, rcx
0x18001411b  mov     rax, [rcx+50h]
0x18001411f  test    rax, rax
0x180014122  jnz     short loc_180014147
0x180014124  mov     rcx, [rsp+68h]; this
0x180014129  mov     r9d, 80004001h; char *
0x18001412f  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180014136  mov     edx, 96h; void *
0x18001413b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014140  mov     eax, 80004001h
0x180014145  jmp     short loc_180014198
0x180014147  movaps  xmm0, xmmword ptr [r9]
0x18001414b  movdqa  [rsp+68h+var_28], xmm0
0x180014151  movaps  xmm1, xmmword ptr [rdx]
0x180014154  movdqa  [rsp+68h+var_18], xmm1
0x18001415a  mov     rcx, [rsp+68h+arg_30]
0x180014162  mov     [rsp+68h+var_38], rcx
0x180014167  mov     rcx, [rsp+68h+arg_28]
0x18001416f  mov     [rsp+68h+var_40], rcx
0x180014174  mov     ecx, [rsp+68h+arg_20]
0x18001417b  mov     [rsp+68h+var_48], ecx
0x18001417f  lea     r9, [rsp+68h+var_28]
0x180014184  lea     rdx, [rsp+68h+var_18]
0x180014189  mov     rcx, [r10+10h]
0x18001418d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014192  jmp     short loc_180014198
0x180014194  mov     eax, [rsp+68h+arg_0]
0x180014198  add     rsp, 68h
0x18001419c  retn
```
