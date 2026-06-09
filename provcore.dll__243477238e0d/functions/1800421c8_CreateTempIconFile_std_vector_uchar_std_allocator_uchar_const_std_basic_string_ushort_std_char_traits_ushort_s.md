# CreateTempIconFile(std::vector<uchar,std::allocator<uchar>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800421c8`
- end: `0x180042291`
- name: `?CreateTempIconFile@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `201`
- prototype: `__int64 __fastcall(const std::vector<unsigned char> *Payload, std::wstring *IconFilePath)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180042050`

## callees

- `0x180002790`
- `0x18000b0a0`
- `0x18000b8c0`
- `0x180011844`
- `0x180011cfc`
- `0x180012770`
- `0x180041050`
- `0x1800421c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042226`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042226`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateTempIconFile(const std::vector<unsigned char> *Payload, std::wstring *IconFilePath)
{
  const std::vector<unsigned char> *v3; // rdx
  int v4; // ebx
  const WCHAR *v5; // rax
  CreateTempIconFile::__l2::<lambda_1> f; // [rsp+20h] [rbp-48h] BYREF
  std::wstring iconPath; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring(&iconPath);
  f.iconPath = &iconPath;
  f.Payload = v3;
  v4 = ExecuteAndConvertAnyException__CreateTempIconFile_::_2_::_lambda_1___(&f);
  if ( v4 < 0 && iconPath._Mypair._Myval2._Mysize )
  {
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&iconPath._Mypair._Myval2);
    DeleteFileW(v5);
  }
  else
  {
    std::wstring::operator=(IconFilePath, &iconPath);
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x20u, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids, v4);
  }
  std::wstring::_Tidy_deallocate(&iconPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800421c8  mov     [rsp+arg_0], rbx
0x1800421cd  push    rdi
0x1800421ce  sub     rsp, 60h
0x1800421d2  mov     rax, cs:__security_cookie
0x1800421d9  xor     rax, rsp
0x1800421dc  mov     [rsp+68h+var_18], rax
0x1800421e1  mov     rdi, IconFilePath
0x1800421e4  mov     IconFilePath, Payload
0x1800421e7  lea     Payload, [rsp+68h+iconPath]; this
0x1800421ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800421f1  nop
0x1800421f2  lea     rax, [rsp+68h+iconPath]
0x1800421f7  mov     [rsp+68h+f.iconPath], rax
0x1800421fc  mov     [rsp+68h+f.Payload], IconFilePath
0x180042201  lea     Payload, [rsp+68h+f]; f
0x180042206  call    ExecuteAndConvertAnyException__CreateTempIconFile____2____lambda_1___
0x18004220b  mov     ebx, eax
0x18004220d  test    eax, eax
0x18004220f  jns     short loc_18004222E
0x180042211  cmp     [rsp+68h+iconPath._Mypair._Myval2._Mysize], 0
0x180042217  jz      short loc_18004222E
0x180042219  lea     Payload, [rsp+68h+iconPath]; this
0x18004221e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042223  mov     Payload, rax; lpFileName
0x180042226  call    cs:__imp_DeleteFileW
0x18004222c  jmp     short loc_18004223B
0x18004222e  lea     IconFilePath, [rsp+68h+iconPath]; _Right
0x180042233  mov     Payload, rdi; this
0x180042236  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004223b  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x180042242  mov     Payload, cs:WPP_GLOBAL_Control
0x180042249  cmp     Payload, rax
0x18004224c  jz      short loc_18004226D
0x18004224e  test    byte ptr [Payload+1Ch], 10h
0x180042252  jz      short loc_18004226D
0x180042254  mov     edx, 20h ; ' '; id
0x180042259  mov     r9d, ebx; _a1
0x18004225c  lea     r8, WPP_d34d1c7997823e4fca50ff7a96bed58c_Traceguids; TraceGuid
0x180042263  mov     Payload, [Payload+10h]; Logger
0x180042267  call    WPP_SF_d
0x18004226c  nop
0x18004226d  lea     Payload, [rsp+68h+iconPath]; this
0x180042272  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042277  mov     eax, ebx
0x180042279  mov     Payload, [rsp+68h+var_18]
0x18004227e  xor     Payload, rsp; StackCookie
0x180042281  call    __security_check_cookie
0x180042286  mov     rbx, [rsp+68h+arg_0]
0x18004228b  add     rsp, 60h
0x18004228f  pop     rdi
0x180042290  retn
```
