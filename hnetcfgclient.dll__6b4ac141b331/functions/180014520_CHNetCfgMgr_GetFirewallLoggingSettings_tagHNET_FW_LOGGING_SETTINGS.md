# CHNetCfgMgr::GetFirewallLoggingSettings(tagHNET_FW_LOGGING_SETTINGS * *)

- ea: `0x180014520`
- end: `0x180014751`
- name: `?GetFirewallLoggingSettings@CHNetCfgMgr@@UEAAJPEAPEAUtagHNET_FW_LOGGING_SETTINGS@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(CHNetCfgMgr *__hidden this, struct tagHNET_FW_LOGGING_SETTINGS **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000d8ec`
- `0x180014520`
- `0x18002a4f0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001461e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001461e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001470b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001470b`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::GetFirewallLoggingSettings(CHNetCfgMgr *this, struct tagHNET_FW_LOGGING_SETTINGS **a2)
{
  PVOID *v4; // rcx
  bool v5; // zf
  unsigned int v6; // ebx
  __int64 v7; // rdx
  struct tagHNET_FW_LOGGING_SETTINGS *v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // eax
  CHNetCfgMgr *v13; // rcx
  int v14; // eax
  struct IWbemClassObject *v16; // [rsp+50h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)this + 10) == 0;
  v16 = 0;
  if ( v5 )
  {
    v6 = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      {
        WPP_SF_d(v4[2], 117, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
      {
        v7 = 118;
LABEL_45:
        WPP_SF_d(v4[2], v7, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v6);
        return v6;
      }
    }
    return v6;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    if ( v4 == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)v4 + 28) & 8) == 0 || *((_BYTE *)v4 + 25) < 2u )
      goto LABEL_41;
    WPP_SF_d(v4[2], 119, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147500035LL);
    goto LABEL_40;
  }
  v8 = (struct tagHNET_FW_LOGGING_SETTINGS *)CoTaskMemAlloc(0x10u);
  *a2 = v8;
  if ( v8 )
  {
    v12 = RetrieveSingleInstance(*((struct IWbemServices **)this + 10), v9, 0, &v16);
    v6 = v12;
    if ( v12 >= 0 )
    {
      if ( v12 )
        goto LABEL_40;
      v14 = CHNetCfgMgr::CopyLoggingInstanceToStruct(v13, v16, *a2);
      v6 = v14;
      if ( v14 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          122,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          (unsigned int)v14);
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v16->lpVtbl->Release)(v16);
      if ( (v6 & 0x80000000) == 0 )
        goto LABEL_40;
      goto LABEL_37;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 121;
      v11 = (unsigned int)v12;
      goto LABEL_24;
    }
  }
  else
  {
    v6 = -2147024882;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 120;
      v11 = 2147942414LL;
LABEL_24:
      WPP_SF_d(v4[2], v10, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v11);
LABEL_37:
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
LABEL_40:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_41:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    v7 = 123;
    goto LABEL_45;
  }
  return v6;
}

```

## disassembly

```asm
0x180014520  push    rbx
0x180014522  push    rdi
0x180014523  push    r14
0x180014525  push    r15
0x180014527  sub     rsp, 28h
0x18001452b  mov     rdi, rdx
0x18001452e  mov     rbx, rcx
0x180014531  mov     rcx, cs:WPP_GLOBAL_Control
0x180014538  lea     r14, WPP_GLOBAL_Control
0x18001453f  lea     r15, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180014546  cmp     rcx, r14
0x180014549  jz      short loc_18001456F
0x18001454b  test    byte ptr [rcx+1Ch], 8
0x18001454f  jz      short loc_18001456F
0x180014551  cmp     byte ptr [rcx+19h], 6
0x180014555  jb      short loc_18001456F
0x180014557  mov     rcx, [rcx+10h]
0x18001455b  mov     edx, 74h ; 't'
0x180014560  mov     r8, r15
0x180014563  call    WPP_SF_
0x180014568  mov     rcx, cs:WPP_GLOBAL_Control
0x18001456f  cmp     qword ptr [rbx+50h], 0
0x180014574  mov     [rsp+48h+arg_0], 0
0x18001457d  jnz     short loc_1800145DB
0x18001457f  mov     ebx, 80004003h
0x180014584  cmp     rcx, r14
0x180014587  jz      loc_180014744
0x18001458d  test    byte ptr [rcx+1Ch], 8
0x180014591  jz      short loc_1800145B4
0x180014593  cmp     byte ptr [rcx+19h], 2
0x180014597  jb      short loc_1800145B4
0x180014599  mov     rcx, [rcx+10h]
0x18001459d  mov     edx, 75h ; 'u'
0x1800145a2  mov     r9d, ebx
0x1800145a5  mov     r8, r15
0x1800145a8  call    WPP_SF_d
0x1800145ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145b4  cmp     rcx, r14
0x1800145b7  jz      loc_180014744
0x1800145bd  test    byte ptr [rcx+1Ch], 8
0x1800145c1  jz      loc_180014744
0x1800145c7  cmp     byte ptr [rcx+19h], 6
0x1800145cb  jb      loc_180014744
0x1800145d1  mov     edx, 76h ; 'v'
0x1800145d6  jmp     loc_180014735
0x1800145db  test    rdi, rdi
0x1800145de  jnz     short loc_180014619
0x1800145e0  mov     ebx, 80004003h
0x1800145e5  cmp     rcx, r14
0x1800145e8  jz      loc_180014744
0x1800145ee  test    byte ptr [rcx+1Ch], 8
0x1800145f2  jz      loc_18001471F
0x1800145f8  cmp     byte ptr [rcx+19h], 2
0x1800145fc  jb      loc_18001471F
0x180014602  mov     rcx, [rcx+10h]
0x180014606  lea     edx, [rdi+77h]
0x180014609  mov     r9d, ebx
0x18001460c  mov     r8, r15
0x18001460f  call    WPP_SF_d
0x180014614  jmp     loc_180014718
0x180014619  mov     ecx, 10h; cb
0x18001461e  call    cs:__imp_CoTaskMemAlloc
0x180014624  mov     [rdi], rax
0x180014627  test    rax, rax
0x18001462a  jnz     short loc_18001466C
0x18001462c  mov     ebx, 8007000Eh
0x180014631  mov     rcx, cs:WPP_GLOBAL_Control
0x180014638  cmp     rcx, r14
0x18001463b  jz      loc_180014702
0x180014641  test    byte ptr [rcx+1Ch], 8
0x180014645  jz      loc_180014702
0x18001464b  cmp     byte ptr [rcx+19h], 2
0x18001464f  jb      loc_180014702
0x180014655  lea     edx, [rax+78h]
0x180014658  mov     r9d, ebx
0x18001465b  mov     rcx, [rcx+10h]
0x18001465f  mov     r8, r15
0x180014662  call    WPP_SF_d
0x180014667  jmp     loc_1800146FB
0x18001466c  mov     rcx, [rbx+50h]; struct IWbemServices *
0x180014670  lea     r9, [rsp+48h+arg_0]; struct IWbemClassObject **
0x180014675  xor     r8d, r8d; unsigned __int8
0x180014678  call    ?RetrieveSingleInstance@@YAJPEAUIWbemServices@@PEBGEPEAPEAUIWbemClassObject@@@Z; RetrieveSingleInstance(IWbemServices *,ushort const *,uchar,IWbemClassObject * *)
0x18001467d  mov     ebx, eax
0x18001467f  test    eax, eax
0x180014681  jns     short loc_1800146A5
0x180014683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001468a  cmp     rcx, r14
0x18001468d  jz      short loc_180014702
0x18001468f  test    byte ptr [rcx+1Ch], 8
0x180014693  jz      short loc_180014702
0x180014695  cmp     byte ptr [rcx+19h], 2
0x180014699  jb      short loc_180014702
0x18001469b  mov     edx, 79h ; 'y'
0x1800146a0  mov     r9d, eax
0x1800146a3  jmp     short loc_18001465B
0x1800146a5  jnz     short loc_180014718
0x1800146a7  mov     r8, [rdi]; struct tagHNET_FW_LOGGING_SETTINGS *
0x1800146aa  mov     rdx, [rsp+48h+arg_0]; struct IWbemClassObject *
0x1800146af  call    ?CopyLoggingInstanceToStruct@CHNetCfgMgr@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_FW_LOGGING_SETTINGS@@@Z; CHNetCfgMgr::CopyLoggingInstanceToStruct(IWbemClassObject *,tagHNET_FW_LOGGING_SETTINGS *)
0x1800146b4  mov     ebx, eax
0x1800146b6  test    eax, eax
0x1800146b8  jns     short loc_1800146E6
0x1800146ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c1  cmp     rcx, r14
0x1800146c4  jz      short loc_1800146E6
0x1800146c6  test    byte ptr [rcx+1Ch], 8
0x1800146ca  jz      short loc_1800146E6
0x1800146cc  cmp     byte ptr [rcx+19h], 2
0x1800146d0  jb      short loc_1800146E6
0x1800146d2  mov     rcx, [rcx+10h]
0x1800146d6  mov     edx, 7Ah ; 'z'
0x1800146db  mov     r9d, eax
0x1800146de  mov     r8, r15
0x1800146e1  call    WPP_SF_d
0x1800146e6  mov     rcx, [rsp+48h+arg_0]
0x1800146eb  mov     rax, [rcx]
0x1800146ee  mov     rax, [rax+10h]
0x1800146f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146f7  test    ebx, ebx
0x1800146f9  jns     short loc_180014718
0x1800146fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014702  cmp     qword ptr [rdi], 0
0x180014706  jz      short loc_18001471F
0x180014708  mov     rcx, [rdi]; pv
0x18001470b  call    cs:__imp_CoTaskMemFree
0x180014711  mov     qword ptr [rdi], 0
0x180014718  mov     rcx, cs:WPP_GLOBAL_Control
0x18001471f  cmp     rcx, r14
0x180014722  jz      short loc_180014744
0x180014724  test    byte ptr [rcx+1Ch], 8
0x180014728  jz      short loc_180014744
0x18001472a  cmp     byte ptr [rcx+19h], 6
0x18001472e  jb      short loc_180014744
0x180014730  mov     edx, 7Bh ; '{'
0x180014735  mov     rcx, [rcx+10h]
0x180014739  mov     r9d, ebx
0x18001473c  mov     r8, r15
0x18001473f  call    WPP_SF_d
0x180014744  mov     eax, ebx
0x180014746  add     rsp, 28h
0x18001474a  pop     r15
0x18001474c  pop     r14
0x18001474e  pop     rdi
0x18001474f  pop     rbx
0x180014750  retn
```
