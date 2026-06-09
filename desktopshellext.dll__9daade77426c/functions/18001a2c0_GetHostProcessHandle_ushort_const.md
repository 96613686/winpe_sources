# GetHostProcessHandle(ushort const *)

- ea: `0x18001a2c0`
- end: `0x18001a333`
- name: `?GetHostProcessHandle@@YA?AV?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@PEBG@Z`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180013a30`
- `0x180013c10`
- `0x18001582c`

## callees

- `0x18000c6d0`
- `0x18001a2c0`
- `0x18001a33c`
- `0x18001a400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a2f5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a2f5`

## string_xrefs

- `0x18001a2c9`: `ProcessId`

## pseudocode

```c
__int64 __fastcall GetHostProcessHandle(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  DWORD *v5; // rax
  HANDLE v6; // rax
  HANDLE v8; // [rsp+50h] [rbp+18h] BYREF
  char v9; // [rsp+58h] [rbp+20h] BYREF
  char v10; // [rsp+5Ch] [rbp+24h]

  GetDWORDValueFromHostSessionKey((__int64)&v9, a2, L"ProcessId", a4);
  if ( !v10 )
    goto LABEL_5;
  v5 = (DWORD *)std::optional<unsigned long>::value(&v9);
  v6 = OpenProcess(0x100000u, 0, *v5);
  v8 = v6;
  if ( !v6 )
  {
    fc::details::registry_store_lock::~registry_store_lock((fc::details::registry_store_lock *)&v8);
LABEL_5:
    *(_BYTE *)(a1 + 8) = 0;
    return a1;
  }
  *(_QWORD *)a1 = v6;
  *(_BYTE *)(a1 + 8) = 1;
  v8 = 0;
  fc::details::registry_store_lock::~registry_store_lock((fc::details::registry_store_lock *)&v8);
  return a1;
}

```

## disassembly

```asm
0x18001a2c0  push    rbx
0x18001a2c2  sub     rsp, 30h
0x18001a2c6  mov     rbx, rcx
0x18001a2c9  lea     r8, aProcessid; "ProcessId"
0x18001a2d0  lea     rcx, [rsp+38h+arg_18]
0x18001a2d5  call    ?GetDWORDValueFromHostSessionKey@@YA?AV?$optional@K@std@@PEBG0@Z; GetDWORDValueFromHostSessionKey(ushort const *,ushort const *)
0x18001a2da  cmp     [rsp+38h+arg_1C], 0
0x18001a2df  jz      short loc_18001A326
0x18001a2e1  lea     rcx, [rsp+38h+arg_18]
0x18001a2e6  call    ?value@?$optional@K@std@@QEGAAAEAKXZ; std::optional<ulong>::value(void)
0x18001a2eb  xor     edx, edx; bInheritHandle
0x18001a2ed  mov     ecx, 100000h; dwDesiredAccess
0x18001a2f2  mov     r8d, [rax]; dwProcessId
0x18001a2f5  call    cs:__imp_OpenProcess
0x18001a2fb  mov     [rsp+38h+arg_10], rax
0x18001a300  lea     rcx, [rsp+38h+arg_10]; this
0x18001a305  test    rax, rax
0x18001a308  jz      short loc_18001A321
0x18001a30a  mov     [rbx], rax
0x18001a30d  mov     byte ptr [rbx+8], 1
0x18001a311  mov     [rsp+38h+arg_10], 0
0x18001a31a  call    ??1registry_store_lock@details@fc@@QEAA@XZ; fc::details::registry_store_lock::~registry_store_lock(void)
0x18001a31f  jmp     short loc_18001A32A
0x18001a321  call    ??1registry_store_lock@details@fc@@QEAA@XZ; fc::details::registry_store_lock::~registry_store_lock(void)
0x18001a326  mov     byte ptr [rbx+8], 0
0x18001a32a  mov     rax, rbx
0x18001a32d  add     rsp, 30h
0x18001a331  pop     rbx
0x18001a332  retn
```
