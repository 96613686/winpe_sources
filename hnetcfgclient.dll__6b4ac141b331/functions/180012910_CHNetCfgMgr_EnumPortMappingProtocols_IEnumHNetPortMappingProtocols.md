# CHNetCfgMgr::EnumPortMappingProtocols(IEnumHNetPortMappingProtocols * *)

- ea: `0x180012910`
- end: `0x180012c18`
- name: `?EnumPortMappingProtocols@CHNetCfgMgr@@UEAAJPEAPEAUIEnumHNetPortMappingProtocols@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(CHNetCfgMgr *__hidden this, struct IEnumHNetPortMappingProtocols **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000f910`
- `0x180012910`
- `0x180015b60`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012a1e`
- `OLEAUT32!__imp_SysAllocString` at `0x180012a1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ac1`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ac1`

## string_xrefs

- `0x180012a10`: `HNet_PortMappingProtocol`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::EnumPortMappingProtocols(CHNetCfgMgr *this, struct IEnumHNetPortMappingProtocols **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  BSTR v8; // rax
  OLECHAR *v9; // rdi
  int v10; // eax
  int v11; // eax
  volatile int *v12; // rdi
  int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  volatile int *v17; // [rsp+70h] [rbp+18h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 270, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)this + 8) )
  {
    v5 = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_d(v4[2], 271, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v6 = 272;
LABEL_54:
        WPP_SF_d(v4[2], v6, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v5);
        return v5;
      }
    }
    return v5;
  }
  if ( a2 )
  {
    *a2 = 0;
    v8 = SysAllocString(L"HNet_PortMappingProtocol");
    v9 = v8;
    if ( !v8 )
    {
      v5 = -2147024882;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v5;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_50;
      v7 = 274;
      goto LABEL_19;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64))(**((_QWORD **)this + 8) + 144LL))(
            *((_QWORD *)this + 8),
            v8,
            16);
    v5 = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        275,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v10);
    }
    SysFreeString(v9);
    if ( v5 )
      goto LABEL_49;
    v17 = 0;
    v11 = ATL::CComObject<CHNCEnum<IEnumHNetPortMappingProtocols,IHNetPortMappingProtocol,CHNetPortMappingProtocol>>::CreateInstance(&v17);
    v5 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          276,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v11);
      }
      goto LABEL_48;
    }
    v12 = v17;
    (*(void (__fastcall **)(volatile int *))(*(_QWORD *)v17 + 8LL))(v17);
    v13 = CHNCEnum<IEnumHNetPortMappingBindings,IHNetPortMappingBinding,CHNetPortMappingBinding>::Initialize(
            v12,
            *((_QWORD *)this + 8),
            0);
    v5 = v13;
    if ( v13 >= 0 )
    {
      v13 = (**(__int64 (__fastcall ***)(volatile int *, GUID *, struct IEnumHNetPortMappingProtocols **))v12)(
              v12,
              &GUID_85d18b7c_3032_11d4_9348_00c04f8eeb71,
              a2);
      v5 = v13;
      if ( v13 >= 0 )
        goto LABEL_47;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v15 = 278;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      v15 = 277;
    }
    WPP_SF_d(v14[2], v15, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v13);
LABEL_47:
    (*(void (__fastcall **)(volatile int *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_48:
    (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
    goto LABEL_49;
  }
  v5 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 8) == 0 || *((_BYTE *)v4 + 25) < 2u )
    goto LABEL_50;
  v7 = 273;
LABEL_19:
  WPP_SF_d(v4[2], v7, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v5);
LABEL_49:
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_50:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v6 = 279;
    goto LABEL_54;
  }
  return v5;
}

```

## disassembly

```asm
0x180012910  mov     [rsp+arg_8], rbx
0x180012915  push    rbp
0x180012916  push    rsi
0x180012917  push    rdi
0x180012918  push    r12
0x18001291a  push    r13
0x18001291c  sub     rsp, 30h
0x180012920  mov     rsi, rdx
0x180012923  mov     rbp, rcx
0x180012926  mov     rcx, cs:WPP_GLOBAL_Control
0x18001292d  lea     r12, WPP_GLOBAL_Control
0x180012934  lea     r13, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001293b  cmp     rcx, r12
0x18001293e  jz      short loc_180012964
0x180012940  test    byte ptr [rcx+1Ch], 8
0x180012944  jz      short loc_180012964
0x180012946  cmp     byte ptr [rcx+19h], 6
0x18001294a  jb      short loc_180012964
0x18001294c  mov     rcx, [rcx+10h]
0x180012950  mov     edx, 10Eh
0x180012955  mov     r8, r13
0x180012958  call    WPP_SF_
0x18001295d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012964  cmp     qword ptr [rbp+40h], 0
0x180012969  mov     [rsp+58h+arg_0], 0
0x180012972  jnz     short loc_1800129D0
0x180012974  mov     ebx, 80004003h
0x180012979  cmp     rcx, r12
0x18001297c  jz      loc_180012C05
0x180012982  test    byte ptr [rcx+1Ch], 8
0x180012986  jz      short loc_1800129A9
0x180012988  cmp     byte ptr [rcx+19h], 2
0x18001298c  jb      short loc_1800129A9
0x18001298e  mov     rcx, [rcx+10h]
0x180012992  mov     edx, 10Fh
0x180012997  mov     r9d, ebx
0x18001299a  mov     r8, r13
0x18001299d  call    WPP_SF_d
0x1800129a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129a9  cmp     rcx, r12
0x1800129ac  jz      loc_180012C05
0x1800129b2  test    byte ptr [rcx+1Ch], 8
0x1800129b6  jz      loc_180012C05
0x1800129bc  cmp     byte ptr [rcx+19h], 6
0x1800129c0  jb      loc_180012C05
0x1800129c6  mov     edx, 110h
0x1800129cb  jmp     loc_180012BF6
0x1800129d0  test    rsi, rsi
0x1800129d3  jnz     short loc_180012A10
0x1800129d5  mov     ebx, 80004003h
0x1800129da  cmp     rcx, r12
0x1800129dd  jz      loc_180012C05
0x1800129e3  test    byte ptr [rcx+1Ch], 8
0x1800129e7  jz      loc_180012BE0
0x1800129ed  cmp     byte ptr [rcx+19h], 2
0x1800129f1  jb      loc_180012BE0
0x1800129f7  mov     edx, 111h
0x1800129fc  mov     rcx, [rcx+10h]
0x180012a00  mov     r9d, ebx
0x180012a03  mov     r8, r13
0x180012a06  call    WPP_SF_d
0x180012a0b  jmp     loc_180012BD9
0x180012a10  lea     rcx, ?c_wszHnetPortMappingProtocol@@3QBGB; "HNet_PortMappingProtocol"
0x180012a17  mov     qword ptr [rsi], 0
0x180012a1e  call    cs:__imp_SysAllocString
0x180012a24  mov     rdi, rax
0x180012a27  test    rax, rax
0x180012a2a  jnz     short loc_180012A5C
0x180012a2c  mov     ebx, 8007000Eh
0x180012a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a38  cmp     rcx, r12
0x180012a3b  jz      loc_180012C05
0x180012a41  test    byte ptr [rcx+1Ch], 8
0x180012a45  jz      loc_180012BE0
0x180012a4b  cmp     byte ptr [rcx+19h], 2
0x180012a4f  jb      loc_180012BE0
0x180012a55  mov     edx, 112h
0x180012a5a  jmp     short loc_1800129FC
0x180012a5c  mov     rcx, [rbp+40h]
0x180012a60  lea     rdx, [rsp+58h+arg_0]
0x180012a65  mov     [rsp+58h+arg_0], 0
0x180012a6e  xor     r9d, r9d
0x180012a71  mov     [rsp+58h+var_38], rdx
0x180012a76  mov     rdx, rdi
0x180012a79  mov     rax, [rcx]
0x180012a7c  lea     r8d, [r9+10h]
0x180012a80  mov     rax, [rax+90h]
0x180012a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a8c  mov     ebx, eax
0x180012a8e  test    eax, eax
0x180012a90  jns     short loc_180012ABE
0x180012a92  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a99  cmp     rcx, r12
0x180012a9c  jz      short loc_180012ABE
0x180012a9e  test    byte ptr [rcx+1Ch], 8
0x180012aa2  jz      short loc_180012ABE
0x180012aa4  cmp     byte ptr [rcx+19h], 2
0x180012aa8  jb      short loc_180012ABE
0x180012aaa  mov     rcx, [rcx+10h]
0x180012aae  mov     edx, 113h
0x180012ab3  mov     r9d, eax
0x180012ab6  mov     r8, r13
0x180012ab9  call    WPP_SF_d
0x180012abe  mov     rcx, rdi; bstrString
0x180012ac1  call    cs:__imp_SysFreeString
0x180012ac7  test    ebx, ebx
0x180012ac9  jnz     loc_180012BD9
0x180012acf  lea     rcx, [rsp+58h+arg_10]
0x180012ad4  mov     [rsp+58h+arg_10], 0
0x180012add  call    ?CreateInstance@?$CComObject@V?$CHNCEnum@UIEnumHNetPortMappingProtocols@@UIHNetPortMappingProtocol@@VCHNetPortMappingProtocol@@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CHNCEnum<IEnumHNetPortMappingProtocols,IHNetPortMappingProtocol,CHNetPortMappingProtocol>>::CreateInstance(ATL::CComObject<CHNCEnum<IEnumHNetPortMappingProtocols,IHNetPortMappingProtocol,CHNetPortMappingProtocol>> * *)
0x180012ae2  mov     ebx, eax
0x180012ae4  test    eax, eax
0x180012ae6  jns     short loc_180012B25
0x180012ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012aef  cmp     rcx, r12
0x180012af2  jz      loc_180012BC8
0x180012af8  test    byte ptr [rcx+1Ch], 8
0x180012afc  jz      loc_180012BC8
0x180012b02  cmp     byte ptr [rcx+19h], 2
0x180012b06  jb      loc_180012BC8
0x180012b0c  mov     rcx, [rcx+10h]
0x180012b10  mov     edx, 114h
0x180012b15  mov     r9d, eax
0x180012b18  mov     r8, r13
0x180012b1b  call    WPP_SF_d
0x180012b20  jmp     loc_180012BC8
0x180012b25  mov     rdi, [rsp+58h+arg_10]
0x180012b2a  mov     rcx, rdi
0x180012b2d  mov     rax, [rdi]
0x180012b30  mov     rax, [rax+8]
0x180012b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b39  mov     r8, [rsp+58h+arg_0]
0x180012b3e  mov     rcx, rdi
0x180012b41  mov     rdx, [rbp+40h]
0x180012b45  call    ?Initialize@?$CHNCEnum@UIEnumHNetPortMappingBindings@@UIHNetPortMappingBinding@@VCHNetPortMappingBinding@@@@QEAAJPEAUIWbemServices@@PEAUIEnumWbemClassObject@@@Z; CHNCEnum<IEnumHNetPortMappingBindings,IHNetPortMappingBinding,CHNetPortMappingBinding>::Initialize(IWbemServices *,IEnumWbemClassObject *)
0x180012b4a  mov     ebx, eax
0x180012b4c  test    eax, eax
0x180012b4e  jns     short loc_180012B6F
0x180012b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b57  cmp     rcx, r12
0x180012b5a  jz      short loc_180012BB9
0x180012b5c  test    byte ptr [rcx+1Ch], 8
0x180012b60  jz      short loc_180012BB9
0x180012b62  cmp     byte ptr [rcx+19h], 2
0x180012b66  jb      short loc_180012BB9
0x180012b68  mov     edx, 115h
0x180012b6d  jmp     short loc_180012BAA
0x180012b6f  mov     rax, [rdi]
0x180012b72  lea     rdx, _GUID_85d18b7c_3032_11d4_9348_00c04f8eeb71
0x180012b79  mov     r8, rsi
0x180012b7c  mov     rcx, rdi
0x180012b7f  mov     rax, [rax]
0x180012b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b87  mov     ebx, eax
0x180012b89  test    eax, eax
0x180012b8b  jns     short loc_180012BB9
0x180012b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b94  cmp     rcx, r12
0x180012b97  jz      short loc_180012BB9
0x180012b99  test    byte ptr [rcx+1Ch], 8
0x180012b9d  jz      short loc_180012BB9
0x180012b9f  cmp     byte ptr [rcx+19h], 2
0x180012ba3  jb      short loc_180012BB9
0x180012ba5  mov     edx, 116h
0x180012baa  mov     rcx, [rcx+10h]
0x180012bae  mov     r9d, eax
0x180012bb1  mov     r8, r13
0x180012bb4  call    WPP_SF_d
0x180012bb9  mov     rax, [rdi]
0x180012bbc  mov     rcx, rdi
0x180012bbf  mov     rax, [rax+10h]
0x180012bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bc8  mov     rcx, [rsp+58h+arg_0]
0x180012bcd  mov     rax, [rcx]
0x180012bd0  mov     rax, [rax+10h]
0x180012bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012be0  cmp     rcx, r12
0x180012be3  jz      short loc_180012C05
0x180012be5  test    byte ptr [rcx+1Ch], 8
0x180012be9  jz      short loc_180012C05
0x180012beb  cmp     byte ptr [rcx+19h], 6
0x180012bef  jb      short loc_180012C05
0x180012bf1  mov     edx, 117h
0x180012bf6  mov     rcx, [rcx+10h]
0x180012bfa  mov     r9d, ebx
0x180012bfd  mov     r8, r13
0x180012c00  call    WPP_SF_d
0x180012c05  mov     eax, ebx
0x180012c07  mov     rbx, [rsp+58h+arg_8]
0x180012c0c  add     rsp, 30h
0x180012c10  pop     r13
0x180012c12  pop     r12
0x180012c14  pop     rdi
0x180012c15  pop     rsi
0x180012c16  pop     rbp
0x180012c17  retn
```
