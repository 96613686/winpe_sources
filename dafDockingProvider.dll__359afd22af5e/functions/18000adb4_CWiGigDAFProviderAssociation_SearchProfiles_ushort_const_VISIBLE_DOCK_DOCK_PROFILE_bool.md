# CWiGigDAFProviderAssociation::SearchProfiles(ushort const *,_VISIBLE_DOCK *,_DOCK_PROFILE *,bool *)

- ea: `0x18000adb4`
- end: `0x18000af2c`
- name: `?SearchProfiles@CWiGigDAFProviderAssociation@@AEAAJPEBGPEAU_VISIBLE_DOCK@@PEAU_DOCK_PROFILE@@PEA_N@Z`
- size: `376`
- prototype: `__int64 __fastcall(struct DockingProviders **this, wchar_t *, struct _VISIBLE_DOCK *, struct _DOCK_PROFILE *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a040`
- `0x18000a810`

## callees

- `0x18000adb4`
- `0x18000c308`
- `0x18000c348`
- `0x18000c398`
- `0x18000d658`
- `0x18000d810`

## string_xrefs

- `0x18000ae7e`: `Complete`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::SearchProfiles(
        struct DockingProviders **this,
        wchar_t *a2,
        struct _VISIBLE_DOCK *a3,
        struct _DOCK_PROFILE *a4,
        bool *a5)
{
  int v9; // ebx
  int v10; // r8d
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const wchar_t *v14; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  v9 = DockingDevnodeHelpers::AepIDToDockProfile(this[334], a2, a4, a5);
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return (unsigned int)v9;
    }
    v12 = 148;
LABEL_10:
    WPP_SF_qD(v11[2], v12, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v9);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = L"Partial";
    if ( !*a5 )
      v14 = (const wchar_t *)L"Complete";
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v14, (__int64)a4);
  }
  v9 = DockingDevnodeHelpers::ConnectedDockToVisibleDock(a4, a3, v10);
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return (unsigned int)v9;
    }
    v12 = 150;
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000adb4  push    rbx
0x18000adb6  push    rbp
0x18000adb7  push    rsi
0x18000adb8  push    rdi
0x18000adb9  push    r12
0x18000adbb  push    r14
0x18000adbd  sub     rsp, 38h
0x18000adc1  mov     rsi, r9
0x18000adc4  mov     r14, r8
0x18000adc7  mov     rbx, rdx
0x18000adca  mov     rdi, rcx
0x18000adcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000add4  lea     r12, WPP_GLOBAL_Control
0x18000addb  cmp     rcx, r12
0x18000adde  jz      short loc_18000AE04
0x18000ade0  cmp     byte ptr [rcx+19h], 4
0x18000ade4  jb      short loc_18000AE04
0x18000ade6  test    byte ptr [rcx+1Ch], 1
0x18000adea  jz      short loc_18000AE04
0x18000adec  mov     rcx, [rcx+10h]
0x18000adf0  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000adf7  mov     edx, 93h
0x18000adfc  mov     r9, rdi
0x18000adff  call    WPP_SF_q
0x18000ae04  mov     rbp, [rsp+68h+arg_20]
0x18000ae0c  mov     r8, rsi; struct _DOCK_PROFILE *
0x18000ae0f  mov     rcx, [rdi+0A70h]; this
0x18000ae16  mov     r9, rbp; bool *
0x18000ae19  mov     rdx, rbx; Str
0x18000ae1c  call    ?AepIDToDockProfile@DockingDevnodeHelpers@@SAJPEAVDockingProviders@@PEBGPEAU_DOCK_PROFILE@@PEA_N@Z; DockingDevnodeHelpers::AepIDToDockProfile(DockingProviders *,ushort const *,_DOCK_PROFILE *,bool *)
0x18000ae21  mov     ebx, eax
0x18000ae23  test    eax, eax
0x18000ae25  jns     short loc_18000AE62
0x18000ae27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae2e  cmp     rcx, r12
0x18000ae31  jz      short loc_18000AE5B
0x18000ae33  cmp     byte ptr [rcx+19h], 4
0x18000ae37  jb      short loc_18000AE5B
0x18000ae39  test    byte ptr [rcx+1Ch], 1
0x18000ae3d  jz      short loc_18000AE5B
0x18000ae3f  mov     edx, 94h
0x18000ae44  mov     rcx, [rcx+10h]
0x18000ae48  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000ae4f  mov     r9, rdi
0x18000ae52  mov     dword ptr [rsp+68h+var_48], ebx
0x18000ae56  call    WPP_SF_qD
0x18000ae5b  mov     eax, ebx
0x18000ae5d  jmp     loc_18000AF1F
0x18000ae62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae69  cmp     rcx, r12
0x18000ae6c  jz      short loc_18000AEB2
0x18000ae6e  cmp     byte ptr [rcx+19h], 3
0x18000ae72  jb      short loc_18000AEB2
0x18000ae74  test    byte ptr [rcx+1Ch], 1
0x18000ae78  jz      short loc_18000AEB2
0x18000ae7a  cmp     byte ptr [rbp+0], 0
0x18000ae7e  lea     rdx, aComplete; "Complete"
0x18000ae85  mov     rcx, [rcx+10h]; LoggerHandle
0x18000ae89  lea     rax, aPartial; "Partial"
0x18000ae90  cmovz   rax, rdx
0x18000ae94  mov     [rsp+68h+var_40], rsi; __int64
0x18000ae99  mov     edx, 95h
0x18000ae9e  mov     [rsp+68h+var_48], rax; __int64
0x18000aea3  mov     r9, rdi
0x18000aea6  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000aead  call    WPP_SF_qSS
0x18000aeb2  mov     rdx, r14; struct _VISIBLE_DOCK *
0x18000aeb5  mov     rcx, rsi; struct _DOCK_PROFILE *
0x18000aeb8  call    ?ConnectedDockToVisibleDock@DockingDevnodeHelpers@@SAJAEBU_DOCK_PROFILE@@PEAU_VISIBLE_DOCK@@@Z; DockingDevnodeHelpers::ConnectedDockToVisibleDock(_DOCK_PROFILE const &,_VISIBLE_DOCK *)
0x18000aebd  mov     ebx, eax
0x18000aebf  test    eax, eax
0x18000aec1  jns     short loc_18000AEE5
0x18000aec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeca  cmp     rcx, r12
0x18000aecd  jz      short loc_18000AE5B
0x18000aecf  cmp     byte ptr [rcx+19h], 4
0x18000aed3  jb      short loc_18000AE5B
0x18000aed5  test    byte ptr [rcx+1Ch], 1
0x18000aed9  jz      short loc_18000AE5B
0x18000aedb  mov     edx, 96h
0x18000aee0  jmp     loc_18000AE44
0x18000aee5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeec  cmp     rcx, r12
0x18000aeef  jz      short loc_18000AF1D
0x18000aef1  cmp     byte ptr [rcx+19h], 4
0x18000aef5  jb      short loc_18000AF1D
0x18000aef7  test    byte ptr [rcx+1Ch], 1
0x18000aefb  jz      short loc_18000AF1D
0x18000aefd  mov     rcx, [rcx+10h]
0x18000af01  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000af08  mov     edx, 97h
0x18000af0d  mov     dword ptr [rsp+68h+var_48], 0
0x18000af15  mov     r9, rdi
0x18000af18  call    WPP_SF_qD
0x18000af1d  xor     eax, eax
0x18000af1f  add     rsp, 38h
0x18000af23  pop     r14
0x18000af25  pop     r12
0x18000af27  pop     rdi
0x18000af28  pop     rsi
0x18000af29  pop     rbp
0x18000af2a  pop     rbx
0x18000af2b  retn
```
