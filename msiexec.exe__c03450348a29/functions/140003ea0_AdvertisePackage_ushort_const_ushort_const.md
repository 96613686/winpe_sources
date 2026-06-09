# AdvertisePackage(ushort const *,ushort const *)

- ea: `0x140003ea0`
- end: `0x140003ff3`
- name: `?AdvertisePackage@@YAHPEBG0@Z`
- size: `339`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140003ea0`
- `0x140003ffc`
- `0x140009820`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140003f9b`
- `KERNEL32!GlobalFree` at `0x140003f9b`
- `msi!__imp_MsiSetInternalUI` at `0x140003ee0`
- `msi!__imp_MsiSetInternalUI` at `0x140003ee0`
- `msi!__imp_MsiAdvertiseProductExW` at `0x140003f2c`
- `msi!__imp_MsiAdvertiseProductExW` at `0x140003f84`
- `msi!__imp_MsiAdvertiseProductExW` at `0x140003f2c`
- `msi!__imp_MsiAdvertiseProductExW` at `0x140003f84`

## pseudocode

```c
__int64 __fastcall AdvertisePackage(const unsigned __int16 *a1, WCHAR *a2)
{
  INSTALLUILEVEL v3; // ecx
  __int16 v5; // ax
  __int64 v6; // rdi
  DWORD dwOptions; // esi
  UINT v8; // ebx
  WCHAR v10[264]; // [rsp+40h] [rbp-238h] BYREF

  v3 = g_INSTALLUILEVEL;
  if ( g_INSTALLUILEVEL == -1 )
    v3 = INSTALLUILEVEL_BASIC;
  MsiSetInternalUI(v3, 0);
  v5 = *a1 | 0x20;
  if ( v5 == 117 )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( *a1 && v5 != 109 )
      return 87;
  }
  dwOptions = g_fAdvertiseNewInstance;
  v8 = MsiAdvertiseProductExW(a2, (LPCWSTR)v6, g_szTransforms, g_iLanguage, 0, dwOptions);
  if ( v8 == 2 && (unsigned int)AppendExtension(a2) )
    v8 = MsiAdvertiseProductExW(v10, (LPCWSTR)v6, g_szTransforms, g_iLanguage, 0, dwOptions);
  if ( !v8 )
    return 0x8000;
  return v8;
}

```

## disassembly

```asm
0x140003ea0  mov     [rsp+arg_0], rbx
0x140003ea5  mov     [rsp+arg_10], rbp
0x140003eaa  push    rsi
0x140003eab  push    rdi
0x140003eac  push    r14
0x140003eae  sub     rsp, 260h
0x140003eb5  mov     rax, cs:__security_cookie
0x140003ebc  xor     rax, rsp
0x140003ebf  mov     [rsp+278h+var_28], rax
0x140003ec7  mov     rbx, rcx
0x140003eca  mov     eax, 3
0x140003ecf  mov     ecx, cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x140003ed5  mov     rbp, rdx
0x140003ed8  cmp     ecx, 0FFFFFFFFh
0x140003edb  cmovz   ecx, eax; dwUILevel
0x140003ede  xor     edx, edx; phWnd
0x140003ee0  call    cs:__imp_MsiSetInternalUI
0x140003ee6  movzx   eax, word ptr [rbx]
0x140003ee9  xor     r14d, r14d
0x140003eec  or      ax, 20h
0x140003ef0  mov     ecx, 1
0x140003ef5  cmp     ax, 75h ; 'u'
0x140003ef9  jnz     loc_140003FD5
0x140003eff  mov     edi, ecx
0x140003f01  cmp     cs:?g_fAdvertiseNewInstance@@3_NA, r14b; bool g_fAdvertiseNewInstance
0x140003f08  mov     esi, r14d
0x140003f0b  movzx   r9d, word ptr cs:?g_iLanguage@@3HA; lgidLanguage
0x140003f13  mov     rdx, rdi; szScriptfilePath
0x140003f16  mov     r8, cs:?g_szTransforms@@3V?$CAPITempBuffer@G$0EAA@@@A; szTransforms
0x140003f1d  cmovnz  esi, ecx
0x140003f20  mov     [rsp+278h+dwOptions], esi; dwOptions
0x140003f24  mov     rcx, rbp; szPackagePath
0x140003f27  mov     [rsp+278h+dwPlatform], r14d; dwPlatform
0x140003f2c  call    cs:__imp_MsiAdvertiseProductExW
0x140003f32  mov     ebx, eax
0x140003f34  cmp     eax, 2
0x140003f37  jnz     short loc_140003FA1
0x140003f39  lea     rax, [rsp+278h+var_238]
0x140003f3e  mov     [rsp+278h+var_240], 104h
0x140003f46  lea     r8, [rsp+278h+szPackagePath]
0x140003f4b  mov     [rsp+278h+szPackagePath], rax
0x140003f50  mov     rcx, rbp; unsigned __int16 *
0x140003f53  mov     [rsp+278h+var_23C], 104h
0x140003f5b  call    ?AppendExtension@@YA?AW4Bool@@PEBG0AEAV?$CAPITempBufferRef@G@@@Z; AppendExtension(ushort const *,ushort const *,CAPITempBufferRef<ushort> &)
0x140003f60  test    eax, eax
0x140003f62  jz      short loc_140003F8C
0x140003f64  movzx   r9d, word ptr cs:?g_iLanguage@@3HA; lgidLanguage
0x140003f6c  mov     rdx, rdi; szScriptfilePath
0x140003f6f  mov     r8, cs:?g_szTransforms@@3V?$CAPITempBuffer@G$0EAA@@@A; szTransforms
0x140003f76  mov     rcx, [rsp+278h+szPackagePath]; szPackagePath
0x140003f7b  mov     [rsp+278h+dwOptions], esi; dwOptions
0x140003f7f  mov     [rsp+278h+dwPlatform], r14d; dwPlatform
0x140003f84  call    cs:__imp_MsiAdvertiseProductExW
0x140003f8a  mov     ebx, eax
0x140003f8c  cmp     [rsp+278h+var_240], 104h
0x140003f94  jle     short loc_140003FA1
0x140003f96  mov     rcx, [rsp+278h+szPackagePath]; hMem
0x140003f9b  call    cs:__imp_GlobalFree
0x140003fa1  mov     eax, 8000h
0x140003fa6  test    ebx, ebx
0x140003fa8  cmovz   ebx, eax
0x140003fab  mov     eax, ebx
0x140003fad  mov     rcx, [rsp+278h+var_28]
0x140003fb5  xor     rcx, rsp; StackCookie
0x140003fb8  call    __security_check_cookie
0x140003fbd  lea     r11, [rsp+278h+var_18]
0x140003fc5  mov     rbx, [r11+20h]
0x140003fc9  mov     rbp, [r11+30h]
0x140003fcd  mov     rsp, r11
0x140003fd0  pop     r14
0x140003fd2  pop     rdi
0x140003fd3  pop     rsi
0x140003fd4  retn
0x140003fd5  mov     rdi, r14
0x140003fd8  cmp     [rbx], r14w
0x140003fdc  jz      loc_140003F01
0x140003fe2  cmp     ax, 6Dh ; 'm'
0x140003fe6  jz      loc_140003F01
0x140003fec  mov     eax, 57h ; 'W'
0x140003ff1  jmp     short loc_140003FAD
```
