# FltpCreateCommunicationPort

- ea: `0x180054074`
- end: `0x18005431f`
- name: `FltpCreateCommunicationPort`
- size: `683`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, PHANDLE Handle@<rdx>, __int64, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180053fb0`
- `0x180054000`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180024c40`
- `0x180054074`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x1800542a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1800542a9`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005426e`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005426e`
- `ntoskrnl!ExAllocatePool2` at `0x1800541ca`
- `ntoskrnl!ExAllocatePool2` at `0x1800541ca`
- `ntoskrnl!ObCreateObject` at `0x180054120`
- `ntoskrnl!ObCreateObject` at `0x180054120`
- `ntoskrnl!ObInsertObject` at `0x1800542d5`
- `ntoskrnl!ObInsertObject` at `0x1800542d5`

## pseudocode

```c
__int64 __fastcall FltpCreateCommunicationPort(
        char *FltObject,
        PHANDLE Handle,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9)
{
  char v9; // r14
  unsigned int inserted; // ebx
  _QWORD *Pool2; // rax
  _QWORD *v16; // rsi
  PVOID *v17; // rcx
  PVOID Object[3]; // [rsp+50h] [rbp-18h] BYREF

  v9 = 0;
  Object[0] = 0;
  if ( a9 > 0 && (*(_DWORD *)(a3 + 24) & 0x200) != 0 )
  {
    inserted = FltObjectReference(FltObject);
    if ( (int)FltpDbgStatus(inserted, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 482, 3223060491LL) >= 0 )
    {
      v9 = 1;
      inserted = ObCreateObject(0, qword_18003EF28, a3, 0, 0, 80, 0, 0, Object);
      if ( (int)FltpDbgStatus(inserted, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 503, 0) >= 0 )
      {
        memset(Object[0], 0, 0x50u);
        _InterlockedAdd((volatile signed __int32 *)FltObject + 1, 1u);
        *((_QWORD *)Object[0] + 6) = FltObject;
        *((_DWORD *)Object[0] + 18) = a9;
        if ( *((_QWORD *)FltObject + 30) )
        {
          Pool2 = (_QWORD *)ExAllocatePool2(256, 48, 1786137926);
          if ( !Pool2 )
          {
            inserted = -1073741670;
            goto LABEL_20;
          }
          Pool2[1] = a4;
          *Pool2 = FltObject;
          Pool2[2] = a5;
          Pool2[3] = a6;
          Pool2[4] = a7;
          Pool2[5] = a8;
          *((_QWORD *)Object[0] + 2) = FltpvConnectionNotify;
          *((_QWORD *)Object[0] + 3) = FltpvDisconnectNotify;
          if ( a7 )
            *((_QWORD *)Object[0] + 4) = FltpvMessageNotify;
          if ( a8 )
            *((_QWORD *)Object[0] + 5) = FltpvMessageNotify2;
          *((_QWORD *)Object[0] + 7) = Pool2;
        }
        else
        {
          *((_QWORD *)Object[0] + 7) = a4;
          *((_QWORD *)Object[0] + 2) = a5;
          *((_QWORD *)Object[0] + 3) = a6;
          *((_QWORD *)Object[0] + 4) = a7;
          *((_QWORD *)Object[0] + 5) = a8;
        }
        v16 = Object[0];
        ExAcquireFastMutex((PFAST_MUTEX)(FltObject + 528));
        if ( (FltObject[600] & 1) == 0 )
        {
          *((_DWORD *)FltObject + 150) += 2;
          v17 = (PVOID *)*((_QWORD *)FltObject + 74);
          if ( *v17 != FltObject + 584 )
            __fastfail(3u);
          *v16 = FltObject + 584;
          v16[1] = v17;
          *v17 = v16;
          *((_QWORD *)FltObject + 74) = v16;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(FltObject + 528));
        v9 = 0;
        inserted = ObInsertObject(Object[0], 0, 0x1F0001u, 0, 0, Handle);
      }
    }
  }
  else
  {
    inserted = -1073741811;
  }
LABEL_20:
  if ( (int)FltpDbgStatus(inserted, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 610, 0) < 0 && v9 )
    FltObjectDereference(FltObject);
  return inserted;
}

```

## disassembly

```asm
0x180054074  push    rbp
0x180054076  push    rbx
0x180054077  push    rsi
0x180054078  push    rdi
0x180054079  push    r12
0x18005407b  push    r13
0x18005407d  push    r14
0x18005407f  push    r15
0x180054081  mov     rbp, rsp
0x180054084  sub     rsp, 68h
0x180054088  mov     esi, [rbp+arg_40]
0x18005408e  xor     r14b, r14b
0x180054091  mov     [rbp+Object], 0
0x180054099  mov     r12, r9
0x18005409c  mov     r15, r8
0x18005409f  mov     r13, rdx
0x1800540a2  mov     rdi, rcx
0x1800540a5  test    esi, esi
0x1800540a7  jg      short loc_1800540B3
0x1800540a9  mov     ebx, 0C000000Dh
0x1800540ae  jmp     loc_1800542E3
0x1800540b3  test    dword ptr [r8+18h], 200h
0x1800540bb  jz      short loc_1800540A9
0x1800540bd  call    FltObjectReference
0x1800540c2  mov     r8d, 1E2h
0x1800540c8  mov     [rsp+68h+NewObject], 0
0x1800540d1  mov     r9d, 0C01C000Bh
0x1800540d7  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x1800540de  mov     ecx, eax
0x1800540e0  mov     ebx, eax
0x1800540e2  call    FltpDbgStatus
0x1800540e7  xor     ecx, ecx
0x1800540e9  test    eax, eax
0x1800540eb  js      loc_1800542E3
0x1800540f1  mov     rdx, cs:qword_18003EF28
0x1800540f8  lea     rax, [rbp+Object]
0x1800540fc  mov     [rsp+68h+var_28], rax
0x180054101  lea     r14d, [rcx+1]
0x180054105  mov     [rsp+68h+var_30], ecx
0x180054109  xor     r9d, r9d
0x18005410c  mov     [rsp+68h+var_38], ecx
0x180054110  mov     r8, r15
0x180054113  mov     dword ptr [rsp+68h+Handle], 50h ; 'P'
0x18005411b  mov     [rsp+68h+NewObject], rcx
0x180054120  call    cs:__imp_ObCreateObject
0x180054127  nop     dword ptr [rax+rax+00h]
0x18005412c  mov     r8d, 1F7h
0x180054132  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x180054139  mov     ecx, eax
0x18005413b  xor     r9d, r9d
0x18005413e  mov     ebx, eax
0x180054140  call    FltpDbgStatus
0x180054145  test    eax, eax
0x180054147  js      loc_1800542E3
0x18005414d  mov     rcx, [rbp+Object]; void *
0x180054151  lea     r8d, [r14+4Fh]; Size
0x180054155  xor     edx, edx; Val
0x180054157  call    memset
0x18005415c  lock add [rdi+4], r14d
0x180054161  mov     rax, [rbp+Object]
0x180054165  mov     [rax+30h], rdi
0x180054169  mov     rax, [rbp+Object]
0x18005416d  mov     [rax+48h], esi
0x180054170  cmp     qword ptr [rdi+0F0h], 0
0x180054178  jnz     short loc_1800541BA
0x18005417a  mov     rax, [rbp+Object]
0x18005417e  mov     rcx, [rbp+arg_20]
0x180054182  mov     [rax+38h], r12
0x180054186  mov     rax, [rbp+Object]
0x18005418a  mov     [rax+10h], rcx
0x18005418e  mov     rax, [rbp+Object]
0x180054192  mov     rcx, [rbp+arg_28]
0x180054196  mov     [rax+18h], rcx
0x18005419a  mov     rax, [rbp+Object]
0x18005419e  mov     rcx, [rbp+arg_30]
0x1800541a2  mov     [rax+20h], rcx
0x1800541a6  mov     rax, [rbp+Object]
0x1800541aa  mov     rcx, [rbp+arg_38]
0x1800541b1  mov     [rax+28h], rcx
0x1800541b5  jmp     loc_180054260
0x1800541ba  mov     edx, 30h ; '0'
0x1800541bf  mov     ecx, 100h
0x1800541c4  mov     r8d, 6A764D46h
0x1800541ca  call    cs:__imp_ExAllocatePool2
0x1800541d1  nop     dword ptr [rax+rax+00h]
0x1800541d6  mov     rdx, rax
0x1800541d9  test    rax, rax
0x1800541dc  jnz     short loc_1800541E8
0x1800541de  mov     ebx, 0C000009Ah
0x1800541e3  jmp     loc_1800542E3
0x1800541e8  mov     rcx, [rbp+arg_30]
0x1800541ec  lea     r9, FltpvConnectionNotify
0x1800541f3  mov     r8, [rbp+arg_38]
0x1800541fa  mov     [rax+8], r12
0x1800541fe  mov     [rax], rdi
0x180054201  mov     rax, [rbp+arg_20]
0x180054205  mov     [rdx+10h], rax
0x180054209  mov     rax, [rbp+arg_28]
0x18005420d  mov     [rdx+18h], rax
0x180054211  mov     [rdx+20h], rcx
0x180054215  mov     [rdx+28h], r8
0x180054219  mov     rax, [rbp+Object]
0x18005421d  mov     [rax+10h], r9
0x180054221  lea     r9, FltpvDisconnectNotify
0x180054228  mov     rax, [rbp+Object]
0x18005422c  mov     [rax+18h], r9
0x180054230  test    rcx, rcx
0x180054233  jz      short loc_180054244
0x180054235  mov     rax, [rbp+Object]
0x180054239  lea     rcx, FltpvMessageNotify
0x180054240  mov     [rax+20h], rcx
0x180054244  test    r8, r8
0x180054247  jz      short loc_180054258
0x180054249  mov     rax, [rbp+Object]
0x18005424d  lea     rcx, FltpvMessageNotify2
0x180054254  mov     [rax+28h], rcx
0x180054258  mov     rax, [rbp+Object]
0x18005425c  mov     [rax+38h], rdx
0x180054260  mov     rsi, [rbp+Object]
0x180054264  lea     rbx, [rdi+210h]
0x18005426b  mov     rcx, rbx; FastMutex
0x18005426e  call    cs:__imp_ExAcquireFastMutex
0x180054275  nop     dword ptr [rax+rax+00h]
0x18005427a  test    [rbx+48h], r14b
0x18005427e  jnz     short loc_1800542A6
0x180054280  add     dword ptr [rbx+48h], 2
0x180054284  lea     rax, [rbx+38h]
0x180054288  mov     rcx, [rax+8]
0x18005428c  cmp     [rcx], rax
0x18005428f  jz      short loc_180054298
0x180054291  mov     ecx, 3
0x180054296  int     29h; Win8: RtlFailFast(ecx)
0x180054298  mov     [rsi], rax
0x18005429b  mov     [rsi+8], rcx
0x18005429f  mov     [rcx], rsi
0x1800542a2  mov     [rax+8], rsi
0x1800542a6  mov     rcx, rbx; FastMutex
0x1800542a9  call    cs:__imp_ExReleaseFastMutex
0x1800542b0  nop     dword ptr [rax+rax+00h]
0x1800542b5  mov     rcx, [rbp+Object]; Object
0x1800542b9  xor     r9d, r9d; ObjectPointerBias
0x1800542bc  xor     edx, edx; PassedAccessState
0x1800542be  mov     [rsp+68h+Handle], r13; Handle
0x1800542c3  mov     r8d, 1F0001h; DesiredAccess
0x1800542c9  mov     [rsp+68h+NewObject], 0; NewObject
0x1800542d2  xor     r14b, r14b
0x1800542d5  call    cs:__imp_ObInsertObject
0x1800542dc  nop     dword ptr [rax+rax+00h]
0x1800542e1  mov     ebx, eax
0x1800542e3  mov     r8d, 262h
0x1800542e9  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x1800542f0  xor     r9d, r9d
0x1800542f3  mov     ecx, ebx
0x1800542f5  call    FltpDbgStatus
0x1800542fa  test    eax, eax
0x1800542fc  jns     short loc_18005430B
0x1800542fe  test    r14b, r14b
0x180054301  jz      short loc_18005430B
0x180054303  mov     rcx, rdi; FltObject
0x180054306  call    FltObjectDereference
0x18005430b  mov     eax, ebx
0x18005430d  add     rsp, 68h
0x180054311  pop     r15
0x180054313  pop     r14
0x180054315  pop     r13
0x180054317  pop     r12
0x180054319  pop     rdi
0x18005431a  pop     rsi
0x18005431b  pop     rbx
0x18005431c  pop     rbp
0x18005431d  retn
```
