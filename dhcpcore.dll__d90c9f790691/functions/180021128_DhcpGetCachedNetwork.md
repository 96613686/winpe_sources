# DhcpGetCachedNetwork

- ea: `0x180021128`
- end: `0x180021418`
- name: `DhcpGetCachedNetwork`
- size: `752`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800227ac`
- `0x18003592c`

## callees

- `0x1800057f0`
- `0x180009038`
- `0x180009174`
- `0x18001098c`
- `0x180010e00`
- `0x180012ef0`
- `0x180014bd8`
- `0x180015604`
- `0x18001bb80`
- `0x18001d826`
- `0x1800205e4`
- `0x180021128`
- `0x180024488`
- `0x1800368d0`
- `0x180047e30`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d4c0`
- `0x18004e118`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800211ac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800211cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800211ac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800211cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021332`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180021332`

## pseudocode

```c
__int64 __fastcall DhcpGetCachedNetwork(__int64 a1)
{
  __int64 v2; // rcx
  const wchar_t *v3; // r14
  int v4; // ecx
  unsigned int v5; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-D0h] BYREF
  size_t pcchLength; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v9[15]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v10; // [rsp+140h] [rbp+40h] BYREF
  void *Buf1; // [rsp+148h] [rbp+48h] BYREF
  __int64 v12; // [rsp+150h] [rbp+50h] BYREF
  LARGE_INTEGER v13; // [rsp+158h] [rbp+58h] BYREF

  Buf1 = 0;
  v12 = 0;
  memset_0(v9, 0, 0xC8u);
  PerformanceCount.QuadPart = 0;
  v13.QuadPart = 0;
  v10 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 189, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(_QWORD *)(a1 + 24));
  *(_QWORD *)(a1 + 1920) = 1;
  *(_DWORD *)(a1 + 1928) = 0;
  *(_DWORD *)(a1 + 1956) = 1;
  QueryPerformanceCounter(&PerformanceCount);
  GetNetworkHint(*(_QWORD *)(a1 + 24), &Buf1, &v10, &v12);
  QueryPerformanceCounter(&v13);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_II(
      (unsigned __int64)(1000000000 * (v13.QuadPart - PerformanceCount.QuadPart))
    / DhcpGlobalPerformanceFrequency.QuadPart,
      190,
      WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids,
      (unsigned __int64)(1000000000 * (v13.QuadPart - PerformanceCount.QuadPart))
    / DhcpGlobalPerformanceFrequency.QuadPart
    / 0xF4240,
      (unsigned __int64)(1000000000 * (v13.QuadPart - PerformanceCount.QuadPart))
    / DhcpGlobalPerformanceFrequency.QuadPart);
  if ( Buf1 )
  {
    v3 = *(const wchar_t **)(a1 + 1888);
    if ( Microsoft_Windows_Dhcp_ClientEnableBits < 0 )
      McTemplateU0zzqbr2_EtwEventWriteTransfer(
        v2,
        (unsigned int)NetworkHintReceived,
        v12,
        (_DWORD)Buf1,
        *(_DWORD *)(a1 + 96),
        *(_QWORD *)(a1 + 88));
    if ( v3 )
    {
      pcchLength = 0;
      if ( StringCchLengthW(v3, 0x7FFFFFFFu, &pcchLength) < 0 )
      {
LABEL_26:
        DhcpPunycodeFree(&Buf1);
        goto LABEL_27;
      }
      if ( v10 == pcchLength + 1 && !memcmp_0(Buf1, v3, 2 * pcchLength) )
      {
        *(_DWORD *)(a1 + 1924) = 1;
        if ( Microsoft_Windows_Dhcp_ClientEnableBits < 0 )
          McTemplateU0zzqbr2_EtwEventWriteTransfer(
            v4,
            (unsigned int)NetworkHintMatchFound,
            v12,
            (_DWORD)Buf1,
            *(_DWORD *)(a1 + 96),
            *(_QWORD *)(a1 + 88));
        if ( !(unsigned int)DhcpIsInitState(a1)
          && !(unsigned int)IsDhcpAddressPlumbedInStack(a1)
          && GetTickCount64() / 0x3E8 <= *(_QWORD *)(a1 + 472) )
        {
          DhcpCopyExistingStackParams(a1, v9);
          v5 = ApplyDhcpConfigurationToNIC(a1, (__int64)v9, 1);
          if ( v5 )
          {
            if ( (xmmword_1800616A0 & 0x10) != 0 )
              WPP_SF_D(1028, 191, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v5);
          }
          else
          {
            *(_DWORD *)(a1 + 776) = 0;
            if ( (xmmword_1800616A0 & 0x10) != 0 )
              WPP_SF_(1028, 192, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
          }
        }
        goto LABEL_26;
      }
    }
    ProcessNetworkChange(a1, Buf1, v10, v12);
    goto LABEL_26;
  }
  *(_DWORD *)(a1 + 1920) = 0;
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v2, NetworkHintNotReceived, *(unsigned int *)(a1 + 48));
  DhcpSaveInterfaceConfiguration(a1);
LABEL_27:
  if ( v12 )
    DhcpPunycodeFree(&v12);
  DhcpCleanParsedOptions((char *)v9);
  return 0;
}

```

## disassembly

```asm
0x180021128  push    rbp
0x18002112a  push    rbx
0x18002112b  push    r14
0x18002112d  push    r15
0x18002112f  lea     rbp, [rsp-18h]
0x180021134  sub     rsp, 118h
0x18002113b  xor     r15d, r15d
0x18002113e  mov     rbx, rcx
0x180021141  lea     rcx, [rsp+130h+var_F0]; void *
0x180021146  mov     [rbp+30h+Buf1], r15
0x18002114a  xor     edx, edx; Val
0x18002114c  mov     [rbp+30h+arg_10], r15
0x180021150  mov     r8d, 0C8h; Size
0x180021156  call    memset_0
0x18002115b  mov     qword ptr [rsp+130h+PerformanceCount], r15
0x180021160  mov     qword ptr [rbp+30h+arg_18], r15
0x180021164  mov     [rbp+30h+arg_0], r15d
0x180021168  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002116f  jz      short loc_18002118B
0x180021171  mov     r9, [rbx+18h]
0x180021175  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002117c  mov     edx, 0BDh
0x180021181  mov     ecx, 404h
0x180021186  call    WPP_SF_q
0x18002118b  lea     rcx, [rsp+130h+PerformanceCount]; lpPerformanceCount
0x180021190  mov     qword ptr [rbx+780h], 1
0x18002119b  mov     [rbx+788h], r15d
0x1800211a2  mov     dword ptr [rbx+7A4h], 1
0x1800211ac  call    cs:__imp_QueryPerformanceCounter
0x1800211b2  mov     rcx, [rbx+18h]
0x1800211b6  lea     r9, [rbp+30h+arg_10]
0x1800211ba  lea     r8, [rbp+30h+arg_0]
0x1800211be  lea     rdx, [rbp+30h+Buf1]
0x1800211c2  call    GetNetworkHint
0x1800211c7  lea     rcx, [rbp+30h+arg_18]; lpPerformanceCount
0x1800211cb  call    cs:__imp_QueryPerformanceCounter
0x1800211d1  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800211d8  jz      short loc_180021220
0x1800211da  mov     rax, qword ptr [rbp+30h+arg_18]
0x1800211de  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800211e5  sub     rax, qword ptr [rsp+130h+PerformanceCount]
0x1800211ea  xor     edx, edx
0x1800211ec  imul    rax, 3B9ACA00h
0x1800211f3  div     qword ptr cs:DhcpGlobalPerformanceFrequency
0x1800211fa  mov     rcx, rax
0x1800211fd  mov     rax, 431BDE82D7B634DBh
0x180021207  mul     rcx
0x18002120a  mov     [rsp+130h+var_110], rcx
0x18002120f  mov     r9, rdx
0x180021212  mov     edx, 0BEh
0x180021217  shr     r9, 12h
0x18002121b  call    WPP_SF_II
0x180021220  cmp     [rbp+30h+Buf1], r15
0x180021224  jnz     short loc_180021253
0x180021226  mov     [rbx+780h], r15d
0x18002122d  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x180021234  jz      short loc_180021246
0x180021236  mov     r8d, [rbx+30h]
0x18002123a  lea     rdx, NetworkHintNotReceived
0x180021241  call    McTemplateU0q_EtwEventWriteTransfer
0x180021246  mov     rcx, rbx
0x180021249  call    DhcpSaveInterfaceConfiguration
0x18002124e  jmp     loc_1800213EF
0x180021253  cmp     cs:Microsoft_Windows_Dhcp_ClientEnableBits, r15b
0x18002125a  mov     r14, [rbx+760h]
0x180021261  jge     short loc_180021287
0x180021263  mov     rax, [rbx+58h]
0x180021267  lea     rdx, NetworkHintReceived
0x18002126e  mov     r9, [rbp+30h+Buf1]
0x180021272  mov     r8, [rbp+30h+arg_10]
0x180021276  mov     [rsp+130h+var_108], rax
0x18002127b  mov     eax, [rbx+60h]
0x18002127e  mov     dword ptr [rsp+130h+var_110], eax
0x180021282  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x180021287  test    r14, r14
0x18002128a  jz      loc_1800213D2
0x180021290  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x180021295  mov     [rsp+130h+pcchLength], r15
0x18002129a  mov     edx, 7FFFFFFFh; cchMax
0x18002129f  mov     rcx, r14; psz
0x1800212a2  call    StringCchLengthW
0x1800212a7  test    eax, eax
0x1800212a9  js      loc_1800213E6
0x1800212af  mov     r8, [rsp+130h+pcchLength]
0x1800212b4  mov     eax, [rbp+30h+arg_0]
0x1800212b7  lea     rcx, [r8+1]
0x1800212bb  cmp     rax, rcx
0x1800212be  jnz     loc_1800213D2
0x1800212c4  mov     rcx, [rbp+30h+Buf1]; Buf1
0x1800212c8  add     r8, r8; Size
0x1800212cb  mov     rdx, r14; Buf2
0x1800212ce  call    memcmp_0
0x1800212d3  test    eax, eax
0x1800212d5  jnz     loc_1800213D2
0x1800212db  mov     dword ptr [rbx+784h], 1
0x1800212e5  cmp     cs:Microsoft_Windows_Dhcp_ClientEnableBits, r15b
0x1800212ec  jge     short loc_180021312
0x1800212ee  mov     rax, [rbx+58h]
0x1800212f2  lea     rdx, NetworkHintMatchFound
0x1800212f9  mov     r9, [rbp+30h+Buf1]
0x1800212fd  mov     r8, [rbp+30h+arg_10]
0x180021301  mov     [rsp+130h+var_108], rax
0x180021306  mov     eax, [rbx+60h]
0x180021309  mov     dword ptr [rsp+130h+var_110], eax
0x18002130d  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x180021312  mov     rcx, rbx
0x180021315  call    DhcpIsInitState
0x18002131a  test    eax, eax
0x18002131c  jnz     loc_1800213E6
0x180021322  mov     rcx, rbx
0x180021325  call    IsDhcpAddressPlumbedInStack
0x18002132a  test    eax, eax
0x18002132c  jnz     loc_1800213E6
0x180021332  call    cs:__imp_GetTickCount64
0x180021338  mov     rcx, rax
0x18002133b  mov     rax, 624DD2F1A9FBE77h
0x180021345  mul     rcx
0x180021348  sub     rcx, rdx
0x18002134b  shr     rcx, 1
0x18002134e  add     rcx, rdx
0x180021351  shr     rcx, 9
0x180021355  cmp     rcx, [rbx+1D8h]
0x18002135c  ja      loc_1800213E6
0x180021362  lea     rdx, [rsp+130h+var_F0]
0x180021367  mov     rcx, rbx
0x18002136a  call    DhcpCopyExistingStackParams
0x18002136f  mov     r8d, 1
0x180021375  lea     rdx, [rsp+130h+var_F0]
0x18002137a  mov     rcx, rbx
0x18002137d  call    ApplyDhcpConfigurationToNIC
0x180021382  test    eax, eax
0x180021384  jz      short loc_1800213AA
0x180021386  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002138d  jz      short loc_1800213E6
0x18002138f  mov     edx, 0BFh
0x180021394  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002139b  mov     ecx, 404h
0x1800213a0  mov     r9d, eax
0x1800213a3  call    WPP_SF_D
0x1800213a8  jmp     short loc_1800213E6
0x1800213aa  mov     [rbx+308h], r15d
0x1800213b1  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800213b8  jz      short loc_1800213E6
0x1800213ba  mov     edx, 0C0h
0x1800213bf  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800213c6  mov     ecx, 404h
0x1800213cb  call    WPP_SF_
0x1800213d0  jmp     short loc_1800213E6
0x1800213d2  mov     r9, [rbp+30h+arg_10]
0x1800213d6  mov     rcx, rbx
0x1800213d9  mov     r8d, [rbp+30h+arg_0]
0x1800213dd  mov     rdx, [rbp+30h+Buf1]
0x1800213e1  call    ProcessNetworkChange
0x1800213e6  lea     rcx, [rbp+30h+Buf1]
0x1800213ea  call    DhcpPunycodeFree
0x1800213ef  cmp     [rbp+30h+arg_10], r15
0x1800213f3  jz      short loc_1800213FE
0x1800213f5  lea     rcx, [rbp+30h+arg_10]
0x1800213f9  call    DhcpPunycodeFree
0x1800213fe  lea     rcx, [rsp+130h+var_F0]; void *
0x180021403  call    DhcpCleanParsedOptions
0x180021408  xor     eax, eax
0x18002140a  add     rsp, 118h
0x180021411  pop     r15
0x180021413  pop     r14
0x180021415  pop     rbx
0x180021416  pop     rbp
0x180021417  retn
```
