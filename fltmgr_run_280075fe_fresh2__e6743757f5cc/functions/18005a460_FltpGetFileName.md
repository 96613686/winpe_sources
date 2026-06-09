# FltpGetFileName

- ea: `0x18005a460`
- end: `0x18005aa1f`
- name: `FltpGetFileName`
- size: `1471`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a2e0`
- `0x18005b920`

## callees

- `0x180009f20`
- `0x18001cd80`
- `0x1800247a0`
- `0x180024900`
- `0x180058380`
- `0x18005a460`
- `0x18005c600`
- `0x18006e9a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18007939c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007939c`
- `ntoskrnl!KeInitializeEvent` at `0x18005a519`
- `ntoskrnl!KeInitializeEvent` at `0x18005a519`
- `ntoskrnl!IoFreeIrp` at `0x18005a62d`
- `ntoskrnl!IoFreeIrp` at `0x18005a62d`
- `ntoskrnl!IoAllocateIrpEx` at `0x18005a52f`
- `ntoskrnl!IoAllocateIrpEx` at `0x18005a52f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005a9e3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005a9e3`
- `ntoskrnl!IofCallDriver` at `0x18005a609`
- `ntoskrnl!IofCallDriver` at `0x18005a609`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18005a587`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x18005a587`
- `ntoskrnl!IoSetIoPriorityHint` at `0x18005a5b5`
- `ntoskrnl!IoSetIoPriorityHint` at `0x18005a5b5`

## pseudocode

```c
__int64 __fastcall FltpGetFileName(__int64 a1)
{
  int v1; // eax
  char v2; // r13
  unsigned int *v4; // r15
  int v5; // ebp
  unsigned int *v6; // r14
  PDEVICE_OBJECT *v7; // rax
  PDEVICE_OBJECT v8; // rsi
  __int64 v9; // rax
  struct _FILE_OBJECT *v10; // rdi
  int v11; // r12d
  __int64 Irp; // rsi
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  struct _DEVICE_OBJECT *v16; // rcx
  unsigned int InformationFile; // edi
  __int64 v18; // r12
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  unsigned int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // esi
  __int64 v25; // rax
  const void **v26; // rdx
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // rax
  unsigned __int16 *v30; // rax
  __int64 v31; // rax
  unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  unsigned __int16 *v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // [rsp+40h] [rbp-98h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+48h] [rbp-90h]
  PVOID Entry; // [rsp+50h] [rbp-88h] BYREF
  struct _KEVENT Event; // [rsp+58h] [rbp-80h] BYREF
  struct _IO_PRIORITY_INFO PriorityInfo; // [rsp+70h] [rbp-68h] BYREF

  v1 = *(_DWORD *)(a1 + 108);
  v2 = 0;
  v4 = 0;
  v39 = 0;
  Entry = 0;
  v5 = 48;
  if ( (_BYTE)v1 != 1 )
    v5 = 9;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 80LL) & 0x400000) == 0 )
  {
    v6 = *(unsigned int **)(*(_QWORD *)(a1 + 112) + 8LL);
    if ( *(_QWORD *)(a1 + 16) )
      v7 = (PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL) + 64LL) + 8LL);
    else
      v7 = (PDEVICE_OBJECT *)a1;
    v8 = *v7;
    DeviceObject = *v7;
    while ( 2 )
    {
      v9 = *(_QWORD *)(a1 + 112);
      v10 = *(struct _FILE_OBJECT **)(a1 + 64);
      memset(&Event, 0, sizeof(Event));
      v11 = *(_DWORD *)(v9 + 20) - 2;
      PriorityInfo = 0;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      Irp = IoAllocateIrpEx(v8, (unsigned __int8)v8->StackSize, 0);
      if ( Irp )
      {
        *(_QWORD *)(Irp + 152) = KeGetCurrentThread();
        *(_BYTE *)(Irp + 64) = 0;
        PriorityInfo.Size = 16;
        *(_QWORD *)&PriorityInfo.ThreadPriority = 0xFFFF;
        PriorityInfo.IoPriority = IoPriorityNormal;
        v13 = IoRetrievePriorityInfo(0, v10, KeGetCurrentThread(), &PriorityInfo);
        if ( (int)FltpDbgStatus(v13, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 9520, 0) >= 0 )
          IoSetIoPriorityHint((PIRP)Irp, PriorityInfo.IoPriority);
        v14 = *(_QWORD *)(Irp + 184);
        *(_DWORD *)(Irp + 16) = 4;
        *(_BYTE *)(v14 - 72) = 5;
        *(_QWORD *)(v14 - 24) = v10;
        *(_QWORD *)(Irp + 24) = v6;
        *(_DWORD *)(v14 - 64) = v11;
        *(_DWORD *)(v14 - 56) = v5;
        v15 = *(_QWORD *)(Irp + 184);
        *(_QWORD *)(v15 - 16) = &FltpFsControlCompletion;
        *(_QWORD *)(v15 - 8) = &Event;
        v16 = DeviceObject;
        *(_BYTE *)(v15 - 69) = -32;
        if ( IofCallDriver(v16, (PIRP)Irp) == 259 )
          FltpCancellableWaitForIo(&Event, (PIRP)Irp);
        InformationFile = *(_DWORD *)(Irp + 48);
        LODWORD(v39) = *(_DWORD *)(Irp + 56);
        IoFreeIrp((PIRP)Irp);
      }
      else
      {
        InformationFile = -1073741670;
      }
      v18 = a1 + 24;
      while ( InformationFile == -2147483643 )
      {
        v31 = *(_QWORD *)(a1 + 24);
        v18 = a1 + 24;
        if ( v31 )
          v32 = (unsigned __int16 *)(v31 + 112);
        else
          v32 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
        InformationFile = FltpReallocNameControl(*(unsigned __int16 **)(a1 + 112), *v32 + 512 + *v6, 0, 0);
        if ( (int)FltpDbgStatus(InformationFile, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 1934, 0) < 0 )
          return InformationFile;
        v6 = *(unsigned int **)(*(_QWORD *)(a1 + 112) + 8LL);
        InformationFile = FltpQueryInformationFile(DeviceObject, *(PFILE_OBJECT *)(a1 + 64), v5, (__int64)&v39);
      }
      if ( InformationFile == -1073741811
        || (InformationFile == -1073741637 || InformationFile == -1073741821) && (v18 = a1 + 24, v5 == 48) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 80LL) & 0x100) == 0
          || (!*(_QWORD *)v18
            ? (v36 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4LL))
            : (v36 = *(_DWORD *)(*(_QWORD *)v18 + 60LL)),
              v36 != 3 || *(_WORD *)(*(_QWORD *)(a1 + 64) + 88LL)) )
        {
          v33 = *(_QWORD *)(a1 + 80);
          if ( v33
            && (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(*(_QWORD *)(v33 + 16) + 4LL) + 22)) & 2) != 0
            && (*(_DWORD *)v33 & 0x80000) != 0
            && !*(_WORD *)(*(_QWORD *)(a1 + 64) + 88LL) )
          {
            *v6 = 0;
LABEL_20:
            if ( *v6 && *((_WORD *)v6 + 2) != 92 )
              return 3221225506LL;
            v19 = *(_QWORD *)(a1 + 24);
            if ( v19 )
              v20 = (unsigned __int16 *)(v19 + 112);
            else
              v20 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
            v21 = *v6 + *v20;
            goto LABEL_24;
          }
          if ( v5 == 48 )
          {
            *(_DWORD *)(a1 + 40) |= 0x2000u;
            if ( (*(_DWORD *)(a1 + 40) & 0x4000) == 0 )
            {
              v8 = DeviceObject;
              v5 = 9;
              continue;
            }
          }
        }
      }
      else if ( InformationFile != -1073741822 )
      {
        if ( (int)FltpDbgStatus(InformationFile, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 2061, 3221225763LL) < 0 )
          return InformationFile;
        goto LABEL_20;
      }
      return 3223060485LL;
    }
  }
  *(_DWORD *)(a1 + 40) |= 4u;
  v6 = 0;
  v34 = *(_QWORD *)(a1 + 24);
  if ( v34 )
    v35 = (unsigned __int16 *)(v34 + 112);
  else
    v35 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
  v21 = *v35;
LABEL_24:
  if ( v21 > 0xFFFE )
  {
    v23 = -1073741562;
  }
  else if ( v21 <= (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 112) + 20LL) - 2 )
  {
    v23 = 0;
  }
  else
  {
    v22 = FltpReallocNameControl(*(unsigned __int16 **)(a1 + 112), v21 + 514, &Entry, (_DWORD *)&v39 + 1);
    v4 = (unsigned int *)Entry;
    v23 = v22;
    v2 = BYTE4(v39);
  }
  if ( (int)FltpDbgStatus(v23, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 2111, 0) < 0 )
    return v23;
  if ( v6 )
  {
    if ( v4 )
      v6 = v4;
    if ( *v6 )
    {
      v29 = *(_QWORD *)(a1 + 24);
      if ( v29 )
        v30 = (unsigned __int16 *)(v29 + 112);
      else
        v30 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
      memmove((void *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 8LL) + 2 * ((unsigned __int64)*v30 >> 1)), v6 + 1, *v6);
    }
  }
  v25 = *(_QWORD *)(a1 + 24);
  if ( v25 )
    v26 = (const void **)(v25 + 112);
  else
    v26 = (const void **)(*(_QWORD *)(a1 + 32) + 8LL);
  memmove(*(void **)(*(_QWORD *)(a1 + 112) + 8LL), v26[1], *(unsigned __int16 *)v26);
  **(_WORD **)(a1 + 112) = v21;
  if ( v4 )
  {
    if ( (v2 & 2) != 0 )
      ExFreeToPagedLookasideList(&stru_18003F440, v4);
    else
      ExFreePoolWithTag(v4, 0x346E4D46u);
  }
  v27 = *(_QWORD *)(a1 + 24);
  if ( v27 )
    v28 = *(_DWORD *)(v27 + 56);
  else
    v28 = **(_DWORD **)(a1 + 32);
  if ( (v28 & 1) != 0 )
  {
    v37 = *(_QWORD *)(a1 + 24);
    if ( v37 )
      v38 = v37 + 112;
    else
      v38 = *(_QWORD *)(a1 + 32) + 8LL;
    FltpParseShareName(v38, *(_QWORD *)(a1 + 112));
  }
  if ( v5 == 48 )
    *(_DWORD *)(a1 + 40) |= 0x1000u;
  return 0;
}

```

## disassembly

```asm
0x18005a460  push    rbx
0x18005a462  push    rbp
0x18005a463  push    rsi
0x18005a464  push    rdi
0x18005a465  push    r12
0x18005a467  push    r13
0x18005a469  push    r14
0x18005a46b  push    r15
0x18005a46d  sub     rsp, 98h
0x18005a474  mov     rax, cs:__security_cookie
0x18005a47b  xor     rax, rsp
0x18005a47e  mov     [rsp+0D8h+var_58], rax
0x18005a486  mov     eax, [rcx+6Ch]
0x18005a489  xor     r13d, r13d
0x18005a48c  mov     rbx, rcx
0x18005a48f  mov     dword ptr [rsp+0D8h+var_98+4], r13d
0x18005a494  xor     r15d, r15d
0x18005a497  mov     dword ptr [rsp+0D8h+var_98], r13d
0x18005a49c  cmp     al, 1
0x18005a49e  mov     [rsp+0D8h+Entry], r15
0x18005a4a3  mov     ecx, 9
0x18005a4a8  mov     ebp, 30h ; '0'
0x18005a4ad  mov     rax, [rbx+40h]
0x18005a4b1  cmovnz  ebp, ecx
0x18005a4b4  mov     ecx, [rax+50h]
0x18005a4b7  bt      ecx, 16h
0x18005a4bb  jb      loc_18005A93E
0x18005a4c1  mov     rax, [rbx+70h]
0x18005a4c5  mov     r14, [rax+8]
0x18005a4c9  cmp     [rbx+10h], r13
0x18005a4cd  jz      loc_18005A95B
0x18005a4d3  mov     rax, [rbx+8]
0x18005a4d7  mov     rcx, [rax+40h]
0x18005a4db  mov     rax, [rcx+40h]
0x18005a4df  add     rax, 8
0x18005a4e3  mov     rsi, [rax]
0x18005a4e6  mov     [rsp+0D8h+DeviceObject], rsi
0x18005a4eb  mov     rax, [rbx+70h]
0x18005a4ef  lea     rcx, [rsp+0D8h+Event]; Event
0x18005a4f4  mov     rdi, [rbx+40h]
0x18005a4f8  xorps   xmm0, xmm0
0x18005a4fb  xor     r8d, r8d; State
0x18005a4fe  xor     edx, edx; Type
0x18005a500  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x18005a505  mov     r12d, [rax+14h]
0x18005a509  xor     eax, eax
0x18005a50b  mov     [rsp+0D8h+Event.Header.WaitListHead.Blink], rax
0x18005a510  sub     r12d, 2
0x18005a514  movups  xmmword ptr [rsp+0D8h+PriorityInfo.Size], xmm0
0x18005a519  call    cs:__imp_KeInitializeEvent
0x18005a520  nop     dword ptr [rax+rax+00h]
0x18005a525  movzx   edx, byte ptr [rsi+4Ch]
0x18005a529  xor     r8d, r8d
0x18005a52c  mov     rcx, rsi
0x18005a52f  call    cs:__imp_IoAllocateIrpEx
0x18005a536  nop     dword ptr [rax+rax+00h]
0x18005a53b  mov     rsi, rax
0x18005a53e  test    rax, rax
0x18005a541  jz      loc_18005A934
0x18005a547  mov     rax, gs:188h
0x18005a550  lea     r9, [rsp+0D8h+PriorityInfo]; PriorityInfo
0x18005a555  mov     [rsi+98h], rax
0x18005a55c  mov     rdx, rdi; FileObject
0x18005a55f  mov     [rsi+40h], r13b
0x18005a563  xor     ecx, ecx; Irp
0x18005a565  mov     [rsp+0D8h+PriorityInfo.Size], 10h
0x18005a56d  mov     qword ptr [rsp+0D8h+PriorityInfo.ThreadPriority], 0FFFFh
0x18005a576  mov     [rsp+0D8h+PriorityInfo.IoPriority], 2
0x18005a57e  mov     r8, gs:188h; Thread
0x18005a587  call    cs:__imp_IoRetrievePriorityInfo
0x18005a58e  nop     dword ptr [rax+rax+00h]
0x18005a593  xor     r9d, r9d
0x18005a596  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x18005a59d  mov     ecx, eax
0x18005a59f  mov     r8d, 2530h
0x18005a5a5  call    FltpDbgStatus
0x18005a5aa  test    eax, eax
0x18005a5ac  js      short loc_18005A5C1
0x18005a5ae  mov     edx, [rsp+0D8h+PriorityInfo.IoPriority]; PriorityHint
0x18005a5b2  mov     rcx, rsi; Irp
0x18005a5b5  call    cs:__imp_IoSetIoPriorityHint
0x18005a5bc  nop     dword ptr [rax+rax+00h]
0x18005a5c1  mov     rax, [rsi+0B8h]
0x18005a5c8  lea     rcx, FltpFsControlCompletion
0x18005a5cf  mov     dword ptr [rsi+10h], 4
0x18005a5d6  mov     rdx, rsi; Irp
0x18005a5d9  mov     byte ptr [rax-48h], 5
0x18005a5dd  mov     [rax-18h], rdi
0x18005a5e1  mov     [rsi+18h], r14
0x18005a5e5  mov     [rax-40h], r12d
0x18005a5e9  mov     [rax-38h], ebp
0x18005a5ec  mov     rax, [rsi+0B8h]
0x18005a5f3  mov     [rax-10h], rcx
0x18005a5f7  lea     rcx, [rsp+0D8h+Event]
0x18005a5fc  mov     [rax-8], rcx
0x18005a600  mov     rcx, [rsp+0D8h+DeviceObject]; DeviceObject
0x18005a605  mov     byte ptr [rax-45h], 0E0h
0x18005a609  call    cs:__imp_IofCallDriver
0x18005a610  nop     dword ptr [rax+rax+00h]
0x18005a615  cmp     eax, 103h
0x18005a61a  jz      loc_18005A922
0x18005a620  mov     eax, [rsi+38h]
0x18005a623  mov     rcx, rsi; Irp
0x18005a626  mov     edi, [rsi+30h]
0x18005a629  mov     dword ptr [rsp+0D8h+var_98], eax
0x18005a62d  call    cs:__imp_IoFreeIrp
0x18005a634  nop     dword ptr [rax+rax+00h]
0x18005a639  lea     r12, [rbx+18h]
0x18005a63d  cmp     edi, 80000005h
0x18005a643  jz      loc_18005A821
0x18005a649  cmp     edi, 0C000000Dh
0x18005a64f  jz      loc_18005A8A6
0x18005a655  cmp     edi, 0C00000BBh
0x18005a65b  jz      loc_18005A970
0x18005a661  cmp     edi, 0C0000003h
0x18005a667  jz      loc_18005A970
0x18005a66d  cmp     edi, 0C0000002h
0x18005a673  jz      loc_18005AA15
0x18005a679  mov     [rsp+0D8h+var_A8], r13
0x18005a67e  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005a685  mov     dword ptr [rsp+0D8h+var_B0], 0C0000098h
0x18005a68d  mov     r8d, 80Dh
0x18005a693  mov     r9d, 0C0000123h
0x18005a699  mov     [rsp+0D8h+var_B8], 0C00000C4h
0x18005a6a1  mov     ecx, edi
0x18005a6a3  call    FltpDbgStatus
0x18005a6a8  test    eax, eax
0x18005a6aa  js      loc_18005A997
0x18005a6b0  mov     ecx, [r14]
0x18005a6b3  test    ecx, ecx
0x18005a6b5  jnz     loc_18005A80B
0x18005a6bb  mov     rax, [rbx+18h]
0x18005a6bf  test    rax, rax
0x18005a6c2  jz      loc_18005A99E
0x18005a6c8  add     rax, 70h ; 'p'
0x18005a6cc  movzx   edi, word ptr [rax]
0x18005a6cf  add     edi, ecx
0x18005a6d1  cmp     edi, 0FFFEh
0x18005a6d7  ja      loc_18005A9AB
0x18005a6dd  mov     r10, [rbx+70h]
0x18005a6e1  mov     eax, edi
0x18005a6e3  mov     ecx, [r10+14h]
0x18005a6e7  sub     rcx, 2
0x18005a6eb  cmp     rax, rcx
0x18005a6ee  jbe     loc_18005A7C1
0x18005a6f4  lea     edx, [rdi+202h]
0x18005a6fa  mov     rcx, r10
0x18005a6fd  lea     r9, [rsp+0D8h+var_98+4]
0x18005a702  lea     r8, [rsp+0D8h+Entry]
0x18005a707  call    FltpReallocNameControl
0x18005a70c  mov     r15, [rsp+0D8h+Entry]
0x18005a711  mov     esi, eax
0x18005a713  mov     r13d, dword ptr [rsp+0D8h+var_98+4]
0x18005a718  mov     r8d, 83Fh
0x18005a71e  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005a725  xor     r9d, r9d
0x18005a728  mov     ecx, esi
0x18005a72a  call    FltpDbgStatus
0x18005a72f  test    eax, eax
0x18005a731  jns     short loc_18005A75A
0x18005a733  mov     eax, esi
0x18005a735  mov     rcx, [rsp+0D8h+var_58]
0x18005a73d  xor     rcx, rsp; StackCookie
0x18005a740  call    __security_check_cookie
0x18005a745  add     rsp, 98h
0x18005a74c  pop     r15
0x18005a74e  pop     r14
0x18005a750  pop     r13
0x18005a752  pop     r12
0x18005a754  pop     rdi
0x18005a755  pop     rsi
0x18005a756  pop     rbp
0x18005a757  pop     rbx
0x18005a758  retn
0x18005a75a  test    r14, r14
0x18005a75d  jnz     short loc_18005A7C8
0x18005a75f  mov     rax, [rbx+18h]
0x18005a763  test    rax, rax
0x18005a766  jz      loc_18005A9C2
0x18005a76c  lea     rdx, [rax+70h]
0x18005a770  mov     rcx, [rbx+70h]
0x18005a774  movzx   r8d, word ptr [rdx]; Size
0x18005a778  mov     rdx, [rdx+8]; Src
0x18005a77c  mov     rcx, [rcx+8]; void *
0x18005a780  call    memmove
0x18005a785  mov     rax, [rbx+70h]
0x18005a789  mov     [rax], di
0x18005a78c  test    r15, r15
0x18005a78f  jnz     loc_18005A9CF
0x18005a795  mov     rax, [rbx+18h]
0x18005a799  test    rax, rax
0x18005a79c  jz      loc_18005A9F4
0x18005a7a2  mov     ecx, [rax+38h]
0x18005a7a5  test    cl, 1
0x18005a7a8  jnz     loc_18005A9FF
0x18005a7ae  cmp     ebp, 30h ; '0'
0x18005a7b1  jnz     short loc_18005A7BA
0x18005a7b3  or      dword ptr [rbx+28h], 1000h
0x18005a7ba  xor     eax, eax
0x18005a7bc  jmp     loc_18005A735
0x18005a7c1  xor     esi, esi
0x18005a7c3  jmp     loc_18005A718
0x18005a7c8  test    r15, r15
0x18005a7cb  cmovnz  r14, r15
0x18005a7cf  mov     ecx, [r14]
0x18005a7d2  test    ecx, ecx
0x18005a7d4  jz      short loc_18005A75F
0x18005a7d6  mov     rax, [rbx+18h]
0x18005a7da  test    rax, rax
0x18005a7dd  jz      loc_18005A9B5
0x18005a7e3  add     rax, 70h ; 'p'
0x18005a7e7  movzx   r9d, word ptr [rax]
0x18005a7eb  lea     rdx, [r14+4]; Src
0x18005a7ef  mov     rax, [rbx+70h]
0x18005a7f3  mov     r8, rcx; Size
0x18005a7f6  shr     r9, 1
0x18005a7f9  mov     rcx, [rax+8]
0x18005a7fd  lea     rcx, [rcx+r9*2]; void *
0x18005a801  call    memmove
0x18005a806  jmp     loc_18005A75F
0x18005a80b  cmp     word ptr [r14+4], 5Ch ; '\'
0x18005a811  jz      loc_18005A6BB
0x18005a817  mov     eax, 0C0000022h
0x18005a81c  jmp     loc_18005A735
0x18005a821  mov     rax, [rbx+18h]
0x18005a825  lea     r12, [rbx+18h]
0x18005a829  test    rax, rax
0x18005a82c  jz      loc_18005A963
0x18005a832  add     rax, 70h ; 'p'
0x18005a836  movzx   ecx, word ptr [rax]
0x18005a839  xor     r9d, r9d
0x18005a83c  mov     edx, [r14]
0x18005a83f  add     ecx, 200h
0x18005a845  add     edx, ecx
0x18005a847  xor     r8d, r8d
0x18005a84a  mov     rcx, [rbx+70h]
0x18005a84e  call    FltpReallocNameControl
0x18005a853  xor     r9d, r9d
0x18005a856  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005a85d  mov     r8d, 78Eh
0x18005a863  mov     ecx, eax
0x18005a865  mov     edi, eax
0x18005a867  call    FltpDbgStatus
0x18005a86c  test    eax, eax
0x18005a86e  js      loc_18005A997
0x18005a874  mov     r9, [rbx+70h]
0x18005a878  lea     rax, [rsp+0D8h+var_98]
0x18005a87d  mov     rdx, [rbx+40h]; FileObject
0x18005a881  mov     rcx, [rsp+0D8h+DeviceObject]; DeviceObject
0x18005a886  mov     [rsp+0D8h+var_B0], rax; __int64
0x18005a88b  mov     r14, [r9+8]
0x18005a88f  mov     r9d, [r9+14h]
0x18005a893  mov     r8, r14
0x18005a896  mov     [rsp+0D8h+var_B8], ebp; int
0x18005a89a  call    FltpQueryInformationFile
0x18005a89f  mov     edi, eax
0x18005a8a1  jmp     loc_18005A63D
0x18005a8a6  mov     rax, [rbx+40h]
0x18005a8aa  mov     ecx, [rax+50h]
0x18005a8ad  bt      ecx, 8
0x18005a8b1  jb      loc_18005A982
0x18005a8b7  mov     rdx, [rbx+50h]
0x18005a8bb  test    rdx, rdx
0x18005a8be  jz      short loc_18005A8DB
0x18005a8c0  mov     rax, [rdx+10h]
0x18005a8c4  movzx   ecx, byte ptr [rax+4]
0x18005a8c8  add     cl, 16h
0x18005a8cb  movzx   eax, cl
0x18005a8ce  lea     rcx, FltpOperationFlags
0x18005a8d5  test    byte ptr [rax+rcx], 2
0x18005a8d9  jnz     short loc_18005A907
0x18005a8db  cmp     ebp, 30h ; '0'
0x18005a8de  jnz     loc_18005AA15
0x18005a8e4  or      dword ptr [rbx+28h], 2000h
0x18005a8eb  test    dword ptr [rbx+28h], 4000h
0x18005a8f2  jnz     loc_18005AA15
0x18005a8f8  mov     rsi, [rsp+0D8h+DeviceObject]
0x18005a8fd  mov     ebp, 9
0x18005a902  jmp     loc_18005A4EB
0x18005a907  test    dword ptr [rdx], 80000h
0x18005a90d  jz      short loc_18005A8DB
0x18005a90f  mov     rax, [rbx+40h]
0x18005a913  cmp     [rax+58h], r13w
0x18005a918  jnz     short loc_18005A8DB
0x18005a91a  mov     [r14], r13d
0x18005a91d  jmp     loc_18005A6B0
0x18005a922  mov     rdx, rsi; Irp
0x18005a925  lea     rcx, [rsp+0D8h+Event]; Object
0x18005a92a  call    FltpCancellableWaitForIo
0x18005a92f  jmp     loc_18005A620
0x18005a934  mov     edi, 0C000009Ah
0x18005a939  jmp     loc_18005A639
0x18005a93e  or      dword ptr [rbx+28h], 4
0x18005a942  xor     r14d, r14d
0x18005a945  mov     rax, [rbx+18h]
0x18005a949  test    rax, rax
0x18005a94c  jz      loc_180079360
0x18005a952  add     rax, 70h ; 'p'
0x18005a956  jmp     loc_180079368
0x18005a95b  mov     rax, rbx
  ... truncated ...
```
