# ApplyQoSPoliciesOnLink

- ea: `0x140011064`
- end: `0x1400112c8`
- name: `ApplyQoSPoliciesOnLink`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140011850`

## callees

- `0x14000a290`
- `0x140011064`
- `0x140011ed4`
- `0x140013a30`
- `0x140013b68`
- `0x140013bc4`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001118e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001118e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400110e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400110e8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400110fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400110fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001129a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001129a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400112a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400112a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001127e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001127e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001113c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001113c`

## pseudocode

```c
__int64 __fastcall ApplyQoSPoliciesOnLink(__int64 a1, _DWORD *a2)
{
  int v4; // edi
  __int64 i; // rbp
  __int64 QoSPolicyFromPolicyIndex; // rax
  unsigned int *v7; // rbx
  unsigned int *v8; // rax
  __int64 v9; // rax
  int v10; // eax
  __int64 j; // rbx
  PVOID v12; // rdx
  PVOID Entry[2]; // [rsp+20h] [rbp-78h]
  __int128 v15; // [rsp+30h] [rbp-68h] BYREF
  __int128 v16; // [rsp+40h] [rbp-58h]
  __int64 v17; // [rsp+50h] [rbp-48h]

  *(_OWORD *)Entry = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
  }
  if ( *(_QWORD *)(a1 + 2448) || *(_QWORD *)(a1 + 2456) )
    return 0;
  v4 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&QoSPolicyResourceLock, 1u);
  for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
  {
    QoSPolicyFromPolicyIndex = BwcFindQoSPolicyFromPolicyIndex((unsigned int)a2[3 * i + 3]);
    v7 = (unsigned int *)QoSPolicyFromPolicyIndex;
    if ( QoSPolicyFromPolicyIndex )
    {
      _InterlockedIncrement((volatile signed __int32 *)(QoSPolicyFromPolicyIndex + 24));
      BwcDereferenceQoSPolicy(QoSPolicyFromPolicyIndex);
    }
    else
    {
      v8 = (unsigned int *)ExAllocateFromNPagedLookasideList(&QoSPolicyList);
      v7 = v8;
      if ( !v8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
        }
        v4 = -1073741670;
        goto LABEL_27;
      }
      Entry[i] = v8;
      memset(v8, 0, 0x50u);
      *((_QWORD *)v7 + 4) = BwcCleanupQoSPolicy;
      v7[2] = a2[3 * i + 2];
      v7[1] = a2[3 * i + 1];
      v7[3] = a2[3 * i + 3];
      KeInitializeSpinLock((PKSPIN_LOCK)v7 + 5);
      v7[14] = 1886613847;
      _InterlockedIncrement((volatile signed __int32 *)v7 + 6);
      v9 = v7[1];
      if ( (_DWORD)v9 )
      {
        v16 = (unsigned __int64)(v9 << 10);
        v17 = 0;
        *(_QWORD *)&v15 = 0;
        v4 = BwcCreateFlow(&v15, v7 + 4);
        if ( v4 < 0 )
          goto LABEL_27;
        *v7 = 1;
      }
      v4 = BwcAddQoSPolicyToQoSPoliciesHashTable(v7);
    }
    v10 = a2[3 * i + 2];
    if ( v10 )
    {
      if ( v10 == 1 )
        *(_QWORD *)(a1 + 2456) = v7;
    }
    else
    {
      *(_QWORD *)(a1 + 2448) = v7;
    }
  }
  if ( v4 >= 0 )
    goto LABEL_31;
LABEL_27:
  for ( j = 0; j != 2; ++j )
  {
    v12 = Entry[j];
    if ( v12 )
      ExFreeToNPagedLookasideList(&QoSPolicyList, v12);
  }
LABEL_31:
  ExReleaseResourceLite(&QoSPolicyResourceLock);
  KeLeaveCriticalRegion();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140011064  push    rbx
0x140011066  push    rbp
0x140011067  push    rsi
0x140011068  push    rdi
0x140011069  push    r12
0x14001106b  push    r14
0x14001106d  push    r15
0x14001106f  sub     rsp, 60h
0x140011073  xorps   xmm1, xmm1
0x140011076  xorps   xmm0, xmm0
0x140011079  xor     eax, eax
0x14001107b  mov     r14, rdx
0x14001107e  movups  xmmword ptr [rsp+98h+Entry], xmm0
0x140011083  mov     [rsp+98h+var_48], rax
0x140011088  mov     rsi, rcx
0x14001108b  movups  [rsp+98h+var_68], xmm1
0x140011090  movups  [rsp+98h+var_58], xmm1
0x140011095  mov     rcx, cs:WPP_GLOBAL_Control
0x14001109c  lea     rax, WPP_GLOBAL_Control
0x1400110a3  cmp     rcx, rax
0x1400110a6  jz      short loc_1400110CA
0x1400110a8  mov     eax, [rcx+2Ch]
0x1400110ab  test    al, 20h
0x1400110ad  jz      short loc_1400110CA
0x1400110af  cmp     byte ptr [rcx+29h], 4
0x1400110b3  jb      short loc_1400110CA
0x1400110b5  mov     rcx, [rcx+18h]
0x1400110b9  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x1400110c0  mov     edx, 10h
0x1400110c5  call    WPP_SF_
0x1400110ca  cmp     qword ptr [rsi+990h], 0
0x1400110d2  jnz     loc_1400112B6
0x1400110d8  cmp     qword ptr [rsi+998h], 0
0x1400110e0  jnz     loc_1400112B6
0x1400110e6  xor     edi, edi
0x1400110e8  call    cs:__imp_KeEnterCriticalRegion
0x1400110ef  nop     dword ptr [rax+rax+00h]
0x1400110f4  mov     dl, 1; Wait
0x1400110f6  lea     rcx, QoSPolicyResourceLock; Resource
0x1400110fd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140011104  nop     dword ptr [rax+rax+00h]
0x140011109  xor     ebp, ebp
0x14001110b  cmp     ebp, [r14]
0x14001110e  jnb     loc_140011267
0x140011114  lea     r15, ds:0[rbp*2]
0x14001111c  add     r15, rbp
0x14001111f  mov     ecx, [r14+r15*4+0Ch]
0x140011124  call    BwcFindQoSPolicyFromPolicyIndex
0x140011129  mov     rbx, rax
0x14001112c  test    rax, rax
0x14001112f  jnz     loc_1400111FA
0x140011135  lea     rcx, QoSPolicyList; Lookaside
0x14001113c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140011143  nop     dword ptr [rax+rax+00h]
0x140011148  mov     rbx, rax
0x14001114b  test    rax, rax
0x14001114e  jz      loc_14001122B
0x140011154  xor     edx, edx; Val
0x140011156  mov     [rsp+rbp*8+98h+Entry], rax
0x14001115b  mov     rcx, rax; void *
0x14001115e  lea     r8d, [rdx+50h]; Size
0x140011162  call    memset
0x140011167  lea     rax, BwcCleanupQoSPolicy
0x14001116e  mov     [rbx+20h], rax
0x140011172  lea     rcx, [rbx+28h]; SpinLock
0x140011176  mov     eax, [r14+r15*4+8]
0x14001117b  mov     [rbx+8], eax
0x14001117e  mov     eax, [r14+r15*4+4]
0x140011183  mov     [rbx+4], eax
0x140011186  mov     eax, [r14+r15*4+0Ch]
0x14001118b  mov     [rbx+0Ch], eax
0x14001118e  call    cs:__imp_KeInitializeSpinLock
0x140011195  nop     dword ptr [rax+rax+00h]
0x14001119a  mov     dword ptr [rbx+38h], 70737157h
0x1400111a1  lock inc dword ptr [rbx+18h]
0x1400111a5  mov     eax, [rbx+4]
0x1400111a8  test    eax, eax
0x1400111aa  jz      short loc_1400111EE
0x1400111ac  shl     rax, 0Ah
0x1400111b0  lea     rdx, [rbx+10h]
0x1400111b4  lea     rcx, [rsp+98h+var_68]
0x1400111b9  mov     qword ptr [rsp+98h+var_58], rax
0x1400111be  mov     qword ptr [rsp+98h+var_58+8], 0
0x1400111c7  mov     [rsp+98h+var_48], 0
0x1400111d0  mov     qword ptr [rsp+98h+var_68], 0
0x1400111d9  call    BwcCreateFlow
0x1400111de  mov     edi, eax
0x1400111e0  test    eax, eax
0x1400111e2  js      loc_14001126B
0x1400111e8  mov     dword ptr [rbx], 1
0x1400111ee  mov     rcx, rbx
0x1400111f1  call    BwcAddQoSPolicyToQoSPoliciesHashTable
0x1400111f6  mov     edi, eax
0x1400111f8  jmp     short loc_140011206
0x1400111fa  lock inc dword ptr [rax+18h]
0x1400111fe  mov     rcx, rax
0x140011201  call    BwcDereferenceQoSPolicy
0x140011206  mov     eax, [r14+r15*4+8]
0x14001120b  test    eax, eax
0x14001120d  jnz     short loc_140011218
0x14001120f  mov     [rsi+990h], rbx
0x140011216  jmp     short loc_140011224
0x140011218  cmp     eax, 1
0x14001121b  jnz     short loc_140011224
0x14001121d  mov     [rsi+998h], rbx
0x140011224  inc     ebp
0x140011226  jmp     loc_14001110B
0x14001122b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011232  lea     rax, WPP_GLOBAL_Control
0x140011239  cmp     rcx, rax
0x14001123c  jz      short loc_140011260
0x14001123e  mov     eax, [rcx+2Ch]
0x140011241  test    al, 20h
0x140011243  jz      short loc_140011260
0x140011245  cmp     byte ptr [rcx+29h], 3
0x140011249  jb      short loc_140011260
0x14001124b  mov     rcx, [rcx+18h]
0x14001124f  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x140011256  mov     edx, 11h
0x14001125b  call    WPP_SF_
0x140011260  mov     edi, 0C000009Ah
0x140011265  jmp     short loc_14001126B
0x140011267  test    edi, edi
0x140011269  jns     short loc_140011293
0x14001126b  xor     ebx, ebx
0x14001126d  mov     rdx, [rsp+rbx*8+98h+Entry]; Entry
0x140011272  test    rdx, rdx
0x140011275  jz      short loc_14001128A
0x140011277  lea     rcx, QoSPolicyList; Lookaside
0x14001127e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140011285  nop     dword ptr [rax+rax+00h]
0x14001128a  inc     rbx
0x14001128d  cmp     rbx, 2
0x140011291  jnz     short loc_14001126D
0x140011293  lea     rcx, QoSPolicyResourceLock; Resource
0x14001129a  call    cs:__imp_ExReleaseResourceLite
0x1400112a1  nop     dword ptr [rax+rax+00h]
0x1400112a6  call    cs:__imp_KeLeaveCriticalRegion
0x1400112ad  nop     dword ptr [rax+rax+00h]
0x1400112b2  mov     eax, edi
0x1400112b4  jmp     short loc_1400112B8
0x1400112b6  xor     eax, eax
0x1400112b8  add     rsp, 60h
0x1400112bc  pop     r15
0x1400112be  pop     r14
0x1400112c0  pop     r12
0x1400112c2  pop     rdi
0x1400112c3  pop     rsi
0x1400112c4  pop     rbp
0x1400112c5  pop     rbx
0x1400112c6  retn
```
