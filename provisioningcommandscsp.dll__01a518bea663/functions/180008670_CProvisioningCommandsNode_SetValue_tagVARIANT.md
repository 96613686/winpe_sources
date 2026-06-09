# CProvisioningCommandsNode::SetValue(tagVARIANT)

- ea: `0x180008670`
- end: `0x180008996`
- name: `?SetValue@CProvisioningCommandsNode@@UEAAJUtagVARIANT@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x180004da4`
- `0x180007c18`
- `0x180008644`
- `0x180008670`
- `0x18000a4d4`
- `0x18000a550`
- `0x18000aa94`
- `0x18000c600`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000894b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000894b`

## pseudocode

```c
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
  _BYTE v18[40]; // [rsp+68h] [rbp-90h] BYREF
  BYTE *v19[2]; // [rsp+90h] [rbp-68h] BYREF
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
    lpValueName = 3;
    tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_18001092B, 0, 0);
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
      LOWORD(v19[0]) = 0;
      std::wstring::assign(v19, a2->bstrVal);
      lpData = (BYTE *)v19;
      if ( v21 >= 8 )
        lpData = v19[0];
      RegistryConfig::AddCommandSetting((RegistryConfig *)v18, v16, v15, v14, v17, 1u, lpData, 2 * v20 + 2);
      CreateProvCommandResultRecord(v16, v15, v14);
      if ( v21 >= 8 )
        operator delete(v19[0]);
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
      RegistryConfig::AddCommandSetting((RegistryConfig *)v18, v16, v15, v14, v17, 4u, Data, 4u);
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
0x180008670  mov     r11, rsp
0x180008673  mov     [r11+18h], rbx
0x180008677  push    rsi
0x180008678  push    rdi
0x180008679  push    r12
0x18000867b  push    r14
0x18000867d  push    r15
0x18000867f  sub     rsp, 0D0h
0x180008686  mov     rax, cs:__security_cookie
0x18000868d  xor     rax, rsp
0x180008690  mov     [rsp+0F8h+var_38], rax
0x180008698  mov     r15, rdx
0x18000869b  mov     r14, rcx
0x18000869e  mov     eax, cs:dword_180014230
0x1800086a4  mov     r12d, 4
0x1800086aa  cmp     eax, r12d
0x1800086ad  jbe     short loc_1800086F1
0x1800086af  mov     eax, [rcx+2Ch]
0x1800086b2  mov     dword ptr [rsp+0F8h+Data], eax
0x1800086b6  lea     rax, [rsp+0F8h+Data]
0x1800086bb  mov     [r11-48h], rax
0x1800086bf  mov     [r11-40h], r12
0x1800086c3  xor     ebx, ebx
0x1800086c5  lea     rax, [r11-68h]
0x1800086c9  mov     qword ptr [rsp+0F8h+dwType], rax
0x1800086ce  mov     dword ptr [rsp+0F8h+lpValueName], 3
0x1800086d6  xor     r9d, r9d
0x1800086d9  xor     r8d, r8d
0x1800086dc  lea     rdx, byte_18001092B
0x1800086e3  lea     rcx, dword_180014230
0x1800086ea  call    _tlgWriteTransfer_EventWriteTransfer
0x1800086ef  jmp     short loc_1800086F3
0x1800086f1  xor     ebx, ebx
0x1800086f3  lea     rcx, [rsp+0F8h+var_90]; this
0x1800086f8  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x1800086fd  nop
0x1800086fe  mov     [rsp+0F8h+var_A8], rbx
0x180008703  mov     [rsp+0F8h+var_B0], rbx
0x180008708  mov     [rsp+0F8h+var_A0], rbx
0x18000870d  mov     [rsp+0F8h+var_98], rbx
0x180008712  mov     rcx, [r14+18h]
0x180008716  mov     rax, [rcx]
0x180008719  lea     r8, [rsp+0F8h+var_A0]
0x18000871e  mov     edx, 1
0x180008723  mov     rax, [rax+58h]
0x180008727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872c  mov     edi, eax
0x18000872e  test    eax, eax
0x180008730  jns     short loc_180008739
0x180008732  mov     edx, 4Ch ; 'L'
0x180008737  jmp     short loc_1800087AA
0x180008739  mov     rcx, [r14+18h]
0x18000873d  mov     rax, [rcx]
0x180008740  lea     r8, [rsp+0F8h+var_A8]
0x180008745  mov     edx, 2
0x18000874a  mov     rax, [rax+58h]
0x18000874e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008753  mov     edi, eax
0x180008755  test    eax, eax
0x180008757  jns     short loc_180008760
0x180008759  mov     edx, 4Dh ; 'M'
0x18000875e  jmp     short loc_1800087AA
0x180008760  mov     rcx, [r14+18h]
0x180008764  mov     rax, [rcx]
0x180008767  lea     r8, [rsp+0F8h+var_B0]
0x18000876c  mov     edx, 3
0x180008771  mov     rax, [rax+58h]
0x180008775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000877a  mov     edi, eax
0x18000877c  test    eax, eax
0x18000877e  jns     short loc_180008787
0x180008780  mov     edx, 4Eh ; 'N'
0x180008785  jmp     short loc_1800087AA
0x180008787  mov     rcx, [r14+18h]
0x18000878b  mov     rax, [rcx]
0x18000878e  lea     r8, [rsp+0F8h+var_98]
0x180008793  mov     edx, r12d
0x180008796  mov     rax, [rax+58h]
0x18000879a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000879f  mov     edi, eax
0x1800087a1  test    eax, eax
0x1800087a3  jns     short loc_1800087D3
0x1800087a5  mov     edx, 4Fh ; 'O'; void *
0x1800087aa  mov     r9d, eax; char *
0x1800087ad  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x1800087b4  mov     rcx, [rsp+0F8h]; this
0x1800087bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087c1  nop
0x1800087c2  lea     rcx, [rsp+0F8h+var_90]; this
0x1800087c7  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800087cc  mov     eax, edi
0x1800087ce  jmp     loc_18000896E
0x1800087d3  mov     ecx, [r14+2Ch]
0x1800087d7  sub     ecx, r12d
0x1800087da  jz      loc_180008896
0x1800087e0  sub     ecx, r12d
0x1800087e3  jz      loc_180008896
0x1800087e9  sub     ecx, 1
0x1800087ec  jz      short loc_180008852
0x1800087ee  sub     ecx, 1
0x1800087f1  jz      short loc_180008852
0x1800087f3  sub     ecx, 1
0x1800087f6  jz      short loc_180008843
0x1800087f8  cmp     ecx, 1
0x1800087fb  jz      short loc_180008843
0x1800087fd  mov     eax, [r14+34h]
0x180008801  and     al, 2
0x180008803  neg     al
0x180008805  sbb     ebx, ebx
0x180008807  and     ebx, 0FA003FF0h
0x18000880d  mov     rcx, [rsp+0F8h]; this
0x180008815  lea     r9d, [rbx-79FFFFEFh]; char *
0x18000881c  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x180008823  mov     edx, 80h; void *
0x180008828  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000882d  nop
0x18000882e  lea     rcx, [rsp+0F8h+var_90]; this
0x180008833  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180008838  lea     eax, [rbx-79FFFFEFh]
0x18000883e  jmp     loc_18000896E
0x180008843  cmp     word ptr [r15+8], 0FFFFh
0x180008849  setz    bl
0x18000884c  mov     dword ptr [rsp+0F8h+Data], ebx
0x180008850  jmp     short loc_18000885A
0x180008852  mov     eax, [r15+8]
0x180008856  mov     dword ptr [rsp+0F8h+Data], eax
0x18000885a  mov     qword ptr [rsp+0F8h+var_C0], r12; DWORD
0x18000885f  lea     rax, [rsp+0F8h+Data]
0x180008864  mov     [rsp+0F8h+lpData], rax; lpData
0x180008869  mov     [rsp+0F8h+dwType], r12d; dwType
0x18000886e  mov     rax, [rsp+0F8h+var_98]
0x180008873  mov     [rsp+0F8h+lpValueName], rax; lpValueName
0x180008878  mov     r9, [rsp+0F8h+var_B0]; unsigned __int16 *
0x18000887d  mov     r8, [rsp+0F8h+var_A8]; unsigned __int16 *
0x180008882  mov     rdx, [rsp+0F8h+var_A0]; unsigned __int16 *
0x180008887  lea     rcx, [rsp+0F8h+var_90]; this
0x18000888c  call    ?AddCommandSetting@RegistryConfig@@QEAAXPEBG000KPEBE_K@Z; RegistryConfig::AddCommandSetting(ushort const *,ushort const *,ushort const *,ushort const *,ulong,uchar const *,unsigned __int64)
0x180008891  jmp     loc_180008952
0x180008896  mov     [rsp+0F8h+var_50], 7
0x1800088a2  mov     [rsp+0F8h+var_58], rbx
0x1800088aa  mov     word ptr [rsp+0F8h+var_68], bx
0x1800088b2  mov     rdx, [r15+8]; Src
0x1800088b6  lea     rcx, [rsp+0F8h+var_68]; void *
0x1800088be  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800088c3  nop
0x1800088c4  mov     rax, [rsp+0F8h+var_58]
0x1800088cc  lea     rcx, [rsp+0F8h+var_68]
0x1800088d4  cmp     [rsp+0F8h+var_50], 8
0x1800088dd  cmovnb  rcx, [rsp+0F8h+var_68]
0x1800088e6  lea     rax, ds:2[rax*2]
0x1800088ee  mov     qword ptr [rsp+0F8h+var_C0], rax; DWORD
0x1800088f3  mov     [rsp+0F8h+lpData], rcx; lpData
0x1800088f8  mov     [rsp+0F8h+dwType], 1; dwType
0x180008900  mov     rax, [rsp+0F8h+var_98]
0x180008905  mov     [rsp+0F8h+lpValueName], rax; lpValueName
0x18000890a  mov     r9, [rsp+0F8h+var_B0]; unsigned __int16 *
0x18000890f  mov     r8, [rsp+0F8h+var_A8]; unsigned __int16 *
0x180008914  mov     rdx, [rsp+0F8h+var_A0]; unsigned __int16 *
0x180008919  lea     rcx, [rsp+0F8h+var_90]; this
0x18000891e  call    ?AddCommandSetting@RegistryConfig@@QEAAXPEBG000KPEBE_K@Z; RegistryConfig::AddCommandSetting(ushort const *,ushort const *,ushort const *,ushort const *,ulong,uchar const *,unsigned __int64)
0x180008923  mov     r8, [rsp+0F8h+var_B0]; unsigned __int16 *
0x180008928  mov     rdx, [rsp+0F8h+var_A8]; unsigned __int16 *
0x18000892d  mov     rcx, [rsp+0F8h+var_A0]; unsigned __int16 *
0x180008932  call    ?CreateProvCommandResultRecord@@YAJPEBG00@Z; CreateProvCommandResultRecord(ushort const *,ushort const *,ushort const *)
0x180008937  nop
0x180008938  cmp     [rsp+0F8h+var_50], 8
0x180008941  jb      short loc_180008952
0x180008943  mov     rcx, [rsp+0F8h+var_68]
0x18000894b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008951  nop
0x180008952  lea     rcx, [rsp+0F8h+var_90]; this
0x180008957  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x18000895c  xor     eax, eax
0x18000895e  jmp     short loc_18000896E
0x180008960  lea     rcx, [rsp+0F8h+var_90]; this
0x180008965  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x18000896a  mov     eax, dword ptr [rsp+0F8h+Data]
0x18000896e  mov     rcx, [rsp+0F8h+var_38]
0x180008976  xor     rcx, rsp; StackCookie
0x180008979  call    __security_check_cookie
0x18000897e  mov     rbx, [rsp+0F8h+arg_10]
0x180008986  add     rsp, 0D0h
0x18000898d  pop     r15
0x18000898f  pop     r14
0x180008991  pop     r12
0x180008993  pop     rdi
0x180008994  pop     rsi
0x180008995  retn
```
