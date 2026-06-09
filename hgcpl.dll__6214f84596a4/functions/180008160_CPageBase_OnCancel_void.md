# CPageBase::OnCancel(void)

- ea: `0x180008160`
- end: `0x180008208`
- name: `?OnCancel@CPageBase@@UEAAXXZ`
- size: `168`
- prototype: `void __fastcall(CPageBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180008160`
- `0x18001a010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x1800081ae`
- `SHLWAPI!__imp_IUnknown_QueryServiceForWebBrowserApp` at `0x1800081ae`

## pseudocode

```c
void __fastcall CPageBase::OnCancel(CPageBase *this)
{
  __int64 v1; // rcx
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF
  __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 2) + 208LL;
  v3 = 0;
  if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v1 + 32LL))(
         v1,
         &GUID_00000000_0000_0000_c000_000000000046,
         &v3) >= 0 )
  {
    v2 = 0;
    if ( (int)IUnknown_QueryServiceForWebBrowserApp(v3, &GUID_0002df05_0000_0000_c000_000000000046, &v2) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2) < 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 256LL))(v2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x180008160  sub     rsp, 28h
0x180008164  mov     rcx, [rcx+10h]
0x180008168  lea     r8, [rsp+28h+arg_8]
0x18000816d  add     rcx, 0D0h
0x180008174  mov     [rsp+28h+arg_8], 0
0x18000817d  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180008184  mov     rax, [rcx]
0x180008187  mov     rax, [rax+20h]
0x18000818b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008190  test    eax, eax
0x180008192  js      short loc_180008203
0x180008194  mov     rcx, [rsp+28h+arg_8]
0x180008199  lea     r8, [rsp+28h+arg_0]
0x18000819e  lea     rdx, _GUID_0002df05_0000_0000_c000_000000000046
0x1800081a5  mov     [rsp+28h+arg_0], 0
0x1800081ae  call    cs:__imp_IUnknown_QueryServiceForWebBrowserApp
0x1800081b4  test    eax, eax
0x1800081b6  js      short loc_1800081F2
0x1800081b8  mov     rcx, [rsp+28h+arg_0]
0x1800081bd  mov     rax, [rcx]
0x1800081c0  mov     rax, [rax+38h]
0x1800081c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081c9  test    eax, eax
0x1800081cb  jns     short loc_1800081E1
0x1800081cd  mov     rcx, [rsp+28h+arg_0]
0x1800081d2  mov     rax, [rcx]
0x1800081d5  mov     rax, [rax+100h]
0x1800081dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081e1  mov     rcx, [rsp+28h+arg_0]
0x1800081e6  mov     rax, [rcx]
0x1800081e9  mov     rax, [rax+10h]
0x1800081ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081f2  mov     rcx, [rsp+28h+arg_8]
0x1800081f7  mov     rax, [rcx]
0x1800081fa  mov     rax, [rax+10h]
0x1800081fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008203  add     rsp, 28h
0x180008207  retn
```
