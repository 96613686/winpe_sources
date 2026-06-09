# GMSAInit

- ea: `0x180005b10`
- end: `0x180005e69`
- name: `GMSAInit`
- size: `857`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001400`
- `0x180001c8a`
- `0x180005b10`
- `0x180006280`
- `0x1800062b0`
- `0x1800065a8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180005bfe`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180005bfe`
- `ntdll!RtlDuplicateUnicodeString` at `0x180005cbb`
- `ntdll!RtlDuplicateUnicodeString` at `0x180005d20`
- `ntdll!RtlDuplicateUnicodeString` at `0x180005cbb`
- `ntdll!RtlDuplicateUnicodeString` at `0x180005d20`
- `ntdll!RtlInitializeResource` at `0x180005c85`
- `ntdll!RtlInitializeResource` at `0x180005c85`
- `ntdll!RtlFreeUnicodeString` at `0x180005e04`
- `ntdll!RtlFreeUnicodeString` at `0x180005e17`
- `ntdll!RtlFreeUnicodeString` at `0x180005e04`
- `ntdll!RtlFreeUnicodeString` at `0x180005e17`

## string_xrefs

- `0x180005b98`: `gmsaclient`

## pseudocode

```c
__int64 __fastcall GMSAInit(
        int a1,
        struct _TRACE_GUID_REGISTRATION *a2,
        struct _TRACE_GUID_REGISTRATION *a3,
        __int64 a4)
{
  ULONG64 *v8; // rsi
  const GUID **v9; // r14
  const GUID *v10; // r8
  _QWORD *v11; // rcx
  struct _TRACE_GUID_REGISTRATION *p_TraceGuidReg; // rdx
  NTSTATUS v14; // eax
  unsigned int v15; // esi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  HLOCAL *v18; // rbx
  struct _TRACE_GUID_REGISTRATION *v19; // rdx
  __int64 v20; // rax
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-278h] BYREF
  WCHAR MofResourceName[16]; // [rsp+50h] [rbp-268h] BYREF
  WCHAR MofImagePath[264]; // [rsp+70h] [rbp-248h] BYREF

  qword_18000B568 = 0;
  WPP_MAIN_CB = 0;
  qword_18000B570 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_GmsaClientTraceControlGuid;
  v8 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v9 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  memset_0(MofImagePath, 0, 0x208u);
  wcscpy(MofResourceName, L"gmsaclent");
  do
  {
    v10 = *v9++;
    TraceGuidReg.Guid = v10;
    TraceGuidReg.RegHandle = 0;
    v8[4] = (ULONG64)v10;
    RegisterTraceGuidsW(WppControlCallback, v8, v10, 1u, &TraceGuidReg, MofImagePath, MofResourceName, v8 + 1);
    v8 = (ULONG64 *)*v8;
  }
  while ( v8 );
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( dword_18000B67C )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_(v11[2], 11, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    return 3221225701LL;
  }
  dword_18000B680 = a1;
  RtlInitializeResource(&Resource);
  dword_18000B670 = 0;
  TraceGuidReg = 0;
  p_TraceGuidReg = &TraceGuidReg;
  if ( a2 )
    p_TraceGuidReg = a2;
  v14 = RtlDuplicateUnicodeString(3u, (PCUNICODE_STRING)p_TraceGuidReg, &SourceString);
  v15 = v14;
  if ( v14 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v17 = 13;
    goto LABEL_17;
  }
  TraceGuidReg = 0;
  v19 = &TraceGuidReg;
  if ( a3 )
    v19 = a3;
  v14 = RtlDuplicateUnicodeString(3u, (PCUNICODE_STRING)v19, &stru_18000B5F8);
  v15 = v14;
  if ( v14 >= 0 )
  {
    xmmword_18000B580 = *(_OWORD *)a4;
    xmmword_18000B590 = *(_OWORD *)(a4 + 16);
    xmmword_18000B5A0 = *(_OWORD *)(a4 + 32);
    xmmword_18000B5B0 = *(_OWORD *)(a4 + 48);
    xmmword_18000B5C0 = *(_OWORD *)(a4 + 64);
    qword_18000B5D0 = *(_QWORD *)(a4 + 80);
    v18 = &hMem;
    qword_18000B5E0 = (__int64)&hMem;
    hMem = &hMem;
    dword_18000B678 = 1;
    dword_18000B67C = 1;
    goto LABEL_26;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 14;
LABEL_17:
    WPP_SF_D(v16[2], v17, &WPP_70b8577d707437755865c965214ce19a_Traceguids, (unsigned int)v14);
  }
LABEL_18:
  v18 = &hMem;
LABEL_26:
  if ( !dword_18000B67C )
  {
    RtlFreeUnicodeString(&SourceString);
    RtlFreeUnicodeString(&stru_18000B5F8);
    v20 = 16;
    do
    {
      *(_BYTE *)v18 = 0;
      v18 = (HLOCAL *)((char *)v18 + 1);
      --v20;
    }
    while ( v20 );
    WppCleanupUm();
  }
  return v15;
}

```

## disassembly

```asm
0x180005b10  mov     [rsp+arg_0], rbx
0x180005b15  mov     [rsp+arg_18], rsi
0x180005b1a  push    rdi
0x180005b1b  push    r12
0x180005b1d  push    r13
0x180005b1f  push    r14
0x180005b21  push    r15
0x180005b23  sub     rsp, 290h
0x180005b2a  mov     rax, cs:__security_cookie
0x180005b31  xor     rax, rsp
0x180005b34  mov     [rsp+2B8h+var_38], rax
0x180005b3c  mov     rbx, r9
0x180005b3f  mov     r13, r8
0x180005b42  mov     r12, rdx
0x180005b45  mov     r15d, ecx
0x180005b48  xor     edi, edi
0x180005b4a  mov     cs:qword_18000B568, rdi
0x180005b51  mov     cs:WPP_MAIN_CB, rdi
0x180005b58  mov     cs:qword_18000B570, 1
0x180005b63  lea     rax, WPP_ThisDir_CTLGUID_GmsaClientTraceControlGuid
0x180005b6a  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180005b71  lea     rsi, WPP_MAIN_CB
0x180005b78  mov     cs:WPP_GLOBAL_Control, rsi
0x180005b7f  lea     r14, WPP_REGISTRATION_GUIDS
0x180005b86  xor     edx, edx; Val
0x180005b88  mov     r8d, 208h; Size
0x180005b8e  lea     rcx, [rsp+2B8h+var_248]; void *
0x180005b93  call    memset_0
0x180005b98  movups  xmm0, xmmword ptr cs:aGmsaclient; "gmsaclient"
0x180005b9f  movups  xmmword ptr [rsp+2B8h+var_268], xmm0
0x180005ba4  movsd   xmm1, qword ptr cs:aGmsaclient+0Eh; "ent"
0x180005bac  movsd   qword ptr [rsp+2B8h+var_268+0Eh], xmm1
0x180005bb2  mov     r8, [r14]; ControlGuid
0x180005bb5  lea     r14, [r14+8]
0x180005bb9  mov     [rsp+2B8h+var_278.Guid], r8
0x180005bbe  mov     [rsp+2B8h+var_278.RegHandle], rdi
0x180005bc3  mov     [rsi+20h], r8
0x180005bc7  lea     rax, [rsi+8]
0x180005bcb  mov     [rsp+2B8h+RegistrationHandle], rax; RegistrationHandle
0x180005bd0  lea     rax, [rsp+2B8h+var_268]
0x180005bd5  mov     [rsp+2B8h+MofResourceName], rax; MofResourceName
0x180005bda  lea     rax, [rsp+2B8h+var_248]
0x180005bdf  mov     [rsp+2B8h+MofImagePath], rax; MofImagePath
0x180005be4  lea     rax, [rsp+2B8h+var_278]
0x180005be9  mov     [rsp+2B8h+TraceGuidReg], rax; TraceGuidReg
0x180005bee  mov     r9d, 1; GuidCount
0x180005bf4  mov     rdx, rsi; RequestContext
0x180005bf7  lea     rcx, WppControlCallback; RequestAddress
0x180005bfe  call    cs:__imp_RegisterTraceGuidsW
0x180005c05  nop     dword ptr [rax+rax+00h]
0x180005c0a  mov     rsi, [rsi]
0x180005c0d  test    rsi, rsi
0x180005c10  jnz     short loc_180005BB2
0x180005c12  lea     r14, WPP_GLOBAL_Control
0x180005c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c20  cmp     rcx, r14
0x180005c23  jz      short loc_180005C45
0x180005c25  test    byte ptr [rcx+1Ch], 8
0x180005c29  jz      short loc_180005C45
0x180005c2b  lea     edx, [rsi+0Ah]
0x180005c2e  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005c35  mov     rcx, [rcx+10h]
0x180005c39  call    WPP_SF_
0x180005c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c45  cmp     cs:dword_18000B67C, edi
0x180005c4b  jz      short loc_180005C77
0x180005c4d  cmp     rcx, r14
0x180005c50  jz      short loc_180005C6D
0x180005c52  test    byte ptr [rcx+1Ch], 1
0x180005c56  jz      short loc_180005C6D
0x180005c58  mov     edx, 0Bh
0x180005c5d  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005c64  mov     rcx, [rcx+10h]
0x180005c68  call    WPP_SF_
0x180005c6d  mov     eax, 0C00000E5h
0x180005c72  jmp     loc_180005E3B
0x180005c77  mov     cs:dword_18000B680, r15d
0x180005c7e  lea     rcx, Resource; Resource
0x180005c85  call    cs:__imp_RtlInitializeResource
0x180005c8c  nop     dword ptr [rax+rax+00h]
0x180005c91  mov     cs:dword_18000B670, edi
0x180005c97  xorps   xmm0, xmm0
0x180005c9a  movups  xmmword ptr [rsp+2B8h+var_278.Guid], xmm0
0x180005c9f  lea     rdx, [rsp+2B8h+var_278]
0x180005ca4  test    r12, r12
0x180005ca7  cmovnz  rdx, r12; SourceString
0x180005cab  lea     r8, SourceString; DestinationString
0x180005cb2  mov     r15d, 3
0x180005cb8  mov     ecx, r15d; Flags
0x180005cbb  call    cs:__imp_RtlDuplicateUnicodeString
0x180005cc2  nop     dword ptr [rax+rax+00h]
0x180005cc7  mov     esi, eax
0x180005cc9  test    eax, eax
0x180005ccb  jns     short loc_180005D02
0x180005ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cd4  cmp     rcx, r14
0x180005cd7  jz      short loc_180005CF6
0x180005cd9  test    byte ptr [rcx+1Ch], 1
0x180005cdd  jz      short loc_180005CF6
0x180005cdf  lea     edx, [r15+0Ah]
0x180005ce3  mov     r9d, eax
0x180005ce6  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005ced  mov     rcx, [rcx+10h]
0x180005cf1  call    WPP_SF_D
0x180005cf6  lea     rbx, hMem
0x180005cfd  jmp     loc_180005DF5
0x180005d02  xorps   xmm0, xmm0
0x180005d05  movups  xmmword ptr [rsp+2B8h+var_278.Guid], xmm0
0x180005d0a  lea     rdx, [rsp+2B8h+var_278]
0x180005d0f  test    r13, r13
0x180005d12  cmovnz  rdx, r13; SourceString
0x180005d16  lea     r8, stru_18000B5F8; DestinationString
0x180005d1d  mov     ecx, r15d; Flags
0x180005d20  call    cs:__imp_RtlDuplicateUnicodeString
0x180005d27  nop     dword ptr [rax+rax+00h]
0x180005d2c  mov     esi, eax
0x180005d2e  test    eax, eax
0x180005d30  jns     short loc_180005D4B
0x180005d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d39  cmp     rcx, r14
0x180005d3c  jz      short loc_180005CF6
0x180005d3e  test    byte ptr [rcx+1Ch], 1
0x180005d42  jz      short loc_180005CF6
0x180005d44  mov     edx, 0Eh
0x180005d49  jmp     short loc_180005CE3
0x180005d4b  movups  xmm0, xmmword ptr [rbx]
0x180005d4e  movaps  cs:xmmword_18000B580, xmm0
0x180005d55  movups  xmm1, xmmword ptr [rbx+10h]
0x180005d59  movaps  cs:xmmword_18000B590, xmm1
0x180005d60  movups  xmm0, xmmword ptr [rbx+20h]
0x180005d64  movaps  cs:xmmword_18000B5A0, xmm0
0x180005d6b  movups  xmm1, xmmword ptr [rbx+30h]
0x180005d6f  movaps  cs:xmmword_18000B5B0, xmm1
0x180005d76  movups  xmm0, xmmword ptr [rbx+40h]
0x180005d7a  movaps  cs:xmmword_18000B5C0, xmm0
0x180005d81  movsd   xmm1, qword ptr [rbx+50h]
0x180005d86  movsd   cs:qword_18000B5D0, xmm1
0x180005d8e  lea     rbx, hMem
0x180005d95  mov     cs:qword_18000B5E0, rbx
0x180005d9c  mov     cs:hMem, rbx
0x180005da3  mov     cs:dword_18000B678, 1
0x180005dad  mov     cs:dword_18000B67C, 1
0x180005db7  jmp     short loc_180005DF5
0x180005db9  mov     esi, 0C0000017h
0x180005dbe  lea     rax, WPP_GLOBAL_Control
0x180005dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dcc  cmp     rcx, rax
0x180005dcf  jz      short loc_180005DEC
0x180005dd1  test    byte ptr [rcx+1Ch], 1
0x180005dd5  jz      short loc_180005DEC
0x180005dd7  mov     edx, 0Ch
0x180005ddc  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005de3  mov     rcx, [rcx+10h]
0x180005de7  call    WPP_SF_
0x180005dec  xor     edi, edi
0x180005dee  lea     rbx, hMem
0x180005df5  cmp     cs:dword_18000B67C, edi
0x180005dfb  jnz     short loc_180005E39
0x180005dfd  lea     rcx, SourceString; UnicodeString
0x180005e04  call    cs:__imp_RtlFreeUnicodeString
0x180005e0b  nop     dword ptr [rax+rax+00h]
0x180005e10  lea     rcx, stru_18000B5F8; UnicodeString
0x180005e17  call    cs:__imp_RtlFreeUnicodeString
0x180005e1e  nop     dword ptr [rax+rax+00h]
0x180005e23  mov     eax, 10h
0x180005e28  mov     [rbx], dil
0x180005e2b  inc     rbx
0x180005e2e  sub     rax, 1
0x180005e32  jnz     short loc_180005E28
0x180005e34  call    WppCleanupUm
0x180005e39  mov     eax, esi
0x180005e3b  mov     rcx, [rsp+2B8h+var_38]
0x180005e43  xor     rcx, rsp; StackCookie
0x180005e46  call    __security_check_cookie
0x180005e4b  lea     r11, [rsp+2B8h+var_28]
0x180005e53  mov     rbx, [r11+30h]
0x180005e57  mov     rsi, [r11+48h]
0x180005e5b  mov     rsp, r11
0x180005e5e  pop     r15
0x180005e60  pop     r14
0x180005e62  pop     r13
0x180005e64  pop     r12
0x180005e66  pop     rdi
0x180005e67  retn
```
