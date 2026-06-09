# CBrowserFrameState::UnblockDialogsForTabThreadID(ulong)

- ea: `0x1801c8d50`
- end: `0x1801c901d`
- name: `?UnblockDialogsForTabThreadID@CBrowserFrameState@@QEAAXK@Z`
- size: `717`
- prototype: `void __fastcall(CBrowserFrameState *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180288ec8`

## callees

- `0x18000c530`
- `0x1801c6140`
- `0x1801c8d50`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801c8f5b`
- `KERNEL32!SetEvent` at `0x1801c8fdf`
- `KERNEL32!SetEvent` at `0x1801c8f5b`
- `KERNEL32!SetEvent` at `0x1801c8fdf`
- `KERNEL32!CreateEventW` at `0x1801c8f4a`
- `KERNEL32!CreateEventW` at `0x1801c8f4a`
- `KERNEL32!CloseHandle` at `0x1801c8f6e`
- `KERNEL32!CloseHandle` at `0x1801c8f6e`
- `KERNEL32!GetLastError` at `0x1801c8f65`
- `KERNEL32!GetLastError` at `0x1801c8f65`
- `KERNEL32!GetCurrentThreadId` at `0x1801c8d99`
- `KERNEL32!GetCurrentThreadId` at `0x1801c8df2`
- `KERNEL32!GetCurrentThreadId` at `0x1801c8d99`
- `KERNEL32!GetCurrentThreadId` at `0x1801c8df2`
- `KERNEL32!LeaveCriticalSection` at `0x1801c8ff8`
- `KERNEL32!LeaveCriticalSection` at `0x1801c8ff8`
- `KERNEL32!EnterCriticalSection` at `0x1801c8e0d`
- `KERNEL32!EnterCriticalSection` at `0x1801c8e0d`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c8feb`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c8feb`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8fa5`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8fa5`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801c8f37`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801c8f37`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c8e00`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c8e00`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c8e50`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c8e50`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801c8dc4`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801c8dc4`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801c8f0a`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801c8f0a`

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
    if ( dword_180663314 && !*((_DWORD *)this + 6) && *((_DWORD *)v23 + 25) )
      *((_DWORD *)this + 6) = *((_DWORD *)v23 + 25);
    v5 = *((_DWORD *)this + 10);
    if ( v5 != GetCurrentThreadId() )
      IsoUnlockArtifact(v21);
  }
  EnterCriticalSection(&g_csDll);
  if ( dword_180663314 )
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
0x1801c8d50  push    rbp
0x1801c8d52  push    rbx
0x1801c8d53  push    rsi
0x1801c8d54  push    rdi
0x1801c8d55  push    r14
0x1801c8d57  push    r15
0x1801c8d59  lea     rbp, [rsp-0F8h]
0x1801c8d61  sub     rsp, 1F8h
0x1801c8d68  mov     rax, cs:__security_cookie
0x1801c8d6f  xor     rax, rsp
0x1801c8d72  mov     [rbp+120h+var_40], rax
0x1801c8d79  mov     r14d, edx
0x1801c8d7c  mov     [rsp+220h+var_1D8], 0
0x1801c8d85  mov     rdi, rcx
0x1801c8d88  mov     [rsp+220h+var_1E0], 0
0x1801c8d91  mov     [rsp+220h+var_1EC], 0
0x1801c8d99  call    cs:__imp_GetCurrentThreadId
0x1801c8d9f  mov     ecx, [rdi+14h]
0x1801c8da2  lea     r9, [rsp+220h+var_1EC]
0x1801c8da7  cmp     [rdi+28h], eax
0x1801c8daa  lea     r8, [rsp+220h+var_1D8]
0x1801c8daf  lea     rax, [rsp+220h+var_1E0]
0x1801c8db4  mov     [rsp+220h+var_200], rax
0x1801c8db9  jz      short loc_1801C8DC2
0x1801c8dbb  mov     edx, 2
0x1801c8dc0  jmp     short loc_1801C8DC4
0x1801c8dc2  xor     edx, edx
0x1801c8dc4  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801c8dca  test    eax, eax
0x1801c8dcc  js      short loc_1801C8E06
0x1801c8dce  cmp     cs:dword_180663314, 0
0x1801c8dd5  jz      short loc_1801C8DEF
0x1801c8dd7  cmp     dword ptr [rdi+18h], 0
0x1801c8ddb  jnz     short loc_1801C8DEF
0x1801c8ddd  mov     rcx, [rsp+220h+var_1E0]
0x1801c8de2  mov     eax, [rcx+64h]
0x1801c8de5  test    eax, eax
0x1801c8de7  jz      short loc_1801C8DEF
0x1801c8de9  mov     eax, [rcx+64h]
0x1801c8dec  mov     [rdi+18h], eax
0x1801c8def  mov     ebx, [rdi+28h]
0x1801c8df2  call    cs:__imp_GetCurrentThreadId
0x1801c8df8  cmp     ebx, eax
0x1801c8dfa  jz      short loc_1801C8E06
0x1801c8dfc  mov     ecx, [rsp+220h+var_1EC]
0x1801c8e00  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801c8e06  lea     rcx, g_csDll; lpCriticalSection
0x1801c8e0d  call    cs:__imp_EnterCriticalSection
0x1801c8e13  cmp     cs:dword_180663314, 0
0x1801c8e1a  jz      loc_1801C8F8A
0x1801c8e20  mov     ecx, [rdi+18h]
0x1801c8e23  test    ecx, ecx
0x1801c8e25  jz      loc_1801C8FF1
0x1801c8e2b  cmp     r14d, 0FFFFFFFFh
0x1801c8e2f  jz      loc_1801C8FF1
0x1801c8e35  lea     r8, [rsp+220h+var_1E8]
0x1801c8e3a  mov     [rsp+220h+var_1D0], 0
0x1801c8e43  lea     rdx, [rsp+220h+var_1D0]
0x1801c8e48  mov     [rsp+220h+var_1E8], 0
0x1801c8e50  call    cs:__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z; IsoLockSharedMemory(ulong,void * *,ulong *)
0x1801c8e56  test    eax, eax
0x1801c8e58  js      loc_1801C8FF1
0x1801c8e5e  cmp     [rsp+220h+var_1E8], 320h
0x1801c8e66  jb      loc_1801C8FF1
0x1801c8e6c  xor     ebx, ebx
0x1801c8e6e  mov     rax, [rsp+220h+var_1D0]
0x1801c8e73  lea     rcx, [rbx+rbx*4]
0x1801c8e77  lea     rsi, [rax+rcx*8]
0x1801c8e7b  test    rsi, rsi
0x1801c8e7e  jz      loc_1801C8F7B
0x1801c8e84  mov     edx, [rsi+1Ch]; unsigned int
0x1801c8e87  test    edx, edx
0x1801c8e89  jz      loc_1801C8F7B
0x1801c8e8f  lea     r8, [rsp+220h+var_1F0]; unsigned int *
0x1801c8e94  mov     [rsp+220h+var_1F0], 0
0x1801c8e9c  mov     rcx, rdi; this
0x1801c8e9f  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801c8ea4  test    eax, eax
0x1801c8ea6  js      loc_1801C8F7B
0x1801c8eac  cmp     r14d, [rsp+220h+var_1F0]
0x1801c8eb1  jnz     loc_1801C8F7B
0x1801c8eb7  test    byte ptr [rsi+18h], 2
0x1801c8ebb  jz      loc_1801C8F7B
0x1801c8ec1  movups  xmm0, xmmword ptr cs:aIetdXxxxxxxx; "IEtd_xxxxxxxx"
0x1801c8ec8  xor     edx, edx; Val
0x1801c8eca  lea     rcx, [rsp+220h+var_1A4]; void *
0x1801c8ecf  movups  xmm1, xmmword ptr cs:aIetdXxxxxxxx+0Ch; "xxxxxxx"
0x1801c8ed6  movaps  xmmword ptr [rsp+220h+var_1C0], xmm0
0x1801c8edb  lea     r8d, [rdx+64h]; Size
0x1801c8edf  movups  xmmword ptr [rsp+220h+var_1C0+0Ch], xmm1
0x1801c8ee4  call    memset_0
0x1801c8ee9  mov     eax, [rsi+24h]
0x1801c8eec  lea     r8, aIeTabDialog08x; "IE_tab_dialog_%08x_%08x"
0x1801c8ef3  mov     r9, [rsi+8]
0x1801c8ef7  lea     rcx, [rsp+220h+var_1C0]; unsigned __int16 *
0x1801c8efc  mov     edx, 40h ; '@'; unsigned __int64
0x1801c8f01  mov     dword ptr [rsp+220h+var_200], eax
0x1801c8f05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801c8f0a  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801c8f10  mov     rdx, rax
0x1801c8f13  mov     rcx, [rax]
0x1801c8f16  mov     rax, [rcx+100h]
0x1801c8f1d  mov     rcx, rdx
0x1801c8f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c8f25  mov     rcx, rax
0x1801c8f28  lea     r9, [rsp+220h+var_1C0]
0x1801c8f2d  mov     r8d, 80h
0x1801c8f33  lea     rdx, [rbp+120h+Name]
0x1801c8f37  call    cs:__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z; IsoPrefixScopeQualifierToName(ulong *,ushort *,ulong,ushort const *)
0x1801c8f3d  xor     r8d, r8d; bInitialState
0x1801c8f40  lea     r9, [rbp+120h+Name]; lpName
0x1801c8f44  xor     ecx, ecx; lpEventAttributes
0x1801c8f46  lea     edx, [r8+1]; bManualReset
0x1801c8f4a  call    cs:__imp_CreateEventW
0x1801c8f50  mov     r15, rax
0x1801c8f53  test    rax, rax
0x1801c8f56  jz      short loc_1801C8F74
0x1801c8f58  mov     rcx, rax; hEvent
0x1801c8f5b  call    cs:__imp_SetEvent
0x1801c8f61  test    eax, eax
0x1801c8f63  jnz     short loc_1801C8F6B
0x1801c8f65  call    cs:__imp_GetLastError
0x1801c8f6b  mov     rcx, r15; hObject
0x1801c8f6e  call    cs:__imp_CloseHandle
0x1801c8f74  mov     dword ptr [rsi+1Ch], 0
0x1801c8f7b  inc     rbx
0x1801c8f7e  cmp     rbx, 14h
0x1801c8f82  jnz     loc_1801C8E6E
0x1801c8f88  jmp     short loc_1801C8FF1
0x1801c8f8a  mov     rax, [rdi+48h]
0x1801c8f8e  test    rax, rax
0x1801c8f91  jz      short loc_1801C8F97
0x1801c8f93  mov     ebx, [rax]
0x1801c8f95  jmp     short loc_1801C8F99
0x1801c8f97  xor     ebx, ebx
0x1801c8f99  dec     ebx
0x1801c8f9b  test    ebx, ebx
0x1801c8f9d  js      short loc_1801C8FF1
0x1801c8f9f  mov     rcx, [rdi+48h]; hdsa
0x1801c8fa3  mov     edx, ebx; i
0x1801c8fa5  call    cs:__imp_DSA_GetItemPtr
0x1801c8fab  lea     r8, [rsp+220h+var_1F0]; unsigned int *
0x1801c8fb0  mov     [rsp+220h+var_1F0], 0
0x1801c8fb8  mov     rcx, rdi; this
0x1801c8fbb  mov     rsi, rax
0x1801c8fbe  mov     edx, [rax+1Ch]; unsigned int
0x1801c8fc1  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801c8fc6  test    eax, eax
0x1801c8fc8  js      short loc_1801C8FD7
0x1801c8fca  cmp     r14d, [rsp+220h+var_1F0]
0x1801c8fcf  jnz     short loc_1801C8FD7
0x1801c8fd1  test    byte ptr [rsi+18h], 2
0x1801c8fd5  jnz     short loc_1801C8FDB
0x1801c8fd7  dec     ebx
0x1801c8fd9  jmp     short loc_1801C8F9B
0x1801c8fdb  mov     rcx, [rsi+10h]; hEvent
0x1801c8fdf  call    cs:__imp_SetEvent
0x1801c8fe5  mov     rcx, [rdi+48h]; hdsa
0x1801c8fe9  mov     edx, ebx; i
0x1801c8feb  call    cs:__imp_DSA_DeleteItem
0x1801c8ff1  lea     rcx, g_csDll; lpCriticalSection
0x1801c8ff8  call    cs:__imp_LeaveCriticalSection
0x1801c8ffe  mov     rcx, [rbp+120h+var_40]
0x1801c9005  xor     rcx, rsp; StackCookie
0x1801c9008  call    __security_check_cookie
0x1801c900d  add     rsp, 1F8h
0x1801c9014  pop     r15
0x1801c9016  pop     r14
0x1801c9018  pop     rdi
0x1801c9019  pop     rsi
0x1801c901a  pop     rbx
0x1801c901b  pop     rbp
0x1801c901c  retn
```
