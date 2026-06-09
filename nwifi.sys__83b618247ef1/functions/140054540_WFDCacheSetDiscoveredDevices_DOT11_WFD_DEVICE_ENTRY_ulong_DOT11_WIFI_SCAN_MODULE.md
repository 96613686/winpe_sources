# WFDCacheSetDiscoveredDevices(_DOT11_WFD_DEVICE_ENTRY *,ulong,DOT11_WIFI_SCAN_MODULE *)

- ea: `0x140054540`
- end: `0x1400546ba`
- name: `?WFDCacheSetDiscoveredDevices@@YAHPEAU_DOT11_WFD_DEVICE_ENTRY@@KPEAUDOT11_WIFI_SCAN_MODULE@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(struct _DOT11_WFD_DEVICE_ENTRY *Src, size_t Size, struct DOT11_WIFI_SCAN_MODULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400546c0`

## callees

- `0x140020dc0`
- `0x140054540`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054608`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140054608`
- `ntoskrnl!ExAllocatePool2` at `0x140054620`
- `ntoskrnl!ExAllocatePool2` at `0x140054620`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054583`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054583`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054594`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054594`

## pseudocode

```c
__int64 __fastcall WFDCacheSetDiscoveredDevices(
        struct _DOT11_WFD_DEVICE_ENTRY *Src,
        size_t Size,
        struct DOT11_WIFI_SCAN_MODULE *a3,
        __int64 a4)
{
  DOT11_BYTE_ARRAY *pWFDDeviceCache; // rbx
  size_t v6; // rbp
  unsigned int v8; // esi
  unsigned int v9; // esi
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  __int64 result; // rax

  pWFDDeviceCache = a3->pWFDDeviceCache;
  v6 = (unsigned int)Size;
  v8 = Size + 12;
  if ( a3->uWFDDeviceCacheSize >= (unsigned int)(Size + 12) )
    goto LABEL_20;
  if ( pWFDDeviceCache )
  {
    if ( *(_QWORD *)&pWFDDeviceCache[-1].Header.Type )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&pWFDDeviceCache[-1].Header.Type, &pWFDDeviceCache[-1]);
    else
      ExFreePoolWithTag(&pWFDDeviceCache[-1], pWFDDeviceCache[-1].uTotalNumOfBytes);
  }
  a3->uWFDDeviceCacheSize = 0;
  v9 = (v8 >> 1) + v8;
  a3->pWFDDeviceCache = 0;
  a3->bWFDDeviceCacheValid = 0;
  v10 = v9 + 16;
  if ( v9 + 16 >= 0x10 )
  {
    if ( v10 > 0x40 )
    {
      if ( v10 > 0x100 )
      {
        if ( v10 > 0x400 )
        {
          if ( v10 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v10, 879326071, a4);
            goto LABEL_17;
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
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_17:
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = p_WaitListHead;
      pWFDDeviceCache = (DOT11_BYTE_ARRAY *)(Pool2 + 16);
      *((_DWORD *)Pool2 + 2) = 879326071;
      if ( Pool2 != (char *)-16LL )
      {
        a3->uWFDDeviceCacheSize = v9;
        a3->pWFDDeviceCache = pWFDDeviceCache;
LABEL_20:
        memmove(pWFDDeviceCache->ucBuffer, Src, v6);
        pWFDDeviceCache->Header = (_NDIS_OBJECT_HEADER)1048960;
        result = 0;
        pWFDDeviceCache->uNumOfBytes = v6;
        pWFDDeviceCache->uTotalNumOfBytes = v6;
        a3->bWFDDeviceCacheValid = 1;
        return result;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v9);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140054540  push    rbx
0x140054542  push    rbp
0x140054543  push    rsi
0x140054544  push    rdi
0x140054545  push    r12
0x140054547  push    r14
0x140054549  sub     rsp, 28h
0x14005454d  mov     rbx, [r8+50h]
0x140054551  mov     rdi, r8
0x140054554  mov     ebp, edx
0x140054556  mov     r14, rcx
0x140054559  mov     r12d, 10h
0x14005455f  lea     esi, [rbp+0Ch]
0x140054562  cmp     [r8+58h], esi
0x140054566  jnb     loc_14005464B
0x14005456c  test    rbx, rbx
0x14005456f  jz      short loc_1400545A0
0x140054571  lea     rcx, [rbx-10h]; P
0x140054575  mov     rax, [rcx]
0x140054578  test    rax, rax
0x14005457b  jz      short loc_140054591
0x14005457d  mov     rdx, rcx; Entry
0x140054580  mov     rcx, rax; Lookaside
0x140054583  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005458a  nop     dword ptr [rax+rax+00h]
0x14005458f  jmp     short loc_1400545A0
0x140054591  mov     edx, [rcx+8]; Tag
0x140054594  call    cs:__imp_ExFreePoolWithTag
0x14005459b  nop     dword ptr [rax+rax+00h]
0x1400545a0  mov     eax, esi
0x1400545a2  mov     dword ptr [rdi+58h], 0
0x1400545a9  shr     eax, 1
0x1400545ab  add     esi, eax
0x1400545ad  mov     qword ptr [rdi+50h], 0
0x1400545b5  mov     byte ptr [rdi+5Ch], 0
0x1400545b9  lea     eax, [rsi+10h]
0x1400545bc  cmp     eax, r12d
0x1400545bf  jb      loc_14005467A
0x1400545c5  mov     ecx, 40h ; '@'
0x1400545ca  cmp     eax, ecx
0x1400545cc  ja      short loc_1400545D7
0x1400545ce  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400545d5  jmp     short loc_140054605
0x1400545d7  cmp     eax, 100h
0x1400545dc  ja      short loc_1400545E7
0x1400545de  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400545e5  jmp     short loc_140054605
0x1400545e7  cmp     eax, 400h
0x1400545ec  ja      short loc_1400545F7
0x1400545ee  lea     rbx, Lookaside
0x1400545f5  jmp     short loc_140054605
0x1400545f7  cmp     eax, 800h
0x1400545fc  ja      short loc_140054616
0x1400545fe  lea     rbx, stru_1400B0180
0x140054605  mov     rcx, rbx; Lookaside
0x140054608  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005460f  nop     dword ptr [rax+rax+00h]
0x140054614  jmp     short loc_14005462C
0x140054616  xor     ebx, ebx
0x140054618  mov     edx, eax
0x14005461a  mov     r8d, 34697377h
0x140054620  call    cs:__imp_ExAllocatePool2
0x140054627  nop     dword ptr [rax+rax+00h]
0x14005462c  test    rax, rax
0x14005462f  jz      short loc_14005467A
0x140054631  mov     [rax], rbx
0x140054634  lea     rbx, [rax+10h]
0x140054638  mov     dword ptr [rax+8], 34697377h
0x14005463f  test    rbx, rbx
0x140054642  jz      short loc_14005467A
0x140054644  mov     [rdi+58h], esi
0x140054647  mov     [rdi+50h], rbx
0x14005464b  mov     r8, rbp; Size
0x14005464e  lea     rcx, [rbx+0Ch]; void *
0x140054652  mov     rdx, r14; Src
0x140054655  call    memmove
0x14005465a  mov     dword ptr [rbx], 100180h
0x140054660  xor     eax, eax
0x140054662  mov     [rbx+4], ebp
0x140054665  mov     [rbx+8], ebp
0x140054668  mov     byte ptr [rdi+5Ch], 1
0x14005466c  add     rsp, 28h
0x140054670  pop     r14
0x140054672  pop     r12
0x140054674  pop     rdi
0x140054675  pop     rsi
0x140054676  pop     rbp
0x140054677  pop     rbx
0x140054678  retn
0x14005467a  mov     rcx, cs:WPP_GLOBAL_Control
0x140054681  lea     rax, WPP_GLOBAL_Control
0x140054688  cmp     rcx, rax
0x14005468b  jz      short loc_1400546B3
0x14005468d  cmp     byte ptr [rcx+29h], 1
0x140054691  jb      short loc_1400546B3
0x140054693  mov     eax, [rcx+2Ch]
0x140054696  test    r12b, al
0x140054699  jz      short loc_1400546B3
0x14005469b  mov     rcx, [rcx+18h]
0x14005469f  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x1400546a6  mov     edx, 15h
0x1400546ab  mov     r9d, esi
0x1400546ae  call    WPP_SF_d
0x1400546b3  mov     eax, 0C000009Ah
0x1400546b8  jmp     short loc_14005466C
```
