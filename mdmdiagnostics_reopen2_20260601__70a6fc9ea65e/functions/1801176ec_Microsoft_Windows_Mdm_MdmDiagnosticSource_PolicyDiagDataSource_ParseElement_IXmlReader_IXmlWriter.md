# Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::ParseElement(IXmlReader *,IXmlWriter *)

- ea: `0x1801176ec`
- end: `0x1801178f8`
- name: `?ParseElement@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlReader@@PEAUIXmlWriter@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource *__hidden this, struct IXmlReader *, struct IXmlWriter *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180117c54`

## callees

- `0x1800ed46c`
- `0x1800f96c0`
- `0x180116f0c`
- `0x1801176ec`
- `0x180193010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117755`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801177d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801177fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117828`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117853`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011787b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801178a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801178cb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117755`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801177d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801177fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117828`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180117853`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011787b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801178a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801178cb`

## string_xrefs

- `0x180117733`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\policydiagdata.cpp`
- `0x1801177cf`: `RegKeyPathRedirect`
- `0x180117874`: `GroupPolicyPath`

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
    if ( appended < 0 && (byte_180268981 & 0x40) != 0 )
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
0x1801176ec  mov     r11, rsp
0x1801176ef  mov     [r11+8], rbx
0x1801176f3  mov     [r11+18h], rsi
0x1801176f7  push    rdi
0x1801176f8  sub     rsp, 30h
0x1801176fc  mov     rax, [rdx]
0x1801176ff  mov     r9, rdx
0x180117702  mov     rsi, r8
0x180117705  mov     qword ptr [r11+10h], 0
0x18011770d  mov     rbx, rcx
0x180117710  lea     rdx, [r11+10h]
0x180117714  xor     r8d, r8d
0x180117717  mov     rcx, r9
0x18011771a  mov     rax, [rax+70h]
0x18011771e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117723  mov     edi, eax
0x180117725  test    eax, eax
0x180117727  jns     short loc_180117749
0x180117729  mov     edx, 80h; void *
0x18011772e  mov     rcx, [rsp+38h]; this
0x180117733  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011773a  mov     r9d, edi; char *
0x18011773d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117742  mov     eax, edi
0x180117744  jmp     loc_1801178E7
0x180117749  mov     rdx, [rsp+38h+arg_8]
0x18011774e  lea     rcx, aCurrentpolicie; "CurrentPolicies"
0x180117755  call    cs:__imp__o__wcsicmp
0x18011775c  nop     dword ptr [rax+rax+00h]
0x180117761  test    eax, eax
0x180117763  jnz     short loc_18011779E
0x180117765  cmp     [rbx+830h], eax
0x18011776b  jnz     short loc_18011779E
0x18011776d  mov     rdx, rsi; struct IXmlWriter *
0x180117770  mov     rcx, rbx; this
0x180117773  call    ?AppendRedirectedOrGroupPolicyInformation@PolicyDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAUIXmlWriter@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::PolicyDiagDataSource::AppendRedirectedOrGroupPolicyInformation(IXmlWriter *)
0x180117778  mov     dword ptr [rbx+830h], 1
0x180117782  test    eax, eax
0x180117784  jns     short loc_18011779E
0x180117786  test    cs:byte_180268981, 40h
0x18011778d  jz      short loc_18011779E
0x18011778f  mov     r8d, eax
0x180117792  lea     rdx, EnterpriseDiagnosticsMdmDiagnosticsAppendingRedirectedRegKeyOrGroupPolicyFailure
0x180117799  call    McTemplateU0d_EventWriteTransfer
0x18011779e  mov     rax, [rsi]
0x1801177a1  xor     r9d, r9d
0x1801177a4  mov     r8, [rsp+38h+arg_8]
0x1801177a9  xor     edx, edx
0x1801177ab  mov     rcx, rsi
0x1801177ae  mov     rax, [rax+0D8h]
0x1801177b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801177ba  mov     edi, eax
0x1801177bc  test    eax, eax
0x1801177be  jns     short loc_1801177CA
0x1801177c0  mov     edx, 8Eh
0x1801177c5  jmp     loc_18011772E
0x1801177ca  mov     rcx, [rsp+38h+arg_8]
0x1801177cf  lea     rdx, aRegkeypathredi; "RegKeyPathRedirect"
0x1801177d6  call    cs:__imp__o__wcsicmp
0x1801177dd  nop     dword ptr [rax+rax+00h]
0x1801177e2  test    eax, eax
0x1801177e4  jnz     short loc_1801177F1
0x1801177e6  mov     [rbx+840h], eax
0x1801177ec  jmp     loc_1801178E5
0x1801177f1  mov     rcx, [rsp+38h+arg_8]
0x1801177f6  lea     rdx, aRegvaluenamere; "RegValueNameRedirect"
0x1801177fd  call    cs:__imp__o__wcsicmp
0x180117804  nop     dword ptr [rax+rax+00h]
0x180117809  test    eax, eax
0x18011780b  jnz     short loc_18011781C
0x18011780d  mov     dword ptr [rbx+840h], 1
0x180117817  jmp     loc_1801178E5
0x18011781c  mov     rcx, [rsp+38h+arg_8]
0x180117821  lea     rdx, aPolicyname; "PolicyName"
0x180117828  call    cs:__imp__o__wcsicmp
0x18011782f  nop     dword ptr [rax+rax+00h]
0x180117834  test    eax, eax
0x180117836  jnz     short loc_180117847
0x180117838  mov     dword ptr [rbx+840h], 3
0x180117842  jmp     loc_1801178E5
0x180117847  mov     rcx, [rsp+38h+arg_8]
0x18011784c  lea     rdx, aPolicyareaname; "PolicyAreaName"
0x180117853  call    cs:__imp__o__wcsicmp
0x18011785a  nop     dword ptr [rax+rax+00h]
0x18011785f  test    eax, eax
0x180117861  jnz     short loc_18011786F
0x180117863  mov     dword ptr [rbx+840h], 2
0x18011786d  jmp     short loc_1801178E5
0x18011786f  mov     rcx, [rsp+38h+arg_8]
0x180117874  lea     rdx, aGrouppolicypat_0; "GroupPolicyPath"
0x18011787b  call    cs:__imp__o__wcsicmp
0x180117882  nop     dword ptr [rax+rax+00h]
0x180117887  test    eax, eax
0x180117889  jnz     short loc_180117897
0x18011788b  mov     dword ptr [rbx+840h], 4
0x180117895  jmp     short loc_1801178E5
0x180117897  mov     rcx, [rsp+38h+arg_8]
0x18011789c  lea     rdx, aGrouppolicynam_0; "GroupPolicyName"
0x1801178a3  call    cs:__imp__o__wcsicmp
0x1801178aa  nop     dword ptr [rax+rax+00h]
0x1801178af  test    eax, eax
0x1801178b1  jnz     short loc_1801178BF
0x1801178b3  mov     dword ptr [rbx+840h], 5
0x1801178bd  jmp     short loc_1801178E5
0x1801178bf  mov     rcx, [rsp+38h+arg_8]
0x1801178c4  lea     rdx, aPeruser; "PerUser"
0x1801178cb  call    cs:__imp__o__wcsicmp
0x1801178d2  nop     dword ptr [rax+rax+00h]
0x1801178d7  test    eax, eax
0x1801178d9  jnz     short loc_1801178E5
0x1801178db  mov     dword ptr [rbx+840h], 6
0x1801178e5  xor     eax, eax
0x1801178e7  mov     rbx, [rsp+38h+arg_0]
0x1801178ec  mov     rsi, [rsp+38h+arg_10]
0x1801178f1  add     rsp, 30h
0x1801178f5  pop     rdi
0x1801178f6  retn
```
