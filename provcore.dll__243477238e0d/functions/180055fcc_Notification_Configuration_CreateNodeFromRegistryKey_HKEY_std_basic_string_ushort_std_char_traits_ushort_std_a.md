# Notification::Configuration::CreateNodeFromRegistryKey(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180055fcc`
- end: `0x180056128`
- name: `?CreateNodeFromRegistryKey@Configuration@Notification@@YA?AV?$shared_ptr@VNode@Configuration@Notification@@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `348`
- prototype: `std::shared_ptr<Notification::Configuration::Node> *__fastcall(std::shared_ptr<Notification::Configuration::Node> *result, HKEY__ *Key, const std::wstring *Path)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002dd94`

## callees

- `0x180002790`
- `0x18000fa6c`
- `0x180011844`
- `0x18001282c`
- `0x180055b58`
- `0x180055fcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005602c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005602c`

## pseudocode

```c
HKEY__ *__fastcall Notification::Configuration::CreateNodeFromRegistryKey(
        HKEY__ *result,
        HKEY__ *Key,
        const std::wstring *Path)
{
  bool v4; // zf
  const WCHAR *v6; // rax
  HKEY v7; // r10
  const wchar_t *v8; // rax
  __int64 v9; // r10
  int v10; // r8d
  std::_Ref_count_base **v11; // rcx
  char v12; // bl
  std::_Ref_count_base *v14[2]; // [rsp+38h] [rbp-40h] BYREF
  std::shared_ptr<Notification::Configuration::RegistryNode> resulta; // [rsp+48h] [rbp-30h] BYREF
  HKEY__ *nodeKey; // [rsp+58h] [rbp-20h] BYREF

  nodeKey = result;
  v4 = Path->_Mypair._Myval2._Mysize == 0;
  nodeKey = 0;
  if ( v4 )
  {
    nodeKey = Key;
  }
  else
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Path->_Mypair._Myval2);
    if ( RegOpenKeyExW(v7, v6, 0, 0x20019u, &nodeKey)
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Path->_Mypair._Myval2);
      WPP_SF_Sd(*(_QWORD *)(v9 + 16), 0xDu, WPP_47982e1cdd76344926602deeea25dda2_Traceguids, v8, v10);
    }
  }
  if ( nodeKey )
  {
    v11 = (std::_Ref_count_base **)std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(
                                     &resulta,
                                     &nodeKey);
    v12 = 5;
  }
  else
  {
    v11 = v14;
    *(_OWORD *)v14 = 0;
    v12 = 6;
  }
  *(_QWORD *)result = 0;
  *((_QWORD *)result + 1) = 0;
  *(_QWORD *)result = *v11;
  *((_QWORD *)result + 1) = v11[1];
  *v11 = 0;
  v11[1] = 0;
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    if ( v14[1] )
      std::_Ref_count_base::_Decref(v14[1]);
  }
  if ( (v12 & 1) != 0 && resulta._Rep )
    std::_Ref_count_base::_Decref(resulta._Rep);
  return result;
}

```

## disassembly

```asm
0x180055fcc  mov     [rsp+arg_18], rbx
0x180055fd1  push    rdi
0x180055fd2  sub     rsp, 70h
0x180055fd6  mov     rax, cs:__security_cookie
0x180055fdd  xor     rax, rsp
0x180055fe0  mov     [rsp+78h+var_18], rax
0x180055fe5  mov     [rsp+78h+nodeKey], rcx
0x180055fea  mov     rbx, Path
0x180055fed  cmp     qword ptr [Path+10h], 0
0x180055ff2  mov     r10, Key
0x180055ff5  mov     rdi, rcx
0x180055ff8  mov     [rsp+78h+var_48], 0
0x180056000  mov     [rsp+78h+nodeKey], 0
0x180056009  jz      short loc_18005607A
0x18005600b  mov     rcx, rbx; this
0x18005600e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180056013  lea     rcx, [rsp+78h+nodeKey]
0x180056018  mov     r9d, 20019h; samDesired
0x18005601e  mov     [rsp+78h+phkResult], rcx; phkResult
0x180056023  xor     r8d, r8d; ulOptions
0x180056026  mov     rcx, r10; hKey
0x180056029  mov     Key, rax; lpSubKey
0x18005602c  call    cs:__imp_RegOpenKeyExW
0x180056032  mov     r8d, eax
0x180056035  test    eax, eax
0x180056037  jz      short loc_18005607F
0x180056039  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180056040  lea     rax, WPP_GLOBAL_Control
0x180056047  cmp     r10, rax
0x18005604a  jz      short loc_18005607F
0x18005604c  test    byte ptr [r10+1Ch], 4
0x180056051  jz      short loc_18005607F
0x180056053  mov     rcx, rbx; this
0x180056056  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005605b  mov     rcx, [r10+10h]; Logger
0x18005605f  mov     r9, rax; _a1
0x180056062  mov     dword ptr [rsp+78h+phkResult], r8d; _a2
0x180056067  mov     edx, 0Dh; id
0x18005606c  lea     Path, WPP_47982e1cdd76344926602deeea25dda2_Traceguids; TraceGuid
0x180056073  call    WPP_SF_Sd
0x180056078  jmp     short loc_18005607F
0x18005607a  mov     [rsp+78h+nodeKey], r10
0x18005607f  cmp     [rsp+78h+nodeKey], 0
0x180056085  jz      short loc_1800560A0
0x180056087  lea     Key, [rsp+78h+nodeKey]; <_Args_0>
0x18005608c  lea     rcx, [rsp+78h+result]; result
0x180056091  call    ??$make_shared@VRegistryNode@Configuration@Notification@@AEAPEAUHKEY__@@@std@@YA?AV?$shared_ptr@VRegistryNode@Configuration@Notification@@@0@AEAPEAUHKEY__@@@Z; std::make_shared<Notification::Configuration::RegistryNode,HKEY__ * &>(HKEY__ * &)
0x180056096  mov     rcx, rax
0x180056099  mov     ebx, 5
0x18005609e  jmp     short loc_1800560B3
0x1800560a0  xorps   xmm0, xmm0
0x1800560a3  lea     rcx, [rsp+78h+var_40]
0x1800560a8  movdqu  xmmword ptr [rsp+78h+var_40], xmm0
0x1800560ae  mov     ebx, 6
0x1800560b3  mov     qword ptr [rdi], 0
0x1800560ba  mov     qword ptr [rdi+8], 0
0x1800560c2  mov     rax, [rcx]
0x1800560c5  mov     [rdi], rax
0x1800560c8  mov     rax, [rcx+8]
0x1800560cc  mov     [rdi+8], rax
0x1800560d0  mov     qword ptr [rcx], 0
0x1800560d7  mov     qword ptr [rcx+8], 0
0x1800560df  test    bl, 2
0x1800560e2  jz      short loc_1800560F6
0x1800560e4  mov     rcx, [rsp+78h+var_40+8]; this
0x1800560e9  and     ebx, 0FFFFFFFDh
0x1800560ec  test    rcx, rcx
0x1800560ef  jz      short loc_1800560F6
0x1800560f1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800560f6  test    bl, 1
0x1800560f9  jz      short loc_18005610A
0x1800560fb  mov     rcx, [rsp+78h+result._Rep]; this
0x180056100  test    rcx, rcx
0x180056103  jz      short loc_18005610A
0x180056105  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005610a  mov     rax, rdi
0x18005610d  mov     rcx, [rsp+78h+var_18]
0x180056112  xor     rcx, rsp; StackCookie
0x180056115  call    __security_check_cookie
0x18005611a  mov     rbx, [rsp+78h+arg_18]
0x180056122  add     rsp, 70h
0x180056126  pop     rdi
0x180056127  retn
```
