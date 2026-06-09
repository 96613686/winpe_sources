# UlGetServerSessionProperty

- ea: `0x1400d7494`
- end: `0x1400d7741`
- name: `UlGetServerSessionProperty`
- size: `685`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, int@<edx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400f1040`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x1400d737c`
- `0x1400d7494`
- `0x1400ef04c`
- `0x1401433d8`
- `0x1401439cc`
- `0x1401c9590`
- `0x1401da4fc`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d7645`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7659`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7645`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7659`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7533`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d7533`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d76e8`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d76e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d76f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d76f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d751e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d751e`

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
  int v9; // r13d
  __int64 v13; // rbx
  __int64 ObjectFromOpaqueId; // rax
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rsi
  unsigned int v17; // ebx
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  unsigned int v23; // eax
  int v24; // eax
  int v26; // [rsp+20h] [rbp-88h]
  __int64 v27; // [rsp+E8h] [rbp+40h]

  v9 = a3;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qqiLqLqq(1033, 33, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, Irp, a2, a3, a4, a5, a6, a7, a8);
  *a8 = 0;
  v13 = *(_QWORD *)(a2 + 56);
  KeEnterCriticalRegion();
  v27 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v13 + 1368), 0);
  ObjectFromOpaqueId = UxGetObjectFromOpaqueId(
                         v9,
                         1,
                         (unsigned int)UlReferenceServerSession,
                         (unsigned int)UlValidateServerSession,
                         a2);
  v16 = (volatile signed __int32 *)ObjectFromOpaqueId;
  if ( !ObjectFromOpaqueId )
  {
    v17 = -1073741811;
    goto LABEL_32;
  }
  if ( *(_WORD *)(ObjectFromOpaqueId + 16) == 1 && !*(_WORD *)(ObjectFromOpaqueId + 18) )
  {
    v17 = -1073741637;
    goto LABEL_27;
  }
  v17 = 0;
  if ( !a4 )
    goto LABEL_25;
  v18 = a4 - 2;
  if ( !v18 )
  {
    IoIs32bitProcess(Irp);
    if ( !*a5 )
    {
      IoIs32bitProcess(Irp);
      v23 = UlCopyQosSettingInfo(Irp, v26, a7, (__int64)a5, a6, (__int64)a8);
      goto LABEL_26;
    }
    goto LABEL_19;
  }
  v19 = v18 - 1;
  if ( !v19 )
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
  v20 = v19 - 2;
  if ( !v20 )
  {
    if ( a6 >= 8 )
    {
      *(_QWORD *)a5 = *(_QWORD *)(ObjectFromOpaqueId + 92);
      *a8 += 8;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
  v21 = v20 - 3;
  if ( !v21 )
  {
LABEL_25:
    v23 = UlCopyAuthConfigToIrp(v15, ObjectFromOpaqueId + 296, Irp, a8);
    goto LABEL_26;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    if ( a6 >= 8 )
    {
      *(_QWORD *)a5 = *(_QWORD *)(ObjectFromOpaqueId + 284);
      *a8 = 8;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
  if ( v22 != 1 )
  {
LABEL_19:
    v17 = -1073741811;
    goto LABEL_27;
  }
  v23 = UlCopyChannelBindConfigToIrp(
          *(_QWORD *)(*(_QWORD *)(ObjectFromOpaqueId + 24) + 56LL),
          ObjectFromOpaqueId + 376,
          Irp,
          a8);
LABEL_26:
  v17 = v23;
LABEL_27:
  v24 = _InterlockedDecrement(v16 + 1);
  if ( UxDebugCheckRefcount && v24 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v16 + 1), 0xBu, v24);
  if ( !v24 )
    UlFreeServerSession((PVOID)v16);
LABEL_32:
  ExReleaseCacheAwarePushLockSharedEx(v27, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qLd(1033, 34, WPP_77b773efe445301db38c0738c64be0c3_Traceguids, a5, *a8, v17);
  return v17;
}

```

## disassembly

```asm
0x1400d7494  mov     r11, rsp
0x1400d7497  push    rbx
0x1400d7498  push    rbp
0x1400d7499  push    rsi
0x1400d749a  push    rdi
0x1400d749b  push    r12
0x1400d749d  push    r13
0x1400d749f  push    r14
0x1400d74a1  push    r15
0x1400d74a3  sub     rsp, 68h
0x1400d74a7  mov     edi, r9d
0x1400d74aa  mov     r13, r8
0x1400d74ad  mov     rsi, rdx
0x1400d74b0  mov     rbp, rcx
0x1400d74b3  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d74ba  mov     r14, [rsp+0A8h+arg_38]
0x1400d74c2  mov     r12d, [rsp+0A8h+arg_28]
0x1400d74ca  mov     r15, [rsp+0A8h+arg_20]
0x1400d74d2  jz      short loc_1400D7513
0x1400d74d4  mov     rax, [rsp+0A8h+arg_30]
0x1400d74dc  mov     edx, 21h ; '!'
0x1400d74e1  mov     [r11-58h], r14
0x1400d74e5  mov     ecx, 409h
0x1400d74ea  mov     [r11-60h], rax
0x1400d74ee  mov     [r11-68h], r12d
0x1400d74f2  mov     [r11-70h], r15
0x1400d74f6  mov     dword ptr [rsp+0A8h+var_78], r9d
0x1400d74fb  mov     r9, rbp
0x1400d74fe  mov     [r11-80h], r8
0x1400d7502  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7509  mov     qword ptr [rsp+0A8h+var_88], rsi
0x1400d750e  call    WPP_SF_qqiLqLqq
0x1400d7513  mov     dword ptr [r14], 0
0x1400d751a  mov     rbx, [rsi+38h]
0x1400d751e  call    cs:__imp_KeEnterCriticalRegion
0x1400d7525  nop     dword ptr [rax+rax+00h]
0x1400d752a  mov     rcx, [rbx+558h]
0x1400d7531  xor     edx, edx
0x1400d7533  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d753a  nop     dword ptr [rax+rax+00h]
0x1400d753f  mov     ebx, 1
0x1400d7544  mov     qword ptr [rsp+0A8h+var_88], rsi; int
0x1400d7549  mov     edx, ebx
0x1400d754b  mov     [rsp+0A8h+arg_38], rax
0x1400d7553  lea     r9, UlValidateServerSession
0x1400d755a  mov     rcx, r13
0x1400d755d  lea     r8, UlReferenceServerSession
0x1400d7564  call    UxGetObjectFromOpaqueId
0x1400d7569  mov     rsi, rax
0x1400d756c  test    rax, rax
0x1400d756f  jnz     short loc_1400D757B
0x1400d7571  mov     ebx, 0C000000Dh
0x1400d7576  jmp     loc_1400D76DE
0x1400d757b  cmp     bx, [rax+10h]
0x1400d757f  jnz     short loc_1400D7593
0x1400d7581  xor     eax, eax
0x1400d7583  cmp     ax, [rsi+12h]
0x1400d7587  jnz     short loc_1400D7593
0x1400d7589  mov     ebx, 0C00000BBh
0x1400d758e  jmp     loc_1400D76A5
0x1400d7593  xor     ebx, ebx
0x1400d7595  test    edi, edi
0x1400d7597  jz      loc_1400D7691
0x1400d759d  sub     edi, 2
0x1400d75a0  jz      loc_1400D7642
0x1400d75a6  sub     edi, 1
0x1400d75a9  jz      short loc_1400D761E
0x1400d75ab  sub     edi, 2
0x1400d75ae  jz      short loc_1400D75FE
0x1400d75b0  sub     edi, 3
0x1400d75b3  jz      loc_1400D7691
0x1400d75b9  sub     edi, 1
0x1400d75bc  jz      short loc_1400D75E2
0x1400d75be  cmp     edi, 1
0x1400d75c1  jnz     short loc_1400D7604
0x1400d75c3  mov     rcx, [rsi+18h]
0x1400d75c7  lea     rdx, [rsi+178h]
0x1400d75ce  mov     r9, r14
0x1400d75d1  mov     r8, rbp
0x1400d75d4  mov     rcx, [rcx+38h]
0x1400d75d8  call    UlCopyChannelBindConfigToIrp
0x1400d75dd  jmp     loc_1400D76A3
0x1400d75e2  cmp     r12d, 8
0x1400d75e6  jb      short loc_1400D7604
0x1400d75e8  mov     rax, [rsi+11Ch]
0x1400d75ef  mov     [r15], rax
0x1400d75f2  mov     dword ptr [r14], 8
0x1400d75f9  jmp     loc_1400D76A5
0x1400d75fe  cmp     r12d, 8
0x1400d7602  jnb     short loc_1400D760E
0x1400d7604  mov     ebx, 0C000000Dh
0x1400d7609  jmp     loc_1400D76A5
0x1400d760e  mov     rax, [rsi+5Ch]
0x1400d7612  mov     [r15], rax
0x1400d7615  add     dword ptr [r14], 8
0x1400d7619  jmp     loc_1400D76A5
0x1400d761e  cmp     r12d, 14h
0x1400d7622  jb      short loc_1400D7604
0x1400d7624  movups  xmm0, xmmword ptr [rsi+108h]
0x1400d762b  movups  xmmword ptr [r15], xmm0
0x1400d762f  mov     eax, [rsi+118h]
0x1400d7635  mov     [r15+10h], eax
0x1400d7639  mov     dword ptr [r14], 14h
0x1400d7640  jmp     short loc_1400D76A5
0x1400d7642  mov     rcx, rbp; Irp
0x1400d7645  call    cs:__imp_IoIs32bitProcess
0x1400d764c  nop     dword ptr [rax+rax+00h]
0x1400d7651  cmp     [r15], ebx
0x1400d7654  jnz     short loc_1400D7604
0x1400d7656  mov     rcx, rbp; Irp
0x1400d7659  call    cs:__imp_IoIs32bitProcess
0x1400d7660  nop     dword ptr [rax+rax+00h]
0x1400d7665  mov     rax, [rsp+0A8h+arg_30]
0x1400d766d  lea     r8, [rsi+68h]
0x1400d7671  mov     [rsp+0A8h+var_68], r14; __int64
0x1400d7676  xor     edx, edx
0x1400d7678  mov     [rsp+0A8h+var_70], r12d; int
0x1400d767d  mov     rcx, rbp; Irp
0x1400d7680  mov     [rsp+0A8h+var_78], r15; __int64
0x1400d7685  mov     [rsp+0A8h+var_80], rax; __int64
0x1400d768a  call    UlCopyQosSettingInfo
0x1400d768f  jmp     short loc_1400D76A3
0x1400d7691  lea     rdx, [rsi+128h]
0x1400d7698  mov     r9, r14
0x1400d769b  mov     r8, rbp
0x1400d769e  call    UlCopyAuthConfigToIrp
0x1400d76a3  mov     ebx, eax
0x1400d76a5  lea     rdx, [rsi+4]; BugCheckParameter2
0x1400d76a9  or      eax, 0FFFFFFFFh
0x1400d76ac  lock xadd [rdx], eax
0x1400d76b0  dec     eax
0x1400d76b2  cmp     cs:UxDebugCheckRefcount, 0
0x1400d76b9  jz      short loc_1400D76D2
0x1400d76bb  cmp     eax, 0FFFFFFFFh
0x1400d76be  jg      short loc_1400D76D2
0x1400d76c0  mov     ecx, 3; BugCheckParameter1
0x1400d76c5  movsxd  r9, eax; BugCheckParameter4
0x1400d76c8  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d76cc  call    UlBugCheckEx
0x1400d76d2  test    eax, eax
0x1400d76d4  jnz     short loc_1400D76DE
0x1400d76d6  mov     rcx, rsi; P
0x1400d76d9  call    UlFreeServerSession
0x1400d76de  mov     rcx, [rsp+0A8h+arg_38]
0x1400d76e6  xor     edx, edx
0x1400d76e8  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d76ef  nop     dword ptr [rax+rax+00h]
0x1400d76f4  call    cs:__imp_KeLeaveCriticalRegion
0x1400d76fb  nop     dword ptr [rax+rax+00h]
0x1400d7700  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d7707  jz      short loc_1400D772D
0x1400d7709  mov     eax, [r14]
0x1400d770c  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d7713  mov     edx, 22h ; '"'
0x1400d7718  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1400d771c  mov     ecx, 409h
0x1400d7721  mov     [rsp+0A8h+var_88], eax
0x1400d7725  mov     r9, r15
0x1400d7728  call    WPP_SF_qLd
0x1400d772d  mov     eax, ebx
0x1400d772f  add     rsp, 68h
0x1400d7733  pop     r15
0x1400d7735  pop     r14
0x1400d7737  pop     r13
0x1400d7739  pop     r12
0x1400d773b  pop     rdi
0x1400d773c  pop     rsi
0x1400d773d  pop     rbp
0x1400d773e  pop     rbx
0x1400d773f  retn
```
