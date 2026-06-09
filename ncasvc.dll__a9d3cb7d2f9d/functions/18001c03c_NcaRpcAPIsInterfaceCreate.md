# NcaRpcAPIsInterfaceCreate

- ea: `0x18001c03c`
- end: `0x18001c3f3`
- name: `NcaRpcAPIsInterfaceCreate`
- size: `951`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b060`

## callees

- `0x180004f34`
- `0x180019ad0`
- `0x180019c70`
- `0x18001abd4`
- `0x18001bc74`
- `0x18001c03c`
- `0x18001c3fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c0dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001c0dd`
- `RPCRT4!RpcServerInqBindings` at `0x18001c335`
- `RPCRT4!RpcServerInqBindings` at `0x18001c335`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18001c2da`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18001c2da`
- `RPCRT4!RpcEpRegisterW` at `0x18001c38b`
- `RPCRT4!RpcEpRegisterW` at `0x18001c38b`
- `RPCRT4!RpcServerUseProtseqW` at `0x18001c232`
- `RPCRT4!RpcServerUseProtseqW` at `0x18001c232`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsInterfaceCreate(
        LPCWSTR StringSecurityDescriptor,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  signed int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rbp
  unsigned __int64 v16; // r14
  __int64 v17; // rsi
  RPC_STATUS v18; // eax
  RPC_STATUS v19; // eax
  RPC_STATUS v20; // eax
  RPC_STATUS v21; // eax

  a5 = 0;
  *(_OWORD *)&gNcaRpcAPIs = 0;
  qword_1800295D0 = 0;
  gNcaRpcAPIs = qword_18001F9A0;
  xmmword_1800295B0 = 0;
  *(_OWORD *)&xmmword_1800295C0 = 0;
  v9 = NcaRpcAPIsRegisterAuthInfo();
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_58;
    v11 = 12;
    goto LABEL_21;
  }
  if ( StringSecurityDescriptor
    && !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &gNcaRpcAPIs + 1, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 13;
LABEL_12:
      WPP_SF_d(v13[2], v14, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, (unsigned int)v9);
    }
    goto LABEL_57;
  }
  LODWORD(xmmword_1800295B0) = a2;
  v9 = NcaSizeTMultiply(a3, 8, &a5);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_58;
    v11 = 14;
    goto LABEL_21;
  }
  xmmword_1800295C0 = (LPVOID)NcaAlloc(a5);
  if ( !xmmword_1800295C0 )
  {
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_58;
    v11 = 15;
LABEL_21:
    WPP_SF_d(v10[2], v11, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, (unsigned int)v9);
LABEL_58:
    NcaRpcAPIsInterfaceDestroy();
    return (unsigned int)v9;
  }
  v15 = 0;
  v16 = 8 * a3;
  while ( 1 )
  {
    v17 = 8 * v15;
    if ( 8 * v15 >= v16 )
      break;
    v9 = NcaStringCopy(*(void **)(v17 + a4));
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 16;
        goto LABEL_21;
      }
      goto LABEL_58;
    }
    *((_QWORD *)&xmmword_1800295B0 + 1) = ++v15;
    v18 = RpcServerUseProtseqW(*(RPC_WSTR *)((char *)xmmword_1800295C0 + v17), 0xAu, 0);
    if ( v18 )
    {
      if ( v18 > 0 )
        v9 = (unsigned __int16)v18 | 0x80070000;
      else
        v9 = v18;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 17;
        goto LABEL_12;
      }
      goto LABEL_57;
    }
  }
  v19 = RpcServerRegisterIfEx(qword_18001F9A0, 0, 0, a2 != 0 ? 9 : 41, 0x4D2u, NcaRpcAPIsSecurityCallback);
  if ( v19 )
  {
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    else
      v9 = v19;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 18;
      goto LABEL_12;
    }
  }
  else
  {
    HIDWORD(qword_1800295D0) = 1;
    v20 = RpcServerInqBindings((RPC_BINDING_VECTOR **)&xmmword_1800295C0 + 1);
    if ( v20 )
    {
      if ( v20 > 0 )
        v9 = (unsigned __int16)v20 | 0x80070000;
      else
        v9 = v20;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 19;
        goto LABEL_12;
      }
    }
    else
    {
      v21 = RpcEpRegisterW(qword_18001F9A0, (RPC_BINDING_VECTOR *)*(&xmmword_1800295C0 + 1), 0, (RPC_WSTR)L"Nca APIs");
      if ( v21 )
      {
        if ( v21 > 0 )
          v9 = (unsigned __int16)v21 | 0x80070000;
        else
          v9 = v21;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 20;
          goto LABEL_12;
        }
      }
      else
      {
        LODWORD(qword_1800295D0) = 1;
      }
    }
  }
LABEL_57:
  if ( v9 < 0 )
    goto LABEL_58;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001c03c  mov     rax, rsp
0x18001c03f  push    rbx
0x18001c040  push    rbp
0x18001c041  push    rsi
0x18001c042  push    r12
0x18001c044  push    r13
0x18001c046  push    r14
0x18001c048  push    r15
0x18001c04a  sub     rsp, 30h
0x18001c04e  xorps   xmm0, xmm0
0x18001c051  mov     qword ptr [rax+28h], 0
0x18001c059  xor     eax, eax
0x18001c05b  lea     r13, qword_18001F9A0
0x18001c062  movups  cs:?gNcaRpcAPIs@@3UNCA_RPC_APIS_COMPONENT_@@A, xmm0; NCA_RPC_APIS_COMPONENT_ gNcaRpcAPIs
0x18001c069  mov     cs:qword_1800295D0, rax
0x18001c070  mov     r12, r9
0x18001c073  mov     qword ptr cs:?gNcaRpcAPIs@@3UNCA_RPC_APIS_COMPONENT_@@A, r13; NCA_RPC_APIS_COMPONENT_ gNcaRpcAPIs
0x18001c07a  mov     r14, r8
0x18001c07d  mov     r15d, edx
0x18001c080  mov     rsi, rcx
0x18001c083  movups  cs:xmmword_1800295B0, xmm0
0x18001c08a  movups  cs:xmmword_1800295C0, xmm0
0x18001c091  call    ?NcaRpcAPIsRegisterAuthInfo@@YAJXZ; NcaRpcAPIsRegisterAuthInfo(void)
0x18001c096  mov     ebx, eax
0x18001c098  test    eax, eax
0x18001c09a  jns     short loc_18001C0C7
0x18001c09c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0a3  lea     rax, WPP_GLOBAL_Control
0x18001c0aa  cmp     rcx, rax
0x18001c0ad  jz      loc_18001C3DB
0x18001c0b3  test    byte ptr [rcx+1Ch], 1
0x18001c0b7  jz      loc_18001C3DB
0x18001c0bd  mov     edx, 0Ch
0x18001c0c2  jmp     loc_18001C1D4
0x18001c0c7  test    rsi, rsi
0x18001c0ca  jz      short loc_18001C146
0x18001c0cc  xor     r9d, r9d; SecurityDescriptorSize
0x18001c0cf  lea     r8, ?gNcaRpcAPIs@@3UNCA_RPC_APIS_COMPONENT_@@A+8; SecurityDescriptor
0x18001c0d6  mov     rcx, rsi; StringSecurityDescriptor
0x18001c0d9  lea     edx, [r9+1]; StringSDRevision
0x18001c0dd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001c0e4  nop     dword ptr [rax+rax+00h]
0x18001c0e9  test    eax, eax
0x18001c0eb  jnz     short loc_18001C146
0x18001c0ed  call    cs:__imp_GetLastError
0x18001c0f4  nop     dword ptr [rax+rax+00h]
0x18001c0f9  mov     ebx, eax
0x18001c0fb  test    eax, eax
0x18001c0fd  jle     short loc_18001C108
0x18001c0ff  movzx   ebx, ax
0x18001c102  or      ebx, 80070000h
0x18001c108  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c10f  lea     rax, WPP_GLOBAL_Control
0x18001c116  cmp     rcx, rax
0x18001c119  jz      loc_18001C3D7
0x18001c11f  test    byte ptr [rcx+1Ch], 1
0x18001c123  jz      loc_18001C3D7
0x18001c129  mov     edx, 0Dh
0x18001c12e  mov     rcx, [rcx+10h]
0x18001c132  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c139  mov     r9d, ebx
0x18001c13c  call    WPP_SF_d
0x18001c141  jmp     loc_18001C3D7
0x18001c146  lea     r8, [rsp+68h+arg_20]
0x18001c14e  mov     dword ptr cs:xmmword_1800295B0, r15d
0x18001c155  mov     edx, 8
0x18001c15a  mov     rcx, r14
0x18001c15d  call    NcaSizeTMultiply
0x18001c162  mov     ebx, eax
0x18001c164  test    eax, eax
0x18001c166  jns     short loc_18001C190
0x18001c168  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c16f  lea     rax, WPP_GLOBAL_Control
0x18001c176  cmp     rcx, rax
0x18001c179  jz      loc_18001C3DB
0x18001c17f  test    byte ptr [rcx+1Ch], 1
0x18001c183  jz      loc_18001C3DB
0x18001c189  mov     edx, 0Eh
0x18001c18e  jmp     short loc_18001C1D4
0x18001c190  mov     rcx, [rsp+68h+arg_20]
0x18001c198  call    NcaAlloc
0x18001c19d  mov     qword ptr cs:xmmword_1800295C0, rax
0x18001c1a4  test    rax, rax
0x18001c1a7  jnz     short loc_18001C1EC
0x18001c1a9  mov     ebx, 8007000Eh
0x18001c1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1b5  lea     rax, WPP_GLOBAL_Control
0x18001c1bc  cmp     rcx, rax
0x18001c1bf  jz      loc_18001C3DB
0x18001c1c5  test    byte ptr [rcx+1Ch], 1
0x18001c1c9  jz      loc_18001C3DB
0x18001c1cf  mov     edx, 0Fh
0x18001c1d4  mov     rcx, [rcx+10h]
0x18001c1d8  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c1df  mov     r9d, ebx
0x18001c1e2  call    WPP_SF_d
0x18001c1e7  jmp     loc_18001C3DB
0x18001c1ec  xor     ebp, ebp
0x18001c1ee  shl     r14, 3
0x18001c1f2  lea     rsi, ds:0[rbp*8]
0x18001c1fa  cmp     rsi, r14
0x18001c1fd  jnb     loc_18001C2B0
0x18001c203  mov     rcx, [rsi+r12]; Src
0x18001c207  lea     rdx, [rsi+rax]
0x18001c20b  call    NcaStringCopy
0x18001c210  mov     ebx, eax
0x18001c212  test    eax, eax
0x18001c214  js      short loc_18001C285
0x18001c216  mov     rcx, qword ptr cs:xmmword_1800295C0
0x18001c21d  xor     r8d, r8d; SecurityDescriptor
0x18001c220  inc     rbp
0x18001c223  mov     qword ptr cs:xmmword_1800295B0+8, rbp
0x18001c22a  mov     rcx, [rsi+rcx]; Protseq
0x18001c22e  lea     edx, [r8+0Ah]; MaxCalls
0x18001c232  call    cs:__imp_RpcServerUseProtseqW
0x18001c239  nop     dword ptr [rax+rax+00h]
0x18001c23e  test    eax, eax
0x18001c240  jnz     short loc_18001C24B
0x18001c242  mov     rax, qword ptr cs:xmmword_1800295C0
0x18001c249  jmp     short loc_18001C1F2
0x18001c24b  jg      short loc_18001C251
0x18001c24d  mov     ebx, eax
0x18001c24f  jmp     short loc_18001C25A
0x18001c251  movzx   ebx, ax
0x18001c254  or      ebx, 80070000h
0x18001c25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c261  lea     rax, WPP_GLOBAL_Control
0x18001c268  cmp     rcx, rax
0x18001c26b  jz      loc_18001C3D7
0x18001c271  test    byte ptr [rcx+1Ch], 1
0x18001c275  jz      loc_18001C3D7
0x18001c27b  mov     edx, 11h
0x18001c280  jmp     loc_18001C12E
0x18001c285  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c28c  lea     rax, WPP_GLOBAL_Control
0x18001c293  cmp     rcx, rax
0x18001c296  jz      loc_18001C3DB
0x18001c29c  test    byte ptr [rcx+1Ch], 1
0x18001c2a0  jz      loc_18001C3DB
0x18001c2a6  mov     edx, 10h
0x18001c2ab  jmp     loc_18001C1D4
0x18001c2b0  lea     rax, NcaRpcAPIsSecurityCallback
0x18001c2b7  neg     r15d
0x18001c2ba  mov     [rsp+68h+IfCallback], rax; IfCallback
0x18001c2bf  mov     rcx, r13; IfSpec
0x18001c2c2  sbb     r9d, r9d
0x18001c2c5  mov     [rsp+68h+MaxCalls], 4D2h; MaxCalls
0x18001c2cd  and     r9d, 0FFFFFFE0h
0x18001c2d1  xor     r8d, r8d; MgrEpv
0x18001c2d4  add     r9d, 29h ; ')'; Flags
0x18001c2d8  xor     edx, edx; MgrTypeUuid
0x18001c2da  call    cs:__imp_RpcServerRegisterIfEx
0x18001c2e1  nop     dword ptr [rax+rax+00h]
0x18001c2e6  test    eax, eax
0x18001c2e8  jz      short loc_18001C324
0x18001c2ea  jg      short loc_18001C2F0
0x18001c2ec  mov     ebx, eax
0x18001c2ee  jmp     short loc_18001C2F9
0x18001c2f0  movzx   ebx, ax
0x18001c2f3  or      ebx, 80070000h
0x18001c2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c300  lea     rax, WPP_GLOBAL_Control
0x18001c307  cmp     rcx, rax
0x18001c30a  jz      loc_18001C3D7
0x18001c310  test    byte ptr [rcx+1Ch], 1
0x18001c314  jz      loc_18001C3D7
0x18001c31a  mov     edx, 12h
0x18001c31f  jmp     loc_18001C12E
0x18001c324  lea     rcx, xmmword_1800295C0+8; BindingVector
0x18001c32b  mov     dword ptr cs:qword_1800295D0+4, 1
0x18001c335  call    cs:__imp_RpcServerInqBindings
0x18001c33c  nop     dword ptr [rax+rax+00h]
0x18001c341  test    eax, eax
0x18001c343  jz      short loc_18001C377
0x18001c345  jg      short loc_18001C34B
0x18001c347  mov     ebx, eax
0x18001c349  jmp     short loc_18001C354
0x18001c34b  movzx   ebx, ax
0x18001c34e  or      ebx, 80070000h
0x18001c354  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c35b  lea     rax, WPP_GLOBAL_Control
0x18001c362  cmp     rcx, rax
0x18001c365  jz      short loc_18001C3D7
0x18001c367  test    byte ptr [rcx+1Ch], 1
0x18001c36b  jz      short loc_18001C3D7
0x18001c36d  mov     edx, 13h
0x18001c372  jmp     loc_18001C12E
0x18001c377  mov     rdx, qword ptr cs:xmmword_1800295C0+8; BindingVector
0x18001c37e  lea     r9, Annotation; "Nca APIs"
0x18001c385  xor     r8d, r8d; UuidVector
0x18001c388  mov     rcx, r13; IfSpec
0x18001c38b  call    cs:__imp_RpcEpRegisterW
0x18001c392  nop     dword ptr [rax+rax+00h]
0x18001c397  test    eax, eax
0x18001c399  jz      short loc_18001C3CD
0x18001c39b  jg      short loc_18001C3A1
0x18001c39d  mov     ebx, eax
0x18001c39f  jmp     short loc_18001C3AA
0x18001c3a1  movzx   ebx, ax
0x18001c3a4  or      ebx, 80070000h
0x18001c3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3b1  lea     rax, WPP_GLOBAL_Control
0x18001c3b8  cmp     rcx, rax
0x18001c3bb  jz      short loc_18001C3D7
0x18001c3bd  test    byte ptr [rcx+1Ch], 1
0x18001c3c1  jz      short loc_18001C3D7
0x18001c3c3  mov     edx, 14h
0x18001c3c8  jmp     loc_18001C12E
0x18001c3cd  mov     dword ptr cs:qword_1800295D0, 1
0x18001c3d7  test    ebx, ebx
0x18001c3d9  jns     short loc_18001C3E0
0x18001c3db  call    NcaRpcAPIsInterfaceDestroy
0x18001c3e0  mov     eax, ebx
0x18001c3e2  add     rsp, 30h
0x18001c3e6  pop     r15
0x18001c3e8  pop     r14
0x18001c3ea  pop     r13
0x18001c3ec  pop     r12
0x18001c3ee  pop     rsi
0x18001c3ef  pop     rbp
0x18001c3f0  pop     rbx
0x18001c3f1  retn
```
