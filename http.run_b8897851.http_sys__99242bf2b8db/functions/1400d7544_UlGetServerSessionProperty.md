# UlGetServerSessionProperty

- ea: `0x1400d7544`
- end: `0x1400d77f1`
- name: `UlGetServerSessionProperty`
- size: `685`
- prototype: `__int64 __usercall@<rax>(PIRP Irp@<rcx>, int@<edx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400f1010`

## callees

- `0x14000a350`
- `0x1400193f8`
- `0x1400d742c`
- `0x1400d7544`
- `0x1400ef01c`
- `0x1401432e8`
- `0x1401438dc`
- `0x1401c9590`
- `0x1401da4fc`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400d76f5`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7709`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d76f5`
- `ntoskrnl!IoIs32bitProcess` at `0x1400d7709`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d75e3`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400d75e3`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7798`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400d7798`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d77a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d77a4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d75ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d75ce`

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
0x1400d7544  mov     r11, rsp
0x1400d7547  push    rbx
0x1400d7548  push    rbp
0x1400d7549  push    rsi
0x1400d754a  push    rdi
0x1400d754b  push    r12
0x1400d754d  push    r13
0x1400d754f  push    r14
0x1400d7551  push    r15
0x1400d7553  sub     rsp, 68h
0x1400d7557  mov     edi, r9d
0x1400d755a  mov     r13, r8
0x1400d755d  mov     rsi, rdx
0x1400d7560  mov     rbp, rcx
0x1400d7563  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d756a  mov     r14, [rsp+0A8h+arg_38]
0x1400d7572  mov     r12d, [rsp+0A8h+arg_28]
0x1400d757a  mov     r15, [rsp+0A8h+arg_20]
0x1400d7582  jz      short loc_1400D75C3
0x1400d7584  mov     rax, [rsp+0A8h+arg_30]
0x1400d758c  mov     edx, 21h ; '!'
0x1400d7591  mov     [r11-58h], r14
0x1400d7595  mov     ecx, 409h
0x1400d759a  mov     [r11-60h], rax
0x1400d759e  mov     [r11-68h], r12d
0x1400d75a2  mov     [r11-70h], r15
0x1400d75a6  mov     dword ptr [rsp+0A8h+var_78], r9d
0x1400d75ab  mov     r9, rbp
0x1400d75ae  mov     [r11-80h], r8
0x1400d75b2  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d75b9  mov     qword ptr [rsp+0A8h+var_88], rsi
0x1400d75be  call    WPP_SF_qqiLqLqq
0x1400d75c3  mov     dword ptr [r14], 0
0x1400d75ca  mov     rbx, [rsi+38h]
0x1400d75ce  call    cs:__imp_KeEnterCriticalRegion
0x1400d75d5  nop     dword ptr [rax+rax+00h]
0x1400d75da  mov     rcx, [rbx+558h]
0x1400d75e1  xor     edx, edx
0x1400d75e3  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1400d75ea  nop     dword ptr [rax+rax+00h]
0x1400d75ef  mov     ebx, 1
0x1400d75f4  mov     qword ptr [rsp+0A8h+var_88], rsi; int
0x1400d75f9  mov     edx, ebx
0x1400d75fb  mov     [rsp+0A8h+arg_38], rax
0x1400d7603  lea     r9, UlValidateServerSession
0x1400d760a  mov     rcx, r13
0x1400d760d  lea     r8, UlReferenceServerSession
0x1400d7614  call    UxGetObjectFromOpaqueId
0x1400d7619  mov     rsi, rax
0x1400d761c  test    rax, rax
0x1400d761f  jnz     short loc_1400D762B
0x1400d7621  mov     ebx, 0C000000Dh
0x1400d7626  jmp     loc_1400D778E
0x1400d762b  cmp     bx, [rax+10h]
0x1400d762f  jnz     short loc_1400D7643
0x1400d7631  xor     eax, eax
0x1400d7633  cmp     ax, [rsi+12h]
0x1400d7637  jnz     short loc_1400D7643
0x1400d7639  mov     ebx, 0C00000BBh
0x1400d763e  jmp     loc_1400D7755
0x1400d7643  xor     ebx, ebx
0x1400d7645  test    edi, edi
0x1400d7647  jz      loc_1400D7741
0x1400d764d  sub     edi, 2
0x1400d7650  jz      loc_1400D76F2
0x1400d7656  sub     edi, 1
0x1400d7659  jz      short loc_1400D76CE
0x1400d765b  sub     edi, 2
0x1400d765e  jz      short loc_1400D76AE
0x1400d7660  sub     edi, 3
0x1400d7663  jz      loc_1400D7741
0x1400d7669  sub     edi, 1
0x1400d766c  jz      short loc_1400D7692
0x1400d766e  cmp     edi, 1
0x1400d7671  jnz     short loc_1400D76B4
0x1400d7673  mov     rcx, [rsi+18h]
0x1400d7677  lea     rdx, [rsi+178h]
0x1400d767e  mov     r9, r14
0x1400d7681  mov     r8, rbp
0x1400d7684  mov     rcx, [rcx+38h]
0x1400d7688  call    UlCopyChannelBindConfigToIrp
0x1400d768d  jmp     loc_1400D7753
0x1400d7692  cmp     r12d, 8
0x1400d7696  jb      short loc_1400D76B4
0x1400d7698  mov     rax, [rsi+11Ch]
0x1400d769f  mov     [r15], rax
0x1400d76a2  mov     dword ptr [r14], 8
0x1400d76a9  jmp     loc_1400D7755
0x1400d76ae  cmp     r12d, 8
0x1400d76b2  jnb     short loc_1400D76BE
0x1400d76b4  mov     ebx, 0C000000Dh
0x1400d76b9  jmp     loc_1400D7755
0x1400d76be  mov     rax, [rsi+5Ch]
0x1400d76c2  mov     [r15], rax
0x1400d76c5  add     dword ptr [r14], 8
0x1400d76c9  jmp     loc_1400D7755
0x1400d76ce  cmp     r12d, 14h
0x1400d76d2  jb      short loc_1400D76B4
0x1400d76d4  movups  xmm0, xmmword ptr [rsi+108h]
0x1400d76db  movups  xmmword ptr [r15], xmm0
0x1400d76df  mov     eax, [rsi+118h]
0x1400d76e5  mov     [r15+10h], eax
0x1400d76e9  mov     dword ptr [r14], 14h
0x1400d76f0  jmp     short loc_1400D7755
0x1400d76f2  mov     rcx, rbp; Irp
0x1400d76f5  call    cs:__imp_IoIs32bitProcess
0x1400d76fc  nop     dword ptr [rax+rax+00h]
0x1400d7701  cmp     [r15], ebx
0x1400d7704  jnz     short loc_1400D76B4
0x1400d7706  mov     rcx, rbp; Irp
0x1400d7709  call    cs:__imp_IoIs32bitProcess
0x1400d7710  nop     dword ptr [rax+rax+00h]
0x1400d7715  mov     rax, [rsp+0A8h+arg_30]
0x1400d771d  lea     r8, [rsi+68h]
0x1400d7721  mov     [rsp+0A8h+var_68], r14; __int64
0x1400d7726  xor     edx, edx
0x1400d7728  mov     [rsp+0A8h+var_70], r12d; int
0x1400d772d  mov     rcx, rbp; Irp
0x1400d7730  mov     [rsp+0A8h+var_78], r15; __int64
0x1400d7735  mov     [rsp+0A8h+var_80], rax; __int64
0x1400d773a  call    UlCopyQosSettingInfo
0x1400d773f  jmp     short loc_1400D7753
0x1400d7741  lea     rdx, [rsi+128h]
0x1400d7748  mov     r9, r14
0x1400d774b  mov     r8, rbp
0x1400d774e  call    UlCopyAuthConfigToIrp
0x1400d7753  mov     ebx, eax
0x1400d7755  lea     rdx, [rsi+4]; BugCheckParameter2
0x1400d7759  or      eax, 0FFFFFFFFh
0x1400d775c  lock xadd [rdx], eax
0x1400d7760  dec     eax
0x1400d7762  cmp     cs:UxDebugCheckRefcount, 0
0x1400d7769  jz      short loc_1400D7782
0x1400d776b  cmp     eax, 0FFFFFFFFh
0x1400d776e  jg      short loc_1400D7782
0x1400d7770  mov     ecx, 3; BugCheckParameter1
0x1400d7775  movsxd  r9, eax; BugCheckParameter4
0x1400d7778  lea     r8d, [rcx+8]; BugCheckParameter3
0x1400d777c  call    UlBugCheckEx
0x1400d7782  test    eax, eax
0x1400d7784  jnz     short loc_1400D778E
0x1400d7786  mov     rcx, rsi; P
0x1400d7789  call    UlFreeServerSession
0x1400d778e  mov     rcx, [rsp+0A8h+arg_38]
0x1400d7796  xor     edx, edx
0x1400d7798  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1400d779f  nop     dword ptr [rax+rax+00h]
0x1400d77a4  call    cs:__imp_KeLeaveCriticalRegion
0x1400d77ab  nop     dword ptr [rax+rax+00h]
0x1400d77b0  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x1400d77b7  jz      short loc_1400D77DD
0x1400d77b9  mov     eax, [r14]
0x1400d77bc  lea     r8, WPP_77b773efe445301db38c0738c64be0c3_Traceguids
0x1400d77c3  mov     edx, 22h ; '"'
0x1400d77c8  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1400d77cc  mov     ecx, 409h
0x1400d77d1  mov     [rsp+0A8h+var_88], eax
0x1400d77d5  mov     r9, r15
0x1400d77d8  call    WPP_SF_qLd
0x1400d77dd  mov     eax, ebx
0x1400d77df  add     rsp, 68h
0x1400d77e3  pop     r15
0x1400d77e5  pop     r14
0x1400d77e7  pop     r13
0x1400d77e9  pop     r12
0x1400d77eb  pop     rdi
0x1400d77ec  pop     rsi
0x1400d77ed  pop     rbp
0x1400d77ee  pop     rbx
0x1400d77ef  retn
```
