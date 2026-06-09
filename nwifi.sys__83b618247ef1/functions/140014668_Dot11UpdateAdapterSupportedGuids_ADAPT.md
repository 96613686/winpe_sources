# Dot11UpdateAdapterSupportedGuids(_ADAPT *)

- ea: `0x140014668`
- end: `0x140014920`
- name: `?Dot11UpdateAdapterSupportedGuids@@YAHPEAU_ADAPT@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(struct _ADAPT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14001454c`

## callees

- `0x14000d22c`
- `0x140014668`
- `0x140015b1c`
- `0x140020dc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400147e9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400147e9`
- `ntoskrnl!ExAllocatePool2` at `0x140014801`
- `ntoskrnl!ExAllocatePool2` at `0x140014801`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014852`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014852`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014863`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014863`

## pseudocode

```c
__int64 __fastcall Dot11UpdateAdapterSupportedGuids(struct _ADAPT *a1)
{
  unsigned int uBufSizeOfSupportedGUIDs; // r9d
  _NDIS_GUID *pSupportedGUIDs; // r8
  unsigned int v4; // eax
  __int64 v5; // r9
  unsigned int v6; // esi
  unsigned __int64 v7; // r9
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // ebp
  unsigned int v12; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *Pool2; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v19; // [rsp+58h] [rbp+10h] BYREF

  uBufSizeOfSupportedGUIDs = a1->uBufSizeOfSupportedGUIDs;
  pSupportedGUIDs = a1->pSupportedGUIDs;
  v18 = 0;
  v19 = 0;
  v4 = PtQueryAdapterSyncEx(a1, 0x10117u, pSupportedGUIDs, uBufSizeOfSupportedGUIDs, &v18, &v19);
  v6 = v4;
  if ( v4 != -2147483643 )
  {
    if ( v4 )
    {
      a1->uNumSupportedGUIDs = 0;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v9 = 11;
        v7 = v4;
        goto LABEL_32;
      }
    }
    else
    {
      v7 = v18 / 0x1CuLL;
      a1->uNumSupportedGUIDs = v7;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v9 = v4 + 10;
LABEL_32:
        WPP_SF_d(v8->AttachedDevice, v9, WPP_539084135bdf378a856f494d89c73045_Traceguids, v7);
      }
    }
    return v6;
  }
  v10 = v19;
  if ( v19 >= a1->uBufSizeOfSupportedGUIDs )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_539084135bdf378a856f494d89c73045_Traceguids, v19);
    v12 = v10 + 16;
    if ( v10 >= 0xFFFFFFF0 )
      return (unsigned int)-1073741670;
    if ( v12 > 0x40 )
    {
      if ( v12 > 0x100 )
      {
        if ( v12 > 0x400 )
        {
          if ( v12 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v12, 2036953975, v5);
LABEL_24:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 2036953975;
              a1->uBufSizeOfSupportedGUIDs = v10;
              a1->uNumSupportedGUIDs = 0;
              v15 = _InterlockedExchange64((volatile __int64 *)&a1->pSupportedGUIDs, (__int64)(Pool2 + 4));
              if ( v15 )
              {
                v16 = v15 - 16;
                if ( *(_QWORD *)v16 )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v16, (PVOID)v16);
                else
                  ExFreePoolWithTag((PVOID)v16, *(_DWORD *)(v16 + 8));
              }
              v17 = PtQueryAdapterSyncEx(a1, 0x10117u, a1->pSupportedGUIDs, a1->uBufSizeOfSupportedGUIDs, &v18, &v19);
              v6 = v17;
              if ( v17 )
              {
                a1->uNumSupportedGUIDs = 0;
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  return v6;
                v9 = 15;
                v7 = v17;
                goto LABEL_32;
              }
              v7 = v18 / 0x1CuLL;
              a1->uNumSupportedGUIDs = v7;
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v9 = 14;
                goto LABEL_32;
              }
              return v6;
            }
            return (unsigned int)-1073741670;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_539084135bdf378a856f494d89c73045_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x140014668  mov     r11, rsp
0x14001466b  mov     [r11+18h], rbx
0x14001466f  push    rbp
0x140014670  push    rsi
0x140014671  push    rdi
0x140014672  sub     rsp, 30h
0x140014676  mov     r9d, [rcx+3C4h]; unsigned int
0x14001467d  lea     rax, [r11+10h]
0x140014681  mov     r8, [rcx+3D0h]; void *
0x140014688  mov     edx, 10117h; unsigned int
0x14001468d  mov     [r11-20h], rax
0x140014691  mov     rbx, rcx
0x140014694  lea     rax, [r11+8]
0x140014698  mov     [rsp+48h+arg_0], 0
0x1400146a0  mov     [r11-28h], rax
0x1400146a4  mov     [rsp+48h+arg_8], 0
0x1400146ac  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x1400146b1  mov     esi, eax
0x1400146b3  cmp     eax, 80000005h
0x1400146b8  jz      short loc_140014731
0x1400146ba  test    eax, eax
0x1400146bc  jnz     short loc_140014703
0x1400146be  mov     r9d, [rsp+48h+arg_0]
0x1400146c3  mov     rax, 2492492492492493h
0x1400146cd  mul     r9
0x1400146d0  sub     r9, rdx
0x1400146d3  shr     r9, 1
0x1400146d6  add     r9, rdx
0x1400146d9  shr     r9, 4
0x1400146dd  mov     [rbx+3C8h], r9d
0x1400146e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146eb  lea     rdi, WPP_GLOBAL_Control
0x1400146f2  cmp     rcx, rdi
0x1400146f5  jz      loc_140014910
0x1400146fb  lea     edx, [rsi+0Ah]
0x1400146fe  jmp     loc_1400148D9
0x140014703  mov     dword ptr [rbx+3C8h], 0
0x14001470d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014714  lea     rdi, WPP_GLOBAL_Control
0x14001471b  cmp     rcx, rdi
0x14001471e  jz      loc_140014910
0x140014724  mov     edx, 0Bh
0x140014729  mov     r9d, esi
0x14001472c  jmp     loc_1400148D9
0x140014731  mov     ebp, [rsp+48h+arg_8]
0x140014735  cmp     ebp, [rbx+3C4h]
0x14001473b  jnb     short loc_14001476F
0x14001473d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014744  lea     rdi, WPP_GLOBAL_Control
0x14001474b  cmp     rcx, rdi
0x14001474e  jz      short loc_140014765
0x140014750  mov     rcx, [rcx+18h]
0x140014754  lea     r8, WPP_539084135bdf378a856f494d89c73045_Traceguids
0x14001475b  mov     edx, 0Ch
0x140014760  call    WPP_SF_
0x140014765  mov     eax, 0C0000001h
0x14001476a  jmp     loc_140014912
0x14001476f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014776  lea     rdi, WPP_GLOBAL_Control
0x14001477d  cmp     rcx, rdi
0x140014780  jz      short loc_14001479A
0x140014782  mov     rcx, [rcx+18h]
0x140014786  lea     r8, WPP_539084135bdf378a856f494d89c73045_Traceguids
0x14001478d  mov     edx, 0Dh
0x140014792  mov     r9d, ebp
0x140014795  call    WPP_SF_d
0x14001479a  lea     eax, [rbp+10h]
0x14001479d  cmp     eax, 10h
0x1400147a0  jb      loc_14001490B
0x1400147a6  mov     ecx, 40h ; '@'
0x1400147ab  cmp     eax, ecx
0x1400147ad  ja      short loc_1400147B8
0x1400147af  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x1400147b6  jmp     short loc_1400147E6
0x1400147b8  cmp     eax, 100h
0x1400147bd  ja      short loc_1400147C8
0x1400147bf  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400147c6  jmp     short loc_1400147E6
0x1400147c8  cmp     eax, 400h
0x1400147cd  ja      short loc_1400147D8
0x1400147cf  lea     rsi, Lookaside
0x1400147d6  jmp     short loc_1400147E6
0x1400147d8  cmp     eax, 800h
0x1400147dd  ja      short loc_1400147F7
0x1400147df  lea     rsi, stru_1400B0180
0x1400147e6  mov     rcx, rsi; Lookaside
0x1400147e9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400147f0  nop     dword ptr [rax+rax+00h]
0x1400147f5  jmp     short loc_14001480D
0x1400147f7  xor     esi, esi
0x1400147f9  mov     edx, eax
0x1400147fb  mov     r8d, 79697377h
0x140014801  call    cs:__imp_ExAllocatePool2
0x140014808  nop     dword ptr [rax+rax+00h]
0x14001480d  test    rax, rax
0x140014810  jz      loc_14001490B
0x140014816  mov     [rax], rsi
0x140014819  lea     rcx, [rax+10h]
0x14001481d  mov     dword ptr [rax+8], 79697377h
0x140014824  mov     [rbx+3C4h], ebp
0x14001482a  mov     dword ptr [rbx+3C8h], 0
0x140014834  xchg    rcx, [rbx+3D0h]
0x14001483b  test    rcx, rcx
0x14001483e  jz      short loc_14001486F
0x140014840  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140014844  mov     rax, [rcx]
0x140014847  test    rax, rax
0x14001484a  jz      short loc_140014860
0x14001484c  mov     rdx, rcx; Entry
0x14001484f  mov     rcx, rax; Lookaside
0x140014852  call    cs:__imp_ExFreeToNPagedLookasideList
0x140014859  nop     dword ptr [rax+rax+00h]
0x14001485e  jmp     short loc_14001486F
0x140014860  mov     edx, [rcx+8]; Tag
0x140014863  call    cs:__imp_ExFreePoolWithTag
0x14001486a  nop     dword ptr [rax+rax+00h]
0x14001486f  mov     r9d, [rbx+3C4h]; unsigned int
0x140014876  lea     rax, [rsp+48h+arg_8]
0x14001487b  mov     r8, [rbx+3D0h]; void *
0x140014882  mov     edx, 10117h; unsigned int
0x140014887  mov     [rsp+48h+var_20], rax; unsigned int *
0x14001488c  mov     rcx, rbx; struct _ADAPT *
0x14001488f  lea     rax, [rsp+48h+arg_0]
0x140014894  mov     [rsp+48h+var_28], rax; unsigned int *
0x140014899  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x14001489e  mov     esi, eax
0x1400148a0  test    eax, eax
0x1400148a2  jnz     short loc_1400148EB
0x1400148a4  mov     r9d, [rsp+48h+arg_0]
0x1400148a9  mov     rax, 2492492492492493h
0x1400148b3  mul     r9
0x1400148b6  sub     r9, rdx
0x1400148b9  shr     r9, 1
0x1400148bc  add     r9, rdx
0x1400148bf  shr     r9, 4
0x1400148c3  mov     [rbx+3C8h], r9d
0x1400148ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148d1  cmp     rcx, rdi
0x1400148d4  jz      short loc_140014910
0x1400148d6  lea     edx, [rsi+0Eh]
0x1400148d9  mov     rcx, [rcx+18h]
0x1400148dd  lea     r8, WPP_539084135bdf378a856f494d89c73045_Traceguids
0x1400148e4  call    WPP_SF_d
0x1400148e9  jmp     short loc_140014910
0x1400148eb  mov     dword ptr [rbx+3C8h], 0
0x1400148f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148fc  cmp     rcx, rdi
0x1400148ff  jz      short loc_140014910
0x140014901  mov     edx, 0Fh
0x140014906  mov     r9d, eax
0x140014909  jmp     short loc_1400148D9
0x14001490b  mov     esi, 0C000009Ah
0x140014910  mov     eax, esi
0x140014912  mov     rbx, [rsp+48h+arg_10]
0x140014917  add     rsp, 30h
0x14001491b  pop     rdi
0x14001491c  pop     rsi
0x14001491d  pop     rbp
0x14001491e  retn
```
