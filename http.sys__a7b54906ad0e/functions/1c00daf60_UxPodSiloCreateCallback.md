# UxPodSiloCreateCallback

- ea: `0x1c00daf60`
- end: `0x1c00db217`
- name: `UxPodSiloCreateCallback`
- size: `695`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1c001b610`
- `0x1c001b900`
- `0x1c008f570`
- `0x1c008f76c`
- `0x1c0098cbc`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c00daf60`
- `0x1c0121390`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c00db136`
- `ntoskrnl!KeInitializeEvent` at `0x1c00db136`
- `ntoskrnl!PsGetSiloIdentifier` at `0x1c00daf8a`
- `ntoskrnl!PsGetSiloIdentifier` at `0x1c00daf8a`
- `ntoskrnl!PsCreateSiloContext` at `0x1c00dafcd`
- `ntoskrnl!PsCreateSiloContext` at `0x1c00dafcd`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1c00dafea`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1c00dafea`
- `ntoskrnl!PsIsHostSilo` at `0x1c00db020`
- `ntoskrnl!PsIsHostSilo` at `0x1c00db020`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x1c00db100`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x1c00db100`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1c00db1d6`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1c00db1d6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00db092`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00db187`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00db092`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00db187`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00db04d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00db16a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00db04d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00db16a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00db09e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00db193`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00db09e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00db193`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00db038`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00db155`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00db038`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00db155`

## pseudocode

```c
__int64 __fastcall UxPodSiloCreateCallback(__int64 a1)
{
  unsigned int SiloIdentifier; // eax
  unsigned int v3; // esi
  int v4; // ebx
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  unsigned int v7; // esi
  __int64 *v8; // r14
  int inserted; // eax
  _QWORD *v10; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-10h] BYREF
  void *v16; // [rsp+68h] [rbp+28h] BYREF

  v16 = 0;
  v15 = 0;
  SiloIdentifier = PsGetSiloIdentifier();
  v3 = SiloIdentifier;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000000) != 0 )
    WPP_SF_qD(13, WPP_f81c21fe6cfa3dad0c4b817d24e83b9f_Traceguids, a1, SiloIdentifier);
  v4 = PsCreateSiloContext(a1, 7744, 512, UxPodCleanupCallback, &v16);
  if ( v4 >= 0 )
  {
    if ( ExAcquireRundownProtection(&UxPodCleanupRundown) )
    {
      memset(v16, 0, 0x1E40u);
      *(_DWORD *)v16 = 1146124373;
      *((_DWORD *)v16 + 18) = v3;
      if ( (unsigned __int8)PsIsHostSilo(a1) )
        *((_BYTE *)v16 + 79) = 1;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(&UxPodListLock, 0);
      v5 = (_QWORD *)qword_1C0077328;
      v6 = (char *)v16 + 8;
      if ( *(__int64 **)qword_1C0077328 != &UxPodList )
        __fastfail(3u);
      *v6 = &UxPodList;
      v6[1] = v5;
      *v5 = v6;
      qword_1C0077328 = (__int64)v6;
      ExReleasePushLockExclusiveEx(&UxPodListLock, 0);
      KeLeaveCriticalRegion();
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x8000000) != 0 )
        WPP_SF_qqD(14, WPP_f81c21fe6cfa3dad0c4b817d24e83b9f_Traceguids, a1, v16, *((_DWORD *)v16 + 18));
      UxPodAttachThread(a1, (__int64)&v15);
      v7 = 0;
      v8 = &qword_1C005BFF8;
      do
      {
        if ( *v8 )
        {
          v12 = ((__int64 (__fastcall *)(void *))*v8)(v16);
          v4 = v12;
          if ( v12 < 0 )
          {
            if ( (HIDWORD(WPP_MAIN_CB.DeviceExtension) & 0x8000000) != 0 )
              WPP_SF_qqDd(v14, v13, a1, v16, v7, v12);
            goto LABEL_15;
          }
        }
        ++v7;
        v8 += 6;
        ++*((_DWORD *)v16 + 21);
      }
      while ( v7 < 0x34 );
      UxPodDetachThread((__int64)&v15);
      inserted = PsInsertPermanentSiloContext(a1, (unsigned int)UxPodMonitorSlot, v16);
      v4 = inserted;
      if ( inserted < 0 )
      {
        if ( (HIDWORD(WPP_MAIN_CB.DeviceExtension) & 0x8000000) != 0 )
          WPP_SF_qqD(16, WPP_f81c21fe6cfa3dad0c4b817d24e83b9f_Traceguids, a1, v16, inserted);
      }
      else
      {
        *((_BYTE *)v16 + 76) = 1;
        *((_DWORD *)v16 + 6) = 1;
        KeInitializeEvent((PRKEVENT)((char *)v16 + 32), NotificationEvent, 0);
        *((_DWORD *)v16 + 14) = 2;
        *((_QWORD *)v16 + 8) = a1;
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(&UxPodListLock, 0);
        *((_BYTE *)v16 + 80) = 1;
        ExReleasePushLockExclusiveEx(&UxPodListLock, 0);
        KeLeaveCriticalRegion();
        v10 = v16;
        *(_DWORD *)(*((_QWORD *)v16 + 492) + 48LL) &= ~0x80u;
        *(_DWORD *)(v10[491] + 48LL) &= ~0x80u;
      }
    }
    else
    {
      v4 = -1073741794;
    }
  }
LABEL_15:
  UxPodDetachThread((__int64)&v15);
  if ( v4 < 0 )
  {
    if ( !v16 )
      return (unsigned int)v4;
    UxPodSiloTerminate(a1);
  }
  if ( v16 )
    PsDereferenceSiloContext();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1c00daf60  mov     [rsp-18h+arg_0], rbx
0x1c00daf65  mov     [rsp-18h+arg_10], rsi
0x1c00daf6a  mov     [rsp-18h+arg_18], rdi
0x1c00daf6f  push    rbp
0x1c00daf70  push    r14
0x1c00daf72  push    r15
0x1c00daf74  mov     rbp, rsp
0x1c00daf77  sub     rsp, 40h
0x1c00daf7b  and     [rbp+arg_8], 0
0x1c00daf80  xorps   xmm0, xmm0
0x1c00daf83  movups  [rbp+var_10], xmm0
0x1c00daf87  mov     rdi, rcx
0x1c00daf8a  call    cs:__imp_PsGetSiloIdentifier
0x1c00daf91  nop     dword ptr [rax+rax+00h]
0x1c00daf96  mov     esi, eax
0x1c00daf98  mov     r15d, 8000000h
0x1c00daf9e  test    dword ptr cs:WPP_MAIN_CB.Queue, r15d
0x1c00dafa5  jnz     loc_1C00FE898
0x1c00dafab  lea     rax, [rbp+arg_8]
0x1c00dafaf  mov     r14d, 1E40h
0x1c00dafb5  mov     edx, r14d
0x1c00dafb8  mov     [rsp+40h+var_20], rax
0x1c00dafbd  lea     r9, UxPodCleanupCallback
0x1c00dafc4  mov     r8d, 200h
0x1c00dafca  mov     rcx, rdi
0x1c00dafcd  call    cs:__imp_PsCreateSiloContext
0x1c00dafd4  nop     dword ptr [rax+rax+00h]
0x1c00dafd9  mov     ebx, eax
0x1c00dafdb  test    eax, eax
0x1c00dafdd  js      loc_1C00DB1BC
0x1c00dafe3  lea     rcx, UxPodCleanupRundown; RunRef
0x1c00dafea  call    cs:__imp_ExAcquireRundownProtection
0x1c00daff1  nop     dword ptr [rax+rax+00h]
0x1c00daff6  test    al, al
0x1c00daff8  jz      loc_1C00FE8B5
0x1c00daffe  mov     rcx, [rbp+arg_8]; void *
0x1c00db002  mov     r8d, r14d; Size
0x1c00db005  xor     edx, edx; Val
0x1c00db007  call    memset
0x1c00db00c  mov     rax, [rbp+arg_8]
0x1c00db010  mov     rcx, rdi
0x1c00db013  mov     dword ptr [rax], 44507855h
0x1c00db019  mov     rax, [rbp+arg_8]
0x1c00db01d  mov     [rax+48h], esi
0x1c00db020  call    cs:__imp_PsIsHostSilo
0x1c00db027  nop     dword ptr [rax+rax+00h]
0x1c00db02c  test    al, al
0x1c00db02e  jz      short loc_1C00DB038
0x1c00db030  mov     rax, [rbp+arg_8]
0x1c00db034  mov     byte ptr [rax+4Fh], 1
0x1c00db038  call    cs:__imp_KeEnterCriticalRegion
0x1c00db03f  nop     dword ptr [rax+rax+00h]
0x1c00db044  xor     edx, edx
0x1c00db046  lea     rcx, UxPodListLock
0x1c00db04d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00db054  nop     dword ptr [rax+rax+00h]
0x1c00db059  mov     rcx, cs:qword_1C0077328
0x1c00db060  lea     rdx, UxPodList
0x1c00db067  mov     rax, [rbp+arg_8]
0x1c00db06b  add     rax, 8
0x1c00db06f  cmp     [rcx], rdx
0x1c00db072  jnz     loc_1C00FE8BF
0x1c00db078  mov     [rax], rdx
0x1c00db07b  xor     edx, edx
0x1c00db07d  mov     [rax+8], rcx
0x1c00db081  mov     [rcx], rax
0x1c00db084  lea     rcx, UxPodListLock
0x1c00db08b  mov     cs:qword_1C0077328, rax
0x1c00db092  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00db099  nop     dword ptr [rax+rax+00h]
0x1c00db09e  call    cs:__imp_KeLeaveCriticalRegion
0x1c00db0a5  nop     dword ptr [rax+rax+00h]
0x1c00db0aa  test    dword ptr cs:WPP_MAIN_CB.Queue, r15d
0x1c00db0b1  jnz     loc_1C00FE8C6
0x1c00db0b7  lea     rdx, [rbp+var_10]
0x1c00db0bb  mov     rcx, rdi
0x1c00db0be  call    UxPodAttachThread
0x1c00db0c3  xor     esi, esi
0x1c00db0c5  lea     r14, qword_1C005BFF8
0x1c00db0cc  mov     rax, [r14]
0x1c00db0cf  test    rax, rax
0x1c00db0d2  jnz     loc_1C00DB1FE
0x1c00db0d8  mov     rax, [rbp+arg_8]
0x1c00db0dc  inc     esi
0x1c00db0de  add     r14, 30h ; '0'
0x1c00db0e2  inc     dword ptr [rax+54h]
0x1c00db0e5  cmp     esi, 34h ; '4'
0x1c00db0e8  jb      short loc_1C00DB0CC
0x1c00db0ea  lea     rcx, [rbp+var_10]
0x1c00db0ee  call    UxPodDetachThread
0x1c00db0f3  mov     r8, [rbp+arg_8]
0x1c00db0f7  mov     rcx, rdi
0x1c00db0fa  mov     edx, cs:UxPodMonitorSlot
0x1c00db100  call    cs:__imp_PsInsertPermanentSiloContext
0x1c00db107  nop     dword ptr [rax+rax+00h]
0x1c00db10c  mov     ebx, eax
0x1c00db10e  test    eax, eax
0x1c00db110  js      loc_1C00FE913
0x1c00db116  mov     rax, [rbp+arg_8]
0x1c00db11a  xor     r8d, r8d; State
0x1c00db11d  xor     edx, edx; Type
0x1c00db11f  mov     byte ptr [rax+4Ch], 1
0x1c00db123  mov     rax, [rbp+arg_8]
0x1c00db127  mov     dword ptr [rax+18h], 1
0x1c00db12e  mov     rcx, [rbp+arg_8]
0x1c00db132  add     rcx, 20h ; ' '; Event
0x1c00db136  call    cs:__imp_KeInitializeEvent
0x1c00db13d  nop     dword ptr [rax+rax+00h]
0x1c00db142  mov     rax, [rbp+arg_8]
0x1c00db146  mov     dword ptr [rax+38h], 2
0x1c00db14d  mov     rax, [rbp+arg_8]
0x1c00db151  mov     [rax+40h], rdi
0x1c00db155  call    cs:__imp_KeEnterCriticalRegion
0x1c00db15c  nop     dword ptr [rax+rax+00h]
0x1c00db161  xor     edx, edx
0x1c00db163  lea     rcx, UxPodListLock
0x1c00db16a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00db171  nop     dword ptr [rax+rax+00h]
0x1c00db176  mov     rax, [rbp+arg_8]
0x1c00db17a  lea     rcx, UxPodListLock
0x1c00db181  xor     edx, edx
0x1c00db183  mov     byte ptr [rax+50h], 1
0x1c00db187  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00db18e  nop     dword ptr [rax+rax+00h]
0x1c00db193  call    cs:__imp_KeLeaveCriticalRegion
0x1c00db19a  nop     dword ptr [rax+rax+00h]
0x1c00db19f  mov     rcx, [rbp+arg_8]
0x1c00db1a3  mov     edx, 0FFFFFF7Fh
0x1c00db1a8  mov     rax, [rcx+0F60h]
0x1c00db1af  and     [rax+30h], edx
0x1c00db1b2  mov     rax, [rcx+0F58h]
0x1c00db1b9  and     [rax+30h], edx
0x1c00db1bc  lea     rcx, [rbp+var_10]
0x1c00db1c0  call    UxPodDetachThread
0x1c00db1c5  test    ebx, ebx
0x1c00db1c7  js      loc_1C00FE942
0x1c00db1cd  mov     rcx, [rbp+arg_8]
0x1c00db1d1  test    rcx, rcx
0x1c00db1d4  jz      short loc_1C00DB1E2
0x1c00db1d6  call    cs:__imp_PsDereferenceSiloContext
0x1c00db1dd  nop     dword ptr [rax+rax+00h]
0x1c00db1e2  mov     rsi, [rsp+40h+arg_10]
0x1c00db1e7  mov     eax, ebx
0x1c00db1e9  mov     rbx, [rsp+40h+arg_0]
0x1c00db1ee  mov     rdi, [rsp+40h+arg_18]
0x1c00db1f3  add     rsp, 40h
0x1c00db1f7  pop     r15
0x1c00db1f9  pop     r14
0x1c00db1fb  pop     rbp
0x1c00db1fc  retn
0x1c00db1fe  mov     rcx, [rbp+arg_8]
0x1c00db202  call    cs:__guard_dispatch_icall_fptr
0x1c00db208  mov     ebx, eax
0x1c00db20a  test    eax, eax
0x1c00db20c  jns     loc_1C00DB0D8
0x1c00db212  jmp     loc_1C00FE8EC
0x1c00fe898  mov     ecx, 0Dh
0x1c00fe89d  lea     rdx, WPP_f81c21fe6cfa3dad0c4b817d24e83b9f_Traceguids
0x1c00fe8a4  mov     r9d, esi
0x1c00fe8a7  mov     r8, rdi
0x1c00fe8aa  call    WPP_SF_qD
0x1c00fe8af  nop
0x1c00fe8b0  jmp     loc_1C00DAFAB
0x1c00fe8b5  mov     ebx, 0C000001Eh
0x1c00fe8ba  jmp     loc_1C00DB1BC
0x1c00fe8bf  mov     ecx, 3
0x1c00fe8c4  int     29h; Win8: RtlFailFast(ecx)
0x1c00fe8c6  mov     r9, [rbp+arg_8]
0x1c00fe8ca  lea     rdx, WPP_f81c21fe6cfa3dad0c4b817d24e83b9f_Traceguids
0x1c00fe8d1  mov     ecx, 0Eh
0x1c00fe8d6  mov     r8, rdi
0x1c00fe8d9  mov     eax, [r9+48h]
0x1c00fe8dd  mov     dword ptr [rsp+40h+var_20], eax
0x1c00fe8e1  call    WPP_SF_qqD
0x1c00fe8e6  nop
0x1c00fe8e7  jmp     loc_1C00DB0B7
0x1c00fe8ec  test    dword ptr cs:WPP_MAIN_CB.DeviceExtension+4, r15d
0x1c00fe8f3  jz      loc_1C00DB1BC
0x1c00fe8f9  mov     r9, [rbp+arg_8]
0x1c00fe8fd  mov     r8, rdi
0x1c00fe900  mov     [rsp+40h+var_18], eax
0x1c00fe904  mov     dword ptr [rsp+40h+var_20], esi
0x1c00fe908  call    WPP_SF_qqDd
0x1c00fe90d  nop
0x1c00fe90e  jmp     loc_1C00DB1BC
0x1c00fe913  test    dword ptr cs:WPP_MAIN_CB.DeviceExtension+4, r15d
0x1c00fe91a  jz      loc_1C00DB1BC
0x1c00fe920  mov     r9, [rbp+arg_8]
0x1c00fe924  lea     rdx, WPP_f81c21fe6cfa3dad0c4b817d24e83b9f_Traceguids
0x1c00fe92b  mov     ecx, 10h
0x1c00fe930  mov     dword ptr [rsp+40h+var_20], eax
0x1c00fe934  mov     r8, rdi
0x1c00fe937  call    WPP_SF_qqD
0x1c00fe93c  nop
0x1c00fe93d  jmp     loc_1C00DB1BC
0x1c00fe942  mov     rdx, [rbp+arg_8]
0x1c00fe946  test    rdx, rdx
0x1c00fe949  jz      loc_1C00DB1E2
0x1c00fe94f  mov     rcx, rdi
0x1c00fe952  call    UxPodSiloTerminate
0x1c00fe957  nop
0x1c00fe958  jmp     loc_1C00DB1CD
```
