# Smb2ValidateAndProcessEcpList

- ea: `0x140007470`
- end: `0x14000782e`
- name: `Smb2ValidateAndProcessEcpList`
- size: `958`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140007020`
- `0x140008480`

## callees

- `0x140007470`
- `0x140007840`
- `0x14000a400`
- `0x1400178d0`
- `0x140029764`
- `0x1400297fc`
- `0x14002a9ac`
- `0x140037120`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140038cca`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140038cca`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140038d12`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140038d12`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x140038c94`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x140038cf9`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x140038c94`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x140038cf9`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140038c5e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x140038c5e`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140038d2b`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140038d2b`

## pseudocode

```c
__int64 __fastcall Smb2ValidateAndProcessEcpList(__int64 a1, __int64 a2, unsigned int *a3, unsigned int a4)
{
  int v6; // r15d
  unsigned int v9; // edi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ecx
  unsigned int v14; // r14d
  bool v15; // cc
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v19; // rcx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  bool v22; // zf
  __int64 v23; // r8
  ULONG EcpContextSize; // [rsp+30h] [rbp-68h] BYREF
  PVOID EcpContext; // [rsp+38h] [rbp-60h] BYREF
  __int64 v26; // [rsp+40h] [rbp-58h]
  GUID EcpType; // [rsp+48h] [rbp-50h] BYREF

  v6 = 0;
  v9 = 0;
  v26 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL) + 424LL) + 88LL);
  while ( a3 )
  {
    v10 = a4 - v9;
    if ( *a3 )
      v10 = *a3;
    if ( v9 > a4 )
      return (unsigned int)-1073741629;
    if ( v10 > a4 )
      return (unsigned int)-1073741629;
    v9 += v10;
    if ( v9 > a4 )
      return (unsigned int)-1073741629;
    v11 = *((unsigned __int16 *)a3 + 2);
    if ( ((v11 + 7) & 0xFFFFFFFFFFFFFFF8uLL) != v11 )
      return (unsigned int)-1073741629;
    v12 = *((unsigned __int16 *)a3 + 5);
    if ( ((v12 + 7) & 0xFFFFFFFFFFFFFFF8uLL) != v12 )
      return (unsigned int)-1073741629;
    if ( (unsigned int)v11 > v10 )
      return (unsigned int)-1073741629;
    if ( (unsigned int)v12 > v10 )
      return (unsigned int)-1073741629;
    v13 = *((unsigned __int16 *)a3 + 3);
    if ( v13 > v10 )
      return (unsigned int)-1073741629;
    v14 = a3[3];
    if ( v14 > v10 || v13 + (unsigned int)v11 > v10 || v14 + (unsigned int)v12 > v10 )
      return (unsigned int)-1073741629;
    v15 = (unsigned __int16)v12 <= (unsigned __int16)v11;
    if ( (unsigned __int16)v12 < (unsigned __int16)v11 )
    {
      if ( (unsigned int)v11 < v14 + (unsigned int)v12 )
        return (unsigned int)-1073741629;
      v15 = (unsigned __int16)v12 <= (unsigned __int16)v11;
    }
    if ( !v15 && (unsigned int)v12 < v13 + (unsigned int)v11 )
      return (unsigned int)-1073741629;
    if ( v13 != 4 )
    {
      if ( v13 == 16 )
      {
        v22 = *(_QWORD *)(a1 + 688) == 0;
        EcpType = 0;
        EcpContext = 0;
        EcpContextSize = 0;
        EcpType = *(GUID *)((char *)a3 + v11);
        if ( !v22
          && ((unsigned __int8)Smb2IsKnownPassthroughEcp(&EcpType)
           || (unsigned __int8)Smb2IsKnownVmbusPassthroughEcp(*(_QWORD *)(a1 + 80), &EcpType, 0)) )
        {
          if ( ((unsigned __int8)Smb2IsKnownPassthroughEcp(&EcpType)
             || (LOBYTE(v23) = 1, (unsigned __int8)Smb2IsKnownVmbusPassthroughEcp(*(_QWORD *)(a1 + 80), &EcpType, v23)))
            && FsRtlFindExtraCreateParameter(*(PECP_LIST *)(a1 + 688), &EcpType, &EcpContext, &EcpContextSize) >= 0 )
          {
            if ( a3[3] == EcpContextSize )
            {
              memmove(EcpContext, (char *)a3 + *((unsigned __int16 *)a3 + 5), EcpContextSize);
              FsRtlAcknowledgeEcp(EcpContext);
            }
          }
          else
          {
            EcpContextSize = a3[3];
            if ( FsRtlAllocateExtraCreateParameter(&EcpType, EcpContextSize, 0, 0, 0x6D537843u, &EcpContext) >= 0 )
            {
              memmove(EcpContext, (char *)a3 + *((unsigned __int16 *)a3 + 5), EcpContextSize);
              FsRtlAcknowledgeEcp(EcpContext);
              if ( FsRtlInsertExtraCreateParameter(*(PECP_LIST *)(a1 + 688), EcpContext) < 0 )
                FsRtlFreeExtraCreateParameter(EcpContext);
            }
          }
        }
      }
      goto LABEL_26;
    }
    v16 = *(unsigned int *)((char *)a3 + v11);
    switch ( (_DWORD)v16 )
    {
      case 0x64694651:
        v6 = Smb2ProcessOnDiskIdEcp(a1, a2, (char *)a3 + v12, v14);
        goto LABEL_26;
      case 0x734C7152:
        if ( (*(_DWORD *)(v26 + 716) & 0x20) == 0 )
          return (unsigned int)-1073741629;
        v6 = 0;
        if ( v14 == 52 )
        {
          *(_BYTE *)a2 |= 0x18u;
          *(_DWORD *)(a2 + 36) = *(unsigned int *)((char *)a3 + v12 + 16);
          *(_DWORD *)(a2 + 40) = *(unsigned __int16 *)((char *)a3 + v12 + 48);
          *(_DWORD *)(a2 + 44) = *(unsigned int *)((char *)a3 + v12 + 20);
          goto LABEL_26;
        }
        if ( v14 == 32 )
        {
          *(_BYTE *)a2 |= 8u;
          *(_DWORD *)(a2 + 36) = *(unsigned int *)((char *)a3 + v12 + 16);
          *(_DWORD *)(a2 + 44) = *(unsigned int *)((char *)a3 + v12 + 20);
          *(_DWORD *)(a2 + 40) = -1;
          goto LABEL_26;
        }
        v6 = -1073741629;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v21 = 21;
          goto LABEL_63;
        }
        goto LABEL_26;
      case 0x6341784D:
        if ( v14 == 8 )
        {
          v19 = *(_QWORD *)(a1 + 72);
          v6 = 0;
          *(_BYTE *)a2 |= 4u;
          if ( *(int *)((char *)a3 + v12) < 0 )
            *(_QWORD *)(v19 + 152) = 0;
          else
            *(_QWORD *)(v19 + 152) = *(unsigned int *)((char *)a3 + v12 + 4);
        }
        else
        {
          v6 = -1073741629;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids, a1);
          }
        }
        goto LABEL_26;
      case 0x51324844:
        if ( v14 >= 8 )
        {
          v6 = 0;
          *(_BYTE *)a2 |= 0x40u;
          *(_DWORD *)(a2 + 48) = *(unsigned int *)((char *)a3 + v12 + 4);
          *(_DWORD *)(a2 + 52) = *(unsigned int *)((char *)a3 + v12);
          goto LABEL_26;
        }
        v6 = -1073741629;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v21 = 20;
LABEL_63:
          WPP_SF_(v20->AttachedDevice, v21, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids);
        }
LABEL_26:
        if ( v6 < 0 )
          return (unsigned int)v6;
        goto LABEL_27;
    }
    if ( (_DWORD)v16 != 1366181956 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids, v16);
      }
      goto LABEL_26;
    }
    *(_BYTE *)a2 |= 0x20u;
    v6 = 0;
    *(_QWORD *)(a2 + 48) = 0;
LABEL_27:
    v17 = *a3;
    if ( (_DWORD)v17 )
    {
      if ( ((v17 + 7) & 0xFFFFFFFFFFFFFFF8uLL) != (unsigned int)v17 )
        return (unsigned int)-1073741629;
      a3 = (unsigned int *)((char *)a3 + (unsigned int)v17);
    }
    else
    {
      a3 = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007470  push    rbx
0x140007472  push    rbp
0x140007473  push    rdi
0x140007474  push    r12
0x140007476  push    r13
0x140007478  push    r15
0x14000747a  sub     rsp, 68h
0x14000747e  mov     rax, cs:__security_cookie
0x140007485  xor     rax, rsp
0x140007488  mov     [rsp+98h+var_40], rax
0x14000748d  mov     rax, [rcx+48h]
0x140007491  mov     ebp, r9d
0x140007494  mov     r13, rdx
0x140007497  mov     [rsp+98h+arg_18], rsi
0x14000749f  xor     r15d, r15d
0x1400074a2  mov     [rsp+98h+var_38], r14
0x1400074a7  mov     rbx, r8
0x1400074aa  mov     r12, rcx
0x1400074ad  mov     r9, [rax+28h]
0x1400074b1  xor     edi, edi
0x1400074b3  mov     rax, [r9+28h]
0x1400074b7  mov     rdx, [rax+1A8h]
0x1400074be  mov     rax, [rdx+58h]
0x1400074c2  mov     [rsp+98h+var_58], rax
0x1400074c7  test    rbx, rbx
0x1400074ca  jz      loc_14000760E
0x1400074d0  mov     ecx, [rbx]
0x1400074d2  mov     eax, ebp
0x1400074d4  sub     eax, edi
0x1400074d6  test    ecx, ecx
0x1400074d8  cmovnz  eax, ecx
0x1400074db  cmp     edi, ebp
0x1400074dd  ja      loc_140007608
0x1400074e3  cmp     eax, ebp
0x1400074e5  ja      loc_140007608
0x1400074eb  add     edi, eax
0x1400074ed  cmp     edi, ebp
0x1400074ef  ja      loc_140007608
0x1400074f5  movzx   edx, word ptr [rbx+4]
0x1400074f9  lea     rcx, [rdx+7]
0x1400074fd  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140007501  cmp     rcx, rdx
0x140007504  jnz     loc_140007608
0x14000750a  movzx   r8d, word ptr [rbx+0Ah]
0x14000750f  lea     rcx, [r8+7]
0x140007513  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140007517  cmp     rcx, r8
0x14000751a  jnz     loc_140007608
0x140007520  cmp     edx, eax
0x140007522  ja      loc_140007608
0x140007528  cmp     r8d, eax
0x14000752b  ja      loc_140007608
0x140007531  movzx   ecx, word ptr [rbx+6]
0x140007535  cmp     ecx, eax
0x140007537  ja      loc_140007608
0x14000753d  mov     r14d, [rbx+0Ch]
0x140007541  cmp     r14d, eax
0x140007544  ja      loc_140007608
0x14000754a  lea     esi, [rcx+rdx]
0x14000754d  cmp     esi, eax
0x14000754f  ja      loc_140007608
0x140007555  lea     r9d, [r14+r8]
0x140007559  cmp     r9d, eax
0x14000755c  ja      loc_140007608
0x140007562  cmp     r8w, dx
0x140007566  jb      loc_14000774A
0x14000756c  jbe     short loc_140007577
0x14000756e  cmp     r8d, esi
0x140007571  jb      loc_140007608
0x140007577  cmp     ecx, 4
0x14000757a  jnz     short loc_1400075D9
0x14000757c  mov     r9d, [rdx+rbx]
0x140007580  cmp     r9d, 64694651h
0x140007587  jz      loc_14000763A
0x14000758d  cmp     r9d, 734C7152h
0x140007594  jnz     loc_140007650
0x14000759a  mov     rax, [rsp+98h+var_58]
0x14000759f  mov     eax, [rax+2CCh]
0x1400075a5  test    al, 20h
0x1400075a7  jz      short loc_140007608
0x1400075a9  xor     r15d, r15d
0x1400075ac  cmp     r14d, 34h ; '4'
0x1400075b0  jnz     loc_1400076CD
0x1400075b6  or      byte ptr [r13+0], 18h
0x1400075bb  mov     eax, [r8+rbx+10h]
0x1400075c0  mov     [r13+24h], eax
0x1400075c4  movzx   eax, word ptr [r8+rbx+30h]
0x1400075ca  mov     [r13+28h], eax
0x1400075ce  mov     eax, [r8+rbx+14h]
0x1400075d3  mov     [r13+2Ch], eax
0x1400075d7  jmp     short loc_1400075E2
0x1400075d9  cmp     ecx, 10h
0x1400075dc  jz      loc_140038BC6
0x1400075e2  test    r15d, r15d
0x1400075e5  js      short loc_14000760E
0x1400075e7  mov     eax, [rbx]
0x1400075e9  test    eax, eax
0x1400075eb  jz      loc_140007691
0x1400075f1  mov     ecx, eax
0x1400075f3  add     rax, 7
0x1400075f7  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400075fb  cmp     rax, rcx
0x1400075fe  jnz     short loc_140007608
0x140007600  add     rbx, rcx
0x140007603  jmp     loc_1400074C7
0x140007608  mov     r15d, 0C00000C3h
0x14000760e  mov     r14, [rsp+98h+var_38]
0x140007613  mov     eax, r15d
0x140007616  mov     rsi, [rsp+98h+arg_18]
0x14000761e  mov     rcx, [rsp+98h+var_40]
0x140007623  xor     rcx, rsp; StackCookie
0x140007626  call    __security_check_cookie
0x14000762b  add     rsp, 68h
0x14000762f  pop     r15
0x140007631  pop     r13
0x140007633  pop     r12
0x140007635  pop     rdi
0x140007636  pop     rbp
0x140007637  pop     rbx
0x140007638  retn
0x14000763a  add     r8, rbx
0x14000763d  mov     r9d, r14d
0x140007640  mov     rdx, r13
0x140007643  mov     rcx, r12
0x140007646  call    Smb2ProcessOnDiskIdEcp
0x14000764b  mov     r15d, eax
0x14000764e  jmp     short loc_1400075E2
0x140007650  cmp     r9d, 6341784Dh
0x140007657  jnz     short loc_140007698
0x140007659  cmp     r14d, 8
0x14000765d  jnz     loc_1400076FB
0x140007663  mov     rcx, [r12+48h]
0x140007668  xor     r15d, r15d
0x14000766b  or      byte ptr [r13+0], 4
0x140007670  cmp     [r8+rbx], r15d
0x140007674  jl      loc_1400077EB
0x14000767a  mov     eax, [r8+rbx+4]
0x14000767f  mov     [rcx+98h], eax
0x140007685  mov     [rcx+9Ch], r15d
0x14000768c  jmp     loc_1400075E2
0x140007691  xor     ebx, ebx
0x140007693  jmp     loc_1400074C7
0x140007698  cmp     r9d, 51324844h
0x14000769f  jnz     loc_14000775C
0x1400076a5  cmp     r14d, 8
0x1400076a9  jb      loc_1400077F7
0x1400076af  xor     r15d, r15d
0x1400076b2  or      byte ptr [r13+0], 40h
0x1400076b7  mov     eax, [r8+rbx+4]
0x1400076bc  mov     [r13+30h], eax
0x1400076c0  mov     eax, [r8+rbx]
0x1400076c4  mov     [r13+34h], eax
0x1400076c8  jmp     loc_1400075E2
0x1400076cd  cmp     r14d, 20h ; ' '
0x1400076d1  jnz     loc_1400077AF
0x1400076d7  or      byte ptr [r13+0], 8
0x1400076dc  mov     eax, [r8+rbx+10h]
0x1400076e1  mov     [r13+24h], eax
0x1400076e5  mov     eax, [r8+rbx+14h]
0x1400076ea  mov     [r13+2Ch], eax
0x1400076ee  mov     dword ptr [r13+28h], 0FFFFFFFFh
0x1400076f6  jmp     loc_1400075E2
0x1400076fb  mov     r15d, 0C00000C3h
0x140007701  mov     rcx, cs:WPP_GLOBAL_Control
0x140007708  lea     rax, WPP_GLOBAL_Control
0x14000770f  cmp     rcx, rax
0x140007712  jz      loc_1400075E2
0x140007718  mov     eax, [rcx+2Ch]
0x14000771b  test    al, 1
0x14000771d  jz      loc_1400075E2
0x140007723  cmp     byte ptr [rcx+29h], 1
0x140007727  jb      loc_1400075E2
0x14000772d  mov     rcx, [rcx+18h]
0x140007731  lea     r8, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids
0x140007738  mov     edx, 13h
0x14000773d  mov     r9, r12
0x140007740  call    WPP_SF_q
0x140007745  jmp     loc_1400075E2
0x14000774a  cmp     edx, r9d
0x14000774d  jb      loc_140007608
0x140007753  cmp     r8w, dx
0x140007757  jmp     loc_14000756C
0x14000775c  cmp     r9d, 516E4844h
0x140007763  jz      loc_140038BB1
0x140007769  mov     rcx, cs:WPP_GLOBAL_Control
0x140007770  lea     rax, WPP_GLOBAL_Control
0x140007777  cmp     rcx, rax
0x14000777a  jz      loc_1400075E2
0x140007780  mov     eax, [rcx+2Ch]
0x140007783  test    al, 40h
0x140007785  jz      loc_1400075E2
0x14000778b  cmp     byte ptr [rcx+29h], 2
0x14000778f  jb      loc_1400075E2
0x140007795  mov     rcx, [rcx+18h]
0x140007799  lea     r8, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids
0x1400077a0  mov     edx, 0Eh
0x1400077a5  call    WPP_SF_d
0x1400077aa  jmp     loc_1400075E2
0x1400077af  mov     r15d, 0C00000C3h
0x1400077b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077bc  lea     rax, WPP_GLOBAL_Control
0x1400077c3  cmp     rcx, rax
0x1400077c6  jz      loc_1400075E2
0x1400077cc  mov     eax, [rcx+2Ch]
0x1400077cf  test    al, 1
0x1400077d1  jz      loc_1400075E2
0x1400077d7  cmp     byte ptr [rcx+29h], 1
0x1400077db  jb      loc_1400075E2
0x1400077e1  mov     edx, 15h
0x1400077e6  jmp     loc_140038B9B
0x1400077eb  mov     [rcx+98h], r15
0x1400077f2  jmp     loc_1400075E2
0x1400077f7  mov     r15d, 0C00000C3h
0x1400077fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140007804  lea     rax, WPP_GLOBAL_Control
0x14000780b  cmp     rcx, rax
0x14000780e  jz      loc_1400075E2
0x140007814  mov     eax, [rcx+2Ch]
0x140007817  test    al, 1
0x140007819  jz      loc_1400075E2
0x14000781f  cmp     byte ptr [rcx+29h], 1
0x140007823  jb      loc_1400075E2
0x140007829  jmp     loc_140038B96
0x140038b96  mov     edx, 14h
0x140038b9b  mov     rcx, [rcx+18h]
0x140038b9f  lea     r8, WPP_ec883060206d3d6ef99cecbe53c54519_Traceguids
0x140038ba6  call    WPP_SF_
0x140038bab  nop
0x140038bac  jmp     loc_1400075E2
0x140038bb1  or      byte ptr [r13+0], 20h
0x140038bb6  xor     r15d, r15d
0x140038bb9  mov     qword ptr [r13+30h], 0
0x140038bc1  jmp     loc_1400075E7
0x140038bc6  cmp     qword ptr [r12+2B0h], 0
0x140038bcf  xorps   xmm0, xmm0
0x140038bd2  movups  xmmword ptr [rsp+98h+EcpType.Data1], xmm0
0x140038bd7  mov     [rsp+98h+EcpContext], 0
0x140038be0  mov     [rsp+98h+EcpContextSize], 0
0x140038be8  movups  xmm0, xmmword ptr [rdx+rbx]
0x140038bec  movups  xmmword ptr [rsp+98h+EcpType.Data1], xmm0
0x140038bf1  jz      loc_1400075E2
0x140038bf7  xor     edx, edx
0x140038bf9  lea     rcx, [rsp+98h+EcpType]; Source1
0x140038bfe  call    Smb2IsKnownPassthroughEcp
0x140038c03  test    al, al
0x140038c05  jnz     short loc_140038C21
0x140038c07  mov     rcx, [r12+50h]
0x140038c0c  lea     rdx, [rsp+98h+EcpType]
0x140038c11  xor     r8d, r8d
0x140038c14  call    Smb2IsKnownVmbusPassthroughEcp
0x140038c19  test    al, al
0x140038c1b  jz      loc_1400075E2
0x140038c21  mov     dl, 1
0x140038c23  lea     rcx, [rsp+98h+EcpType]; Source1
0x140038c28  call    Smb2IsKnownPassthroughEcp
0x140038c2d  test    al, al
0x140038c2f  jnz     short loc_140038C47
0x140038c31  mov     rcx, [r12+50h]
0x140038c36  lea     rdx, [rsp+98h+EcpType]
0x140038c3b  mov     r8b, 1
0x140038c3e  call    Smb2IsKnownVmbusPassthroughEcp
0x140038c43  test    al, al
0x140038c45  jz      short loc_140038CA6
0x140038c47  mov     rcx, [r12+2B0h]; EcpList
0x140038c4f  lea     r9, [rsp+98h+EcpContextSize]; EcpContextSize
0x140038c54  lea     r8, [rsp+98h+EcpContext]; EcpContext
0x140038c59  lea     rdx, [rsp+98h+EcpType]; EcpType
0x140038c5e  call    cs:__imp_FsRtlFindExtraCreateParameter
0x140038c65  nop     dword ptr [rax+rax+00h]
0x140038c6a  test    eax, eax
0x140038c6c  js      short loc_140038CA6
0x140038c6e  mov     eax, [rsp+98h+EcpContextSize]
0x140038c72  cmp     [rbx+0Ch], eax
0x140038c75  jnz     loc_1400075E2
0x140038c7b  movzx   edx, word ptr [rbx+0Ah]
0x140038c7f  mov     r8d, eax; Size
0x140038c82  mov     rcx, [rsp+98h+EcpContext]; void *
0x140038c87  add     rdx, rbx; Src
0x140038c8a  call    memmove
0x140038c8f  mov     rcx, [rsp+98h+EcpContext]; EcpContext
0x140038c94  call    cs:__imp_FsRtlAcknowledgeEcp
0x140038c9b  nop     dword ptr [rax+rax+00h]
0x140038ca0  nop
0x140038ca1  jmp     loc_1400075E2
0x140038ca6  mov     edx, [rbx+0Ch]; SizeOfContext
0x140038ca9  lea     rax, [rsp+98h+EcpContext]
0x140038cae  mov     [rsp+98h+var_70], rax; EcpContext
0x140038cb3  lea     rcx, [rsp+98h+EcpType]; EcpType
0x140038cb8  xor     r9d, r9d; CleanupCallback
0x140038cbb  mov     [rsp+98h+PoolTag], 6D537843h; PoolTag
0x140038cc3  xor     r8d, r8d; Flags
0x140038cc6  mov     [rsp+98h+EcpContextSize], edx
0x140038cca  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140038cd1  nop     dword ptr [rax+rax+00h]
0x140038cd6  test    eax, eax
0x140038cd8  js      loc_1400075E2
0x140038cde  movzx   edx, word ptr [rbx+0Ah]
0x140038ce2  mov     r8d, [rsp+98h+EcpContextSize]; Size
0x140038ce7  add     rdx, rbx; Src
0x140038cea  mov     rcx, [rsp+98h+EcpContext]; void *
  ... truncated ...
```
