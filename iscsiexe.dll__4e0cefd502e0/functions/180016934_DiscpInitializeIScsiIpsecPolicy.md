# DiscpInitializeIScsiIpsecPolicy

- ea: `0x180016934`
- end: `0x180016b25`
- name: `DiscpInitializeIScsiIpsecPolicy`
- size: `497`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eeb0`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180014888`
- `0x180014d7c`
- `0x180016934`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800169b2`
- `ISCSIUM!DiscpAllocMemory` at `0x1800169b2`
- `ISCSIUM!DiscpFreeMemory` at `0x180016a70`
- `ISCSIUM!DiscpFreeMemory` at `0x180016ab7`
- `ISCSIUM!DiscpFreeMemory` at `0x180016ad4`
- `ISCSIUM!DiscpFreeMemory` at `0x180016a70`
- `ISCSIUM!DiscpFreeMemory` at `0x180016ab7`
- `ISCSIUM!DiscpFreeMemory` at `0x180016ad4`
- `fwpuclnt!FwpmEngineClose0` at `0x180016af1`
- `fwpuclnt!FwpmEngineClose0` at `0x180016af1`
- `fwpuclnt!FwpmEngineOpen0` at `0x18001699f`
- `fwpuclnt!FwpmEngineOpen0` at `0x18001699f`

## string_xrefs

- `0x18001696c`: `Microsoft iSCSI Initiator Service`

## pseudocode

```c
__int64 DiscpInitializeIScsiIpsecPolicy()
{
  unsigned int v0; // ebx
  __int64 v1; // rax
  __int64 v3[2]; // [rsp+30h] [rbp-78h] BYREF
  FWPM_SESSION0 session; // [rsp+40h] [rbp-68h] BYREF

  v3[0] = 0;
  memset_0(&session, 0, sizeof(session));
  session.displayData.name = L"Microsoft iSCSI Initiator Service";
  session.displayData.description = L"Microsoft iSCSI Initiator Service";
  session.flags = 1;
  v0 = FwpmEngineOpen0(0, 0xAu, 0, &session, &DiscpEngineHandle);
  if ( !v0 )
  {
    v1 = DiscpAllocMemory(124);
    if ( v1 )
    {
      *(_OWORD *)(v1 + 4) = 0;
      *(_DWORD *)(v1 + 36) = 0;
      *(_QWORD *)(v1 + 44) = 0;
      *(_DWORD *)(v1 + 56) = 28800;
      *(_DWORD *)(v1 + 40) = 1;
      *(_DWORD *)(v1 + 52) = 1;
      *(_QWORD *)(v1 + 60) = 3;
      *(_QWORD *)(v1 + 72) = 0;
      *(_DWORD *)(v1 + 84) = 28800;
      *(_DWORD *)(v1 + 68) = 1;
      *(_DWORD *)(v1 + 80) = 1;
      *(_QWORD *)(v1 + 88) = 2;
      *(_QWORD *)(v1 + 100) = 0;
      *(_DWORD *)(v1 + 112) = 28800;
      *(_DWORD *)(v1 + 96) = 1;
      *(_DWORD *)(v1 + 108) = 1;
      *(_QWORD *)(v1 + 116) = 1;
      *(_DWORD *)v1 = 28800;
      *(_QWORD *)(v1 + 24) = v1 + 40;
      *(_DWORD *)(v1 + 32) = 0;
      *(_DWORD *)(v1 + 20) = 3;
      DiscpMMPolicyTemplate = v1;
      v0 = DiscpBuildTxPolicyTemplate(v3, 0);
      if ( !v0 )
      {
        v0 = DiscpAddProviderContext(
               (__int64)L"iSCSI Initiator Transport NoPFS Policy",
               (__int64)L"iSCSI Initiator Transport NoPFS Policy",
               1,
               v3[0],
               (__int64)DiscpTxPolicyNoPFSGuid);
        DiscpFreeMemory(v3[0]);
        if ( !v0 )
        {
          v0 = DiscpBuildTxPolicyTemplate(v3, 6u);
          if ( !v0 )
          {
            v0 = DiscpAddProviderContext(
                   (__int64)L"iSCSI Initiator Transport PFS Policy",
                   (__int64)L"iSCSI Initiator Transport PFS Policy",
                   1,
                   v3[0],
                   (__int64)DiscpTxPolicyPFSGuid);
            DiscpFreeMemory(v3[0]);
            if ( !v0 )
              return v0;
          }
        }
      }
    }
    else
    {
      v0 = 8;
    }
    if ( DiscpMMPolicyTemplate )
    {
      DiscpFreeMemory(DiscpMMPolicyTemplate);
      DiscpMMPolicyTemplate = 0;
    }
    if ( DiscpEngineHandle )
    {
      FwpmEngineClose0(DiscpEngineHandle);
      DiscpEngineHandle = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180016934  mov     [rsp+arg_0], rbx
0x180016939  push    rsi
0x18001693a  sub     rsp, 0A0h
0x180016941  mov     rax, cs:__security_cookie
0x180016948  xor     rax, rsp
0x18001694b  mov     [rsp+0A8h+var_18], rax
0x180016953  xor     edx, edx; Val
0x180016955  mov     [rsp+0A8h+var_78], 0
0x18001695e  lea     rcx, [rsp+0A8h+session]; void *
0x180016963  lea     r8d, [rdx+48h]; Size
0x180016967  call    memset_0
0x18001696c  lea     rax, aMicrosoftIscsi; "Microsoft iSCSI Initiator Service"
0x180016973  mov     esi, 1
0x180016978  mov     [rsp+0A8h+session.displayData.name], rax
0x18001697d  lea     r9, [rsp+0A8h+session]; session
0x180016982  mov     [rsp+0A8h+session.displayData.description], rax
0x180016987  xor     r8d, r8d; authIdentity
0x18001698a  lea     rax, DiscpEngineHandle
0x180016991  mov     [rsp+0A8h+session.flags], esi
0x180016995  lea     edx, [rsi+9]; authnService
0x180016998  mov     [rsp+0A8h+engineHandle], rax; engineHandle
0x18001699d  xor     ecx, ecx; serverName
0x18001699f  call    cs:__imp_FwpmEngineOpen0
0x1800169a5  mov     ebx, eax
0x1800169a7  test    eax, eax
0x1800169a9  jnz     loc_180016B02
0x1800169af  lea     ecx, [rsi+7Bh]
0x1800169b2  call    cs:__imp_DiscpAllocMemory
0x1800169b8  test    rax, rax
0x1800169bb  jz      loc_180016AC3
0x1800169c1  mov     edx, 7080h
0x1800169c6  lea     r8d, [rsi+2]
0x1800169ca  xor     ecx, ecx
0x1800169cc  xorps   xmm0, xmm0
0x1800169cf  movups  xmmword ptr [rax+4], xmm0
0x1800169d3  mov     [rax+24h], ecx
0x1800169d6  lea     rcx, [rax+28h]
0x1800169da  mov     qword ptr [rax+2Ch], 0
0x1800169e2  mov     [rcx+10h], edx
0x1800169e5  mov     [rcx], esi
0x1800169e7  mov     [rcx+0Ch], esi
0x1800169ea  mov     [rcx+14h], r8
0x1800169ee  mov     qword ptr [rax+48h], 0
0x1800169f6  mov     [rcx+2Ch], edx
0x1800169f9  mov     [rcx+1Ch], esi
0x1800169fc  mov     [rcx+28h], esi
0x1800169ff  mov     qword ptr [rcx+30h], 2
0x180016a07  mov     qword ptr [rax+64h], 0
0x180016a0f  mov     [rcx+48h], edx
0x180016a12  mov     [rcx+38h], esi
0x180016a15  mov     [rcx+44h], esi
0x180016a18  mov     [rcx+4Ch], rsi
0x180016a1c  mov     [rax], edx
0x180016a1e  xor     edx, edx
0x180016a20  mov     [rax+18h], rcx
0x180016a24  lea     rcx, [rsp+0A8h+var_78]
0x180016a29  mov     [rax+20h], ebx
0x180016a2c  mov     [rax+14h], r8d
0x180016a30  mov     cs:DiscpMMPolicyTemplate, rax
0x180016a37  call    DiscpBuildTxPolicyTemplate
0x180016a3c  mov     ebx, eax
0x180016a3e  test    eax, eax
0x180016a40  jnz     loc_180016AC8
0x180016a46  mov     r9, [rsp+0A8h+var_78]
0x180016a4b  lea     rcx, aIscsiInitiator; "iSCSI Initiator Transport NoPFS Policy"
0x180016a52  lea     rax, DiscpTxPolicyNoPFSGuid
0x180016a59  mov     rdx, rcx
0x180016a5c  mov     r8d, esi
0x180016a5f  mov     [rsp+0A8h+engineHandle], rax
0x180016a64  call    DiscpAddProviderContext
0x180016a69  mov     rcx, [rsp+0A8h+var_78]
0x180016a6e  mov     ebx, eax
0x180016a70  call    cs:__imp_DiscpFreeMemory
0x180016a76  test    ebx, ebx
0x180016a78  jnz     short loc_180016AC8
0x180016a7a  lea     edx, [rsi+5]
0x180016a7d  lea     rcx, [rsp+0A8h+var_78]
0x180016a82  call    DiscpBuildTxPolicyTemplate
0x180016a87  mov     ebx, eax
0x180016a89  test    eax, eax
0x180016a8b  jnz     short loc_180016AC8
0x180016a8d  mov     r9, [rsp+0A8h+var_78]
0x180016a92  lea     rcx, aIscsiInitiator_0; "iSCSI Initiator Transport PFS Policy"
0x180016a99  lea     rax, DiscpTxPolicyPFSGuid
0x180016aa0  mov     rdx, rcx
0x180016aa3  mov     r8d, esi
0x180016aa6  mov     [rsp+0A8h+engineHandle], rax
0x180016aab  call    DiscpAddProviderContext
0x180016ab0  mov     rcx, [rsp+0A8h+var_78]
0x180016ab5  mov     ebx, eax
0x180016ab7  call    cs:__imp_DiscpFreeMemory
0x180016abd  test    ebx, ebx
0x180016abf  jz      short loc_180016B02
0x180016ac1  jmp     short loc_180016AC8
0x180016ac3  mov     ebx, 8
0x180016ac8  mov     rcx, cs:DiscpMMPolicyTemplate
0x180016acf  test    rcx, rcx
0x180016ad2  jz      short loc_180016AE5
0x180016ad4  call    cs:__imp_DiscpFreeMemory
0x180016ada  mov     cs:DiscpMMPolicyTemplate, 0
0x180016ae5  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x180016aec  test    rcx, rcx
0x180016aef  jz      short loc_180016B02
0x180016af1  call    cs:__imp_FwpmEngineClose0
0x180016af7  mov     cs:DiscpEngineHandle, 0
0x180016b02  mov     eax, ebx
0x180016b04  mov     rcx, [rsp+0A8h+var_18]
0x180016b0c  xor     rcx, rsp; StackCookie
0x180016b0f  call    __security_check_cookie
0x180016b14  mov     rbx, [rsp+0A8h+arg_0]
0x180016b1c  add     rsp, 0A0h
0x180016b23  pop     rsi
0x180016b24  retn
```
