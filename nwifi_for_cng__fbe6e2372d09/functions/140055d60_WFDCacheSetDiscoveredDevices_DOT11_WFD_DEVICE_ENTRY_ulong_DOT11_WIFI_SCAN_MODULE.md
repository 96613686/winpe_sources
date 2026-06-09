# WFDCacheSetDiscoveredDevices(_DOT11_WFD_DEVICE_ENTRY *,ulong,DOT11_WIFI_SCAN_MODULE *)

- ea: `0x140055d60`
- end: `0x140055eda`
- name: `?WFDCacheSetDiscoveredDevices@@YAHPEAU_DOT11_WFD_DEVICE_ENTRY@@KPEAUDOT11_WIFI_SCAN_MODULE@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(struct _DOT11_WFD_DEVICE_ENTRY *Src, size_t Size, struct DOT11_WIFI_SCAN_MODULE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140055ee0`

## callees

- `0x140020dc0`
- `0x140055d60`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140055e28`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140055e28`
- `ntoskrnl!ExAllocatePool2` at `0x140055e40`
- `ntoskrnl!ExAllocatePool2` at `0x140055e40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055da3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140055da3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055db4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055db4`

## pseudocode

```c
__int64 __fastcall WFDCacheSetDiscoveredDevices(
        struct _DOT11_WFD_DEVICE_ENTRY *Src,
        size_t Size,
        struct DOT11_WIFI_SCAN_MODULE *a3)
{
  DOT11_BYTE_ARRAY *pWFDDeviceCache; // rbx
  size_t v5; // rbp
  unsigned int v7; // esi
  unsigned int v8; // esi
  unsigned int v9; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  __int64 result; // rax

  pWFDDeviceCache = a3->pWFDDeviceCache;
  v5 = (unsigned int)Size;
  v7 = Size + 12;
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
  v8 = (v7 >> 1) + v7;
  a3->pWFDDeviceCache = 0;
  a3->bWFDDeviceCacheValid = 0;
  v9 = v8 + 16;
  if ( v8 + 16 >= 0x10 )
  {
    if ( v9 > 0x40 )
    {
      if ( v9 > 0x100 )
      {
        if ( v9 > 0x400 )
        {
          if ( v9 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v9, 879326071);
            goto LABEL_17;
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
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_17:
    if ( Pool2 )
    {
      *(_QWORD *)Pool2 = p_WaitListHead;
      pWFDDeviceCache = (DOT11_BYTE_ARRAY *)(Pool2 + 16);
      *((_DWORD *)Pool2 + 2) = 879326071;
      if ( Pool2 != (char *)-16LL )
      {
        a3->uWFDDeviceCacheSize = v8;
        a3->pWFDDeviceCache = pWFDDeviceCache;
LABEL_20:
        memmove(pWFDDeviceCache->ucBuffer, Src, v5);
        pWFDDeviceCache->Header = (_NDIS_OBJECT_HEADER)1048960;
        result = 0;
        pWFDDeviceCache->uNumOfBytes = v5;
        pWFDDeviceCache->uTotalNumOfBytes = v5;
        a3->bWFDDeviceCacheValid = 1;
        return result;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer)
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids, v8);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140055d60  push    rbx
0x140055d62  push    rbp
0x140055d63  push    rsi
0x140055d64  push    rdi
0x140055d65  push    r12
0x140055d67  push    r14
0x140055d69  sub     rsp, 28h
0x140055d6d  mov     rbx, [r8+50h]
0x140055d71  mov     rdi, r8
0x140055d74  mov     ebp, edx
0x140055d76  mov     r14, rcx
0x140055d79  mov     r12d, 10h
0x140055d7f  lea     esi, [rbp+0Ch]
0x140055d82  cmp     [r8+58h], esi
0x140055d86  jnb     loc_140055E6B
0x140055d8c  test    rbx, rbx
0x140055d8f  jz      short loc_140055DC0
0x140055d91  lea     rcx, [rbx-10h]; P
0x140055d95  mov     rax, [rcx]
0x140055d98  test    rax, rax
0x140055d9b  jz      short loc_140055DB1
0x140055d9d  mov     rdx, rcx; Entry
0x140055da0  mov     rcx, rax; Lookaside
0x140055da3  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055daa  nop     dword ptr [rax+rax+00h]
0x140055daf  jmp     short loc_140055DC0
0x140055db1  mov     edx, [rcx+8]; Tag
0x140055db4  call    cs:__imp_ExFreePoolWithTag
0x140055dbb  nop     dword ptr [rax+rax+00h]
0x140055dc0  mov     eax, esi
0x140055dc2  mov     dword ptr [rdi+58h], 0
0x140055dc9  shr     eax, 1
0x140055dcb  add     esi, eax
0x140055dcd  mov     qword ptr [rdi+50h], 0
0x140055dd5  mov     byte ptr [rdi+5Ch], 0
0x140055dd9  lea     eax, [rsi+10h]
0x140055ddc  cmp     eax, r12d
0x140055ddf  jb      loc_140055E9A
0x140055de5  mov     ecx, 40h ; '@'
0x140055dea  cmp     eax, ecx
0x140055dec  ja      short loc_140055DF7
0x140055dee  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140055df5  jmp     short loc_140055E25
0x140055df7  cmp     eax, 100h
0x140055dfc  ja      short loc_140055E07
0x140055dfe  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140055e05  jmp     short loc_140055E25
0x140055e07  cmp     eax, 400h
0x140055e0c  ja      short loc_140055E17
0x140055e0e  lea     rbx, Lookaside
0x140055e15  jmp     short loc_140055E25
0x140055e17  cmp     eax, 800h
0x140055e1c  ja      short loc_140055E36
0x140055e1e  lea     rbx, stru_1400B31C0
0x140055e25  mov     rcx, rbx; Lookaside
0x140055e28  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140055e2f  nop     dword ptr [rax+rax+00h]
0x140055e34  jmp     short loc_140055E4C
0x140055e36  xor     ebx, ebx
0x140055e38  mov     edx, eax
0x140055e3a  mov     r8d, 34697377h
0x140055e40  call    cs:__imp_ExAllocatePool2
0x140055e47  nop     dword ptr [rax+rax+00h]
0x140055e4c  test    rax, rax
0x140055e4f  jz      short loc_140055E9A
0x140055e51  mov     [rax], rbx
0x140055e54  lea     rbx, [rax+10h]
0x140055e58  mov     dword ptr [rax+8], 34697377h
0x140055e5f  test    rbx, rbx
0x140055e62  jz      short loc_140055E9A
0x140055e64  mov     [rdi+58h], esi
0x140055e67  mov     [rdi+50h], rbx
0x140055e6b  mov     r8, rbp; Size
0x140055e6e  lea     rcx, [rbx+0Ch]; void *
0x140055e72  mov     rdx, r14; Src
0x140055e75  call    memmove
0x140055e7a  mov     dword ptr [rbx], 100180h
0x140055e80  xor     eax, eax
0x140055e82  mov     [rbx+4], ebp
0x140055e85  mov     [rbx+8], ebp
0x140055e88  mov     byte ptr [rdi+5Ch], 1
0x140055e8c  add     rsp, 28h
0x140055e90  pop     r14
0x140055e92  pop     r12
0x140055e94  pop     rdi
0x140055e95  pop     rsi
0x140055e96  pop     rbp
0x140055e97  pop     rbx
0x140055e98  retn
0x140055e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ea1  lea     rax, WPP_GLOBAL_Control
0x140055ea8  cmp     rcx, rax
0x140055eab  jz      short loc_140055ED3
0x140055ead  cmp     byte ptr [rcx+29h], 1
0x140055eb1  jb      short loc_140055ED3
0x140055eb3  mov     eax, [rcx+2Ch]
0x140055eb6  test    r12b, al
0x140055eb9  jz      short loc_140055ED3
0x140055ebb  mov     rcx, [rcx+18h]
0x140055ebf  lea     r8, WPP_98d4bfef0f1a33477cd81b24b04290f1_Traceguids
0x140055ec6  mov     edx, 15h
0x140055ecb  mov     r9d, esi
0x140055ece  call    WPP_SF_d
0x140055ed3  mov     eax, 0C000009Ah
0x140055ed8  jmp     short loc_140055E8C
```
