# NatAddICMPv6RuleToGroupExceptionForSharingEx(_GUID const *,ushort const *,ushort,uchar,_GUID,eWFP_IP_TYPE,int)

- ea: `0x18008359c`
- end: `0x1800838ac`
- name: `?NatAddICMPv6RuleToGroupExceptionForSharingEx@@YAJPEBU_GUID@@PEBGGEU1@W4eWFP_IP_TYPE@@H@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800326d4`

## callees

- `0x18000d090`
- `0x180032f70`
- `0x180051f30`
- `0x180052bf4`
- `0x18008359c`
- `0x1800838b4`
- `0x180083c00`

## import_xrefs

- `FirewallAPI!FWClosePolicyStore` at `0x180083847`
- `FirewallAPI!FWClosePolicyStore` at `0x180083847`
- `FirewallAPI!FWOpenPolicyStore` at `0x180083671`
- `FirewallAPI!FWOpenPolicyStore` at `0x180083671`
- `FirewallAPI!FWAddFirewallRule` at `0x1800837a5`
- `FirewallAPI!FWAddFirewallRule` at `0x1800837a5`

## string_xrefs

- `0x18008372e`: `@ipnathlp.dll,-148`
- `0x18008373a`: `@ipnathlp.dll,-10147`
- `0x180083784`: `@ipnathlp.dll,-140`

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
0x18008359c  mov     [rsp-8+arg_8], rbx
0x1800835a1  mov     [rsp-8+arg_18], rsi
0x1800835a6  push    rbp
0x1800835a7  push    rdi
0x1800835a8  push    r15
0x1800835aa  lea     rbp, [rsp-1D0h]
0x1800835b2  sub     rsp, 2D0h
0x1800835b9  mov     rax, cs:__security_cookie
0x1800835c0  xor     rax, rsp
0x1800835c3  mov     [rbp+1E0h+var_20], rax
0x1800835ca  mov     r10, [rbp+1E0h+arg_20]
0x1800835d1  mov     rdi, rcx
0x1800835d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800835db  lea     r15, WPP_GLOBAL_Control
0x1800835e2  mov     esi, 200h
0x1800835e7  cmp     rcx, r15
0x1800835ea  jz      short loc_18008361B
0x1800835ec  test    [rcx+1Ch], esi
0x1800835ef  jz      short loc_18008361B
0x1800835f1  cmp     byte ptr [rcx+19h], 6
0x1800835f5  jb      short loc_18008361B
0x1800835f7  mov     eax, [rbp+1E0h+arg_28]
0x1800835fd  mov     rcx, [rcx+10h]
0x180083601  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x180083605  movzx   edx, r9b
0x180083609  mov     [rsp+2E0h+var_2B8], r10
0x18008360e  movzx   r9d, r8w
0x180083612  mov     dword ptr [rsp+2E0h+var_2C0], edx
0x180083616  call    WPP_SF_dd_guid_d
0x18008361b  xor     edx, edx; Val
0x18008361d  mov     [rsp+2E0h+var_298], 0
0x180083626  mov     r8d, 1F8h; Size
0x18008362c  lea     rcx, [rsp+2E0h+var_290]; void *
0x180083631  call    memset_0
0x180083636  xor     edx, edx; Val
0x180083638  mov     [rsp+2E0h+var_2A0], 0
0x180083640  lea     rcx, [rbp+1E0h+var_90]; void *
0x180083647  lea     r8d, [rdx+64h]; Size
0x18008364b  call    memset_0
0x180083650  xor     edx, edx
0x180083652  lea     rax, [rsp+2E0h+var_298]
0x180083657  mov     [rsp+2E0h+var_2B8], rax
0x18008365c  mov     ecx, 221h
0x180083661  mov     dword ptr [rsp+2E0h+var_2C0], 0
0x180083669  lea     r9d, [rdx+2]
0x18008366d  lea     r8d, [rdx+5]
0x180083671  call    cs:__imp_FWOpenPolicyStore
0x180083678  nop     dword ptr [rax+rax+00h]
0x18008367d  test    eax, eax
0x18008367f  jz      short loc_1800836D0
0x180083681  jg      short loc_180083687
0x180083683  mov     ebx, eax
0x180083685  jmp     short loc_180083690
0x180083687  movzx   ebx, ax
0x18008368a  or      ebx, 80070000h
0x180083690  mov     rcx, cs:WPP_GLOBAL_Control
0x180083697  cmp     rcx, r15
0x18008369a  jz      loc_18008383A
0x1800836a0  test    [rcx+1Ch], esi
0x1800836a3  jz      loc_18008383A
0x1800836a9  cmp     byte ptr [rcx+19h], 2
0x1800836ad  jb      loc_18008383A
0x1800836b3  mov     edx, 50h ; 'P'
0x1800836b8  mov     rcx, [rcx+10h]
0x1800836bc  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x1800836c3  mov     r9d, eax
0x1800836c6  call    WPP_SF_d
0x1800836cb  jmp     loc_180083833
0x1800836d0  lea     rcx, [rbp+1E0h+var_90]; unsigned __int16 *
0x1800836d7  call    ?NatGenerateGuid@@YAJPEAG_K@Z; NatGenerateGuid(ushort *,unsigned __int64)
0x1800836dc  mov     ebx, eax
0x1800836de  test    eax, eax
0x1800836e0  jns     short loc_18008370C
0x1800836e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800836e9  cmp     rcx, r15
0x1800836ec  jz      loc_18008383A
0x1800836f2  test    [rcx+1Ch], esi
0x1800836f5  jz      loc_18008383A
0x1800836fb  cmp     byte ptr [rcx+19h], 2
0x1800836ff  jb      loc_18008383A
0x180083705  mov     edx, 51h ; 'Q'
0x18008370a  jmp     short loc_1800836B8
0x18008370c  neg     [rbp+1E0h+arg_30]
0x180083712  lea     rdx, [rsp+2E0h+var_290]
0x180083717  mov     ecx, 1
0x18008371c  mov     byte ptr [rsp+2E0h+var_2A0], 85h
0x180083721  mov     eax, 221h
0x180083726  mov     [rbp+1E0h+var_258], ecx
0x180083729  mov     [rsp+2E0h+var_288], ax
0x18008372e  lea     rax, aIpnathlpDll148; "@ipnathlp.dll,-148"
0x180083735  mov     [rsp+2E0h+var_278], rax
0x18008373a  lea     rax, aIpnathlpDll101_4; "@ipnathlp.dll,-10147"
0x180083741  mov     [rsp+2E0h+var_270], rax
0x180083746  lea     rax, [rbp+1E0h+var_90]
0x18008374d  mov     [rsp+2E0h+var_280], rax
0x180083752  mov     eax, 3Ah ; ':'
0x180083757  mov     [rbp+1E0h+var_260], ax
0x18008375b  sbb     eax, eax
0x18008375d  neg     eax
0x18008375f  mov     [rbp+1E0h+var_198], ecx
0x180083762  add     eax, ecx
0x180083764  mov     [rbp+1E0h+var_16C], cx
0x180083768  mov     rcx, [rsp+2E0h+var_298]
0x18008376d  mov     dword ptr [rsp+2E0h+var_264], eax
0x180083771  mov     eax, 100h
0x180083776  mov     word ptr [rsp+2E0h+var_2A0+2], ax
0x18008377b  lea     rax, [rsp+2E0h+var_2A0]
0x180083780  mov     [rbp+1E0h+var_250], rax
0x180083784  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x18008378b  mov     [rbp+1E0h+var_158], rax
0x180083792  mov     dword ptr [rsp+2E0h+var_268], 7
0x18008379a  mov     [rbp+1E0h+var_190], rdi
0x18008379e  mov     [rbp+1E0h+var_170], 3
0x1800837a5  call    cs:__imp_FWAddFirewallRule
0x1800837ac  nop     dword ptr [rax+rax+00h]
0x1800837b1  test    eax, eax
0x1800837b3  jz      short loc_1800837E5
0x1800837b5  jg      short loc_1800837BB
0x1800837b7  mov     ebx, eax
0x1800837b9  jmp     short loc_1800837C4
0x1800837bb  movzx   ebx, ax
0x1800837be  or      ebx, 80070000h
0x1800837c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800837cb  cmp     rcx, r15
0x1800837ce  jz      short loc_18008383A
0x1800837d0  test    [rcx+1Ch], esi
0x1800837d3  jz      short loc_18008383A
0x1800837d5  cmp     byte ptr [rcx+19h], 2
0x1800837d9  jb      short loc_18008383A
0x1800837db  mov     edx, 52h ; 'R'
0x1800837e0  jmp     loc_1800836B8
0x1800837e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800837ec  cmp     rcx, r15
0x1800837ef  jz      short loc_18008383A
0x1800837f1  test    [rcx+1Ch], esi
0x1800837f4  jz      short loc_18008383A
0x1800837f6  cmp     byte ptr [rcx+19h], 5
0x1800837fa  jb      short loc_18008383A
0x1800837fc  mov     eax, dword ptr [rsp+2E0h+var_268]
0x180083800  mov     edx, 53h ; 'S'
0x180083805  movzx   r9d, [rbp+1E0h+var_260]
0x18008380a  mov     rcx, [rcx+10h]; LoggerHandle
0x18008380e  mov     dword ptr [rsp+2E0h+var_2A8], eax; char
0x180083812  mov     rax, [rsp+2E0h+var_280]
0x180083817  mov     [rsp+2E0h+var_2B0], rax; __int64
0x18008381c  mov     rax, [rsp+2E0h+var_278]
0x180083821  mov     [rsp+2E0h+var_2B8], rax; __int64
0x180083826  mov     eax, dword ptr [rsp+2E0h+var_264]
0x18008382a  mov     dword ptr [rsp+2E0h+var_2C0], eax; char
0x18008382e  call    WPP_SF_DdSSd
0x180083833  mov     rcx, cs:WPP_GLOBAL_Control
0x18008383a  mov     rax, [rsp+2E0h+var_298]
0x18008383f  test    rax, rax
0x180083842  jz      short loc_18008385A
0x180083844  mov     rcx, rax
0x180083847  call    cs:__imp_FWClosePolicyStore
0x18008384e  nop     dword ptr [rax+rax+00h]
0x180083853  mov     rcx, cs:WPP_GLOBAL_Control
0x18008385a  cmp     rcx, r15
0x18008385d  jz      short loc_180083882
0x18008385f  test    [rcx+1Ch], esi
0x180083862  jz      short loc_180083882
0x180083864  cmp     byte ptr [rcx+19h], 6
0x180083868  jb      short loc_180083882
0x18008386a  mov     rcx, [rcx+10h]
0x18008386e  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x180083875  mov     edx, 54h ; 'T'
0x18008387a  mov     r9d, ebx
0x18008387d  call    WPP_SF_d
0x180083882  mov     eax, ebx
0x180083884  mov     rcx, [rbp+1E0h+var_20]
0x18008388b  xor     rcx, rsp; StackCookie
0x18008388e  call    __security_check_cookie
0x180083893  lea     r11, [rsp+2E0h+var_10]
0x18008389b  mov     rbx, [r11+28h]
0x18008389f  mov     rsi, [r11+38h]
0x1800838a3  mov     rsp, r11
0x1800838a6  pop     r15
0x1800838a8  pop     rdi
0x1800838a9  pop     rbp
0x1800838aa  retn
```
