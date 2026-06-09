# ServiceModule::DwHandler(ulong,ulong,void const *,void const *)

- ea: `0x18000f21c`
- end: `0x18000f605`
- name: `?DwHandler@ServiceModule@@QEAAKKKPEBX0@Z`
- size: `1001`
- prototype: `unsigned int __fastcall(ServiceModule *__hidden this, unsigned int, unsigned int, const void *, const void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800189d0`

## callees

- `0x180001710`
- `0x180002320`
- `0x180004c00`
- `0x1800052b4`
- `0x18000f21c`
- `0x1800171b8`
- `0x180018ac4`
- `0x180019200`
- `0x180019228`
- `0x180019c68`
- `0x18001f920`
- `0x18001fe84`
- `0x180020224`
- `0x18003060c`
- `0x180034dfc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f4c9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f4c9`
- `KERNEL32!GetLastError` at `0x18000f2ed`
- `KERNEL32!GetLastError` at `0x18000f2ed`
- `KERNEL32!SetEvent` at `0x18000f2a3`
- `KERNEL32!SetEvent` at `0x18000f2a3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000f4f0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000f4f0`

## pseudocode

```c
DWORD __fastcall ServiceModule::DwHandler(ServiceModule *this, __int64 a2, int a3, const wchar_t *a4)
{
  int v6; // esi
  ServiceModule *v7; // rcx
  ServiceModule *v8; // rcx
  int Win32Error; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  ServiceModule *v12; // rcx
  GUID *v13; // rax
  GUID *v14; // rbx
  GUID v15; // xmm0
  unsigned int (*v16)(struct NMEVENT_HEADER *); // rcx
  wchar_t *v17; // rax
  GUID *v18; // rax
  GUID *v19; // rax
  GUID iid; // [rsp+30h] [rbp-238h] BYREF
  OLECHAR sz[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( ServiceStatus.dwCurrentState == 3 )
    return 1061;
  v6 = 0;
  if ( (_DWORD)a2 != 1 )
  {
    if ( (_DWORD)a2 == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
      return v6;
    }
    if ( (_DWORD)a2 == 14 )
    {
      if ( (unsigned int)(a3 - 5) <= 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
        v13 = (GUID *)MemAlloc(0xE68u);
        v14 = v13;
        if ( !v13 )
          return v6;
        memset_0(v13, 0, 0xE68u);
        v15 = GUID_NULL;
        *(_DWORD *)&v14->Data2 = 3;
        v16 = (unsigned int (*)(struct NMEVENT_HEADER *))ConmanEventWorkItem;
        goto LABEL_28;
      }
      return 120;
    }
    if ( (_DWORD)a2 != 11 || !a4 )
      return 120;
    if ( *((_DWORD *)a4 + 1) == 5 )
    {
      if ( a3 == 0x8000 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, a4 + 14);
LABEL_56:
        LanEventNotify(7, 0);
        return v6;
      }
      if ( a3 == 32772 )
      {
        iid = GUID_NULL;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids, a4 + 14);
        v17 = wcsrchr(a4 + 14, 0x7Bu);
        if ( v17 )
        {
          StringCchCopyW(sz, 0x104u, v17);
          IIDFromString(sz, &iid);
        }
        if ( !memcmp_0(&iid, &GUID_NULL, 0x10u) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
          goto LABEL_56;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetImpl'::`2'::impl) )
        {
          v18 = (GUID *)MemAlloc(0xE68u);
          v14 = v18;
          if ( v18 )
          {
            memset_0(v18, 0, 0xE68u);
LABEL_52:
            *(_DWORD *)v14->Data4 = 2;
            v16 = (unsigned int (*)(struct NMEVENT_HEADER *))LanEventWorkItem;
            v15 = iid;
            *(_DWORD *)&v14->Data2 = 6;
            v14[2].Data1 = 0;
LABEL_28:
            v14->Data1 = 1;
            v14[1] = v15;
            if ( !(unsigned int)QueueUserWorkItemInThread(v16, (struct NMEVENT_HEADER *)v14) )
              FreeConmanEvent((struct CONMAN_EVENT *)v14);
          }
        }
        else
        {
          v19 = (GUID *)MemAlloc(0xE68u);
          v14 = v19;
          if ( v19 )
          {
            *(_QWORD *)&v19->Data1 = 0;
            goto LABEL_52;
          }
        }
      }
    }
    return v6;
  }
  v7 = (ServiceModule *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
  ServiceModule::SetServiceStatus(v7, 3u);
  if ( !hObject )
  {
    v12 = (ServiceModule *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids);
    ServiceModule::SetServiceStatus(v12, 4u);
    return 1061;
  }
  if ( SetEvent(hObject) )
    return v6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    Win32Error = HrFromLastWin32Error();
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, hObject, Win32Error);
  }
  ServiceModule::SetServiceStatus(v8, 4u);
  return GetLastError();
}

```

## disassembly

```asm
0x18000f21c  mov     [rsp+arg_0], rbx
0x18000f221  mov     [rsp+arg_8], rsi
0x18000f226  push    rdi
0x18000f227  sub     rsp, 260h
0x18000f22e  mov     rax, cs:__security_cookie
0x18000f235  xor     rax, rsp
0x18000f238  mov     [rsp+268h+var_18], rax
0x18000f240  cmp     cs:ServiceStatus.dwCurrentState, 3
0x18000f247  mov     rdi, r9
0x18000f24a  jnz     short loc_18000F256
0x18000f24c  mov     eax, 425h
0x18000f251  jmp     loc_18000F5E0
0x18000f256  xor     esi, esi
0x18000f258  cmp     edx, 1
0x18000f25b  jnz     loc_18000F32E
0x18000f261  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f268  lea     rbx, WPP_GLOBAL_Control
0x18000f26f  cmp     rcx, rbx
0x18000f272  jz      short loc_18000F28D
0x18000f274  test    byte ptr [rcx+1Ch], 8
0x18000f278  jz      short loc_18000F28D
0x18000f27a  mov     rcx, [rcx+10h]
0x18000f27e  lea     edx, [rsi+0Ah]
0x18000f281  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f288  call    WPP_SF_
0x18000f28d  mov     edx, 3; unsigned int
0x18000f292  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x18000f297  mov     rcx, cs:hObject; hEvent
0x18000f29e  test    rcx, rcx
0x18000f2a1  jz      short loc_18000F2F8
0x18000f2a3  call    cs:__imp_SetEvent
0x18000f2a9  test    eax, eax
0x18000f2ab  jnz     loc_18000F5DE
0x18000f2b1  mov     rax, cs:WPP_GLOBAL_Control
0x18000f2b8  cmp     rax, rbx
0x18000f2bb  jz      short loc_18000F2E3
0x18000f2bd  test    byte ptr [rax+1Ch], 8
0x18000f2c1  jz      short loc_18000F2E3
0x18000f2c3  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000f2c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2cf  mov     r9, cs:hObject
0x18000f2d6  mov     [rsp+268h+var_248], eax
0x18000f2da  mov     rcx, [rcx+10h]
0x18000f2de  call    WPP_SF_qd
0x18000f2e3  mov     edx, 4; unsigned int
0x18000f2e8  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x18000f2ed  call    cs:__imp_GetLastError
0x18000f2f3  jmp     loc_18000F5E0
0x18000f2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2ff  cmp     rcx, rbx
0x18000f302  jz      short loc_18000F31F
0x18000f304  test    byte ptr [rcx+1Ch], 8
0x18000f308  jz      short loc_18000F31F
0x18000f30a  mov     rcx, [rcx+10h]
0x18000f30e  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f315  mov     edx, 0Ch
0x18000f31a  call    WPP_SF_
0x18000f31f  mov     edx, 4; unsigned int
0x18000f324  call    ?SetServiceStatus@ServiceModule@@QEAAXK@Z; ServiceModule::SetServiceStatus(ulong)
0x18000f329  jmp     loc_18000F24C
0x18000f32e  cmp     edx, 4
0x18000f331  jnz     short loc_18000F36E
0x18000f333  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f33a  lea     rbx, WPP_GLOBAL_Control
0x18000f341  cmp     rcx, rbx
0x18000f344  jz      loc_18000F5DE
0x18000f34a  test    byte ptr [rcx+1Ch], 8
0x18000f34e  jz      loc_18000F5DE
0x18000f354  mov     rcx, [rcx+10h]
0x18000f358  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f35f  mov     edx, 0Dh
0x18000f364  call    WPP_SF_
0x18000f369  jmp     loc_18000F5DE
0x18000f36e  cmp     edx, 0Eh
0x18000f371  jnz     loc_18000F40F
0x18000f377  lea     eax, [r8-5]
0x18000f37b  cmp     eax, 1
0x18000f37e  ja      loc_18000F5D9
0x18000f384  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f38b  lea     rbx, WPP_GLOBAL_Control
0x18000f392  cmp     rcx, rbx
0x18000f395  jz      short loc_18000F3AD
0x18000f397  test    byte ptr [rcx+1Ch], 8
0x18000f39b  jz      short loc_18000F3AD
0x18000f39d  mov     rcx, [rcx+10h]
0x18000f3a1  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f3a8  call    WPP_SF_
0x18000f3ad  mov     edi, 0E68h
0x18000f3b2  mov     ecx, edi; unsigned __int64
0x18000f3b4  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000f3b9  mov     rbx, rax
0x18000f3bc  test    rax, rax
0x18000f3bf  jz      loc_18000F5DE
0x18000f3c5  mov     r8d, edi; Size
0x18000f3c8  xor     edx, edx; Val
0x18000f3ca  mov     rcx, rax; void *
0x18000f3cd  call    memset_0
0x18000f3d2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f3d9  mov     dword ptr [rbx+4], 3
0x18000f3e0  lea     rcx, ?ConmanEventWorkItem@@YAKPEAUNMEVENT_HEADER@@@Z; unsigned int (*)(struct NMEVENT_HEADER *)
0x18000f3e7  mov     dword ptr [rbx], 1
0x18000f3ed  mov     rdx, rbx; struct NMEVENT_HEADER *
0x18000f3f0  movdqu  xmmword ptr [rbx+10h], xmm0
0x18000f3f5  call    ?QueueUserWorkItemInThread@@YAHP6AKPEAUNMEVENT_HEADER@@@Z0@Z; QueueUserWorkItemInThread(ulong (*)(NMEVENT_HEADER *),NMEVENT_HEADER *)
0x18000f3fa  test    eax, eax
0x18000f3fc  jnz     loc_18000F5DE
0x18000f402  mov     rcx, rbx; lpMem
0x18000f405  call    ?FreeConmanEvent@@YAXPEAUCONMAN_EVENT@@@Z; FreeConmanEvent(CONMAN_EVENT *)
0x18000f40a  jmp     loc_18000F5DE
0x18000f40f  cmp     edx, 0Bh
0x18000f412  jnz     loc_18000F5D9
0x18000f418  test    rdi, rdi
0x18000f41b  jz      loc_18000F5D9
0x18000f421  cmp     dword ptr [r9+4], 5
0x18000f426  jnz     loc_18000F5DE
0x18000f42c  cmp     r8d, 8000h
0x18000f433  jnz     short loc_18000F474
0x18000f435  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f43c  lea     rbx, WPP_GLOBAL_Control
0x18000f443  cmp     rcx, rbx
0x18000f446  jz      loc_18000F5CD
0x18000f44c  test    byte ptr [rcx+1Ch], 8
0x18000f450  jz      loc_18000F5CD
0x18000f456  mov     rcx, [rcx+10h]
0x18000f45a  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f461  add     r9, 1Ch
0x18000f465  mov     edx, 0Fh
0x18000f46a  call    WPP_SF_S
0x18000f46f  jmp     loc_18000F5CD
0x18000f474  cmp     r8d, 8004h
0x18000f47b  jnz     loc_18000F5DE
0x18000f481  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000f488  movdqu  xmmword ptr [rsp+268h+iid.Data1], xmm0
0x18000f48e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f495  lea     rbx, WPP_GLOBAL_Control
0x18000f49c  cmp     rcx, rbx
0x18000f49f  jz      short loc_18000F4C0
0x18000f4a1  test    byte ptr [rcx+1Ch], 8
0x18000f4a5  jz      short loc_18000F4C0
0x18000f4a7  mov     rcx, [rcx+10h]
0x18000f4ab  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f4b2  add     r9, 1Ch
0x18000f4b6  mov     edx, 10h
0x18000f4bb  call    WPP_SF_S
0x18000f4c0  mov     edx, 7Bh ; '{'; Ch
0x18000f4c5  lea     rcx, [rdi+1Ch]; Str
0x18000f4c9  call    cs:__imp_wcsrchr
0x18000f4cf  test    rax, rax
0x18000f4d2  jz      short loc_18000F4F6
0x18000f4d4  mov     r8, rax; unsigned __int16 *
0x18000f4d7  lea     rcx, [rsp+268h+sz]; unsigned __int16 *
0x18000f4dc  mov     edx, 104h; unsigned __int64
0x18000f4e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f4e6  lea     rdx, [rsp+268h+iid]; lpiid
0x18000f4eb  lea     rcx, [rsp+268h+sz]; lpsz
0x18000f4f0  call    cs:__imp_IIDFromString
0x18000f4f6  mov     r8d, 10h; Size
0x18000f4fc  lea     rdx, GUID_NULL; Buf2
0x18000f503  lea     rcx, [rsp+268h+iid]; Buf1
0x18000f508  call    memcmp_0
0x18000f50d  test    eax, eax
0x18000f50f  jz      loc_18000F5A6
0x18000f515  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f51c  cmp     rcx, rbx
0x18000f51f  jz      short loc_18000F53C
0x18000f521  test    byte ptr [rcx+1Ch], 8
0x18000f525  jz      short loc_18000F53C
0x18000f527  mov     rcx, [rcx+10h]
0x18000f52b  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f532  mov     edx, 11h
0x18000f537  call    WPP_SF_
0x18000f53c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety> `wil::Feature<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetImpl(void)'::`2'::impl
0x18000f543  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::__private_IsEnabled(void)
0x18000f548  test    al, al
0x18000f54a  jz      short loc_18000F56F
0x18000f54c  mov     edi, 0E68h
0x18000f551  mov     ecx, edi; unsigned __int64
0x18000f553  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000f558  mov     rbx, rax
0x18000f55b  test    rax, rax
0x18000f55e  jz      short loc_18000F5DE
0x18000f560  mov     r8d, edi; Size
0x18000f563  xor     edx, edx; Val
0x18000f565  mov     rcx, rax; void *
0x18000f568  call    memset_0
0x18000f56d  jmp     short loc_18000F584
0x18000f56f  mov     ecx, 0E68h; unsigned __int64
0x18000f574  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18000f579  mov     rbx, rax
0x18000f57c  test    rax, rax
0x18000f57f  jz      short loc_18000F5DE
0x18000f581  mov     [rax], rsi
0x18000f584  mov     dword ptr [rbx+8], 2
0x18000f58b  lea     rcx, ?LanEventWorkItem@@YAKPEAUNMEVENT_HEADER@@@Z; LanEventWorkItem(NMEVENT_HEADER *)
0x18000f592  movups  xmm0, xmmword ptr [rsp+268h+iid.Data1]
0x18000f597  mov     dword ptr [rbx+4], 6
0x18000f59e  mov     [rbx+20h], esi
0x18000f5a1  jmp     loc_18000F3E7
0x18000f5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5ad  cmp     rcx, rbx
0x18000f5b0  jz      short loc_18000F5CD
0x18000f5b2  test    byte ptr [rcx+1Ch], 8
0x18000f5b6  jz      short loc_18000F5CD
0x18000f5b8  mov     rcx, [rcx+10h]
0x18000f5bc  lea     r8, WPP_b4d1654223233927dad0a39c06a0afa5_Traceguids
0x18000f5c3  mov     edx, 12h
0x18000f5c8  call    WPP_SF_
0x18000f5cd  xor     edx, edx
0x18000f5cf  lea     ecx, [rdx+7]
0x18000f5d2  call    ?LanEventNotify@@YAXW4CONMAN_EVENTTYPE@@PEAUINetConnection@@PEBGPEBU_GUID@@@Z; LanEventNotify(CONMAN_EVENTTYPE,INetConnection *,ushort const *,_GUID const *)
0x18000f5d7  jmp     short loc_18000F5DE
0x18000f5d9  mov     esi, 78h ; 'x'
0x18000f5de  mov     eax, esi
0x18000f5e0  mov     rcx, [rsp+268h+var_18]
0x18000f5e8  xor     rcx, rsp; StackCookie
0x18000f5eb  call    __security_check_cookie
0x18000f5f0  lea     r11, [rsp+268h+var_8]
0x18000f5f8  mov     rbx, [r11+10h]
0x18000f5fc  mov     rsi, [r11+18h]
0x18000f600  mov     rsp, r11
0x18000f603  pop     rdi
0x18000f604  retn
```
