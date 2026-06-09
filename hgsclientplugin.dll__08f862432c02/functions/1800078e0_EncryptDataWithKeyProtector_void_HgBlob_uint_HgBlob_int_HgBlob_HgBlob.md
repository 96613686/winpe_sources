# EncryptDataWithKeyProtector(void *,HgBlob,uint,HgBlob,int,HgBlob *,HgBlob *)

- ea: `0x1800078e0`
- end: `0x180007986`
- name: `?EncryptDataWithKeyProtector@@YAJPEAXUHgBlob@@I1HPEAU1@2@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, struct _MI_Application *, unsigned int, __int64, int, union _MI_Value *, union _MI_Value *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049f4`
- `0x1800078e0`
- `0x1800092fc`

## string_xrefs

- `0x180007941`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`
- `0x180007964`: `servercommon\base\securehostingservice\common\service\plugin\hgsclientplugin.cpp`

## pseudocode

```c
__int64 __fastcall EncryptDataWithKeyProtector(
        __int64 a1,
        struct _MI_Application *a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        union _MI_Value *a6,
        union _MI_Value *a7)
{
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 result; // rax
  struct HgBlob *v10; // [rsp+20h] [rbp-28h]
  struct HgBlob *v11; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( LODWORD(a2->reserved1) && a2->reserved2 && *(_DWORD *)a4 && *(_QWORD *)(a4 + 8) )
  {
    if ( a6 && a7 )
    {
      try
      {
        LOBYTE(v10) = a5 != 0;
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::EncryptDataWithKeyProtector(
          (Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *)a6,
          a2,
          (const struct HgBlob *)a3,
          a4,
          v10,
          a6,
          a7,
          v11);
        result = 0;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x10E, v7, v8);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
        (const char *)0x80070057LL,
        (int)v10);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\hgsclientplugin.cpp",
      (const char *)0x80070057LL,
      (int)v10);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800078e0  sub     rsp, 48h
0x1800078e4  mov     r10d, r8d
0x1800078e7  xor     eax, eax
0x1800078e9  cmp     [rdx], eax
0x1800078eb  jbe     short loc_180007959
0x1800078ed  cmp     [rdx+8], rax
0x1800078f1  jz      short loc_180007959
0x1800078f3  cmp     [r9], eax
0x1800078f6  jbe     short loc_180007959
0x1800078f8  cmp     [r9+8], rax
0x1800078fc  jz      short loc_180007959
0x1800078fe  mov     rcx, [rsp+48h+arg_28]; this
0x180007903  test    rcx, rcx
0x180007906  jz      short loc_180007936
0x180007908  mov     r8, [rsp+48h+arg_30]
0x180007910  test    r8, r8
0x180007913  jz      short loc_180007936
0x180007915  cmp     [rsp+48h+arg_20], eax
0x180007919  setnz   al
0x18000791c  mov     [rsp+48h+var_18], r8; union _MI_Value *
0x180007921  mov     [rsp+48h+var_20], rcx; union _MI_Value *
0x180007926  mov     byte ptr [rsp+48h+var_28], al; struct HgBlob *
0x18000792a  mov     r8d, r10d; struct HgBlob *
0x18000792d  call    ?EncryptDataWithKeyProtector@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAU_MI_Application@@AEBUHgBlob@@I1_NAEAU7@3@Z; Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::EncryptDataWithKeyProtector(_MI_Application &,HgBlob const &,uint,HgBlob const &,bool,HgBlob &,HgBlob &)
0x180007932  xor     eax, eax
0x180007934  jmp     short loc_180007980
0x180007936  mov     rcx, [rsp+48h]; this
0x18000793b  mov     r9d, 80070057h; char *
0x180007941  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x180007948  mov     edx, 104h; void *
0x18000794d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007952  mov     eax, 80070057h
0x180007957  jmp     short loc_180007980
0x180007959  mov     rcx, [rsp+48h]; this
0x18000795e  mov     r9d, 80070057h; char *
0x180007964  lea     r8, aServercommonBa_1; "servercommon\\base\\securehostingservic"...
0x18000796b  mov     edx, 103h; void *
0x180007970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007975  mov     eax, 80070057h
0x18000797a  jmp     short loc_180007980
0x18000797c  mov     eax, [rsp+48h+arg_8]
0x180007980  add     rsp, 48h
0x180007984  retn
```
