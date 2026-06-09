# Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker::SetSessionVariable(ushort *,tagVARIANT &)

- ea: `0x14004c7e0`
- end: `0x14004c8d2`
- name: `?SetSessionVariable@ConfigManagerInvoker@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAGAEAUtagVARIANT@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker *__hidden this, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000e610`
- `0x140013404`
- `0x14004c7e0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004c856`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14004c856`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker::SetSessionVariable(
        Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  LPVOID *ppv; // rdi
  HRESULT Instance; // eax
  unsigned int v8; // ebx
  LPVOID v9; // rcx
  __int128 v11; // [rsp+30h] [rbp-50h] BYREF
  IRecordInfo *pRecInfo; // [rsp+40h] [rbp-40h]
  _QWORD v13[3]; // [rsp+50h] [rbp-30h] BYREF
  int v14; // [rsp+68h] [rbp-18h]
  HRESULT *v15; // [rsp+70h] [rbp-10h]
  HRESULT v16; // [rsp+A0h] [rbp+20h] BYREF

  v16 = 0;
  v13[0] = 0;
  v13[1] = "SetSessionVariable";
  v13[2] = COmaDmLogger::GetLogger();
  v14 = 2;
  v15 = &v16;
  ppv = (LPVOID *)((char *)this + 8);
  if ( !*ppv )
  {
    Instance = CoCreateInstance(
                 &GUID_66d0db14_5638_475f_a386_629522d8c461,
                 0,
                 1u,
                 &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
                 ppv);
    v8 = Instance;
    v16 = Instance;
    if ( Instance < 0 )
    {
      LODWORD(v13[0]) = 9010;
LABEL_6:
      HIDWORD(v13[0]) = Instance;
      goto LABEL_7;
    }
  }
  v9 = *ppv;
  v11 = *(_OWORD *)&a3->vt;
  pRecInfo = a3->pRecInfo;
  Instance = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int128 *))(*(_QWORD *)v9 + 104LL))(v9, a2, &v11);
  v8 = Instance;
  v16 = Instance;
  if ( Instance < 0 )
  {
    LODWORD(v13[0]) = 9015;
    goto LABEL_6;
  }
LABEL_7:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v13);
  return v8;
}

```

## disassembly

```asm
0x14004c7e0  mov     [rsp-18h+arg_8], rbx
0x14004c7e5  mov     [rsp-18h+arg_10], rsi
0x14004c7ea  push    rbp
0x14004c7eb  push    rdi
0x14004c7ec  push    r14
0x14004c7ee  mov     rbp, rsp
0x14004c7f1  sub     rsp, 80h
0x14004c7f8  mov     rsi, r8
0x14004c7fb  mov     r14, rdx
0x14004c7fe  mov     rdi, rcx
0x14004c801  mov     [rbp+arg_0], 0
0x14004c808  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004c80d  mov     [rbp+var_30], 0
0x14004c815  lea     rcx, aSetsessionvari; "SetSessionVariable"
0x14004c81c  mov     [rbp+var_28], rcx
0x14004c820  mov     [rbp+var_20], rax
0x14004c824  mov     [rbp+var_18], 2
0x14004c82b  lea     rax, [rbp+arg_0]
0x14004c82f  mov     [rbp+var_10], rax
0x14004c833  add     rdi, 8
0x14004c837  cmp     qword ptr [rdi], 0
0x14004c83b  jnz     short loc_14004C874
0x14004c83d  mov     [rsp+80h+ppv], rdi; ppv
0x14004c842  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x14004c849  xor     edx, edx; pUnkOuter
0x14004c84b  lea     r8d, [rdx+1]; dwClsContext
0x14004c84f  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x14004c856  call    cs:__imp_CoCreateInstance
0x14004c85d  nop     dword ptr [rax+rax+00h]
0x14004c862  mov     ebx, eax
0x14004c864  mov     [rbp+arg_0], eax
0x14004c867  test    eax, eax
0x14004c869  jns     short loc_14004C874
0x14004c86b  mov     dword ptr [rbp+var_30], 2332h
0x14004c872  jmp     short loc_14004C8AB
0x14004c874  mov     rcx, [rdi]
0x14004c877  movups  xmm0, xmmword ptr [rsi]
0x14004c87a  movaps  [rbp+var_50], xmm0
0x14004c87e  movsd   xmm1, qword ptr [rsi+10h]
0x14004c883  movsd   [rbp+var_40], xmm1
0x14004c888  mov     rax, [rcx]
0x14004c88b  lea     r8, [rbp+var_50]
0x14004c88f  mov     rdx, r14
0x14004c892  mov     rax, [rax+68h]
0x14004c896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c89b  mov     ebx, eax
0x14004c89d  mov     [rbp+arg_0], eax
0x14004c8a0  test    eax, eax
0x14004c8a2  jns     short loc_14004C8AE
0x14004c8a4  mov     dword ptr [rbp+var_30], 2337h
0x14004c8ab  mov     dword ptr [rbp+var_30+4], eax
0x14004c8ae  lea     rcx, [rbp+var_30]; this
0x14004c8b2  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004c8b7  mov     eax, ebx
0x14004c8b9  lea     r11, [rsp+80h+var_s0]
0x14004c8c1  mov     rbx, [r11+28h]
0x14004c8c5  mov     rsi, [r11+30h]
0x14004c8c9  mov     rsp, r11
0x14004c8cc  pop     r14
0x14004c8ce  pop     rdi
0x14004c8cf  pop     rbp
0x14004c8d0  retn
```
