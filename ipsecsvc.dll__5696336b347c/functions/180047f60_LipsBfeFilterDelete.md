# LipsBfeFilterDelete

- ea: `0x180047f60`
- end: `0x1800480b0`
- name: `LipsBfeFilterDelete`
- size: `336`
- prototype: `__int64 __fastcall(GUID *key)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180045930`
- `0x18004606c`
- `0x180046880`
- `0x180047c94`
- `0x180047d18`
- `0x180047d9c`
- `0x180049b30`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x180047f60`
- `0x180048bd0`
- `0x180048ca4`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180047ff1`
- `ntdll!EtwEventWrite` at `0x180048022`
- `ntdll!EtwEventWrite` at `0x180047ff1`
- `ntdll!EtwEventWrite` at `0x180048022`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180048001`
- `fwpuclnt!FwpmFilterDeleteByKey0` at `0x180048001`

## string_xrefs

- `0x18004806c`: `FwpmFilterDeleteByKey0`
- `0x180048097`: `LipsBfeFilterDelete`

## pseudocode

```c
__int64 __fastcall LipsBfeFilterDelete(GUID *key)
{
  unsigned int v1; // ebx
  __int64 v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v6; // r8d

  v1 = 0;
  v3 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&key->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&key->Data1 )
    v3 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)key->Data4;
  if ( v3 )
  {
    v1 = LipsBfeBind();
    if ( v1 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_20;
      v5 = 38;
      goto LABEL_8;
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_FilterDeleteByKey_Begin, 0, 0);
    v1 = FwpmFilterDeleteByKey0(gLipsBfeEngineHandle, key);
    if ( g_Provider )
      EtwEventWrite(g_Provider, IPSEC_BFE_FilterDeleteByKey_End, 0, 0);
    if ( v1 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_20;
      v5 = 39;
LABEL_8:
      WPP_SF_d(v4[2], v5, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v1);
      goto LABEL_20;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_s_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v6, (unsigned int)"FwpmFilterDeleteByKey0", (__int64)key);
  }
LABEL_20:
  *key = 0;
  LipsBfeUnbindOnFailure(v1);
  if ( v1 )
    return LipsReportError(v1, "LipsBfeFilterDelete");
  else
    return 0;
}

```

## disassembly

```asm
0x180047f60  mov     [rsp+arg_0], rbx
0x180047f65  push    rdi
0x180047f66  sub     rsp, 30h
0x180047f6a  mov     rax, qword ptr cs:GUID_NULL.Data1
0x180047f71  xor     ebx, ebx
0x180047f73  mov     rdi, rcx
0x180047f76  sub     rax, [rcx]
0x180047f79  jnz     short loc_180047F86
0x180047f7b  mov     rax, qword ptr cs:GUID_NULL.Data4
0x180047f82  sub     rax, [rcx+8]
0x180047f86  test    rax, rax
0x180047f89  jz      loc_180048082
0x180047f8f  call    LipsBfeBind
0x180047f94  mov     ebx, eax
0x180047f96  test    eax, eax
0x180047f98  jz      short loc_180047FD8
0x180047f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fa1  lea     rax, WPP_GLOBAL_Control
0x180047fa8  cmp     rcx, rax
0x180047fab  jz      loc_180048082
0x180047fb1  test    byte ptr [rcx+1Ch], 10h
0x180047fb5  jz      loc_180048082
0x180047fbb  mov     edx, 26h ; '&'
0x180047fc0  mov     rcx, [rcx+10h]
0x180047fc4  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180047fcb  mov     r9d, ebx
0x180047fce  call    WPP_SF_d
0x180047fd3  jmp     loc_180048082
0x180047fd8  mov     rcx, cs:g_Provider
0x180047fdf  test    rcx, rcx
0x180047fe2  jz      short loc_180047FF7
0x180047fe4  xor     r9d, r9d
0x180047fe7  lea     rdx, IPSEC_BFE_FilterDeleteByKey_Begin
0x180047fee  xor     r8d, r8d
0x180047ff1  call    cs:__imp_EtwEventWrite
0x180047ff7  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x180047ffe  mov     rdx, rdi; key
0x180048001  call    cs:__imp_FwpmFilterDeleteByKey0
0x180048007  mov     rcx, cs:g_Provider
0x18004800e  mov     ebx, eax
0x180048010  test    rcx, rcx
0x180048013  jz      short loc_180048028
0x180048015  xor     r9d, r9d
0x180048018  lea     rdx, IPSEC_BFE_FilterDeleteByKey_End
0x18004801f  xor     r8d, r8d
0x180048022  call    cs:__imp_EtwEventWrite
0x180048028  test    ebx, ebx
0x18004802a  jz      short loc_18004804F
0x18004802c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048033  lea     rax, WPP_GLOBAL_Control
0x18004803a  cmp     rcx, rax
0x18004803d  jz      short loc_180048082
0x18004803f  test    byte ptr [rcx+1Ch], 10h
0x180048043  jz      short loc_180048082
0x180048045  mov     edx, 27h ; '''
0x18004804a  jmp     loc_180047FC0
0x18004804f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048056  lea     rax, WPP_GLOBAL_Control
0x18004805d  cmp     rcx, rax
0x180048060  jz      short loc_180048082
0x180048062  test    byte ptr [rcx+1Ch], 4
0x180048066  jz      short loc_180048082
0x180048068  mov     rcx, [rcx+10h]
0x18004806c  lea     r9, aFwpmfilterdele; "FwpmFilterDeleteByKey0"
0x180048073  mov     edx, 28h ; '('
0x180048078  mov     [rsp+38h+var_18], rdi
0x18004807d  call    WPP_SF_s_guid_
0x180048082  xorps   xmm0, xmm0
0x180048085  mov     ecx, ebx
0x180048087  movups  xmmword ptr [rdi], xmm0
0x18004808a  call    LipsBfeUnbindOnFailure
0x18004808f  test    ebx, ebx
0x180048091  jnz     short loc_180048097
0x180048093  xor     eax, eax
0x180048095  jmp     short loc_1800480A5
0x180048097  lea     rdx, aLipsbfefilterd; "LipsBfeFilterDelete"
0x18004809e  mov     ecx, ebx
0x1800480a0  call    LipsReportError
0x1800480a5  mov     rbx, [rsp+38h+arg_0]
0x1800480aa  add     rsp, 30h
0x1800480ae  pop     rdi
0x1800480af  retn
```
