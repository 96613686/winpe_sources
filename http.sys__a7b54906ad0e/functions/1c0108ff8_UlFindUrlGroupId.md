# UlFindUrlGroupId

- ea: `0x1c0108ff8`
- end: `0x1c010922a`
- name: `UlFindUrlGroupId`
- size: `562`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1c010035c`
- `0x1c011a2e0`

## callees

- `0x1c001b900`
- `0x1c008f008`
- `0x1c008f064`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c0093a10`
- `0x1c00a6318`
- `0x1c00a8f10`
- `0x1c00a93f4`
- `0x1c0101848`
- `0x1c0108ff8`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0109169`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0109169`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c01090c7`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c01090c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01091bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01091bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0109175`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0109175`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01090b2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01090b2`

## pseudocode

```c
__int64 __fastcall UlFindUrlGroupId(__int64 a1, __int64 a2, void *a3, _QWORD *a4, _QWORD *a5)
{
  int v9; // edx
  int v10; // ecx
  __int64 v11; // rdx
  int RegistrationNode; // ebx
  int v13; // r8d
  __int64 v14; // r14
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  PVOID v19; // rcx
  PVOID P; // [rsp+48h] [rbp-71h] BYREF
  PVOID v22; // [rsp+50h] [rbp-69h]
  __int64 v23; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v24[144]; // [rsp+68h] [rbp-51h] BYREF

  v22 = 0;
  P = 0;
  memset(v24, 0, 0x88u);
  v23 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qSqqq(v10, v9, a1, *(_QWORD *)(a2 + 8), (char)a3, (char)a4, (char)a5);
  *a4 = 0;
  RegistrationNode = UlReferenceRequestQueueByHandle(a3);
  if ( RegistrationNode < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 8) == 0 )
      goto LABEL_20;
    v18 = 143;
    goto LABEL_19;
  }
  LOBYTE(v13) = 1;
  RegistrationNode = UlSanitizeUrl(a1, *(_QWORD *)(a2 + 8), v13, (unsigned int)&P, (__int64)v24);
  if ( RegistrationNode < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 8) == 0 )
      goto LABEL_20;
    v18 = 144;
LABEL_19:
    WPP_SF_D(v18, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
    goto LABEL_20;
  }
  KeEnterCriticalRegion();
  v14 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(a1 + 1360), 0);
  RegistrationNode = UlpTreeFindRegistrationNode(a1, P, &v23);
  if ( RegistrationNode < 0 )
  {
    if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
      WPP_SF_Sd(145, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, P, (unsigned int)RegistrationNode);
  }
  else
  {
    v15 = v23;
    v16 = *(_QWORD *)(v23 + 88);
    if ( (*(_DWORD *)(v16 + 64) & 1) != 0 && *(PVOID *)(v16 + 72) == v22 )
    {
      *a4 = *(_QWORD *)(v16 + 8);
      v17 = *(_QWORD *)(v15 + 80);
      v23 = 0;
      *a5 = v17;
    }
    else
    {
      if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
        WPP_SF_qq(146, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, v16, *(_QWORD *)(v16 + 8));
      RegistrationNode = -1073741790;
    }
  }
  ExReleaseCacheAwarePushLockSharedEx(v14, 0);
  KeLeaveCriticalRegion();
LABEL_20:
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  v19 = v22;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22, 0xFFFFFFFF) == 1 )
      UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)v22);
    v22 = 0;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_iId(v19, v11, *a4, *a5, RegistrationNode);
  return (unsigned int)RegistrationNode;
}

```

## disassembly

```asm
0x1c0108ff8  mov     rax, rsp
0x1c0108ffb  mov     [rax+8], rbx
0x1c0108fff  mov     [rax+10h], rsi
0x1c0109003  mov     [rax+18h], rdi
0x1c0109007  push    rbp
0x1c0109008  push    r14
0x1c010900a  push    r15
0x1c010900c  lea     rbp, [rax-57h]
0x1c0109010  sub     rsp, 0F0h
0x1c0109017  and     [rbp+4Fh+var_B8], 0
0x1c010901c  mov     rbx, r8
0x1c010901f  and     [rbp+4Fh+P], 0
0x1c0109024  mov     r14, rdx
0x1c0109027  mov     rdi, rcx
0x1c010902a  xor     edx, edx; Val
0x1c010902c  mov     r8d, 88h; Size
0x1c0109032  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1c0109036  mov     rsi, r9
0x1c0109039  call    memset
0x1c010903e  and     [rbp+4Fh+var_B0], 0
0x1c0109043  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109049  mov     r15, [rbp+4Fh+arg_20]
0x1c010904d  test    al, 8
0x1c010904f  jz      short loc_1C010906C
0x1c0109051  mov     r9, [r14+8]
0x1c0109055  mov     r8, rdi
0x1c0109058  mov     [rsp+100h+var_D0], r15
0x1c010905d  mov     [rsp+100h+var_D8], rsi
0x1c0109062  mov     [rsp+100h+var_E0], rbx
0x1c0109067  call    WPP_SF_qSqqq
0x1c010906c  and     qword ptr [rsi], 0
0x1c0109070  lea     r9, [rbp+4Fh+var_B8]
0x1c0109074  mov     r8d, 1
0x1c010907a  mov     rcx, rbx; Handle
0x1c010907d  call    UlReferenceRequestQueueByHandle
0x1c0109082  mov     ebx, eax
0x1c0109084  test    eax, eax
0x1c0109086  js      loc_1C0109194
0x1c010908c  mov     rdx, [r14+8]
0x1c0109090  lea     rax, [rbp+4Fh+var_A0]
0x1c0109094  lea     r9, [rbp+4Fh+P]
0x1c0109098  mov     [rsp+100h+var_E0], rax
0x1c010909d  mov     r8b, 1
0x1c01090a0  mov     rcx, rdi
0x1c01090a3  call    UlSanitizeUrl
0x1c01090a8  mov     ebx, eax
0x1c01090aa  test    eax, eax
0x1c01090ac  js      loc_1C0109183
0x1c01090b2  call    cs:__imp_KeEnterCriticalRegion
0x1c01090b9  nop     dword ptr [rax+rax+00h]
0x1c01090be  mov     rcx, [rdi+550h]
0x1c01090c5  xor     edx, edx
0x1c01090c7  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c01090ce  nop     dword ptr [rax+rax+00h]
0x1c01090d3  mov     rdx, [rbp+4Fh+P]
0x1c01090d7  lea     r8, [rbp+4Fh+var_B0]
0x1c01090db  mov     rcx, rdi
0x1c01090de  mov     r14, rax
0x1c01090e1  call    UlpTreeFindRegistrationNode
0x1c01090e6  mov     ebx, eax
0x1c01090e8  test    eax, eax
0x1c01090ea  js      short loc_1C0109142
0x1c01090ec  mov     rdx, [rbp+4Fh+var_B0]
0x1c01090f0  mov     r8, [rdx+58h]
0x1c01090f4  mov     ecx, [r8+40h]
0x1c01090f8  test    cl, 1
0x1c01090fb  jz      short loc_1C010911C
0x1c01090fd  mov     rax, [rbp+4Fh+var_B8]
0x1c0109101  cmp     [r8+48h], rax
0x1c0109105  jnz     short loc_1C010911C
0x1c0109107  mov     rax, [r8+8]
0x1c010910b  mov     [rsi], rax
0x1c010910e  mov     rax, [rdx+50h]
0x1c0109112  and     [rbp+4Fh+var_B0], 0
0x1c0109117  mov     [r15], rax
0x1c010911a  jmp     short loc_1C0109164
0x1c010911c  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c0109122  test    al, 8
0x1c0109124  jz      short loc_1C010913B
0x1c0109126  mov     r9, [r8+8]
0x1c010912a  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109131  mov     ecx, 92h
0x1c0109136  call    WPP_SF_qq
0x1c010913b  mov     ebx, 0C0000022h
0x1c0109140  jmp     short loc_1C0109164
0x1c0109142  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c0109148  test    al, 8
0x1c010914a  jz      short loc_1C0109164
0x1c010914c  mov     r8, [rbp+4Fh+P]
0x1c0109150  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109157  mov     ecx, 91h
0x1c010915c  mov     r9d, ebx
0x1c010915f  call    WPP_SF_Sd
0x1c0109164  xor     edx, edx
0x1c0109166  mov     rcx, r14
0x1c0109169  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c0109170  nop     dword ptr [rax+rax+00h]
0x1c0109175  call    cs:__imp_KeLeaveCriticalRegion
0x1c010917c  nop     dword ptr [rax+rax+00h]
0x1c0109181  jmp     short loc_1C01091B2
0x1c0109183  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c0109189  test    al, 8
0x1c010918b  jz      short loc_1C01091B2
0x1c010918d  mov     ecx, 90h
0x1c0109192  jmp     short loc_1C01091A3
0x1c0109194  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c010919a  test    al, 8
0x1c010919c  jz      short loc_1C01091B2
0x1c010919e  mov     ecx, 8Fh
0x1c01091a3  mov     r8d, ebx
0x1c01091a6  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c01091ad  call    WPP_SF_D
0x1c01091b2  mov     rcx, [rbp+4Fh+P]; P
0x1c01091b6  test    rcx, rcx
0x1c01091b9  jz      short loc_1C01091CE
0x1c01091bb  xor     edx, edx; Tag
0x1c01091bd  call    cs:__imp_ExFreePoolWithTag
0x1c01091c4  nop     dword ptr [rax+rax+00h]
0x1c01091c9  and     [rbp+4Fh+P], 0
0x1c01091ce  mov     rcx, [rbp+4Fh+var_B8]
0x1c01091d2  test    rcx, rcx
0x1c01091d5  jz      short loc_1C01091F1
0x1c01091d7  or      eax, 0FFFFFFFFh
0x1c01091da  lock xadd [rcx], eax
0x1c01091de  cmp     eax, 1
0x1c01091e1  jnz     short loc_1C01091EC
0x1c01091e3  mov     rcx, [rbp+4Fh+var_B8]; P
0x1c01091e7  call    UlFreeRequestQueue
0x1c01091ec  and     [rbp+4Fh+var_B8], 0
0x1c01091f1  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01091f7  test    al, 8
0x1c01091f9  jz      short loc_1C010920A
0x1c01091fb  mov     r9, [r15]
0x1c01091fe  mov     r8, [rsi]
0x1c0109201  mov     dword ptr [rsp+100h+var_E0], ebx
0x1c0109205  call    WPP_SF_iId
0x1c010920a  lea     r11, [rsp+100h+var_10]
0x1c0109212  mov     eax, ebx
0x1c0109214  mov     rbx, [r11+20h]
0x1c0109218  mov     rsi, [r11+28h]
0x1c010921c  mov     rdi, [r11+30h]
0x1c0109220  mov     rsp, r11
0x1c0109223  pop     r15
0x1c0109225  pop     r14
0x1c0109227  pop     rbp
0x1c0109228  retn
```
