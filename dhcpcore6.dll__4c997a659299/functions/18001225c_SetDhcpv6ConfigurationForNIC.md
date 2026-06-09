# SetDhcpv6ConfigurationForNIC

- ea: `0x18001225c`
- end: `0x180012606`
- name: `SetDhcpv6ConfigurationForNIC`
- size: `938`
- prototype: `__int64 __fastcall(__int64, __int128 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cabc`

## callees

- `0x1800015a0`
- `0x1800016e0`
- `0x180004a8c`
- `0x180004c3c`
- `0x180005b88`
- `0x180007efc`
- `0x18000e000`
- `0x18000ed18`
- `0x180010fd4`
- `0x18001225c`
- `0x18001260c`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001e110`
- `0x1800338c0`
- `0x180034458`
- `0x1800348c4`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001232d`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18001232d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012367`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012367`

## pseudocode

```c
__int64 __fastcall SetDhcpv6ConfigurationForNIC(__int64 a1, __int128 *a2, unsigned int a3, unsigned int a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // r8d
  __int128 v11; // xmm0
  __time64_t v12; // rax
  __int64 v13; // r9
  unsigned int v14; // esi
  __int64 v15; // r8
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  int v18; // ecx
  int v19; // r8d
  int v20; // ecx
  unsigned int updated; // ebx
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  int v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v29[5]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v30; // [rsp+74h] [rbp-8Ch]
  __int128 v31; // [rsp+7Ch] [rbp-84h]
  _BYTE v32[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 *v33; // [rsp+1C0h] [rbp+C0h]
  __int64 v34; // [rsp+1C8h] [rbp+C8h]
  __int64 *v35; // [rsp+1D0h] [rbp+D0h]
  __int64 v36; // [rsp+1D8h] [rbp+D8h]
  __int64 *v37; // [rsp+1E0h] [rbp+E0h]
  __int64 v38; // [rsp+1E8h] [rbp+E8h]
  __int64 v39; // [rsp+1F0h] [rbp+F0h]
  __int64 v40; // [rsp+1F8h] [rbp+F8h]
  int *v41; // [rsp+200h] [rbp+100h]
  __int64 v42; // [rsp+208h] [rbp+108h]
  int *v43; // [rsp+210h] [rbp+110h]
  __int64 v44; // [rsp+218h] [rbp+118h]
  int *v45; // [rsp+220h] [rbp+120h]
  __int64 v46; // [rsp+228h] [rbp+128h]
  __int64 v47; // [rsp+230h] [rbp+130h]
  __int64 v48; // [rsp+238h] [rbp+138h]
  UUID *v49; // [rsp+240h] [rbp+140h]
  __int64 v50; // [rsp+248h] [rbp+148h]

  memset_0(v29, 0, 0x140u);
  if ( (unsigned int)Dhcpv6IsInitState(a1) )
    Dhcpv6ClearAllOptions((RTL_SRWLOCK *)a1);
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF__IPV6_S(1025, 45, v10, (_DWORD)a2, *(_QWORD *)(a1 + 56));
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0b16z_EtwEventWriteTransfer(v9, v8, a2, *(_QWORD *)(a1 + 56));
  InitializeTraceElementFromContext(v29, a1, 0, 125);
  v11 = *a2;
  v30 = 23;
  v31 = v11;
  TraceLogEx(v29);
  v12 = _time64(0);
  if ( v12 <= *(_QWORD *)(a1 + 536) )
    v14 = 0;
  else
    v14 = v12 - *(_DWORD *)(a1 + 536);
  if ( *(_DWORD *)(a1 + 9020) )
  {
    QueryPerformanceCounter((LARGE_INTEGER *)(a1 + 9008));
    v16 = (unsigned __int64)(1000000000LL * (*(_QWORD *)(a1 + 9008) - *(_QWORD *)(a1 + 9000)))
        / Dhcpv6GlobalPerformanceFrequency.QuadPart;
    v17 = v16 / 0xF4240;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_ii(v16, 46, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
    *(_DWORD *)(a1 + 9016) = v17;
    if ( (unsigned int)dword_180042048 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180042048, 0x400000000000LL, v15, v13) )
    {
      v26 = *(unsigned int *)(a1 + 9016);
      v33 = &v26;
      v27 = *(_QWORD *)(a1 + 536);
      v35 = &v27;
      v28 = *(_QWORD *)(a1 + 512);
      v37 = &v28;
      v39 = a1 + 32;
      v23 = *(_DWORD *)(a1 + 48);
      v41 = &v23;
      v24 = *(_DWORD *)(a1 + 92);
      v43 = &v24;
      v25 = *(_DWORD *)(a1 + 96);
      v45 = &v25;
      v47 = a1 + 9136;
      v49 = &Dhcpv6GlobalBootGuid;
      v34 = 8;
      v36 = 8;
      v38 = 8;
      v40 = 16;
      v42 = 4;
      v44 = 4;
      v46 = 4;
      v48 = 16;
      v50 = 16;
      tlgWriteTransfer_EtwEventWriteTransfer(v18, (unsigned int)byte_18003C391, v19, v13, 11, (__int64)v32);
    }
    *(_DWORD *)(a1 + 9020) = 0;
  }
  updated = Dhcpv6AddOrUpdateIPv6Address(
              (int)a1 + 24,
              *(_DWORD *)(a1 + 48),
              (_DWORD)a2,
              v13,
              v14 < a3 ? a3 - v14 : 0,
              v14 < a4 ? a4 - v14 : 0);
  if ( !updated )
  {
    if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
      *(_DWORD *)(a1 + 8864) = 1;
    else
      *(_DWORD *)(a1 + 8860) |= 1u;
    *(_DWORD *)(a1 + 8920) = ((unsigned int)Dhcpv6RegisterWithDns(a1, 0) != 0) + 2;
    NotifyDnsCache();
  }
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 2) != 0 )
    McTemplateU0b16qq_EtwEventWriteTransfer(
      v20,
      (unsigned int)AddressPlumbed,
      (_DWORD)a2,
      *(_DWORD *)(a1 + 48),
      updated);
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 47, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, updated);
  return updated;
}

```

## disassembly

```asm
0x18001225c  push    rbp
0x18001225e  push    rbx
0x18001225f  push    rsi
0x180012260  push    rdi
0x180012261  push    r12
0x180012263  push    r13
0x180012265  push    r14
0x180012267  push    r15
0x180012269  lea     rbp, [rsp-168h]
0x180012271  sub     rsp, 268h
0x180012278  mov     rax, cs:__security_cookie
0x18001227f  xor     rax, rsp
0x180012282  mov     [rbp+1A0h+var_50], rax
0x180012289  mov     r15d, r8d
0x18001228c  mov     r14, rdx
0x18001228f  mov     rdi, rcx
0x180012292  xor     edx, edx; Val
0x180012294  mov     r8d, 140h; Size
0x18001229a  lea     rcx, [rsp+2A0h+var_240]; void *
0x18001229f  mov     r12d, r9d
0x1800122a2  call    memset_0
0x1800122a7  mov     rcx, rdi
0x1800122aa  call    Dhcpv6IsInitState
0x1800122af  xor     r13d, r13d
0x1800122b2  test    eax, eax
0x1800122b4  jz      short loc_1800122BE
0x1800122b6  mov     rcx, rdi
0x1800122b9  call    Dhcpv6ClearAllOptions
0x1800122be  test    byte ptr cs:xmmword_1800423E0, 2
0x1800122c5  jz      short loc_1800122E2
0x1800122c7  mov     rax, [rdi+38h]
0x1800122cb  mov     edx, 2Dh ; '-'
0x1800122d0  mov     ecx, 401h
0x1800122d5  mov     [rsp+2A0h+var_280], rax
0x1800122da  mov     r9, r14
0x1800122dd  call    WPP_SF__IPV6_S
0x1800122e2  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x1800122e9  jz      short loc_1800122F7
0x1800122eb  mov     r9, [rdi+38h]
0x1800122ef  mov     r8, r14
0x1800122f2  call    McTemplateU0b16z_EtwEventWriteTransfer
0x1800122f7  mov     r9d, 7Dh ; '}'
0x1800122fd  lea     rcx, [rsp+2A0h+var_240]
0x180012302  xor     r8d, r8d
0x180012305  mov     rdx, rdi
0x180012308  call    InitializeTraceElementFromContext
0x18001230d  movups  xmm0, xmmword ptr [r14]
0x180012311  mov     eax, 17h
0x180012316  lea     rcx, [rsp+2A0h+var_240]
0x18001231b  mov     [rsp+2A0h+var_22C], ax
0x180012320  movdqu  [rsp+2A0h+var_224], xmm0
0x180012326  call    TraceLogEx
0x18001232b  xor     ecx, ecx; Time
0x18001232d  call    cs:__imp__time64
0x180012334  nop     dword ptr [rax+rax+00h]
0x180012339  mov     rsi, rax
0x18001233c  cmp     rax, [rdi+218h]
0x180012343  jle     short loc_18001234D
0x180012345  sub     esi, [rdi+218h]
0x18001234b  jmp     short loc_180012350
0x18001234d  mov     esi, r13d
0x180012350  cmp     [rdi+233Ch], r13d
0x180012357  jz      loc_18001252A
0x18001235d  lea     rbx, [rdi+2330h]
0x180012364  mov     rcx, rbx; lpPerformanceCount
0x180012367  call    cs:__imp_QueryPerformanceCounter
0x18001236e  nop     dword ptr [rax+rax+00h]
0x180012373  mov     rax, [rbx]
0x180012376  xor     edx, edx
0x180012378  sub     rax, [rdi+2328h]
0x18001237f  imul    rax, 3B9ACA00h
0x180012386  div     qword ptr cs:Dhcpv6GlobalPerformanceFrequency
0x18001238d  mov     rcx, rax
0x180012390  mov     rax, 431BDE82D7B634DBh
0x18001239a  mul     rcx
0x18001239d  mov     rbx, rdx
0x1800123a0  shr     rbx, 12h
0x1800123a4  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800123ab  jz      short loc_1800123C6
0x1800123ad  mov     edx, 2Eh ; '.'
0x1800123b2  mov     [rsp+2A0h+var_280], rcx
0x1800123b7  mov     r9, rbx
0x1800123ba  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800123c1  call    WPP_SF_ii
0x1800123c6  mov     [rdi+2338h], ebx
0x1800123cc  mov     eax, cs:dword_180042048
0x1800123d2  cmp     eax, 5
0x1800123d5  jbe     loc_180012523
0x1800123db  mov     rdx, 400000000000h
0x1800123e5  lea     rcx, dword_180042048
0x1800123ec  call    _tlgKeywordOn
0x1800123f1  test    al, al
0x1800123f3  jz      loc_180012523
0x1800123f9  mov     eax, [rdi+2338h]
0x1800123ff  lea     rdx, byte_18003C391
0x180012406  mov     [rsp+2A0h+var_260], rax
0x18001240b  lea     rax, [rsp+2A0h+var_260]
0x180012410  mov     [rbp+1A0h+var_E0], rax
0x180012417  mov     rax, [rdi+218h]
0x18001241e  mov     [rsp+2A0h+var_258], rax
0x180012423  lea     rax, [rsp+2A0h+var_258]
0x180012428  mov     [rbp+1A0h+var_D0], rax
0x18001242f  mov     rax, [rdi+200h]
0x180012436  mov     [rsp+2A0h+var_250], rax
0x18001243b  lea     rax, [rsp+2A0h+var_250]
0x180012440  mov     [rbp+1A0h+var_C0], rax
0x180012447  lea     rax, [rdi+20h]
0x18001244b  mov     [rbp+1A0h+var_B0], rax
0x180012452  mov     eax, [rdi+30h]
0x180012455  mov     [rsp+2A0h+var_270], eax
0x180012459  lea     rax, [rsp+2A0h+var_270]
0x18001245e  mov     [rbp+1A0h+var_A0], rax
0x180012465  mov     eax, [rdi+5Ch]
0x180012468  mov     [rsp+2A0h+var_26C], eax
0x18001246c  lea     rax, [rsp+2A0h+var_26C]
0x180012471  mov     [rbp+1A0h+var_90], rax
0x180012478  mov     eax, [rdi+60h]
0x18001247b  mov     [rsp+2A0h+var_268], eax
0x18001247f  lea     rax, [rsp+2A0h+var_268]
0x180012484  mov     [rbp+1A0h+var_80], rax
0x18001248b  lea     rax, [rdi+23B0h]
0x180012492  mov     [rbp+1A0h+var_70], rax
0x180012499  lea     rax, Dhcpv6GlobalBootGuid
0x1800124a0  mov     [rbp+1A0h+var_60], rax
0x1800124a7  lea     rax, [rbp+1A0h+var_100]
0x1800124ae  mov     [rsp+2A0h+var_278], rax
0x1800124b3  mov     dword ptr [rsp+2A0h+var_280], 0Bh
0x1800124bb  mov     [rbp+1A0h+var_D8], 8
0x1800124c6  mov     [rbp+1A0h+var_C8], 8
0x1800124d1  mov     [rbp+1A0h+var_B8], 8
0x1800124dc  mov     [rbp+1A0h+var_A8], 10h
0x1800124e7  mov     [rbp+1A0h+var_98], 4
0x1800124f2  mov     [rbp+1A0h+var_88], 4
0x1800124fd  mov     [rbp+1A0h+var_78], 4
0x180012508  mov     [rbp+1A0h+var_68], 10h
0x180012513  mov     [rbp+1A0h+var_58], 10h
0x18001251e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180012523  mov     [rdi+233Ch], r13d
0x18001252a  mov     eax, r12d
0x18001252d  lea     rcx, [rdi+18h]
0x180012531  sub     eax, esi
0x180012533  cmp     esi, r12d
0x180012536  sbb     r8d, r8d
0x180012539  and     r8d, eax
0x18001253c  mov     eax, r15d
0x18001253f  sub     eax, esi
0x180012541  mov     dword ptr [rsp+2A0h+var_278], r8d
0x180012546  cmp     esi, r15d
0x180012549  mov     r8, r14
0x18001254c  sbb     edx, edx
0x18001254e  and     edx, eax
0x180012550  mov     dword ptr [rsp+2A0h+var_280], edx
0x180012554  mov     edx, [rdi+30h]
0x180012557  call    Dhcpv6AddOrUpdateIPv6Address
0x18001255c  mov     ebx, eax
0x18001255e  test    eax, eax
0x180012560  jnz     short loc_18001259E
0x180012562  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, r13d
0x180012569  jz      short loc_180012577
0x18001256b  mov     dword ptr [rdi+22A0h], 1
0x180012575  jmp     short loc_18001257E
0x180012577  or      dword ptr [rdi+229Ch], 1
0x18001257e  xor     edx, edx
0x180012580  mov     rcx, rdi
0x180012583  call    Dhcpv6RegisterWithDns
0x180012588  mov     ecx, r13d
0x18001258b  test    eax, eax
0x18001258d  setnz   cl
0x180012590  add     ecx, 2
0x180012593  mov     [rdi+22D8h], ecx
0x180012599  call    NotifyDnsCache
0x18001259e  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 2
0x1800125a5  jz      short loc_1800125BE
0x1800125a7  mov     r9d, [rdi+30h]
0x1800125ab  lea     rdx, AddressPlumbed
0x1800125b2  mov     r8, r14
0x1800125b5  mov     dword ptr [rsp+2A0h+var_280], ebx
0x1800125b9  call    McTemplateU0b16qq_EtwEventWriteTransfer
0x1800125be  test    byte ptr cs:xmmword_1800423E0, 2
0x1800125c5  jz      short loc_1800125E0
0x1800125c7  mov     edx, 2Fh ; '/'
0x1800125cc  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x1800125d3  mov     ecx, 401h
0x1800125d8  mov     r9d, ebx
0x1800125db  call    WPP_SF_D
0x1800125e0  mov     eax, ebx
0x1800125e2  mov     rcx, [rbp+1A0h+var_50]
0x1800125e9  xor     rcx, rsp; StackCookie
0x1800125ec  call    __security_check_cookie
0x1800125f1  add     rsp, 268h
0x1800125f8  pop     r15
0x1800125fa  pop     r14
0x1800125fc  pop     r13
0x1800125fe  pop     r12
0x180012600  pop     rdi
0x180012601  pop     rsi
0x180012602  pop     rbx
0x180012603  pop     rbp
0x180012604  retn
```
