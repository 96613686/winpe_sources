# NatAddICMPv6RuleToGroupExceptionForSharingEx(_GUID const *,ushort const *,ushort,uchar,_GUID,eWFP_IP_TYPE,int)

- ea: `0x18007d1b4`
- end: `0x18007d4b1`
- name: `?NatAddICMPv6RuleToGroupExceptionForSharingEx@@YAJPEBU_GUID@@PEBGGEU1@W4eWFP_IP_TYPE@@H@Z`
- size: `765`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18002dd90`

## callees

- `0x18000c750`
- `0x18002e5e0`
- `0x18004e0c0`
- `0x18004ed64`
- `0x18007d1b4`
- `0x18007d4b8`
- `0x18007d7e4`

## import_xrefs

- `FirewallAPI!FWClosePolicyStore` at `0x18007d453`
- `FirewallAPI!FWClosePolicyStore` at `0x18007d453`
- `FirewallAPI!FWOpenPolicyStore` at `0x18007d289`
- `FirewallAPI!FWOpenPolicyStore` at `0x18007d289`
- `FirewallAPI!FWAddFirewallRule` at `0x18007d3b7`
- `FirewallAPI!FWAddFirewallRule` at `0x18007d3b7`

## string_xrefs

- `0x18007d340`: `@ipnathlp.dll,-148`
- `0x18007d34c`: `@ipnathlp.dll,-10147`
- `0x18007d396`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 __fastcall NatAddICMPv6RuleToGroupExceptionForSharingEx(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int8 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  int Guid; // eax
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  const wchar_t *v21; // [rsp+70h] [rbp-90h]
  char v22[4]; // [rsp+78h] [rbp-88h]
  char v23[4]; // [rsp+7Ch] [rbp-84h]
  __int16 v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+88h] [rbp-78h]
  int *v26; // [rsp+90h] [rbp-70h]
  int v27; // [rsp+148h] [rbp+48h]
  __int64 v28; // [rsp+150h] [rbp+50h]
  int v29; // [rsp+170h] [rbp+70h]
  __int16 v30; // [rsp+174h] [rbp+74h]
  const wchar_t *v31; // [rsp+188h] [rbp+88h]
  unsigned __int16 v32[56]; // [rsp+250h] [rbp+150h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dd_guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), a4, a3, (unsigned __int16)a3, a4, a5);
  }
  v16 = 0;
  memset_0(v17, 0, 0x1F8u);
  v15 = 0;
  memset_0(v32, 0, 0x64u);
  Guid = FWOpenPolicyStore(545, 0, 5, 2, 0, &v16);
  if ( Guid )
  {
    if ( Guid > 0 )
      v11 = (unsigned __int16)Guid | 0x80070000;
    else
      v11 = Guid;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 80;
LABEL_13:
      WPP_SF_d(v12[2], v13, &WPP_213010f39927376708ca656d45278473_Traceguids, (unsigned int)Guid);
LABEL_31:
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    Guid = NatGenerateGuid(v32, v9);
    v11 = Guid;
    if ( Guid >= 0 )
    {
      LOBYTE(v15) = -123;
      v25 = 1;
      v18 = 545;
      v20 = (__int64)L"@ipnathlp.dll,-148";
      v21 = L"@ipnathlp.dll,-10147";
      v19 = (__int64)v32;
      v24 = 58;
      v27 = 1;
      v30 = 1;
      *(_DWORD *)v23 = (a7 != 0) + 1;
      HIWORD(v15) = 256;
      v26 = &v15;
      v31 = L"@ipnathlp.dll,-140";
      *(_DWORD *)v22 = 7;
      v28 = a1;
      v29 = 3;
      Guid = FWAddFirewallRule(v16, v17);
      if ( Guid )
      {
        if ( Guid > 0 )
          v11 = (unsigned __int16)Guid | 0x80070000;
        else
          v11 = Guid;
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 82;
          goto LABEL_13;
        }
      }
      else
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_DdSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23[0], v20, v19, v22[0]);
          goto LABEL_31;
        }
      }
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 81;
        goto LABEL_13;
      }
    }
  }
  if ( v16 )
  {
    FWClosePolicyStore(v16, v9, v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x200) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 84, &WPP_213010f39927376708ca656d45278473_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18007d1b4  mov     [rsp-8+arg_8], rbx
0x18007d1b9  mov     [rsp-8+arg_18], rsi
0x18007d1be  push    rbp
0x18007d1bf  push    rdi
0x18007d1c0  push    r15
0x18007d1c2  lea     rbp, [rsp-1D0h]
0x18007d1ca  sub     rsp, 2D0h
0x18007d1d1  mov     rax, cs:__security_cookie
0x18007d1d8  xor     rax, rsp
0x18007d1db  mov     [rbp+1E0h+var_20], rax
0x18007d1e2  mov     r10, [rbp+1E0h+arg_20]
0x18007d1e9  mov     rdi, rcx
0x18007d1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d1f3  lea     r15, WPP_GLOBAL_Control
0x18007d1fa  mov     esi, 200h
0x18007d1ff  cmp     rcx, r15
0x18007d202  jz      short loc_18007D233
0x18007d204  test    [rcx+1Ch], esi
0x18007d207  jz      short loc_18007D233
0x18007d209  cmp     byte ptr [rcx+19h], 6
0x18007d20d  jb      short loc_18007D233
0x18007d20f  mov     eax, [rbp+1E0h+arg_28]
0x18007d215  mov     rcx, [rcx+10h]
0x18007d219  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x18007d21d  movzx   edx, r9b
0x18007d221  mov     [rsp+2E0h+var_2B8], r10
0x18007d226  movzx   r9d, r8w
0x18007d22a  mov     dword ptr [rsp+2E0h+var_2C0], edx
0x18007d22e  call    WPP_SF_dd_guid_d
0x18007d233  xor     edx, edx; Val
0x18007d235  mov     [rsp+2E0h+var_298], 0
0x18007d23e  mov     r8d, 1F8h; Size
0x18007d244  lea     rcx, [rsp+2E0h+var_290]; void *
0x18007d249  call    memset_0
0x18007d24e  xor     edx, edx; Val
0x18007d250  mov     [rsp+2E0h+var_2A0], 0
0x18007d258  lea     rcx, [rbp+1E0h+var_90]; void *
0x18007d25f  lea     r8d, [rdx+64h]; Size
0x18007d263  call    memset_0
0x18007d268  xor     edx, edx
0x18007d26a  lea     rax, [rsp+2E0h+var_298]
0x18007d26f  mov     [rsp+2E0h+var_2B8], rax
0x18007d274  mov     ecx, 221h
0x18007d279  mov     dword ptr [rsp+2E0h+var_2C0], 0
0x18007d281  lea     r9d, [rdx+2]
0x18007d285  lea     r8d, [rdx+5]
0x18007d289  call    cs:__imp_FWOpenPolicyStore
0x18007d28f  test    eax, eax
0x18007d291  jz      short loc_18007D2E2
0x18007d293  jg      short loc_18007D299
0x18007d295  mov     ebx, eax
0x18007d297  jmp     short loc_18007D2A2
0x18007d299  movzx   ebx, ax
0x18007d29c  or      ebx, 80070000h
0x18007d2a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2a9  cmp     rcx, r15
0x18007d2ac  jz      loc_18007D446
0x18007d2b2  test    [rcx+1Ch], esi
0x18007d2b5  jz      loc_18007D446
0x18007d2bb  cmp     byte ptr [rcx+19h], 2
0x18007d2bf  jb      loc_18007D446
0x18007d2c5  mov     edx, 50h ; 'P'
0x18007d2ca  mov     rcx, [rcx+10h]
0x18007d2ce  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18007d2d5  mov     r9d, eax
0x18007d2d8  call    WPP_SF_d
0x18007d2dd  jmp     loc_18007D43F
0x18007d2e2  lea     rcx, [rbp+1E0h+var_90]; unsigned __int16 *
0x18007d2e9  call    ?NatGenerateGuid@@YAJPEAG_K@Z; NatGenerateGuid(ushort *,unsigned __int64)
0x18007d2ee  mov     ebx, eax
0x18007d2f0  test    eax, eax
0x18007d2f2  jns     short loc_18007D31E
0x18007d2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d2fb  cmp     rcx, r15
0x18007d2fe  jz      loc_18007D446
0x18007d304  test    [rcx+1Ch], esi
0x18007d307  jz      loc_18007D446
0x18007d30d  cmp     byte ptr [rcx+19h], 2
0x18007d311  jb      loc_18007D446
0x18007d317  mov     edx, 51h ; 'Q'
0x18007d31c  jmp     short loc_18007D2CA
0x18007d31e  neg     [rbp+1E0h+arg_30]
0x18007d324  lea     rdx, [rsp+2E0h+var_290]
0x18007d329  mov     ecx, 1
0x18007d32e  mov     byte ptr [rsp+2E0h+var_2A0], 85h
0x18007d333  mov     eax, 221h
0x18007d338  mov     [rbp+1E0h+var_258], ecx
0x18007d33b  mov     [rsp+2E0h+var_288], ax
0x18007d340  lea     rax, aIpnathlpDll148; "@ipnathlp.dll,-148"
0x18007d347  mov     [rsp+2E0h+var_278], rax
0x18007d34c  lea     rax, aIpnathlpDll101_4; "@ipnathlp.dll,-10147"
0x18007d353  mov     [rsp+2E0h+var_270], rax
0x18007d358  lea     rax, [rbp+1E0h+var_90]
0x18007d35f  mov     [rsp+2E0h+var_280], rax
0x18007d364  mov     eax, 3Ah ; ':'
0x18007d369  mov     [rbp+1E0h+var_260], ax
0x18007d36d  sbb     eax, eax
0x18007d36f  neg     eax
0x18007d371  mov     [rbp+1E0h+var_198], ecx
0x18007d374  add     eax, ecx
0x18007d376  mov     [rbp+1E0h+var_16C], cx
0x18007d37a  mov     rcx, [rsp+2E0h+var_298]
0x18007d37f  mov     dword ptr [rsp+2E0h+var_264], eax
0x18007d383  mov     eax, 100h
0x18007d388  mov     word ptr [rsp+2E0h+var_2A0+2], ax
0x18007d38d  lea     rax, [rsp+2E0h+var_2A0]
0x18007d392  mov     [rbp+1E0h+var_250], rax
0x18007d396  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x18007d39d  mov     [rbp+1E0h+var_158], rax
0x18007d3a4  mov     dword ptr [rsp+2E0h+var_268], 7
0x18007d3ac  mov     [rbp+1E0h+var_190], rdi
0x18007d3b0  mov     [rbp+1E0h+var_170], 3
0x18007d3b7  call    cs:__imp_FWAddFirewallRule
0x18007d3bd  test    eax, eax
0x18007d3bf  jz      short loc_18007D3F1
0x18007d3c1  jg      short loc_18007D3C7
0x18007d3c3  mov     ebx, eax
0x18007d3c5  jmp     short loc_18007D3D0
0x18007d3c7  movzx   ebx, ax
0x18007d3ca  or      ebx, 80070000h
0x18007d3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3d7  cmp     rcx, r15
0x18007d3da  jz      short loc_18007D446
0x18007d3dc  test    [rcx+1Ch], esi
0x18007d3df  jz      short loc_18007D446
0x18007d3e1  cmp     byte ptr [rcx+19h], 2
0x18007d3e5  jb      short loc_18007D446
0x18007d3e7  mov     edx, 52h ; 'R'
0x18007d3ec  jmp     loc_18007D2CA
0x18007d3f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d3f8  cmp     rcx, r15
0x18007d3fb  jz      short loc_18007D446
0x18007d3fd  test    [rcx+1Ch], esi
0x18007d400  jz      short loc_18007D446
0x18007d402  cmp     byte ptr [rcx+19h], 5
0x18007d406  jb      short loc_18007D446
0x18007d408  mov     eax, dword ptr [rsp+2E0h+var_268]
0x18007d40c  mov     edx, 53h ; 'S'
0x18007d411  movzx   r9d, [rbp+1E0h+var_260]
0x18007d416  mov     rcx, [rcx+10h]; LoggerHandle
0x18007d41a  mov     dword ptr [rsp+2E0h+var_2A8], eax; char
0x18007d41e  mov     rax, [rsp+2E0h+var_280]
0x18007d423  mov     [rsp+2E0h+var_2B0], rax; __int64
0x18007d428  mov     rax, [rsp+2E0h+var_278]
0x18007d42d  mov     [rsp+2E0h+var_2B8], rax; __int64
0x18007d432  mov     eax, dword ptr [rsp+2E0h+var_264]
0x18007d436  mov     dword ptr [rsp+2E0h+var_2C0], eax; char
0x18007d43a  call    WPP_SF_DdSSd
0x18007d43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d446  mov     rax, [rsp+2E0h+var_298]
0x18007d44b  test    rax, rax
0x18007d44e  jz      short loc_18007D460
0x18007d450  mov     rcx, rax
0x18007d453  call    cs:__imp_FWClosePolicyStore
0x18007d459  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d460  cmp     rcx, r15
0x18007d463  jz      short loc_18007D488
0x18007d465  test    [rcx+1Ch], esi
0x18007d468  jz      short loc_18007D488
0x18007d46a  cmp     byte ptr [rcx+19h], 6
0x18007d46e  jb      short loc_18007D488
0x18007d470  mov     rcx, [rcx+10h]
0x18007d474  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x18007d47b  mov     edx, 54h ; 'T'
0x18007d480  mov     r9d, ebx
0x18007d483  call    WPP_SF_d
0x18007d488  mov     eax, ebx
0x18007d48a  mov     rcx, [rbp+1E0h+var_20]
0x18007d491  xor     rcx, rsp; StackCookie
0x18007d494  call    __security_check_cookie
0x18007d499  lea     r11, [rsp+2E0h+var_10]
0x18007d4a1  mov     rbx, [r11+28h]
0x18007d4a5  mov     rsi, [r11+38h]
0x18007d4a9  mov     rsp, r11
0x18007d4ac  pop     r15
0x18007d4ae  pop     rdi
0x18007d4af  pop     rbp
0x18007d4b0  retn
```
