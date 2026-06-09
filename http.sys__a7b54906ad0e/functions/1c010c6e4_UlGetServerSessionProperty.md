# UlGetServerSessionProperty

- ea: `0x1c010c6e4`
- end: `0x1c010c966`
- name: `UlGetServerSessionProperty`
- size: `642`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, int@<edx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1c011abf0`

## callees

- `0x1c004b684`
- `0x1c008fd30`
- `0x1c00941ec`
- `0x1c00a17c0`
- `0x1c00a8364`
- `0x1c010c6e4`
- `0x1c011938c`
- `0x1c01394e0`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1c010c88d`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010c8a1`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010c88d`
- `ntoskrnl!IoIs32bitProcess` at `0x1c010c8a1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c010c90c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c010c90c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c010c77f`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c010c77f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010c918`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c010c918`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010c76a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c010c76a`

## pseudocode

```c
__int64 __fastcall UlGetServerSessionProperty(
        PIRP Irp,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        unsigned int a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned int v11; // edi
  __int64 v12; // rbx
  __int64 ObjectFromOpaqueId; // rax
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rbx
  int v16; // esi
  int v17; // esi
  int v18; // esi
  int v19; // esi
  int v20; // esi
  unsigned int v21; // eax
  int v23; // [rsp+20h] [rbp-68h]
  __int64 v24; // [rsp+98h] [rbp+10h]
  int v25; // [rsp+A0h] [rbp+18h]

  v25 = a3;
  v11 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qqiLqLqq(33, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids, Irp, a2, a3, a4, a5, a6, a7, a8);
  *a8 = 0;
  v12 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  v24 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v12 + 1360), 0);
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         v25,
                         1,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateServerSession,
                         a2);
  v15 = (volatile signed __int32 *)ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId )
  {
    v11 = -1073741811;
    goto LABEL_29;
  }
  if ( *(_WORD *)(ObjectFromOpaqueId + 16) == 1 && !*(_WORD *)(ObjectFromOpaqueId + 18) )
  {
    v11 = -1073741637;
    goto LABEL_27;
  }
  if ( !a4 )
    goto LABEL_25;
  v16 = a4 - 2;
  if ( !v16 )
  {
    IoIs32bitProcess(Irp);
    if ( !*a5 )
    {
      IoIs32bitProcess(Irp);
      v21 = UlCopyQosSettingInfo(Irp, v23, a7, (__int64)a5, a6, (__int64)a8);
      goto LABEL_26;
    }
    goto LABEL_19;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    if ( a6 >= 0x14 )
    {
      *(_OWORD *)a5 = *(_OWORD *)(ObjectFromOpaqueId + 264);
      a5[4] = *(_DWORD *)(ObjectFromOpaqueId + 280);
      *a8 = 20;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
  v18 = v17 - 2;
  if ( !v18 )
  {
    if ( a6 >= 8 )
    {
      *(_QWORD *)a5 = *(_QWORD *)(ObjectFromOpaqueId + 92);
      *a8 += 8;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
  v19 = v18 - 3;
  if ( !v19 )
  {
LABEL_25:
    v21 = UlCopyAuthConfigToIrp(v14, ObjectFromOpaqueId + 296, Irp, a8);
    goto LABEL_26;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    if ( a6 >= 8 )
    {
      *(_QWORD *)a5 = *(_QWORD *)(ObjectFromOpaqueId + 284);
      *a8 = 8;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
  if ( v20 != 1 )
  {
LABEL_19:
    v11 = -1073741811;
    goto LABEL_27;
  }
  v21 = UlCopyChannelBindConfigToIrp(ObjectFromOpaqueId + 376, Irp, a8);
LABEL_26:
  v11 = v21;
LABEL_27:
  if ( _InterlockedExchangeAdd(v15 + 1, 0xFFFFFFFF) == 1 )
    UlFreeServerSession((PVOID)v15);
LABEL_29:
  ExReleaseCacheAwarePushLockSharedEx(v24, 0);
  KeLeaveCriticalRegion();
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qLd(34, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids, a5, (unsigned int)*a8, v11);
  return v11;
}

```

## disassembly

```asm
0x1c010c6e4  mov     r11, rsp
0x1c010c6e7  mov     [r11+8], rbx
0x1c010c6eb  mov     [r11+18h], r8
0x1c010c6ef  push    rbp
0x1c010c6f0  push    rsi
0x1c010c6f1  push    rdi
0x1c010c6f2  push    r12
0x1c010c6f4  push    r13
0x1c010c6f6  push    r14
0x1c010c6f8  push    r15
0x1c010c6fa  sub     rsp, 50h
0x1c010c6fe  mov     esi, r9d
0x1c010c701  mov     r13, rdx
0x1c010c704  mov     rbp, rcx
0x1c010c707  xor     edi, edi
0x1c010c709  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c010c713  mov     r14, [rsp+88h+arg_38]
0x1c010c71b  mov     r12d, [rsp+88h+arg_28]
0x1c010c723  mov     r15, [rsp+88h+arg_20]
0x1c010c72b  jz      short loc_1C010C763
0x1c010c72d  mov     rax, [rsp+88h+arg_30]
0x1c010c735  lea     ecx, [rdi+21h]
0x1c010c738  mov     [r11-40h], r14
0x1c010c73c  mov     [r11-48h], rax
0x1c010c740  mov     [r11-50h], r12d
0x1c010c744  mov     [r11-58h], r15
0x1c010c748  mov     dword ptr [rsp+88h+var_60], r9d
0x1c010c74d  mov     r9, rdx
0x1c010c750  mov     [r11-68h], r8
0x1c010c754  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010c75b  mov     r8, rbp
0x1c010c75e  call    WPP_SF_qqiLqLqq
0x1c010c763  mov     [r14], edi
0x1c010c766  mov     rbx, [r13+38h]
0x1c010c76a  call    cs:__imp_KeEnterCriticalRegion
0x1c010c771  nop     dword ptr [rax+rax+00h]
0x1c010c776  mov     rcx, [rbx+550h]
0x1c010c77d  xor     edx, edx
0x1c010c77f  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c010c786  nop     dword ptr [rax+rax+00h]
0x1c010c78b  mov     rcx, [rsp+88h+arg_10]
0x1c010c793  lea     r9, UlValidateServerSession
0x1c010c79a  mov     qword ptr [rsp+88h+var_68], r13; int
0x1c010c79f  lea     r8, UlReferenceServerSession
0x1c010c7a6  mov     r13d, 1
0x1c010c7ac  mov     [rsp+88h+arg_8], rax
0x1c010c7b4  mov     edx, r13d
0x1c010c7b7  call    UxGetObjectFromOpaqueId
0x1c010c7bc  mov     rbx, rax
0x1c010c7bf  test    rax, rax
0x1c010c7c2  jnz     short loc_1C010C7CE
0x1c010c7c4  mov     edi, 0C000000Dh
0x1c010c7c9  jmp     loc_1C010C902
0x1c010c7ce  cmp     r13w, [rax+10h]
0x1c010c7d3  jnz     short loc_1C010C7E5
0x1c010c7d5  cmp     di, [rax+12h]
0x1c010c7d9  jnz     short loc_1C010C7E5
0x1c010c7db  mov     edi, 0C00000BBh
0x1c010c7e0  jmp     loc_1C010C8ED
0x1c010c7e5  test    esi, esi
0x1c010c7e7  jz      loc_1C010C8D9
0x1c010c7ed  sub     esi, 2
0x1c010c7f0  jz      loc_1C010C88A
0x1c010c7f6  sub     esi, r13d
0x1c010c7f9  jz      short loc_1C010C866
0x1c010c7fb  sub     esi, 2
0x1c010c7fe  jz      short loc_1C010C846
0x1c010c800  sub     esi, 3
0x1c010c803  jz      loc_1C010C8D9
0x1c010c809  sub     esi, r13d
0x1c010c80c  jz      short loc_1C010C82A
0x1c010c80e  cmp     esi, r13d
0x1c010c811  jnz     short loc_1C010C84C
0x1c010c813  lea     rcx, [rax+178h]
0x1c010c81a  mov     r8, r14
0x1c010c81d  mov     rdx, rbp
0x1c010c820  call    UlCopyChannelBindConfigToIrp
0x1c010c825  jmp     loc_1C010C8EB
0x1c010c82a  cmp     r12d, 8
0x1c010c82e  jb      short loc_1C010C84C
0x1c010c830  mov     rax, [rax+11Ch]
0x1c010c837  mov     [r15], rax
0x1c010c83a  mov     dword ptr [r14], 8
0x1c010c841  jmp     loc_1C010C8ED
0x1c010c846  cmp     r12d, 8
0x1c010c84a  jnb     short loc_1C010C856
0x1c010c84c  mov     edi, 0C000000Dh
0x1c010c851  jmp     loc_1C010C8ED
0x1c010c856  mov     rax, [rax+5Ch]
0x1c010c85a  mov     [r15], rax
0x1c010c85d  add     dword ptr [r14], 8
0x1c010c861  jmp     loc_1C010C8ED
0x1c010c866  cmp     r12d, 14h
0x1c010c86a  jb      short loc_1C010C84C
0x1c010c86c  movups  xmm0, xmmword ptr [rax+108h]
0x1c010c873  movups  xmmword ptr [r15], xmm0
0x1c010c877  mov     eax, [rax+118h]
0x1c010c87d  mov     [r15+10h], eax
0x1c010c881  mov     dword ptr [r14], 14h
0x1c010c888  jmp     short loc_1C010C8ED
0x1c010c88a  mov     rcx, rbp; Irp
0x1c010c88d  call    cs:__imp_IoIs32bitProcess
0x1c010c894  nop     dword ptr [rax+rax+00h]
0x1c010c899  cmp     [r15], edi
0x1c010c89c  jnz     short loc_1C010C84C
0x1c010c89e  mov     rcx, rbp; Irp
0x1c010c8a1  call    cs:__imp_IoIs32bitProcess
0x1c010c8a8  nop     dword ptr [rax+rax+00h]
0x1c010c8ad  mov     rax, [rsp+88h+arg_30]
0x1c010c8b5  lea     r8, [rbx+68h]
0x1c010c8b9  mov     [rsp+88h+var_48], r14; __int64
0x1c010c8be  xor     edx, edx
0x1c010c8c0  mov     [rsp+88h+var_50], r12d; int
0x1c010c8c5  mov     rcx, rbp; Irp
0x1c010c8c8  mov     [rsp+88h+var_58], r15; __int64
0x1c010c8cd  mov     [rsp+88h+var_60], rax; __int64
0x1c010c8d2  call    UlCopyQosSettingInfo
0x1c010c8d7  jmp     short loc_1C010C8EB
0x1c010c8d9  lea     rdx, [rax+128h]
0x1c010c8e0  mov     r9, r14
0x1c010c8e3  mov     r8, rbp
0x1c010c8e6  call    UlCopyAuthConfigToIrp
0x1c010c8eb  mov     edi, eax
0x1c010c8ed  or      eax, 0FFFFFFFFh
0x1c010c8f0  lock xadd [rbx+4], eax
0x1c010c8f5  cmp     eax, r13d
0x1c010c8f8  jnz     short loc_1C010C902
0x1c010c8fa  mov     rcx, rbx; P
0x1c010c8fd  call    UlFreeServerSession
0x1c010c902  mov     rcx, [rsp+88h+arg_8]
0x1c010c90a  xor     edx, edx
0x1c010c90c  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c010c913  nop     dword ptr [rax+rax+00h]
0x1c010c918  call    cs:__imp_KeLeaveCriticalRegion
0x1c010c91f  nop     dword ptr [rax+rax+00h]
0x1c010c924  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c010c92e  jz      short loc_1C010C94B
0x1c010c930  mov     r9d, [r14]
0x1c010c933  lea     rdx, WPP_b8ffd3ae972b35620541fe70f727c058_Traceguids
0x1c010c93a  mov     ecx, 22h ; '"'
0x1c010c93f  mov     [rsp+88h+var_68], edi
0x1c010c943  mov     r8, r15
0x1c010c946  call    WPP_SF_qLd
0x1c010c94b  mov     rbx, [rsp+88h+arg_0]
0x1c010c953  mov     eax, edi
0x1c010c955  add     rsp, 50h
0x1c010c959  pop     r15
0x1c010c95b  pop     r14
0x1c010c95d  pop     r13
0x1c010c95f  pop     r12
0x1c010c961  pop     rdi
0x1c010c962  pop     rsi
0x1c010c963  pop     rbp
0x1c010c964  retn
```
