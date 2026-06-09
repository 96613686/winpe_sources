# Microsoft::HostGuardian::Client::HgServicePlugin::DecryptWithKeyProtector(HgBlob,HgBlob,HgBlob *)

- ea: `0x1800140ac`
- end: `0x18001410e`
- name: `?DecryptWithKeyProtector@HgServicePlugin@Client@HostGuardian@Microsoft@@QEAAJUHgBlob@@0PEAU5@@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d0b8`

## callees

- `0x1800064b4`
- `0x1800140ac`
- `0x180017010`

## string_xrefs

- `0x1800140c4`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::DecryptWithKeyProtector(__int64 a1)
{
  __int64 (*v1)(void); // rax
  __int64 result; // rax
  const char *v3; // r9
  int v4; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(__int64 (**)(void))(a1 + 88);
  if ( v1 )
  {
    try
    {
      result = v1();
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xAD,
                             (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
                             v3);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
      (const char *)0x80004001LL,
      v4);
    return 2147500033LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800140ac  sub     rsp, 58h
0x1800140b0  mov     rax, [rcx+58h]
0x1800140b4  test    rax, rax
0x1800140b7  jnz     short loc_1800140DC
0x1800140b9  mov     rcx, [rsp+58h]; this
0x1800140be  mov     r9d, 80004001h; char *
0x1800140c4  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x1800140cb  mov     edx, 0A7h; void *
0x1800140d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800140d5  mov     eax, 80004001h
0x1800140da  jmp     short loc_180014108
0x1800140dc  movaps  xmm0, xmmword ptr [r8]
0x1800140e0  movdqa  [rsp+58h+var_28], xmm0
0x1800140e6  movaps  xmm1, xmmword ptr [rdx]
0x1800140e9  movdqa  [rsp+58h+var_18], xmm1
0x1800140ef  lea     r8, [rsp+58h+var_28]
0x1800140f4  lea     rdx, [rsp+58h+var_18]
0x1800140f9  mov     rcx, [rcx+10h]
0x1800140fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014102  jmp     short loc_180014108
0x180014104  mov     eax, [rsp+58h+arg_0]
0x180014108  add     rsp, 58h
0x18001410c  retn
```
