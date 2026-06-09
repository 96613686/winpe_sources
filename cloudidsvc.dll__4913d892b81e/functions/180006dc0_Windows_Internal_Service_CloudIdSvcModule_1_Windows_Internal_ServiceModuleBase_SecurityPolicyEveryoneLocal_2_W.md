# Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(uchar)

- ea: `0x180006dc0`
- end: `0x180006e8b`
- name: `?RunServiceMain@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAAJE@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800085d0`

## callees

- `0x180003e64`
- `0x180004820`
- `0x180006d14`
- `0x180006dc0`
- `0x180007a88`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006e50`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006e50`

## string_xrefs

- `0x180006e63`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(
        __int64 a1,
        char a2)
{
  _QWORD *v3; // rax
  int v4; // eax
  SERVICE_STATUS_HANDLE v5; // rcx
  unsigned int v6; // ebx
  _BYTE v8[8]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v9[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  Windows::Internal::ServiceModuleBase *v11; // [rsp+70h] [rbp+8h] BYREF
  char *v12; // [rsp+78h] [rbp+10h] BYREF

  LOBYTE(v12) = a2;
  *(_DWORD *)(a1 + 24) |= 1u;
  v8[0] = 0;
  v11 = 0;
  v3 = _lambda_fca37cefd63776a0e871ccafc44a49bc_::_lambda_fca37cefd63776a0e871ccafc44a49bc_(
         v9,
         a1,
         (__int64)v8,
         (__int64)&v11,
         (__int64)&v12);
  v4 = _lambda_fca37cefd63776a0e871ccafc44a49bc_::operator()((__int64)v3);
  LODWORD(v12) = v4;
  if ( (v4 & 0x1FFF0000) == 0x70000 )
  {
    *(_DWORD *)(a1 + 28) = (unsigned __int16)v4;
  }
  else
  {
    if ( v4 < 0 )
      *(_DWORD *)(a1 + 28) = 1066;
    *(_DWORD *)(a1 + 32) = v4;
  }
  if ( v11 )
    Windows::Internal::ServiceModuleBase::Uninitialize(v11);
  v5 = *(SERVICE_STATUS_HANDLE *)(a1 + 8);
  *(_DWORD *)(a1 + 20) = 1;
  SetServiceStatus(v5, (LPSERVICE_STATUS)(a1 + 16));
  v6 = (unsigned int)v12;
  if ( (int)v12 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x275,
    (int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)v12);
  return v6;
}

```

## disassembly

```asm
0x180006dc0  mov     r11, rsp
0x180006dc3  mov     [r11+18h], rbx
0x180006dc7  mov     byte ptr [rsp+arg_8], dl
0x180006dcb  push    rdi
0x180006dcc  sub     rsp, 60h
0x180006dd0  or      dword ptr [rcx+18h], 1
0x180006dd4  lea     rax, [r11+10h]
0x180006dd8  mov     rdx, rcx
0x180006ddb  mov     [r11-48h], rax
0x180006ddf  mov     rbx, rcx
0x180006de2  mov     [rsp+68h+var_38], 0
0x180006de7  lea     rcx, [r11-30h]
0x180006deb  mov     qword ptr [r11+8], 0
0x180006df3  lea     r9, [r11+8]
0x180006df7  lea     r8, [r11-38h]
0x180006dfb  call    ??0_lambda_fca37cefd63776a0e871ccafc44a49bc_@@QEAA@PEAV?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@AEAEAEAPEAVServiceModuleBase@23@AEAJ@Z; _lambda_fca37cefd63776a0e871ccafc44a49bc_::_lambda_fca37cefd63776a0e871ccafc44a49bc_(Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *,uchar &,Windows::Internal::ServiceModuleBase * &,long &)
0x180006e00  mov     rcx, rax
0x180006e03  call    ??R_lambda_fca37cefd63776a0e871ccafc44a49bc_@@QEBA@XZ; _lambda_fca37cefd63776a0e871ccafc44a49bc_::operator()(void)
0x180006e08  mov     ecx, eax
0x180006e0a  mov     dword ptr [rsp+68h+arg_8], eax
0x180006e0e  and     ecx, 1FFF0000h
0x180006e14  cmp     ecx, 70000h
0x180006e1a  jnz     short loc_180006E24
0x180006e1c  movzx   eax, ax
0x180006e1f  mov     [rbx+1Ch], eax
0x180006e22  jmp     short loc_180006E32
0x180006e24  test    eax, eax
0x180006e26  jns     short loc_180006E2F
0x180006e28  mov     dword ptr [rbx+1Ch], 42Ah
0x180006e2f  mov     [rbx+20h], eax
0x180006e32  mov     rcx, [rsp+68h+arg_0]; this
0x180006e37  test    rcx, rcx
0x180006e3a  jz      short loc_180006E41
0x180006e3c  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180006e41  mov     rcx, [rbx+8]; hServiceStatus
0x180006e45  lea     rdx, [rbx+10h]; lpServiceStatus
0x180006e49  mov     dword ptr [rbx+14h], 1
0x180006e50  call    cs:__imp_SetServiceStatus
0x180006e56  mov     ebx, dword ptr [rsp+68h+arg_8]
0x180006e5a  test    ebx, ebx
0x180006e5c  jns     short loc_180006E7B
0x180006e5e  mov     rcx, [rsp+68h]; this
0x180006e63  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180006e6a  mov     r9d, ebx; char *
0x180006e6d  mov     edx, 275h; void *
0x180006e72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e77  mov     eax, ebx
0x180006e79  jmp     short loc_180006E7D
0x180006e7b  xor     eax, eax
0x180006e7d  mov     rbx, [rsp+68h+arg_10]
0x180006e85  add     rsp, 60h
0x180006e89  pop     rdi
0x180006e8a  retn
```
