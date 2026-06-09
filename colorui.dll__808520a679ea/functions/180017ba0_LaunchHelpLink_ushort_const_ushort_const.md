# LaunchHelpLink(ushort const *,ushort const *)

- ea: `0x180017ba0`
- end: `0x180017c6a`
- name: `?LaunchHelpLink@@YAJPEBG0@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cd90`

## callees

- `0x180017ba0`
- `0x180019010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180017c22`
- `ntdll!WinSqmAddToStream` at `0x180017c22`
- `ole32!CoCreateInstance` at `0x180017bd6`
- `ole32!CoCreateInstance` at `0x180017bd6`
- `OLEAUT32!__imp_SysAllocString` at `0x180017be9`
- `OLEAUT32!__imp_SysAllocString` at `0x180017be9`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c57`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c57`

## pseudocode

```c
__int64 __fastcall LaunchHelpLink(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  OLECHAR *v2; // rbx
  HRESULT v3; // edi
  int v5; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v6; // [rsp+38h] [rbp-10h]
  LPVOID v7; // [rsp+58h] [rbp+10h] BYREF

  v7 = 0;
  v2 = 0;
  v3 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         0x17u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &v7);
  if ( v3 >= 0 )
  {
    v2 = SysAllocString(L"mshelp://windows/?id=76f61616-6d12-46ec-bac2-49969d130c79");
    if ( v2 )
    {
      v5 = 2;
      v6 = L"HELP_ENTRY_ID_COLOR_MANAGEMENT_CHANGE_SETTINGS";
      WinSqmAddToStream(0, 911, 1, &v5);
      v3 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v7 + 24LL))(v7, v2);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  SysFreeString(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017ba0  mov     r11, rsp
0x180017ba3  mov     [r11+8], rbx
0x180017ba7  mov     [r11+10h], rdx
0x180017bab  push    rdi
0x180017bac  sub     rsp, 40h
0x180017bb0  lea     rax, [r11+10h]
0x180017bb4  mov     qword ptr [r11+10h], 0
0x180017bbc  xor     ebx, ebx
0x180017bbe  mov     [r11-28h], rax
0x180017bc2  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180017bc9  xor     edx, edx; pUnkOuter
0x180017bcb  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180017bd2  lea     r8d, [rbx+17h]; dwClsContext
0x180017bd6  call    cs:__imp_CoCreateInstance
0x180017bdc  mov     edi, eax
0x180017bde  test    eax, eax
0x180017be0  js      short loc_180017C3E
0x180017be2  lea     rcx, psz; "mshelp://windows/?id=76f61616-6d12-46ec"...
0x180017be9  call    cs:__imp_SysAllocString
0x180017bef  mov     rbx, rax
0x180017bf2  test    rax, rax
0x180017bf5  jnz     short loc_180017BFE
0x180017bf7  mov     edi, 8007000Eh
0x180017bfc  jmp     short loc_180017C3E
0x180017bfe  xor     ecx, ecx
0x180017c00  mov     [rsp+48h+var_18], 2
0x180017c08  lea     rax, aHelpEntryIdCol; "HELP_ENTRY_ID_COLOR_MANAGEMENT_CHANGE_S"...
0x180017c0f  mov     edx, 38Fh
0x180017c14  lea     r9, [rsp+48h+var_18]
0x180017c19  mov     [rsp+48h+var_10], rax
0x180017c1e  lea     r8d, [rcx+1]
0x180017c22  call    cs:__imp_WinSqmAddToStream
0x180017c28  mov     rcx, [rsp+48h+arg_8]
0x180017c2d  mov     rdx, rbx
0x180017c30  mov     rax, [rcx]
0x180017c33  mov     rax, [rax+18h]
0x180017c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c3c  mov     edi, eax
0x180017c3e  mov     rcx, [rsp+48h+arg_8]
0x180017c43  test    rcx, rcx
0x180017c46  jz      short loc_180017C54
0x180017c48  mov     rax, [rcx]
0x180017c4b  mov     rax, [rax+10h]
0x180017c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c54  mov     rcx, rbx; bstrString
0x180017c57  call    cs:__imp_SysFreeString
0x180017c5d  mov     rbx, [rsp+48h+arg_0]
0x180017c62  mov     eax, edi
0x180017c64  add     rsp, 40h
0x180017c68  pop     rdi
0x180017c69  retn
```
