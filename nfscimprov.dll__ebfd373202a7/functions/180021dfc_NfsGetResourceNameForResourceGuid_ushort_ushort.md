# NfsGetResourceNameForResourceGuid(ushort *,ushort * *)

- ea: `0x180021dfc`
- end: `0x180021f77`
- name: `?NfsGetResourceNameForResourceGuid@@YAKPEAGPEAPEAG@Z`
- size: `379`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180019818`

## callees

- `0x1800096cc`
- `0x180009704`
- `0x18000990c`
- `0x18000eae4`
- `0x18000eeb4`
- `0x18000ef38`
- `0x18000f454`
- `0x180021dfc`
- `0x180029894`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180021e5a`
- `KERNEL32!GetLastError` at `0x180021edf`
- `KERNEL32!GetLastError` at `0x180021e5a`
- `KERNEL32!GetLastError` at `0x180021edf`
- `KERNEL32!LocalFree` at `0x180021f11`
- `KERNEL32!LocalFree` at `0x180021f11`
- `CLUSAPI!CloseCluster` at `0x180021f2d`
- `CLUSAPI!CloseCluster` at `0x180021f2d`
- `CLUSAPI!OpenClusterResource` at `0x180021ed1`
- `CLUSAPI!OpenClusterResource` at `0x180021ed1`
- `CLUSAPI!OpenCluster` at `0x180021e4c`
- `CLUSAPI!OpenCluster` at `0x180021e4c`
- `CLUSAPI!CloseClusterResource` at `0x180021f1f`
- `CLUSAPI!CloseClusterResource` at `0x180021f1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NfsGetResourceNameForResourceGuid(unsigned __int16 *a1, unsigned __int16 **a2)
{
  struct _HCLUSTER *v3; // rsi
  __int64 v4; // rdx
  DWORD ResourceName; // ebx
  unsigned __int64 last_of; // rax
  __int64 v7; // r11
  __int64 v8; // rax
  __int64 v9; // rdx
  const WCHAR *v10; // rdx
  struct _HRESOURCE *v11; // rdi
  __int64 v12; // rdx
  LPCWSTR lpszResourceName[4]; // [rsp+28h] [rbp-21h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp+1Fh] BYREF

  std::wstring::wstring(v15, a1);
  std::wstring::wstring(lpszResourceName, v15);
  v3 = OpenCluster(0);
  if ( v3 || (ResourceName = GetLastError()) == 0 )
  {
    if ( std::wstring::find_first_of(v15) != -1 )
    {
      last_of = std::wstring::find_last_of(v15);
      if ( last_of != -1 && last_of > 1 )
      {
        v8 = std::wstring::substr(v15, v16, v7 + 1, last_of - 1);
        std::wstring::operator=(lpszResourceName, v8);
        LOBYTE(v9) = 1;
        std::wstring::_Tidy(v16, v9, 0);
      }
    }
    v10 = (const WCHAR *)lpszResourceName;
    if ( lpszResourceName[3] >= (LPCWSTR)8 )
      v10 = lpszResourceName[0];
    v11 = OpenClusterResource(v3, v10);
    if ( v11 || (ResourceName = GetLastError()) == 0 )
    {
      ResourceName = GetResourceName(v11);
      if ( !ResourceName )
        *a2 = 0;
      if ( v11 )
        CloseClusterResource(v11);
    }
    if ( v3 )
      CloseCluster(v3);
  }
  LOBYTE(v4) = 1;
  std::wstring::_Tidy(lpszResourceName, v4, 0);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v15, v12, 0);
  return ResourceName;
}

```

## disassembly

```asm
0x180021dfc  mov     [rsp-8+arg_10], rbx
0x180021e01  mov     [rsp-8+arg_18], rsi
0x180021e06  push    rbp
0x180021e07  push    rdi
0x180021e08  push    r14
0x180021e0a  lea     rbp, [rsp-47h]
0x180021e0f  sub     rsp, 90h
0x180021e16  mov     rax, cs:__security_cookie
0x180021e1d  xor     rax, rsp
0x180021e20  mov     [rbp+57h+var_18], rax
0x180021e24  mov     r14, rdx
0x180021e27  mov     [rbp+57h+hMem], 0
0x180021e2f  mov     rdx, rcx
0x180021e32  lea     rcx, [rbp+57h+var_58]
0x180021e36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180021e3b  nop
0x180021e3c  lea     rdx, [rbp+57h+var_58]
0x180021e40  lea     rcx, [rbp+57h+lpszResourceName]
0x180021e44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180021e49  nop
0x180021e4a  xor     ecx, ecx; lpszClusterName
0x180021e4c  call    cs:__imp_OpenCluster
0x180021e52  mov     rsi, rax
0x180021e55  test    rax, rax
0x180021e58  jnz     short loc_180021E6A
0x180021e5a  call    cs:__imp_GetLastError
0x180021e60  mov     ebx, eax
0x180021e62  test    eax, eax
0x180021e64  jnz     loc_180021F34
0x180021e6a  lea     rcx, [rbp+57h+var_58]
0x180021e6e  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_first_of(ushort const *,unsigned __int64)
0x180021e73  mov     r11, rax
0x180021e76  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021e7a  jz      short loc_180021EC0
0x180021e7c  lea     rcx, [rbp+57h+var_58]
0x180021e80  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find_last_of(ushort const *,unsigned __int64)
0x180021e85  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021e89  jz      short loc_180021EC0
0x180021e8b  cmp     rax, 1
0x180021e8f  jbe     short loc_180021EC0
0x180021e91  lea     r9, [rax-1]
0x180021e95  lea     r8, [r11+1]
0x180021e99  lea     rdx, [rbp+57h+var_38]
0x180021e9d  lea     rcx, [rbp+57h+var_58]
0x180021ea1  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180021ea6  mov     rdx, rax
0x180021ea9  lea     rcx, [rbp+57h+lpszResourceName]
0x180021ead  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180021eb2  xor     r8d, r8d
0x180021eb5  mov     dl, 1
0x180021eb7  lea     rcx, [rbp+57h+var_38]
0x180021ebb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180021ec0  lea     rdx, [rbp+57h+lpszResourceName]
0x180021ec4  cmp     [rbp+57h+var_60], 8
0x180021ec9  cmovnb  rdx, [rbp+57h+lpszResourceName]; lpszResourceName
0x180021ece  mov     rcx, rsi; hCluster
0x180021ed1  call    cs:__imp_OpenClusterResource
0x180021ed7  mov     rdi, rax
0x180021eda  test    rax, rax
0x180021edd  jnz     short loc_180021EEB
0x180021edf  call    cs:__imp_GetLastError
0x180021ee5  mov     ebx, eax
0x180021ee7  test    eax, eax
0x180021ee9  jnz     short loc_180021F25
0x180021eeb  lea     rdx, [rbp+57h+hMem]
0x180021eef  mov     rcx, rdi; hResource
0x180021ef2  call    GetResourceName
0x180021ef7  mov     ebx, eax
0x180021ef9  test    eax, eax
0x180021efb  jnz     short loc_180021F08
0x180021efd  mov     rax, [rbp+57h+hMem]
0x180021f01  mov     [r14], rax
0x180021f04  xor     ecx, ecx
0x180021f06  jmp     short loc_180021F0C
0x180021f08  mov     rcx, [rbp+57h+hMem]; hMem
0x180021f0c  test    rcx, rcx
0x180021f0f  jz      short loc_180021F17
0x180021f11  call    cs:__imp_LocalFree
0x180021f17  test    rdi, rdi
0x180021f1a  jz      short loc_180021F25
0x180021f1c  mov     rcx, rdi; hResource
0x180021f1f  call    cs:__imp_CloseClusterResource
0x180021f25  test    rsi, rsi
0x180021f28  jz      short loc_180021F34
0x180021f2a  mov     rcx, rsi; hCluster
0x180021f2d  call    cs:__imp_CloseCluster
0x180021f33  nop
0x180021f34  xor     r8d, r8d
0x180021f37  mov     dl, 1
0x180021f39  lea     rcx, [rbp+57h+lpszResourceName]
0x180021f3d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180021f42  nop
0x180021f43  xor     r8d, r8d
0x180021f46  mov     dl, 1
0x180021f48  lea     rcx, [rbp+57h+var_58]
0x180021f4c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180021f51  mov     eax, ebx
0x180021f53  mov     rcx, [rbp+57h+var_18]
0x180021f57  xor     rcx, rsp; StackCookie
0x180021f5a  call    __security_check_cookie
0x180021f5f  lea     r11, [rsp+0A0h+var_10]
0x180021f67  mov     rbx, [r11+30h]
0x180021f6b  mov     rsi, [r11+38h]
0x180021f6f  mov     rsp, r11
0x180021f72  pop     r14
0x180021f74  pop     rdi
0x180021f75  pop     rbp
0x180021f76  retn
```
