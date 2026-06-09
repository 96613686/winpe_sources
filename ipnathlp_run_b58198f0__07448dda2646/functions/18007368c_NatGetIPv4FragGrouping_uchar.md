# NatGetIPv4FragGrouping(uchar *)

- ea: `0x18007368c`
- end: `0x180073990`
- name: `?NatGetIPv4FragGrouping@@YAEPEAE@Z`
- size: `772`
- prototype: `unsigned __int8 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180075f14`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18004561c`
- `0x180051f30`
- `0x180052bf4`
- `0x18007368c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800738e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800738e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073880`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073880`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800738fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800738fc`
- `NSI!NsiGetAllParameters` at `0x180073806`
- `NSI!NsiGetAllParameters` at `0x180073806`

## string_xrefs

- `0x1800736f0`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
bool __fastcall NatGetIPv4FragGrouping(unsigned __int8 *a1)
{
  bool v1; // bl
  unsigned int AllParameters; // eax
  __int64 v3; // r9
  PVOID *v4; // rcx
  unsigned int v5; // edi
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v10[160]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR SubKey[64]; // [rsp+160h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 292, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  wcscpy(ValueName, L"EnableIPv4GroupForwardedFragments");
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  memset_0(v10, 0, 0x9Cu);
  v1 = 1;
  AllParameters = NsiGetAllParameters(1, &NPI_MS_IPV4_MODULEID, 6);
  if ( AllParameters )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        293,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        AllParameters);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v1 = 0;
    goto LABEL_24;
  }
  GroupForwardedFragmentsOld = v10[112];
  if ( GroupForwardedFragmentsEnabled )
    goto LABEL_23;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    v5 = RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData);
    RegCloseKey(hKey);
    if ( v5 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v1;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5);
    }
    else
    {
      v1 = *(_DWORD *)Data != 0;
    }
    goto LABEL_23;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
LABEL_23:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    LOBYTE(v3) = v1;
    WPP_SF_c(v4[2], 296, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18007368c  push    rbp
0x18007368e  push    rbx
0x18007368f  push    rsi
0x180073690  push    rdi
0x180073691  push    r14
0x180073693  push    r15
0x180073695  lea     rbp, [rsp-0F8h]
0x18007369d  sub     rsp, 1F8h
0x1800736a4  mov     rax, cs:__security_cookie
0x1800736ab  xor     rax, rsp
0x1800736ae  mov     [rbp+120h+var_40], rax
0x1800736b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800736bc  lea     r14, WPP_GLOBAL_Control
0x1800736c3  lea     r15, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800736ca  mov     esi, 200h
0x1800736cf  cmp     rcx, r14
0x1800736d2  jz      short loc_1800736F0
0x1800736d4  test    [rcx+1Ch], esi
0x1800736d7  jz      short loc_1800736F0
0x1800736d9  cmp     byte ptr [rcx+19h], 6
0x1800736dd  jb      short loc_1800736F0
0x1800736df  mov     rcx, [rcx+10h]
0x1800736e3  mov     edx, 124h
0x1800736e8  mov     r8, r15
0x1800736eb  call    WPP_SF_
0x1800736f0  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x1800736f7  lea     rcx, [rsp+220h+var_1B0]; void *
0x1800736fc  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180073703  mov     ebx, 9Ch
0x180073708  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18007370e  mov     r8d, ebx; Size
0x180073711  movaps  xmmword ptr [rbp+120h+SubKey], xmm0
0x180073715  xor     edx, edx; Val
0x180073717  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18007371e  movaps  [rbp+120h+var_A0], xmm0
0x180073725  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18007372c  movaps  [rbp+120h+var_B0], xmm1
0x180073730  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180073737  movaps  [rbp+120h+var_80], xmm0
0x18007373e  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180073745  movaps  [rbp+120h+var_90], xmm1
0x18007374c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180073753  movaps  [rbp+120h+var_60], xmm0
0x18007375a  movaps  xmm0, xmmword ptr cs:aEnableipv4grou; "EnableIPv4GroupForwardedFragments"
0x180073761  movaps  [rbp+120h+var_70], xmm1
0x180073768  movaps  xmm1, xmmword ptr cs:aEnableipv4grou+10h; "v4GroupForwardedFragments"
0x18007376f  movaps  xmmword ptr [rbp+120h+ValueName], xmm0
0x180073773  movaps  xmm0, xmmword ptr cs:aEnableipv4grou+20h; "orwardedFragments"
0x18007377a  movaps  [rbp+120h+var_100], xmm1
0x18007377e  movaps  xmm1, xmmword ptr cs:aEnableipv4grou+30h; "Fragments"
0x180073785  mov     [rbp+120h+var_50], eax
0x18007378b  mov     eax, dword ptr cs:aEnableipv4grou+40h; "s"
0x180073791  movaps  [rbp+120h+var_F0], xmm0
0x180073795  movaps  [rbp+120h+var_E0], xmm1
0x180073799  mov     [rbp+120h+var_D0], eax
0x18007379c  mov     [rsp+220h+hKey], 0
0x1800737a5  mov     dword ptr [rsp+220h+Data], 0
0x1800737ad  mov     [rsp+220h+cbData], 4
0x1800737b5  call    memset_0
0x1800737ba  mov     [rsp+220h+var_1D0], 0
0x1800737c2  lea     rax, [rsp+220h+var_1B0]
0x1800737c7  mov     [rsp+220h+var_1D8], 0
0x1800737d0  lea     rdx, NPI_MS_IPV4_MODULEID
0x1800737d7  mov     [rsp+220h+var_1E0], 0
0x1800737df  xor     r9d, r9d
0x1800737e2  mov     [rsp+220h+var_1E8], 0
0x1800737eb  mov     [rsp+220h+var_1F0], ebx
0x1800737ef  mov     [rsp+220h+lpcbData], rax
0x1800737f4  lea     ebx, [r9+1]
0x1800737f8  mov     dword ptr [rsp+220h+phkResult], 0
0x180073800  mov     ecx, ebx
0x180073802  lea     r8d, [r9+6]
0x180073806  call    cs:__imp_NsiGetAllParameters
0x18007380d  nop     dword ptr [rax+rax+00h]
0x180073812  test    eax, eax
0x180073814  jz      short loc_18007384F
0x180073816  mov     rcx, cs:WPP_GLOBAL_Control
0x18007381d  cmp     rcx, r14
0x180073820  jz      short loc_180073848
0x180073822  test    [rcx+1Ch], esi
0x180073825  jz      short loc_180073848
0x180073827  cmp     byte ptr [rcx+19h], 2
0x18007382b  jb      short loc_180073848
0x18007382d  mov     rcx, [rcx+10h]
0x180073831  mov     edx, 125h
0x180073836  mov     r9d, eax
0x180073839  mov     r8, r15
0x18007383c  call    WPP_SF_d
0x180073841  mov     rcx, cs:WPP_GLOBAL_Control
0x180073848  xor     bl, bl
0x18007384a  jmp     loc_18007394A
0x18007384f  cmp     cs:?GroupForwardedFragmentsEnabled@@3EA, 0; uchar GroupForwardedFragmentsEnabled
0x180073856  mov     al, [rbp+120h+var_140]
0x180073859  mov     cs:?GroupForwardedFragmentsOld@@3EA, al; uchar GroupForwardedFragmentsOld
0x18007385f  jnz     loc_180073943
0x180073865  lea     rax, [rsp+220h+hKey]
0x18007386a  mov     r9d, ebx; samDesired
0x18007386d  xor     r8d, r8d; ulOptions
0x180073870  mov     [rsp+220h+phkResult], rax; phkResult
0x180073875  lea     rdx, [rbp+120h+SubKey]; lpSubKey
0x180073879  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073880  call    cs:__imp_RegOpenKeyExW
0x180073887  nop     dword ptr [rax+rax+00h]
0x18007388c  test    eax, eax
0x18007388e  jz      short loc_1800738C6
0x180073890  mov     rcx, cs:WPP_GLOBAL_Control
0x180073897  cmp     rcx, r14
0x18007389a  jz      loc_18007396E
0x1800738a0  test    [rcx+1Ch], esi
0x1800738a3  jz      loc_18007394A
0x1800738a9  cmp     byte ptr [rcx+19h], 2
0x1800738ad  jb      loc_18007394A
0x1800738b3  mov     rcx, [rcx+10h]
0x1800738b7  mov     edx, 126h
0x1800738bc  mov     r8, r15
0x1800738bf  call    WPP_SF_
0x1800738c4  jmp     short loc_180073943
0x1800738c6  mov     rcx, [rsp+220h+hKey]; hKey
0x1800738cb  lea     rax, [rsp+220h+cbData]
0x1800738d0  mov     [rsp+220h+lpcbData], rax; lpcbData
0x1800738d5  lea     rdx, [rbp+120h+ValueName]; lpValueName
0x1800738d9  lea     rax, [rsp+220h+Data]
0x1800738de  xor     r9d, r9d; lpType
0x1800738e1  xor     r8d, r8d; lpReserved
0x1800738e4  mov     [rsp+220h+phkResult], rax; lpData
0x1800738e9  call    cs:__imp_RegQueryValueExW
0x1800738f0  nop     dword ptr [rax+rax+00h]
0x1800738f5  mov     rcx, [rsp+220h+hKey]; hKey
0x1800738fa  mov     edi, eax
0x1800738fc  call    cs:__imp_RegCloseKey
0x180073903  nop     dword ptr [rax+rax+00h]
0x180073908  test    edi, edi
0x18007390a  jz      short loc_180073939
0x18007390c  mov     rcx, cs:WPP_GLOBAL_Control
0x180073913  cmp     rcx, r14
0x180073916  jz      short loc_18007396E
0x180073918  test    [rcx+1Ch], esi
0x18007391b  jz      short loc_18007394A
0x18007391d  cmp     byte ptr [rcx+19h], 2
0x180073921  jb      short loc_18007394A
0x180073923  mov     rcx, [rcx+10h]
0x180073927  mov     edx, 127h
0x18007392c  mov     r9d, edi
0x18007392f  mov     r8, r15
0x180073932  call    WPP_SF_d
0x180073937  jmp     short loc_180073943
0x180073939  mov     eax, dword ptr [rsp+220h+Data]
0x18007393d  neg     eax
0x18007393f  sbb     cl, cl
0x180073941  and     bl, cl
0x180073943  mov     rcx, cs:WPP_GLOBAL_Control
0x18007394a  cmp     rcx, r14
0x18007394d  jz      short loc_18007396E
0x18007394f  test    [rcx+1Ch], esi
0x180073952  jz      short loc_18007396E
0x180073954  cmp     byte ptr [rcx+19h], 6
0x180073958  jb      short loc_18007396E
0x18007395a  mov     rcx, [rcx+10h]
0x18007395e  mov     edx, 128h
0x180073963  mov     r9b, bl
0x180073966  mov     r8, r15
0x180073969  call    WPP_SF_c
0x18007396e  mov     al, bl
0x180073970  mov     rcx, [rbp+120h+var_40]
0x180073977  xor     rcx, rsp; StackCookie
0x18007397a  call    __security_check_cookie
0x18007397f  add     rsp, 1F8h
0x180073986  pop     r15
0x180073988  pop     r14
0x18007398a  pop     rdi
0x18007398b  pop     rsi
0x18007398c  pop     rbx
0x18007398d  pop     rbp
0x18007398e  retn
```
