# GetPluginVersion

- ea: `0x180008410`
- end: `0x18000844e`
- name: `GetPluginVersion`
- size: `62`
- prototype: `__int64 __fastcall(_OWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049f4`
- `0x180008410`

## string_xrefs

- `0x18000841e`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall GetPluginVersion(_OWORD *a1)
{
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1 )
  {
    result = 0;
    *a1 = c_currentVersion;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      (const char *)0x80070057LL);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008410  sub     rsp, 28h
0x180008414  test    rcx, rcx
0x180008417  jnz     short loc_18000843C
0x180008419  mov     rcx, [rsp+28h]; this
0x18000841e  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180008425  mov     r9d, 80070057h; char *
0x18000842b  mov     edx, 1Eh; void *
0x180008430  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008435  mov     eax, 80070057h
0x18000843a  jmp     short loc_180008449
0x18000843c  movups  xmm0, cs:?c_currentVersion@@3UPluginVersion@@B; PluginVersion const c_currentVersion
0x180008443  xor     eax, eax
0x180008445  movdqu  xmmword ptr [rcx], xmm0
0x180008449  add     rsp, 28h
0x18000844d  retn
```
