# UlQueryConfigGroupProperty

- ea: `0x1c01097f4`
- end: `0x1c0109ac4`
- name: `UlQueryConfigGroupProperty`
- size: `720`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1c011b4a0`

## callees

- `0x1c00035ac`
- `0x1c004b684`
- `0x1c008fd30`
- `0x1c00941ec`
- `0x1c00a17c0`
- `0x1c01097f4`
- `0x1c011938c`
- `0x1c01394e0`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1c01099c9`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01099df`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01099fb`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01099c9`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01099df`
- `ntoskrnl!IoIs32bitProcess` at `0x1c01099fb`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0109a6c`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c0109a6c`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0109896`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0109896`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0109a78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0109a78`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0109881`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0109881`

## pseudocode

```c
__int64 __fastcall UlQueryConfigGroupProperty(
        PIRP Irp,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        unsigned int a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned int v9; // edi
  __int64 v13; // rbx
  __int64 ObjectFromOpaqueId; // rax
  volatile signed __int32 *v15; // rbx
  int v16; // esi
  int v17; // esi
  int v18; // esi
  int v19; // esi
  int v20; // esi
  int v21; // esi
  __int64 v22; // rax
  unsigned int v23; // eax
  int v25; // [rsp+20h] [rbp-68h]
  int v27; // [rsp+A0h] [rbp+18h]
  __int64 v28; // [rsp+C8h] [rbp+40h]

  v27 = a3;
  v9 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qqiLqLqq(136, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, Irp, a2, a3, a4, a5, a6, a7, a8);
  *a8 = 0;
  v13 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  v28 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v13 + 1360), 0);
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         v27,
                         2,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateConfigGroup,
                         a2);
  v15 = (volatile signed __int32 *)ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId || *(_DWORD *)ObjectFromOpaqueId != 1245932629 )
    goto LABEL_29;
  if ( *(_DWORD *)(*(_QWORD *)(ObjectFromOpaqueId + 48) + 16LL) != 1 )
  {
    if ( a4 )
    {
      v16 = a4 - 2;
      if ( !v16 )
      {
        IoIs32bitProcess(Irp);
        if ( *a5 > 1u )
          goto LABEL_29;
        IoIs32bitProcess(Irp);
        v23 = UlCopyQosSettingInfo(Irp, v25, a7, (__int64)a5, a6, (__int64)a8);
        goto LABEL_28;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        if ( a6 >= 0x14 )
        {
          *(_OWORD *)a5 = *(_OWORD *)(ObjectFromOpaqueId + 272);
          a5[4] = *(_DWORD *)(ObjectFromOpaqueId + 288);
          *a8 = 20;
          goto LABEL_30;
        }
        goto LABEL_29;
      }
      v18 = v17 - 2;
      if ( !v18 )
      {
        if ( a6 >= 8 )
        {
          v22 = *(_QWORD *)(ObjectFromOpaqueId + 56);
          goto LABEL_22;
        }
        goto LABEL_29;
      }
      v19 = v18 - 3;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( !v20 )
        {
          if ( a6 >= 8 )
          {
            v22 = *(_QWORD *)(ObjectFromOpaqueId + 292);
            goto LABEL_22;
          }
LABEL_29:
          v9 = -1073741811;
          goto LABEL_30;
        }
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 == 1 && a6 >= 8 )
          {
            v22 = *(_QWORD *)(ObjectFromOpaqueId + 440);
LABEL_22:
            *(_QWORD *)a5 = v22;
            *a8 = 8;
            goto LABEL_30;
          }
          goto LABEL_29;
        }
        v23 = UlCopyChannelBindConfigToIrp(ObjectFromOpaqueId + 384, Irp, a8);
LABEL_28:
        v9 = v23;
        goto LABEL_30;
      }
    }
    v23 = UlCopyAuthConfigToIrp(0, ObjectFromOpaqueId + 304, Irp, a8);
    goto LABEL_28;
  }
  v9 = -1073741637;
LABEL_30:
  if ( v15 && _InterlockedExchangeAdd(v15 + 1, 0xFFFFFFFF) == 1 )
    UlFreeConfigGroup((PVOID)v15);
  ExReleaseCacheAwarePushLockSharedEx(v28, 0);
  KeLeaveCriticalRegion();
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qLd(137, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, a5, (unsigned int)*a8, v9);
  return v9;
}

```

## disassembly

```asm
0x1c01097f4  mov     r11, rsp
0x1c01097f7  mov     [r11+8], rbx
0x1c01097fb  mov     [r11+18h], r8
0x1c01097ff  mov     [r11+10h], rdx
0x1c0109803  push    rbp
0x1c0109804  push    rsi
0x1c0109805  push    rdi
0x1c0109806  push    r12
0x1c0109808  push    r13
0x1c010980a  push    r14
0x1c010980c  push    r15
0x1c010980e  sub     rsp, 50h
0x1c0109812  xor     eax, eax
0x1c0109814  mov     esi, r9d
0x1c0109817  mov     edi, eax
0x1c0109819  mov     rbx, rdx
0x1c010981c  mov     r12, rcx
0x1c010981f  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109825  mov     r14, [rsp+88h+arg_38]
0x1c010982d  mov     r13, [rsp+88h+arg_30]
0x1c0109835  mov     ebp, [rsp+88h+arg_28]
0x1c010983c  mov     r15, [rsp+88h+arg_20]
0x1c0109844  test    al, 8
0x1c0109846  jz      short loc_1C0109878
0x1c0109848  mov     [r11-40h], r14
0x1c010984c  mov     ecx, 88h
0x1c0109851  mov     [r11-48h], r13
0x1c0109855  mov     [rsp+88h+var_50], ebp
0x1c0109859  mov     [r11-58h], r15
0x1c010985d  mov     dword ptr [rsp+88h+var_60], r9d
0x1c0109862  mov     r9, rdx
0x1c0109865  mov     [r11-68h], r8
0x1c0109869  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109870  mov     r8, r12
0x1c0109873  call    WPP_SF_qqiLqLqq
0x1c0109878  xor     eax, eax
0x1c010987a  mov     [r14], eax
0x1c010987d  mov     rbx, [rbx+38h]
0x1c0109881  call    cs:__imp_KeEnterCriticalRegion
0x1c0109888  nop     dword ptr [rax+rax+00h]
0x1c010988d  mov     rcx, [rbx+550h]
0x1c0109894  xor     edx, edx
0x1c0109896  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c010989d  nop     dword ptr [rax+rax+00h]
0x1c01098a2  mov     rcx, [rsp+88h+arg_10]
0x1c01098aa  lea     r9, UlValidateConfigGroup
0x1c01098b1  mov     [rsp+88h+arg_38], rax
0x1c01098b9  lea     r8, UlReferenceServerSession
0x1c01098c0  mov     rax, qword ptr [rsp+88h+arg_8]
0x1c01098c8  mov     edx, 2
0x1c01098cd  mov     qword ptr [rsp+88h+var_68], rax; int
0x1c01098d2  call    UxGetObjectFromOpaqueId
0x1c01098d7  xor     ecx, ecx
0x1c01098d9  mov     rbx, rax
0x1c01098dc  test    rax, rax
0x1c01098df  jz      loc_1C0109A43
0x1c01098e5  cmp     dword ptr [rax], 4A436C55h
0x1c01098eb  jnz     loc_1C0109A43
0x1c01098f1  mov     rax, [rax+30h]
0x1c01098f5  lea     edx, [rcx+1]
0x1c01098f8  mov     eax, [rax+10h]
0x1c01098fb  cmp     dx, ax
0x1c01098fe  jnz     short loc_1C0109912
0x1c0109900  shr     eax, 10h
0x1c0109903  cmp     cx, ax
0x1c0109906  jnz     short loc_1C0109912
0x1c0109908  mov     edi, 0C00000BBh
0x1c010990d  jmp     loc_1C0109A48
0x1c0109912  test    esi, esi
0x1c0109914  jz      loc_1C0109A2D
0x1c010991a  sub     esi, 2
0x1c010991d  jz      loc_1C01099C6
0x1c0109923  sub     esi, edx
0x1c0109925  jz      short loc_1C010999C
0x1c0109927  sub     esi, 2
0x1c010992a  jz      short loc_1C0109980
0x1c010992c  sub     esi, 3
0x1c010992f  jz      loc_1C0109A2D
0x1c0109935  sub     esi, edx
0x1c0109937  jz      short loc_1C010996E
0x1c0109939  sub     esi, edx
0x1c010993b  jz      short loc_1C0109957
0x1c010993d  cmp     esi, edx
0x1c010993f  jnz     loc_1C0109A43
0x1c0109945  cmp     ebp, 8
0x1c0109948  jb      loc_1C0109A43
0x1c010994e  mov     rax, [rbx+1B8h]
0x1c0109955  jmp     short loc_1C010998D
0x1c0109957  lea     rcx, [rbx+180h]
0x1c010995e  mov     r8, r14
0x1c0109961  mov     rdx, r12
0x1c0109964  call    UlCopyChannelBindConfigToIrp
0x1c0109969  jmp     loc_1C0109A3F
0x1c010996e  cmp     ebp, 8
0x1c0109971  jb      loc_1C0109A43
0x1c0109977  mov     rax, [rbx+124h]
0x1c010997e  jmp     short loc_1C010998D
0x1c0109980  cmp     ebp, 8
0x1c0109983  jb      loc_1C0109A43
0x1c0109989  mov     rax, [rbx+38h]
0x1c010998d  mov     [r15], rax
0x1c0109990  mov     dword ptr [r14], 8
0x1c0109997  jmp     loc_1C0109A48
0x1c010999c  cmp     ebp, 14h
0x1c010999f  jb      loc_1C0109A43
0x1c01099a5  movups  xmm0, xmmword ptr [rbx+110h]
0x1c01099ac  movups  xmmword ptr [r15], xmm0
0x1c01099b0  mov     eax, [rbx+120h]
0x1c01099b6  mov     [r15+10h], eax
0x1c01099ba  mov     dword ptr [r14], 14h
0x1c01099c1  jmp     loc_1C0109A48
0x1c01099c6  mov     rcx, r12; Irp
0x1c01099c9  call    cs:__imp_IoIs32bitProcess
0x1c01099d0  nop     dword ptr [rax+rax+00h]
0x1c01099d5  mov     eax, [r15]
0x1c01099d8  test    eax, eax
0x1c01099da  jnz     short loc_1C01099F3
0x1c01099dc  mov     rcx, r12; Irp
0x1c01099df  call    cs:__imp_IoIs32bitProcess
0x1c01099e6  nop     dword ptr [rax+rax+00h]
0x1c01099eb  lea     r8, [rbx+50h]
0x1c01099ef  xor     edx, edx
0x1c01099f1  jmp     short loc_1C0109A10
0x1c01099f3  cmp     eax, 1
0x1c01099f6  jnz     short loc_1C0109A43
0x1c01099f8  mov     rcx, r12; Irp
0x1c01099fb  call    cs:__imp_IoIs32bitProcess
0x1c0109a02  nop     dword ptr [rax+rax+00h]
0x1c0109a07  lea     r8, [rbx+68h]
0x1c0109a0b  mov     edx, 1
0x1c0109a10  mov     [rsp+88h+var_48], r14; __int64
0x1c0109a15  mov     rcx, r12; Irp
0x1c0109a18  mov     [rsp+88h+var_50], ebp; int
0x1c0109a1c  mov     [rsp+88h+var_58], r15; __int64
0x1c0109a21  mov     [rsp+88h+var_60], r13; __int64
0x1c0109a26  call    UlCopyQosSettingInfo
0x1c0109a2b  jmp     short loc_1C0109A3F
0x1c0109a2d  lea     rdx, [rbx+130h]
0x1c0109a34  mov     r9, r14
0x1c0109a37  mov     r8, r12
0x1c0109a3a  call    UlCopyAuthConfigToIrp
0x1c0109a3f  mov     edi, eax
0x1c0109a41  jmp     short loc_1C0109A48
0x1c0109a43  mov     edi, 0C000000Dh
0x1c0109a48  test    rbx, rbx
0x1c0109a4b  jz      short loc_1C0109A62
0x1c0109a4d  or      eax, 0FFFFFFFFh
0x1c0109a50  lock xadd [rbx+4], eax
0x1c0109a55  cmp     eax, 1
0x1c0109a58  jnz     short loc_1C0109A62
0x1c0109a5a  mov     rcx, rbx; P
0x1c0109a5d  call    UlFreeConfigGroup
0x1c0109a62  mov     rcx, [rsp+88h+arg_38]
0x1c0109a6a  xor     edx, edx
0x1c0109a6c  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c0109a73  nop     dword ptr [rax+rax+00h]
0x1c0109a78  call    cs:__imp_KeLeaveCriticalRegion
0x1c0109a7f  nop     dword ptr [rax+rax+00h]
0x1c0109a84  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0109a8a  test    al, 8
0x1c0109a8c  jz      short loc_1C0109AA9
0x1c0109a8e  mov     r9d, [r14]
0x1c0109a91  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c0109a98  mov     ecx, 89h
0x1c0109a9d  mov     [rsp+88h+var_68], edi
0x1c0109aa1  mov     r8, r15
0x1c0109aa4  call    WPP_SF_qLd
0x1c0109aa9  mov     rbx, [rsp+88h+arg_0]
0x1c0109ab1  mov     eax, edi
0x1c0109ab3  add     rsp, 50h
0x1c0109ab7  pop     r15
0x1c0109ab9  pop     r14
0x1c0109abb  pop     r13
0x1c0109abd  pop     r12
0x1c0109abf  pop     rdi
0x1c0109ac0  pop     rsi
0x1c0109ac1  pop     rbp
0x1c0109ac2  retn
```
