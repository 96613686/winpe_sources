# CDynamicManagementNode::GetAllContextChildNodes(ushort const *,ushort const *,ulong *,ushort * * *)

- ea: `0x1800c03e4`
- end: `0x1800c0696`
- name: `?GetAllContextChildNodes@CDynamicManagementNode@@IEAAJPEBG0PEAKPEAPEAPEAG@Z`
- size: `690`
- prototype: `__int64 __fastcall(CDynamicManagementNode *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c06a0`

## callees

- `0x180025a78`
- `0x18002dc38`
- `0x1800c03e4`
- `0x1800e3b48`
- `0x1800e3edc`
- `0x1800e438c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800c046b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c0481`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c04de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c0555`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c05c7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c046b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c0481`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c04de`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c0555`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c05c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c062b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0656`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c062b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c0656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c0642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800c04c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800c053f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800c05b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800c04c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800c053f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800c05b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c043b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c043b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDynamicManagementNode::GetAllContextChildNodes(
        CDynamicManagementNode *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  unsigned int *v5; // r13
  unsigned __int16 ***v8; // r12
  _OWORD *v9; // rax
  _QWORD *v10; // rbx
  unsigned int v12; // edi
  const unsigned __int16 *v13; // rdx
  _QWORD *v14; // r13
  BSTR v15; // rax
  OLECHAR *v16; // rsi
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdx
  _QWORD *v19; // r12
  BSTR v20; // rax
  _QWORD *v21; // r14
  BSTR v22; // rax
  _QWORD *v23; // r15
  __int64 v24; // r14
  OLECHAR *v25; // rcx
  unsigned __int16 *v26[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v27; // [rsp+70h] [rbp+40h] BYREF
  unsigned int *v28; // [rsp+88h] [rbp+58h] BYREF

  v28 = a4;
  v27 = (unsigned __int16 *)this;
  v5 = a4;
  if ( a4 )
  {
    v8 = a5;
    if ( a5 )
    {
      if ( a3 && a2 )
      {
        v9 = CoTaskMemAlloc(0x10u);
        v10 = v9;
        if ( !v9 )
          return 2147942414LL;
        v12 = 2;
        *v9 = 0;
        *(_QWORD *)v9 = SysAllocString(L"SettingsPackResponse");
        v10[1] = SysAllocString(L"ContextStatus");
        v26[0] = 0;
        v27 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          v26,
          0);
        if ( (unsigned int)DynamoGetSettingsPack(a2, v13, a3, v26) != -2147024894 )
        {
          v14 = CoTaskMemRealloc(v10, 0x18u);
          v15 = SysAllocString(L"SettingsPack");
          v16 = v15;
          if ( !v14 || !v15 )
          {
            v23 = v10;
            v24 = 0;
            goto LABEL_23;
          }
          v10 = v14;
          v14[2] = v15;
          v12 = 3;
          v5 = v28;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v27,
          0);
        if ( (unsigned int)DynamoGetSignalDefinition(a2, v17, a3, &v27) != -2147024894 )
        {
          LODWORD(v28) = v12 + 1;
          v19 = CoTaskMemRealloc(v10, 8LL * (v12 + 1));
          v20 = SysAllocString(L"SignalDefinition");
          v16 = v20;
          if ( !v19 || !v20 )
            goto LABEL_21;
          v10 = v19;
          v19[v12] = v20;
          v12 = (unsigned int)v28;
          v8 = a5;
        }
        LODWORD(v28) = 0;
        if ( (unsigned int)DynamoGetAltitude(a2, v18, a3, (int *)&v28) == -2147024894 )
        {
LABEL_19:
          *v5 = v12;
          *v8 = (unsigned __int16 **)v10;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v26);
          return 0;
        }
        v21 = CoTaskMemRealloc(v10, 8LL * (v12 + 1));
        v22 = SysAllocString(L"Altitude");
        v16 = v22;
        if ( v21 && v22 )
        {
          v10 = v21;
          v21[v12++] = v22;
          goto LABEL_19;
        }
LABEL_21:
        if ( !v10 )
        {
LABEL_27:
          if ( v16 )
            SysFreeString(v16);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v26);
          return 2147942414LL;
        }
        v23 = v10;
        v24 = 0;
        if ( !v12 )
        {
LABEL_26:
          CoTaskMemFree(v10);
          goto LABEL_27;
        }
        do
        {
LABEL_23:
          v25 = (OLECHAR *)v23[v24];
          if ( v25 )
            SysFreeString(v25);
          v24 = (unsigned int)(v24 + 1);
        }
        while ( (unsigned int)v24 < v12 );
        goto LABEL_26;
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800c03e4  mov     [rsp-38h+arg_8], rbx
0x1800c03e9  mov     [rsp-38h+arg_18], r9
0x1800c03ee  mov     [rsp-38h+arg_0], rcx
0x1800c03f3  push    rbp
0x1800c03f4  push    rsi
0x1800c03f5  push    rdi
0x1800c03f6  push    r12
0x1800c03f8  push    r13
0x1800c03fa  push    r14
0x1800c03fc  push    r15
0x1800c03fe  mov     rbp, rsp
0x1800c0401  sub     rsp, 30h
0x1800c0405  mov     r13, r9
0x1800c0408  mov     r14, r8
0x1800c040b  mov     r15, rdx
0x1800c040e  test    r9, r9
0x1800c0411  jz      loc_1800C067B
0x1800c0417  mov     r12, [rbp+arg_20]
0x1800c041b  test    r12, r12
0x1800c041e  jz      loc_1800C067B
0x1800c0424  test    r8, r8
0x1800c0427  jz      loc_1800C067B
0x1800c042d  test    rdx, rdx
0x1800c0430  jz      loc_1800C067B
0x1800c0436  mov     ecx, 10h; cb
0x1800c043b  call    cs:__imp_CoTaskMemAlloc
0x1800c0442  nop     dword ptr [rax+rax+00h]
0x1800c0447  mov     rbx, rax
0x1800c044a  test    rax, rax
0x1800c044d  jnz     short loc_1800C0459
0x1800c044f  mov     eax, 8007000Eh
0x1800c0454  jmp     loc_1800C0680
0x1800c0459  mov     edi, 2
0x1800c045e  xorps   xmm0, xmm0
0x1800c0461  movups  xmmword ptr [rax], xmm0
0x1800c0464  lea     rcx, aSettingspackre; "SettingsPackResponse"
0x1800c046b  call    cs:__imp_SysAllocString
0x1800c0472  nop     dword ptr [rax+rax+00h]
0x1800c0477  mov     [rbx], rax
0x1800c047a  lea     rcx, aContextstatus; "ContextStatus"
0x1800c0481  call    cs:__imp_SysAllocString
0x1800c0488  nop     dword ptr [rax+rax+00h]
0x1800c048d  mov     [rbx+8], rax
0x1800c0491  mov     [rbp+var_10], 0
0x1800c0499  mov     [rbp+arg_0], 0
0x1800c04a1  xor     edx, edx
0x1800c04a3  lea     rcx, [rbp+var_10]
0x1800c04a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c04ac  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800c04b0  mov     r8, r14; unsigned __int16 *
0x1800c04b3  mov     rcx, r15; unsigned __int16 *
0x1800c04b6  call    ?DynamoGetSettingsPack@@YAJPEBG00PEAPEAG@Z; DynamoGetSettingsPack(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800c04bb  cmp     eax, 80070002h
0x1800c04c0  jz      short loc_1800C050F
0x1800c04c2  lea     edx, [rdi+16h]; cb
0x1800c04c5  mov     rcx, rbx; pv
0x1800c04c8  call    cs:__imp_CoTaskMemRealloc
0x1800c04cf  nop     dword ptr [rax+rax+00h]
0x1800c04d4  mov     r13, rax
0x1800c04d7  lea     rcx, aSettingspack; "SettingsPack"
0x1800c04de  call    cs:__imp_SysAllocString
0x1800c04e5  nop     dword ptr [rax+rax+00h]
0x1800c04ea  mov     rsi, rax
0x1800c04ed  test    r13, r13
0x1800c04f0  jz      loc_1800C060B
0x1800c04f6  test    rax, rax
0x1800c04f9  jz      loc_1800C060B
0x1800c04ff  mov     rbx, r13
0x1800c0502  mov     [r13+10h], rax
0x1800c0506  mov     edi, 3
0x1800c050b  mov     r13, [rbp+arg_18]
0x1800c050f  xor     edx, edx
0x1800c0511  lea     rcx, [rbp+arg_0]
0x1800c0515  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c051a  lea     r9, [rbp+arg_0]; unsigned __int16 **
0x1800c051e  mov     r8, r14; unsigned __int16 *
0x1800c0521  mov     rcx, r15; unsigned __int16 *
0x1800c0524  call    ?DynamoGetSignalDefinition@@YAJPEBG00PEAPEAG@Z; DynamoGetSignalDefinition(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800c0529  cmp     eax, 80070002h
0x1800c052e  jz      short loc_1800C0586
0x1800c0530  lea     eax, [rdi+1]
0x1800c0533  mov     dword ptr [rbp+arg_18], eax
0x1800c0536  mov     edx, eax
0x1800c0538  shl     rdx, 3; cb
0x1800c053c  mov     rcx, rbx; pv
0x1800c053f  call    cs:__imp_CoTaskMemRealloc
0x1800c0546  nop     dword ptr [rax+rax+00h]
0x1800c054b  mov     r12, rax
0x1800c054e  lea     rcx, aSignaldefiniti; "SignalDefinition"
0x1800c0555  call    cs:__imp_SysAllocString
0x1800c055c  nop     dword ptr [rax+rax+00h]
0x1800c0561  mov     rsi, rax
0x1800c0564  test    r12, r12
0x1800c0567  jz      loc_1800C0613
0x1800c056d  test    rax, rax
0x1800c0570  jz      loc_1800C0613
0x1800c0576  mov     rbx, r12
0x1800c0579  mov     ecx, edi
0x1800c057b  mov     [r12+rcx*8], rax
0x1800c057f  mov     edi, dword ptr [rbp+arg_18]
0x1800c0582  mov     r12, [rbp+arg_20]
0x1800c0586  mov     dword ptr [rbp+arg_18], 0
0x1800c058d  lea     r9, [rbp+arg_18]; int *
0x1800c0591  mov     r8, r14; unsigned __int16 *
0x1800c0594  mov     rcx, r15; unsigned __int16 *
0x1800c0597  call    ?DynamoGetAltitude@@YAJPEBG00PEAH@Z; DynamoGetAltitude(ushort const *,ushort const *,ushort const *,int *)
0x1800c059c  cmp     eax, 80070002h
0x1800c05a1  jz      short loc_1800C05EC
0x1800c05a3  lea     r15d, [rdi+1]
0x1800c05a7  mov     edx, r15d
0x1800c05aa  shl     rdx, 3; cb
0x1800c05ae  mov     rcx, rbx; pv
0x1800c05b1  call    cs:__imp_CoTaskMemRealloc
0x1800c05b8  nop     dword ptr [rax+rax+00h]
0x1800c05bd  mov     r14, rax
0x1800c05c0  lea     rcx, aAltitude; "Altitude"
0x1800c05c7  call    cs:__imp_SysAllocString
0x1800c05ce  nop     dword ptr [rax+rax+00h]
0x1800c05d3  mov     rsi, rax
0x1800c05d6  test    r14, r14
0x1800c05d9  jz      short loc_1800C0613
0x1800c05db  test    rax, rax
0x1800c05de  jz      short loc_1800C0613
0x1800c05e0  mov     rbx, r14
0x1800c05e3  mov     ecx, edi
0x1800c05e5  mov     [r14+rcx*8], rax
0x1800c05e9  mov     edi, r15d
0x1800c05ec  mov     [r13+0], edi
0x1800c05f0  mov     [r12], rbx
0x1800c05f4  lea     rcx, [rbp+arg_0]
0x1800c05f8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c05fd  nop
0x1800c05fe  lea     rcx, [rbp+var_10]
0x1800c0602  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c0607  xor     eax, eax
0x1800c0609  jmp     short loc_1800C0680
0x1800c060b  mov     r15, rbx
0x1800c060e  xor     r14d, r14d
0x1800c0611  jmp     short loc_1800C0622
0x1800c0613  test    rbx, rbx
0x1800c0616  jz      short loc_1800C064E
0x1800c0618  mov     r15, rbx
0x1800c061b  xor     r14d, r14d
0x1800c061e  test    edi, edi
0x1800c0620  jz      short loc_1800C063F
0x1800c0622  mov     rcx, [r15+r14*8]; bstrString
0x1800c0626  test    rcx, rcx
0x1800c0629  jz      short loc_1800C0637
0x1800c062b  call    cs:__imp_SysFreeString
0x1800c0632  nop     dword ptr [rax+rax+00h]
0x1800c0637  inc     r14d
0x1800c063a  cmp     r14d, edi
0x1800c063d  jb      short loc_1800C0622
0x1800c063f  mov     rcx, rbx; pv
0x1800c0642  call    cs:__imp_CoTaskMemFree
0x1800c0649  nop     dword ptr [rax+rax+00h]
0x1800c064e  test    rsi, rsi
0x1800c0651  jz      short loc_1800C0663
0x1800c0653  mov     rcx, rsi; bstrString
0x1800c0656  call    cs:__imp_SysFreeString
0x1800c065d  nop     dword ptr [rax+rax+00h]
0x1800c0662  nop
0x1800c0663  lea     rcx, [rbp+arg_0]
0x1800c0667  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c066c  nop
0x1800c066d  lea     rcx, [rbp+var_10]
0x1800c0671  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c0676  jmp     loc_1800C044F
0x1800c067b  mov     eax, 80070057h
0x1800c0680  mov     rbx, [rsp+30h+arg_8]
0x1800c0685  add     rsp, 30h
0x1800c0689  pop     r15
0x1800c068b  pop     r14
0x1800c068d  pop     r13
0x1800c068f  pop     r12
0x1800c0691  pop     rdi
0x1800c0692  pop     rsi
0x1800c0693  pop     rbp
0x1800c0694  retn
```
