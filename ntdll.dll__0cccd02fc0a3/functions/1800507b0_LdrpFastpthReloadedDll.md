# LdrpFastpthReloadedDll

- ea: `0x1800507b0`
- end: `0x180050d01`
- name: `LdrpFastpthReloadedDll`
- size: `1361`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800249a0`

## callees

- `0x1800183a0`
- `0x18001b984`
- `0x1800254e0`
- `0x1800259fc`
- `0x18002dae0`
- `0x18004cef8`
- `0x1800501dc`
- `0x1800507b0`
- `0x1800526f0`
- `0x180052720`
- `0x180053150`
- `0x180053dd0`
- `0x180053e34`
- `0x180053f30`
- `0x180054000`
- `0x1800bb614`
- `0x1800fb270`
- `0x1800fce28`

## pseudocode

```c
__int64 __fastcall LdrpFastpthReloadedDll(_OWORD *a1, int a2, __int64 a3, _QWORD *a4)
{
  _OWORD *v7; // rbp
  int Count; // r14d
  int v9; // edi
  __int64 v10; // rdx
  int LoadedDllByNameLockHeld; // ebx
  int v12; // r12d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  char *v22; // rcx
  int v23; // r9d
  int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int CurrentServiceSessionId; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rcx
  char *v35; // rcx
  __int64 v36; // rdi
  _QWORD *SchedulerSharedDataSlot; // rdx
  __int64 i; // rcx
  __int64 v40; // rbx
  __int64 v41; // rdi
  int v42; // ecx
  __int64 Heap_0; // rax
  __int64 *v45; // rdx
  _QWORD *v46; // rdx
  _QWORD *v47; // r8
  int v48; // edx
  __int64 v49; // rcx
  char *v50; // rcx
  int v51; // r9d
  __int64 v52; // [rsp+20h] [rbp-68h]
  _OWORD v53[5]; // [rsp+30h] [rbp-58h] BYREF

  v7 = a1;
  Count = -1073741275;
  if ( (a2 & 0x20) != 0 )
  {
    v53[0] = 0;
    if ( !a1 )
    {
      LdrpGetBaseNameFromFullName(0, v53);
      v7 = v53;
    }
    v9 = LdrpHashUnicodeString(v7);
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((_DWORD)v7, 0, a2, (_DWORD)a4, v9);
    if ( LoadedDllByNameLockHeld < 0 )
    {
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v10);
      v17 = 0;
      v12 = 0;
    }
    else
    {
      v12 = *(_DWORD *)(*(_QWORD *)(*a4 + 152LL) + 56LL);
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v10);
      v17 = 1;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v14, v13, v15, v16) )
      v21 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v21 = 2147353476;
    if ( *(_BYTE *)v21 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v22 = (unsigned int)RtlGetCurrentServiceSessionId(v21, v18, v19, v20)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v22 & 0x20) != 0 )
      {
        v23 = 0;
        v52 = (__int64)v7;
        if ( !v17 )
          v23 = 3;
LABEL_30:
        LdrpLogEtwEvent(5280, 0, 0, v23, v52, 0);
      }
    }
  }
  else
  {
    if ( (a2 & 0x200) == 0 )
      return (unsigned int)Count;
    v53[0] = 0;
    v12 = 0;
    LdrpGetBaseNameFromFullName(a1, v53);
    v24 = LdrpHashUnicodeString(v53);
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((unsigned int)v53, (_DWORD)v7, a2, (_DWORD)a4, v24);
    if ( LoadedDllByNameLockHeld >= 0 )
      v12 = *(_DWORD *)(*(_QWORD *)(*a4 + 152LL) + 56LL);
    RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v25);
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId(v27, v26, v28, v29);
    if ( v7 )
    {
      if ( CurrentServiceSessionId )
        v34 = (__int64)NtCurrentPeb()->SharedData + 554;
      else
        v34 = 2147353476;
      if ( *(_BYTE *)v34 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
      {
        v35 = (unsigned int)RtlGetCurrentServiceSessionId(v34, v31, v32, v33)
            ? (char *)NtCurrentPeb()->SharedData + 555
            : (char *)2147353477;
        if ( (*v35 & 0x20) != 0 )
        {
          v23 = 0;
          v52 = (__int64)v7;
          if ( LoadedDllByNameLockHeld < 0 )
            v23 = 3;
          goto LABEL_30;
        }
      }
    }
    else
    {
      if ( CurrentServiceSessionId )
        v49 = (__int64)NtCurrentPeb()->SharedData + 554;
      else
        v49 = 2147353476;
      if ( *(_BYTE *)v49 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
      {
        v50 = (unsigned int)RtlGetCurrentServiceSessionId(v49, v31, v32, v33)
            ? (char *)NtCurrentPeb()->SharedData + 555
            : (char *)2147353477;
        if ( (*v50 & 0x20) != 0 )
        {
          v51 = 0;
          if ( LoadedDllByNameLockHeld < 0 )
            v51 = 3;
          LdrpLogEtwEvent(5280, 0, 0, v51, (__int64)v53, 0);
        }
      }
    }
  }
  if ( LoadedDllByNameLockHeld >= 0 )
  {
    if ( *(_DWORD *)(*a4 + 268LL) == 9 )
    {
      Count = -1073740608;
      LdrpLogEtwHotPatchStatus(LdrpImageEntry + 88, *a4, 0, -1073740608, 2);
    }
    else if ( v12 == 9 )
    {
      Count = LdrpIncrementModuleLoadCount(*a4);
      if ( Count >= 0 )
      {
        Count = 0;
        if ( a3 )
        {
          v36 = *a4;
          SchedulerSharedDataSlot = NtCurrentTeb()->SchedulerSharedDataSlot;
          if ( SchedulerSharedDataSlot )
          {
            for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
            {
              if ( !SchedulerSharedDataSlot[i] )
              {
                SchedulerSharedDataSlot[i] = &LdrpModuleDatatableLock;
                break;
              }
            }
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)&LdrpModuleDatatableLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(&LdrpModuleDatatableLock, SchedulerSharedDataSlot);
          v40 = *(_QWORD *)(a3 + 152);
          if ( *(_DWORD *)(v40 + 24) || (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 )
          {
            v41 = *(_QWORD *)(v36 + 152);
            if ( (unsigned __int8)LdrpDependencyExist(*(_QWORD *)(a3 + 152), v41) )
            {
              v42 = *(_DWORD *)(v41 + 24);
              if ( (unsigned int)(v42 - 2) <= 0xFFFFFFFC )
                *(_DWORD *)(v41 + 24) = v42 - 1;
            }
            else
            {
              Heap_0 = RtlAllocateHeap_0(LdrpHeap, (unsigned int)(NtdllBaseTag + 2359296), 32);
              if ( Heap_0 )
              {
                *(_DWORD *)(Heap_0 + 24) |= 1u;
                v45 = *(__int64 **)(v40 + 40);
                if ( v45 )
                {
                  *(_QWORD *)Heap_0 = *v45;
                  *v45 = Heap_0;
                }
                else
                {
                  *(_QWORD *)Heap_0 = Heap_0;
                }
                *(_QWORD *)(v40 + 40) = Heap_0;
                v46 = (_QWORD *)(Heap_0 + 16);
                *(_QWORD *)(Heap_0 + 8) = v41;
                v47 = *(_QWORD **)(v41 + 48);
                if ( v47 )
                {
                  *v46 = *v47;
                  *v47 = v46;
                }
                else
                {
                  *v46 = v46;
                }
                *(_QWORD *)(v41 + 48) = v46;
                v48 = *(_DWORD *)(Heap_0 + 24);
                *(_QWORD *)(Heap_0 + 24) = v40;
                if ( (v48 & 1) != 0 )
                  *(_DWORD *)(Heap_0 + 24) = v40 ^ ((unsigned __int8)v48 ^ (unsigned __int8)v40) & 1;
              }
              else
              {
                Count = -1073741801;
              }
            }
          }
          else
          {
            Count = -1073741515;
          }
          RtlReleaseSRWLockExclusive(&LdrpModuleDatatableLock);
        }
        if ( Count >= 0 )
          return (unsigned int)Count;
        if ( (NtCurrentTeb()->SameTebFlags & 0x1000) != 0 )
        {
          LdrpDecrementModuleLoadCountEx(*a4, 0);
        }
        else
        {
          LdrpDrainWorkQueue(0);
          LdrpDecrementModuleLoadCountEx(*a4, 0);
          LdrpDropLastInProgressCount();
        }
      }
    }
    LdrpDereferenceModule(*a4);
    *a4 = 0;
    return (unsigned int)Count;
  }
  return (unsigned int)LoadedDllByNameLockHeld;
}

```

## disassembly

```asm
0x1800507b0  push    rbx
0x1800507b2  push    rbp
0x1800507b3  push    rsi
0x1800507b4  push    rdi
0x1800507b5  push    r12
0x1800507b7  push    r13
0x1800507b9  push    r14
0x1800507bb  push    r15
0x1800507bd  sub     rsp, 48h
0x1800507c1  mov     rsi, r9
0x1800507c4  mov     r13, r8
0x1800507c7  mov     ebx, edx
0x1800507c9  mov     rbp, rcx
0x1800507cc  mov     r14d, 0C0000225h
0x1800507d2  test    dl, 20h
0x1800507d5  jz      loc_1800508DA
0x1800507db  xorps   xmm0, xmm0
0x1800507de  movups  [rsp+88h+var_58], xmm0
0x1800507e3  test    rcx, rcx
0x1800507e6  jnz     short loc_1800507F7
0x1800507e8  lea     rdx, [rsp+88h+var_58]
0x1800507ed  call    LdrpGetBaseNameFromFullName
0x1800507f2  lea     rbp, [rsp+88h+var_58]
0x1800507f7  mov     rcx, rbp
0x1800507fa  call    LdrpHashUnicodeString
0x1800507ff  lea     r15, LdrpModuleDatatableLock
0x180050806  mov     edi, eax
0x180050808  mov     rcx, r15
0x18005080b  call    RtlAcquireSRWLockShared
0x180050810  mov     r9, rsi
0x180050813  mov     dword ptr [rsp+88h+var_68], edi
0x180050817  mov     r8d, ebx
0x18005081a  xor     edx, edx
0x18005081c  mov     rcx, rbp
0x18005081f  call    LdrpFindLoadedDllByNameLockHeld
0x180050824  mov     ebx, eax
0x180050826  test    eax, eax
0x180050828  js      loc_1800508C8
0x18005082e  mov     rax, [rsi]
0x180050831  mov     rcx, [rax+98h]
0x180050838  mov     r12d, [rcx+38h]
0x18005083c  mov     rcx, r15
0x18005083f  call    RtlReleaseSRWLockShared
0x180050844  mov     edi, 1
0x180050849  call    RtlGetCurrentServiceSessionId
0x18005084e  test    eax, eax
0x180050850  jnz     loc_180050C59
0x180050856  mov     ecx, 7FFE0384h
0x18005085b  cmp     byte ptr [rcx], 0
0x18005085e  jz      loc_1800509CD
0x180050864  mov     rax, gs:60h
0x18005086d  test    byte ptr [rax+378h], 4
0x180050874  jz      loc_1800509CD
0x18005087a  call    RtlGetCurrentServiceSessionId
0x18005087f  test    eax, eax
0x180050881  jz      loc_180050C75
0x180050887  mov     rax, gs:60h
0x180050890  mov     rcx, [rax+90h]
0x180050897  add     rcx, 22Bh
0x18005089e  test    byte ptr [rcx], 20h
0x1800508a1  jz      loc_1800509CD
0x1800508a7  xor     r9d, r9d
0x1800508aa  mov     [rsp+88h+var_60], 0
0x1800508b3  test    edi, edi
0x1800508b5  mov     [rsp+88h+var_68], rbp
0x1800508ba  mov     eax, 3
0x1800508bf  cmovz   r9d, eax
0x1800508c3  jmp     loc_1800509BE
0x1800508c8  mov     rcx, r15
0x1800508cb  call    RtlReleaseSRWLockShared
0x1800508d0  xor     edi, edi
0x1800508d2  xor     r12d, r12d
0x1800508d5  jmp     loc_180050849
0x1800508da  bt      ebx, 9
0x1800508de  jnb     loc_180050AC0
0x1800508e4  xorps   xmm0, xmm0
0x1800508e7  lea     rdx, [rsp+88h+var_58]
0x1800508ec  movups  [rsp+88h+var_58], xmm0
0x1800508f1  xor     r12d, r12d
0x1800508f4  call    LdrpGetBaseNameFromFullName
0x1800508f9  lea     rcx, [rsp+88h+var_58]
0x1800508fe  call    LdrpHashUnicodeString
0x180050903  lea     r15, LdrpModuleDatatableLock
0x18005090a  mov     edi, eax
0x18005090c  mov     rcx, r15
0x18005090f  call    RtlAcquireSRWLockShared
0x180050914  mov     r9, rsi
0x180050917  mov     dword ptr [rsp+88h+var_68], edi
0x18005091b  mov     r8d, ebx
0x18005091e  lea     rcx, [rsp+88h+var_58]
0x180050923  mov     rdx, rbp
0x180050926  call    LdrpFindLoadedDllByNameLockHeld
0x18005092b  mov     ebx, eax
0x18005092d  test    eax, eax
0x18005092f  js      short loc_18005093F
0x180050931  mov     rax, [rsi]
0x180050934  mov     rcx, [rax+98h]
0x18005093b  mov     r12d, [rcx+38h]
0x18005093f  mov     rcx, r15
0x180050942  call    RtlReleaseSRWLockShared
0x180050947  call    RtlGetCurrentServiceSessionId
0x18005094c  test    rbp, rbp
0x18005094f  jz      loc_180050B8C
0x180050955  test    eax, eax
0x180050957  jnz     loc_180050C33
0x18005095d  mov     ecx, 7FFE0384h
0x180050962  cmp     byte ptr [rcx], 0
0x180050965  jz      short loc_1800509CD
0x180050967  mov     rax, gs:60h
0x180050970  test    byte ptr [rax+378h], 4
0x180050977  jz      short loc_1800509CD
0x180050979  call    RtlGetCurrentServiceSessionId
0x18005097e  test    eax, eax
0x180050980  jz      loc_180050C4F
0x180050986  mov     rax, gs:60h
0x18005098f  mov     rcx, [rax+90h]
0x180050996  add     rcx, 22Bh
0x18005099d  test    byte ptr [rcx], 20h
0x1800509a0  jz      short loc_1800509CD
0x1800509a2  xor     r9d, r9d
0x1800509a5  mov     [rsp+88h+var_60], 0
0x1800509ae  test    ebx, ebx
0x1800509b0  mov     [rsp+88h+var_68], rbp
0x1800509b5  mov     eax, 3
0x1800509ba  cmovs   r9d, eax
0x1800509be  xor     r8d, r8d
0x1800509c1  xor     edx, edx
0x1800509c3  mov     ecx, 14A0h
0x1800509c8  call    LdrpLogEtwEvent
0x1800509cd  test    ebx, ebx
0x1800509cf  js      loc_180050AD5
0x1800509d5  mov     rax, [rsi]
0x1800509d8  cmp     dword ptr [rax+10Ch], 9
0x1800509df  jz      loc_180050CA0
0x1800509e5  cmp     r12d, 9
0x1800509e9  jnz     loc_180050AB1
0x1800509ef  mov     rcx, rax
0x1800509f2  call    LdrpIncrementModuleLoadCount
0x1800509f7  mov     r14d, eax
0x1800509fa  test    eax, eax
0x1800509fc  js      loc_180050AB1
0x180050a02  xor     r14d, r14d
0x180050a05  mov     ebp, 1000h
0x180050a0a  test    r13, r13
0x180050a0d  jz      short loc_180050A80
0x180050a0f  mov     rax, gs:30h
0x180050a18  mov     rdi, [rsi]
0x180050a1b  mov     rdx, [rax+1850h]
0x180050a22  test    rdx, rdx
0x180050a25  jz      short loc_180050A32
0x180050a27  xor     ecx, ecx
0x180050a29  cmp     ecx, 8
0x180050a2c  jb      loc_180050AD9
0x180050a32  lock bts qword ptr [r15], 0
0x180050a38  jb      loc_180050C1B
0x180050a3e  mov     rbx, [r13+98h]
0x180050a45  cmp     [rbx+18h], r14d
0x180050a49  jz      loc_180050C7F
0x180050a4f  mov     rdi, [rdi+98h]
0x180050a56  mov     rcx, rbx
0x180050a59  mov     rdx, rdi
0x180050a5c  call    LdrpDependencyExist
0x180050a61  test    al, al
0x180050a63  jz      loc_180050AEE
0x180050a69  mov     ecx, [rdi+18h]
0x180050a6c  lea     eax, [rcx-2]
0x180050a6f  cmp     eax, 0FFFFFFFCh
0x180050a72  jbe     loc_180050B79
0x180050a78  mov     rcx, r15
0x180050a7b  call    RtlReleaseSRWLockExclusive
0x180050a80  test    r14d, r14d
0x180050a83  jns     short loc_180050AC0
0x180050a85  mov     rax, gs:30h
0x180050a8e  test    [rax+17EEh], bp
0x180050a95  jnz     loc_180050CF2
0x180050a9b  xor     ecx, ecx
0x180050a9d  call    LdrpDrainWorkQueue
0x180050aa2  mov     rcx, [rsi]
0x180050aa5  xor     edx, edx
0x180050aa7  call    LdrpDecrementModuleLoadCountEx
0x180050aac  call    LdrpDropLastInProgressCount
0x180050ab1  mov     rcx, [rsi]
0x180050ab4  call    LdrpDereferenceModule
0x180050ab9  mov     qword ptr [rsi], 0
0x180050ac0  mov     eax, r14d
0x180050ac3  add     rsp, 48h
0x180050ac7  pop     r15
0x180050ac9  pop     r14
0x180050acb  pop     r13
0x180050acd  pop     r12
0x180050acf  pop     rdi
0x180050ad0  pop     rsi
0x180050ad1  pop     rbp
0x180050ad2  pop     rbx
0x180050ad3  retn
0x180050ad5  mov     eax, ebx
0x180050ad7  jmp     short loc_180050AC3
0x180050ad9  cmp     [rdx+rcx*8], r14
0x180050add  lea     r8, [rdx+rcx*8]
0x180050ae1  jz      loc_180050B84
0x180050ae7  inc     ecx
0x180050ae9  jmp     loc_180050A29
0x180050aee  mov     edx, cs:NtdllBaseTag
0x180050af4  mov     r8d, 20h ; ' '
0x180050afa  mov     rcx, cs:LdrpHeap
0x180050b01  add     edx, 240000h
0x180050b07  call    RtlAllocateHeap_0
0x180050b0c  mov     rcx, rax
0x180050b0f  test    rax, rax
0x180050b12  jz      loc_180050C28
0x180050b18  or      dword ptr [rax+18h], 1
0x180050b1c  mov     rdx, [rbx+28h]
0x180050b20  test    rdx, rdx
0x180050b23  jz      loc_180050C0B
0x180050b29  mov     rax, [rdx]
0x180050b2c  mov     [rcx], rax
0x180050b2f  mov     [rdx], rcx
0x180050b32  mov     [rbx+28h], rcx
0x180050b36  lea     rdx, [rcx+10h]
0x180050b3a  mov     [rcx+8], rdi
0x180050b3e  mov     r8, [rdi+30h]
0x180050b42  test    r8, r8
0x180050b45  jz      loc_180050C13
0x180050b4b  mov     rax, [r8]
0x180050b4e  mov     [rdx], rax
0x180050b51  mov     [r8], rdx
0x180050b54  mov     [rdi+30h], rdx
0x180050b58  mov     edx, [rcx+18h]
0x180050b5b  mov     [rcx+18h], rbx
0x180050b5f  test    dl, 1
0x180050b62  jz      loc_180050A78
0x180050b68  mov     eax, ebx
0x180050b6a  xor     eax, edx
0x180050b6c  and     eax, 1
0x180050b6f  xor     eax, ebx
0x180050b71  mov     [rcx+18h], eax
0x180050b74  jmp     loc_180050A78
0x180050b79  lea     eax, [rcx-1]
0x180050b7c  mov     [rdi+18h], eax
0x180050b7f  jmp     loc_180050A78
0x180050b84  mov     [r8], r15
0x180050b87  jmp     loc_180050A32
0x180050b8c  test    eax, eax
0x180050b8e  jnz     loc_180050CCC
0x180050b94  mov     ecx, 7FFE0384h
0x180050b99  cmp     byte ptr [rcx], 0
0x180050b9c  jz      loc_1800509CD
0x180050ba2  mov     rax, gs:60h
0x180050bab  test    byte ptr [rax+378h], 4
0x180050bb2  jz      loc_1800509CD
0x180050bb8  call    RtlGetCurrentServiceSessionId
0x180050bbd  test    eax, eax
0x180050bbf  jz      loc_180050CE8
0x180050bc5  mov     rax, gs:60h
0x180050bce  mov     rcx, [rax+90h]
0x180050bd5  add     rcx, 22Bh
0x180050bdc  test    byte ptr [rcx], 20h
0x180050bdf  jz      loc_1800509CD
0x180050be5  xor     r9d, r9d
0x180050be8  mov     [rsp+88h+var_60], 0
0x180050bf1  mov     eax, 3
0x180050bf6  test    ebx, ebx
0x180050bf8  cmovs   r9d, eax
0x180050bfc  lea     rax, [rsp+88h+var_58]
0x180050c01  mov     [rsp+88h+var_68], rax
0x180050c06  jmp     loc_1800509BE
0x180050c0b  mov     [rax], rcx
0x180050c0e  jmp     loc_180050B32
0x180050c13  mov     [rdx], rdx
0x180050c16  jmp     loc_180050B54
0x180050c1b  mov     rcx, r15
0x180050c1e  call    RtlpAcquireSRWLockExclusiveContended
0x180050c23  jmp     loc_180050A3E
0x180050c28  mov     r14d, 0C0000017h
0x180050c2e  jmp     loc_180050A78
0x180050c33  mov     rax, gs:60h
0x180050c3c  mov     rcx, [rax+90h]
0x180050c43  add     rcx, 22Ah
0x180050c4a  jmp     loc_180050962
0x180050c4f  mov     ecx, 7FFE0385h
0x180050c54  jmp     loc_18005099D
0x180050c59  mov     rax, gs:60h
0x180050c62  mov     rcx, [rax+90h]
0x180050c69  add     rcx, 22Ah
0x180050c70  jmp     loc_18005085B
0x180050c75  mov     ecx, 7FFE0385h
0x180050c7a  jmp     loc_18005089E
0x180050c7f  mov     rax, gs:30h
0x180050c88  test    [rax+17EEh], bp
0x180050c8f  jnz     loc_180050A4F
0x180050c95  mov     r14d, 0C0000135h
0x180050c9b  jmp     loc_180050A78
0x180050ca0  mov     rcx, cs:LdrpImageEntry
0x180050ca7  mov     r14d, 0C00004C0h
0x180050cad  add     rcx, 58h ; 'X'
0x180050cb1  mov     dword ptr [rsp+88h+var_68], 2
0x180050cb9  mov     r9d, r14d
0x180050cbc  xor     r8d, r8d
0x180050cbf  mov     rdx, rax
0x180050cc2  call    LdrpLogEtwHotPatchStatus
  ... truncated ...
```
