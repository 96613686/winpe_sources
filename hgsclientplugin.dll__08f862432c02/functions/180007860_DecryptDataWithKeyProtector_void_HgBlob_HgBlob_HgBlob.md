# DecryptDataWithKeyProtector(void *,HgBlob,HgBlob,HgBlob *)

- ea: `0x180007860`
- end: `0x1800078d9`
- name: `?DecryptDataWithKeyProtector@@YAJPEAXUHgBlob@@1PEAU1@@Z`
- size: `121`
- prototype: `__int64 __fastcall(Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *, struct _MI_Application *, __int64, const struct HgBlob *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049f4`
- `0x180007860`
- `0x180009070`

## string_xrefs

- `0x18000788b`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x1800078b7`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall DecryptDataWithKeyProtector(
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *a1,
        struct _MI_Application *a2,
        __int64 a3,
        const struct HgBlob *a4)
{
  __int64 result; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  struct HgBlob *v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( LODWORD(a2->reserved1) && a2->reserved2 && *(_DWORD *)a3 && *(_QWORD *)(a3 + 8) )
  {
    if ( a4 )
    {
      try
      {
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector(
          a1,
          a2,
          (const struct HgBlob *)a3,
          a4,
          v7);
        result = 0;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x120, v5, v6);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
        (const char *)0x80070057LL,
        (int)v7);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      (const char *)0x80070057LL,
      (int)v7);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007860  sub     rsp, 28h
0x180007864  xor     eax, eax
0x180007866  cmp     [rdx], eax
0x180007868  jbe     short loc_1800078AC
0x18000786a  cmp     [rdx+8], rax
0x18000786e  jz      short loc_1800078AC
0x180007870  cmp     [r8], eax
0x180007873  jbe     short loc_1800078AC
0x180007875  cmp     [r8+8], rax
0x180007879  jz      short loc_1800078AC
0x18000787b  test    r9, r9
0x18000787e  jnz     short loc_1800078A3
0x180007880  mov     rcx, [rsp+28h]; this
0x180007885  mov     r9d, 80070057h; char *
0x18000788b  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180007892  mov     edx, 119h; void *
0x180007897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000789c  mov     eax, 80070057h
0x1800078a1  jmp     short loc_1800078D3
0x1800078a3  call    ?DecryptDataWithKeyProtector@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAU_MI_Application@@AEBUHgBlob@@1AEAU7@@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector(_MI_Application &,HgBlob const &,HgBlob const &,HgBlob &)
0x1800078a8  xor     eax, eax
0x1800078aa  jmp     short loc_1800078D3
0x1800078ac  mov     rcx, [rsp+28h]; this
0x1800078b1  mov     r9d, 80070057h; char *
0x1800078b7  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x1800078be  mov     edx, 118h; void *
0x1800078c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800078c8  mov     eax, 80070057h
0x1800078cd  jmp     short loc_1800078D3
0x1800078cf  mov     eax, [rsp+28h+arg_8]
0x1800078d3  add     rsp, 28h
0x1800078d7  retn
```
