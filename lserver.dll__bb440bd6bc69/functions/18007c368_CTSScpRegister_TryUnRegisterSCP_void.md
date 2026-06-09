# CTSScpRegister::TryUnRegisterSCP(void)

- ea: `0x18007c368`
- end: `0x18007c4c6`
- name: `?TryUnRegisterSCP@CTSScpRegister@@AEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007bb18`
- `0x18007c0e0`
- `0x18007c4cc`

## callees

- `0x18001aea4`
- `0x180078bbc`
- `0x180078f54`
- `0x180079e20`
- `0x18007aaf8`
- `0x18007c368`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x18007c3b0`
- `ADVAPI32!RegDeleteKeyW` at `0x18007c3b0`
- `KERNEL32!LocalFree` at `0x18007c48b`
- `KERNEL32!LocalFree` at `0x18007c48b`

## string_xrefs

- `0x18007c454`: `"ComposeString"`
- `0x18007c3f6`: `"GetLocalComputerObject"`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSScpRegister::TryUnRegisterSCP(CTSScpRegister *this)
{
  int LocalComputerObject; // ebx
  HLOCAL v3; // rdi
  void *ppObject; // [rsp+30h] [rbp-828h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-820h] BYREF
  WCHAR SubKey[1024]; // [rsp+40h] [rbp-818h] BYREF

  hMem = 0;
  ppObject = 0;
  GetScpGUIDRegistryKeyPath(*((_QWORD *)this + 12), SubKey);
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  LocalComputerObject = GetLocalComputerObject(&ppObject);
  if ( LocalComputerObject >= 0 )
  {
    LocalComputerObject = ComposeString(&hMem, L"CN=", *((_QWORD *)this + 12));
    v3 = hMem;
    if ( LocalComputerObject >= 0 )
    {
      LocalComputerObject = (*(__int64 (__fastcall **)(void *, HLOCAL))(*(_QWORD *)ppObject + 56LL))(ppObject, hMem);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)L"\"ComposeString\"",
        LocalComputerObject);
    }
    if ( v3 )
      LocalFree(v3);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
      (unsigned int)L"\"GetLocalComputerObject\"",
      LocalComputerObject);
  }
  ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(&ppObject);
  return (unsigned int)LocalComputerObject;
}

```

## disassembly

```asm
0x18007c368  mov     [rsp+arg_8], rbx
0x18007c36d  push    rdi
0x18007c36e  sub     rsp, 850h
0x18007c375  mov     rax, cs:__security_cookie
0x18007c37c  xor     rax, rsp
0x18007c37f  mov     [rsp+858h+var_18], rax
0x18007c387  mov     rdi, rcx
0x18007c38a  and     [rsp+858h+hMem], 0
0x18007c390  and     [rsp+858h+ppObject], 0
0x18007c396  lea     rdx, [rsp+858h+SubKey]
0x18007c39b  mov     rcx, [rcx+60h]
0x18007c39f  call    GetScpGUIDRegistryKeyPath
0x18007c3a4  lea     rdx, [rsp+858h+SubKey]; lpSubKey
0x18007c3a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007c3b0  call    cs:__imp_RegDeleteKeyW
0x18007c3b7  nop     dword ptr [rax+rax+00h]
0x18007c3bc  lea     rcx, [rsp+858h+ppObject]; ppObject
0x18007c3c1  call    GetLocalComputerObject
0x18007c3c6  mov     ebx, eax
0x18007c3c8  test    eax, eax
0x18007c3ca  jns     short loc_18007C412
0x18007c3cc  lea     rax, WPP_GLOBAL_Control
0x18007c3d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3da  cmp     rcx, rax
0x18007c3dd  jz      loc_18007C498
0x18007c3e3  cmp     byte ptr [rcx+19h], 2
0x18007c3e7  jb      loc_18007C498
0x18007c3ed  mov     edx, 3Ah ; ':'
0x18007c3f2  mov     [rsp+858h+var_838], ebx
0x18007c3f6  lea     r9, aGetlocalcomput; "\"GetLocalComputerObject\""
0x18007c3fd  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007c404  mov     rcx, [rcx+10h]
0x18007c408  call    WPP_SF_SD
0x18007c40d  jmp     loc_18007C498
0x18007c412  mov     r8, [rdi+60h]
0x18007c416  lea     rdx, aCn_0; "CN="
0x18007c41d  lea     rcx, [rsp+858h+hMem]
0x18007c422  call    ComposeString
0x18007c427  mov     ebx, eax
0x18007c429  mov     rdi, [rsp+858h+hMem]
0x18007c42e  test    eax, eax
0x18007c430  jns     short loc_18007C46D
0x18007c432  lea     rax, WPP_GLOBAL_Control
0x18007c439  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c440  cmp     rcx, rax
0x18007c443  jz      short loc_18007C483
0x18007c445  cmp     byte ptr [rcx+19h], 2
0x18007c449  jb      short loc_18007C483
0x18007c44b  mov     edx, 3Bh ; ';'
0x18007c450  mov     [rsp+858h+var_838], ebx
0x18007c454  lea     r9, aComposestring; "\"ComposeString\""
0x18007c45b  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007c462  mov     rcx, [rcx+10h]
0x18007c466  call    WPP_SF_SD
0x18007c46b  jmp     short loc_18007C483
0x18007c46d  mov     rcx, [rsp+858h+ppObject]
0x18007c472  mov     rax, [rcx]
0x18007c475  mov     rdx, rdi
0x18007c478  mov     rax, [rax+38h]
0x18007c47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c481  mov     ebx, eax
0x18007c483  test    rdi, rdi
0x18007c486  jz      short loc_18007C498
0x18007c488  mov     rcx, rdi; hMem
0x18007c48b  call    cs:__imp_LocalFree
0x18007c492  nop     dword ptr [rax+rax+00h]
0x18007c497  nop
0x18007c498  lea     rcx, [rsp+858h+ppObject]
0x18007c49d  call    ??1?$CComPtrBase@UIADs@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(void)
0x18007c4a2  mov     eax, ebx
0x18007c4a4  mov     rcx, [rsp+858h+var_18]
0x18007c4ac  xor     rcx, rsp; StackCookie
0x18007c4af  call    __security_check_cookie
0x18007c4b4  mov     rbx, [rsp+858h+arg_8]
0x18007c4bc  add     rsp, 850h
0x18007c4c3  pop     rdi
0x18007c4c4  retn
```
