# COMPlusUninstallActionW

- ea: `0x180016e20`
- end: `0x180016f26`
- name: `COMPlusUninstallActionW`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001e60`
- `0x180015594`
- `0x1800166f8`
- `0x180016aac`
- `0x180016e20`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016eb8`
- `msvcrt!_wcsicmp` at `0x180016eef`
- `msvcrt!_wcsicmp` at `0x180016eb8`
- `msvcrt!_wcsicmp` at `0x180016eef`
- `msvcrt!wcschr` at `0x180016e9a`
- `msvcrt!wcschr` at `0x180016ec7`
- `msvcrt!wcschr` at `0x180016e9a`
- `msvcrt!wcschr` at `0x180016ec7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016f0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016e55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016e55`

## string_xrefs

- `0x180016eae`: `RemoveApplication`
- `0x180016ee5`: `RemovePartition`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COMPlusUninstallActionW(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  unsigned __int64 v4; // rsi
  unsigned __int16 *v5; // rax
  wchar_t *v6; // rdi
  int v8; // ebx
  wchar_t *v9; // rax
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  int v12; // eax

  v4 = (int)(safe_lstrlenW(a3) + 1);
  v5 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v4, 2u));
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v8 = StringCchCopyW(v5, v4, a3);
  if ( v8 >= 0 )
  {
    v9 = wcschr(v6, 0x3Au);
    if ( v9 )
    {
      *v9 = 0;
      v10 = v9 + 1;
      if ( _wcsicmp(v6, L"RemoveApplication") )
      {
        if ( !_wcsicmp(v6, L"RemovePartition") )
        {
          v12 = RemovePartition(v10);
          goto LABEL_10;
        }
      }
      else
      {
        v11 = wcschr(v10, 0x3Au);
        if ( v11 )
        {
          *v11 = 0;
          v12 = RemoveApplication(v11 + 1, v10);
LABEL_10:
          v8 = v12;
          goto LABEL_12;
        }
      }
    }
    v8 = -2147024809;
  }
LABEL_12:
  CoTaskMemFree(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016e20  mov     [rsp+arg_0], rbx
0x180016e25  mov     [rsp+arg_8], rsi
0x180016e2a  push    rdi
0x180016e2b  sub     rsp, 20h
0x180016e2f  mov     rbx, r8
0x180016e32  mov     rcx, r8; unsigned __int16 *
0x180016e35  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180016e3a  inc     eax
0x180016e3c  movsxd  rsi, eax
0x180016e3f  mov     eax, 2
0x180016e44  mul     rsi
0x180016e47  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016e4e  cmovb   rax, rcx
0x180016e52  mov     rcx, rax; cb
0x180016e55  call    cs:__imp_CoTaskMemAlloc
0x180016e5b  mov     rdi, rax
0x180016e5e  test    rax, rax
0x180016e61  jnz     short loc_180016E6D
0x180016e63  mov     eax, 8007000Eh
0x180016e68  jmp     loc_180016F16
0x180016e6d  mov     r8, rbx; unsigned __int16 *
0x180016e70  mov     rdx, rsi; unsigned __int64
0x180016e73  mov     rcx, rdi; unsigned __int16 *
0x180016e76  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016e7b  mov     ebx, eax
0x180016e7d  test    eax, eax
0x180016e7f  jns     short loc_180016E90
0x180016e81  mov     rcx, rdi; pv
0x180016e84  call    cs:__imp_CoTaskMemFree
0x180016e8a  nop
0x180016e8b  jmp     loc_180016F14
0x180016e90  mov     esi, 3Ah ; ':'
0x180016e95  mov     edx, esi; Ch
0x180016e97  mov     rcx, rdi; Str
0x180016e9a  call    cs:__imp_wcschr
0x180016ea0  test    rax, rax
0x180016ea3  jz      short loc_180016F05
0x180016ea5  xor     ecx, ecx
0x180016ea7  mov     [rax], cx
0x180016eaa  lea     rbx, [rax+2]
0x180016eae  lea     rdx, aRemoveapplicat; "RemoveApplication"
0x180016eb5  mov     rcx, rdi; String1
0x180016eb8  call    cs:__imp__wcsicmp
0x180016ebe  test    eax, eax
0x180016ec0  jnz     short loc_180016EE5
0x180016ec2  mov     edx, esi; Ch
0x180016ec4  mov     rcx, rbx; Str
0x180016ec7  call    cs:__imp_wcschr
0x180016ecd  test    rax, rax
0x180016ed0  jz      short loc_180016F05
0x180016ed2  xor     ecx, ecx
0x180016ed4  mov     [rax], cx
0x180016ed7  lea     rcx, [rax+2]; String2
0x180016edb  mov     rdx, rbx; psz
0x180016ede  call    ?RemoveApplication@@YAJPEBG0@Z; RemoveApplication(ushort const *,ushort const *)
0x180016ee3  jmp     short loc_180016F01
0x180016ee5  lea     rdx, aRemovepartitio; "RemovePartition"
0x180016eec  mov     rcx, rdi; String1
0x180016eef  call    cs:__imp__wcsicmp
0x180016ef5  test    eax, eax
0x180016ef7  jnz     short loc_180016F05
0x180016ef9  mov     rcx, rbx; String2
0x180016efc  call    ?RemovePartition@@YAJPEBG@Z; RemovePartition(ushort const *)
0x180016f01  mov     ebx, eax
0x180016f03  jmp     short loc_180016F0A
0x180016f05  mov     ebx, 80070057h
0x180016f0a  mov     rcx, rdi; pv
0x180016f0d  call    cs:__imp_CoTaskMemFree
0x180016f13  nop
0x180016f14  mov     eax, ebx
0x180016f16  mov     rbx, [rsp+28h+arg_0]
0x180016f1b  mov     rsi, [rsp+28h+arg_8]
0x180016f20  add     rsp, 20h
0x180016f24  pop     rdi
0x180016f25  retn
```
