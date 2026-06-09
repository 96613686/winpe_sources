# UnwrapKeyProtector(void *,HgBlob,HgBlob *,HgBlob *,HgBlob *,HgBlob *)

- ea: `0x180008320`
- end: `0x1800083b1`
- name: `?UnwrapKeyProtector@@YAJPEAXUHgBlob@@PEAU1@222@Z`
- size: `145`
- prototype: `__int64 __fastcall(__int64, struct _MI_Application *, const struct HgBlob *, struct HgBlob *, struct HgBlob *, struct HgBlob *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049f4`
- `0x180008320`
- `0x1800096ec`

## string_xrefs

- `0x18000836c`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x18000838f`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall UnwrapKeyProtector(
        __int64 a1,
        struct _MI_Application *a2,
        const struct HgBlob *a3,
        struct HgBlob *a4,
        struct HgBlob *a5,
        struct HgBlob *a6)
{
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-18h]
  struct HgBlob *v10; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( LODWORD(a2->reserved1) && a2->reserved2 )
  {
    if ( a3 && a4 && a5 && a6 )
    {
      try
      {
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::UnwrapKeyProtector(
          a6,
          a2,
          a3,
          a4,
          a5,
          a6,
          v10);
        result = 0;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0xF6, v6, v7);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
        (const char *)0x80070057LL,
        v9);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      (const char *)0x80070057LL,
      v9);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008320  sub     rsp, 38h
0x180008324  cmp     dword ptr [rdx], 0
0x180008327  jbe     short loc_180008384
0x180008329  cmp     qword ptr [rdx+8], 0
0x18000832e  jz      short loc_180008384
0x180008330  test    r8, r8
0x180008333  jz      short loc_180008361
0x180008335  test    r9, r9
0x180008338  jz      short loc_180008361
0x18000833a  mov     rax, [rsp+38h+arg_20]
0x18000833f  test    rax, rax
0x180008342  jz      short loc_180008361
0x180008344  mov     rcx, [rsp+38h+arg_28]; this
0x180008349  test    rcx, rcx
0x18000834c  jz      short loc_180008361
0x18000834e  mov     [rsp+38h+var_10], rcx; struct HgBlob *
0x180008353  mov     [rsp+38h+var_18], rax; struct HgBlob *
0x180008358  call    ?UnwrapKeyProtector@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAU_MI_Application@@AEBUHgBlob@@AEAU7@222@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::UnwrapKeyProtector(_MI_Application &,HgBlob const &,HgBlob &,HgBlob &,HgBlob &,HgBlob &)
0x18000835d  xor     eax, eax
0x18000835f  jmp     short loc_1800083AB
0x180008361  mov     rcx, [rsp+38h]; this
0x180008366  mov     r9d, 80070057h; char *
0x18000836c  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180008373  mov     edx, 0EDh; void *
0x180008378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000837d  mov     eax, 80070057h
0x180008382  jmp     short loc_1800083AB
0x180008384  mov     rcx, [rsp+38h]; this
0x180008389  mov     r9d, 80070057h; char *
0x18000838f  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180008396  mov     edx, 0ECh; void *
0x18000839b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083a0  mov     eax, 80070057h
0x1800083a5  jmp     short loc_1800083AB
0x1800083a7  mov     eax, [rsp+38h+arg_8]
0x1800083ab  add     rsp, 38h
0x1800083af  retn
```
