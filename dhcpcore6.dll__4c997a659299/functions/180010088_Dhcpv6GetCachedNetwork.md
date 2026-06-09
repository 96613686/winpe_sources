# Dhcpv6GetCachedNetwork

- ea: `0x180010088`
- end: `0x180010337`
- name: `Dhcpv6GetCachedNetwork`
- size: `687`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010340`
- `0x180010d18`

## callees

- `0x18000bf10`
- `0x18000c740`
- `0x18000cabc`
- `0x18000f3a4`
- `0x180010088`
- `0x180011b98`
- `0x180011e04`
- `0x180013028`
- `0x180016440`
- `0x180019ad0`
- `0x1800338c0`
- `0x180033900`
- `0x180034458`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180010285`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180010285`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800100ec`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010111`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800100ec`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010111`

## pseudocode

```c
int __fastcall Dhcpv6GetCachedNetwork(__int64 a1, unsigned int a2)
{
  char *v4; // rdi
  const WCHAR *v5; // r8
  int result; // eax
  char *v7; // rdx
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // eax
  int v16; // [rsp+30h] [rbp-19h] BYREF
  LPVOID v17; // [rsp+38h] [rbp-11h] BYREF
  int v18; // [rsp+40h] [rbp-9h] BYREF
  const WCHAR *v19; // [rsp+48h] [rbp-1h] BYREF
  LARGE_INTEGER v20; // [rsp+50h] [rbp+7h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp+Fh] BYREF
  __int128 v22; // [rsp+60h] [rbp+17h] BYREF

  *(_QWORD *)(a1 + 8980) = 0;
  *(_DWORD *)(a1 + 8988) = 0;
  v19 = 0;
  v17 = 0;
  v16 = 0;
  PerformanceCount.QuadPart = 0;
  v20.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  GetNetworkHint(a1 + 24, &v19, &v16, &v17);
  QueryPerformanceCounter(&v20);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_ii(
      (unsigned __int64)(1000000000 * (v20.QuadPart - PerformanceCount.QuadPart))
    / Dhcpv6GlobalPerformanceFrequency.QuadPart,
      134,
      WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
  v4 = *(char **)(a1 + 8952);
  *(_DWORD *)(a1 + 8976) = 1;
  v5 = v19;
  if ( v19 )
  {
    if ( !v4 )
      goto LABEL_29;
    v7 = (char *)((char *)v19 - v4);
    do
    {
      v8 = *(unsigned __int16 *)&v7[(_QWORD)v4];
      v9 = *(unsigned __int16 *)v4 - v8;
      if ( v9 )
        break;
      v4 += 2;
    }
    while ( v8 );
    if ( !v9 && (unsigned int)Dhcpv6CompareMode(a2, *(unsigned int *)(a1 + 8944)) )
    {
      v18 = 0;
      v16 = 0;
      v22 = 0;
      v10 = IsDHCPV6AddrPlumbed(a1, &v22, &v18, &v16);
      v11 = g_fVelocityDhcpv6ContextBitfieldUpdate;
      v12 = v10;
      if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
      {
        v13 = *(_DWORD *)(a1 + 8880);
        v11 = g_fVelocityDhcpv6ContextBitfieldUpdate;
      }
      else
      {
        v13 = (*(_DWORD *)(a1 + 8860) >> 5) & 1;
      }
      if ( v13
        || (!v11 ? (v14 = (*(_DWORD *)(a1 + 8860) >> 5) & 1) : (v14 = *(_DWORD *)(a1 + 8880)),
            !v14 && !v12 && _time64(0) > *(_QWORD *)(a1 + 512)) )
      {
        v15 = Dhcpv6PlumbConfig(a1, 1, 0);
        if ( v15 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_D(1028, 136, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v15);
        }
        else if ( (xmmword_1800423E0 & 0x10) != 0 )
        {
          WPP_SF_(1028, 137, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
        }
      }
    }
    else
    {
LABEL_29:
      ProcessNetworkChange(a1, v5, (__int64)v5, (int)v17, a2);
    }
    result = DhcpFree((LPVOID *)&v19);
  }
  else
  {
    result = Dhcpv6SaveInterfaceConfiguration(a1);
    if ( v4 )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 135, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
      result = Dhcpv6UnplumbStack(a1, 1);
    }
  }
  if ( v17 )
    return DhcpFree(&v17);
  return result;
}

```

## disassembly

```asm
0x180010088  push    rbp
0x18001008a  push    rbx
0x18001008b  push    rsi
0x18001008c  push    rdi
0x18001008d  lea     rbp, [rsp-3Fh]
0x180010092  sub     rsp, 88h
0x180010099  mov     rax, cs:__security_cookie
0x1800100a0  xor     rax, rsp
0x1800100a3  mov     [rbp+57h+var_30], rax
0x1800100a7  mov     rbx, rcx
0x1800100aa  mov     qword ptr [rcx+2314h], 0
0x1800100b5  mov     dword ptr [rcx+231Ch], 0
0x1800100bf  mov     esi, edx
0x1800100c1  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800100c5  mov     [rbp+57h+var_58], 0
0x1800100cd  mov     [rbp+57h+var_68], 0
0x1800100d5  mov     [rbp+57h+var_70], 0
0x1800100dc  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x1800100e4  mov     qword ptr [rbp+57h+var_50], 0
0x1800100ec  call    cs:__imp_QueryPerformanceCounter
0x1800100f3  nop     dword ptr [rax+rax+00h]
0x1800100f8  lea     rcx, [rbx+18h]
0x1800100fc  lea     r9, [rbp+57h+var_68]
0x180010100  lea     r8, [rbp+57h+var_70]
0x180010104  lea     rdx, [rbp+57h+var_58]
0x180010108  call    GetNetworkHint
0x18001010d  lea     rcx, [rbp+57h+var_50]; lpPerformanceCount
0x180010111  call    cs:__imp_QueryPerformanceCounter
0x180010118  nop     dword ptr [rax+rax+00h]
0x18001011d  test    byte ptr cs:xmmword_1800423E0, 10h
0x180010124  jz      short loc_18001016B
0x180010126  mov     rax, qword ptr [rbp+57h+var_50]
0x18001012a  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x180010131  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x180010135  xor     edx, edx
0x180010137  imul    rax, 3B9ACA00h
0x18001013e  div     qword ptr cs:Dhcpv6GlobalPerformanceFrequency
0x180010145  mov     rcx, rax
0x180010148  mov     rax, 431BDE82D7B634DBh
0x180010152  mul     rcx
0x180010155  mov     [rsp+0A0h+var_80], rcx
0x18001015a  mov     r9, rdx
0x18001015d  mov     edx, 86h
0x180010162  shr     r9, 12h
0x180010166  call    WPP_SF_ii
0x18001016b  mov     rdi, [rbx+22F8h]
0x180010172  mov     dword ptr [rbx+2310h], 1
0x18001017c  mov     r8, [rbp+57h+var_58]
0x180010180  test    r8, r8
0x180010183  jnz     short loc_1800101C7
0x180010185  mov     rcx, rbx
0x180010188  call    Dhcpv6SaveInterfaceConfiguration
0x18001018d  test    rdi, rdi
0x180010190  jz      loc_18001030E
0x180010196  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001019d  jz      short loc_1800101B5
0x18001019f  mov     edx, 87h
0x1800101a4  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800101ab  mov     ecx, 404h
0x1800101b0  call    WPP_SF_
0x1800101b5  mov     edx, 1
0x1800101ba  mov     rcx, rbx
0x1800101bd  call    Dhcpv6UnplumbStack
0x1800101c2  jmp     loc_18001030E
0x1800101c7  test    rdi, rdi
0x1800101ca  jz      loc_1800102F2
0x1800101d0  mov     rdx, r8
0x1800101d3  sub     rdx, rdi
0x1800101d6  movzx   eax, word ptr [rdi]
0x1800101d9  movzx   ecx, word ptr [rdi+rdx]
0x1800101dd  sub     eax, ecx
0x1800101df  jnz     short loc_1800101E9
0x1800101e1  add     rdi, 2
0x1800101e5  test    ecx, ecx
0x1800101e7  jnz     short loc_1800101D6
0x1800101e9  test    eax, eax
0x1800101eb  jnz     loc_1800102F2
0x1800101f1  mov     edx, [rbx+22F0h]
0x1800101f7  mov     ecx, esi
0x1800101f9  call    Dhcpv6CompareMode
0x1800101fe  test    eax, eax
0x180010200  jz      loc_1800102F2
0x180010206  xorps   xmm0, xmm0
0x180010209  mov     [rbp+57h+var_60], 0
0x180010210  lea     r9, [rbp+57h+var_70]
0x180010214  mov     [rbp+57h+var_70], 0
0x18001021b  lea     r8, [rbp+57h+var_60]
0x18001021f  mov     rcx, rbx
0x180010222  lea     rdx, [rbp+57h+var_40]
0x180010226  movups  [rbp+57h+var_40], xmm0
0x18001022a  call    IsDHCPV6AddrPlumbed
0x18001022f  mov     edx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x180010235  mov     r8d, eax
0x180010238  test    edx, edx
0x18001023a  jz      short loc_18001024A
0x18001023c  mov     ecx, [rbx+22B0h]
0x180010242  mov     edx, cs:g_fVelocityDhcpv6ContextBitfieldUpdate
0x180010248  jmp     short loc_180010256
0x18001024a  mov     ecx, [rbx+229Ch]
0x180010250  shr     ecx, 5
0x180010253  and     ecx, 1
0x180010256  test    ecx, ecx
0x180010258  jnz     short loc_18001029A
0x18001025a  test    edx, edx
0x18001025c  jz      short loc_180010266
0x18001025e  mov     eax, [rbx+22B0h]
0x180010264  jmp     short loc_180010272
0x180010266  mov     eax, [rbx+229Ch]
0x18001026c  shr     eax, 5
0x18001026f  and     eax, 1
0x180010272  test    eax, eax
0x180010274  jnz     loc_180010305
0x18001027a  test    r8d, r8d
0x18001027d  jnz     loc_180010305
0x180010283  xor     ecx, ecx; Time
0x180010285  call    cs:__imp__time64
0x18001028c  nop     dword ptr [rax+rax+00h]
0x180010291  cmp     rax, [rbx+200h]
0x180010298  jle     short loc_180010305
0x18001029a  xor     r8d, r8d
0x18001029d  mov     rcx, rbx
0x1800102a0  lea     edx, [r8+1]
0x1800102a4  call    Dhcpv6PlumbConfig
0x1800102a9  test    eax, eax
0x1800102ab  jz      short loc_1800102D1
0x1800102ad  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800102b4  jz      short loc_180010305
0x1800102b6  mov     edx, 88h
0x1800102bb  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800102c2  mov     ecx, 404h
0x1800102c7  mov     r9d, eax
0x1800102ca  call    WPP_SF_D
0x1800102cf  jmp     short loc_180010305
0x1800102d1  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800102d8  jz      short loc_180010305
0x1800102da  mov     edx, 89h
0x1800102df  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800102e6  mov     ecx, 404h
0x1800102eb  call    WPP_SF_
0x1800102f0  jmp     short loc_180010305
0x1800102f2  mov     r9, [rbp+57h+var_68]
0x1800102f6  mov     rdx, r8
0x1800102f9  mov     rcx, rbx
0x1800102fc  mov     dword ptr [rsp+0A0h+var_80], esi
0x180010300  call    ProcessNetworkChange
0x180010305  lea     rcx, [rbp+57h+var_58]
0x180010309  call    DhcpFree
0x18001030e  cmp     [rbp+57h+var_68], 0
0x180010313  jz      short loc_18001031E
0x180010315  lea     rcx, [rbp+57h+var_68]
0x180010319  call    DhcpFree
0x18001031e  mov     rcx, [rbp+57h+var_30]
0x180010322  xor     rcx, rsp; StackCookie
0x180010325  call    __security_check_cookie
0x18001032a  add     rsp, 88h
0x180010331  pop     rdi
0x180010332  pop     rsi
0x180010333  pop     rbx
0x180010334  pop     rbp
0x180010335  retn
```
