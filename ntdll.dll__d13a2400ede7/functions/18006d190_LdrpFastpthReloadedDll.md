# LdrpFastpthReloadedDll

- ea: `0x18006d190`
- end: `0x18006d6e1`
- name: `LdrpFastpthReloadedDll`
- size: `1361`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180024990`

## callees

- `0x1800183a0`
- `0x18001b984`
- `0x1800254d0`
- `0x1800259ec`
- `0x18002cde0`
- `0x180069af8`
- `0x18006cbbc`
- `0x18006d190`
- `0x18006f0d0`
- `0x18006f100`
- `0x18006fb30`
- `0x1800707b0`
- `0x180070814`
- `0x180070910`
- `0x1800709e0`
- `0x1800bf8f4`
- `0x1800fbfb0`
- `0x1800fd448`

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
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((_DWORD)v7, 0, a2, (_DWORD)a4, v9);
    if ( LoadedDllByNameLockHeld < 0 )
    {
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v10);
      v17 = 0;
      v12 = 0;
    }
    else
    {
      v12 = *(_DWORD *)(*(_QWORD *)(*a4 + 152LL) + 56LL);
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v10);
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
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((unsigned int)v53, (_DWORD)v7, a2, (_DWORD)a4, v24);
    if ( LoadedDllByNameLockHeld >= 0 )
      v12 = *(_DWORD *)(*(_QWORD *)(*a4 + 152LL) + 56LL);
    RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v25);
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
                SchedulerSharedDataSlot[i] = LdrpModuleDatatableLock;
                break;
              }
            }
          }
          if ( _interlockedbittestandset64((volatile signed __int32 *)LdrpModuleDatatableLock, 0) )
            RtlpAcquireSRWLockExclusiveContended(LdrpModuleDatatableLock);
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
          RtlReleaseSRWLockExclusive(LdrpModuleDatatableLock);
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
0x18006d190  push    rbx
0x18006d192  push    rbp
0x18006d193  push    rsi
0x18006d194  push    rdi
0x18006d195  push    r12
0x18006d197  push    r13
0x18006d199  push    r14
0x18006d19b  push    r15
0x18006d19d  sub     rsp, 48h
0x18006d1a1  mov     rsi, r9
0x18006d1a4  mov     r13, r8
0x18006d1a7  mov     ebx, edx
0x18006d1a9  mov     rbp, rcx
0x18006d1ac  mov     r14d, 0C0000225h
0x18006d1b2  test    dl, 20h
0x18006d1b5  jz      loc_18006D2BA
0x18006d1bb  xorps   xmm0, xmm0
0x18006d1be  movups  [rsp+88h+var_58], xmm0
0x18006d1c3  test    rcx, rcx
0x18006d1c6  jnz     short loc_18006D1D7
0x18006d1c8  lea     rdx, [rsp+88h+var_58]
0x18006d1cd  call    LdrpGetBaseNameFromFullName
0x18006d1d2  lea     rbp, [rsp+88h+var_58]
0x18006d1d7  mov     rcx, rbp
0x18006d1da  call    LdrpHashUnicodeString
0x18006d1df  lea     r15, LdrpModuleDatatableLock
0x18006d1e6  mov     edi, eax
0x18006d1e8  mov     rcx, r15
0x18006d1eb  call    RtlAcquireSRWLockShared
0x18006d1f0  mov     r9, rsi
0x18006d1f3  mov     dword ptr [rsp+88h+var_68], edi
0x18006d1f7  mov     r8d, ebx
0x18006d1fa  xor     edx, edx
0x18006d1fc  mov     rcx, rbp
0x18006d1ff  call    LdrpFindLoadedDllByNameLockHeld
0x18006d204  mov     ebx, eax
0x18006d206  test    eax, eax
0x18006d208  js      loc_18006D2A8
0x18006d20e  mov     rax, [rsi]
0x18006d211  mov     rcx, [rax+98h]
0x18006d218  mov     r12d, [rcx+38h]
0x18006d21c  mov     rcx, r15
0x18006d21f  call    RtlReleaseSRWLockShared
0x18006d224  mov     edi, 1
0x18006d229  call    RtlGetCurrentServiceSessionId
0x18006d22e  test    eax, eax
0x18006d230  jnz     loc_18006D639
0x18006d236  mov     ecx, 7FFE0384h
0x18006d23b  cmp     byte ptr [rcx], 0
0x18006d23e  jz      loc_18006D3AD
0x18006d244  mov     rax, gs:60h
0x18006d24d  test    byte ptr [rax+378h], 4
0x18006d254  jz      loc_18006D3AD
0x18006d25a  call    RtlGetCurrentServiceSessionId
0x18006d25f  test    eax, eax
0x18006d261  jz      loc_18006D655
0x18006d267  mov     rax, gs:60h
0x18006d270  mov     rcx, [rax+90h]
0x18006d277  add     rcx, 22Bh
0x18006d27e  test    byte ptr [rcx], 20h
0x18006d281  jz      loc_18006D3AD
0x18006d287  xor     r9d, r9d
0x18006d28a  mov     [rsp+88h+var_60], 0
0x18006d293  test    edi, edi
0x18006d295  mov     [rsp+88h+var_68], rbp
0x18006d29a  mov     eax, 3
0x18006d29f  cmovz   r9d, eax
0x18006d2a3  jmp     loc_18006D39E
0x18006d2a8  mov     rcx, r15
0x18006d2ab  call    RtlReleaseSRWLockShared
0x18006d2b0  xor     edi, edi
0x18006d2b2  xor     r12d, r12d
0x18006d2b5  jmp     loc_18006D229
0x18006d2ba  bt      ebx, 9
0x18006d2be  jnb     loc_18006D4A0
0x18006d2c4  xorps   xmm0, xmm0
0x18006d2c7  lea     rdx, [rsp+88h+var_58]
0x18006d2cc  movups  [rsp+88h+var_58], xmm0
0x18006d2d1  xor     r12d, r12d
0x18006d2d4  call    LdrpGetBaseNameFromFullName
0x18006d2d9  lea     rcx, [rsp+88h+var_58]
0x18006d2de  call    LdrpHashUnicodeString
0x18006d2e3  lea     r15, LdrpModuleDatatableLock
0x18006d2ea  mov     edi, eax
0x18006d2ec  mov     rcx, r15
0x18006d2ef  call    RtlAcquireSRWLockShared
0x18006d2f4  mov     r9, rsi
0x18006d2f7  mov     dword ptr [rsp+88h+var_68], edi
0x18006d2fb  mov     r8d, ebx
0x18006d2fe  lea     rcx, [rsp+88h+var_58]
0x18006d303  mov     rdx, rbp
0x18006d306  call    LdrpFindLoadedDllByNameLockHeld
0x18006d30b  mov     ebx, eax
0x18006d30d  test    eax, eax
0x18006d30f  js      short loc_18006D31F
0x18006d311  mov     rax, [rsi]
0x18006d314  mov     rcx, [rax+98h]
0x18006d31b  mov     r12d, [rcx+38h]
0x18006d31f  mov     rcx, r15
0x18006d322  call    RtlReleaseSRWLockShared
0x18006d327  call    RtlGetCurrentServiceSessionId
0x18006d32c  test    rbp, rbp
0x18006d32f  jz      loc_18006D56C
0x18006d335  test    eax, eax
0x18006d337  jnz     loc_18006D613
0x18006d33d  mov     ecx, 7FFE0384h
0x18006d342  cmp     byte ptr [rcx], 0
0x18006d345  jz      short loc_18006D3AD
0x18006d347  mov     rax, gs:60h
0x18006d350  test    byte ptr [rax+378h], 4
0x18006d357  jz      short loc_18006D3AD
0x18006d359  call    RtlGetCurrentServiceSessionId
0x18006d35e  test    eax, eax
0x18006d360  jz      loc_18006D62F
0x18006d366  mov     rax, gs:60h
0x18006d36f  mov     rcx, [rax+90h]
0x18006d376  add     rcx, 22Bh
0x18006d37d  test    byte ptr [rcx], 20h
0x18006d380  jz      short loc_18006D3AD
0x18006d382  xor     r9d, r9d
0x18006d385  mov     [rsp+88h+var_60], 0
0x18006d38e  test    ebx, ebx
0x18006d390  mov     [rsp+88h+var_68], rbp
0x18006d395  mov     eax, 3
0x18006d39a  cmovs   r9d, eax
0x18006d39e  xor     r8d, r8d
0x18006d3a1  xor     edx, edx
0x18006d3a3  mov     ecx, 14A0h
0x18006d3a8  call    LdrpLogEtwEvent
0x18006d3ad  test    ebx, ebx
0x18006d3af  js      loc_18006D4B5
0x18006d3b5  mov     rax, [rsi]
0x18006d3b8  cmp     dword ptr [rax+10Ch], 9
0x18006d3bf  jz      loc_18006D680
0x18006d3c5  cmp     r12d, 9
0x18006d3c9  jnz     loc_18006D491
0x18006d3cf  mov     rcx, rax
0x18006d3d2  call    LdrpIncrementModuleLoadCount
0x18006d3d7  mov     r14d, eax
0x18006d3da  test    eax, eax
0x18006d3dc  js      loc_18006D491
0x18006d3e2  xor     r14d, r14d
0x18006d3e5  mov     ebp, 1000h
0x18006d3ea  test    r13, r13
0x18006d3ed  jz      short loc_18006D460
0x18006d3ef  mov     rax, gs:30h
0x18006d3f8  mov     rdi, [rsi]
0x18006d3fb  mov     rdx, [rax+1850h]
0x18006d402  test    rdx, rdx
0x18006d405  jz      short loc_18006D412
0x18006d407  xor     ecx, ecx
0x18006d409  cmp     ecx, 8
0x18006d40c  jb      loc_18006D4B9
0x18006d412  lock bts qword ptr [r15], 0
0x18006d418  jb      loc_18006D5FB
0x18006d41e  mov     rbx, [r13+98h]
0x18006d425  cmp     [rbx+18h], r14d
0x18006d429  jz      loc_18006D65F
0x18006d42f  mov     rdi, [rdi+98h]
0x18006d436  mov     rcx, rbx
0x18006d439  mov     rdx, rdi
0x18006d43c  call    LdrpDependencyExist
0x18006d441  test    al, al
0x18006d443  jz      loc_18006D4CE
0x18006d449  mov     ecx, [rdi+18h]
0x18006d44c  lea     eax, [rcx-2]
0x18006d44f  cmp     eax, 0FFFFFFFCh
0x18006d452  jbe     loc_18006D559
0x18006d458  mov     rcx, r15
0x18006d45b  call    RtlReleaseSRWLockExclusive
0x18006d460  test    r14d, r14d
0x18006d463  jns     short loc_18006D4A0
0x18006d465  mov     rax, gs:30h
0x18006d46e  test    [rax+17EEh], bp
0x18006d475  jnz     loc_18006D6D2
0x18006d47b  xor     ecx, ecx
0x18006d47d  call    LdrpDrainWorkQueue
0x18006d482  mov     rcx, [rsi]
0x18006d485  xor     edx, edx
0x18006d487  call    LdrpDecrementModuleLoadCountEx
0x18006d48c  call    LdrpDropLastInProgressCount
0x18006d491  mov     rcx, [rsi]
0x18006d494  call    LdrpDereferenceModule
0x18006d499  mov     qword ptr [rsi], 0
0x18006d4a0  mov     eax, r14d
0x18006d4a3  add     rsp, 48h
0x18006d4a7  pop     r15
0x18006d4a9  pop     r14
0x18006d4ab  pop     r13
0x18006d4ad  pop     r12
0x18006d4af  pop     rdi
0x18006d4b0  pop     rsi
0x18006d4b1  pop     rbp
0x18006d4b2  pop     rbx
0x18006d4b3  retn
0x18006d4b5  mov     eax, ebx
0x18006d4b7  jmp     short loc_18006D4A3
0x18006d4b9  cmp     [rdx+rcx*8], r14
0x18006d4bd  lea     r8, [rdx+rcx*8]
0x18006d4c1  jz      loc_18006D564
0x18006d4c7  inc     ecx
0x18006d4c9  jmp     loc_18006D409
0x18006d4ce  mov     edx, cs:NtdllBaseTag
0x18006d4d4  mov     r8d, 20h ; ' '
0x18006d4da  mov     rcx, cs:LdrpHeap
0x18006d4e1  add     edx, 240000h
0x18006d4e7  call    RtlAllocateHeap_0
0x18006d4ec  mov     rcx, rax
0x18006d4ef  test    rax, rax
0x18006d4f2  jz      loc_18006D608
0x18006d4f8  or      dword ptr [rax+18h], 1
0x18006d4fc  mov     rdx, [rbx+28h]
0x18006d500  test    rdx, rdx
0x18006d503  jz      loc_18006D5EB
0x18006d509  mov     rax, [rdx]
0x18006d50c  mov     [rcx], rax
0x18006d50f  mov     [rdx], rcx
0x18006d512  mov     [rbx+28h], rcx
0x18006d516  lea     rdx, [rcx+10h]
0x18006d51a  mov     [rcx+8], rdi
0x18006d51e  mov     r8, [rdi+30h]
0x18006d522  test    r8, r8
0x18006d525  jz      loc_18006D5F3
0x18006d52b  mov     rax, [r8]
0x18006d52e  mov     [rdx], rax
0x18006d531  mov     [r8], rdx
0x18006d534  mov     [rdi+30h], rdx
0x18006d538  mov     edx, [rcx+18h]
0x18006d53b  mov     [rcx+18h], rbx
0x18006d53f  test    dl, 1
0x18006d542  jz      loc_18006D458
0x18006d548  mov     eax, ebx
0x18006d54a  xor     eax, edx
0x18006d54c  and     eax, 1
0x18006d54f  xor     eax, ebx
0x18006d551  mov     [rcx+18h], eax
0x18006d554  jmp     loc_18006D458
0x18006d559  lea     eax, [rcx-1]
0x18006d55c  mov     [rdi+18h], eax
0x18006d55f  jmp     loc_18006D458
0x18006d564  mov     [r8], r15
0x18006d567  jmp     loc_18006D412
0x18006d56c  test    eax, eax
0x18006d56e  jnz     loc_18006D6AC
0x18006d574  mov     ecx, 7FFE0384h
0x18006d579  cmp     byte ptr [rcx], 0
0x18006d57c  jz      loc_18006D3AD
0x18006d582  mov     rax, gs:60h
0x18006d58b  test    byte ptr [rax+378h], 4
0x18006d592  jz      loc_18006D3AD
0x18006d598  call    RtlGetCurrentServiceSessionId
0x18006d59d  test    eax, eax
0x18006d59f  jz      loc_18006D6C8
0x18006d5a5  mov     rax, gs:60h
0x18006d5ae  mov     rcx, [rax+90h]
0x18006d5b5  add     rcx, 22Bh
0x18006d5bc  test    byte ptr [rcx], 20h
0x18006d5bf  jz      loc_18006D3AD
0x18006d5c5  xor     r9d, r9d
0x18006d5c8  mov     [rsp+88h+var_60], 0
0x18006d5d1  mov     eax, 3
0x18006d5d6  test    ebx, ebx
0x18006d5d8  cmovs   r9d, eax
0x18006d5dc  lea     rax, [rsp+88h+var_58]
0x18006d5e1  mov     [rsp+88h+var_68], rax
0x18006d5e6  jmp     loc_18006D39E
0x18006d5eb  mov     [rax], rcx
0x18006d5ee  jmp     loc_18006D512
0x18006d5f3  mov     [rdx], rdx
0x18006d5f6  jmp     loc_18006D534
0x18006d5fb  mov     rcx, r15
0x18006d5fe  call    RtlpAcquireSRWLockExclusiveContended
0x18006d603  jmp     loc_18006D41E
0x18006d608  mov     r14d, 0C0000017h
0x18006d60e  jmp     loc_18006D458
0x18006d613  mov     rax, gs:60h
0x18006d61c  mov     rcx, [rax+90h]
0x18006d623  add     rcx, 22Ah
0x18006d62a  jmp     loc_18006D342
0x18006d62f  mov     ecx, 7FFE0385h
0x18006d634  jmp     loc_18006D37D
0x18006d639  mov     rax, gs:60h
0x18006d642  mov     rcx, [rax+90h]
0x18006d649  add     rcx, 22Ah
0x18006d650  jmp     loc_18006D23B
0x18006d655  mov     ecx, 7FFE0385h
0x18006d65a  jmp     loc_18006D27E
0x18006d65f  mov     rax, gs:30h
0x18006d668  test    [rax+17EEh], bp
0x18006d66f  jnz     loc_18006D42F
0x18006d675  mov     r14d, 0C0000135h
0x18006d67b  jmp     loc_18006D458
0x18006d680  mov     rcx, cs:LdrpImageEntry
0x18006d687  mov     r14d, 0C00004C0h
0x18006d68d  add     rcx, 58h ; 'X'
0x18006d691  mov     dword ptr [rsp+88h+var_68], 2
0x18006d699  mov     r9d, r14d
0x18006d69c  xor     r8d, r8d
0x18006d69f  mov     rdx, rax
0x18006d6a2  call    LdrpLogEtwHotPatchStatus
  ... truncated ...
```
