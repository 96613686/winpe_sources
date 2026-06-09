# DimIsAccessAllowedToService(ulong)

- ea: `0x1800197f0`
- end: `0x18001994a`
- name: `?DimIsAccessAllowedToService@@YAHK@Z`
- size: `346`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180019a24`

## callees

- `0x1800056c4`
- `0x18000def0`
- `0x1800197f0`
- `0x180045d40`
- `0x180045d7c`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800198c4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800198f9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800198c4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800198f9`
- `RPCRT4!RpcRevertToSelf` at `0x18001990e`
- `RPCRT4!RpcRevertToSelf` at `0x18001990e`
- `RPCRT4!RpcImpersonateClient` at `0x180019853`
- `RPCRT4!RpcImpersonateClient` at `0x180019853`

## string_xrefs

- `0x18001986c`: `DimIsAccessAllowedToService: Failed to impersonate the client. Error=%d `

## pseudocode

```c
__int64 __fastcall DimIsAccessAllowedToService(char a1)
{
  int v2; // edi
  unsigned int v3; // eax
  WINBOOL IsMember; // [rsp+20h] [rbp-E0h] BYREF
  GUID ActivityId; // [rsp+28h] [rbp-D8h] BYREF
  int v7; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[2044]; // [rsp+44h] [rbp-BCh] BYREF

  IsMember = 0;
  v7 = 0;
  ActivityId = 0;
  memset_0(v8, 0, sizeof(v8));
  v2 = SetRasServerActivityId(&ActivityId);
  v3 = RpcImpersonateClient(0);
  if ( !v3 )
  {
    if ( (a1 & 2) != 0 )
    {
      CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFBLL, Sid, &IsMember);
      if ( IsMember )
      {
LABEL_11:
        RpcRevertToSelf();
        goto LABEL_12;
      }
      IsMember = 0;
    }
    if ( (a1 & 4) != 0 )
    {
      CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFBLL, qword_180071160, &IsMember);
      if ( !IsMember )
        IsMember = 0;
    }
    goto LABEL_11;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString(&v7, L"DimIsAccessAllowedToService: Failed to impersonate the client. Error=%d ", v3);
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v7);
  }
LABEL_12:
  if ( v2 )
    ReSetActivityId(&ActivityId);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800197f0  mov     [rsp-8+arg_0], rbx
0x1800197f5  mov     [rsp-8+arg_8], rdi
0x1800197fa  push    rbp
0x1800197fb  lea     rbp, [rsp-750h]
0x180019803  sub     rsp, 850h
0x18001980a  mov     rax, cs:__security_cookie
0x180019811  xor     rax, rsp
0x180019814  mov     [rbp+750h+var_10], rax
0x18001981b  mov     ebx, ecx
0x18001981d  mov     [rsp+850h+IsMember], 0
0x180019825  xorps   xmm0, xmm0
0x180019828  lea     rcx, [rsp+850h+var_80C]; void *
0x18001982d  xor     eax, eax
0x18001982f  xor     edx, edx; Val
0x180019831  mov     r8d, 7FCh; Size
0x180019837  mov     [rsp+850h+var_810], eax
0x18001983b  movups  xmmword ptr [rsp+850h+ActivityId.Data1], xmm0
0x180019840  call    memset_0
0x180019845  lea     rcx, [rsp+850h+ActivityId]; ActivityId
0x18001984a  call    SetRasServerActivityId
0x18001984f  xor     ecx, ecx; BindingHandle
0x180019851  mov     edi, eax
0x180019853  call    cs:__imp_RpcImpersonateClient
0x180019859  test    eax, eax
0x18001985b  jz      short loc_1800198AC
0x18001985d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180019864  jz      loc_180019914
0x18001986a  xor     ecx, ecx
0x18001986c  lea     rdx, aDimisaccessall; "DimIsAccessAllowedToService: Failed to "...
0x180019873  mov     word ptr [rsp+850h+var_810], cx
0x180019878  mov     r8d, eax
0x18001987b  lea     rcx, [rsp+850h+var_810]
0x180019880  call    FormatRRASErrorString
0x180019885  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18001988c  jz      loc_180019914
0x180019892  lea     r8, [rsp+850h+var_810]
0x180019897  lea     rdx, RasDimTraceError
0x18001989e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800198a5  call    McTemplateU0z_EventWriteTransfer
0x1800198aa  jmp     short loc_180019914
0x1800198ac  test    bl, 2
0x1800198af  jz      short loc_1800198D9
0x1800198b1  mov     rdx, cs:Sid; SidToCheck
0x1800198b8  lea     r8, [rsp+850h+IsMember]; IsMember
0x1800198bd  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x1800198c4  call    cs:__imp_CheckTokenMembership
0x1800198ca  cmp     [rsp+850h+IsMember], 0
0x1800198cf  jnz     short loc_18001990E
0x1800198d1  xor     eax, eax
0x1800198d3  mov     [rsp+850h+IsMember], eax
0x1800198d7  jmp     short loc_1800198DD
0x1800198d9  mov     eax, [rsp+850h+IsMember]
0x1800198dd  test    eax, eax
0x1800198df  jnz     short loc_18001990E
0x1800198e1  test    bl, 4
0x1800198e4  jz      short loc_18001990E
0x1800198e6  mov     rdx, cs:qword_180071160; SidToCheck
0x1800198ed  lea     r8, [rsp+850h+IsMember]; IsMember
0x1800198f2  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x1800198f9  call    cs:__imp_CheckTokenMembership
0x1800198ff  cmp     [rsp+850h+IsMember], 0
0x180019904  jnz     short loc_18001990E
0x180019906  mov     [rsp+850h+IsMember], 0
0x18001990e  call    cs:__imp_RpcRevertToSelf
0x180019914  test    edi, edi
0x180019916  jz      short loc_180019922
0x180019918  lea     rcx, [rsp+850h+ActivityId]; ActivityId
0x18001991d  call    ReSetActivityId
0x180019922  mov     eax, [rsp+850h+IsMember]
0x180019926  mov     rcx, [rbp+750h+var_10]
0x18001992d  xor     rcx, rsp; StackCookie
0x180019930  call    __security_check_cookie
0x180019935  lea     r11, [rsp+850h+var_s0]
0x18001993d  mov     rbx, [r11+10h]
0x180019941  mov     rdi, [r11+18h]
0x180019945  mov     rsp, r11
0x180019948  pop     rbp
0x180019949  retn
```
