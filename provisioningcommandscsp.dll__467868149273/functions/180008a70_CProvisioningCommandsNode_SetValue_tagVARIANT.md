# CProvisioningCommandsNode::SetValue(tagVARIANT)

- ea: `0x180008a70`
- end: `0x180008d9d`
- name: `?SetValue@CProvisioningCommandsNode@@UEAAJUtagVARIANT@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x180004ee4`
- `0x180007fac`
- `0x180008a50`
- `0x180008a70`
- `0x18000aa28`
- `0x18000aab0`
- `0x18000b064`
- `0x18000ccc0`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008d4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008d4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProvisioningCommandsNode::SetValue(CProvisioningCommandsNode *this, struct tagVARIANT *a2)
{
  int v4; // ebx
  int v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 result; // rax
  unsigned int v9; // ebx
  const char *v10; // r9
  BYTE *lpData; // rcx
  int lpValueName; // [rsp+20h] [rbp-D8h]
  BYTE Data[4]; // [rsp+40h] [rbp-B8h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-B0h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-A8h] BYREF
  unsigned __int16 *v16; // [rsp+58h] [rbp-A0h] BYREF
  LPCWSTR v17; // [rsp+60h] [rbp-98h] BYREF
  HKEY v18[5]; // [rsp+68h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+90h] [rbp-68h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-58h]
  unsigned __int64 v21; // [rsp+A8h] [rbp-50h]
  BYTE *v22; // [rsp+B0h] [rbp-48h]
  __int64 v23; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( (unsigned int)dword_180014230 <= 4 )
  {
    v4 = 0;
  }
  else
  {
    *(_DWORD *)Data = *((_DWORD *)this + 11);
    v22 = Data;
    v23 = 4;
    v4 = 0;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, (unsigned __int8 *)byte_18001092B, 0, 0, 3u, &v19);
  }
  RegistryConfig::RegistryConfig((RegistryConfig *)v18);
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         1,
         &v16);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 76;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
      (const char *)(unsigned int)v5,
      lpValueName);
    RegistryConfig::~RegistryConfig((RegistryConfig *)v18);
    return v6;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         2,
         &v15);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 77;
    goto LABEL_12;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         3,
         &v14);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 78;
    goto LABEL_12;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPCWSTR *))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         4,
         &v17);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 79;
    goto LABEL_12;
  }
  try
  {
    if ( *((_DWORD *)this + 11) == 4 || *((_DWORD *)this + 11) == 8 )
    {
      v21 = 7;
      v20 = 0;
      LOWORD(v19.Ptr) = 0;
      std::wstring::assign(&v19, a2->bstrVal);
      lpData = (BYTE *)&v19;
      if ( v21 >= 8 )
        lpData = (BYTE *)v19.Ptr;
      RegistryConfig::AddCommandSetting(v18, v16, v15, v14, v17, 1u, lpData, 2 * v20 + 2);
      CreateProvCommandResultRecord(v16, v15, v14);
      if ( v21 >= 8 )
        operator delete((void *)v19.Ptr);
    }
    else
    {
      if ( *((_DWORD *)this + 11) == 9 || *((_DWORD *)this + 11) == 10 )
      {
        *(_DWORD *)Data = a2->lVal;
      }
      else
      {
        if ( (unsigned int)(*((_DWORD *)this + 11) - 11) >= 2 )
        {
          v9 = (*((_DWORD *)this + 13) & 2) != 0 ? 0xFA003FF0 : 0;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x80,
            (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
            (const char *)(v9 - 2046820335),
            lpValueName);
          RegistryConfig::~RegistryConfig((RegistryConfig *)v18);
          return v9 - 2046820335;
        }
        LOBYTE(v4) = a2->iVal == -1;
        *(_DWORD *)Data = v4;
      }
      RegistryConfig::AddCommandSetting(v18, v16, v15, v14, v17, 4u, Data, 4u);
    }
    RegistryConfig::~RegistryConfig((RegistryConfig *)v18);
    result = 0;
  }
  catch ( ... )
  {
    *(_DWORD *)Data = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x84,
                        (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
                        v10);
    RegistryConfig::~RegistryConfig((RegistryConfig *)v18);
    return *(unsigned int *)Data;
  }
  return result;
}

```

## disassembly

```asm
0x180008a70  mov     r11, rsp
0x180008a73  mov     [r11+18h], rbx
0x180008a77  push    rsi
0x180008a78  push    rdi
0x180008a79  push    r12
0x180008a7b  push    r14
0x180008a7d  push    r15
0x180008a7f  sub     rsp, 0D0h
0x180008a86  mov     rax, cs:__security_cookie
0x180008a8d  xor     rax, rsp
0x180008a90  mov     [rsp+0F8h+var_38], rax
0x180008a98  mov     r15, rdx
0x180008a9b  mov     r14, rcx
0x180008a9e  mov     eax, cs:dword_180014230
0x180008aa4  mov     r12d, 4
0x180008aaa  cmp     eax, r12d
0x180008aad  jbe     short loc_180008AF1
0x180008aaf  mov     eax, [rcx+2Ch]
0x180008ab2  mov     dword ptr [rsp+0F8h+Data], eax
0x180008ab6  lea     rax, [rsp+0F8h+Data]
0x180008abb  mov     [r11-48h], rax
0x180008abf  mov     [r11-40h], r12
0x180008ac3  xor     ebx, ebx
0x180008ac5  lea     rax, [r11-68h]
0x180008ac9  mov     qword ptr [rsp+0F8h+dwType], rax
0x180008ace  mov     dword ptr [rsp+0F8h+lpValueName], 3
0x180008ad6  xor     r9d, r9d
0x180008ad9  xor     r8d, r8d
0x180008adc  lea     rdx, byte_18001092B
0x180008ae3  lea     rcx, dword_180014230
0x180008aea  call    _tlgWriteTransfer_EventWriteTransfer
0x180008aef  jmp     short loc_180008AF3
0x180008af1  xor     ebx, ebx
0x180008af3  lea     rcx, [rsp+0F8h+var_90]; this
0x180008af8  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180008afd  nop
0x180008afe  mov     [rsp+0F8h+var_A8], rbx
0x180008b03  mov     [rsp+0F8h+var_B0], rbx
0x180008b08  mov     [rsp+0F8h+var_A0], rbx
0x180008b0d  mov     [rsp+0F8h+var_98], rbx
0x180008b12  mov     rcx, [r14+18h]
0x180008b16  mov     rax, [rcx]
0x180008b19  lea     r8, [rsp+0F8h+var_A0]
0x180008b1e  mov     edx, 1
0x180008b23  mov     rax, [rax+58h]
0x180008b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b2c  mov     edi, eax
0x180008b2e  test    eax, eax
0x180008b30  jns     short loc_180008B39
0x180008b32  mov     edx, 4Ch ; 'L'
0x180008b37  jmp     short loc_180008BAA
0x180008b39  mov     rcx, [r14+18h]
0x180008b3d  mov     rax, [rcx]
0x180008b40  lea     r8, [rsp+0F8h+var_A8]
0x180008b45  mov     edx, 2
0x180008b4a  mov     rax, [rax+58h]
0x180008b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b53  mov     edi, eax
0x180008b55  test    eax, eax
0x180008b57  jns     short loc_180008B60
0x180008b59  mov     edx, 4Dh ; 'M'
0x180008b5e  jmp     short loc_180008BAA
0x180008b60  mov     rcx, [r14+18h]
0x180008b64  mov     rax, [rcx]
0x180008b67  lea     r8, [rsp+0F8h+var_B0]
0x180008b6c  mov     edx, 3
0x180008b71  mov     rax, [rax+58h]
0x180008b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b7a  mov     edi, eax
0x180008b7c  test    eax, eax
0x180008b7e  jns     short loc_180008B87
0x180008b80  mov     edx, 4Eh ; 'N'
0x180008b85  jmp     short loc_180008BAA
0x180008b87  mov     rcx, [r14+18h]
0x180008b8b  mov     rax, [rcx]
0x180008b8e  lea     r8, [rsp+0F8h+var_98]
0x180008b93  mov     edx, r12d
0x180008b96  mov     rax, [rax+58h]
0x180008b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9f  mov     edi, eax
0x180008ba1  test    eax, eax
0x180008ba3  jns     short loc_180008BD3
0x180008ba5  mov     edx, 4Fh ; 'O'; void *
0x180008baa  mov     r9d, eax; char *
0x180008bad  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008bb4  mov     rcx, [rsp+0F8h]; this
0x180008bbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bc1  nop
0x180008bc2  lea     rcx, [rsp+0F8h+var_90]; this
0x180008bc7  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008bcc  mov     eax, edi
0x180008bce  jmp     loc_180008D74
0x180008bd3  mov     ecx, [r14+2Ch]
0x180008bd7  sub     ecx, r12d
0x180008bda  jz      loc_180008C96
0x180008be0  sub     ecx, r12d
0x180008be3  jz      loc_180008C96
0x180008be9  sub     ecx, 1
0x180008bec  jz      short loc_180008C52
0x180008bee  sub     ecx, 1
0x180008bf1  jz      short loc_180008C52
0x180008bf3  sub     ecx, 1
0x180008bf6  jz      short loc_180008C43
0x180008bf8  cmp     ecx, 1
0x180008bfb  jz      short loc_180008C43
0x180008bfd  mov     eax, [r14+34h]
0x180008c01  and     al, 2
0x180008c03  neg     al
0x180008c05  sbb     ebx, ebx
0x180008c07  and     ebx, 0FA003FF0h
0x180008c0d  mov     rcx, [rsp+0F8h]; this
0x180008c15  lea     r9d, [rbx-79FFFFEFh]; char *
0x180008c1c  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008c23  mov     edx, 80h; void *
0x180008c28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c2d  nop
0x180008c2e  lea     rcx, [rsp+0F8h+var_90]; this
0x180008c33  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008c38  lea     eax, [rbx-79FFFFEFh]
0x180008c3e  jmp     loc_180008D74
0x180008c43  cmp     word ptr [r15+8], 0FFFFh
0x180008c49  setz    bl
0x180008c4c  mov     dword ptr [rsp+0F8h+Data], ebx
0x180008c50  jmp     short loc_180008C5A
0x180008c52  mov     eax, [r15+8]
0x180008c56  mov     dword ptr [rsp+0F8h+Data], eax
0x180008c5a  mov     qword ptr [rsp+0F8h+var_C0], r12; DWORD
0x180008c5f  lea     rax, [rsp+0F8h+Data]
0x180008c64  mov     [rsp+0F8h+lpData], rax; lpData
0x180008c69  mov     [rsp+0F8h+dwType], r12d; dwType
0x180008c6e  mov     rax, [rsp+0F8h+var_98]
0x180008c73  mov     [rsp+0F8h+lpValueName], rax; lpValueName
0x180008c78  mov     r9, [rsp+0F8h+var_B0]; unsigned __int16 *
0x180008c7d  mov     r8, [rsp+0F8h+var_A8]; unsigned __int16 *
0x180008c82  mov     rdx, [rsp+0F8h+var_A0]; unsigned __int16 *
0x180008c87  lea     rcx, [rsp+0F8h+var_90]; this
0x180008c8c  call    ?AddCommandSetting@RegistryConfig@@QEAAXPEBG000KPEBE_K@Z; RegistryConfig::AddCommandSetting(ushort const *,ushort const *,ushort const *,ushort const *,ulong,uchar const *,unsigned __int64)
0x180008c91  jmp     loc_180008D58
0x180008c96  mov     [rsp+0F8h+var_50], 7
0x180008ca2  mov     [rsp+0F8h+var_58], rbx
0x180008caa  mov     word ptr [rsp+0F8h+var_68], bx
0x180008cb2  mov     rdx, [r15+8]; Src
0x180008cb6  lea     rcx, [rsp+0F8h+var_68]; void *
0x180008cbe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008cc3  nop
0x180008cc4  mov     rax, [rsp+0F8h+var_58]
0x180008ccc  lea     rcx, [rsp+0F8h+var_68]
0x180008cd4  cmp     [rsp+0F8h+var_50], 8
0x180008cdd  cmovnb  rcx, qword ptr [rsp+0F8h+var_68]
0x180008ce6  lea     rax, ds:2[rax*2]
0x180008cee  mov     qword ptr [rsp+0F8h+var_C0], rax; DWORD
0x180008cf3  mov     [rsp+0F8h+lpData], rcx; lpData
0x180008cf8  mov     [rsp+0F8h+dwType], 1; dwType
0x180008d00  mov     rax, [rsp+0F8h+var_98]
0x180008d05  mov     [rsp+0F8h+lpValueName], rax; lpValueName
0x180008d0a  mov     r9, [rsp+0F8h+var_B0]; unsigned __int16 *
0x180008d0f  mov     r8, [rsp+0F8h+var_A8]; unsigned __int16 *
0x180008d14  mov     rdx, [rsp+0F8h+var_A0]; unsigned __int16 *
0x180008d19  lea     rcx, [rsp+0F8h+var_90]; this
0x180008d1e  call    ?AddCommandSetting@RegistryConfig@@QEAAXPEBG000KPEBE_K@Z; RegistryConfig::AddCommandSetting(ushort const *,ushort const *,ushort const *,ushort const *,ulong,uchar const *,unsigned __int64)
0x180008d23  mov     r8, [rsp+0F8h+var_B0]; unsigned __int16 *
0x180008d28  mov     rdx, [rsp+0F8h+var_A8]; unsigned __int16 *
0x180008d2d  mov     rcx, [rsp+0F8h+var_A0]; unsigned __int16 *
0x180008d32  call    ?CreateProvCommandResultRecord@@YAJPEBG00@Z; CreateProvCommandResultRecord(ushort const *,ushort const *,ushort const *)
0x180008d37  nop
0x180008d38  cmp     [rsp+0F8h+var_50], 8
0x180008d41  jb      short loc_180008D58
0x180008d43  mov     rcx, qword ptr [rsp+0F8h+var_68]
0x180008d4b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008d52  nop     dword ptr [rax+rax+00h]
0x180008d57  nop
0x180008d58  lea     rcx, [rsp+0F8h+var_90]; this
0x180008d5d  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008d62  xor     eax, eax
0x180008d64  jmp     short loc_180008D74
0x180008d66  lea     rcx, [rsp+0F8h+var_90]; this
0x180008d6b  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008d70  mov     eax, dword ptr [rsp+0F8h+Data]
0x180008d74  mov     rcx, [rsp+0F8h+var_38]
0x180008d7c  xor     rcx, rsp; StackCookie
0x180008d7f  call    __security_check_cookie
0x180008d84  mov     rbx, [rsp+0F8h+arg_10]
0x180008d8c  add     rsp, 0D0h
0x180008d93  pop     r15
0x180008d95  pop     r14
0x180008d97  pop     r12
0x180008d99  pop     rdi
0x180008d9a  pop     rsi
0x180008d9b  retn
```
