# FltpNamePurgeWorker

- ea: `0x180077380`
- end: `0x1800775ff`
- name: `FltpNamePurgeWorker`
- size: `639`
- prototype: `void __fastcall(PVOID StartContext)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x1800247a0`
- `0x180024c00`
- `0x1800614b0`
- `0x180077380`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800773d6`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1800773d6`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1800774bc`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180077550`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1800774bc`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180077550`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007749e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180077539`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18007749e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180077539`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077520`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077584`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077520`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180077584`
- `ntoskrnl!ExReleaseFastResource` at `0x180077514`
- `ntoskrnl!ExReleaseFastResource` at `0x180077578`
- `ntoskrnl!ExReleaseFastResource` at `0x180077514`
- `ntoskrnl!ExReleaseFastResource` at `0x180077578`
- `ntoskrnl!ExSetTimer` at `0x1800775bb`
- `ntoskrnl!ExSetTimer` at `0x1800775bb`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18007744a`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x18007744a`
- `ntoskrnl!ExCancelTimer` at `0x180077488`
- `ntoskrnl!ExCancelTimer` at `0x180077488`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800775ce`
- `ntoskrnl!PsTerminateSystemThread` at `0x1800775ce`

## string_xrefs

- `0x1800774f4`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c
void __fastcall FltpNamePurgeWorker(PVOID StartContext)
{
  __int64 v1; // rdi
  __int64 v2; // rsi
  NTSTATUS v3; // eax
  int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rbp
  __int64 v7; // r8
  _QWORD *v8; // r14
  _QWORD *v9; // rbx
  _QWORD *v10; // r15
  NTSTATUS v11; // eax
  __int64 v12; // r8
  KPROCESSOR_MODE WaitMode[8]; // [rsp+20h] [rbp-E8h]
  __int64 Alertable; // [rsp+28h] [rbp-E0h]
  _BYTE v15[80]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v16[2]; // [rsp+90h] [rbp-78h] BYREF
  __int128 Object; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v18; // [rsp+B0h] [rbp-58h]

  v18 = 0;
  v1 = 0;
  v2 = 0;
  Object = 0;
  memset(v15, 0, 0x48u);
  ExInitializeFastOwnerEntry(v15);
  *(_QWORD *)&Object = &Event;
  *((_QWORD *)&Object + 1) = &stru_18003FE98;
  v18 = qword_18003FEB0;
  while ( 1 )
  {
    while ( 1 )
    {
      v3 = KeWaitForMultipleObjects(3u, (PVOID *)&Object, WaitAny, Executive, 0, 0, 0, 0);
      if ( v3 )
        break;
      if ( ++v1 >= v2 + 32 )
      {
        ExCancelTimer(qword_18003FEB0, 0);
        goto LABEL_9;
      }
      v16[0] = 0;
      v16[1] = -1;
      ExSetTimer(qword_18003FEB0, -1200000000, 0, v16, *(_QWORD *)WaitMode, Alertable);
    }
    v4 = v3 - 1;
    if ( !v4 )
      break;
    if ( v4 == 1 && v1 > v2 )
    {
LABEL_9:
      v5 = qword_18003E808;
      v2 = v1;
      KeEnterCriticalRegion();
      v6 = v5 + 192;
      LOBYTE(v7) = 1;
      ExAcquireFastResourceShared(v5 + 192, v15, v7);
      v8 = (_QWORD *)(v5 + 296);
      v9 = *(_QWORD **)(v5 + 296);
      while ( v9 != v8 )
      {
        v10 = v9 - 2;
        v11 = FltObjectReference(v9 - 2);
        if ( (int)FltpDbgStatus(v11) >= 0 )
        {
          ExReleaseFastResource(v6, v15);
          KeLeaveCriticalRegion();
          FltpPurgeVolumeNameCache((__int64)(v9 - 2), 0, 1);
          KeEnterCriticalRegion();
          LOBYTE(v12) = 1;
          ExAcquireFastResourceShared(v6, v15, v12);
          v9 = (_QWORD *)*v9;
          FltObjectDereference(v10);
        }
        else
        {
          v9 = (_QWORD *)*v9;
        }
      }
      ExReleaseFastResource(v6, v15);
      KeLeaveCriticalRegion();
    }
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x180077380  mov     r11, rsp
0x180077383  push    rbx
0x180077384  push    rbp
0x180077385  push    rsi
0x180077386  push    rdi
0x180077387  push    r12
0x180077389  push    r13
0x18007738b  push    r14
0x18007738d  push    r15
0x18007738f  sub     rsp, 0C8h
0x180077396  mov     rax, cs:__security_cookie
0x18007739d  xor     rax, rsp
0x1800773a0  mov     [rsp+108h+var_50], rax
0x1800773a8  xor     r12d, r12d
0x1800773ab  lea     rcx, [rsp+108h+var_C8]; void *
0x1800773b0  xorps   xmm0, xmm0
0x1800773b3  xor     eax, eax
0x1800773b5  xor     edx, edx; Val
0x1800773b7  mov     [r11-58h], rax
0x1800773bb  mov     r8d, 48h ; 'H'; Size
0x1800773c1  mov     edi, r12d
0x1800773c4  mov     esi, r12d
0x1800773c7  movups  xmmword ptr [r11-68h], xmm0
0x1800773cc  call    memset
0x1800773d1  lea     rcx, [rsp+108h+var_C8]
0x1800773d6  call    cs:__imp_ExInitializeFastOwnerEntry
0x1800773dd  nop     dword ptr [rax+rax+00h]
0x1800773e2  lea     rax, Event
0x1800773e9  mov     r13d, 1F30h
0x1800773ef  mov     [rsp+108h+Object], rax
0x1800773f7  lea     rax, stru_18003FE98
0x1800773fe  mov     [rsp+108h+var_60], rax
0x180077406  mov     rax, cs:qword_18003FEB0
0x18007740d  mov     [rsp+108h+var_58], rax
0x180077415  nop     word ptr [rax+rax+00000000h]
0x180077420  mov     [rsp+108h+WaitBlockArray], r12; WaitBlockArray
0x180077425  lea     rdx, [rsp+108h+Object]; Object
0x18007742d  mov     [rsp+108h+Timeout], r12; Timeout
0x180077432  xor     r9d, r9d; WaitReason
0x180077435  mov     byte ptr [rsp+108h+Alertable], r12b; Alertable
0x18007743a  mov     r8d, 1; WaitType
0x180077440  mov     ecx, 3; Count
0x180077445  mov     [rsp+108h+WaitMode], r12b; WaitMode
0x18007744a  call    cs:__imp_KeWaitForMultipleObjects
0x180077451  nop     dword ptr [rax+rax+00h]
0x180077456  test    eax, eax
0x180077458  jz      short loc_18007746F
0x18007745a  sub     eax, 1
0x18007745d  jz      loc_1800775CC
0x180077463  cmp     eax, 1
0x180077466  jnz     short loc_180077420
0x180077468  cmp     rdi, rsi
0x18007746b  jle     short loc_180077420
0x18007746d  jmp     short loc_180077494
0x18007746f  mov     rcx, cs:qword_18003FEB0
0x180077476  lea     rax, [rsi+20h]
0x18007747a  inc     rdi
0x18007747d  cmp     rdi, rax
0x180077480  jl      loc_180077595
0x180077486  xor     edx, edx
0x180077488  call    cs:__imp_ExCancelTimer
0x18007748f  nop     dword ptr [rax+rax+00h]
0x180077494  mov     rbx, cs:qword_18003E808
0x18007749b  mov     rsi, rdi
0x18007749e  call    cs:__imp_KeEnterCriticalRegion
0x1800774a5  nop     dword ptr [rax+rax+00h]
0x1800774aa  lea     rbp, [rbx+0C0h]
0x1800774b1  mov     r8b, 1
0x1800774b4  mov     rcx, rbp
0x1800774b7  lea     rdx, [rsp+108h+var_C8]
0x1800774bc  call    cs:__imp_ExAcquireFastResourceShared
0x1800774c3  nop     dword ptr [rax+rax+00h]
0x1800774c8  lea     r14, [rbx+128h]
0x1800774cf  mov     rbx, [r14]
0x1800774d2  cmp     rbx, r14
0x1800774d5  jz      loc_180077570
0x1800774db  lea     r15, [rbx-10h]
0x1800774df  mov     rcx, r15; FltObject
0x1800774e2  call    FltObjectReference
0x1800774e7  mov     ecx, eax
0x1800774e9  mov     qword ptr [rsp+108h+WaitMode], r12
0x1800774ee  mov     r9d, 0C01C000Bh
0x1800774f4  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x1800774fb  mov     r8d, r13d
0x1800774fe  call    FltpDbgStatus
0x180077503  test    eax, eax
0x180077505  jns     short loc_18007750C
0x180077507  mov     rbx, [rbx]
0x18007750a  jmp     short loc_180077567
0x18007750c  lea     rdx, [rsp+108h+var_C8]
0x180077511  mov     rcx, rbp
0x180077514  call    cs:__imp_ExReleaseFastResource
0x18007751b  nop     dword ptr [rax+rax+00h]
0x180077520  call    cs:__imp_KeLeaveCriticalRegion
0x180077527  nop     dword ptr [rax+rax+00h]
0x18007752c  mov     r8b, 1
0x18007752f  xor     edx, edx
0x180077531  mov     rcx, r15
0x180077534  call    FltpPurgeVolumeNameCache
0x180077539  call    cs:__imp_KeEnterCriticalRegion
0x180077540  nop     dword ptr [rax+rax+00h]
0x180077545  mov     r8b, 1
0x180077548  lea     rdx, [rsp+108h+var_C8]
0x18007754d  mov     rcx, rbp
0x180077550  call    cs:__imp_ExAcquireFastResourceShared
0x180077557  nop     dword ptr [rax+rax+00h]
0x18007755c  mov     rbx, [rbx]
0x18007755f  mov     rcx, r15; FltObject
0x180077562  call    FltObjectDereference
0x180077567  cmp     rbx, r14
0x18007756a  jnz     loc_1800774DB
0x180077570  lea     rdx, [rsp+108h+var_C8]
0x180077575  mov     rcx, rbp
0x180077578  call    cs:__imp_ExReleaseFastResource
0x18007757f  nop     dword ptr [rax+rax+00h]
0x180077584  call    cs:__imp_KeLeaveCriticalRegion
0x18007758b  nop     dword ptr [rax+rax+00h]
0x180077590  jmp     loc_180077420
0x180077595  lea     r9, [rsp+108h+var_78]
0x18007759d  mov     [rsp+108h+var_78], r12
0x1800775a5  xor     r8d, r8d
0x1800775a8  mov     [rsp+108h+var_70], 0FFFFFFFFFFFFFFFFh
0x1800775b4  mov     rdx, 0FFFFFFFFB8797400h
0x1800775bb  call    cs:__imp_ExSetTimer
0x1800775c2  nop     dword ptr [rax+rax+00h]
0x1800775c7  jmp     loc_180077420
0x1800775cc  xor     ecx, ecx; ExitStatus
0x1800775ce  call    cs:__imp_PsTerminateSystemThread
0x1800775d5  nop     dword ptr [rax+rax+00h]
0x1800775da  mov     rcx, [rsp+108h+var_50]
0x1800775e2  xor     rcx, rsp; StackCookie
0x1800775e5  call    __security_check_cookie
0x1800775ea  add     rsp, 0C8h
0x1800775f1  pop     r15
0x1800775f3  pop     r14
0x1800775f5  pop     r13
0x1800775f7  pop     r12
0x1800775f9  pop     rdi
0x1800775fa  pop     rsi
0x1800775fb  pop     rbp
0x1800775fc  pop     rbx
0x1800775fd  retn
```
