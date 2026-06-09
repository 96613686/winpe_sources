# CServiceCallback::GetAppInstallPath(ushort * *)

- ea: `0x18000cc90`
- end: `0x18000ce0f`
- name: `?GetAppInstallPath@CServiceCallback@@EEBAJPEAPEAG@Z`
- size: `383`
- prototype: `__int64 __fastcall(CServiceCallback *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180001ba0`
- `0x18000296c`
- `0x180002de0`
- `0x180005964`
- `0x1800080fc`
- `0x18000cc90`

## import_xrefs

- `ext-ms-win-storage-sense-l1-1-0!GetStorageSettings` at `0x18000cd36`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageSettings` at `0x18000cd36`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18000cd82`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x18000cd82`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCount` at `0x18000cce7`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCount` at `0x18000cce7`

## string_xrefs

- `0x18000ccff`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetAppInstallPath(CServiceCallback *this, unsigned __int16 **a2)
{
  int StorageInstanceCount; // ebx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v9; // [rsp+28h] [rbp-D8h] BYREF
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v11[524]; // [rsp+34h] [rbp-CCh] BYREF
  int v12; // [rsp+240h] [rbp+140h]
  int v13; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  *a2 = 0;
  if ( !(unsigned __int8)IsGetStorageInstanceCountPresent(this) )
    return 2147500033LL;
  v8 = 0;
  StorageInstanceCount = GetStorageInstanceCount(0, &v8);
  if ( StorageInstanceCount < 0 )
  {
    v5 = 48;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)(unsigned int)StorageInstanceCount,
      v8);
    return (unsigned int)StorageInstanceCount;
  }
  v6 = v8;
  v7 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      LODWORD(v9) = 0;
      if ( (int)GetStorageSettings(0, v7, 2, &v9) >= 0 && ((unsigned __int8)v9 & 0x10) != 0 )
        break;
      v6 = v8;
      if ( ++v7 >= v8 )
        goto LABEL_12;
    }
    v6 = v8;
  }
LABEL_12:
  if ( v7 == v6 )
    return 2147943568LL;
  memset_0(v11, 0, 0x454u);
  v10 = 1112;
  StorageInstanceCount = GetStorageDeviceInfo(0, v7, &v10);
  if ( StorageInstanceCount < 0 )
  {
    v5 = 66;
    goto LABEL_5;
  }
  if ( (v11[520] & 1) != 0 || v12 || v13 )
    return 2147943568LL;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v9,
    v11,
    -1);
  if ( !v9 )
  {
    StorageInstanceCount = -2147024882;
    v5 = 73;
    goto LABEL_5;
  }
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x18000cc90  mov     [rsp-8+arg_0], rbx
0x18000cc95  mov     [rsp-8+arg_10], rdi
0x18000cc9a  push    rbp
0x18000cc9b  lea     rbp, [rsp-3A0h]
0x18000cca3  sub     rsp, 4A0h
0x18000ccaa  mov     rax, cs:__security_cookie
0x18000ccb1  xor     rax, rsp
0x18000ccb4  mov     [rbp+3A0h+var_10], rax
0x18000ccbb  mov     rdi, rdx
0x18000ccbe  mov     qword ptr [rdx], 0
0x18000ccc5  call    IsGetStorageInstanceCountPresent
0x18000ccca  test    al, al
0x18000cccc  jnz     short loc_18000CCD8
0x18000ccce  mov     eax, 80004001h
0x18000ccd3  jmp     loc_18000CDEB
0x18000ccd8  lea     rdx, [rsp+4A0h+var_480]
0x18000ccdd  mov     [rsp+4A0h+var_480], 0; int
0x18000cce5  xor     ecx, ecx
0x18000cce7  call    cs:__imp_GetStorageInstanceCount
0x18000cced  mov     ebx, eax
0x18000ccef  test    eax, eax
0x18000ccf1  jns     short loc_18000CD15
0x18000ccf3  mov     edx, 30h ; '0'; void *
0x18000ccf8  mov     rcx, [rbp+3A8h]; this
0x18000ccff  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x18000cd06  mov     r9d, ebx; char *
0x18000cd09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd0e  mov     eax, ebx
0x18000cd10  jmp     loc_18000CDEB
0x18000cd15  mov     eax, [rsp+4A0h+var_480]
0x18000cd19  xor     ebx, ebx
0x18000cd1b  test    eax, eax
0x18000cd1d  jz      short loc_18000CD57
0x18000cd1f  lea     r9, [rsp+4A0h+var_478]
0x18000cd24  mov     dword ptr [rsp+4A0h+var_478], 0
0x18000cd2c  mov     r8d, 2
0x18000cd32  mov     edx, ebx
0x18000cd34  xor     ecx, ecx
0x18000cd36  call    cs:__imp_GetStorageSettings
0x18000cd3c  test    eax, eax
0x18000cd3e  js      short loc_18000CD47
0x18000cd40  test    byte ptr [rsp+4A0h+var_478], 10h
0x18000cd45  jnz     short loc_18000CD53
0x18000cd47  mov     eax, [rsp+4A0h+var_480]
0x18000cd4b  inc     ebx
0x18000cd4d  cmp     ebx, eax
0x18000cd4f  jb      short loc_18000CD1F
0x18000cd51  jmp     short loc_18000CD57
0x18000cd53  mov     eax, [rsp+4A0h+var_480]
0x18000cd57  cmp     ebx, eax
0x18000cd59  jz      loc_18000CDE6
0x18000cd5f  xor     edx, edx; Val
0x18000cd61  lea     rcx, [rsp+4A0h+var_46C]; void *
0x18000cd66  mov     r8d, 454h; Size
0x18000cd6c  call    memset_0
0x18000cd71  lea     r8, [rsp+4A0h+var_470]
0x18000cd76  mov     [rsp+4A0h+var_470], 458h
0x18000cd7e  mov     edx, ebx
0x18000cd80  xor     ecx, ecx
0x18000cd82  call    cs:__imp_GetStorageDeviceInfo
0x18000cd88  mov     ebx, eax
0x18000cd8a  test    eax, eax
0x18000cd8c  jns     short loc_18000CD98
0x18000cd8e  mov     edx, 42h ; 'B'
0x18000cd93  jmp     loc_18000CCF8
0x18000cd98  test    [rbp+3A0h+var_264], 1
0x18000cd9f  jnz     short loc_18000CDE6
0x18000cda1  cmp     [rbp+3A0h+var_260], 0
0x18000cda8  jnz     short loc_18000CDE6
0x18000cdaa  cmp     [rbp+3A0h+var_258], 0
0x18000cdb1  jnz     short loc_18000CDE6
0x18000cdb3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cdb7  lea     rdx, [rsp+4A0h+var_46C]
0x18000cdbc  lea     rcx, [rsp+4A0h+var_478]
0x18000cdc1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000cdc6  mov     rax, [rsp+4A0h+var_478]
0x18000cdcb  test    rax, rax
0x18000cdce  jz      short loc_18000CDD7
0x18000cdd0  mov     [rdi], rax
0x18000cdd3  xor     eax, eax
0x18000cdd5  jmp     short loc_18000CDEB
0x18000cdd7  mov     ebx, 8007000Eh
0x18000cddc  mov     edx, 49h ; 'I'
0x18000cde1  jmp     loc_18000CCF8
0x18000cde6  mov     eax, 80070490h
0x18000cdeb  mov     rcx, [rbp+3A0h+var_10]
0x18000cdf2  xor     rcx, rsp; StackCookie
0x18000cdf5  call    __security_check_cookie
0x18000cdfa  lea     r11, [rsp+4A0h+var_s0]
0x18000ce02  mov     rbx, [r11+10h]
0x18000ce06  mov     rdi, [r11+20h]
0x18000ce0a  mov     rsp, r11
0x18000ce0d  pop     rbp
0x18000ce0e  retn
```
