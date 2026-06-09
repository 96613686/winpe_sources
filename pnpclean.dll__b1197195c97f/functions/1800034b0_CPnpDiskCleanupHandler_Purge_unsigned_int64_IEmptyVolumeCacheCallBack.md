# CPnpDiskCleanupHandler::Purge(unsigned __int64,IEmptyVolumeCacheCallBack *)

- ea: `0x1800034b0`
- end: `0x1800036be`
- name: `?Purge@CPnpDiskCleanupHandler@@UEAAJ_KPEAUIEmptyVolumeCacheCallBack@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(CPnpDiskCleanupHandler *this, __int64, struct IEmptyVolumeCacheCallBack *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x1800034b0`
- `0x180004c14`
- `0x180006dc4`
- `0x180007dec`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `SETUPAPI!pSetupCreateTextLogSectionW` at `0x18000355b`
- `SETUPAPI!pSetupCreateTextLogSectionW` at `0x18000355b`
- `SETUPAPI!pSetupCloseTextLogSection` at `0x18000367b`
- `SETUPAPI!pSetupCloseTextLogSection` at `0x18000367b`
- `SETUPAPI!pSetupStringFromGuid` at `0x180003537`
- `SETUPAPI!pSetupStringFromGuid` at `0x180003537`
- `SETUPAPI!pSetupIsUserAdmin` at `0x180003501`
- `SETUPAPI!pSetupIsUserAdmin` at `0x180003501`
- `RPCRT4!UuidCreate` at `0x180003513`
- `RPCRT4!UuidCreate` at `0x180003513`

## pseudocode

```c
__int64 __fastcall CPnpDiskCleanupHandler::Purge(
        CPnpDiskCleanupHandler *this,
        __int64 a2,
        struct IEmptyVolumeCacheCallBack *a3)
{
  unsigned int v5; // ebx
  int v6; // edx
  int v7; // ecx
  int v8; // edi
  unsigned int v9; // eax
  int v10; // edx
  int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  struct IEmptyVolumeCacheCallBackVtbl *lpVtbl; // rax
  __int64 v17; // [rsp+40h] [rbp-79h] BYREF
  __int128 v18; // [rsp+48h] [rbp-71h] BYREF
  __int128 v19; // [rsp+58h] [rbp-61h]
  __int128 v20; // [rsp+68h] [rbp-51h]
  __int64 v21; // [rsp+78h] [rbp-41h]
  UUID Uuid; // [rsp+80h] [rbp-39h] BYREF
  _WORD v23[40]; // [rsp+90h] [rbp-29h] BYREF

  v18 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v17 = 0;
  Uuid = GUID_NULL;
  if ( !(unsigned int)pSetupIsUserAdmin(this) )
    return 0;
  if ( UuidCreate(&Uuid) )
    Uuid = GUID_NULL;
  if ( (unsigned int)pSetupStringFromGuid(&Uuid, v23, 39) )
    v23[0] = 0;
  v5 = 0;
  v8 = pSetupCreateTextLogSectionW(v23, 3, L"Device and Driver Disk Cleanup Handler", &v17);
  if ( !v8 )
    v17 = 1;
  *((_QWORD *)&v20 + 1) = a2;
  LODWORD(v18) = 1;
  v19 = 0u;
  *(_QWORD *)&v20 = 0;
  *((_QWORD *)&v18 + 1) = a3;
  LODWORD(v21) = 2;
  v9 = PnpCleanDevicesEx(
         v7,
         v6,
         (unsigned int)PnpDiskCleanupStatusCallback,
         (unsigned int)&v18,
         (__int64)&PnpCleanSetupLogCallback,
         (__int64)&v17,
         0);
  v11 = v20;
  *(_QWORD *)&v19 = v20 + v19;
  *(_QWORD *)&v20 = 0;
  if ( v9 )
    v5 = v9;
  LODWORD(v21) = 1;
  v12 = PnpCleanDriversEx(
          v11,
          v10,
          (unsigned int)PnpDiskCleanupStatusCallback,
          (unsigned int)&v18,
          (__int64)&PnpCleanSetupLogCallback,
          (__int64)&v17,
          0);
  *(_QWORD *)&v19 = v20 + v19;
  *(_QWORD *)&v20 = 0;
  LODWORD(v21) = 3;
  if ( v12 )
    v5 = v12;
  v13 = PnpCleanFiles(
          (unsigned int)PnpDiskCleanupStatusCallback,
          (unsigned int)&v18,
          (unsigned int)&PnpCleanSetupLogCallback,
          (unsigned int)&v17,
          0);
  v14 = v20 + v19;
  *(_QWORD *)&v19 = v20 + v19;
  *(_QWORD *)&v20 = 0;
  if ( v13 )
    v5 = v13;
  if ( a3 )
  {
    lpVtbl = a3->lpVtbl;
    *((_QWORD *)&v20 + 1) = v14;
    ((void (__fastcall *)(struct IEmptyVolumeCacheCallBack *, __int64, __int64, __int64, _QWORD))lpVtbl->PurgeProgress)(
      a3,
      v14,
      v14,
      1,
      0);
  }
  if ( v8 )
    pSetupCloseTextLogSection(v17, v5);
  if ( v5 == 1223 )
    return 2147500036LL;
  else
    return v5 != 0;
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp-8+arg_0], rbx
0x1800034b5  push    rbp
0x1800034b6  push    rsi
0x1800034b7  push    rdi
0x1800034b8  push    r14
0x1800034ba  push    r15
0x1800034bc  lea     rbp, [rsp-37h]
0x1800034c1  sub     rsp, 0F0h
0x1800034c8  mov     rax, cs:__security_cookie
0x1800034cf  xor     rax, rsp
0x1800034d2  mov     [rbp+57h+var_30], rax
0x1800034d6  xorps   xmm0, xmm0
0x1800034d9  xor     eax, eax
0x1800034db  movups  [rbp+57h+var_C8], xmm0
0x1800034df  mov     rsi, r8
0x1800034e2  mov     r14, rdx
0x1800034e5  movups  [rbp+57h+var_B8], xmm0
0x1800034e9  mov     [rbp+57h+var_98], rax
0x1800034ed  movups  [rbp+57h+var_A8], xmm0
0x1800034f1  mov     [rbp+57h+var_D0], rax
0x1800034f5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800034fc  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180003501  call    cs:__imp_pSetupIsUserAdmin
0x180003507  test    eax, eax
0x180003509  jz      loc_180003699
0x18000350f  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180003513  call    cs:__imp_UuidCreate
0x180003519  test    eax, eax
0x18000351b  jz      short loc_180003529
0x18000351d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180003524  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180003529  mov     r8d, 27h ; '''
0x18000352f  lea     rdx, [rbp+57h+var_80]
0x180003533  lea     rcx, [rbp+57h+Uuid]
0x180003537  call    cs:__imp_pSetupStringFromGuid
0x18000353d  test    eax, eax
0x18000353f  jz      short loc_180003547
0x180003541  xor     eax, eax
0x180003543  mov     [rbp+57h+var_80], ax
0x180003547  xor     ebx, ebx
0x180003549  lea     r9, [rbp+57h+var_D0]
0x18000354d  lea     r8, aDeviceAndDrive; "Device and Driver Disk Cleanup Handler"
0x180003554  lea     rcx, [rbp+57h+var_80]
0x180003558  lea     edx, [rbx+3]
0x18000355b  call    cs:__imp_pSetupCreateTextLogSectionW
0x180003561  mov     edi, eax
0x180003563  test    eax, eax
0x180003565  jnz     short loc_18000356F
0x180003567  mov     [rbp+57h+var_D0], 1
0x18000356f  mov     qword ptr [rbp+57h+var_A8+8], r14
0x180003573  lea     rax, [rbp+57h+var_D0]
0x180003577  mov     [rsp+110h+var_E0], ebx
0x18000357b  lea     r14, ?PnpDiskCleanupStatusCallback@@YAHPEAU_PNPCLEAN_STATUS_DATA@@PEAX@Z; PnpDiskCleanupStatusCallback(_PNPCLEAN_STATUS_DATA *,void *)
0x180003582  mov     [rsp+110h+var_E8], rax
0x180003587  lea     r15, PnpCleanSetupLogCallback
0x18000358e  mov     r8, r14
0x180003591  mov     dword ptr [rbp+57h+var_C8], 1
0x180003598  lea     r9, [rbp+57h+var_C8]
0x18000359c  mov     qword ptr [rbp+57h+var_B8], rbx
0x1800035a0  mov     qword ptr [rbp+57h+var_B8+8], rbx
0x1800035a4  mov     qword ptr [rbp+57h+var_A8], rbx
0x1800035a8  mov     qword ptr [rbp+57h+var_C8+8], rsi
0x1800035ac  mov     dword ptr [rbp+57h+var_98], 2
0x1800035b3  mov     [rsp+110h+var_F0], r15
0x1800035b8  call    PnpCleanDevicesEx
0x1800035bd  mov     rcx, qword ptr [rbp+57h+var_A8]
0x1800035c1  lea     r9, [rbp+57h+var_C8]
0x1800035c5  add     qword ptr [rbp+57h+var_B8], rcx
0x1800035c9  mov     r8, r14
0x1800035cc  test    eax, eax
0x1800035ce  mov     qword ptr [rbp+57h+var_A8], rbx
0x1800035d2  mov     [rsp+110h+var_E0], 0
0x1800035da  cmovnz  ebx, eax
0x1800035dd  mov     dword ptr [rbp+57h+var_98], 1
0x1800035e4  lea     rax, [rbp+57h+var_D0]
0x1800035e8  mov     [rsp+110h+var_E8], rax
0x1800035ed  mov     [rsp+110h+var_F0], r15
0x1800035f2  call    PnpCleanDriversEx
0x1800035f7  mov     rcx, qword ptr [rbp+57h+var_A8]
0x1800035fb  lea     r9, [rbp+57h+var_D0]
0x1800035ff  add     qword ptr [rbp+57h+var_B8], rcx
0x180003603  lea     rdx, [rbp+57h+var_C8]
0x180003607  test    eax, eax
0x180003609  mov     qword ptr [rbp+57h+var_A8], 0
0x180003611  mov     r8, r15
0x180003614  mov     dword ptr [rbp+57h+var_98], 3
0x18000361b  mov     rcx, r14
0x18000361e  mov     dword ptr [rsp+110h+var_F0], 0
0x180003626  cmovnz  ebx, eax
0x180003629  call    PnpCleanFiles
0x18000362e  mov     rdx, qword ptr [rbp+57h+var_B8]
0x180003632  add     rdx, qword ptr [rbp+57h+var_A8]
0x180003636  test    eax, eax
0x180003638  mov     qword ptr [rbp+57h+var_B8], rdx
0x18000363c  mov     qword ptr [rbp+57h+var_A8], 0
0x180003644  cmovnz  ebx, eax
0x180003647  test    rsi, rsi
0x18000364a  jz      short loc_180003671
0x18000364c  mov     rax, [rsi]
0x18000364f  mov     r9d, 1
0x180003655  mov     r8, rdx
0x180003658  mov     qword ptr [rbp+57h+var_A8+8], rdx
0x18000365c  mov     rcx, rsi
0x18000365f  mov     [rsp+110h+var_F0], 0
0x180003668  mov     rax, [rax+20h]
0x18000366c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003671  test    edi, edi
0x180003673  jz      short loc_180003681
0x180003675  mov     rcx, [rbp+57h+var_D0]
0x180003679  mov     edx, ebx
0x18000367b  call    cs:__imp_pSetupCloseTextLogSection
0x180003681  cmp     ebx, 4C7h
0x180003687  jnz     short loc_180003690
0x180003689  mov     eax, 80004004h
0x18000368e  jmp     short loc_18000369B
0x180003690  xor     eax, eax
0x180003692  test    ebx, ebx
0x180003694  setnz   al
0x180003697  jmp     short loc_18000369B
0x180003699  xor     eax, eax
0x18000369b  mov     rcx, [rbp+57h+var_30]
0x18000369f  xor     rcx, rsp; StackCookie
0x1800036a2  call    __security_check_cookie
0x1800036a7  mov     rbx, [rsp+110h+arg_0]
0x1800036af  add     rsp, 0F0h
0x1800036b6  pop     r15
0x1800036b8  pop     r14
0x1800036ba  pop     rdi
0x1800036bb  pop     rsi
0x1800036bc  pop     rbp
0x1800036bd  retn
```
