# CHNetConn::GetIcmpSettings(tagHNET_FW_ICMP_SETTINGS * *)

- ea: `0x18001c450`
- end: `0x18001c614`
- name: `?GetIcmpSettings@CHNetConn@@UEAAJPEAPEAUtagHNET_FW_ICMP_SETTINGS@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct tagHNET_FW_ICMP_SETTINGS **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180018cd0`
- `0x18001c450`
- `0x18001c61c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c4b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c4b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5ce`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetIcmpSettings(CHNetConn *this, struct tagHNET_FW_ICMP_SETTINGS **a2)
{
  PVOID *v4; // rcx
  struct tagHNET_FW_ICMP_SETTINGS *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int IcmpSettingsInstance; // eax
  CHNetConn *v9; // rcx
  __int64 v10; // r9
  int v11; // eax
  struct IWbemClassObject *v13; // [rsp+58h] [rbp+10h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = 0;
  if ( a2 )
  {
    v5 = (struct tagHNET_FW_ICMP_SETTINGS *)CoTaskMemAlloc(9u);
    *a2 = v5;
    if ( v5 )
    {
      IcmpSettingsInstance = CHNetConn::GetIcmpSettingsInstance(this, &v13);
      v6 = IcmpSettingsInstance;
      if ( IcmpSettingsInstance >= 0 )
      {
        if ( IcmpSettingsInstance )
          goto LABEL_33;
        v11 = CHNetConn::CopyIcmpSettingsInstanceToStruct(v9, v13, *a2);
        v6 = v11;
        if ( v11 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            173,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v11);
        }
        ((void (__fastcall *)(struct IWbemClassObject *))v13->lpVtbl->Release)(v13);
        if ( (v6 & 0x80000000) == 0 )
          goto LABEL_33;
        goto LABEL_30;
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 172;
        v10 = (unsigned int)IcmpSettingsInstance;
LABEL_29:
        WPP_SF_d(v4[2], v7, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v10);
LABEL_30:
        v4 = (PVOID *)WPP_GLOBAL_Control;
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
        v7 = 170;
LABEL_28:
        v10 = v6;
        goto LABEL_29;
      }
    }
  }
  else
  {
    v6 = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      v7 = 171;
      goto LABEL_28;
    }
  }
  if ( *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
LABEL_33:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 174, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001c450  push    rbx
0x18001c452  push    rdi
0x18001c453  push    r14
0x18001c455  push    r15
0x18001c457  sub     rsp, 28h
0x18001c45b  mov     rdi, rdx
0x18001c45e  mov     rbx, rcx
0x18001c461  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c468  lea     r14, WPP_GLOBAL_Control
0x18001c46f  lea     r15, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c476  cmp     rcx, r14
0x18001c479  jz      short loc_18001C49F
0x18001c47b  test    byte ptr [rcx+1Ch], 8
0x18001c47f  jz      short loc_18001C49F
0x18001c481  cmp     byte ptr [rcx+19h], 6
0x18001c485  jb      short loc_18001C49F
0x18001c487  mov     rcx, [rcx+10h]
0x18001c48b  mov     edx, 0A9h
0x18001c490  mov     r8, r15
0x18001c493  call    WPP_SF_
0x18001c498  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c49f  mov     [rsp+48h+arg_8], 0
0x18001c4a8  test    rdi, rdi
0x18001c4ab  jz      loc_18001C594
0x18001c4b1  mov     ecx, 9; cb
0x18001c4b6  call    cs:__imp_CoTaskMemAlloc
0x18001c4bc  mov     [rdi], rax
0x18001c4bf  test    rax, rax
0x18001c4c2  jnz     short loc_18001C4F7
0x18001c4c4  mov     ebx, 8007000Eh
0x18001c4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4d0  cmp     rcx, r14
0x18001c4d3  jz      loc_18001C5C5
0x18001c4d9  test    byte ptr [rcx+1Ch], 8
0x18001c4dd  jz      loc_18001C5C5
0x18001c4e3  cmp     byte ptr [rcx+19h], 2
0x18001c4e7  jb      loc_18001C5C5
0x18001c4ed  mov     edx, 0AAh
0x18001c4f2  jmp     loc_18001C5AF
0x18001c4f7  lea     rdx, [rsp+48h+arg_8]; struct IWbemClassObject **
0x18001c4fc  mov     rcx, rbx; this
0x18001c4ff  call    ?GetIcmpSettingsInstance@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetIcmpSettingsInstance(IWbemClassObject * *)
0x18001c504  mov     ebx, eax
0x18001c506  test    eax, eax
0x18001c508  jns     short loc_18001C538
0x18001c50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c511  cmp     rcx, r14
0x18001c514  jz      loc_18001C5C5
0x18001c51a  test    byte ptr [rcx+1Ch], 8
0x18001c51e  jz      loc_18001C5C5
0x18001c524  cmp     byte ptr [rcx+19h], 2
0x18001c528  jb      loc_18001C5C5
0x18001c52e  mov     edx, 0ACh
0x18001c533  mov     r9d, eax
0x18001c536  jmp     short loc_18001C5B2
0x18001c538  jnz     loc_18001C5DB
0x18001c53e  mov     r8, [rdi]; struct tagHNET_FW_ICMP_SETTINGS *
0x18001c541  mov     rdx, [rsp+48h+arg_8]; struct IWbemClassObject *
0x18001c546  call    ?CopyIcmpSettingsInstanceToStruct@CHNetConn@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_FW_ICMP_SETTINGS@@@Z; CHNetConn::CopyIcmpSettingsInstanceToStruct(IWbemClassObject *,tagHNET_FW_ICMP_SETTINGS *)
0x18001c54b  mov     ebx, eax
0x18001c54d  test    eax, eax
0x18001c54f  jns     short loc_18001C57D
0x18001c551  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c558  cmp     rcx, r14
0x18001c55b  jz      short loc_18001C57D
0x18001c55d  test    byte ptr [rcx+1Ch], 8
0x18001c561  jz      short loc_18001C57D
0x18001c563  cmp     byte ptr [rcx+19h], 2
0x18001c567  jb      short loc_18001C57D
0x18001c569  mov     rcx, [rcx+10h]
0x18001c56d  mov     edx, 0ADh
0x18001c572  mov     r9d, eax
0x18001c575  mov     r8, r15
0x18001c578  call    WPP_SF_d
0x18001c57d  mov     rcx, [rsp+48h+arg_8]
0x18001c582  mov     rax, [rcx]
0x18001c585  mov     rax, [rax+10h]
0x18001c589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c58e  test    ebx, ebx
0x18001c590  js      short loc_18001C5BE
0x18001c592  jmp     short loc_18001C5DB
0x18001c594  mov     ebx, 80004003h
0x18001c599  cmp     rcx, r14
0x18001c59c  jz      short loc_18001C5C5
0x18001c59e  test    byte ptr [rcx+1Ch], 8
0x18001c5a2  jz      short loc_18001C5C5
0x18001c5a4  cmp     byte ptr [rcx+19h], 2
0x18001c5a8  jb      short loc_18001C5C5
0x18001c5aa  mov     edx, 0ABh
0x18001c5af  mov     r9d, ebx
0x18001c5b2  mov     rcx, [rcx+10h]
0x18001c5b6  mov     r8, r15
0x18001c5b9  call    WPP_SF_d
0x18001c5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5c5  cmp     qword ptr [rdi], 0
0x18001c5c9  jz      short loc_18001C5E2
0x18001c5cb  mov     rcx, [rdi]; pv
0x18001c5ce  call    cs:__imp_CoTaskMemFree
0x18001c5d4  mov     qword ptr [rdi], 0
0x18001c5db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5e2  cmp     rcx, r14
0x18001c5e5  jz      short loc_18001C607
0x18001c5e7  test    byte ptr [rcx+1Ch], 8
0x18001c5eb  jz      short loc_18001C607
0x18001c5ed  cmp     byte ptr [rcx+19h], 6
0x18001c5f1  jb      short loc_18001C607
0x18001c5f3  mov     rcx, [rcx+10h]
0x18001c5f7  mov     edx, 0AEh
0x18001c5fc  mov     r9d, ebx
0x18001c5ff  mov     r8, r15
0x18001c602  call    WPP_SF_d
0x18001c607  mov     eax, ebx
0x18001c609  add     rsp, 28h
0x18001c60d  pop     r15
0x18001c60f  pop     r14
0x18001c611  pop     rdi
0x18001c612  pop     rbx
0x18001c613  retn
```
