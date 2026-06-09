# CExtensionHandler::HandleProvisionState(__MIDL___MIDL_itf_mvengine_0000_0000_0001,_MVHandlerData *)

- ea: `0x1800143f0`
- end: `0x180014540`
- name: `?HandleProvisionState@CExtensionHandler@@UEAAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAU_MVHandlerData@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180001850`
- `0x1800076a4`
- `0x18000ee10`
- `0x1800143f0`
- `0x1800145f8`
- `0x180015474`

## string_xrefs

- `0x18001441f`: `onecoreuap\admin\prov\multivariant\handlers\extension\extensionhandler.cpp`
- `0x180014445`: `Extension handler`
- `0x180014473`: `Extension handler`
- `0x1800144ef`: `Extension handler`

## pseudocode

```c
__int64 __fastcall CExtensionHandler::HandleProvisionState(__int64 a1, unsigned int a2, _DWORD *a3)
{
  int v6; // eax
  HKEY v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // ebx
  int ExtensionsFromRegistry; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  CMvExtensionKey **i; // rbx
  __int64 v17; // rcx
  unsigned int v18; // edx
  int v20; // [rsp+20h] [rbp-38h]
  const WCHAR *v21[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v23; // [rsp+78h] [rbp+20h] BYREF

  v6 = CHandlerBase::HandleProvisionState();
  v11 = v6;
  if ( v6 >= 0 )
  {
    if ( (unsigned int)dword_180052170 > 4 )
    {
      v23 = a2;
      v21[0] = L"Extension handler";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (__int64)byte_1800494E9,
        v9,
        v10,
        v21,
        (__int64)&v23);
    }
    if ( a2 == 10 )
    {
      return 0;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 56) )
        goto LABEL_10;
      try
      {
        ExtensionsFromRegistry = CExtensionHandler::ReadExtensionsFromRegistry((CExtensionHandler *)a1, v7);
      }
      catch ( std::bad_alloc )
      {
        v11 = -2147024882;
        goto LABEL_20;
      }
      catch ( ... )
      {
        v11 = -2147467259;
        goto LABEL_20;
      }
      v11 = ExtensionsFromRegistry;
      if ( ExtensionsFromRegistry >= 0 )
      {
LABEL_10:
        for ( i = *(CMvExtensionKey ***)(a1 + 32); i != *(CMvExtensionKey ***)(a1 + 40); i += 2 )
        {
          if ( (int)CMvExtensionKey::ReadKeys(*i) >= 0 )
          {
            v17 = 0;
            v18 = *((_DWORD *)*i + 150);
            if ( v18 )
            {
              while ( *((_DWORD *)*i + v17 + 132) != a2 )
              {
                v17 = (unsigned int)(v17 + 1);
                if ( (unsigned int)v17 >= v18 )
                  goto LABEL_19;
              }
              *a3 = 1;
              a3[3] = 1;
            }
          }
LABEL_19:
          ;
        }
        return 0;
      }
      else
      {
LABEL_20:
        if ( (unsigned int)dword_180052170 > 2 )
        {
          v23 = v11;
          v21[0] = L"Extension handler";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v13,
            (__int64)&unk_180049438,
            v14,
            v15,
            v21,
            (__int64)&v23);
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\extension\\extensionhandler.cpp",
      (const char *)(unsigned int)v6,
      v20);
  }
  return v11;
}

```

## disassembly

```asm
0x1800143f0  mov     [rsp+arg_0], rbx
0x1800143f5  mov     [rsp+arg_8], rsi
0x1800143fa  push    rdi
0x1800143fb  push    r14
0x1800143fd  push    r15
0x1800143ff  sub     rsp, 40h
0x180014403  mov     r15, r8
0x180014406  mov     r14d, edx
0x180014409  mov     rsi, rcx
0x18001440c  call    ?HandleProvisionState@CHandlerBase@@UEAAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAU_MVHandlerData@@@Z; CHandlerBase::HandleProvisionState(__MIDL___MIDL_itf_mvengine_0000_0000_0001,_MVHandlerData *)
0x180014411  mov     ebx, eax
0x180014413  test    eax, eax
0x180014415  jns     short loc_180014435
0x180014417  mov     rcx, [rsp+58h]; this
0x18001441c  mov     r9d, eax; char *
0x18001441f  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014426  mov     edx, 8Eh; void *
0x18001442b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014430  jmp     loc_18001452A
0x180014435  mov     eax, cs:dword_180052170
0x18001443b  cmp     eax, 4
0x18001443e  jbe     short loc_180014473
0x180014440  mov     [rsp+58h+arg_18], r14d
0x180014445  lea     rdi, aExtensionHandl; "Extension handler"
0x18001444c  mov     [rsp+58h+var_28], rdi
0x180014451  lea     rax, [rsp+58h+arg_18]
0x180014456  mov     [rsp+58h+var_30], rax
0x18001445b  lea     rax, [rsp+58h+var_28]
0x180014460  mov     [rsp+58h+var_38], rax
0x180014465  lea     rdx, byte_1800494E9
0x18001446c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014471  jmp     short loc_18001447A
0x180014473  lea     rdi, aExtensionHandl; "Extension handler"
0x18001447a  cmp     r14d, 0Ah
0x18001447e  jnz     short loc_180014487
0x180014480  xor     ebx, ebx
0x180014482  jmp     loc_18001452A
0x180014487  cmp     dword ptr [rsi+38h], 0
0x18001448b  jnz     short loc_18001449D
0x18001448d  mov     rcx, rsi; this
0x180014490  call    ?ReadExtensionsFromRegistry@CExtensionHandler@@IEAAJPEAUHKEY__@@@Z; CExtensionHandler::ReadExtensionsFromRegistry(HKEY__ *)
0x180014495  mov     ebx, eax
0x180014497  test    eax, eax
0x180014499  jns     short loc_18001449D
0x18001449b  jmp     short loc_1800144F6
0x18001449d  mov     rbx, [rsi+20h]
0x1800144a1  mov     edi, 1
0x1800144a6  cmp     rbx, [rsi+28h]
0x1800144aa  jnz     short loc_1800144B0
0x1800144ac  xor     ebx, ebx
0x1800144ae  jmp     short loc_18001452A
0x1800144b0  mov     rcx, [rbx]; this
0x1800144b3  call    ?ReadKeys@CMvExtensionKey@@QEAAJXZ; CMvExtensionKey::ReadKeys(void)
0x1800144b8  test    eax, eax
0x1800144ba  js      short loc_1800144E5
0x1800144bc  mov     r8, [rbx]
0x1800144bf  xor     ecx, ecx
0x1800144c1  mov     edx, [r8+258h]
0x1800144c8  test    edx, edx
0x1800144ca  jz      short loc_1800144E5
0x1800144cc  cmp     [r8+rcx*4+210h], r14d
0x1800144d4  jz      short loc_1800144DE
0x1800144d6  add     ecx, edi
0x1800144d8  cmp     ecx, edx
0x1800144da  jb      short loc_1800144CC
0x1800144dc  jmp     short loc_1800144E5
0x1800144de  mov     [r15], edi
0x1800144e1  mov     [r15+0Ch], edi
0x1800144e5  add     rbx, 10h
0x1800144e9  jmp     short loc_1800144A6
0x1800144eb  mov     ebx, [rsp+58h+arg_18]
0x1800144ef  lea     rdi, aExtensionHandl; "Extension handler"
0x1800144f6  mov     eax, cs:dword_180052170
0x1800144fc  cmp     eax, 2
0x1800144ff  jbe     short loc_18001452A
0x180014501  mov     [rsp+58h+arg_18], ebx
0x180014505  mov     [rsp+58h+var_28], rdi
0x18001450a  lea     rax, [rsp+58h+arg_18]
0x18001450f  mov     [rsp+58h+var_30], rax
0x180014514  lea     rax, [rsp+58h+var_28]
0x180014519  mov     [rsp+58h+var_38], rax
0x18001451e  lea     rdx, unk_180049438
0x180014525  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001452a  mov     eax, ebx
0x18001452c  mov     rbx, [rsp+58h+arg_0]
0x180014531  mov     rsi, [rsp+58h+arg_8]
0x180014536  add     rsp, 40h
0x18001453a  pop     r15
0x18001453c  pop     r14
0x18001453e  pop     rdi
0x18001453f  retn
```
