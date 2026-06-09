# CProvisioningCommandsNode::Clear(void)

- ea: `0x1800090e0`
- end: `0x1800093d4`
- name: `?Clear@CProvisioningCommandsNode@@UEAAJXZ`
- size: `756`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x180004ee4`
- `0x1800090e0`
- `0x18000aa28`
- `0x18000aab0`
- `0x18000b2c0`
- `0x18000b570`
- `0x18000ccc0`
- `0x18000e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=2
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
  HKEY v17[4]; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int16 **v18; // [rsp+68h] [rbp-20h]
  __int64 v19; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned int)dword_180014230 > 4 )
  {
    LODWORD(v14) = *((_DWORD *)this + 11);
    v18 = &v14;
    v19 = 4;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)&dword_180014230,
      (unsigned __int8 *)byte_1800109A1,
      0,
      0,
      3u,
      (PEVENT_DATA_DESCRIPTOR)v17);
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
        RegistryConfig::~RegistryConfig((void **)v17);
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
        RegistryConfig::~RegistryConfig((void **)v17);
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
        RegistryConfig::~RegistryConfig((void **)v17);
        return v8;
      }
      RegistryConfig::Delete(v17, v16, v15, v14);
      RegistryConfig::~RegistryConfig((void **)v17);
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
    RegistryConfig::~RegistryConfig((void **)v17);
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
    RegistryConfig::~RegistryConfig((void **)v17);
    return v12;
  }
  RegistryConfig::DeleteCommandSet(v17, v15, v16);
  RegistryConfig::~RegistryConfig((void **)v17);
  return 0;
}

```

## disassembly

```asm
0x1800090e0  mov     r11, rsp
0x1800090e3  mov     [r11+10h], rsi
0x1800090e7  push    rdi
0x1800090e8  sub     rsp, 80h
0x1800090ef  mov     rax, cs:__security_cookie
0x1800090f6  xor     rax, rsp
0x1800090f9  mov     [rsp+88h+var_10], rax
0x1800090fe  mov     rsi, rcx
0x180009101  mov     eax, cs:dword_180014230
0x180009107  cmp     eax, 4
0x18000910a  jbe     short loc_18000914C
0x18000910c  mov     eax, [rcx+2Ch]
0x18000910f  mov     dword ptr [rsp+88h+var_58], eax
0x180009113  lea     rax, [r11-58h]
0x180009117  mov     [r11-20h], rax
0x18000911b  mov     qword ptr [r11-18h], 4
0x180009123  lea     rax, [r11-40h]
0x180009127  mov     [r11-60h], rax
0x18000912b  mov     [rsp+88h+var_68], 3; int
0x180009133  xor     r9d, r9d
0x180009136  xor     r8d, r8d
0x180009139  lea     rdx, byte_1800109A1
0x180009140  lea     rcx, dword_180014230
0x180009147  call    _tlgWriteTransfer_EventWriteTransfer
0x18000914c  mov     ecx, [rsi+2Ch]
0x18000914f  sub     ecx, 2
0x180009152  jz      loc_1800092F4
0x180009158  sub     ecx, 1
0x18000915b  jz      short loc_18000919E
0x18000915d  sub     ecx, 3
0x180009160  jz      loc_1800092F4
0x180009166  cmp     ecx, 1
0x180009169  jz      short loc_18000919E
0x18000916b  test    byte ptr [rsi+34h], 8
0x18000916f  jnz     loc_1800093CD
0x180009175  mov     rcx, [rsp+88h]; this
0x18000917d  mov     r9d, 86000011h; char *
0x180009183  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x18000918a  mov     edx, 30h ; '0'; void *
0x18000918f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009194  mov     eax, 86000011h
0x180009199  jmp     loc_1800092D5
0x18000919e  lea     rcx, [rsp+88h+var_40]; this
0x1800091a3  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x1800091a8  nop
0x1800091a9  mov     [rsp+88h+var_50], 0
0x1800091b2  mov     [rsp+88h+var_48], 0
0x1800091bb  mov     [rsp+88h+var_58], 0
0x1800091c4  mov     rcx, [rsi+18h]
0x1800091c8  mov     rax, [rcx]
0x1800091cb  lea     r8, [rsp+88h+var_48]
0x1800091d0  mov     edx, 1
0x1800091d5  mov     rax, [rax+58h]
0x1800091d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091de  mov     edi, eax
0x1800091e0  test    eax, eax
0x1800091e2  jns     short loc_180009212
0x1800091e4  mov     rcx, [rsp+88h]; this
0x1800091ec  mov     r9d, eax; char *
0x1800091ef  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x1800091f6  mov     edx, 26h ; '&'; void *
0x1800091fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009200  nop
0x180009201  lea     rcx, [rsp+88h+var_40]; this
0x180009206  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x18000920b  mov     eax, edi
0x18000920d  jmp     loc_1800092D5
0x180009212  mov     rcx, [rsi+18h]
0x180009216  mov     rax, [rcx]
0x180009219  lea     r8, [rsp+88h+var_50]
0x18000921e  mov     edx, 2
0x180009223  mov     rax, [rax+58h]
0x180009227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000922c  mov     edi, eax
0x18000922e  test    eax, eax
0x180009230  jns     short loc_18000925D
0x180009232  mov     rcx, [rsp+88h]; this
0x18000923a  mov     r9d, eax; char *
0x18000923d  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180009244  mov     edx, 27h ; '''; void *
0x180009249  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000924e  nop
0x18000924f  lea     rcx, [rsp+88h+var_40]; this
0x180009254  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180009259  mov     eax, edi
0x18000925b  jmp     short loc_1800092D5
0x18000925d  mov     rcx, [rsi+18h]
0x180009261  mov     rax, [rcx]
0x180009264  lea     r8, [rsp+88h+var_58]
0x180009269  mov     edx, 3
0x18000926e  mov     rax, [rax+58h]
0x180009272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009277  mov     edi, eax
0x180009279  test    eax, eax
0x18000927b  jns     short loc_1800092A8
0x18000927d  mov     rcx, [rsp+88h]; this
0x180009285  mov     r9d, eax; char *
0x180009288  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x18000928f  mov     edx, 28h ; '('; void *
0x180009294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009299  nop
0x18000929a  lea     rcx, [rsp+88h+var_40]; this
0x18000929f  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800092a4  mov     eax, edi
0x1800092a6  jmp     short loc_1800092D5
0x1800092a8  mov     r9, [rsp+88h+var_58]; unsigned __int16 *
0x1800092ad  mov     r8, [rsp+88h+var_50]; unsigned __int16 *
0x1800092b2  mov     rdx, [rsp+88h+var_48]; unsigned __int16 *
0x1800092b7  lea     rcx, [rsp+88h+var_40]; this
0x1800092bc  call    ?Delete@RegistryConfig@@QEAAXPEBG00@Z; RegistryConfig::Delete(ushort const *,ushort const *,ushort const *)
0x1800092c1  nop
0x1800092c2  lea     rcx, [rsp+88h+var_40]; this
0x1800092c7  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800092cc  jmp     loc_1800093CD
0x1800092d1  mov     eax, dword ptr [rsp+88h+var_58]
0x1800092d5  mov     rcx, [rsp+88h+var_10]
0x1800092da  xor     rcx, rsp; StackCookie
0x1800092dd  call    __security_check_cookie
0x1800092e2  mov     rsi, [rsp+88h+arg_8]
0x1800092ea  add     rsp, 80h
0x1800092f1  pop     rdi
0x1800092f2  retn
0x1800092f4  lea     rcx, [rsp+88h+var_40]; this
0x1800092f9  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x1800092fe  nop
0x1800092ff  mov     [rsp+88h+var_48], 0
0x180009308  mov     [rsp+88h+var_50], 0
0x180009311  mov     rcx, [rsi+18h]
0x180009315  mov     rax, [rcx]
0x180009318  lea     r8, [rsp+88h+var_50]
0x18000931d  mov     edx, 1
0x180009322  mov     rax, [rax+58h]
0x180009326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932b  mov     edi, eax
0x18000932d  test    eax, eax
0x18000932f  jns     short loc_18000935F
0x180009331  mov     rcx, [rsp+88h]; this
0x180009339  mov     r9d, eax; char *
0x18000933c  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180009343  mov     edx, 16h; void *
0x180009348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000934d  nop
0x18000934e  lea     rcx, [rsp+88h+var_40]; this
0x180009353  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180009358  mov     eax, edi
0x18000935a  jmp     loc_1800092D5
0x18000935f  mov     rcx, [rsi+18h]
0x180009363  mov     rax, [rcx]
0x180009366  lea     r8, [rsp+88h+var_48]
0x18000936b  mov     edx, 2
0x180009370  mov     rax, [rax+58h]
0x180009374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009379  mov     edi, eax
0x18000937b  test    eax, eax
0x18000937d  jns     short loc_1800093AD
0x18000937f  mov     rcx, [rsp+88h]; this
0x180009387  mov     r9d, eax; char *
0x18000938a  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x180009391  mov     edx, 17h; void *
0x180009396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000939b  nop
0x18000939c  lea     rcx, [rsp+88h+var_40]; this
0x1800093a1  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800093a6  mov     eax, edi
0x1800093a8  jmp     loc_1800092D5
0x1800093ad  mov     r8, [rsp+88h+var_48]; unsigned __int16 *
0x1800093b2  mov     rdx, [rsp+88h+var_50]; unsigned __int16 *
0x1800093b7  lea     rcx, [rsp+88h+var_40]; this
0x1800093bc  call    ?DeleteCommandSet@RegistryConfig@@QEAAXPEBG0@Z; RegistryConfig::DeleteCommandSet(ushort const *,ushort const *)
0x1800093c1  nop
0x1800093c2  lea     rcx, [rsp+88h+var_40]; this
0x1800093c7  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800093cc  nop
0x1800093cd  xor     eax, eax
0x1800093cf  jmp     loc_1800092D5
```
