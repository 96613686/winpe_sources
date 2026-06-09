# PsmpCreateAndInitializeHostJob

- ea: `0x18000d378`
- end: `0x18000d7df`
- name: `PsmpCreateAndInitializeHostJob`
- size: `1127`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, HANDLE *, _QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c7b0`
- `0x1800188f8`

## callees

- `0x18000d14c`
- `0x18000d378`
- `0x18000d7e8`
- `0x18000d934`
- `0x18000ebd0`
- `0x18000ec9c`
- `0x18001720c`
- `0x18001efd4`

## import_xrefs

- `ntdll!NtClose` at `0x18000d7ae`
- `ntdll!NtClose` at `0x18000d7ae`
- `ntdll!NtSetInformationJobObject` at `0x18000d579`
- `ntdll!NtSetInformationJobObject` at `0x18000d579`
- `ntdll!TpAllocJobNotification` at `0x18000d5a2`
- `ntdll!TpAllocJobNotification` at `0x18000d5a2`

## pseudocode

```c
__int64 __fastcall PsmpCreateAndInitializeHostJob(__int64 a1, int a2, __int64 a3, __int64 a4, HANDLE *a5, _QWORD *a6)
{
  NTSTATUS JobObject; // esi
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rdi
  HANDLE *v13; // r14
  __int64 v14; // r12
  __int64 v15; // r8
  _QWORD *v16; // rcx
  __int64 v18; // rcx
  bool v19; // zf
  __int64 v20; // rax
  int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  int JobInformation; // [rsp+78h] [rbp+10h] BYREF
  __int64 v29; // [rsp+88h] [rbp+20h]

  v29 = a4;
  JobObject = 0;
  JobInformation = 192;
  v10 = 0;
  v11 = 0;
  if ( (a2 & 0x40) != 0 )
  {
    v12 = 0;
    JobInformation = 16;
    v13 = (HANDLE *)(a1 + 208);
    v14 = a1 + 6760;
    goto LABEL_3;
  }
  v18 = *(_QWORD *)(*(_QWORD *)(a1 + 312) + 56LL);
  if ( (a2 & 0xC) != 0 )
  {
    if ( (a2 & 8) != 0 )
    {
      v19 = (*(_DWORD *)(a1 + 132) & 0x100) == 0;
      JobInformation = 16;
      if ( v19 )
      {
        v10 = *(_DWORD *)(v18 + 16) != 4 ? 0x10 : 0;
        _interlockedbittestandset((volatile signed __int32 *)(a1 + 132), 8u);
      }
      v14 = a4 + 88;
      v12 = a4;
      v13 = (HANDLE *)(a4 + 48);
      v11 = v10;
      goto LABEL_27;
    }
    v24 = *(_QWORD *)(a1 + 6808);
    if ( v24 == -1 )
    {
      *(_QWORD *)(a1 + 6808) = a3;
    }
    else if ( v24 != a3 && (*(_DWORD *)(a1 + 132) & 0x1000) != 0 )
    {
      return (unsigned int)-1058275322;
    }
    v13 = (HANDLE *)(a1 + 200);
    v14 = a1 + 6752;
    v26 = *(_DWORD *)(v18 + 16) - 4;
    JobInformation = 16;
    v12 = a1 + 6984;
    v10 = v26 != 0 ? 8 : 0;
  }
  else
  {
    v20 = *(_QWORD *)(a1 + 6800);
    if ( v20 == -1 )
    {
      *(_QWORD *)(a1 + 6800) = a3;
    }
    else if ( v20 != a3 && (*(_DWORD *)(a1 + 132) & 0x1000) != 0 )
    {
      return (unsigned int)-1058275322;
    }
    v13 = (HANDLE *)(a1 + 192);
    v21 = *(_DWORD *)(v18 + 16) - 4;
    JobInformation = 208;
    v14 = a1 + 6744;
    v12 = a1 + 6944;
    v10 = v21 != 0 ? 0xFFFFFFE7 : 0;
  }
LABEL_27:
  if ( v12 )
  {
    v22 = a6;
    if ( a6 )
    {
      if ( !*(_QWORD *)(v12 + 8) )
      {
        *(_QWORD *)(v12 + 8) = *a6;
        *v22 = 0;
      }
    }
  }
LABEL_3:
  if ( (a2 & 2) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(a1 + 132), 0x80u);
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 156));
  }
  if ( *v13 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_ii(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
        *(_QWORD *)(a1 + 96),
        a3);
LABEL_12:
    if ( a5 )
      *a5 = *v13;
    return (unsigned int)JobObject;
  }
  JobObject = PsmpCreateJobObject(v12, v13, v10, v11);
  if ( JobObject >= 0 )
  {
    if ( !v14 )
    {
LABEL_8:
      if ( (a2 & 4) != 0 )
      {
        JobObject = PsmpSubscribeForInternalNotification(*v13);
        if ( JobObject < 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_ii(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
              *(_QWORD *)(a1 + 96),
              a3);
          goto LABEL_15;
        }
        PsmpUpdateApplicationEnergyTrackingState(a1);
      }
      else if ( (a2 & 8) != 0 )
      {
        JobObject = PsmpSubscribeForInternalNotification(*v13);
        if ( JobObject < 0 )
          goto LABEL_15;
      }
      if ( v12 )
        PsmpNotificationsDeliverHostMessage(v12, 0, 0);
      goto LABEL_12;
    }
    JobObject = NtSetInformationJobObject(*v13, (JOBOBJECTINFOCLASS)16, &JobInformation, 4u);
    if ( JobObject < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_15;
      v25 = 22;
    }
    else
    {
      JobObject = TpAllocJobNotification(v14, *v13, PsmpJobNotificationCallback, a1, 0);
      if ( JobObject >= 0 )
        goto LABEL_8;
      v16 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_15;
      v25 = 23;
    }
    WPP_SF_iid(v16[2], v25, v23, *(_QWORD *)(a1 + 96), a3, a2);
LABEL_15:
    if ( v13 && *v13 )
      NtClose(*v13);
    if ( v12 )
    {
      PsmpHostContextCleanup(v12);
      v27 = *(_DWORD *)(v12 + 16);
      *(_OWORD *)v12 = 0;
      *(_OWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 32) = 0;
      *(_QWORD *)v12 = a1;
      *(_DWORD *)(v12 + 16) = v27;
    }
    return (unsigned int)JobObject;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_iid(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v15, *(_QWORD *)(a1 + 96), a3, a2);
  return (unsigned int)JobObject;
}

```

## disassembly

```asm
0x18000d378  mov     [rsp+arg_18], r9
0x18000d37d  push    rbx
0x18000d37e  push    rbp
0x18000d37f  push    rsi
0x18000d380  push    rdi
0x18000d381  push    r12
0x18000d383  push    r14
0x18000d385  push    r15
0x18000d387  sub     rsp, 30h
0x18000d38b  xor     esi, esi
0x18000d38d  mov     [rsp+68h+JobInformation], 0C0h
0x18000d395  mov     r15d, edx
0x18000d398  mov     [rsp+68h+arg_0], rsi
0x18000d39d  mov     rbp, r8
0x18000d3a0  mov     rbx, rcx
0x18000d3a3  mov     r8d, esi
0x18000d3a6  mov     edx, esi
0x18000d3a8  test    r15b, 40h
0x18000d3ac  jz      loc_18000D46D
0x18000d3b2  mov     edi, esi
0x18000d3b4  mov     [rsp+68h+JobInformation], 10h
0x18000d3bc  lea     r14, [rcx+0D0h]
0x18000d3c3  lea     r12, [rcx+1A68h]
0x18000d3ca  test    r15b, 2
0x18000d3ce  jnz     loc_18000D6F2
0x18000d3d4  cmp     [r14], rsi
0x18000d3d7  jnz     loc_18000D529
0x18000d3dd  mov     r9d, edx
0x18000d3e0  mov     rcx, rdi
0x18000d3e3  mov     rdx, r14
0x18000d3e6  call    PsmpCreateJobObject
0x18000d3eb  mov     esi, eax
0x18000d3ed  test    eax, eax
0x18000d3ef  js      loc_18000D63E
0x18000d3f5  test    r12, r12
0x18000d3f8  jnz     loc_18000D567
0x18000d3fe  test    r15b, 4
0x18000d402  jnz     loc_18000D736
0x18000d408  test    r15b, 8
0x18000d40c  jnz     loc_18000D5F7
0x18000d412  test    rdi, rdi
0x18000d415  jz      short loc_18000D424
0x18000d417  xor     r8d, r8d
0x18000d41a  xor     edx, edx
0x18000d41c  mov     rcx, rdi
0x18000d41f  call    PsmpNotificationsDeliverHostMessage
0x18000d424  mov     rcx, [rsp+68h+arg_20]
0x18000d42c  test    rcx, rcx
0x18000d42f  jz      short loc_18000D45C
0x18000d431  mov     rax, [r14]
0x18000d434  mov     [rcx], rax
0x18000d437  jmp     short loc_18000D45C
0x18000d439  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d440  test    byte ptr [rcx+1Ch], 2
0x18000d444  jnz     loc_18000D72A
0x18000d44a  test    r14, r14
0x18000d44d  jnz     loc_18000D7A2
0x18000d453  test    rdi, rdi
0x18000d456  jnz     loc_18000D7B9
0x18000d45c  mov     eax, esi
0x18000d45e  add     rsp, 30h
0x18000d462  pop     r15
0x18000d464  pop     r14
0x18000d466  pop     r12
0x18000d468  pop     rdi
0x18000d469  pop     rsi
0x18000d46a  pop     rbp
0x18000d46b  pop     rbx
0x18000d46c  retn
0x18000d46d  mov     rax, [rcx+138h]
0x18000d474  mov     rcx, [rax+38h]
0x18000d478  test    r15b, 0Ch
0x18000d47c  jz      short loc_18000D4B0
0x18000d47e  test    r15b, 8
0x18000d482  jz      loc_18000D5B7
0x18000d488  test    dword ptr [rbx+84h], 100h
0x18000d492  mov     [rsp+68h+JobInformation], 10h
0x18000d49a  jz      loc_18000D621
0x18000d4a0  lea     r12, [r9+58h]
0x18000d4a4  mov     rdi, r9
0x18000d4a7  lea     r14, [r9+30h]
0x18000d4ab  mov     edx, r8d
0x18000d4ae  jmp     short loc_18000D4F6
0x18000d4b0  mov     rax, [rbx+1A90h]
0x18000d4b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d4bb  jz      loc_18000D5EB
0x18000d4c1  cmp     rax, rbp
0x18000d4c4  jnz     loc_18000D67A
0x18000d4ca  mov     eax, [rcx+10h]
0x18000d4cd  lea     r14, [rbx+0C0h]
0x18000d4d4  sub     eax, 4
0x18000d4d7  mov     [rsp+68h+JobInformation], 0D0h
0x18000d4df  neg     eax
0x18000d4e1  lea     r12, [rbx+1A58h]
0x18000d4e8  lea     rdi, [rbx+1B20h]
0x18000d4ef  sbb     r8d, r8d
0x18000d4f2  and     r8d, 0FFFFFFE7h
0x18000d4f6  test    rdi, rdi
0x18000d4f9  jz      loc_18000D3CA
0x18000d4ff  mov     rcx, [rsp+68h+arg_28]
0x18000d507  test    rcx, rcx
0x18000d50a  jz      loc_18000D3CA
0x18000d510  cmp     [rdi+8], rsi
0x18000d514  jnz     loc_18000D3CA
0x18000d51a  mov     rax, [rcx]
0x18000d51d  mov     [rdi+8], rax
0x18000d521  mov     [rcx], rsi
0x18000d524  jmp     loc_18000D3CA
0x18000d529  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d530  test    byte ptr [rcx+1Ch], 2
0x18000d534  jz      loc_18000D424
0x18000d53a  cmp     byte ptr [rcx+19h], 4
0x18000d53e  jb      loc_18000D424
0x18000d544  mov     r9, [rbx+60h]
0x18000d548  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18000d54f  mov     rcx, [rcx+10h]
0x18000d553  mov     edx, 14h
0x18000d558  mov     [rsp+68h+var_48], rbp
0x18000d55d  call    WPP_SF_ii
0x18000d562  jmp     loc_18000D424
0x18000d567  mov     rcx, [r14]; JobHandle
0x18000d56a  lea     r8, [rsp+68h+JobInformation]; JobInformation
0x18000d56f  mov     r9d, 4; JobInformationLength
0x18000d575  lea     edx, [r9+0Ch]; JobInformationClass
0x18000d579  call    cs:__imp_NtSetInformationJobObject
0x18000d57f  mov     esi, eax
0x18000d581  test    eax, eax
0x18000d583  js      loc_18000D68F
0x18000d589  mov     rdx, [r14]
0x18000d58c  lea     r8, PsmpJobNotificationCallback
0x18000d593  mov     r9, rbx
0x18000d596  mov     [rsp+68h+var_48], 0
0x18000d59f  mov     rcx, r12
0x18000d5a2  call    cs:__imp_TpAllocJobNotification
0x18000d5a8  mov     esi, eax
0x18000d5aa  test    eax, eax
0x18000d5ac  jns     loc_18000D3FE
0x18000d5b2  jmp     loc_18000D439
0x18000d5b7  mov     rax, [rbx+1A98h]
0x18000d5be  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d5c2  jz      loc_18000D6B1
0x18000d5c8  cmp     rax, rbp
0x18000d5cb  jz      loc_18000D6B8
0x18000d5d1  test    dword ptr [rbx+84h], 1000h
0x18000d5db  jz      loc_18000D6B8
0x18000d5e1  mov     esi, 0C0EC0006h
0x18000d5e6  jmp     loc_18000D45C
0x18000d5eb  mov     [rbx+1A90h], rbp
0x18000d5f2  jmp     loc_18000D4CA
0x18000d5f7  mov     r9, [rsp+68h+arg_18]
0x18000d5ff  lea     r8, PsmpPureHostNotification
0x18000d606  mov     rcx, [r14]; JobHandle
0x18000d609  lea     rdx, [r9+60h]
0x18000d60d  call    PsmpSubscribeForInternalNotification
0x18000d612  mov     esi, eax
0x18000d614  test    eax, eax
0x18000d616  jns     loc_18000D412
0x18000d61c  jmp     loc_18000D44A
0x18000d621  mov     eax, [rcx+10h]
0x18000d624  sub     eax, 4
0x18000d627  neg     eax
0x18000d629  sbb     r8d, r8d
0x18000d62c  and     r8d, 10h
0x18000d630  lock bts dword ptr [rbx+84h], 8
0x18000d639  jmp     loc_18000D4A0
0x18000d63e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d645  test    byte ptr [rcx+1Ch], 2
0x18000d649  jz      loc_18000D45C
0x18000d64f  cmp     byte ptr [rcx+19h], 2
0x18000d653  jb      loc_18000D45C
0x18000d659  mov     r9, [rbx+60h]
0x18000d65d  mov     edx, 15h
0x18000d662  mov     rcx, [rcx+10h]
0x18000d666  mov     [rsp+68h+var_40], r15d
0x18000d66b  mov     [rsp+68h+var_48], rbp
0x18000d670  call    WPP_SF_iid
0x18000d675  jmp     loc_18000D45C
0x18000d67a  test    dword ptr [rbx+84h], 1000h
0x18000d684  jz      loc_18000D4CA
0x18000d68a  jmp     loc_18000D5E1
0x18000d68f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d696  test    byte ptr [rcx+1Ch], 2
0x18000d69a  jz      loc_18000D44A
0x18000d6a0  cmp     byte ptr [rcx+19h], 2
0x18000d6a4  jb      loc_18000D44A
0x18000d6aa  mov     edx, 16h
0x18000d6af  jmp     short loc_18000D70E
0x18000d6b1  mov     [rbx+1A98h], rbp
0x18000d6b8  lea     rax, [rbx+70h]
0x18000d6bc  mov     [rsp+68h+arg_0], rax
0x18000d6c1  lea     r14, [rbx+0C8h]
0x18000d6c8  mov     eax, [rcx+10h]
0x18000d6cb  lea     r12, [rbx+1A60h]
0x18000d6d2  sub     eax, 4
0x18000d6d5  mov     [rsp+68h+JobInformation], 10h
0x18000d6dd  neg     eax
0x18000d6df  lea     rdi, [rbx+1B48h]
0x18000d6e6  sbb     r8d, r8d
0x18000d6e9  and     r8d, 8
0x18000d6ed  jmp     loc_18000D4F6
0x18000d6f2  lock or dword ptr [rbx+84h], 80h
0x18000d6fd  lock inc dword ptr [rbx+9Ch]
0x18000d704  jmp     loc_18000D3D4
0x18000d709  mov     edx, 17h
0x18000d70e  mov     r9, [rbx+60h]
0x18000d712  mov     rcx, [rcx+10h]
0x18000d716  mov     [rsp+68h+var_40], r15d
0x18000d71b  mov     [rsp+68h+var_48], rbp
0x18000d720  call    WPP_SF_iid
0x18000d725  jmp     loc_18000D44A
0x18000d72a  cmp     byte ptr [rcx+19h], 2
0x18000d72e  jb      loc_18000D44A
0x18000d734  jmp     short loc_18000D709
0x18000d736  mov     rdx, [rsp+68h+arg_0]
0x18000d73b  lea     r8, PsmpExecutionRequestNotification
0x18000d742  mov     rcx, [r14]; JobHandle
0x18000d745  mov     r9, rbx
0x18000d748  or      r9, 1
0x18000d74c  call    PsmpSubscribeForInternalNotification
0x18000d751  mov     esi, eax
0x18000d753  test    eax, eax
0x18000d755  jns     short loc_18000D795
0x18000d757  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d75e  test    byte ptr [rcx+1Ch], 2
0x18000d762  jz      loc_18000D44A
0x18000d768  cmp     byte ptr [rcx+19h], 2
0x18000d76c  jb      loc_18000D44A
0x18000d772  mov     r9, [rbx+60h]
0x18000d776  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18000d77d  mov     rcx, [rcx+10h]
0x18000d781  mov     edx, 18h
0x18000d786  mov     [rsp+68h+var_48], rbp
0x18000d78b  call    WPP_SF_ii
0x18000d790  jmp     loc_18000D44A
0x18000d795  mov     rcx, rbx
0x18000d798  call    PsmpUpdateApplicationEnergyTrackingState
0x18000d79d  jmp     loc_18000D412
0x18000d7a2  mov     rcx, [r14]; Handle
0x18000d7a5  test    rcx, rcx
0x18000d7a8  jz      loc_18000D453
0x18000d7ae  call    cs:__imp_NtClose
0x18000d7b4  jmp     loc_18000D453
0x18000d7b9  mov     rcx, rdi
0x18000d7bc  call    PsmpHostContextCleanup
0x18000d7c1  mov     eax, [rdi+10h]
0x18000d7c4  xorps   xmm0, xmm0
0x18000d7c7  movups  xmmword ptr [rdi], xmm0
0x18000d7ca  xor     ecx, ecx
0x18000d7cc  movups  xmmword ptr [rdi+10h], xmm0
0x18000d7d0  mov     [rdi+20h], rcx
0x18000d7d4  mov     [rdi], rbx
0x18000d7d7  mov     [rdi+10h], eax
0x18000d7da  jmp     loc_18000D45C
```
