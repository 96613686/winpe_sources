# CShareItemResult::UpdateResult(_SHARE_OPERATION_RESULT)

- ea: `0x180066ba4`
- end: `0x180066c54`
- name: `?UpdateResult@CShareItemResult@@QEAAJW4_SHARE_OPERATION_RESULT@@@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006d410`

## callees

- `0x180066250`
- `0x180066ba4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c3d`
- `SHELL32!SHCreateItemFromParsingName` at `0x180066c25`
- `SHELL32!SHCreateItemFromParsingName` at `0x180066c25`

## pseudocode

```c
__int64 __fastcall CShareItemResult::UpdateResult(__int64 a1, int a2)
{
  __int64 v3; // rcx
  HRESULT v4; // ebx
  PCWSTR pszPath; // [rsp+40h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 )
  {
    return 0;
  }
  else
  {
    v3 = *(_QWORD *)(a1 + 8);
    if ( v3 )
    {
      *(_DWORD *)(a1 + 36) = 0;
      pv = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v3 + 40LL))(v3, 2147844096LL, &pv);
      if ( v4 >= 0 )
      {
        pszPath = 0;
        v4 = PathMapLocalToUNC((const unsigned __int16 *)pv, (unsigned __int16 **)&pszPath);
        if ( v4 >= 0 )
        {
          v4 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)(a1 + 16));
          CoTaskMemFree((LPVOID)pszPath);
        }
        CoTaskMemFree(pv);
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180066ba4  mov     [rsp+arg_0], rbx
0x180066ba9  push    rdi
0x180066baa  sub     rsp, 20h
0x180066bae  mov     rdi, rcx
0x180066bb1  test    edx, edx
0x180066bb3  jnz     loc_180066C45
0x180066bb9  mov     rcx, [rcx+8]
0x180066bbd  test    rcx, rcx
0x180066bc0  jnz     short loc_180066BC9
0x180066bc2  mov     ebx, 8000FFFFh
0x180066bc7  jmp     short loc_180066C47
0x180066bc9  mov     dword ptr [rdi+24h], 0
0x180066bd0  lea     r8, [rsp+28h+pv]
0x180066bd5  mov     [rsp+28h+pv], 0
0x180066bde  mov     edx, 80058000h
0x180066be3  mov     rax, [rcx]
0x180066be6  mov     rax, [rax+28h]
0x180066bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bef  mov     ebx, eax
0x180066bf1  test    eax, eax
0x180066bf3  js      short loc_180066C47
0x180066bf5  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x180066bfa  lea     rdx, [rsp+28h+pszPath]; unsigned __int16 **
0x180066bff  mov     [rsp+28h+pszPath], 0
0x180066c08  call    ?PathMapLocalToUNC@@YAJPEBGPEAPEAG@Z; PathMapLocalToUNC(ushort const *,ushort * *)
0x180066c0d  mov     ebx, eax
0x180066c0f  test    eax, eax
0x180066c11  js      short loc_180066C38
0x180066c13  mov     rcx, [rsp+28h+pszPath]; pszPath
0x180066c18  lea     r9, [rdi+10h]; ppv
0x180066c1c  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180066c23  xor     edx, edx; pbc
0x180066c25  call    cs:__imp_SHCreateItemFromParsingName
0x180066c2b  mov     rcx, [rsp+28h+pszPath]; pv
0x180066c30  mov     ebx, eax
0x180066c32  call    cs:__imp_CoTaskMemFree
0x180066c38  mov     rcx, [rsp+28h+pv]; pv
0x180066c3d  call    cs:__imp_CoTaskMemFree
0x180066c43  jmp     short loc_180066C47
0x180066c45  xor     ebx, ebx
0x180066c47  mov     eax, ebx
0x180066c49  mov     rbx, [rsp+28h+arg_0]
0x180066c4e  add     rsp, 20h
0x180066c52  pop     rdi
0x180066c53  retn
```
