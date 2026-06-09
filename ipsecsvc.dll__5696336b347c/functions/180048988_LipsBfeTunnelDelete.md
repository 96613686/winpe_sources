# LipsBfeTunnelDelete

- ea: `0x180048988`
- end: `0x180048aab`
- name: `LipsBfeTunnelDelete`
- size: `291`
- prototype: `__int64 __fastcall(GUID *key)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180049b30`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x180047c94`
- `0x180048988`
- `0x180048bd0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180048a11`
- `ntdll!EtwEventWrite` at `0x180048a42`
- `ntdll!EtwEventWrite` at `0x180048a11`
- `ntdll!EtwEventWrite` at `0x180048a42`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x180048a21`
- `fwpuclnt!FwpmIPsecTunnelDeleteByKey0` at `0x180048a21`

## string_xrefs

- `0x180048a92`: `LipsBfeTunnelDelete`

## pseudocode

```c
__int64 __fastcall LipsBfeTunnelDelete(GUID *key)
{
  unsigned int v1; // ebx
  __int64 v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  v1 = 0;
  v3 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&key->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&key->Data1 )
    v3 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)key->Data4;
  if ( v3 )
  {
    if ( !--gLipsNumExemptionCount )
      LipsBfeDeleteIpv6NbrDiscExemptions();
    v1 = LipsBfeBind();
    if ( v1 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_19;
      v5 = 44;
      goto LABEL_18;
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_FilterDeleteByKey_Begin, 0, 0);
    v1 = FwpmIPsecTunnelDeleteByKey0(gLipsBfeEngineHandle, key);
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_FilterDeleteByKey_End, 0, 0);
    if ( v1 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v5 = 45;
LABEL_18:
        WPP_SF_d(v4[2], v5, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v1);
      }
    }
  }
LABEL_19:
  *key = 0;
  LipsBfeUnbindOnFailure(v1);
  if ( v1 )
    return LipsReportError(v1, "LipsBfeTunnelDelete");
  else
    return 0;
}

```

## disassembly

```asm
0x180048988  mov     [rsp+arg_0], rbx
0x18004898d  push    rdi
0x18004898e  sub     rsp, 20h
0x180048992  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180048999  xor     ebx, ebx
0x18004899b  mov     rdi, rcx
0x18004899e  sub     rax, [rcx]
0x1800489a1  jnz     short loc_1800489AE
0x1800489a3  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800489aa  sub     rax, [rcx+8]
0x1800489ae  test    rax, rax
0x1800489b1  jz      loc_180048A7D
0x1800489b7  add     cs:gLipsNumExemptionCount, 0FFFFFFFFh
0x1800489be  jnz     short loc_1800489C5
0x1800489c0  call    LipsBfeDeleteIpv6NbrDiscExemptions
0x1800489c5  call    LipsBfeBind
0x1800489ca  mov     ebx, eax
0x1800489cc  test    eax, eax
0x1800489ce  jz      short loc_1800489F8
0x1800489d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489d7  lea     rax, WPP_GLOBAL_Control
0x1800489de  cmp     rcx, rax
0x1800489e1  jz      loc_180048A7D
0x1800489e7  test    byte ptr [rcx+1Ch], 10h
0x1800489eb  jz      loc_180048A7D
0x1800489f1  mov     edx, 2Ch ; ','
0x1800489f6  jmp     short loc_180048A6A
0x1800489f8  mov     rcx, cs:g_Provider
0x1800489ff  test    rcx, rcx
0x180048a02  jz      short loc_180048A17
0x180048a04  xor     r9d, r9d
0x180048a07  lea     rdx, IPSEC_BFE_FilterDeleteByKey_Begin
0x180048a0e  xor     r8d, r8d
0x180048a11  call    cs:__imp_EtwEventWrite
0x180048a17  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x180048a1e  mov     rdx, rdi; key
0x180048a21  call    cs:__imp_FwpmIPsecTunnelDeleteByKey0
0x180048a27  mov     rcx, cs:g_Provider
0x180048a2e  mov     ebx, eax
0x180048a30  test    rcx, rcx
0x180048a33  jz      short loc_180048A48
0x180048a35  xor     r9d, r9d
0x180048a38  lea     rdx, IPSEC_BFE_FilterDeleteByKey_End
0x180048a3f  xor     r8d, r8d
0x180048a42  call    cs:__imp_EtwEventWrite
0x180048a48  test    ebx, ebx
0x180048a4a  jz      short loc_180048A7D
0x180048a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048a53  lea     rax, WPP_GLOBAL_Control
0x180048a5a  cmp     rcx, rax
0x180048a5d  jz      short loc_180048A7D
0x180048a5f  test    byte ptr [rcx+1Ch], 10h
0x180048a63  jz      short loc_180048A7D
0x180048a65  mov     edx, 2Dh ; '-'
0x180048a6a  mov     rcx, [rcx+10h]
0x180048a6e  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180048a75  mov     r9d, ebx
0x180048a78  call    WPP_SF_d
0x180048a7d  xorps   xmm0, xmm0
0x180048a80  mov     ecx, ebx
0x180048a82  movups  xmmword ptr [rdi], xmm0
0x180048a85  call    LipsBfeUnbindOnFailure
0x180048a8a  test    ebx, ebx
0x180048a8c  jnz     short loc_180048A92
0x180048a8e  xor     eax, eax
0x180048a90  jmp     short loc_180048AA0
0x180048a92  lea     rdx, aLipsbfetunneld; "LipsBfeTunnelDelete"
0x180048a99  mov     ecx, ebx
0x180048a9b  call    LipsReportError
0x180048aa0  mov     rbx, [rsp+28h+arg_0]
0x180048aa5  add     rsp, 20h
0x180048aa9  pop     rdi
0x180048aaa  retn
```
