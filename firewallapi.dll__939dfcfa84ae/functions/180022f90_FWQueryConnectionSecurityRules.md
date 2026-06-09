# FWQueryConnectionSecurityRules

- ea: `0x180022f90`
- end: `0x1800230ce`
- name: `FWQueryConnectionSecurityRules`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000a530`
- `0x180022f90`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180022fcb`
- `ntdll!EtwEventWrite` at `0x1800230b2`
- `ntdll!EtwEventWrite` at `0x180022fcb`
- `ntdll!EtwEventWrite` at `0x1800230b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180023005`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180023005`

## pseudocode

```c
__int64 __fastcall FWQueryConnectionSecurityRules(__int64 a1, __int64 a2, __int16 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryConnectionSecurityRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v9 = Int_FWQueryObject(
         1,
         (unsigned int)FWVerifyConnectionSecurityRuleQuery,
         (unsigned int)RPC_FWQueryConnectionSecurityRules2_10,
         (unsigned int)RRPC_FWQueryConnectionSecurityRules2_10,
         (__int64)Int_RPC_FWEnumConnectionSecurityRules2_0,
         (__int64)Int_RRPC_FWEnumConnectionSecurityRules2_0,
         a1,
         a2,
         a3,
         a4,
         a5,
         0);
  v10 = v9;
  if ( v9 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v9);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryConnectionSecurityRules, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x180022f90  push    rbx
0x180022f92  push    rbp
0x180022f93  push    rsi
0x180022f94  push    rdi
0x180022f95  push    r14
0x180022f97  push    r15
0x180022f99  sub     rsp, 68h
0x180022f9d  mov     r14, [rsp+98h+arg_20]
0x180022fa5  mov     rbx, rcx
0x180022fa8  mov     rcx, cs:g_Provider
0x180022faf  mov     rbp, r9
0x180022fb2  movzx   esi, r8w
0x180022fb6  mov     rdi, rdx
0x180022fb9  test    rcx, rcx
0x180022fbc  jz      short loc_180022FD7
0x180022fbe  xor     r9d, r9d
0x180022fc1  lea     rdx, MPS_CLNT_API_Enter_QueryConnectionSecurityRules
0x180022fc8  xor     r8d, r8d
0x180022fcb  call    cs:__imp_EtwEventWrite
0x180022fd2  nop     dword ptr [rax+rax+00h]
0x180022fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fde  lea     r15, WPP_GLOBAL_Control
0x180022fe5  cmp     rcx, r15
0x180022fe8  jz      short loc_180023005
0x180022fea  test    byte ptr [rcx+1Ch], 8
0x180022fee  jz      short loc_180023005
0x180022ff0  mov     rcx, [rcx+10h]
0x180022ff4  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180022ffb  mov     edx, 0B8h
0x180023000  call    WPP_SF_
0x180023005  call    cs:__imp_GetTickCount64
0x18002300c  nop     dword ptr [rax+rax+00h]
0x180023011  mov     [rsp+98h+var_40], 0
0x180023019  lea     rax, ?Int_RRPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180023020  mov     [rsp+98h+var_48], r14
0x180023025  lea     r9, RRPC_FWQueryConnectionSecurityRules2_10
0x18002302c  mov     [rsp+98h+var_50], rbp
0x180023031  lea     r8, RPC_FWQueryConnectionSecurityRules2_10
0x180023038  mov     [rsp+98h+var_58], si
0x18002303d  lea     rdx, FWVerifyConnectionSecurityRuleQuery
0x180023044  mov     [rsp+98h+var_60], rdi
0x180023049  mov     ecx, 1
0x18002304e  mov     [rsp+98h+var_68], rbx
0x180023053  mov     [rsp+98h+var_70], rax
0x180023058  lea     rax, ?Int_RPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18002305f  mov     [rsp+98h+var_78], rax
0x180023064  call    Int_FWQueryObject
0x180023069  mov     ebx, eax
0x18002306b  test    eax, eax
0x18002306d  jz      short loc_180023099
0x18002306f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023076  cmp     rcx, r15
0x180023079  jz      short loc_180023099
0x18002307b  test    byte ptr [rcx+1Ch], 1
0x18002307f  jz      short loc_180023099
0x180023081  mov     rcx, [rcx+10h]
0x180023085  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18002308c  mov     edx, 0B9h
0x180023091  mov     r9d, eax
0x180023094  call    WPP_SF_d
0x180023099  mov     rcx, cs:g_Provider
0x1800230a0  test    rcx, rcx
0x1800230a3  jz      short loc_1800230BE
0x1800230a5  xor     r9d, r9d
0x1800230a8  lea     rdx, MPS_CLNT_API_Exit_QueryConnectionSecurityRules
0x1800230af  xor     r8d, r8d
0x1800230b2  call    cs:__imp_EtwEventWrite
0x1800230b9  nop     dword ptr [rax+rax+00h]
0x1800230be  mov     eax, ebx
0x1800230c0  add     rsp, 68h
0x1800230c4  pop     r15
0x1800230c6  pop     r14
0x1800230c8  pop     rdi
0x1800230c9  pop     rsi
0x1800230ca  pop     rbp
0x1800230cb  pop     rbx
0x1800230cc  retn
```
