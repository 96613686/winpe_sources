# CloudExperienceHostAPI::OobeXmlAdapter::TryGetString(HSTRING__ *,HSTRING__ * *,uchar *)

- ea: `0x1800573b0`
- end: `0x180057478`
- name: `?TryGetString@OobeXmlAdapter@CloudExperienceHostAPI@@UEAAJPEAUHSTRING__@@PEAPEAU3@PEAE@Z`
- size: `200`
- prototype: `int(CloudExperienceHostAPI::OobeXmlAdapter *__hidden this, HSTRING, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180009814`
- `0x18000b200`
- `0x1800573b0`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180057424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180057424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800573ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800573ec`

## string_xrefs

- `0x18005744d`: `shellcommon\shell\oobe\core\components\winrt\oobexml.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudExperienceHostAPI::OobeXmlAdapter::TryGetString(
        CloudExperienceHostAPI::OobeXmlAdapter *this,
        HSTRING a2,
        HSTRING *a3,
        unsigned __int8 *a4)
{
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, PCWSTR, PCNZWCH *); // rbx
  PCWSTR StringRawBuffer; // rax
  HRESULT String; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  PCNZWCH sourceString; // [rsp+60h] [rbp+8h] BYREF

  *a3 = 0;
  sourceString = 0;
  v7 = *((_QWORD *)this + 8);
  v8 = *(__int64 (__fastcall **)(__int64, PCWSTR, PCNZWCH *))(*(_QWORD *)v7 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &sourceString,
    0);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  String = v8(v7, StringRawBuffer, &sourceString);
  v11 = String;
  if ( String < 0 )
  {
    if ( String != -2147023728 )
    {
      v13 = 70;
      goto LABEL_10;
    }
    *a4 = 0;
  }
  else
  {
    *a4 = 1;
    v12 = -1;
    do
      ++v12;
    while ( sourceString[v12] );
    String = WindowsCreateString(sourceString, v12, a3);
    v11 = String;
    if ( String < 0 )
    {
      v13 = 60;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobexml.cpp",
        (const char *)(unsigned int)String,
        v15);
      goto LABEL_11;
    }
  }
  v11 = 0;
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
  return v11;
}

```

## disassembly

```asm
0x1800573b0  push    rbx
0x1800573b2  push    rbp
0x1800573b3  push    rsi
0x1800573b4  push    rdi
0x1800573b5  push    r14
0x1800573b7  push    r15
0x1800573b9  sub     rsp, 28h
0x1800573bd  mov     r14, r9
0x1800573c0  mov     r15, r8
0x1800573c3  mov     rsi, rdx
0x1800573c6  xor     ebp, ebp
0x1800573c8  mov     [r8], rbp
0x1800573cb  mov     [rsp+58h+sourceString], rbp
0x1800573d0  mov     rdi, [rcx+40h]
0x1800573d4  mov     rax, [rdi]
0x1800573d7  mov     rbx, [rax+28h]
0x1800573db  xor     edx, edx
0x1800573dd  lea     rcx, [rsp+58h+sourceString]
0x1800573e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800573e7  xor     edx, edx; length
0x1800573e9  mov     rcx, rsi; string
0x1800573ec  call    cs:__imp_WindowsGetStringRawBuffer
0x1800573f2  lea     r8, [rsp+58h+sourceString]
0x1800573f7  mov     rdx, rax
0x1800573fa  mov     rcx, rdi
0x1800573fd  mov     rax, rbx
0x180057400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057405  mov     ebx, eax
0x180057407  test    eax, eax
0x180057409  js      short loc_180057437
0x18005740b  mov     byte ptr [r14], 1
0x18005740f  mov     rcx, [rsp+58h+sourceString]; sourceString
0x180057414  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180057418  inc     rdx; length
0x18005741b  cmp     [rcx+rdx*2], bp
0x18005741f  jnz     short loc_180057418
0x180057421  mov     r8, r15; string
0x180057424  call    cs:__imp_WindowsCreateString
0x18005742a  mov     ebx, eax
0x18005742c  test    eax, eax
0x18005742e  jns     short loc_180057441
0x180057430  mov     edx, 3Ch ; '<'
0x180057435  jmp     short loc_18005744A
0x180057437  cmp     eax, 80070490h
0x18005743c  jnz     short loc_180057445
0x18005743e  mov     [r14], bpl
0x180057441  mov     ebx, ebp
0x180057443  jmp     short loc_18005745F
0x180057445  mov     edx, 46h ; 'F'; void *
0x18005744a  mov     r9d, eax; char *
0x18005744d  lea     r8, aShellcommonShe_20; "shellcommon\\shell\\oobe\\core\\compone"...
0x180057454  mov     rcx, [rsp+58h]; this
0x180057459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005745e  nop
0x18005745f  lea     rcx, [rsp+58h+sourceString]
0x180057464  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057469  mov     eax, ebx
0x18005746b  add     rsp, 28h
0x18005746f  pop     r15
0x180057471  pop     r14
0x180057473  pop     rdi
0x180057474  pop     rsi
0x180057475  pop     rbp
0x180057476  pop     rbx
0x180057477  retn
```
