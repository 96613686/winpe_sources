# Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector(HgBlob,HgBlob *,HgBlob *,HgBlob *,HgBlob *)

- ea: `0x180014318`
- end: `0x180014388`
- name: `?UnwrapKeyProtector@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJUHgBlob@@PEAU5@111@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int128 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e100`

## callees

- `0x1800064b4`
- `0x180014318`
- `0x180017010`

## string_xrefs

- `0x180014333`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::UnwrapKeyProtector(__int64 a1, __int128 *a2)
{
  __int64 (__fastcall *v2)(__int64, __int128 *); // rax
  __int64 result; // rax
  __int64 v4; // rcx
  const char *v5; // r9
  __int128 v6; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = *(__int64 (__fastcall **)(__int64, __int128 *))(a1 + 72);
  if ( v2 )
  {
    v6 = *a2;
    v4 = *(_QWORD *)(a1 + 16);
    try
    {
      result = v2(v4, &v6);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x8B,
                             (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                             v5);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL);
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014318  sub     rsp, 58h
0x18001431c  mov     r10, rcx
0x18001431f  mov     rax, [rcx+48h]
0x180014323  test    rax, rax
0x180014326  jnz     short loc_18001434B
0x180014328  mov     rcx, [rsp+58h]; this
0x18001432d  mov     r9d, 80004001h; char *
0x180014333  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x18001433a  mov     edx, 83h; void *
0x18001433f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014344  mov     eax, 80004001h
0x180014349  jmp     short loc_180014382
0x18001434b  movaps  xmm0, xmmword ptr [rdx]
0x18001434e  movdqa  [rsp+58h+var_18], xmm0
0x180014354  mov     rcx, [rsp+58h+arg_28]
0x18001435c  mov     [rsp+58h+var_30], rcx
0x180014361  mov     rcx, [rsp+58h+arg_20]
0x180014369  mov     [rsp+58h+var_38], rcx
0x18001436e  lea     rdx, [rsp+58h+var_18]
0x180014373  mov     rcx, [r10+10h]
0x180014377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001437c  jmp     short loc_180014382
0x18001437e  mov     eax, [rsp+58h+arg_0]
0x180014382  add     rsp, 58h
0x180014386  retn
```
