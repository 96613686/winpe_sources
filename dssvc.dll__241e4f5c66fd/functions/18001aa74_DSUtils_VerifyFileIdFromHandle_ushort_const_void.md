# DSUtils::VerifyFileIdFromHandle(ushort const *,void *)

- ea: `0x18001aa74`
- end: `0x18001ab00`
- name: `?VerifyFileIdFromHandle@DSUtils@@YAJPEBGPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(wchar_t *String2, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ca4c`
- `0x18000d3e4`

## callees

- `0x1800041a0`
- `0x180006cb0`
- `0x180006f78`
- `0x18000bf80`
- `0x18001a1e8`
- `0x18001aa74`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001aaaa`
- `msvcrt!_wcsicmp` at `0x18001aaaa`

## string_xrefs

- `0x18001aac8`: `VerifyFileIdFromHandle: File Id in the shared token %s is different from the file Id in handle %s`

## pseudocode

```c
__int64 __fastcall DSUtils::VerifyFileIdFromHandle(wchar_t *String2, const unsigned __int16 *a2, void *a3)
{
  HANDLE v4; // r8
  int FileIdFromHandle; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  DSLogger *v10; // rax
  wchar_t *String1[5]; // [rsp+30h] [rbp-28h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(String1);
  FileIdFromHandle = DSUtils::GetFileIdFromHandle(v4, (__int64)String1, (__int64)v4);
  if ( FileIdFromHandle >= 0 && _wcsicmp(String1[0], String2) )
  {
    v10 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v7,
                        v6,
                        v8,
                        v9);
    DSLogger::LogError(
      v10,
      L"DSUtils::VerifyFileIdFromHandle",
      0x1D8u,
      L"VerifyFileIdFromHandle: File Id in the shared token %s is different from the file Id in handle %s",
      String2,
      String1[0]);
    FileIdFromHandle = -1055719411;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(String1);
  return (unsigned int)FileIdFromHandle;
}

```

## disassembly

```asm
0x18001aa74  mov     [rsp+arg_0], rbx
0x18001aa79  push    rdi
0x18001aa7a  sub     rsp, 50h
0x18001aa7e  mov     r8, rdx
0x18001aa81  mov     rdi, rcx
0x18001aa84  lea     rcx, [rsp+58h+String1]
0x18001aa89  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001aa8e  nop
0x18001aa8f  lea     rdx, [rsp+58h+String1]
0x18001aa94  mov     rcx, r8; hFile
0x18001aa97  call    ?GetFileIdFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFileIdFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x18001aa9c  mov     ebx, eax
0x18001aa9e  test    eax, eax
0x18001aaa0  js      short loc_18001AAE9
0x18001aaa2  mov     rdx, rdi; String2
0x18001aaa5  mov     rcx, [rsp+58h+String1]; String1
0x18001aaaa  call    cs:__imp__wcsicmp
0x18001aab0  test    eax, eax
0x18001aab2  jz      short loc_18001AAE9
0x18001aab4  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001aab9  mov     rcx, [rsp+58h+String1]
0x18001aabe  mov     [rsp+58h+var_30], rcx
0x18001aac3  mov     [rsp+58h+var_38], rdi
0x18001aac8  lea     r9, aVerifyfileidfr; "VerifyFileIdFromHandle: File Id in the "...
0x18001aacf  mov     r8d, 1D8h; unsigned int
0x18001aad5  lea     rdx, aDsutilsVerifyf; "DSUtils::VerifyFileIdFromHandle"
0x18001aadc  mov     rcx, rax; this
0x18001aadf  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001aae4  mov     ebx, 0C113000Dh
0x18001aae9  lea     rcx, [rsp+58h+String1]
0x18001aaee  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001aaf3  mov     eax, ebx
0x18001aaf5  mov     rbx, [rsp+58h+arg_0]
0x18001aafa  add     rsp, 50h
0x18001aafe  pop     rdi
0x18001aaff  retn
```
