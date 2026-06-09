# LipsBfeProviderContextDelete

- ea: `0x1800482dc`
- end: `0x180048423`
- name: `LipsBfeProviderContextDelete`
- size: `327`
- prototype: `__int64 __fastcall(GUID *key)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800454f0`
- `0x180045930`
- `0x180047094`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x1800482dc`
- `0x180048bd0`
- `0x180048ca4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180048364`
- `ntdll!EtwEventWrite` at `0x180048395`
- `ntdll!EtwEventWrite` at `0x180048364`
- `ntdll!EtwEventWrite` at `0x180048395`
- `RPCRT4!UuidIsNil` at `0x1800482f4`
- `RPCRT4!UuidIsNil` at `0x1800482f4`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180048374`
- `fwpuclnt!FwpmProviderContextDeleteByKey0` at `0x180048374`

## string_xrefs

- `0x1800483df`: `FwpmProviderContextDeleteByKey0`
- `0x18004840a`: `LipsBfeProviderContextDelete`

## pseudocode

```c
__int64 __fastcall LipsBfeProviderContextDelete(GUID *key)
{
  unsigned int v1; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // r8d
  RPC_STATUS Status; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  Status = 0;
  if ( UuidIsNil(key, &Status) )
    goto LABEL_18;
  v1 = LipsBfeBind();
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v4 = 31;
    goto LABEL_6;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_ProviderContextDeleteByKey_Begin, 0, 0);
  v1 = FwpmProviderContextDeleteByKey0(gLipsBfeEngineHandle, key);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_ProviderContextDeleteByKey_End, 0, 0);
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v4 = 32;
LABEL_6:
    WPP_SF_d(v3[2], v4, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v1);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      v5,
      (unsigned int)"FwpmProviderContextDeleteByKey0",
      (__int64)key);
LABEL_18:
  *key = 0;
  LipsBfeUnbindOnFailure(v1);
  if ( v1 )
    return LipsReportError(v1, "LipsBfeProviderContextDelete");
  else
    return 0;
}

```

## disassembly

```asm
0x1800482dc  mov     [rsp+arg_0], rbx
0x1800482e1  push    rdi
0x1800482e2  sub     rsp, 30h
0x1800482e6  xor     ebx, ebx
0x1800482e8  lea     rdx, [rsp+38h+Status]; Status
0x1800482ed  mov     [rsp+38h+Status], ebx
0x1800482f1  mov     rdi, rcx
0x1800482f4  call    cs:__imp_UuidIsNil
0x1800482fa  test    eax, eax
0x1800482fc  jnz     loc_1800483F5
0x180048302  call    LipsBfeBind
0x180048307  mov     ebx, eax
0x180048309  test    eax, eax
0x18004830b  jz      short loc_18004834B
0x18004830d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048314  lea     rax, WPP_GLOBAL_Control
0x18004831b  cmp     rcx, rax
0x18004831e  jz      loc_1800483F5
0x180048324  test    byte ptr [rcx+1Ch], 10h
0x180048328  jz      loc_1800483F5
0x18004832e  mov     edx, 1Fh
0x180048333  mov     rcx, [rcx+10h]
0x180048337  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x18004833e  mov     r9d, ebx
0x180048341  call    WPP_SF_d
0x180048346  jmp     loc_1800483F5
0x18004834b  mov     rcx, cs:g_Provider
0x180048352  test    rcx, rcx
0x180048355  jz      short loc_18004836A
0x180048357  xor     r9d, r9d
0x18004835a  lea     rdx, IPSEC_BFE_ProviderContextDeleteByKey_Begin
0x180048361  xor     r8d, r8d
0x180048364  call    cs:__imp_EtwEventWrite
0x18004836a  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x180048371  mov     rdx, rdi; key
0x180048374  call    cs:__imp_FwpmProviderContextDeleteByKey0
0x18004837a  mov     rcx, cs:g_Provider
0x180048381  mov     ebx, eax
0x180048383  test    rcx, rcx
0x180048386  jz      short loc_18004839B
0x180048388  xor     r9d, r9d
0x18004838b  lea     rdx, IPSEC_BFE_ProviderContextDeleteByKey_End
0x180048392  xor     r8d, r8d
0x180048395  call    cs:__imp_EtwEventWrite
0x18004839b  test    ebx, ebx
0x18004839d  jz      short loc_1800483C2
0x18004839f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483a6  lea     rax, WPP_GLOBAL_Control
0x1800483ad  cmp     rcx, rax
0x1800483b0  jz      short loc_1800483F5
0x1800483b2  test    byte ptr [rcx+1Ch], 10h
0x1800483b6  jz      short loc_1800483F5
0x1800483b8  mov     edx, 20h ; ' '
0x1800483bd  jmp     loc_180048333
0x1800483c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483c9  lea     rax, WPP_GLOBAL_Control
0x1800483d0  cmp     rcx, rax
0x1800483d3  jz      short loc_1800483F5
0x1800483d5  test    byte ptr [rcx+1Ch], 4
0x1800483d9  jz      short loc_1800483F5
0x1800483db  mov     rcx, [rcx+10h]
0x1800483df  lea     r9, aFwpmproviderco; "FwpmProviderContextDeleteByKey0"
0x1800483e6  mov     edx, 21h ; '!'
0x1800483eb  mov     [rsp+38h+var_18], rdi
0x1800483f0  call    WPP_SF_s_guid_
0x1800483f5  xorps   xmm0, xmm0
0x1800483f8  mov     ecx, ebx
0x1800483fa  movups  xmmword ptr [rdi], xmm0
0x1800483fd  call    LipsBfeUnbindOnFailure
0x180048402  test    ebx, ebx
0x180048404  jnz     short loc_18004840A
0x180048406  xor     eax, eax
0x180048408  jmp     short loc_180048418
0x18004840a  lea     rdx, aLipsbfeprovide_0; "LipsBfeProviderContextDelete"
0x180048411  mov     ecx, ebx
0x180048413  call    LipsReportError
0x180048418  mov     rbx, [rsp+38h+arg_0]
0x18004841d  add     rsp, 30h
0x180048421  pop     rdi
0x180048422  retn
```
