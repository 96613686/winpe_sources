# CNfsXmlParser::NfsXmlReadPermissionTemplate(IXMLDOMNode *)

- ea: `0x180028338`
- end: `0x180028504`
- name: `?NfsXmlReadPermissionTemplate@CNfsXmlParser@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CNfsXmlParser *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180028794`

## callees

- `0x1800096cc`
- `0x180009888`
- `0x18000eae4`
- `0x180028148`
- `0x180028338`
- `0x18002850c`
- `0x1800289e4`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800283fd`
- `msvcrt!_wcsicmp` at `0x1800283fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800284c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800284c4`

## string_xrefs

- `0x1800283f2`: `PermissionTemplate`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNfsXmlParser::NfsXmlReadPermissionTemplate(CNfsXmlParser *this, struct IXMLDOMNode *a2)
{
  int PermissionTemplateAttributes; // ebx
  __int64 v5; // rcx
  unsigned int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-49h] BYREF
  int v12; // [rsp+24h] [rbp-45h] BYREF
  __int64 v13; // [rsp+28h] [rbp-41h] BYREF
  __int64 v14; // [rsp+30h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-31h] BYREF
  __int128 v16; // [rsp+40h] [rbp-29h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h]
  _BYTE v18[32]; // [rsp+60h] [rbp-9h] BYREF
  _WORD v19[8]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v20; // [rsp+90h] [rbp+27h]
  __int64 v21; // [rsp+98h] [rbp+2Fh]

  v11 = 0;
  String1 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  v21 = 7;
  v20 = 0;
  v19[0] = 0;
  v16 = 0;
  v17 = 0;
  PermissionTemplateAttributes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))a2->lpVtbl->get_nodeType)(
                                   a2,
                                   &v11);
  if ( PermissionTemplateAttributes >= 0 )
  {
    if ( v11 == 1 )
    {
      PermissionTemplateAttributes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))a2->lpVtbl->get_nodeName)(
                                       a2,
                                       &String1);
      if ( PermissionTemplateAttributes >= 0 && !_wcsicmp(String1, L"PermissionTemplate") )
      {
        PermissionTemplateAttributes = CNfsXmlParser::NfsXmlReadPermissionTemplateAttributes(v5, a2, v19);
        if ( PermissionTemplateAttributes >= 0 )
        {
          PermissionTemplateAttributes = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_childNodes)(
                                           a2,
                                           &v14);
          if ( PermissionTemplateAttributes >= 0 )
            PermissionTemplateAttributes = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 64LL))(
                                             v14,
                                             &v12);
        }
        v6 = 0;
        if ( PermissionTemplateAttributes >= 0 )
        {
          do
          {
            if ( (int)v6 >= v12 )
              break;
            PermissionTemplateAttributes = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 56LL))(
                                             v14,
                                             v6,
                                             &v13);
            if ( PermissionTemplateAttributes >= 0 )
            {
              PermissionTemplateAttributes = CNfsXmlParser::NfsXmlReadPermissionList(v7, v13, &v16);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
            v13 = 0;
            ++v6;
          }
          while ( PermissionTemplateAttributes >= 0 );
          if ( PermissionTemplateAttributes >= 0 )
          {
            v8 = std::wstring::wstring(v18, v19);
            CNfsXmlParser::NfsXmlSetPermissionTemplate(this, v8, &v16);
          }
        }
      }
    }
    else
    {
      PermissionTemplateAttributes = -2147024809;
    }
  }
  SysFreeString(String1);
  std::vector<CNfsXmlSharePermission *>::_Tidy(&v16);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v19, v9, 0);
  return (unsigned int)PermissionTemplateAttributes;
}

```

## disassembly

```asm
0x180028338  mov     [rsp-8+arg_10], rbx
0x18002833d  push    rbp
0x18002833e  push    rsi
0x18002833f  push    rdi
0x180028340  lea     rbp, [rsp-47h]
0x180028345  sub     rsp, 0B0h
0x18002834c  mov     rax, cs:__security_cookie
0x180028353  xor     rax, rsp
0x180028356  mov     [rbp+57h+var_20], rax
0x18002835a  mov     rdi, rdx
0x18002835d  mov     rsi, rcx
0x180028360  mov     [rbp+57h+var_A0], 0
0x180028367  mov     [rbp+57h+String1], 0
0x18002836f  mov     [rbp+57h+var_90], 0
0x180028377  mov     [rbp+57h+var_9C], 0
0x18002837e  mov     [rbp+57h+var_98], 0
0x180028386  mov     [rbp+57h+var_28], 7
0x18002838e  mov     [rbp+57h+var_30], 0
0x180028396  xor     eax, eax
0x180028398  mov     [rbp+57h+var_40], ax
0x18002839c  xorps   xmm0, xmm0
0x18002839f  movdqu  [rbp+57h+var_80], xmm0
0x1800283a4  mov     [rbp+57h+var_70], rax
0x1800283a8  mov     rax, [rdx]
0x1800283ab  lea     rdx, [rbp+57h+var_A0]
0x1800283af  mov     rcx, rdi
0x1800283b2  mov     rax, [rax+50h]
0x1800283b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283bb  mov     ebx, eax
0x1800283bd  test    eax, eax
0x1800283bf  js      loc_1800284C0
0x1800283c5  cmp     [rbp+57h+var_A0], 1
0x1800283c9  jz      short loc_1800283D5
0x1800283cb  mov     ebx, 80070057h
0x1800283d0  jmp     loc_1800284C0
0x1800283d5  mov     rax, [rdi]
0x1800283d8  lea     rdx, [rbp+57h+String1]
0x1800283dc  mov     rcx, rdi
0x1800283df  mov     rax, [rax+38h]
0x1800283e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283e8  mov     ebx, eax
0x1800283ea  test    eax, eax
0x1800283ec  js      loc_1800284C0
0x1800283f2  lea     rdx, aPermissiontemp; "PermissionTemplate"
0x1800283f9  mov     rcx, [rbp+57h+String1]; String1
0x1800283fd  call    cs:__imp__wcsicmp
0x180028403  test    eax, eax
0x180028405  jnz     loc_1800284C0
0x18002840b  lea     r8, [rbp+57h+var_40]
0x18002840f  mov     rdx, rdi
0x180028412  call    ?NfsXmlReadPermissionTemplateAttributes@CNfsXmlParser@@AEAAJPEAUIXMLDOMNode@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CNfsXmlParser::NfsXmlReadPermissionTemplateAttributes(IXMLDOMNode *,std::wstring &)
0x180028417  mov     ebx, eax
0x180028419  test    eax, eax
0x18002841b  js      short loc_18002844C
0x18002841d  mov     rax, [rdi]
0x180028420  lea     rdx, [rbp+57h+var_90]
0x180028424  mov     rcx, rdi
0x180028427  mov     rax, [rax+60h]
0x18002842b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028430  mov     ebx, eax
0x180028432  test    eax, eax
0x180028434  js      short loc_18002844C
0x180028436  mov     rcx, [rbp+57h+var_90]
0x18002843a  mov     rax, [rcx]
0x18002843d  lea     rdx, [rbp+57h+var_9C]
0x180028441  mov     rax, [rax+40h]
0x180028445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002844a  mov     ebx, eax
0x18002844c  xor     edi, edi
0x18002844e  test    ebx, ebx
0x180028450  js      short loc_1800284C0
0x180028452  cmp     edi, [rbp+57h+var_9C]
0x180028455  jge     short loc_1800284A0
0x180028457  mov     rcx, [rbp+57h+var_90]
0x18002845b  mov     rax, [rcx]
0x18002845e  lea     r8, [rbp+57h+var_98]
0x180028462  mov     edx, edi
0x180028464  mov     rax, [rax+38h]
0x180028468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002846d  mov     ebx, eax
0x18002846f  test    eax, eax
0x180028471  js      short loc_180028492
0x180028473  lea     r8, [rbp+57h+var_80]
0x180028477  mov     rdx, [rbp+57h+var_98]
0x18002847b  call    ?NfsXmlReadPermissionList@CNfsXmlParser@@AEAAJPEAUIXMLDOMNode@@AEAV?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@@Z; CNfsXmlParser::NfsXmlReadPermissionList(IXMLDOMNode *,std::vector<CNfsXmlSharePermission *> &)
0x180028480  mov     ebx, eax
0x180028482  mov     rcx, [rbp+57h+var_98]
0x180028486  mov     rax, [rcx]
0x180028489  mov     rax, [rax+10h]
0x18002848d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028492  mov     [rbp+57h+var_98], 0
0x18002849a  inc     edi
0x18002849c  test    ebx, ebx
0x18002849e  jns     short loc_180028452
0x1800284a0  test    ebx, ebx
0x1800284a2  js      short loc_1800284C0
0x1800284a4  lea     rdx, [rbp+57h+var_40]
0x1800284a8  lea     rcx, [rbp+57h+var_60]
0x1800284ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800284b1  lea     r8, [rbp+57h+var_80]
0x1800284b5  mov     rdx, rax
0x1800284b8  mov     rcx, rsi
0x1800284bb  call    ?NfsXmlSetPermissionTemplate@CNfsXmlParser@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@3@@Z; CNfsXmlParser::NfsXmlSetPermissionTemplate(std::wstring,std::vector<CNfsXmlSharePermission *> &)
0x1800284c0  mov     rcx, [rbp+57h+String1]; bstrString
0x1800284c4  call    cs:__imp_SysFreeString
0x1800284ca  nop
0x1800284cb  lea     rcx, [rbp+57h+var_80]
0x1800284cf  call    ?_Tidy@?$vector@PEAVCNfsXmlSharePermission@@V?$allocator@PEAVCNfsXmlSharePermission@@@std@@@std@@IEAAXXZ; std::vector<CNfsXmlSharePermission *>::_Tidy(void)
0x1800284d4  nop
0x1800284d5  xor     r8d, r8d
0x1800284d8  mov     dl, 1
0x1800284da  lea     rcx, [rbp+57h+var_40]
0x1800284de  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800284e3  mov     eax, ebx
0x1800284e5  mov     rcx, [rbp+57h+var_20]
0x1800284e9  xor     rcx, rsp; StackCookie
0x1800284ec  call    __security_check_cookie
0x1800284f1  mov     rbx, [rsp+0C0h+arg_10]
0x1800284f9  add     rsp, 0B0h
0x180028500  pop     rdi
0x180028501  pop     rsi
0x180028502  pop     rbp
0x180028503  retn
```
