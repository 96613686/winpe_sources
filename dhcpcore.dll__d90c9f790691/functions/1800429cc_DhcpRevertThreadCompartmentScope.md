# DhcpRevertThreadCompartmentScope

- ea: `0x1800429cc`
- end: `0x180042a6c`
- name: `DhcpRevertThreadCompartmentScope`
- size: `160`
- prototype: `void __fastcall(NET_IF_COMPARTMENT_SCOPE CompartmentScope)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800147e4`
- `0x180018aa0`
- `0x180023928`

## callees

- `0x1800429cc`
- `0x18004b4bc`
- `0x18004dd28`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x1800429f0`
- `IPHLPAPI!GetCurrentThreadCompartmentScope` at `0x1800429f0`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x180042a24`
- `IPHLPAPI!SetCurrentThreadCompartmentScope` at `0x180042a24`

## pseudocode

```c
void __fastcall DhcpRevertThreadCompartmentScope(NET_IF_COMPARTMENT_SCOPE CompartmentScope)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  UINT32 v4; // [rsp+40h] [rbp+8h] BYREF
  UINT32 v5; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  v4 = 0;
  GetCurrentThreadCompartmentScope(&v4, &v5);
  if ( CompartmentScope != v4 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_Dd(1028, 16, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids, v4, CompartmentScope);
    v2 = SetCurrentThreadCompartmentScope(CompartmentScope);
    v3 = v2;
    if ( v2 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_ddD(1025, 17, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids, v4, CompartmentScope, v2);
      __fastfail(v3);
    }
  }
}

```

## disassembly

```asm
0x1800429cc  mov     rax, rsp
0x1800429cf  mov     [rax+18h], rbx
0x1800429d3  push    rdi
0x1800429d4  sub     rsp, 30h
0x1800429d8  mov     edi, ecx
0x1800429da  mov     dword ptr [rax+10h], 0
0x1800429e1  lea     rcx, [rax+8]; CompartmentScope
0x1800429e5  mov     dword ptr [rax+8], 0
0x1800429ec  lea     rdx, [rax+10h]; CompartmentId
0x1800429f0  call    cs:__imp_GetCurrentThreadCompartmentScope
0x1800429f6  mov     r9d, [rsp+38h+arg_0]
0x1800429fb  cmp     edi, r9d
0x1800429fe  jz      short loc_180042A61
0x180042a00  mov     edx, 10h
0x180042a05  test    byte ptr cs:xmmword_1800616A0, dl
0x180042a0b  jz      short loc_180042A22
0x180042a0d  mov     ecx, 404h
0x180042a12  mov     [rsp+38h+var_18], edi
0x180042a16  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x180042a1d  call    WPP_SF_Dd
0x180042a22  mov     ecx, edi; CompartmentScope
0x180042a24  call    cs:__imp_SetCurrentThreadCompartmentScope
0x180042a2a  mov     ebx, eax
0x180042a2c  test    eax, eax
0x180042a2e  jz      short loc_180042A61
0x180042a30  test    byte ptr cs:xmmword_1800616A0, 2
0x180042a37  jz      short loc_180042A5C
0x180042a39  mov     r9d, [rsp+38h+arg_0]
0x180042a3e  lea     r8, WPP_7a9c28c0d9d83b6f632816efa12309d5_Traceguids
0x180042a45  mov     edx, 11h
0x180042a4a  mov     [rsp+38h+var_10], ebx
0x180042a4e  mov     ecx, 401h
0x180042a53  mov     [rsp+38h+var_18], edi
0x180042a57  call    WPP_SF_ddD
0x180042a5c  mov     rcx, rbx
0x180042a5f  int     29h; Win8: RtlFailFast(ecx)
0x180042a61  mov     rbx, [rsp+38h+arg_10]
0x180042a66  add     rsp, 30h
0x180042a6a  pop     rdi
0x180042a6b  retn
```
