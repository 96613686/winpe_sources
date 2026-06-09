# CUSTOM_ERROR_TABLE::ReadAlternateHostName(INativeConfigurationSystem *,ushort const *)

- ea: `0x1800070c4`
- end: `0x1800071a3`
- name: `?ReadAlternateHostName@CUSTOM_ERROR_TABLE@@AEAAJPEAVINativeConfigurationSystem@@PEBG@Z`
- size: `223`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_TABLE *__hidden this, struct INativeConfigurationSystem *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800065f0`

## callees

- `0x1800070c4`
- `0x180008010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007159`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007159`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_TABLE::ReadAlternateHostName(
        CUSTOM_ERROR_TABLE *this,
        struct INativeConfigurationSystem *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(struct INativeConfigurationSystem *, const wchar_t *, const unsigned __int16 *, __int64 *, __int64 *, _QWORD); // rax
  int v6; // ebx
  const unsigned __int16 *v8; // [rsp+40h] [rbp-18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v3 = *(_QWORD *)a2;
  v9 = 0;
  v5 = *(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, const unsigned __int16 *, __int64 *, __int64 *, _QWORD))(v3 + 24);
  v10 = 0;
  v8 = 0;
  v6 = v5(a2, L"system.webServer/serverRuntime", a3, &v10, &v9, 0);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(
           v10,
           L"alternateHostName",
           &v8,
           0,
           0);
    if ( v6 >= 0 )
      v6 = STRU::Copy((CUSTOM_ERROR_TABLE *)((char *)this + 192), v8);
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800070c4  mov     r11, rsp
0x1800070c7  mov     [r11+8], rbx
0x1800070cb  push    rdi
0x1800070cc  sub     rsp, 50h
0x1800070d0  mov     rax, [rdx]
0x1800070d3  lea     r9, [r11+20h]
0x1800070d7  mov     rdi, rcx
0x1800070da  mov     qword ptr [r11-30h], 0
0x1800070e2  lea     rcx, [r11+10h]
0x1800070e6  mov     qword ptr [r11+10h], 0
0x1800070ee  mov     r10, rdx
0x1800070f1  mov     [r11-38h], rcx
0x1800070f5  mov     rax, [rax+18h]
0x1800070f9  lea     rdx, aSystemWebserve_1; "system.webServer/serverRuntime"
0x180007100  mov     rcx, r10
0x180007103  mov     qword ptr [r11+20h], 0
0x18000710b  mov     qword ptr [r11-18h], 0
0x180007113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007118  mov     ebx, eax
0x18000711a  test    eax, eax
0x18000711c  js      short loc_180007161
0x18000711e  mov     rcx, [rsp+58h+arg_18]
0x180007123  lea     r8, [rsp+58h+var_18]
0x180007128  xor     r9d, r9d
0x18000712b  mov     [rsp+58h+var_38], 0
0x180007134  lea     rdx, aAlternatehostn; "alternateHostName"
0x18000713b  mov     rax, [rcx]
0x18000713e  mov     rax, [rax+40h]
0x180007142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007147  mov     ebx, eax
0x180007149  test    eax, eax
0x18000714b  js      short loc_180007161
0x18000714d  mov     rdx, [rsp+58h+var_18]
0x180007152  lea     rcx, [rdi+0C0h]
0x180007159  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000715f  mov     ebx, eax
0x180007161  mov     rcx, [rsp+58h+arg_8]
0x180007166  test    rcx, rcx
0x180007169  jz      short loc_180007180
0x18000716b  mov     rax, [rcx]
0x18000716e  mov     rax, [rax+10h]
0x180007172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007177  mov     [rsp+58h+arg_8], 0
0x180007180  mov     rcx, [rsp+58h+arg_18]
0x180007185  test    rcx, rcx
0x180007188  jz      short loc_180007196
0x18000718a  mov     rax, [rcx]
0x18000718d  mov     rax, [rax+10h]
0x180007191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007196  mov     eax, ebx
0x180007198  mov     rbx, [rsp+58h+arg_0]
0x18000719d  add     rsp, 50h
0x1800071a1  pop     rdi
0x1800071a2  retn
```
