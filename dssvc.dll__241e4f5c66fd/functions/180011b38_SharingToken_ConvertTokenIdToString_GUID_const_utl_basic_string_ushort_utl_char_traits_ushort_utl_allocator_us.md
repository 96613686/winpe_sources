# SharingToken::ConvertTokenIdToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180011b38`
- end: `0x180011bd3`
- name: `?ConvertTokenIdToString@SharingToken@@SAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(const GUID *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f740`
- `0x180014050`

## callees

- `0x180006e54`
- `0x180006f78`
- `0x18000bf80`
- `0x180011b38`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011b61`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011b61`

## string_xrefs

- `0x180011ba5`: `SharingToken::ConvertTokenIdToString`

## pseudocode

```c
__int64 __fastcall SharingToken::ConvertTokenIdToString(const GUID *a1, _QWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  DSLogger *v8; // rax
  unsigned int v10; // [rsp+20h] [rbp-78h]
  OLECHAR sz; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v12[78]; // [rsp+32h] [rbp-66h] BYREF

  if ( StringFromGUID2(a1, &sz, 39) == 39 )
  {
    if ( utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
           a2,
           v12,
           36) )
    {
      return 0;
    }
    v7 = -2147024882;
  }
  else
  {
    v7 = -2147418113;
  }
  v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                     v4,
                     v3,
                     v5,
                     v6);
  v10 = v7;
  DSLogger::LogError(v8, L"SharingToken::ConvertTokenIdToString", 0x52u, L"hr=0x%x.", v10);
  return v7;
}

```

## disassembly

```asm
0x180011b38  push    rbx
0x180011b3a  sub     rsp, 90h
0x180011b41  mov     rax, cs:__security_cookie
0x180011b48  xor     rax, rsp
0x180011b4b  mov     [rsp+98h+var_18], rax
0x180011b53  mov     rbx, rdx
0x180011b56  mov     r8d, 27h ; '''; cchMax
0x180011b5c  lea     rdx, [rsp+98h+sz]; lpsz
0x180011b61  call    cs:__imp_StringFromGUID2
0x180011b67  cmp     eax, 27h ; '''
0x180011b6a  jz      short loc_180011B73
0x180011b6c  mov     ebx, 8000FFFFh
0x180011b71  jmp     short loc_180011B8F
0x180011b73  mov     r8d, 24h ; '$'
0x180011b79  lea     rdx, [rsp+98h+var_66]
0x180011b7e  mov     rcx, rbx
0x180011b81  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180011b86  test    al, al
0x180011b88  jnz     short loc_180011BB6
0x180011b8a  mov     ebx, 8007000Eh
0x180011b8f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180011b94  lea     r9, aHr0xX; "hr=0x%x."
0x180011b9b  mov     [rsp+98h+var_78], ebx
0x180011b9f  mov     r8d, 52h ; 'R'; unsigned int
0x180011ba5  lea     rdx, aSharingtokenCo; "SharingToken::ConvertTokenIdToString"
0x180011bac  mov     rcx, rax; this
0x180011baf  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180011bb4  jmp     short loc_180011BB8
0x180011bb6  xor     ebx, ebx
0x180011bb8  mov     eax, ebx
0x180011bba  mov     rcx, [rsp+98h+var_18]
0x180011bc2  xor     rcx, rsp; StackCookie
0x180011bc5  call    __security_check_cookie
0x180011bca  add     rsp, 90h
0x180011bd1  pop     rbx
0x180011bd2  retn
```
