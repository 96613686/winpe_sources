# CProvisioningCommandsNode::Clear(void)

- ea: `0x180008cc0`
- end: `0x180008fb3`
- name: `?Clear@CProvisioningCommandsNode@@UEAAJXZ`
- size: `755`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x180004da4`
- `0x180008cc0`
- `0x18000a4d4`
- `0x18000a550`
- `0x18000acc4`
- `0x18000af48`
- `0x18000c600`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::Clear(CProvisioningCommandsNode *this)
{
  int v3; // eax
  unsigned int v4; // edi
  int v5; // eax
  unsigned int v6; // edi
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // edi
  int v13; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int16 *v16; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int16 **v18; // [rsp+68h] [rbp-20h]
  __int64 v19; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned int)dword_180014230 > 4 )
  {
    LODWORD(v14) = *((_DWORD *)this + 11);
    v18 = &v14;
    v19 = 4;
    v13 = 3;
    tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_1800109A1, 0, 0);
  }
  if ( *((_DWORD *)this + 11) != 2 )
  {
    if ( *((_DWORD *)this + 11) == 3 )
      goto LABEL_9;
    if ( *((_DWORD *)this + 11) != 6 )
    {
      if ( *((_DWORD *)this + 11) != 7 )
      {
        if ( (*((_BYTE *)this + 52) & 8) == 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30,
            (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
            (const char *)0x86000011LL,
            v13);
          return 2248146961LL;
        }
        return 0;
      }
LABEL_9:
      RegistryConfig::RegistryConfig((RegistryConfig *)v17);
      v15 = 0;
      v16 = 0;
      v14 = 0;
      v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
             *((_QWORD *)this + 3),
             1,
             &v16);
      v4 = v3;
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
          (const char *)(unsigned int)v3,
          v13);
        RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
        return v4;
      }
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
             *((_QWORD *)this + 3),
             2,
             &v15);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
          (const char *)(unsigned int)v5,
          v13);
        RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
        return v6;
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
             *((_QWORD *)this + 3),
             3,
             &v14);
      v8 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28,
          (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
          (const char *)(unsigned int)v7,
          v13);
        RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
        return v8;
      }
      RegistryConfig::Delete((RegistryConfig *)v17, v16, v15, v14);
      RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
      return 0;
    }
  }
  RegistryConfig::RegistryConfig((RegistryConfig *)v17);
  v16 = 0;
  v15 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
         *((_QWORD *)this + 3),
         1,
         &v15);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
      (const char *)(unsigned int)v9,
      v13);
    RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
    return v10;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
          *((_QWORD *)this + 3),
          2,
          &v16);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
      (const char *)(unsigned int)v11,
      v13);
    RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
    return v12;
  }
  RegistryConfig::DeleteCommandSet((RegistryConfig *)v17, v15, v16);
  RegistryConfig::~RegistryConfig((RegistryConfig *)v17);
  return 0;
}

```

## disassembly

```asm
0x180008cc0  mov     r11, rsp
0x180008cc3  mov     [r11+10h], rsi
0x180008cc7  push    rdi
0x180008cc8  sub     rsp, 80h
0x180008ccf  mov     rax, cs:__security_cookie
0x180008cd6  xor     rax, rsp
0x180008cd9  mov     [rsp+88h+var_10], rax
0x180008cde  mov     rsi, rcx
0x180008ce1  mov     eax, cs:dword_180014230
0x180008ce7  cmp     eax, 4
0x180008cea  jbe     short loc_180008D2C
0x180008cec  mov     eax, [rcx+2Ch]
0x180008cef  mov     dword ptr [rsp+88h+var_58], eax
0x180008cf3  lea     rax, [r11-58h]
0x180008cf7  mov     [r11-20h], rax
0x180008cfb  mov     qword ptr [r11-18h], 4
0x180008d03  lea     rax, [r11-40h]
0x180008d07  mov     [r11-60h], rax
0x180008d0b  mov     [rsp+88h+var_68], 3; int
0x180008d13  xor     r9d, r9d
0x180008d16  xor     r8d, r8d
0x180008d19  lea     rdx, byte_1800109A1
0x180008d20  lea     rcx, dword_180014230
0x180008d27  call    _tlgWriteTransfer_EventWriteTransfer
0x180008d2c  mov     ecx, [rsi+2Ch]
0x180008d2f  sub     ecx, 2
0x180008d32  jz      loc_180008ED3
0x180008d38  sub     ecx, 1
0x180008d3b  jz      short loc_180008D7E
0x180008d3d  sub     ecx, 3
0x180008d40  jz      loc_180008ED3
0x180008d46  cmp     ecx, 1
0x180008d49  jz      short loc_180008D7E
0x180008d4b  test    byte ptr [rsi+34h], 8
0x180008d4f  jnz     loc_180008FAC
0x180008d55  mov     rcx, [rsp+88h]; this
0x180008d5d  mov     r9d, 86000011h; char *
0x180008d63  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180008d6a  mov     edx, 30h ; '0'; void *
0x180008d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d74  mov     eax, 86000011h
0x180008d79  jmp     loc_180008EB5
0x180008d7e  lea     rcx, [rsp+88h+var_40]; this
0x180008d83  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180008d88  nop
0x180008d89  mov     [rsp+88h+var_50], 0
0x180008d92  mov     [rsp+88h+var_48], 0
0x180008d9b  mov     [rsp+88h+var_58], 0
0x180008da4  mov     rcx, [rsi+18h]
0x180008da8  mov     rax, [rcx]
0x180008dab  lea     r8, [rsp+88h+var_48]
0x180008db0  mov     edx, 1
0x180008db5  mov     rax, [rax+58h]
0x180008db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbe  mov     edi, eax
0x180008dc0  test    eax, eax
0x180008dc2  jns     short loc_180008DF2
0x180008dc4  mov     rcx, [rsp+88h]; this
0x180008dcc  mov     r9d, eax; char *
0x180008dcf  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180008dd6  mov     edx, 26h ; '&'; void *
0x180008ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008de0  nop
0x180008de1  lea     rcx, [rsp+88h+var_40]; this
0x180008de6  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008deb  mov     eax, edi
0x180008ded  jmp     loc_180008EB5
0x180008df2  mov     rcx, [rsi+18h]
0x180008df6  mov     rax, [rcx]
0x180008df9  lea     r8, [rsp+88h+var_50]
0x180008dfe  mov     edx, 2
0x180008e03  mov     rax, [rax+58h]
0x180008e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0c  mov     edi, eax
0x180008e0e  test    eax, eax
0x180008e10  jns     short loc_180008E3D
0x180008e12  mov     rcx, [rsp+88h]; this
0x180008e1a  mov     r9d, eax; char *
0x180008e1d  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180008e24  mov     edx, 27h ; '''; void *
0x180008e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e2e  nop
0x180008e2f  lea     rcx, [rsp+88h+var_40]; this
0x180008e34  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008e39  mov     eax, edi
0x180008e3b  jmp     short loc_180008EB5
0x180008e3d  mov     rcx, [rsi+18h]
0x180008e41  mov     rax, [rcx]
0x180008e44  lea     r8, [rsp+88h+var_58]
0x180008e49  mov     edx, 3
0x180008e4e  mov     rax, [rax+58h]
0x180008e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e57  mov     edi, eax
0x180008e59  test    eax, eax
0x180008e5b  jns     short loc_180008E88
0x180008e5d  mov     rcx, [rsp+88h]; this
0x180008e65  mov     r9d, eax; char *
0x180008e68  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180008e6f  mov     edx, 28h ; '('; void *
0x180008e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e79  nop
0x180008e7a  lea     rcx, [rsp+88h+var_40]; this
0x180008e7f  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008e84  mov     eax, edi
0x180008e86  jmp     short loc_180008EB5
0x180008e88  mov     r9, [rsp+88h+var_58]; unsigned __int16 *
0x180008e8d  mov     r8, [rsp+88h+var_50]; unsigned __int16 *
0x180008e92  mov     rdx, [rsp+88h+var_48]; unsigned __int16 *
0x180008e97  lea     rcx, [rsp+88h+var_40]; this
0x180008e9c  call    ?Delete@RegistryConfig@@QEAAXPEBG00@Z; RegistryConfig::Delete(ushort const *,ushort const *,ushort const *)
0x180008ea1  nop
0x180008ea2  lea     rcx, [rsp+88h+var_40]; this
0x180008ea7  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008eac  jmp     loc_180008FAC
0x180008eb1  mov     eax, dword ptr [rsp+88h+var_58]
0x180008eb5  mov     rcx, [rsp+88h+var_10]
0x180008eba  xor     rcx, rsp; StackCookie
0x180008ebd  call    __security_check_cookie
0x180008ec2  mov     rsi, [rsp+88h+arg_8]
0x180008eca  add     rsp, 80h
0x180008ed1  pop     rdi
0x180008ed2  retn
0x180008ed3  lea     rcx, [rsp+88h+var_40]; this
0x180008ed8  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180008edd  nop
0x180008ede  mov     [rsp+88h+var_48], 0
0x180008ee7  mov     [rsp+88h+var_50], 0
0x180008ef0  mov     rcx, [rsi+18h]
0x180008ef4  mov     rax, [rcx]
0x180008ef7  lea     r8, [rsp+88h+var_50]
0x180008efc  mov     edx, 1
0x180008f01  mov     rax, [rax+58h]
0x180008f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f0a  mov     edi, eax
0x180008f0c  test    eax, eax
0x180008f0e  jns     short loc_180008F3E
0x180008f10  mov     rcx, [rsp+88h]; this
0x180008f18  mov     r9d, eax; char *
0x180008f1b  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180008f22  mov     edx, 16h; void *
0x180008f27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f2c  nop
0x180008f2d  lea     rcx, [rsp+88h+var_40]; this
0x180008f32  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008f37  mov     eax, edi
0x180008f39  jmp     loc_180008EB5
0x180008f3e  mov     rcx, [rsi+18h]
0x180008f42  mov     rax, [rcx]
0x180008f45  lea     r8, [rsp+88h+var_48]
0x180008f4a  mov     edx, 2
0x180008f4f  mov     rax, [rax+58h]
0x180008f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f58  mov     edi, eax
0x180008f5a  test    eax, eax
0x180008f5c  jns     short loc_180008F8C
0x180008f5e  mov     rcx, [rsp+88h]; this
0x180008f66  mov     r9d, eax; char *
0x180008f69  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180008f70  mov     edx, 17h; void *
0x180008f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f7a  nop
0x180008f7b  lea     rcx, [rsp+88h+var_40]; this
0x180008f80  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008f85  mov     eax, edi
0x180008f87  jmp     loc_180008EB5
0x180008f8c  mov     r8, [rsp+88h+var_48]; unsigned __int16 *
0x180008f91  mov     rdx, [rsp+88h+var_50]; unsigned __int16 *
0x180008f96  lea     rcx, [rsp+88h+var_40]; this
0x180008f9b  call    ?DeleteCommandSet@RegistryConfig@@QEAAXPEBG0@Z; RegistryConfig::DeleteCommandSet(ushort const *,ushort const *)
0x180008fa0  nop
0x180008fa1  lea     rcx, [rsp+88h+var_40]; this
0x180008fa6  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008fab  nop
0x180008fac  xor     eax, eax
0x180008fae  jmp     loc_180008EB5
```
