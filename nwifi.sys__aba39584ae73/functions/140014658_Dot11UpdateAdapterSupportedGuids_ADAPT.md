# Dot11UpdateAdapterSupportedGuids(_ADAPT *)

- ea: `0x140014658`
- end: `0x140014910`
- name: `?Dot11UpdateAdapterSupportedGuids@@YAHPEAU_ADAPT@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(struct _ADAPT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14001453c`

## callees

- `0x14000d21c`
- `0x140014658`
- `0x140015b0c`
- `0x140020dc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400147d9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400147d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400147f1`
- `ntoskrnl!ExAllocatePool2` at `0x1400147f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014842`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014842`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014853`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014853`

## pseudocode

```c
__int64 __fastcall Dot11UpdateAdapterSupportedGuids(struct _ADAPT *a1)
{
  unsigned int uBufSizeOfSupportedGUIDs; // r9d
  _NDIS_GUID *pSupportedGUIDs; // r8
  unsigned int v4; // eax
  unsigned int v5; // esi
  unsigned __int64 v6; // r9
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // ebp
  unsigned int v11; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  _DWORD *Pool2; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+58h] [rbp+10h] BYREF

  uBufSizeOfSupportedGUIDs = a1->uBufSizeOfSupportedGUIDs;
  pSupportedGUIDs = a1->pSupportedGUIDs;
  v17 = 0;
  v18 = 0;
  v4 = PtQueryAdapterSyncEx(a1, 0x10117u, pSupportedGUIDs, uBufSizeOfSupportedGUIDs, &v17, &v18);
  v5 = v4;
  if ( v4 != -2147483643 )
  {
    if ( v4 )
    {
      a1->uNumSupportedGUIDs = 0;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v8 = 11;
        v6 = v4;
        goto LABEL_32;
      }
    }
    else
    {
      v6 = v17 / 0x1CuLL;
      a1->uNumSupportedGUIDs = v6;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v8 = v4 + 10;
LABEL_32:
        WPP_SF_d(v7->AttachedDevice, v8, WPP_539084135bdf378a856f494d89c73045_Traceguids, v6);
      }
    }
    return v5;
  }
  v9 = v18;
  if ( v18 >= a1->uBufSizeOfSupportedGUIDs )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_539084135bdf378a856f494d89c73045_Traceguids, v18);
    v11 = v9 + 16;
    if ( v9 >= 0xFFFFFFF0 )
      return (unsigned int)-1073741670;
    if ( v11 > 0x40 )
    {
      if ( v11 > 0x100 )
      {
        if ( v11 > 0x400 )
        {
          if ( v11 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v11, 2036953975);
LABEL_24:
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 2036953975;
              a1->uBufSizeOfSupportedGUIDs = v9;
              a1->uNumSupportedGUIDs = 0;
              v14 = _InterlockedExchange64((volatile __int64 *)&a1->pSupportedGUIDs, (__int64)(Pool2 + 4));
              if ( v14 )
              {
                v15 = v14 - 16;
                if ( *(_QWORD *)v15 )
                  ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v15, (PVOID)v15);
                else
                  ExFreePoolWithTag((PVOID)v15, *(_DWORD *)(v15 + 8));
              }
              v16 = PtQueryAdapterSyncEx(a1, 0x10117u, a1->pSupportedGUIDs, a1->uBufSizeOfSupportedGUIDs, &v17, &v18);
              v5 = v16;
              if ( v16 )
              {
                a1->uNumSupportedGUIDs = 0;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  return v5;
                v8 = 15;
                v6 = v16;
                goto LABEL_32;
              }
              v6 = v17 / 0x1CuLL;
              a1->uNumSupportedGUIDs = v6;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                v8 = 14;
                goto LABEL_32;
              }
              return v5;
            }
            return (unsigned int)-1073741670;
          }
          p_WaitListHead = &stru_1400B31C0;
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
0x140014658  mov     r11, rsp
0x14001465b  mov     [r11+18h], rbx
0x14001465f  push    rbp
0x140014660  push    rsi
0x140014661  push    rdi
0x140014662  sub     rsp, 30h
0x140014666  mov     r9d, [rcx+3C4h]; unsigned int
0x14001466d  lea     rax, [r11+10h]
0x140014671  mov     r8, [rcx+3D0h]; void *
0x140014678  mov     edx, 10117h; unsigned int
0x14001467d  mov     [r11-20h], rax
0x140014681  mov     rbx, rcx
0x140014684  lea     rax, [r11+8]
0x140014688  mov     [rsp+48h+arg_0], 0
0x140014690  mov     [r11-28h], rax
0x140014694  mov     [rsp+48h+arg_8], 0
0x14001469c  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x1400146a1  mov     esi, eax
0x1400146a3  cmp     eax, 80000005h
0x1400146a8  jz      short loc_140014721
0x1400146aa  test    eax, eax
0x1400146ac  jnz     short loc_1400146F3
0x1400146ae  mov     r9d, [rsp+48h+arg_0]
0x1400146b3  mov     rax, 2492492492492493h
0x1400146bd  mul     r9
0x1400146c0  sub     r9, rdx
0x1400146c3  shr     r9, 1
0x1400146c6  add     r9, rdx
0x1400146c9  shr     r9, 4
0x1400146cd  mov     [rbx+3C8h], r9d
0x1400146d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146db  lea     rdi, WPP_GLOBAL_Control
0x1400146e2  cmp     rcx, rdi
0x1400146e5  jz      loc_140014900
0x1400146eb  lea     edx, [rsi+0Ah]
0x1400146ee  jmp     loc_1400148C9
0x1400146f3  mov     dword ptr [rbx+3C8h], 0
0x1400146fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140014704  lea     rdi, WPP_GLOBAL_Control
0x14001470b  cmp     rcx, rdi
0x14001470e  jz      loc_140014900
0x140014714  mov     edx, 0Bh
0x140014719  mov     r9d, esi
0x14001471c  jmp     loc_1400148C9
0x140014721  mov     ebp, [rsp+48h+arg_8]
0x140014725  cmp     ebp, [rbx+3C4h]
0x14001472b  jnb     short loc_14001475F
0x14001472d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014734  lea     rdi, WPP_GLOBAL_Control
0x14001473b  cmp     rcx, rdi
0x14001473e  jz      short loc_140014755
0x140014740  mov     rcx, [rcx+18h]
0x140014744  lea     r8, WPP_539084135bdf378a856f494d89c73045_Traceguids
0x14001474b  mov     edx, 0Ch
0x140014750  call    WPP_SF_
0x140014755  mov     eax, 0C0000001h
0x14001475a  jmp     loc_140014902
0x14001475f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014766  lea     rdi, WPP_GLOBAL_Control
0x14001476d  cmp     rcx, rdi
0x140014770  jz      short loc_14001478A
0x140014772  mov     rcx, [rcx+18h]
0x140014776  lea     r8, WPP_539084135bdf378a856f494d89c73045_Traceguids
0x14001477d  mov     edx, 0Dh
0x140014782  mov     r9d, ebp
0x140014785  call    WPP_SF_d
0x14001478a  lea     eax, [rbp+10h]
0x14001478d  cmp     eax, 10h
0x140014790  jb      loc_1400148FB
0x140014796  mov     ecx, 40h ; '@'
0x14001479b  cmp     eax, ecx
0x14001479d  ja      short loc_1400147A8
0x14001479f  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x1400147a6  jmp     short loc_1400147D6
0x1400147a8  cmp     eax, 100h
0x1400147ad  ja      short loc_1400147B8
0x1400147af  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400147b6  jmp     short loc_1400147D6
0x1400147b8  cmp     eax, 400h
0x1400147bd  ja      short loc_1400147C8
0x1400147bf  lea     rsi, Lookaside
0x1400147c6  jmp     short loc_1400147D6
0x1400147c8  cmp     eax, 800h
0x1400147cd  ja      short loc_1400147E7
0x1400147cf  lea     rsi, stru_1400B31C0
0x1400147d6  mov     rcx, rsi; Lookaside
0x1400147d9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400147e0  nop     dword ptr [rax+rax+00h]
0x1400147e5  jmp     short loc_1400147FD
0x1400147e7  xor     esi, esi
0x1400147e9  mov     edx, eax
0x1400147eb  mov     r8d, 79697377h
0x1400147f1  call    cs:__imp_ExAllocatePool2
0x1400147f8  nop     dword ptr [rax+rax+00h]
0x1400147fd  test    rax, rax
0x140014800  jz      loc_1400148FB
0x140014806  mov     [rax], rsi
0x140014809  lea     rcx, [rax+10h]
0x14001480d  mov     dword ptr [rax+8], 79697377h
0x140014814  mov     [rbx+3C4h], ebp
0x14001481a  mov     dword ptr [rbx+3C8h], 0
0x140014824  xchg    rcx, [rbx+3D0h]
0x14001482b  test    rcx, rcx
0x14001482e  jz      short loc_14001485F
0x140014830  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140014834  mov     rax, [rcx]
0x140014837  test    rax, rax
0x14001483a  jz      short loc_140014850
0x14001483c  mov     rdx, rcx; Entry
0x14001483f  mov     rcx, rax; Lookaside
0x140014842  call    cs:__imp_ExFreeToNPagedLookasideList
0x140014849  nop     dword ptr [rax+rax+00h]
0x14001484e  jmp     short loc_14001485F
0x140014850  mov     edx, [rcx+8]; Tag
0x140014853  call    cs:__imp_ExFreePoolWithTag
0x14001485a  nop     dword ptr [rax+rax+00h]
0x14001485f  mov     r9d, [rbx+3C4h]; unsigned int
0x140014866  lea     rax, [rsp+48h+arg_8]
0x14001486b  mov     r8, [rbx+3D0h]; void *
0x140014872  mov     edx, 10117h; unsigned int
0x140014877  mov     [rsp+48h+var_20], rax; unsigned int *
0x14001487c  mov     rcx, rbx; struct _ADAPT *
0x14001487f  lea     rax, [rsp+48h+arg_0]
0x140014884  mov     [rsp+48h+var_28], rax; unsigned int *
0x140014889  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x14001488e  mov     esi, eax
0x140014890  test    eax, eax
0x140014892  jnz     short loc_1400148DB
0x140014894  mov     r9d, [rsp+48h+arg_0]
0x140014899  mov     rax, 2492492492492493h
0x1400148a3  mul     r9
0x1400148a6  sub     r9, rdx
0x1400148a9  shr     r9, 1
0x1400148ac  add     r9, rdx
0x1400148af  shr     r9, 4
0x1400148b3  mov     [rbx+3C8h], r9d
0x1400148ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148c1  cmp     rcx, rdi
0x1400148c4  jz      short loc_140014900
0x1400148c6  lea     edx, [rsi+0Eh]
0x1400148c9  mov     rcx, [rcx+18h]
0x1400148cd  lea     r8, WPP_539084135bdf378a856f494d89c73045_Traceguids
0x1400148d4  call    WPP_SF_d
0x1400148d9  jmp     short loc_140014900
0x1400148db  mov     dword ptr [rbx+3C8h], 0
0x1400148e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400148ec  cmp     rcx, rdi
0x1400148ef  jz      short loc_140014900
0x1400148f1  mov     edx, 0Fh
0x1400148f6  mov     r9d, eax
0x1400148f9  jmp     short loc_1400148C9
0x1400148fb  mov     esi, 0C000009Ah
0x140014900  mov     eax, esi
0x140014902  mov     rbx, [rsp+48h+arg_10]
0x140014907  add     rsp, 30h
0x14001490b  pop     rdi
0x14001490c  pop     rsi
0x14001490d  pop     rbp
0x14001490e  retn
```
