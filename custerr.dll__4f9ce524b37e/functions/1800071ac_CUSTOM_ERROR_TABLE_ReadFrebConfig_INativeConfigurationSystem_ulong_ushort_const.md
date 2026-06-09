# CUSTOM_ERROR_TABLE::ReadFrebConfig(INativeConfigurationSystem *,ulong,ushort const *)

- ea: `0x1800071ac`
- end: `0x18000732b`
- name: `?ReadFrebConfig@CUSTOM_ERROR_TABLE@@AEAAJPEAVINativeConfigurationSystem@@KPEBG@Z`
- size: `383`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_TABLE *__hidden this, struct INativeConfigurationSystem *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800065f0`

## callees

- `0x1800071ac`
- `0x180008010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800072b9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800072b9`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800072c7`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800072c7`

## string_xrefs

- `0x180007298`: `directory`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_TABLE::ReadFrebConfig(
        CUSTOM_ERROR_TABLE *this,
        struct INativeConfigurationSystem *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v6)(struct INativeConfigurationSystem *, __int64 *); // rax
  int v8; // ebx
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h] BYREF
  const unsigned __int16 *v12; // [rsp+40h] [rbp-10h] BYREF
  __int64 v13; // [rsp+78h] [rbp+28h] BYREF
  const unsigned __int16 *v14; // [rsp+88h] [rbp+38h] BYREF

  v14 = a4;
  v4 = *(_QWORD *)a2;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v6 = *(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64 *))(v4 + 56);
  v13 = 0;
  LODWORD(v14) = 0;
  v8 = v6(a2, &v11);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v11 + 32LL))(v11, a3, &v10, 0);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v10 + 32LL))(
             v10,
             L"traceFailedRequestsLogging",
             &v13);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 72LL))(
               v13,
               L"enabled",
               &v14,
               0,
               0);
        if ( v8 >= 0 )
        {
          if ( (_DWORD)v14 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v13 + 64LL))(
                   v13,
                   L"directory",
                   &v12,
                   0,
                   0);
            if ( v8 >= 0 )
              v8 = STRU::Copy((CUSTOM_ERROR_TABLE *)((char *)this + 80), v12);
          }
          else
          {
            STRU::Reset((CUSTOM_ERROR_TABLE *)((char *)this + 80));
          }
        }
      }
    }
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800071ac  mov     [rsp-18h+arg_0], rbx
0x1800071b1  mov     [rsp-18h+arg_18], r9
0x1800071b6  push    rbp
0x1800071b7  push    rsi
0x1800071b8  push    rdi
0x1800071b9  mov     rbp, rsp
0x1800071bc  sub     rsp, 50h
0x1800071c0  mov     rax, [rdx]
0x1800071c3  mov     r9, rdx
0x1800071c6  mov     rdi, rcx
0x1800071c9  mov     [rbp+var_18], 0
0x1800071d1  lea     rdx, [rbp+var_18]
0x1800071d5  mov     [rbp+var_20], 0
0x1800071dd  mov     rcx, r9
0x1800071e0  mov     [rbp+var_10], 0
0x1800071e8  mov     rax, [rax+38h]
0x1800071ec  mov     esi, r8d
0x1800071ef  mov     [rbp+arg_8], 0
0x1800071f7  mov     dword ptr [rbp+arg_18], 0
0x1800071fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007203  mov     ebx, eax
0x180007205  test    eax, eax
0x180007207  js      loc_1800072CD
0x18000720d  mov     rcx, [rbp+var_18]
0x180007211  lea     r8, [rbp+var_20]
0x180007215  xor     r9d, r9d
0x180007218  mov     edx, esi
0x18000721a  mov     rax, [rcx]
0x18000721d  mov     rax, [rax+20h]
0x180007221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007226  mov     ebx, eax
0x180007228  test    eax, eax
0x18000722a  js      loc_1800072CD
0x180007230  mov     rcx, [rbp+var_20]
0x180007234  lea     r8, [rbp+arg_8]
0x180007238  lea     rdx, aTracefailedreq; "traceFailedRequestsLogging"
0x18000723f  mov     rax, [rcx]
0x180007242  mov     rax, [rax+20h]
0x180007246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724b  mov     ebx, eax
0x18000724d  test    eax, eax
0x18000724f  js      short loc_1800072CD
0x180007251  mov     rcx, [rbp+arg_8]
0x180007255  lea     r8, [rbp+arg_18]
0x180007259  xor     r9d, r9d
0x18000725c  mov     [rsp+50h+var_30], 0
0x180007265  lea     rdx, aEnabled; "enabled"
0x18000726c  mov     rax, [rcx]
0x18000726f  mov     rax, [rax+48h]
0x180007273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007278  mov     ebx, eax
0x18000727a  test    eax, eax
0x18000727c  js      short loc_1800072CD
0x18000727e  cmp     dword ptr [rbp+arg_18], 0
0x180007282  jz      short loc_1800072C3
0x180007284  mov     rcx, [rbp+arg_8]
0x180007288  lea     r8, [rbp+var_10]
0x18000728c  xor     r9d, r9d
0x18000728f  mov     [rsp+50h+var_30], 0
0x180007298  lea     rdx, aDirectory; "directory"
0x18000729f  mov     rax, [rcx]
0x1800072a2  mov     rax, [rax+40h]
0x1800072a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ab  mov     ebx, eax
0x1800072ad  test    eax, eax
0x1800072af  js      short loc_1800072CD
0x1800072b1  mov     rdx, [rbp+var_10]
0x1800072b5  lea     rcx, [rdi+50h]
0x1800072b9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800072bf  mov     ebx, eax
0x1800072c1  jmp     short loc_1800072CD
0x1800072c3  lea     rcx, [rdi+50h]
0x1800072c7  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800072cd  mov     rcx, [rbp+arg_8]
0x1800072d1  test    rcx, rcx
0x1800072d4  jz      short loc_1800072EA
0x1800072d6  mov     rax, [rcx]
0x1800072d9  mov     rax, [rax+10h]
0x1800072dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e2  mov     [rbp+arg_8], 0
0x1800072ea  mov     rcx, [rbp+var_20]
0x1800072ee  test    rcx, rcx
0x1800072f1  jz      short loc_180007307
0x1800072f3  mov     rax, [rcx]
0x1800072f6  mov     rax, [rax+10h]
0x1800072fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072ff  mov     [rbp+var_20], 0
0x180007307  mov     rcx, [rbp+var_18]
0x18000730b  test    rcx, rcx
0x18000730e  jz      short loc_18000731C
0x180007310  mov     rax, [rcx]
0x180007313  mov     rax, [rax+10h]
0x180007317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000731c  mov     eax, ebx
0x18000731e  mov     rbx, [rsp+50h+arg_0]
0x180007323  add     rsp, 50h
0x180007327  pop     rdi
0x180007328  pop     rsi
0x180007329  pop     rbp
0x18000732a  retn
```
