# LipsBfeFilterAdd

- ea: `0x180047e20`
- end: `0x180047f59`
- name: `LipsBfeFilterAdd`
- size: `313`
- prototype: `__int64 __fastcall(FWPM_FILTER0 *filter)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800454f0`
- `0x180045f98`
- `0x180046160`
- `0x18004713c`
- `0x1800475ec`
- `0x180047a34`
- `0x1800491d8`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x180047e20`
- `0x180048bd0`
- `0x180048d24`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180047e9a`
- `ntdll!EtwEventWrite` at `0x180047ed1`
- `ntdll!EtwEventWrite` at `0x180047e9a`
- `ntdll!EtwEventWrite` at `0x180047ed1`
- `fwpuclnt!FwpmFilterAdd0` at `0x180047eb0`
- `fwpuclnt!FwpmFilterAdd0` at `0x180047eb0`

## pseudocode

```c
__int64 __fastcall LipsBfeFilterAdd(FWPM_FILTER0 *filter)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int v5; // edx
  int v6; // r8d
  int v7; // r9d

  filter->providerKey = (GUID *)LipsProviderGuid;
  v2 = LipsBfeBind();
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_17;
    v4 = 34;
    goto LABEL_5;
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_FilterAdd_Begin, 0, 0);
  v2 = FwpmFilterAdd0(gLipsBfeEngineHandle, filter, 0, 0);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_FilterAdd_End, 0, 0);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_17;
    v4 = 35;
LABEL_5:
    WPP_SF_d(v3[2], v4, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v2);
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s_guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, v7, (__int64)filter, (__int64)&filter->rawContext);
LABEL_17:
  LipsBfeUnbindOnFailure(v2);
  if ( v2 )
    return LipsReportError(v2, "LipsBfeFilterAdd");
  else
    return 0;
}

```

## disassembly

```asm
0x180047e20  mov     [rsp+arg_0], rbx
0x180047e25  push    rdi
0x180047e26  sub     rsp, 30h
0x180047e2a  lea     rax, LipsProviderGuid
0x180047e31  mov     rdi, rcx
0x180047e34  mov     [rcx+28h], rax
0x180047e38  call    LipsBfeBind
0x180047e3d  mov     ebx, eax
0x180047e3f  test    eax, eax
0x180047e41  jz      short loc_180047E81
0x180047e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e4a  lea     rax, WPP_GLOBAL_Control
0x180047e51  cmp     rcx, rax
0x180047e54  jz      loc_180047F31
0x180047e5a  test    byte ptr [rcx+1Ch], 10h
0x180047e5e  jz      loc_180047F31
0x180047e64  mov     edx, 22h ; '"'
0x180047e69  mov     rcx, [rcx+10h]
0x180047e6d  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180047e74  mov     r9d, ebx
0x180047e77  call    WPP_SF_d
0x180047e7c  jmp     loc_180047F31
0x180047e81  mov     rcx, cs:g_Provider
0x180047e88  test    rcx, rcx
0x180047e8b  jz      short loc_180047EA0
0x180047e8d  xor     r9d, r9d
0x180047e90  lea     rdx, IPSEC_BFE_FilterAdd_Begin
0x180047e97  xor     r8d, r8d
0x180047e9a  call    cs:__imp_EtwEventWrite
0x180047ea0  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x180047ea7  xor     r9d, r9d; id
0x180047eaa  xor     r8d, r8d; sd
0x180047ead  mov     rdx, rdi; filter
0x180047eb0  call    cs:__imp_FwpmFilterAdd0
0x180047eb6  mov     rcx, cs:g_Provider
0x180047ebd  mov     ebx, eax
0x180047ebf  test    rcx, rcx
0x180047ec2  jz      short loc_180047ED7
0x180047ec4  xor     r9d, r9d
0x180047ec7  lea     rdx, IPSEC_BFE_FilterAdd_End
0x180047ece  xor     r8d, r8d
0x180047ed1  call    cs:__imp_EtwEventWrite
0x180047ed7  test    ebx, ebx
0x180047ed9  jz      short loc_180047EFE
0x180047edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ee2  lea     rax, WPP_GLOBAL_Control
0x180047ee9  cmp     rcx, rax
0x180047eec  jz      short loc_180047F31
0x180047eee  test    byte ptr [rcx+1Ch], 10h
0x180047ef2  jz      short loc_180047F31
0x180047ef4  mov     edx, 23h ; '#'
0x180047ef9  jmp     loc_180047E69
0x180047efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f05  lea     rax, WPP_GLOBAL_Control
0x180047f0c  cmp     rcx, rax
0x180047f0f  jz      short loc_180047F31
0x180047f11  test    byte ptr [rcx+1Ch], 4
0x180047f15  jz      short loc_180047F31
0x180047f17  mov     rcx, [rcx+10h]
0x180047f1b  lea     rax, [rdi+98h]
0x180047f22  mov     [rsp+38h+var_10], rax
0x180047f27  mov     [rsp+38h+var_18], rdi
0x180047f2c  call    WPP_SF_s_guid__guid_
0x180047f31  mov     ecx, ebx
0x180047f33  call    LipsBfeUnbindOnFailure
0x180047f38  test    ebx, ebx
0x180047f3a  jnz     short loc_180047F40
0x180047f3c  xor     eax, eax
0x180047f3e  jmp     short loc_180047F4E
0x180047f40  lea     rdx, aLipsbfefiltera; "LipsBfeFilterAdd"
0x180047f47  mov     ecx, ebx
0x180047f49  call    LipsReportError
0x180047f4e  mov     rbx, [rsp+38h+arg_0]
0x180047f53  add     rsp, 30h
0x180047f57  pop     rdi
0x180047f58  retn
```
