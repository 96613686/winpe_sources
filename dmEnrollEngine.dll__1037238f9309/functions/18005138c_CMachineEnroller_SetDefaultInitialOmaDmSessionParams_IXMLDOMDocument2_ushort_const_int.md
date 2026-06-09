# CMachineEnroller::SetDefaultInitialOmaDmSessionParams(IXMLDOMDocument2 *,ushort const *,int *)

- ea: `0x18005138c`
- end: `0x180051606`
- name: `?SetDefaultInitialOmaDmSessionParams@CMachineEnroller@@CAJPEAUIXMLDOMDocument2@@PEBGPEAH@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f648`

## callees

- `0x1800140d0`
- `0x18004f0ec`
- `0x18005138c`
- `0x180065c78`
- `0x18007b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800513f4`
- `OLEAUT32!__imp_SysAllocString` at `0x180051415`
- `OLEAUT32!__imp_SysAllocString` at `0x180051436`
- `OLEAUT32!__imp_SysAllocString` at `0x1800513f4`
- `OLEAUT32!__imp_SysAllocString` at `0x180051415`
- `OLEAUT32!__imp_SysAllocString` at `0x180051436`
- `OLEAUT32!__imp_SysFreeString` at `0x1800514f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180051505`
- `OLEAUT32!__imp_SysFreeString` at `0x1800514f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180051505`

## string_xrefs

- `0x1800515bd`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Security\MachineEnrollment\OmaDmRetry']/parm[@name='AuxRetryInterval']/@value`
- `0x18005142f`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Security\MachineEnrollment\OmaDmRetry']`
- `0x18005140e`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Software\Microsoft\Enrollment\OmaDmRetry']`
- `0x1800515cc`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Security\MachineEnrollment\OmaDmRetry']/parm[@name='AuxNumRetries']/@value`
- `0x180051566`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Software\Microsoft\Enrollment\OmaDmRetry']/parm[@name='AuxNumRetries']/@value`
- `0x180051557`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Software\Microsoft\Enrollment\OmaDmRetry']/parm[@name='AuxRetryInterval']/@value`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMachineEnroller::SetDefaultInitialOmaDmSessionParams(
        struct IXMLDOMDocument *a1,
        const unsigned __int16 *a2,
        int *a3)
{
  OLECHAR *v6; // r14
  OLECHAR *v7; // rdi
  BSTR v8; // r15
  int ValueFromXmlAndDefaultOnError; // eax
  const unsigned __int16 *v10; // rdx
  BOOL v11; // esi
  __int64 i; // rbx
  unsigned int v13; // ebx
  _QWORD v15[2]; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v16[4]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v17; // [rsp+40h] [rbp-10h]
  int v18; // [rsp+90h] [rbp+40h] BYREF
  __int64 v19; // [rsp+98h] [rbp+48h] BYREF

  v18 = 0;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v19 = 0;
  v15[0] = "CMachineEnroller::SetDefaultInitialOmaDmSessionParams";
  v15[1] = &v18;
  if ( !a3 || !a2 )
  {
    v18 = -2147024809;
    goto LABEL_27;
  }
  v6 = SysAllocString(
         L"wap-provisioningdoc/characteristic[@type='DMClient']/characteristic[@type='Provider']/*/characteristic[@type='Poll']");
  if ( !v6 )
  {
    v18 = -2147024882;
    goto LABEL_27;
  }
  v7 = SysAllocString(
         L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\\Software\\Microsoft\\Enrollment\\OmaDmRetry']");
  if ( v7 )
  {
    v8 = SysAllocString(
           L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\\Security\\MachineEnrollment\\OmaDmRetry']");
    if ( v8 )
    {
      v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int64 *))a1->lpVtbl->selectSingleNode)(
              a1,
              v6,
              &v19);
      if ( v18 )
      {
        v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int64 *))a1->lpVtbl->selectSingleNode)(
                a1,
                v7,
                &v19);
        if ( !v18 )
        {
          if ( v19 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            v19 = 0;
          }
          ValueFromXmlAndDefaultOnError = CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(
                                            a1,
                                            L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='H"
                                             "KLM\\Software\\Microsoft\\Enrollment\\OmaDmRetry']/parm[@name='AuxRetryInterval']/@value",
                                            0xFu,
                                            v16);
          v10 = L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\\Software\\Microsoft\\En"
                 "rollment\\OmaDmRetry']/parm[@name='AuxNumRetries']/@value";
          goto LABEL_12;
        }
        v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, BSTR, __int64 *))a1->lpVtbl->selectSingleNode)(
                a1,
                v8,
                &v19);
        if ( !v18 )
        {
          if ( v19 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            v19 = 0;
          }
          ValueFromXmlAndDefaultOnError = CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(
                                            a1,
                                            L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='H"
                                             "KLM\\Security\\MachineEnrollment\\OmaDmRetry']/parm[@name='AuxRetryInterval']/@value",
                                            0xFu,
                                            v16);
          v10 = L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\\Security\\MachineEnroll"
                 "ment\\OmaDmRetry']/parm[@name='AuxNumRetries']/@value";
          goto LABEL_12;
        }
      }
      else
      {
        *a3 = 1;
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
      }
      ValueFromXmlAndDefaultOnError = CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(
                                        a1,
                                        L"wap-provisioningdoc/characteristic[@type='DMClient']/characteristic[@type='Provi"
                                         "der']/*/characteristic[@type='Poll']/parm[@name='IntervalForFirstSetOfRetries']/@value",
                                        0xFu,
                                        v16);
      v10 = L"wap-provisioningdoc/characteristic[@type='DMClient']/characteristic[@type='Provider']/*/characteristic[@type"
             "='Poll']/parm[@name='NumberOfFirstRetries']/@value";
LABEL_12:
      v11 = ValueFromXmlAndDefaultOnError == 0;
      if ( !CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(a1, v10, 0xAu, &v16[1]) || v11 )
      {
        for ( i = 0; i != 8; ++i )
          SetPollValueToRegistry(a2, (LPCWSTR)(&g_RegistryKeyNames)[i], v16[i]);
      }
      goto LABEL_16;
    }
  }
  v18 = -2147024882;
LABEL_16:
  SysFreeString(v6);
  if ( v7 )
    SysFreeString(v7);
LABEL_27:
  v13 = v18;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v15, (__int64)a2);
  return v13;
}

```

## disassembly

```asm
0x18005138c  mov     [rsp-28h+arg_0], rbx
0x180051391  mov     [rsp-28h+arg_8], rsi
0x180051396  push    rbp
0x180051397  push    rdi
0x180051398  push    r12
0x18005139a  push    r14
0x18005139c  push    r15
0x18005139e  mov     rbp, rsp
0x1800513a1  sub     rsp, 50h
0x1800513a5  mov     rsi, r8
0x1800513a8  mov     r12, rdx
0x1800513ab  mov     rbx, rcx
0x1800513ae  mov     [rbp+arg_10], 0
0x1800513b5  xorps   xmm0, xmm0
0x1800513b8  movups  xmmword ptr [rbp+var_20], xmm0
0x1800513bc  movups  [rbp+var_10], xmm0
0x1800513c0  mov     [rbp+arg_18], 0
0x1800513c8  lea     rax, aCmachineenroll_12; "CMachineEnroller::SetDefaultInitialOmaD"...
0x1800513cf  mov     [rbp+var_30], rax
0x1800513d3  lea     rax, [rbp+arg_10]
0x1800513d7  mov     [rbp+var_28], rax
0x1800513db  test    r8, r8
0x1800513de  jz      loc_1800515D8
0x1800513e4  test    rdx, rdx
0x1800513e7  jz      loc_1800515D8
0x1800513ed  lea     rcx, aWapProvisionin_17; "wap-provisioningdoc/characteristic[@typ"...
0x1800513f4  call    cs:__imp_SysAllocString
0x1800513fa  mov     r14, rax
0x1800513fd  test    rax, rax
0x180051400  jnz     short loc_18005140E
0x180051402  mov     [rbp+arg_10], 8007000Eh
0x180051409  jmp     loc_1800515DF
0x18005140e  lea     rcx, aWapProvisionin_16; "wap-provisioningdoc/characteristic[@typ"...
0x180051415  call    cs:__imp_SysAllocString
0x18005141b  mov     rdi, rax
0x18005141e  test    rax, rax
0x180051421  jnz     short loc_18005142F
0x180051423  mov     [rbp+arg_10], 8007000Eh
0x18005142a  jmp     loc_1800514F0
0x18005142f  lea     rcx, aWapProvisionin_2; "wap-provisioningdoc/characteristic[@typ"...
0x180051436  call    cs:__imp_SysAllocString
0x18005143c  mov     r15, rax
0x18005143f  test    rax, rax
0x180051442  jz      short loc_180051423
0x180051444  mov     rax, [rbx]
0x180051447  lea     r8, [rbp+arg_18]
0x18005144b  mov     rdx, r14
0x18005144e  mov     rcx, rbx
0x180051451  mov     rax, [rax+128h]
0x180051458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005145d  mov     [rbp+arg_10], eax
0x180051460  test    eax, eax
0x180051462  jnz     loc_180051510
0x180051468  mov     dword ptr [rsi], 1
0x18005146e  mov     rcx, [rbp+arg_18]
0x180051472  test    rcx, rcx
0x180051475  jz      short loc_18005148B
0x180051477  mov     rax, [rcx]
0x18005147a  mov     rax, [rax+10h]
0x18005147e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051483  mov     [rbp+arg_18], 0
0x18005148b  lea     r9, [rbp+var_20]; unsigned int *
0x18005148f  mov     r8d, 0Fh; unsigned int
0x180051495  lea     rdx, aWapProvisionin_3; "wap-provisioningdoc/characteristic[@typ"...
0x18005149c  mov     rcx, rbx; struct IXMLDOMDocument *
0x18005149f  call    ?ExtractValueFromXmlAndDefaultOnError@CMachineEnroller@@CAJPEAUIXMLDOMDocument@@PEBGKPEAK@Z; CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(IXMLDOMDocument *,ushort const *,ulong,ulong *)
0x1800514a4  lea     rdx, aWapProvisionin_5; "wap-provisioningdoc/characteristic[@typ"...
0x1800514ab  xor     esi, esi
0x1800514ad  test    eax, eax
0x1800514af  setz    sil
0x1800514b3  lea     r9, [rbp+var_20+4]; unsigned int *
0x1800514b7  mov     r8d, 0Ah; unsigned int
0x1800514bd  mov     rcx, rbx; struct IXMLDOMDocument *
0x1800514c0  call    ?ExtractValueFromXmlAndDefaultOnError@CMachineEnroller@@CAJPEAUIXMLDOMDocument@@PEBGKPEAK@Z; CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(IXMLDOMDocument *,ushort const *,ulong,ulong *)
0x1800514c5  test    eax, eax
0x1800514c7  jz      short loc_1800514CD
0x1800514c9  test    esi, esi
0x1800514cb  jz      short loc_1800514F0
0x1800514cd  xor     ebx, ebx
0x1800514cf  lea     rdx, ?g_RegistryKeyNames@@3PAPEBGA; ushort const * near * g_RegistryKeyNames
0x1800514d6  mov     r8d, [rbp+rbx*4+var_20]; unsigned int
0x1800514db  mov     rdx, [rdx+rbx*8]; lpValueName
0x1800514df  mov     rcx, r12; unsigned __int16 *
0x1800514e2  call    ?SetPollValueToRegistry@@YAJPEBG0K@Z; SetPollValueToRegistry(ushort const *,ushort const *,ulong)
0x1800514e7  inc     rbx
0x1800514ea  cmp     rbx, 8
0x1800514ee  jnz     short loc_1800514CF
0x1800514f0  mov     rcx, r14; bstrString
0x1800514f3  call    cs:__imp_SysFreeString
0x1800514f9  test    rdi, rdi
0x1800514fc  jz      loc_1800515DF
0x180051502  mov     rcx, rdi; bstrString
0x180051505  call    cs:__imp_SysFreeString
0x18005150b  jmp     loc_1800515DF
0x180051510  mov     rax, [rbx]
0x180051513  lea     r8, [rbp+arg_18]
0x180051517  mov     rdx, rdi
0x18005151a  mov     rcx, rbx
0x18005151d  mov     rax, [rax+128h]
0x180051524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051529  mov     [rbp+arg_10], eax
0x18005152c  test    eax, eax
0x18005152e  jnz     short loc_180051572
0x180051530  mov     rcx, [rbp+arg_18]
0x180051534  test    rcx, rcx
0x180051537  jz      short loc_18005154D
0x180051539  mov     rax, [rcx]
0x18005153c  mov     rax, [rax+10h]
0x180051540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051545  mov     [rbp+arg_18], 0
0x18005154d  lea     r9, [rbp+var_20]; unsigned int *
0x180051551  mov     r8d, 0Fh; unsigned int
0x180051557  lea     rdx, aWapProvisionin_0; "wap-provisioningdoc/characteristic[@typ"...
0x18005155e  mov     rcx, rbx; struct IXMLDOMDocument *
0x180051561  call    ?ExtractValueFromXmlAndDefaultOnError@CMachineEnroller@@CAJPEAUIXMLDOMDocument@@PEBGKPEAK@Z; CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(IXMLDOMDocument *,ushort const *,ulong,ulong *)
0x180051566  lea     rdx, aWapProvisionin_1; "wap-provisioningdoc/characteristic[@typ"...
0x18005156d  jmp     loc_1800514AB
0x180051572  mov     rax, [rbx]
0x180051575  lea     r8, [rbp+arg_18]
0x180051579  mov     rdx, r15
0x18005157c  mov     rcx, rbx
0x18005157f  mov     rax, [rax+128h]
0x180051586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005158b  mov     [rbp+arg_10], eax
0x18005158e  test    eax, eax
0x180051590  jnz     loc_18005148B
0x180051596  mov     rcx, [rbp+arg_18]
0x18005159a  test    rcx, rcx
0x18005159d  jz      short loc_1800515B3
0x18005159f  mov     rax, [rcx]
0x1800515a2  mov     rax, [rax+10h]
0x1800515a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515ab  mov     [rbp+arg_18], 0
0x1800515b3  lea     r9, [rbp+var_20]; unsigned int *
0x1800515b7  mov     r8d, 0Fh; unsigned int
0x1800515bd  lea     rdx, aWapProvisionin_7; "wap-provisioningdoc/characteristic[@typ"...
0x1800515c4  mov     rcx, rbx; struct IXMLDOMDocument *
0x1800515c7  call    ?ExtractValueFromXmlAndDefaultOnError@CMachineEnroller@@CAJPEAUIXMLDOMDocument@@PEBGKPEAK@Z; CMachineEnroller::ExtractValueFromXmlAndDefaultOnError(IXMLDOMDocument *,ushort const *,ulong,ulong *)
0x1800515cc  lea     rdx, aWapProvisionin_4; "wap-provisioningdoc/characteristic[@typ"...
0x1800515d3  jmp     loc_1800514AB
0x1800515d8  mov     [rbp+arg_10], 80070057h
0x1800515df  mov     ebx, [rbp+arg_10]
0x1800515e2  lea     rcx, [rbp+var_30]; this
0x1800515e6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800515eb  mov     eax, ebx
0x1800515ed  lea     r11, [rsp+50h+var_s0]
0x1800515f2  mov     rbx, [r11+30h]
0x1800515f6  mov     rsi, [r11+38h]
0x1800515fa  mov     rsp, r11
0x1800515fd  pop     r15
0x1800515ff  pop     r14
0x180051601  pop     r12
0x180051603  pop     rdi
0x180051604  pop     rbp
0x180051605  retn
```
