# GMSARefreshPasswords

- ea: `0x180005e70`
- end: `0x18000607d`
- name: `GMSARefreshPasswords`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800036c0`
- `0x180005e70`
- `0x180006280`
- `0x1800063cc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005f18`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005fdc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005f18`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005fdc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005f04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005fc8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005f04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005fc8`
- `ntdll!RtlAcquireResourceShared` at `0x180005ec5`
- `ntdll!RtlAcquireResourceShared` at `0x180005ec5`
- `ntdll!RtlReleaseResource` at `0x18000602b`
- `ntdll!RtlReleaseResource` at `0x18000602b`

## pseudocode

```c
void __fastcall GMSARefreshPasswords(unsigned int *a1)
{
  unsigned int *v1; // r14
  unsigned int v2; // ebx
  HLOCAL *v3; // rdi
  _QWORD *v4; // rsi
  unsigned __int64 v5; // rdx
  int GroupMSAPassword; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+10h] BYREF

  v1 = a1;
  v2 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  RtlAcquireResourceShared(&Resource, 1u);
  v3 = (HLOCAL *)hMem;
  if ( hMem != &hMem )
  {
    do
    {
      SystemTimeAsFileTime = 0;
      v4 = v3 + 6;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime((const FILETIME *)v3 + 6, &SystemTimeAsFileTime) <= 0
        || (v5 = (*v4 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL, !(_DWORD)v5) )
      {
        GroupMSAPassword = GmsapGetGroupMSAPassword(0, (struct _tagGMsaListEntry *)v3, 0, 0, 0, 0, 0, 0, 0);
        if ( GroupMSAPassword < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
            (unsigned int)v3[3],
            (__int64)v3[2],
            GroupMSAPassword);
        }
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( CompareFileTime((const FILETIME *)v3 + 6, &SystemTimeAsFileTime) <= 0
          || (v5 = (*v4 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL, !(_DWORD)v5) )
        {
          LODWORD(v5) = -1;
        }
      }
      v3 = (HLOCAL *)*v3;
      if ( v2 < (unsigned int)v5 )
        LODWORD(v5) = v2;
      v2 = v5;
    }
    while ( v3 != &hMem );
    v1 = a1;
  }
  RtlReleaseResource(&Resource);
  if ( v1 )
    *v1 = v2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
}

```

## disassembly

```asm
0x180005e70  mov     [rsp+arg_10], rbx
0x180005e75  mov     [rsp+arg_18], rsi
0x180005e7a  mov     [rsp+arg_0], rcx
0x180005e7f  push    rdi
0x180005e80  push    r14
0x180005e82  push    r15
0x180005e84  sub     rsp, 50h
0x180005e88  mov     r14, rcx
0x180005e8b  or      ebx, 0FFFFFFFFh
0x180005e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e95  lea     r15, WPP_GLOBAL_Control
0x180005e9c  cmp     rcx, r15
0x180005e9f  jz      short loc_180005EBC
0x180005ea1  test    byte ptr [rcx+1Ch], 8
0x180005ea5  jz      short loc_180005EBC
0x180005ea7  mov     rcx, [rcx+10h]
0x180005eab  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005eb2  mov     edx, 10h
0x180005eb7  call    WPP_SF_
0x180005ebc  mov     dl, 1; Wait
0x180005ebe  lea     rcx, Resource; Resource
0x180005ec5  call    cs:__imp_RtlAcquireResourceShared
0x180005ecc  nop     dword ptr [rax+rax+00h]
0x180005ed1  mov     rdi, cs:hMem
0x180005ed8  lea     rax, hMem
0x180005edf  cmp     rdi, rax
0x180005ee2  jz      loc_180006024
0x180005ee8  mov     r14, 346DC5D63886594Bh
0x180005ef2  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005ef7  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005f00  lea     rsi, [rdi+30h]
0x180005f04  call    cs:__imp_GetSystemTimeAsFileTime
0x180005f0b  nop     dword ptr [rax+rax+00h]
0x180005f10  lea     rdx, [rsp+68h+SystemTimeAsFileTime]; lpFileTime2
0x180005f15  mov     rcx, rsi; lpFileTime1
0x180005f18  call    cs:__imp_CompareFileTime
0x180005f1f  nop     dword ptr [rax+rax+00h]
0x180005f24  test    eax, eax
0x180005f26  jle     short loc_180005F42
0x180005f28  mov     rcx, [rsi]
0x180005f2b  mov     rax, r14
0x180005f2e  sub     rcx, qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime]
0x180005f33  mul     rcx
0x180005f36  shr     rdx, 0Bh
0x180005f3a  test    edx, edx
0x180005f3c  jnz     loc_180006005
0x180005f42  mov     [rsp+68h+var_28], 0
0x180005f4b  xor     r9d, r9d
0x180005f4e  mov     [rsp+68h+var_30], 0
0x180005f57  xor     r8d, r8d
0x180005f5a  mov     [rsp+68h+var_38], 0
0x180005f63  mov     rdx, rdi
0x180005f66  mov     [rsp+68h+var_40], 0
0x180005f6f  xor     ecx, ecx
0x180005f71  mov     dword ptr [rsp+68h+var_48], 0
0x180005f79  call    GmsapGetGroupMSAPassword
0x180005f7e  test    eax, eax
0x180005f80  jns     short loc_180005FBA
0x180005f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f89  cmp     rcx, r15
0x180005f8c  jz      short loc_180005FBA
0x180005f8e  test    byte ptr [rcx+1Ch], 4
0x180005f92  jz      short loc_180005FBA
0x180005f94  mov     r9, [rdi+18h]
0x180005f98  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180005f9f  mov     rcx, [rcx+10h]
0x180005fa3  mov     edx, 11h
0x180005fa8  mov     dword ptr [rsp+68h+var_40], eax
0x180005fac  mov     rax, [rdi+10h]
0x180005fb0  mov     [rsp+68h+var_48], rax
0x180005fb5  call    WPP_SF_SSD
0x180005fba  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005fbf  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005fc8  call    cs:__imp_GetSystemTimeAsFileTime
0x180005fcf  nop     dword ptr [rax+rax+00h]
0x180005fd4  lea     rdx, [rsp+68h+SystemTimeAsFileTime]; lpFileTime2
0x180005fd9  mov     rcx, rsi; lpFileTime1
0x180005fdc  call    cs:__imp_CompareFileTime
0x180005fe3  nop     dword ptr [rax+rax+00h]
0x180005fe8  test    eax, eax
0x180005fea  jle     short loc_180006002
0x180005fec  mov     rcx, [rsi]
0x180005fef  mov     rax, r14
0x180005ff2  sub     rcx, qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime]
0x180005ff7  mul     rcx
0x180005ffa  shr     rdx, 0Bh
0x180005ffe  test    edx, edx
0x180006000  jnz     short loc_180006005
0x180006002  or      edx, 0FFFFFFFFh
0x180006005  mov     rdi, [rdi]
0x180006008  lea     rax, hMem
0x18000600f  cmp     ebx, edx
0x180006011  cmovb   edx, ebx
0x180006014  mov     ebx, edx
0x180006016  cmp     rdi, rax
0x180006019  jnz     loc_180005EF2
0x18000601f  mov     r14, [rsp+68h+arg_0]
0x180006024  lea     rcx, Resource; Resource
0x18000602b  call    cs:__imp_RtlReleaseResource
0x180006032  nop     dword ptr [rax+rax+00h]
0x180006037  test    r14, r14
0x18000603a  jz      short loc_18000603F
0x18000603c  mov     [r14], ebx
0x18000603f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006046  cmp     rcx, r15
0x180006049  jz      short loc_180006066
0x18000604b  test    byte ptr [rcx+1Ch], 8
0x18000604f  jz      short loc_180006066
0x180006051  mov     rcx, [rcx+10h]
0x180006055  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000605c  mov     edx, 12h
0x180006061  call    WPP_SF_
0x180006066  lea     r11, [rsp+68h+var_18]
0x18000606b  mov     rbx, [r11+30h]
0x18000606f  mov     rsi, [r11+38h]
0x180006073  mov     rsp, r11
0x180006076  pop     r15
0x180006078  pop     r14
0x18000607a  pop     rdi
0x18000607b  retn
```
