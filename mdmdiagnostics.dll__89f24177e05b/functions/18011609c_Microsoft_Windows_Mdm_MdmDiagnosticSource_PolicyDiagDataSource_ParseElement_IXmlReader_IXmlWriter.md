# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::ParseElement(IXmlReader *,IXmlWriter *)

- ea: `0x18011609c`
- end: `0x180116277`
- name: `?ParseElement@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this, struct IXmlReader *, struct IXmlWriter *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801165cc`

## callees

- `0x1800ece5c`
- `0x1800f8708`
- `0x1801158ec`
- `0x18011609c`
- `0x180191010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180116105`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180116180`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801161a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801161c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801161eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011620d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011622f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180116251`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180116105`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180116180`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801161a1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801161c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801161eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011620d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011622f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180116251`

## string_xrefs

- `0x1801160e3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x180116179`: `RegKeyPathRedirect`
- `0x180116206`: `GroupPolicyPath`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::ParseElement(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *this,
        struct IXmlReader *a2,
        struct IXmlWriter *a3)
{
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v6; // edi
  __int64 v7; // rdx
  int appended; // eax
  __int64 v10; // rcx
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  v13 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))lpVtbl->GetLocalName)(a2, &v13, 0);
  if ( v6 < 0 )
  {
    v7 = 128;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\policydiagdata.cpp",
      (const char *)(unsigned int)v6,
      v11);
    return (unsigned int)v6;
  }
  if ( !(unsigned int)_o__wcsicmp(L"CurrentPolicies", v13) && !*((_DWORD *)this + 524) )
  {
    appended = Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::AppendRedirectedOrGroupPolicyInformation(
                 this,
                 a3);
    *((_DWORD *)this + 524) = 1;
    if ( appended < 0 && (byte_1802668C1 & 0x40) != 0 )
      McTemplateU0d_EventWriteTransfer(
        v10,
        EnterpriseDiagnosticsMdmDiagnosticsAppendingRedirectedRegKeyOrGroupPolicyFailure,
        (unsigned int)appended);
  }
  v6 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))a3->lpVtbl->WriteStartElement)(
         a3,
         0,
         v13,
         0);
  if ( v6 < 0 )
  {
    v7 = 142;
    goto LABEL_3;
  }
  if ( (unsigned int)_o__wcsicmp(v13, L"RegKeyPathRedirect") )
  {
    if ( (unsigned int)_o__wcsicmp(v13, L"RegValueNameRedirect") )
    {
      if ( (unsigned int)_o__wcsicmp(v13, L"PolicyName") )
      {
        if ( (unsigned int)_o__wcsicmp(v13, L"PolicyAreaName") )
        {
          if ( (unsigned int)_o__wcsicmp(v13, L"GroupPolicyPath") )
          {
            if ( (unsigned int)_o__wcsicmp(v13, L"GroupPolicyName") )
            {
              if ( !(unsigned int)_o__wcsicmp(v13, L"PerUser") )
                *((_DWORD *)this + 528) = 6;
            }
            else
            {
              *((_DWORD *)this + 528) = 5;
            }
          }
          else
          {
            *((_DWORD *)this + 528) = 4;
          }
        }
        else
        {
          *((_DWORD *)this + 528) = 2;
        }
      }
      else
      {
        *((_DWORD *)this + 528) = 3;
      }
    }
    else
    {
      *((_DWORD *)this + 528) = 1;
    }
  }
  else
  {
    *((_DWORD *)this + 528) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18011609c  mov     r11, rsp
0x18011609f  mov     [r11+8], rbx
0x1801160a3  mov     [r11+18h], rsi
0x1801160a7  push    rdi
0x1801160a8  sub     rsp, 30h
0x1801160ac  mov     rax, [rdx]
0x1801160af  mov     r9, rdx
0x1801160b2  mov     rsi, r8
0x1801160b5  mov     qword ptr [r11+10h], 0
0x1801160bd  mov     rbx, rcx
0x1801160c0  lea     rdx, [r11+10h]
0x1801160c4  xor     r8d, r8d
0x1801160c7  mov     rcx, r9
0x1801160ca  mov     rax, [rax+70h]
0x1801160ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801160d3  mov     edi, eax
0x1801160d5  test    eax, eax
0x1801160d7  jns     short loc_1801160F9
0x1801160d9  mov     edx, 80h; void *
0x1801160de  mov     rcx, [rsp+38h]; this
0x1801160e3  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801160ea  mov     r9d, edi; char *
0x1801160ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801160f2  mov     eax, edi
0x1801160f4  jmp     loc_180116267
0x1801160f9  mov     rdx, [rsp+38h+arg_8]
0x1801160fe  lea     rcx, aCurrentpolicie; "CurrentPolicies"
0x180116105  call    cs:__imp__o__wcsicmp
0x18011610b  test    eax, eax
0x18011610d  jnz     short loc_180116148
0x18011610f  cmp     [rbx+830h], eax
0x180116115  jnz     short loc_180116148
0x180116117  mov     rdx, rsi; struct IXmlWriter *
0x18011611a  mov     rcx, rbx; this
0x18011611d  call    ?AppendRedirectedOrGroupPolicyInformation@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlWriter@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::AppendRedirectedOrGroupPolicyInformation(IXmlWriter *)
0x180116122  mov     dword ptr [rbx+830h], 1
0x18011612c  test    eax, eax
0x18011612e  jns     short loc_180116148
0x180116130  test    cs:byte_1802668C1, 40h
0x180116137  jz      short loc_180116148
0x180116139  mov     r8d, eax
0x18011613c  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsAppendingRedirectedRegKeyOrGroupPolicyFailure
0x180116143  call    McTemplateU0d_EventWriteTransfer
0x180116148  mov     rax, [rsi]
0x18011614b  xor     r9d, r9d
0x18011614e  mov     r8, [rsp+38h+arg_8]
0x180116153  xor     edx, edx
0x180116155  mov     rcx, rsi
0x180116158  mov     rax, [rax+0D8h]
0x18011615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116164  mov     edi, eax
0x180116166  test    eax, eax
0x180116168  jns     short loc_180116174
0x18011616a  mov     edx, 8Eh
0x18011616f  jmp     loc_1801160DE
0x180116174  mov     rcx, [rsp+38h+arg_8]
0x180116179  lea     rdx, aRegkeypathredi; "RegKeyPathRedirect"
0x180116180  call    cs:__imp__o__wcsicmp
0x180116186  test    eax, eax
0x180116188  jnz     short loc_180116195
0x18011618a  mov     [rbx+840h], eax
0x180116190  jmp     loc_180116265
0x180116195  mov     rcx, [rsp+38h+arg_8]
0x18011619a  lea     rdx, aRegvaluenamere; "RegValueNameRedirect"
0x1801161a1  call    cs:__imp__o__wcsicmp
0x1801161a7  test    eax, eax
0x1801161a9  jnz     short loc_1801161BA
0x1801161ab  mov     dword ptr [rbx+840h], 1
0x1801161b5  jmp     loc_180116265
0x1801161ba  mov     rcx, [rsp+38h+arg_8]
0x1801161bf  lea     rdx, aPolicyname; "PolicyName"
0x1801161c6  call    cs:__imp__o__wcsicmp
0x1801161cc  test    eax, eax
0x1801161ce  jnz     short loc_1801161DF
0x1801161d0  mov     dword ptr [rbx+840h], 3
0x1801161da  jmp     loc_180116265
0x1801161df  mov     rcx, [rsp+38h+arg_8]
0x1801161e4  lea     rdx, aPolicyareaname; "PolicyAreaName"
0x1801161eb  call    cs:__imp__o__wcsicmp
0x1801161f1  test    eax, eax
0x1801161f3  jnz     short loc_180116201
0x1801161f5  mov     dword ptr [rbx+840h], 2
0x1801161ff  jmp     short loc_180116265
0x180116201  mov     rcx, [rsp+38h+arg_8]
0x180116206  lea     rdx, aGrouppolicypat_0; "GroupPolicyPath"
0x18011620d  call    cs:__imp__o__wcsicmp
0x180116213  test    eax, eax
0x180116215  jnz     short loc_180116223
0x180116217  mov     dword ptr [rbx+840h], 4
0x180116221  jmp     short loc_180116265
0x180116223  mov     rcx, [rsp+38h+arg_8]
0x180116228  lea     rdx, aGrouppolicynam_0; "GroupPolicyName"
0x18011622f  call    cs:__imp__o__wcsicmp
0x180116235  test    eax, eax
0x180116237  jnz     short loc_180116245
0x180116239  mov     dword ptr [rbx+840h], 5
0x180116243  jmp     short loc_180116265
0x180116245  mov     rcx, [rsp+38h+arg_8]
0x18011624a  lea     rdx, aPeruser; "PerUser"
0x180116251  call    cs:__imp__o__wcsicmp
0x180116257  test    eax, eax
0x180116259  jnz     short loc_180116265
0x18011625b  mov     dword ptr [rbx+840h], 6
0x180116265  xor     eax, eax
0x180116267  mov     rbx, [rsp+38h+arg_0]
0x18011626c  mov     rsi, [rsp+38h+arg_10]
0x180116271  add     rsp, 30h
0x180116275  pop     rdi
0x180116276  retn
```
