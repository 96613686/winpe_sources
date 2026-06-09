# BfsInsertPolicyEntryLocked

- ea: `0x140008728`
- end: `0x140008e2f`
- name: `BfsInsertPolicyEntryLocked`
- size: `1799`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400073e0`

## callees

- `0x140001008`
- `0x1400061d0`
- `0x140008728`
- `0x140008e38`
- `0x140008ecc`
- `0x140010cc8`
- `0x140012ca0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140008b13`
- `ntoskrnl!KeInitializeEvent` at `0x140008b13`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400087ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400087ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008821`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008821`
- `ntoskrnl!RtlCopySid` at `0x1400089d4`
- `ntoskrnl!RtlCopySid` at `0x140008a10`
- `ntoskrnl!RtlCopySid` at `0x1400089d4`
- `ntoskrnl!RtlCopySid` at `0x140008a10`
- `ntoskrnl!ExSetTimer` at `0x140008b7a`
- `ntoskrnl!ExSetTimer` at `0x140008b7a`
- `ntoskrnl!KeResetEvent` at `0x1400088b8`
- `ntoskrnl!KeResetEvent` at `0x1400088b8`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008bc6`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008bec`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008bc6`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140008bec`
- `ntoskrnl!KeSetEvent` at `0x140008d53`
- `ntoskrnl!KeSetEvent` at `0x140008dfe`
- `ntoskrnl!KeSetEvent` at `0x140008d53`
- `ntoskrnl!KeSetEvent` at `0x140008dfe`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008d74`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008d8b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008dc9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008dd9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008d74`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008d8b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008dc9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140008dd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008db7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008da1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008db7`
- `ntoskrnl!ExAllocatePool2` at `0x14000892f`
- `ntoskrnl!ExAllocatePool2` at `0x14000899d`
- `ntoskrnl!ExAllocatePool2` at `0x140008a45`
- `ntoskrnl!ExAllocatePool2` at `0x140008ab3`
- `ntoskrnl!ExAllocatePool2` at `0x14000892f`
- `ntoskrnl!ExAllocatePool2` at `0x14000899d`
- `ntoskrnl!ExAllocatePool2` at `0x140008a45`
- `ntoskrnl!ExAllocatePool2` at `0x140008ab3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400087fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400087fb`
- `FLTMGR!FltClose` at `0x140008e15`
- `FLTMGR!FltClose` at `0x140008e15`

## pseudocode

```c
__int64 __fastcall BfsInsertPolicyEntryLocked(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        _DWORD *a7,
        __int64 *a8)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v10; // rcx
  void *v11; // r12
  __int64 v12; // rax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdi
  int v16; // eax
  void *Pool2; // r14
  void *v18; // rsi
  int v19; // r8d
  int v20; // r9d
  NTSTATUS inserted; // ebx
  struct _KEVENT *v23; // rcx
  int v24; // ecx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  bool v31; // cc
  NTSTATUS v32; // eax
  __int64 v33; // rax
  struct _KEVENT *v34; // rax
  __int64 v35; // rsi
  _QWORD *v36; // rbx
  _QWORD *v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  __int64 v44; // rax
  _QWORD *v45; // rdi
  _QWORD *v46; // rax
  __int64 v47; // rcx
  _QWORD *v48; // r8
  struct _KEVENT *v49; // rcx
  struct _KEVENT *v50; // rcx
  int Timeout; // [rsp+20h] [rbp-A9h]
  int Timeouta; // [rsp+20h] [rbp-A9h]
  int Timeoutb; // [rsp+20h] [rbp-A9h]
  int v54[2]; // [rsp+30h] [rbp-99h] BYREF
  char v55; // [rsp+38h] [rbp-91h]
  char v56; // [rsp+39h] [rbp-90h]
  char v57; // [rsp+3Ah] [rbp-8Fh]
  _DWORD *v58; // [rsp+40h] [rbp-89h]
  int v59[2]; // [rsp+48h] [rbp-81h] BYREF
  PSID Sid; // [rsp+50h] [rbp-79h]
  PSID SourceSid; // [rsp+58h] [rbp-71h]
  __int64 v62; // [rsp+60h] [rbp-69h]
  __int64 v63; // [rsp+68h] [rbp-61h]
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING v65; // [rsp+80h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v66; // [rsp+90h] [rbp-39h] BYREF
  int *v67; // [rsp+B0h] [rbp-19h]
  __int64 v68; // [rsp+B8h] [rbp-11h]

  v10 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a3 + 8);
  v58 = a7;
  v62 = a4;
  v63 = a3;
  SourceSid = a5;
  v11 = 0;
  Sid = a6;
  v65 = 0;
  *(_QWORD *)v54 = 0;
  UnicodeString = 0;
  *(_QWORD *)v59 = 0;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  v12 = BfsLookupPolicyEntryHashTable(v10);
  v15 = v12;
  if ( !v12 )
  {
    Pool2 = (void *)ExAllocatePool2(256, 4LL * a5[1] + 8, 1400071746);
    if ( !Pool2 )
    {
      inserted = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v54[0] = -1073741801;
        v67 = v54;
        v68 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v25, (int)&byte_140016D91, v26, v27, Timeout, &v66);
      }
      goto LABEL_64;
    }
    v18 = (void *)ExAllocatePool2(256, 4LL * a6[1] + 8, 1400071746);
    if ( !v18 )
    {
      v30 = dword_140019000;
      v31 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_26;
    }
    v32 = RtlCopySid(4 * *((unsigned __int8 *)SourceSid + 1) + 8, Pool2, SourceSid);
    inserted = v32;
    if ( v32 >= 0 )
    {
      inserted = RtlCopySid(4 * *((unsigned __int8 *)Sid + 1) + 8, v18, Sid);
      if ( inserted >= 0 )
      {
        v33 = ExAllocatePool2(256, 152, 1165190722);
        v15 = v33;
        if ( v33 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v33 + 144));
          v34 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1987274306);
          *(_QWORD *)(v15 + 40) = v34;
          if ( !v34 )
          {
            inserted = -1073741801;
            if ( (unsigned int)dword_140019000 <= 3 )
              goto LABEL_49;
            v54[0] = -1073741801;
            goto LABEL_12;
          }
          *(_QWORD *)(v15 + 24) = Pool2;
          *(_QWORD *)(v15 + 32) = v18;
          *(_DWORD *)(v15 + 56) = 268435457;
          *(_DWORD *)(v15 + 104) = 0;
          *(_OWORD *)(v15 + 112) = 0;
          *(_OWORD *)(v15 + 128) = 0;
          KeInitializeEvent(v34, NotificationEvent, 0);
          v35 = v63;
          inserted = BfsInsertEntryHashTable(*(_QWORD *)(v63 + 8), v62, v15);
          if ( inserted >= 0 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v15 + 144));
            v36 = (_QWORD *)(v63 + 16);
            if ( (_QWORD *)*v36 == v36 )
              ExSetTimer(*(_QWORD *)(v63 + 32), -300000000, 300000000, 0);
            v37 = *(_QWORD **)(v63 + 24);
            if ( (_QWORD *)*v37 != v36 )
              goto LABEL_67;
            v55 = 1;
            *(_QWORD *)(v15 + 72) = v37;
            *(_QWORD *)(v15 + 64) = v36;
            *v37 = v15 + 64;
            *(_QWORD *)(v35 + 24) = v15 + 64;
            _InterlockedExchange64((volatile __int64 *)(v15 + 96), MEMORY[0xFFFFF78000000014]);
            goto LABEL_39;
          }
          Pool2 = 0;
          v18 = 0;
          if ( (unsigned int)dword_140019000 > 3 )
          {
            v54[0] = inserted;
            goto LABEL_12;
          }
LABEL_49:
          BfsDereferencePolicyEntryEx((PVOID)v15);
LABEL_50:
          if ( !v55
            || (v44 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v63 + 8)), (v45 = (_QWORD *)v44) == 0) )
          {
LABEL_55:
            if ( v56 )
              RtlFreeUnicodeString(&UnicodeString);
            if ( v57 )
              RtlFreeUnicodeString(&v65);
            if ( !Pool2 )
              goto LABEL_61;
            goto LABEL_60;
          }
          *(_DWORD *)(v44 + 56) = 1;
          v46 = (_QWORD *)(v44 + 64);
          v47 = *v46;
          if ( *(_QWORD **)(*v46 + 8LL) == v46 )
          {
            v48 = (_QWORD *)v46[1];
            if ( (_QWORD *)*v48 == v46 )
            {
              *v48 = v47;
              *(_QWORD *)(v47 + 8) = v48;
              v49 = (struct _KEVENT *)v45[5];
              *v46 = 0;
              v45[9] = 0;
              KeSetEvent(v49, 0, 0);
              BfsDereferencePolicyEntryEx(v45);
              goto LABEL_55;
            }
          }
LABEL_67:
          __fastfail(3u);
        }
        v31 = (unsigned int)dword_140019000 <= 3;
LABEL_26:
        inserted = -1073741801;
        if ( !v31 )
        {
          v54[0] = -1073741801;
          goto LABEL_28;
        }
LABEL_60:
        ExFreePoolWithTag(Pool2, 0);
LABEL_61:
        if ( v18 )
          ExFreePoolWithTag(v18, 0);
        goto LABEL_64;
      }
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_60;
      v54[0] = inserted;
    }
    else
    {
      v30 = dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_60;
      v54[0] = v32;
    }
LABEL_28:
    v68 = 4;
    v67 = v54;
    tlgWriteTransfer_EtwWriteTransfer(v30, (int)&byte_140016D91, v28, v29, Timeout, &v66);
    goto LABEL_60;
  }
  v16 = *(_DWORD *)(v12 + 56);
  Pool2 = 0;
  v18 = 0;
  if ( (v16 & 0x10000000) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 144));
    if ( *(_DWORD *)(v15 + 56) != 268435457
      || (ExReleasePushLockExclusiveEx(a3, 0),
          KeLeaveCriticalRegion(),
          *v58 = 0,
          KeWaitForSingleObject(*(PVOID *)(v15 + 40), Executive, 0, 0, 0),
          *(_DWORD *)(v15 + 56) == 0x10000000) )
    {
      *a8 = v15;
      return 0;
    }
    inserted = -1073741823;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v54[0] = -1073741823;
      v67 = v54;
      v68 = 4;
      tlgWriteTransfer_EtwWriteTransfer(-1073741823, (int)&byte_140016D91, v19, v20, Timeouta, &v66);
    }
    goto LABEL_49;
  }
  if ( v16 != 2 )
  {
    v24 = -1073741823;
    inserted = -1073741823;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v54[0] = -1073741823;
LABEL_12:
      v68 = 4;
      v67 = v54;
      tlgWriteTransfer_EtwWriteTransfer(v24, (int)&byte_140016D91, v13, v14, Timeout, &v66);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v23 = *(struct _KEVENT **)(v15 + 40);
  *(_DWORD *)(v15 + 56) = 268435457;
  KeResetEvent(v23);
  _InterlockedIncrement((volatile signed __int32 *)(v15 + 144));
LABEL_39:
  inserted = RtlConvertSidToUnicodeString(&UnicodeString, SourceSid, 1u);
  if ( inserted < 0 )
    goto LABEL_46;
  v56 = 1;
  inserted = RtlConvertSidToUnicodeString(&v65, Sid, 1u);
  if ( inserted < 0 )
    goto LABEL_46;
  v57 = 1;
  inserted = BfsOpenPolicyDirectory(a1, 0, (unsigned int)&UnicodeString, 0, (__int64)v59);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v54[0] = inserted;
      v67 = v54;
      v68 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v41, (int)&byte_140016D91, v42, v43, Timeoutb, &v66);
    }
    v11 = *(void **)v59;
    goto LABEL_48;
  }
  v11 = *(void **)v59;
  inserted = BfsCreateStorage(a1, 0, v59[0], (unsigned int)&v65, (__int64)v54);
  if ( inserted < 0 )
  {
LABEL_46:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v67 = v54;
      v54[0] = inserted;
      v68 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v38, (int)&byte_140016D91, v39, v40, Timeout, &v66);
    }
LABEL_48:
    v18 = 0;
    Pool2 = 0;
    if ( !v15 )
      goto LABEL_50;
    goto LABEL_49;
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v65);
  v50 = *(struct _KEVENT **)(v15 + 40);
  *(_QWORD *)(v15 + 48) = *(_QWORD *)v54;
  *(_DWORD *)(v15 + 56) = 0x10000000;
  KeSetEvent(v50, 0, 0);
  *a8 = v15;
LABEL_64:
  if ( v11 )
    FltClose(v11);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140008728  mov     [rsp-8+arg_8], rbx
0x14000872d  push    rbp
0x14000872e  push    rsi
0x14000872f  push    rdi
0x140008730  push    r12
0x140008732  push    r13
0x140008734  push    r14
0x140008736  push    r15
0x140008738  lea     rbp, [rsp-7]
0x14000873d  sub     rsp, 0D0h
0x140008744  mov     rax, cs:__security_cookie
0x14000874b  xor     rax, rsp
0x14000874e  mov     [rbp+37h+var_40], rax
0x140008752  mov     rax, [rbp+37h+arg_30]
0x140008756  mov     rbx, r8
0x140008759  mov     r14, [rbp+37h+arg_20]
0x14000875d  mov     r10, r9
0x140008760  mov     rsi, [rbp+37h+arg_28]
0x140008764  xorps   xmm0, xmm0
0x140008767  mov     r15, [rbp+37h+arg_38]
0x14000876b  mov     r13, rcx
0x14000876e  mov     rcx, [rbx+8]; HashTable
0x140008772  mov     r8, r14
0x140008775  mov     [rsp+100h+var_C0], rax
0x14000877a  mov     rdx, r10
0x14000877d  xor     eax, eax
0x14000877f  mov     [rbp+37h+var_A0], r9
0x140008783  mov     r9, rsi
0x140008786  mov     [rbp+37h+var_98], rbx
0x14000878a  mov     [rbp+37h+SourceSid], r14
0x14000878e  mov     r12d, eax
0x140008791  mov     [rbp+37h+Sid], rsi
0x140008795  movups  xmmword ptr [rbp+37h+var_80.Length], xmm0
0x140008799  mov     qword ptr [rsp+100h+var_D0], rax
0x14000879e  movups  xmmword ptr [rbp+37h+UnicodeString.Length], xmm0
0x1400087a2  mov     qword ptr [rsp+100h+var_B8], rax
0x1400087a7  mov     [rsp+100h+var_C7], al
0x1400087ab  mov     [rsp+100h+var_C8], al
0x1400087af  mov     [rsp+100h+var_C6], al
0x1400087b3  call    BfsLookupPolicyEntryHashTable
0x1400087b8  mov     rdi, rax
0x1400087bb  test    rax, rax
0x1400087be  jz      loc_140008915
0x1400087c4  mov     eax, [rax+38h]
0x1400087c7  xor     r14d, r14d
0x1400087ca  xor     esi, esi
0x1400087cc  bt      eax, 1Ch
0x1400087d0  jnb     loc_1400088A8
0x1400087d6  lock inc dword ptr [rdi+90h]
0x1400087dd  cmp     dword ptr [rdi+38h], 10000001h
0x1400087e4  jnz     loc_14000887B
0x1400087ea  xor     edx, edx
0x1400087ec  mov     rcx, rbx
0x1400087ef  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400087f6  nop     dword ptr [rax+rax+00h]
0x1400087fb  call    cs:__imp_KeLeaveCriticalRegion
0x140008802  nop     dword ptr [rax+rax+00h]
0x140008807  mov     r13, [rsp+100h+var_C0]
0x14000880c  xor     r9d, r9d; Alertable
0x14000880f  xor     r8d, r8d; WaitMode
0x140008812  mov     [rsp+100h+Timeout], rsi; int
0x140008817  xor     edx, edx; WaitReason
0x140008819  mov     [r13+0], esi
0x14000881d  mov     rcx, [rdi+28h]; Object
0x140008821  call    cs:__imp_KeWaitForSingleObject
0x140008828  nop     dword ptr [rax+rax+00h]
0x14000882d  cmp     dword ptr [rdi+38h], 10000000h
0x140008834  jz      short loc_14000887B
0x140008836  mov     eax, cs:dword_140019000
0x14000883c  mov     ecx, 0C0000001h; int
0x140008841  mov     ebx, ecx
0x140008843  cmp     eax, 3
0x140008846  jbe     loc_140008CD2
0x14000884c  lea     rax, [rsp+100h+var_D0]
0x140008851  mov     [rsp+100h+var_D0], ecx
0x140008855  mov     [rbp+37h+var_50], rax
0x140008859  lea     rdx, byte_140016D91; int
0x140008860  lea     rax, [rbp+37h+var_70]
0x140008864  mov     [rbp+37h+var_48], 4
0x14000886c  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140008871  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008876  jmp     loc_140008CD2
0x14000887b  mov     [r15], rdi
0x14000887e  xor     eax, eax
0x140008880  mov     rcx, [rbp+37h+var_40]
0x140008884  xor     rcx, rsp; StackCookie
0x140008887  call    __security_check_cookie
0x14000888c  mov     rbx, [rsp+100h+arg_8]
0x140008894  add     rsp, 0D0h
0x14000889b  pop     r15
0x14000889d  pop     r14
0x14000889f  pop     r13
0x1400088a1  pop     r12
0x1400088a3  pop     rdi
0x1400088a4  pop     rsi
0x1400088a5  pop     rbp
0x1400088a6  retn
0x1400088a8  cmp     eax, 2
0x1400088ab  jnz     short loc_1400088D0
0x1400088ad  mov     rcx, [rdi+28h]; Event
0x1400088b1  mov     dword ptr [rdi+38h], 10000001h
0x1400088b8  call    cs:__imp_KeResetEvent
0x1400088bf  nop     dword ptr [rax+rax+00h]
0x1400088c4  lock inc dword ptr [rdi+90h]
0x1400088cb  jmp     loc_140008BBB
0x1400088d0  mov     eax, cs:dword_140019000
0x1400088d6  mov     ecx, 0C0000001h; int
0x1400088db  mov     ebx, ecx
0x1400088dd  cmp     eax, 3
0x1400088e0  jbe     loc_140008CCD
0x1400088e6  mov     [rsp+100h+var_D0], ecx
0x1400088ea  lea     rax, [rsp+100h+var_D0]
0x1400088ef  mov     [rbp+37h+var_48], 4
0x1400088f7  mov     [rbp+37h+var_50], rax
0x1400088fb  lea     rdx, byte_140016D91; int
0x140008902  lea     rax, [rbp+37h+var_70]
0x140008906  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000890b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008910  jmp     loc_140008CCD
0x140008915  movzx   edx, byte ptr [r14+1]
0x14000891a  mov     ebx, 100h
0x14000891f  mov     r8d, 53736642h
0x140008925  mov     ecx, ebx
0x140008927  lea     rdx, ds:8[rdx*4]
0x14000892f  call    cs:__imp_ExAllocatePool2
0x140008936  nop     dword ptr [rax+rax+00h]
0x14000893b  mov     r14, rax
0x14000893e  test    rax, rax
0x140008941  jnz     short loc_140008988
0x140008943  mov     eax, cs:dword_140019000
0x140008949  mov     edx, 0C0000017h
0x14000894e  mov     ebx, edx
0x140008950  cmp     eax, 3
0x140008953  jbe     loc_140008E0D
0x140008959  lea     rax, [rsp+100h+var_D0]
0x14000895e  mov     [rsp+100h+var_D0], edx
0x140008962  mov     [rbp+37h+var_50], rax
0x140008966  lea     rdx, byte_140016D91; int
0x14000896d  lea     rax, [rbp+37h+var_70]
0x140008971  mov     [rbp+37h+var_48], 4
0x140008979  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000897e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008983  jmp     loc_140008E0D
0x140008988  movzx   edx, byte ptr [rsi+1]
0x14000898c  mov     r8d, 53736642h
0x140008992  mov     rcx, rbx
0x140008995  lea     rdx, ds:8[rdx*4]
0x14000899d  call    cs:__imp_ExAllocatePool2
0x1400089a4  nop     dword ptr [rax+rax+00h]
0x1400089a9  mov     rsi, rax
0x1400089ac  test    rax, rax
0x1400089af  jnz     short loc_1400089BF
0x1400089b1  mov     ecx, cs:dword_140019000
0x1400089b7  cmp     ecx, 3
0x1400089ba  jmp     loc_140008A62
0x1400089bf  mov     rax, [rbp+37h+SourceSid]
0x1400089c3  mov     rdx, r14; DestinationSid
0x1400089c6  mov     r8, rax; SourceSid
0x1400089c9  movzx   ecx, byte ptr [rax+1]
0x1400089cd  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x1400089d4  call    cs:__imp_RtlCopySid
0x1400089db  nop     dword ptr [rax+rax+00h]
0x1400089e0  mov     ebx, eax
0x1400089e2  test    eax, eax
0x1400089e4  jns     short loc_1400089FB
0x1400089e6  mov     ecx, cs:dword_140019000
0x1400089ec  cmp     ecx, 3
0x1400089ef  jbe     loc_140008D9C
0x1400089f5  mov     [rsp+100h+var_D0], eax
0x1400089f9  jmp     short loc_140008A73
0x1400089fb  mov     rax, [rbp+37h+Sid]
0x1400089ff  mov     rdx, rsi; DestinationSid
0x140008a02  mov     r8, rax; SourceSid
0x140008a05  movzx   ecx, byte ptr [rax+1]
0x140008a09  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140008a10  call    cs:__imp_RtlCopySid
0x140008a17  nop     dword ptr [rax+rax+00h]
0x140008a1c  mov     ebx, eax
0x140008a1e  test    eax, eax
0x140008a20  jns     short loc_140008A37
0x140008a22  mov     eax, cs:dword_140019000
0x140008a28  cmp     eax, 3
0x140008a2b  jbe     loc_140008D9C
0x140008a31  mov     [rsp+100h+var_D0], ebx
0x140008a35  jmp     short loc_140008A73
0x140008a37  mov     edx, 98h
0x140008a3c  mov     r8d, 45736642h
0x140008a42  lea     ecx, [rdx+68h]
0x140008a45  call    cs:__imp_ExAllocatePool2
0x140008a4c  nop     dword ptr [rax+rax+00h]
0x140008a51  mov     rdi, rax
0x140008a54  test    rax, rax
0x140008a57  jnz     short loc_140008A9E
0x140008a59  mov     eax, cs:dword_140019000
0x140008a5f  cmp     eax, 3
0x140008a62  mov     edx, 0C0000017h
0x140008a67  mov     ebx, edx
0x140008a69  jbe     loc_140008D9C
0x140008a6f  mov     [rsp+100h+var_D0], edx
0x140008a73  lea     rax, [rsp+100h+var_D0]
0x140008a78  mov     [rbp+37h+var_48], 4
0x140008a80  mov     [rbp+37h+var_50], rax
0x140008a84  lea     rdx, byte_140016D91; int
0x140008a8b  lea     rax, [rbp+37h+var_70]
0x140008a8f  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140008a94  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008a99  jmp     loc_140008D9C
0x140008a9e  lock inc dword ptr [rax+90h]
0x140008aa5  mov     edx, 18h
0x140008aaa  mov     r8d, 76736642h
0x140008ab0  lea     ecx, [rdx+28h]
0x140008ab3  call    cs:__imp_ExAllocatePool2
0x140008aba  nop     dword ptr [rax+rax+00h]
0x140008abf  mov     [rdi+28h], rax
0x140008ac3  test    rax, rax
0x140008ac6  jnz     short loc_140008AE7
0x140008ac8  mov     eax, cs:dword_140019000
0x140008ace  mov     edx, 0C0000017h
0x140008ad3  mov     ebx, edx
0x140008ad5  cmp     eax, 3
0x140008ad8  jbe     loc_140008CCD
0x140008ade  mov     [rsp+100h+var_D0], edx
0x140008ae2  jmp     loc_1400088EA
0x140008ae7  mov     [rdi+18h], r14
0x140008aeb  xorps   xmm0, xmm0
0x140008aee  mov     [rdi+20h], rsi
0x140008af2  xorps   xmm1, xmm1
0x140008af5  mov     dword ptr [rdi+38h], 10000001h
0x140008afc  xor     r8d, r8d; State
0x140008aff  mov     [rdi+68h], r12d
0x140008b03  xor     edx, edx; Type
0x140008b05  movups  xmmword ptr [rdi+70h], xmm0
0x140008b09  mov     rcx, rax; Event
0x140008b0c  movups  xmmword ptr [rdi+80h], xmm1
0x140008b13  call    cs:__imp_KeInitializeEvent
0x140008b1a  nop     dword ptr [rax+rax+00h]
0x140008b1f  mov     rsi, [rbp+37h+var_98]
0x140008b23  mov     r8, rdi
0x140008b26  mov     rdx, [rbp+37h+var_A0]
0x140008b2a  mov     rcx, [rsi+8]
0x140008b2e  call    BfsInsertEntryHashTable
0x140008b33  mov     ebx, eax
0x140008b35  test    eax, eax
0x140008b37  jns     short loc_140008B56
0x140008b39  mov     eax, cs:dword_140019000
0x140008b3f  xor     r14d, r14d
0x140008b42  xor     esi, esi
0x140008b44  cmp     eax, 3
0x140008b47  jbe     loc_140008CCD
0x140008b4d  mov     [rsp+100h+var_D0], ebx
0x140008b51  jmp     loc_1400088EA
0x140008b56  lock inc dword ptr [rdi+90h]
0x140008b5d  lea     rbx, [rsi+10h]
0x140008b61  cmp     [rbx], rbx
0x140008b64  jnz     short loc_140008B86
0x140008b66  mov     rcx, [rsi+20h]
0x140008b6a  xor     r9d, r9d
0x140008b6d  mov     rdx, 0FFFFFFFFEE1E5D00h
0x140008b74  mov     r8d, 11E1A300h
0x140008b7a  call    cs:__imp_ExSetTimer
0x140008b81  nop     dword ptr [rax+rax+00h]
0x140008b86  mov     rax, [rbx+8]
0x140008b8a  cmp     [rax], rbx
0x140008b8d  jnz     loc_140008E28
0x140008b93  lea     rcx, [rdi+40h]
0x140008b97  mov     [rsp+100h+var_C8], 1
0x140008b9c  mov     [rcx+8], rax
0x140008ba0  mov     [rcx], rbx
0x140008ba3  mov     [rax], rcx
0x140008ba6  mov     rax, 0FFFFF78000000014h
0x140008bb0  mov     [rbx+8], rcx
0x140008bb4  mov     rax, [rax]
0x140008bb7  xchg    rax, [rcx+20h]
0x140008bbb  mov     rdx, [rbp+37h+SourceSid]; Sid
0x140008bbf  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x140008bc3  mov     r8b, 1; AllocateDestinationString
0x140008bc6  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008bcd  nop     dword ptr [rax+rax+00h]
0x140008bd2  mov     ebx, eax
0x140008bd4  test    eax, eax
0x140008bd6  js      loc_140008C8E
0x140008bdc  mov     rdx, [rbp+37h+Sid]; Sid
0x140008be0  lea     rcx, [rbp+37h+var_80]; UnicodeString
0x140008be4  mov     r8b, 1; AllocateDestinationString
0x140008be7  mov     [rsp+100h+var_C7], 1
0x140008bec  call    cs:__imp_RtlConvertSidToUnicodeString
0x140008bf3  nop     dword ptr [rax+rax+00h]
0x140008bf8  mov     ebx, eax
0x140008bfa  test    eax, eax
0x140008bfc  js      loc_140008C8E
0x140008c02  lea     rax, [rsp+100h+var_B8]
0x140008c07  mov     [rsp+100h+var_C6], 1
0x140008c0c  xor     r9d, r9d
0x140008c0f  mov     [rsp+100h+Timeout], rax; int
0x140008c14  lea     r8, [rbp+37h+UnicodeString]
0x140008c18  xor     edx, edx
0x140008c1a  mov     rcx, r13
0x140008c1d  call    BfsOpenPolicyDirectory
0x140008c22  mov     ebx, eax
0x140008c24  test    eax, eax
  ... truncated ...
```
