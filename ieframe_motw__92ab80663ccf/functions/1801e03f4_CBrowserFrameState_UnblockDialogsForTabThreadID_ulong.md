# CBrowserFrameState::UnblockDialogsForTabThreadID(ulong)

- ea: `0x1801e03f4`
- end: `0x1801e0722`
- name: `?UnblockDialogsForTabThreadID@CBrowserFrameState@@QEAAXK@Z`
- size: `814`
- prototype: `void __fastcall(CBrowserFrameState *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802aaebc`

## callees

- `0x180009610`
- `0x1801dd1f0`
- `0x1801e03f4`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801e0635`
- `KERNEL32!SetEvent` at `0x1801e06d1`
- `KERNEL32!SetEvent` at `0x1801e0635`
- `KERNEL32!SetEvent` at `0x1801e06d1`
- `KERNEL32!CreateEventW` at `0x1801e061e`
- `KERNEL32!CreateEventW` at `0x1801e061e`
- `KERNEL32!CloseHandle` at `0x1801e0654`
- `KERNEL32!CloseHandle` at `0x1801e0654`
- `KERNEL32!GetLastError` at `0x1801e0645`
- `KERNEL32!GetLastError` at `0x1801e0645`
- `KERNEL32!GetCurrentThreadId` at `0x1801e043d`
- `KERNEL32!GetCurrentThreadId` at `0x1801e04a2`
- `KERNEL32!GetCurrentThreadId` at `0x1801e043d`
- `KERNEL32!GetCurrentThreadId` at `0x1801e04a2`
- `KERNEL32!LeaveCriticalSection` at `0x1801e06f6`
- `KERNEL32!LeaveCriticalSection` at `0x1801e06f6`
- `KERNEL32!EnterCriticalSection` at `0x1801e04c9`
- `KERNEL32!EnterCriticalSection` at `0x1801e04c9`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801e06e3`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801e06e3`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801e0691`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801e0691`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801e0605`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801e0605`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801e04b6`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801e04b6`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801e0512`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801e0512`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801e046e`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801e046e`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801e05d2`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801e05d2`

## pseudocode

```c
void __fastcall CBrowserFrameState::UnblockDialogsForTabThreadID(CBrowserFrameState *this, int a2)
{
  unsigned int v4; // edx
  int v5; // ebx
  unsigned int v6; // ecx
  __int64 i; // rbx
  char *v8; // rsi
  unsigned int v9; // edx
  struct IsoScope *DefaultScope; // rax
  unsigned int *v11; // rax
  HANDLE EventW; // rax
  void *v13; // r15
  int *v14; // rax
  int v15; // ebx
  int j; // ebx
  HANDLE *ItemPtr; // rax
  HANDLE *v18; // rsi
  __int64 v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  struct _IsoUntrustedComponent *v23; // [rsp+40h] [rbp-C0h] BYREF
  struct _IsoComponent *v24; // [rsp+48h] [rbp-B8h] BYREF
  char *v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[28]; // [rsp+60h] [rbp-A0h] BYREF
  char v27[100]; // [rsp+7Ch] [rbp-84h] BYREF
  WCHAR Name[128]; // [rsp+E0h] [rbp-20h] BYREF

  v24 = 0;
  v23 = 0;
  v21 = 0;
  if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    v4 = 0;
  else
    v4 = 2;
  if ( (int)IsoGetTrustSplitComponent(*((_DWORD *)this + 5), v4, &v24, &v21, &v23) >= 0 )
  {
    if ( dword_1806A733C && !*((_DWORD *)this + 6) && *((_DWORD *)v23 + 25) )
      *((_DWORD *)this + 6) = *((_DWORD *)v23 + 25);
    v5 = *((_DWORD *)this + 10);
    if ( v5 != GetCurrentThreadId() )
      IsoUnlockArtifact(v21);
  }
  EnterCriticalSection(&g_csDll);
  if ( dword_1806A733C )
  {
    v6 = *((_DWORD *)this + 6);
    if ( v6 )
    {
      if ( a2 != -1 )
      {
        v25 = 0;
        v22 = 0;
        if ( (int)IsoLockSharedMemory(v6, (void **)&v25, &v22) >= 0 && v22 >= 0x320 )
        {
          for ( i = 0; i != 20; ++i )
          {
            v8 = &v25[40 * i];
            if ( v8 )
            {
              v9 = *((_DWORD *)v8 + 7);
              if ( v9 )
              {
                v20 = 0;
                if ( (int)CBrowserFrameState::FindRootTabThreadID(this, v9, &v20) >= 0 && a2 == v20 && (v8[24] & 2) != 0 )
                {
                  *(_OWORD *)v26 = *(_OWORD *)L"IEtd_xxxxxxxx";
                  *(_OWORD *)&v26[12] = *(_OWORD *)L"xxxxxxx";
                  memset_0(v27, 0, sizeof(v27));
                  LODWORD(v19) = *((_DWORD *)v8 + 9);
                  StringCchPrintfW((unsigned __int16 *)v26, 0x40u, L"IE_tab_dialog_%08x_%08x", *((_QWORD *)v8 + 1), v19);
                  DefaultScope = IsoGetDefaultScope();
                  v11 = (unsigned int *)(*(__int64 (__fastcall **)(struct IsoScope *))(*(_QWORD *)DefaultScope + 256LL))(DefaultScope);
                  IsoPrefixScopeQualifierToName(v11, Name, 0x80u, (const unsigned __int16 *)v26);
                  EventW = CreateEventW(0, 1, 0, Name);
                  v13 = EventW;
                  if ( EventW )
                  {
                    if ( !SetEvent(EventW) )
                      GetLastError();
                    CloseHandle(v13);
                  }
                  *((_DWORD *)v8 + 7) = 0;
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v14 = (int *)*((_QWORD *)this + 9);
    if ( v14 )
      v15 = *v14;
    else
      v15 = 0;
    for ( j = v15 - 1; j >= 0; --j )
    {
      ItemPtr = (HANDLE *)DSA_GetItemPtr(*((HDSA *)this + 9), j);
      v20 = 0;
      v18 = ItemPtr;
      if ( (int)CBrowserFrameState::FindRootTabThreadID(this, *((_DWORD *)ItemPtr + 7), &v20) >= 0
        && a2 == v20
        && ((_BYTE)v18[3] & 2) != 0 )
      {
        SetEvent(v18[2]);
        DSA_DeleteItem(*((HDSA *)this + 9), j);
        break;
      }
    }
  }
  LeaveCriticalSection(&g_csDll);
}

```

## disassembly

```asm
0x1801e03f4  push    rbp
0x1801e03f6  push    rbx
0x1801e03f7  push    rsi
0x1801e03f8  push    rdi
0x1801e03f9  push    r14
0x1801e03fb  push    r15
0x1801e03fd  lea     rbp, [rsp-0F8h]
0x1801e0405  sub     rsp, 1F8h
0x1801e040c  mov     rax, cs:__security_cookie
0x1801e0413  xor     rax, rsp
0x1801e0416  mov     [rbp+120h+var_40], rax
0x1801e041d  mov     r14d, edx
0x1801e0420  mov     [rsp+220h+var_1D8], 0
0x1801e0429  mov     rdi, rcx
0x1801e042c  mov     [rsp+220h+var_1E0], 0
0x1801e0435  mov     [rsp+220h+var_1EC], 0
0x1801e043d  call    cs:__imp_GetCurrentThreadId
0x1801e0444  nop     dword ptr [rax+rax+00h]
0x1801e0449  mov     ecx, [rdi+14h]
0x1801e044c  lea     r9, [rsp+220h+var_1EC]
0x1801e0451  cmp     [rdi+28h], eax
0x1801e0454  lea     r8, [rsp+220h+var_1D8]
0x1801e0459  lea     rax, [rsp+220h+var_1E0]
0x1801e045e  mov     [rsp+220h+var_200], rax
0x1801e0463  jz      short loc_1801E046C
0x1801e0465  mov     edx, 2
0x1801e046a  jmp     short loc_1801E046E
0x1801e046c  xor     edx, edx
0x1801e046e  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801e0475  nop     dword ptr [rax+rax+00h]
0x1801e047a  test    eax, eax
0x1801e047c  js      short loc_1801E04C2
0x1801e047e  cmp     cs:dword_1806A733C, 0
0x1801e0485  jz      short loc_1801E049F
0x1801e0487  cmp     dword ptr [rdi+18h], 0
0x1801e048b  jnz     short loc_1801E049F
0x1801e048d  mov     rcx, [rsp+220h+var_1E0]
0x1801e0492  mov     eax, [rcx+64h]
0x1801e0495  test    eax, eax
0x1801e0497  jz      short loc_1801E049F
0x1801e0499  mov     eax, [rcx+64h]
0x1801e049c  mov     [rdi+18h], eax
0x1801e049f  mov     ebx, [rdi+28h]
0x1801e04a2  call    cs:__imp_GetCurrentThreadId
0x1801e04a9  nop     dword ptr [rax+rax+00h]
0x1801e04ae  cmp     ebx, eax
0x1801e04b0  jz      short loc_1801E04C2
0x1801e04b2  mov     ecx, [rsp+220h+var_1EC]
0x1801e04b6  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801e04bd  nop     dword ptr [rax+rax+00h]
0x1801e04c2  lea     rcx, g_csDll; lpCriticalSection
0x1801e04c9  call    cs:__imp_EnterCriticalSection
0x1801e04d0  nop     dword ptr [rax+rax+00h]
0x1801e04d5  cmp     cs:dword_1806A733C, 0
0x1801e04dc  jz      loc_1801E0676
0x1801e04e2  mov     ecx, [rdi+18h]
0x1801e04e5  test    ecx, ecx
0x1801e04e7  jz      loc_1801E06EF
0x1801e04ed  cmp     r14d, 0FFFFFFFFh
0x1801e04f1  jz      loc_1801E06EF
0x1801e04f7  lea     r8, [rsp+220h+var_1E8]
0x1801e04fc  mov     [rsp+220h+var_1D0], 0
0x1801e0505  lea     rdx, [rsp+220h+var_1D0]
0x1801e050a  mov     [rsp+220h+var_1E8], 0
0x1801e0512  call    cs:__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z; IsoLockSharedMemory(ulong,void * *,ulong *)
0x1801e0519  nop     dword ptr [rax+rax+00h]
0x1801e051e  test    eax, eax
0x1801e0520  js      loc_1801E06EF
0x1801e0526  cmp     [rsp+220h+var_1E8], 320h
0x1801e052e  jb      loc_1801E06EF
0x1801e0534  xor     ebx, ebx
0x1801e0536  mov     rax, [rsp+220h+var_1D0]
0x1801e053b  lea     rcx, [rbx+rbx*4]
0x1801e053f  lea     rsi, [rax+rcx*8]
0x1801e0543  test    rsi, rsi
0x1801e0546  jz      loc_1801E0667
0x1801e054c  mov     edx, [rsi+1Ch]; unsigned int
0x1801e054f  test    edx, edx
0x1801e0551  jz      loc_1801E0667
0x1801e0557  lea     r8, [rsp+220h+var_1F0]; unsigned int *
0x1801e055c  mov     [rsp+220h+var_1F0], 0
0x1801e0564  mov     rcx, rdi; this
0x1801e0567  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801e056c  test    eax, eax
0x1801e056e  js      loc_1801E0667
0x1801e0574  cmp     r14d, [rsp+220h+var_1F0]
0x1801e0579  jnz     loc_1801E0667
0x1801e057f  test    byte ptr [rsi+18h], 2
0x1801e0583  jz      loc_1801E0667
0x1801e0589  movups  xmm0, xmmword ptr cs:aIetdXxxxxxxx; "IEtd_xxxxxxxx"
0x1801e0590  xor     edx, edx; Val
0x1801e0592  lea     rcx, [rsp+220h+var_1A4]; void *
0x1801e0597  movups  xmm1, xmmword ptr cs:aIetdXxxxxxxx+0Ch; "xxxxxxx"
0x1801e059e  movaps  xmmword ptr [rsp+220h+var_1C0], xmm0
0x1801e05a3  lea     r8d, [rdx+64h]; Size
0x1801e05a7  movups  xmmword ptr [rsp+220h+var_1C0+0Ch], xmm1
0x1801e05ac  call    memset_0
0x1801e05b1  mov     eax, [rsi+24h]
0x1801e05b4  lea     r8, aIeTabDialog08x; "IE_tab_dialog_%08x_%08x"
0x1801e05bb  mov     r9, [rsi+8]
0x1801e05bf  lea     rcx, [rsp+220h+var_1C0]; unsigned __int16 *
0x1801e05c4  mov     edx, 40h ; '@'; unsigned __int64
0x1801e05c9  mov     dword ptr [rsp+220h+var_200], eax
0x1801e05cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801e05d2  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801e05d9  nop     dword ptr [rax+rax+00h]
0x1801e05de  mov     rdx, rax
0x1801e05e1  mov     rcx, [rax]
0x1801e05e4  mov     rax, [rcx+100h]
0x1801e05eb  mov     rcx, rdx
0x1801e05ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e05f3  mov     rcx, rax
0x1801e05f6  lea     r9, [rsp+220h+var_1C0]
0x1801e05fb  mov     r8d, 80h
0x1801e0601  lea     rdx, [rbp+120h+Name]
0x1801e0605  call    cs:__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z; IsoPrefixScopeQualifierToName(ulong *,ushort *,ulong,ushort const *)
0x1801e060c  nop     dword ptr [rax+rax+00h]
0x1801e0611  xor     r8d, r8d; bInitialState
0x1801e0614  lea     r9, [rbp+120h+Name]; lpName
0x1801e0618  xor     ecx, ecx; lpEventAttributes
0x1801e061a  lea     edx, [r8+1]; bManualReset
0x1801e061e  call    cs:__imp_CreateEventW
0x1801e0625  nop     dword ptr [rax+rax+00h]
0x1801e062a  mov     r15, rax
0x1801e062d  test    rax, rax
0x1801e0630  jz      short loc_1801E0660
0x1801e0632  mov     rcx, rax; hEvent
0x1801e0635  call    cs:__imp_SetEvent
0x1801e063c  nop     dword ptr [rax+rax+00h]
0x1801e0641  test    eax, eax
0x1801e0643  jnz     short loc_1801E0651
0x1801e0645  call    cs:__imp_GetLastError
0x1801e064c  nop     dword ptr [rax+rax+00h]
0x1801e0651  mov     rcx, r15; hObject
0x1801e0654  call    cs:__imp_CloseHandle
0x1801e065b  nop     dword ptr [rax+rax+00h]
0x1801e0660  mov     dword ptr [rsi+1Ch], 0
0x1801e0667  inc     rbx
0x1801e066a  cmp     rbx, 14h
0x1801e066e  jnz     loc_1801E0536
0x1801e0674  jmp     short loc_1801E06EF
0x1801e0676  mov     rax, [rdi+48h]
0x1801e067a  test    rax, rax
0x1801e067d  jz      short loc_1801E0683
0x1801e067f  mov     ebx, [rax]
0x1801e0681  jmp     short loc_1801E0685
0x1801e0683  xor     ebx, ebx
0x1801e0685  dec     ebx
0x1801e0687  test    ebx, ebx
0x1801e0689  js      short loc_1801E06EF
0x1801e068b  mov     rcx, [rdi+48h]; hdsa
0x1801e068f  mov     edx, ebx; i
0x1801e0691  call    cs:__imp_DSA_GetItemPtr
0x1801e0698  nop     dword ptr [rax+rax+00h]
0x1801e069d  lea     r8, [rsp+220h+var_1F0]; unsigned int *
0x1801e06a2  mov     [rsp+220h+var_1F0], 0
0x1801e06aa  mov     rcx, rdi; this
0x1801e06ad  mov     rsi, rax
0x1801e06b0  mov     edx, [rax+1Ch]; unsigned int
0x1801e06b3  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801e06b8  test    eax, eax
0x1801e06ba  js      short loc_1801E06C9
0x1801e06bc  cmp     r14d, [rsp+220h+var_1F0]
0x1801e06c1  jnz     short loc_1801E06C9
0x1801e06c3  test    byte ptr [rsi+18h], 2
0x1801e06c7  jnz     short loc_1801E06CD
0x1801e06c9  dec     ebx
0x1801e06cb  jmp     short loc_1801E0687
0x1801e06cd  mov     rcx, [rsi+10h]; hEvent
0x1801e06d1  call    cs:__imp_SetEvent
0x1801e06d8  nop     dword ptr [rax+rax+00h]
0x1801e06dd  mov     rcx, [rdi+48h]; hdsa
0x1801e06e1  mov     edx, ebx; i
0x1801e06e3  call    cs:__imp_DSA_DeleteItem
0x1801e06ea  nop     dword ptr [rax+rax+00h]
0x1801e06ef  lea     rcx, g_csDll; lpCriticalSection
0x1801e06f6  call    cs:__imp_LeaveCriticalSection
0x1801e06fd  nop     dword ptr [rax+rax+00h]
0x1801e0702  mov     rcx, [rbp+120h+var_40]
0x1801e0709  xor     rcx, rsp; StackCookie
0x1801e070c  call    __security_check_cookie
0x1801e0711  add     rsp, 1F8h
0x1801e0718  pop     r15
0x1801e071a  pop     r14
0x1801e071c  pop     rdi
0x1801e071d  pop     rsi
0x1801e071e  pop     rbx
0x1801e071f  pop     rbp
0x1801e0720  retn
```
