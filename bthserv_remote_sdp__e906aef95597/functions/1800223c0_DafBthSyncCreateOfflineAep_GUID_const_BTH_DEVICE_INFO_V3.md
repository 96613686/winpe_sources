# DafBthSyncCreateOfflineAep(_GUID const *,_BTH_DEVICE_INFO_V3 *)

- ea: `0x1800223c0`
- end: `0x1800226b4`
- name: `?DafBthSyncCreateOfflineAep@@YAJPEBU_GUID@@PEAU_BTH_DEVICE_INFO_V3@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _BTH_DEVICE_INFO_V3 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022a74`

## callees

- `0x1800017a0`
- `0x1800223c0`
- `0x18002354c`
- `0x180023628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022575`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800225dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022575`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800225dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022444`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022444`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800225a9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800225a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022641`
- `deviceassociation!DafMemFree` at `0x18002261e`
- `deviceassociation!DafMemFree` at `0x18002261e`
- `deviceassociation!DafStartFinalize` at `0x1800225c4`
- `deviceassociation!DafStartFinalize` at `0x1800225c4`
- `deviceassociation!DafSelectCeremony` at `0x180022593`
- `deviceassociation!DafSelectCeremony` at `0x180022593`
- `deviceassociation!DafStartEnumCeremonies` at `0x18002255a`
- `deviceassociation!DafStartEnumCeremonies` at `0x18002255a`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x180022507`
- `deviceassociation!DafCreateAssociationContextFromOobBlob` at `0x180022507`
- `deviceassociation!DafCloseAssociationContext` at `0x1800225fb`
- `deviceassociation!DafCloseAssociationContext` at `0x1800225fb`

## pseudocode

```c
__int64 __fastcall DafBthSyncCreateOfflineAep(const struct _GUID *a1, struct _BTH_DEVICE_INFO_V3 *a2)
{
  signed int LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // r9d
  signed int started; // ebx
  _BYTE *v9; // rcx
  int v10; // eax
  int v11; // eax
  bool v12; // cf
  HANDLE hHandle; // [rsp+48h] [rbp-1h] BYREF
  __int64 v15; // [rsp+50h] [rbp+7h]
  __int64 v16; // [rsp+58h] [rbp+Fh]
  __int128 v17; // [rsp+60h] [rbp+17h] BYREF
  __int128 v18; // [rsp+70h] [rbp+27h]
  int v19; // [rsp+80h] [rbp+37h]

  v19 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( hHandle )
  {
    WORD2(v17) = 32;
    *((_QWORD *)&v18 + 1) = *((_QWORD *)a2 + 1);
    DWORD1(v18) = *(_DWORD *)a2;
    v19 = *((_DWORD *)a2 + 4);
    *(_DWORD *)((char *)&v17 + 6) = 0;
    WORD5(v17) = 0;
    HIDWORD(v17) = 458519;
    LODWORD(v18) = 2;
    v10 = DafCreateAssociationContextFromOobBlob(a1, 36, &v17);
    started = v10;
    if ( v10 >= 0 )
    {
      started = DafStartEnumCeremonies(0, 0, 0, DafBthSyncEnumCeremoniesCompleteCallback, &hHandle);
      if ( started >= 0 )
      {
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        started = v15;
        if ( (int)v15 >= 0 )
        {
          started = DafSelectCeremony(0, &DAF_Ceremony_JustWorks);
          if ( started >= 0 )
          {
            ResetEvent(hHandle);
            started = DafStartFinalize(0, &DafBthSyncFinalizeCompleteCallback, &hHandle);
            if ( started >= 0 )
              WaitForSingleObject(hHandle, 0xFFFFFFFF);
          }
        }
      }
      goto LABEL_19;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids,
        v7,
        v10);
      goto LABEL_19;
    }
  }
  else
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids,
        v7,
        started);
LABEL_19:
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( v16 )
  {
    DafMemFree(v16, v5, v6);
    v9 = WPP_GLOBAL_Control;
    v16 = 0;
  }
  if ( hHandle )
  {
    CloseHandle(hHandle);
    v9 = WPP_GLOBAL_Control;
    hHandle = 0;
  }
  v11 = 0;
  if ( started )
    v12 = v9[25] < 2u;
  else
    v12 = v9[25] < 5u;
  if ( v9 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v11) = !v12;
    if ( v11 )
      WPP_SF_sd(*((_QWORD *)v9 + 2), 51, (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids, v7, started);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800223c0  mov     [rsp-8+arg_10], rbx
0x1800223c5  mov     [rsp-8+arg_18], rsi
0x1800223ca  push    rbp
0x1800223cb  push    rdi
0x1800223cc  push    r15
0x1800223ce  lea     rbp, [rsp-47h]
0x1800223d3  sub     rsp, 90h
0x1800223da  mov     rax, cs:__security_cookie
0x1800223e1  xor     rax, rsp
0x1800223e4  mov     [rbp+57h+var_18], rax
0x1800223e8  xor     eax, eax
0x1800223ea  xorps   xmm0, xmm0
0x1800223ed  xor     esi, esi
0x1800223ef  mov     [rbp+57h+var_20], eax
0x1800223f2  mov     [rbp+57h+var_48], rsi
0x1800223f6  mov     rbx, rdx
0x1800223f9  mov     [rbp+57h+var_60], rsi
0x1800223fd  mov     rdi, rcx
0x180022400  mov     [rbp+57h+var_50], rsi
0x180022404  movups  [rbp+57h+var_40], xmm0
0x180022408  movups  [rbp+57h+var_30], xmm0
0x18002240c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022413  lea     r15, WPP_GLOBAL_Control
0x18002241a  cmp     rcx, r15
0x18002241d  jz      short loc_180022438
0x18002241f  cmp     byte ptr [rcx+19h], 5
0x180022423  jb      short loc_180022438
0x180022425  mov     rcx, [rcx+10h]
0x180022429  lea     edx, [rax+30h]
0x18002242c  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022433  call    WPP_SF_s
0x180022438  xor     r9d, r9d; lpName
0x18002243b  xor     r8d, r8d; bInitialState
0x18002243e  xor     ecx, ecx; lpEventAttributes
0x180022440  lea     edx, [r9+1]; bManualReset
0x180022444  call    cs:__imp_CreateEventW
0x18002244b  nop     dword ptr [rax+rax+00h]
0x180022450  mov     [rbp+57h+hHandle], rax
0x180022454  test    rax, rax
0x180022457  jnz     short loc_1800224AC
0x180022459  call    cs:__imp_GetLastError
0x180022460  nop     dword ptr [rax+rax+00h]
0x180022465  mov     ebx, eax
0x180022467  test    eax, eax
0x180022469  jle     short loc_180022474
0x18002246b  movzx   ebx, ax
0x18002246e  or      ebx, 80070000h
0x180022474  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247b  cmp     rcx, r15
0x18002247e  jz      loc_1800225EF
0x180022484  cmp     byte ptr [rcx+19h], 2
0x180022488  jb      loc_1800225EF
0x18002248e  mov     edx, 31h ; '1'
0x180022493  mov     dword ptr [rsp+0A0h+var_80], ebx
0x180022497  mov     rcx, [rcx+10h]
0x18002249b  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x1800224a2  call    WPP_SF_sd
0x1800224a7  jmp     loc_1800225E8
0x1800224ac  mov     [rsp+0A0h+var_68], rsi
0x1800224b1  lea     r8, [rbp+57h+var_40]
0x1800224b5  mov     eax, 20h ; ' '
0x1800224ba  mov     [rsp+0A0h+var_70], rsi
0x1800224bf  mov     word ptr [rbp+57h+var_40+4], ax
0x1800224c3  xor     r9d, r9d
0x1800224c6  mov     rax, [rbx+8]
0x1800224ca  mov     rcx, rdi
0x1800224cd  mov     qword ptr [rbp+57h+var_30+8], rax
0x1800224d1  mov     eax, [rbx]
0x1800224d3  mov     dword ptr [rbp+57h+var_30+4], eax
0x1800224d6  lea     edx, [r9+24h]
0x1800224da  mov     eax, [rbx+10h]
0x1800224dd  mov     [rbp+57h+var_20], eax
0x1800224e0  lea     rax, [rbp+57h+var_60]
0x1800224e4  mov     [rsp+0A0h+var_78], rax
0x1800224e9  lea     rax, [rbp+57h+var_48]
0x1800224ed  mov     [rsp+0A0h+var_80], rax
0x1800224f2  mov     dword ptr [rbp+57h+var_40+6], esi
0x1800224f5  mov     word ptr [rbp+57h+var_40+0Ah], si
0x1800224f9  mov     dword ptr [rbp+57h+var_40+0Ch], 6FF17h
0x180022500  mov     dword ptr [rbp+57h+var_30], 2
0x180022507  call    cs:__imp_DafCreateAssociationContextFromOobBlob
0x18002250e  nop     dword ptr [rax+rax+00h]
0x180022513  mov     ebx, eax
0x180022515  test    eax, eax
0x180022517  jns     short loc_180022541
0x180022519  mov     rcx, cs:WPP_GLOBAL_Control
0x180022520  cmp     rcx, r15
0x180022523  jz      loc_1800225EF
0x180022529  cmp     byte ptr [rcx+19h], 2
0x18002252d  jb      loc_1800225EF
0x180022533  mov     edx, 32h ; '2'
0x180022538  mov     dword ptr [rsp+0A0h+var_80], eax
0x18002253c  jmp     loc_180022497
0x180022541  mov     rcx, [rbp+57h+var_60]
0x180022545  lea     rax, [rbp+57h+hHandle]
0x180022549  lea     r9, ?DafBthSyncEnumCeremoniesCompleteCallback@@YAXKPEBU_CEREMONY@@PEAXJ@Z; DafBthSyncEnumCeremoniesCompleteCallback(ulong,_CEREMONY const *,void *,long)
0x180022550  mov     [rsp+0A0h+var_80], rax
0x180022555  xor     r8d, r8d
0x180022558  xor     edx, edx
0x18002255a  call    cs:__imp_DafStartEnumCeremonies
0x180022561  nop     dword ptr [rax+rax+00h]
0x180022566  mov     ebx, eax
0x180022568  test    eax, eax
0x18002256a  js      short loc_1800225E8
0x18002256c  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180022570  or      edi, 0FFFFFFFFh
0x180022573  mov     edx, edi; dwMilliseconds
0x180022575  call    cs:__imp_WaitForSingleObject
0x18002257c  nop     dword ptr [rax+rax+00h]
0x180022581  mov     ebx, dword ptr [rbp+57h+var_50]
0x180022584  test    ebx, ebx
0x180022586  js      short loc_1800225E8
0x180022588  mov     rcx, [rbp+57h+var_60]
0x18002258c  lea     rdx, DAF_Ceremony_JustWorks
0x180022593  call    cs:__imp_DafSelectCeremony
0x18002259a  nop     dword ptr [rax+rax+00h]
0x18002259f  mov     ebx, eax
0x1800225a1  test    eax, eax
0x1800225a3  js      short loc_1800225E8
0x1800225a5  mov     rcx, [rbp+57h+hHandle]; hEvent
0x1800225a9  call    cs:__imp_ResetEvent
0x1800225b0  nop     dword ptr [rax+rax+00h]
0x1800225b5  mov     rcx, [rbp+57h+var_60]
0x1800225b9  lea     r8, [rbp+57h+hHandle]
0x1800225bd  lea     rdx, ?DafBthSyncFinalizeCompleteCallback@@YAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; DafBthSyncFinalizeCompleteCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x1800225c4  call    cs:__imp_DafStartFinalize
0x1800225cb  nop     dword ptr [rax+rax+00h]
0x1800225d0  mov     ebx, eax
0x1800225d2  test    eax, eax
0x1800225d4  js      short loc_1800225E8
0x1800225d6  mov     rcx, [rbp+57h+hHandle]; hHandle
0x1800225da  mov     edx, edi; dwMilliseconds
0x1800225dc  call    cs:__imp_WaitForSingleObject
0x1800225e3  nop     dword ptr [rax+rax+00h]
0x1800225e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225ef  mov     rax, [rbp+57h+var_60]
0x1800225f3  test    rax, rax
0x1800225f6  jz      short loc_180022612
0x1800225f8  mov     rcx, rax
0x1800225fb  call    cs:__imp_DafCloseAssociationContext
0x180022602  nop     dword ptr [rax+rax+00h]
0x180022607  mov     rcx, cs:WPP_GLOBAL_Control
0x18002260e  mov     [rbp+57h+var_60], rsi
0x180022612  mov     rax, [rbp+57h+var_48]
0x180022616  test    rax, rax
0x180022619  jz      short loc_180022635
0x18002261b  mov     rcx, rax
0x18002261e  call    cs:__imp_DafMemFree
0x180022625  nop     dword ptr [rax+rax+00h]
0x18002262a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022631  mov     [rbp+57h+var_48], rsi
0x180022635  mov     rax, [rbp+57h+hHandle]
0x180022639  test    rax, rax
0x18002263c  jz      short loc_180022658
0x18002263e  mov     rcx, rax; hObject
0x180022641  call    cs:__imp_CloseHandle
0x180022648  nop     dword ptr [rax+rax+00h]
0x18002264d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022654  mov     [rbp+57h+hHandle], rsi
0x180022658  mov     eax, esi
0x18002265a  test    ebx, ebx
0x18002265c  jnz     short loc_180022664
0x18002265e  cmp     byte ptr [rcx+19h], 5
0x180022662  jmp     short loc_180022668
0x180022664  cmp     byte ptr [rcx+19h], 2
0x180022668  setnb   al
0x18002266b  cmp     rcx, r15
0x18002266e  jz      short loc_18002268D
0x180022670  test    eax, eax
0x180022672  jz      short loc_18002268D
0x180022674  mov     rcx, [rcx+10h]
0x180022678  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x18002267f  mov     edx, 33h ; '3'
0x180022684  mov     dword ptr [rsp+0A0h+var_80], ebx
0x180022688  call    WPP_SF_sd
0x18002268d  mov     eax, ebx
0x18002268f  mov     rcx, [rbp+57h+var_18]
0x180022693  xor     rcx, rsp; StackCookie
0x180022696  call    __security_check_cookie
0x18002269b  lea     r11, [rsp+0A0h+var_10]
0x1800226a3  mov     rbx, [r11+30h]
0x1800226a7  mov     rsi, [r11+38h]
0x1800226ab  mov     rsp, r11
0x1800226ae  pop     r15
0x1800226b0  pop     rdi
0x1800226b1  pop     rbp
0x1800226b2  retn
```
