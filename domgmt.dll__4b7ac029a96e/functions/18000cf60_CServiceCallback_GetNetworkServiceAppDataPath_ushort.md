# CServiceCallback::GetNetworkServiceAppDataPath(ushort * *)

- ea: `0x18000cf60`
- end: `0x18000d019`
- name: `?GetNetworkServiceAppDataPath@CServiceCallback@@EEBAJPEAPEAG@Z`
- size: `185`
- prototype: `__int64 __fastcall(CServiceCallback *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180001ba0`
- `0x180005964`
- `0x1800080fc`
- `0x18000cf60`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000cfa0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000cfa0`

## string_xrefs

- `0x18000cfb9`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetNetworkServiceAppDataPath(CServiceCallback *this, unsigned __int16 **a2)
{
  int BasicProfileFolderPath; // ebx
  __int64 v4; // rdx
  unsigned __int16 *v6; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v7[528]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a2 = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(8, L"S-1-5-20", v7, 260);
  if ( BasicProfileFolderPath < 0 )
  {
    v4 = 121;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      (int)v6);
    return (unsigned int)BasicProfileFolderPath;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v6,
    v7,
    -1);
  if ( !v6 )
  {
    BasicProfileFolderPath = -2147024882;
    v4 = 124;
    goto LABEL_3;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x18000cf60  mov     [rsp+arg_0], rbx
0x18000cf65  push    rdi
0x18000cf66  sub     rsp, 250h
0x18000cf6d  mov     rax, cs:__security_cookie
0x18000cf74  xor     rax, rsp
0x18000cf77  mov     [rsp+258h+var_18], rax
0x18000cf7f  mov     rdi, rdx
0x18000cf82  mov     qword ptr [rdx], 0
0x18000cf89  lea     rdx, aS1520; "S-1-5-20"
0x18000cf90  mov     r9d, 104h
0x18000cf96  lea     r8, [rsp+258h+var_228]
0x18000cf9b  mov     ecx, 8
0x18000cfa0  call    cs:__imp_GetBasicProfileFolderPath
0x18000cfa6  mov     ebx, eax
0x18000cfa8  test    eax, eax
0x18000cfaa  jns     short loc_18000CFCC
0x18000cfac  mov     edx, 79h ; 'y'; void *
0x18000cfb1  mov     rcx, [rsp+258h]; this
0x18000cfb9  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x18000cfc0  mov     r9d, ebx; char *
0x18000cfc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cfc8  mov     eax, ebx
0x18000cfca  jmp     short loc_18000CFF8
0x18000cfcc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cfd0  lea     rdx, [rsp+258h+var_228]
0x18000cfd5  lea     rcx, [rsp+258h+var_238]
0x18000cfda  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000cfdf  mov     rax, [rsp+258h+var_238]
0x18000cfe4  test    rax, rax
0x18000cfe7  jnz     short loc_18000CFF3
0x18000cfe9  mov     ebx, 8007000Eh
0x18000cfee  lea     edx, [rax+7Ch]
0x18000cff1  jmp     short loc_18000CFB1
0x18000cff3  mov     [rdi], rax
0x18000cff6  xor     eax, eax
0x18000cff8  mov     rcx, [rsp+258h+var_18]
0x18000d000  xor     rcx, rsp; StackCookie
0x18000d003  call    __security_check_cookie
0x18000d008  mov     rbx, [rsp+258h+arg_0]
0x18000d010  add     rsp, 250h
0x18000d017  pop     rdi
0x18000d018  retn
```
