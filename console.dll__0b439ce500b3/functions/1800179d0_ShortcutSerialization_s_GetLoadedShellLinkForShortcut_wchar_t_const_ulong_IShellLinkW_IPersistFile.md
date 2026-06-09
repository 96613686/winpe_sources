# ShortcutSerialization::s_GetLoadedShellLinkForShortcut(wchar_t const *,ulong,IShellLinkW * *,IPersistFile * *)

- ea: `0x1800179d0`
- end: `0x180017b0f`
- name: `?s_GetLoadedShellLinkForShortcut@ShortcutSerialization@@CAJPEB_WKPEAPEAUIShellLinkW@@PEAPEAUIPersistFile@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, struct IShellLinkW **, struct IPersistFile **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800178fc`
- `0x1800180bc`

## callees

- `0x1800179d0`
- `0x18001a010`

## import_xrefs

- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180017a1f`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180017a1f`

## pseudocode

```c
__int64 __fastcall ShortcutSerialization::s_GetLoadedShellLinkForShortcut(
        const wchar_t *a1,
        unsigned int a2,
        struct IShellLinkW **a3,
        struct IPersistFile **a4)
{
  HRESULT v8; // ebx
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF
  void *v11; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  *a4 = 0;
  v11 = 0;
  v8 = SHCoCreateInstance(0, &CLSID_ShellLink, 0, &GUID_000214f9_0000_0000_c000_000000000046, &v11);
  if ( v8 >= 0 )
  {
    v10 = 0;
    v8 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v11)(
           v11,
           &GUID_0000010b_0000_0000_c000_000000000046,
           &v10);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v10 + 40LL))(v10, a1, a2);
      if ( v8 >= 0 )
      {
        v8 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IShellLinkW **))v11)(
               v11,
               &GUID_000214f9_0000_0000_c000_000000000046,
               a3);
        if ( v8 >= 0 )
        {
          v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IPersistFile **))v10)(
                 v10,
                 &GUID_0000010b_0000_0000_c000_000000000046,
                 a4);
          if ( v8 < 0 )
          {
            ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
            *a3 = 0;
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800179d0  mov     r11, rsp
0x1800179d3  mov     [r11+8], rbx
0x1800179d7  mov     [r11+10h], rbp
0x1800179db  push    rsi
0x1800179dc  push    rdi
0x1800179dd  push    r14
0x1800179df  sub     rsp, 30h
0x1800179e3  mov     qword ptr [r8], 0
0x1800179ea  lea     rax, [r11+20h]
0x1800179ee  mov     qword ptr [r9], 0
0x1800179f5  mov     rsi, r9
0x1800179f8  mov     rdi, r8
0x1800179fb  mov     qword ptr [r11+20h], 0
0x180017a03  mov     ebp, edx
0x180017a05  mov     [r11-28h], rax
0x180017a09  mov     r14, rcx
0x180017a0c  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x180017a13  xor     r8d, r8d; pUnkOuter
0x180017a16  lea     rdx, CLSID_ShellLink; pclsid
0x180017a1d  xor     ecx, ecx; pszCLSID
0x180017a1f  call    cs:__imp_SHCoCreateInstance
0x180017a26  nop     dword ptr [rax+rax+00h]
0x180017a2b  mov     ebx, eax
0x180017a2d  test    eax, eax
0x180017a2f  js      loc_180017AF9
0x180017a35  mov     rcx, [rsp+48h+arg_18]
0x180017a3a  lea     r8, [rsp+48h+arg_10]
0x180017a3f  mov     [rsp+48h+arg_10], 0
0x180017a48  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180017a4f  mov     rax, [rcx]
0x180017a52  mov     rax, [rax]
0x180017a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a5a  mov     ebx, eax
0x180017a5c  test    eax, eax
0x180017a5e  js      loc_180017AE8
0x180017a64  mov     rcx, [rsp+48h+arg_10]
0x180017a69  mov     r8d, ebp
0x180017a6c  mov     rdx, r14
0x180017a6f  mov     rax, [rcx]
0x180017a72  mov     rax, [rax+28h]
0x180017a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a7b  mov     ebx, eax
0x180017a7d  test    eax, eax
0x180017a7f  js      short loc_180017AD7
0x180017a81  mov     rcx, [rsp+48h+arg_18]
0x180017a86  lea     rdx, _GUID_000214f9_0000_0000_c000_000000000046
0x180017a8d  mov     r8, rdi
0x180017a90  mov     rax, [rcx]
0x180017a93  mov     rax, [rax]
0x180017a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a9b  mov     ebx, eax
0x180017a9d  test    eax, eax
0x180017a9f  js      short loc_180017AD7
0x180017aa1  mov     rcx, [rsp+48h+arg_10]
0x180017aa6  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180017aad  mov     r8, rsi
0x180017ab0  mov     rax, [rcx]
0x180017ab3  mov     rax, [rax]
0x180017ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017abb  mov     ebx, eax
0x180017abd  test    eax, eax
0x180017abf  jns     short loc_180017AD7
0x180017ac1  mov     rcx, [rdi]
0x180017ac4  mov     rax, [rcx]
0x180017ac7  mov     rax, [rax+10h]
0x180017acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad0  mov     qword ptr [rdi], 0
0x180017ad7  mov     rcx, [rsp+48h+arg_10]
0x180017adc  mov     rax, [rcx]
0x180017adf  mov     rax, [rax+10h]
0x180017ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ae8  mov     rcx, [rsp+48h+arg_18]
0x180017aed  mov     rax, [rcx]
0x180017af0  mov     rax, [rax+10h]
0x180017af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017af9  mov     rbp, [rsp+48h+arg_8]
0x180017afe  mov     eax, ebx
0x180017b00  mov     rbx, [rsp+48h+arg_0]
0x180017b05  add     rsp, 30h
0x180017b09  pop     r14
0x180017b0b  pop     rdi
0x180017b0c  pop     rsi
0x180017b0d  retn
```
