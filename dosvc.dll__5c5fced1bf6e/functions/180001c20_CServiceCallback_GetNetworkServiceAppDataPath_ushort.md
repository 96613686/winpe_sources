# CServiceCallback::GetNetworkServiceAppDataPath(ushort * *)

- ea: `0x180001c20`
- end: `0x180001cf8`
- name: `?GetNetworkServiceAppDataPath@CServiceCallback@@EEBAJPEAPEAG@Z`
- size: `216`
- prototype: `__int64 __fastcall(CServiceCallback *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180001c20`
- `0x180001d00`
- `0x180003290`
- `0x180005020`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180001c60`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180001c60`

## string_xrefs

- `0x180001c74`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`
- `0x180001cb4`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetNetworkServiceAppDataPath(CServiceCallback *this, unsigned __int16 **a2)
{
  int BasicProfileFolderPath; // eax
  unsigned int v4; // ebx
  unsigned __int16 *v6; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v7[528]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a2 = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(8, L"S-1-5-20", v7, 260);
  v4 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath >= 0 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v6,
      v7,
      -1);
    if ( v6 )
    {
      *a2 = v6;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
        (const char *)0x8007000ELL,
        0);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      (int)v6);
    return v4;
  }
}

```

## disassembly

```asm
0x180001c20  mov     [rsp+arg_0], rbx
0x180001c25  push    rdi
0x180001c26  sub     rsp, 250h
0x180001c2d  mov     rax, cs:__security_cookie
0x180001c34  xor     rax, rsp
0x180001c37  mov     [rsp+258h+var_18], rax
0x180001c3f  mov     rdi, rdx
0x180001c42  mov     qword ptr [rdx], 0
0x180001c49  lea     rdx, aS1520; "S-1-5-20"
0x180001c50  mov     r9d, 104h
0x180001c56  lea     r8, [rsp+258h+var_228]
0x180001c5b  mov     ecx, 8
0x180001c60  call    cs:__imp_GetBasicProfileFolderPath
0x180001c66  mov     ebx, eax
0x180001c68  test    eax, eax
0x180001c6a  jns     short loc_180001C8C
0x180001c6c  mov     rcx, [rsp+258h]; this
0x180001c74  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180001c7b  mov     r9d, eax; char *
0x180001c7e  mov     edx, 79h ; 'y'; void *
0x180001c83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001c88  mov     eax, ebx
0x180001c8a  jmp     short loc_180001CD7
0x180001c8c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180001c93  lea     rdx, [rsp+258h+var_228]
0x180001c98  lea     rcx, [rsp+258h+var_238]
0x180001c9d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180001ca2  mov     rax, [rsp+258h+var_238]
0x180001ca7  test    rax, rax
0x180001caa  jnz     short loc_180001CD2
0x180001cac  mov     rcx, [rsp+258h]; this
0x180001cb4  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x180001cbb  mov     r9d, 8007000Eh; char *
0x180001cc1  mov     edx, 7Ch ; '|'; void *
0x180001cc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001ccb  mov     eax, 8007000Eh
0x180001cd0  jmp     short loc_180001CD7
0x180001cd2  mov     [rdi], rax
0x180001cd5  xor     eax, eax
0x180001cd7  mov     rcx, [rsp+258h+var_18]
0x180001cdf  xor     rcx, rsp; StackCookie
0x180001ce2  call    __security_check_cookie
0x180001ce7  mov     rbx, [rsp+258h+arg_0]
0x180001cef  add     rsp, 250h
0x180001cf6  pop     rdi
0x180001cf7  retn
```
