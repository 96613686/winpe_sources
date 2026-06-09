# _AttemptEarlyStartTab

- ea: `0x1801f7fa4`
- end: `0x1801f82d9`
- name: `_AttemptEarlyStartTab`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f0498`

## callees

- `0x1801caff4`
- `0x1801ef0dc`
- `0x1801f7fa4`
- `0x1801fa590`
- `0x1801fa66c`
- `0x180204a50`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801f821d`
- `KERNEL32!CloseHandle` at `0x1801f823e`
- `KERNEL32!CloseHandle` at `0x1801f826a`
- `KERNEL32!CloseHandle` at `0x1801f821d`
- `KERNEL32!CloseHandle` at `0x1801f823e`
- `KERNEL32!CloseHandle` at `0x1801f826a`
- `KERNEL32!GetCurrentThreadId` at `0x1801f80a4`
- `KERNEL32!GetCurrentThreadId` at `0x1801f80a4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801f8033`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801f8033`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f8043`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f8043`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801f828d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801f828d`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1801f8058`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1801f8058`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x1801f808e`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x1801f808e`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801f822d`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801f8259`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801f827c`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801f822d`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801f8259`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801f827c`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1801f81b3`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1801f81b3`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801f82a2`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801f82a2`

## pseudocode

```c
__int64 __fastcall AttemptEarlyStartTab(_DWORD *a1, __int64 a2, _BYTE *a3, __int64 a4, struct CHomePageProtector *a5)
{
  HRESULT started; // ebx
  unsigned int v9; // esi
  DWORD CurrentThreadId; // eax
  int v11; // r14d
  unsigned int v12; // edx
  unsigned int v13; // ecx
  __int64 v14; // rcx
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  int v17; // eax
  HANDLE v18; // rax
  unsigned int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  DWORD *v24; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  PWSTR AppID; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v28; // [rsp+88h] [rbp-78h] BYREF
  __int128 v29; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  _BYTE v32[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v33; // [rsp+C2h] [rbp-3Eh]
  int v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+D0h] [rbp-30h]
  int v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+224h] [rbp+124h]
  int v38; // [rsp+228h] [rbp+128h]
  unsigned int v39; // [rsp+258h] [rbp+158h]
  int v40; // [rsp+25Ch] [rbp+15Ch]

  *a3 = 0;
  LODWORD(v22) = 0;
  v23 = 0;
  v21 = 0;
  v28 = 0;
  if ( (unsigned __int8)ShouldStartTabProcessEarly(
                          (_DWORD)a1,
                          (unsigned int)&v22,
                          (unsigned int)&v23,
                          (unsigned int)&v21,
                          (__int64)&v28,
                          a4,
                          a5) )
  {
    AppID = 0;
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435465) && !IsDualEngineProcess()
      || (started = GetCurrentProcessExplicitAppUserModelID(&AppID), started >= 0) )
    {
      v9 = (unsigned int)v22;
      v20 = 0;
      v24 = 0;
      started = IsoAllocSharedMemoryPerFlags((unsigned int)v22, &v20, 4u, (void **)&v24);
      if ( started >= 0 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v22 = 0;
        *v24 = CurrentThreadId;
        started = CreateEarlyStartEvent(v9, CurrentThreadId, &v22);
        if ( started < 0 )
        {
          IsoFreeSharedMemory(v20);
        }
        else
        {
          hObject = 0;
          started = CreateEarlyStartMutex(v9, *v24, &hObject);
          if ( started < 0 )
          {
            IsoFreeSharedMemory(v20);
            CloseHandle(v22);
          }
          else
          {
            memset_0(v32, 0, 0x278u);
            v11 = v21;
            v12 = a1[29];
            v13 = a1[28];
            v39 = v20;
            v36 = a1[80];
            v32[0] = 20;
            v33 = 632;
            v40 = 103;
            v38 = 104;
            v35 = 105;
            v34 = v21;
            v37 = 0;
            IESessionSetTabProcessCompCreDat(v13, v12, (struct _IsoCreationComponentData *)v32);
            v21 = 0;
            v14 = v9;
            LODWORD(v14) = v9 | 0x20000000;
            *(_QWORD *)&v29 = 0;
            v30 = 0u;
            BYTE8(v29) = 0;
            v31 = 0;
            v27 = 0;
            started = IsoCreateComponentByCreDat(v14, v32, AppID, &v21, 0, 0, &v29, &v27, 0);
            if ( started < 0 )
            {
              CloseHandle(hObject);
              IsoFreeSharedMemory(v20);
              CloseHandle(v22);
            }
            else
            {
              v15 = v29;
              v16 = v30;
              *(_DWORD *)(a2 + 4) = v23;
              *(_QWORD *)(a2 + 64) = v27;
              v17 = v21;
              *(_OWORD *)(a2 + 16) = v15;
              *(_DWORD *)(a2 + 56) = v17;
              *(_QWORD *)&v15 = v31;
              *(_QWORD *)(a2 + 72) = v22;
              v18 = hObject;
              *(_OWORD *)(a2 + 32) = v16;
              *(_QWORD *)(a2 + 80) = v18;
              *(_DWORD *)a2 = v9;
              *(_DWORD *)(a2 + 8) = v11;
              *(_QWORD *)(a2 + 48) = v15;
              *a3 = 1;
              BYTE8(v29) = 0;
            }
            _IsoWindowsContainer::~_IsoWindowsContainer((_IsoWindowsContainer *)&v29);
          }
        }
      }
    }
    CoTaskMemFree(AppID);
    if ( v28 )
      IsoRemoveDependency(v28);
  }
  else
  {
    return 0;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1801f7fa4  push    rbp
0x1801f7fa6  push    rbx
0x1801f7fa7  push    rsi
0x1801f7fa8  push    rdi
0x1801f7fa9  push    r12
0x1801f7fab  push    r13
0x1801f7fad  push    r14
0x1801f7faf  push    r15
0x1801f7fb1  lea     rbp, [rsp-258h]
0x1801f7fb9  sub     rsp, 358h
0x1801f7fc0  mov     rax, cs:__security_cookie
0x1801f7fc7  xor     rax, rsp
0x1801f7fca  mov     [rbp+290h+var_50], rax
0x1801f7fd1  mov     rax, [rbp+290h+arg_20]
0x1801f7fd8  xor     r13d, r13d
0x1801f7fdb  mov     [rsp+390h+var_360], rax
0x1801f7fe0  mov     r12, r8
0x1801f7fe3  mov     [rsp+390h+var_368], r9
0x1801f7fe8  lea     rax, [rbp+290h+var_308]
0x1801f7fec  mov     rdi, rdx
0x1801f7fef  mov     [r8], r13b
0x1801f7ff2  lea     r9, [rsp+390h+var_33C]
0x1801f7ff7  mov     [rsp+390h+var_370], rax
0x1801f7ffc  lea     r8, [rsp+390h+var_330]
0x1801f8001  mov     dword ptr [rsp+390h+var_338], r13d
0x1801f8006  lea     rdx, [rsp+390h+var_338]
0x1801f800b  mov     [rsp+390h+var_330], r13d
0x1801f8010  mov     r15, rcx
0x1801f8013  mov     [rsp+390h+var_33C], r13d
0x1801f8018  mov     [rbp+290h+var_308], r13
0x1801f801c  call    _ShouldStartTabProcessEarly
0x1801f8021  test    al, al
0x1801f8023  jz      loc_1801F82B0
0x1801f8029  mov     ecx, 10000009h
0x1801f802e  mov     [rsp+390h+AppID], r13
0x1801f8033  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801f803a  nop     dword ptr [rax+rax+00h]
0x1801f803f  test    al, al
0x1801f8041  jnz     short loc_1801F8053
0x1801f8043  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801f804a  nop     dword ptr [rax+rax+00h]
0x1801f804f  test    al, al
0x1801f8051  jz      short loc_1801F806E
0x1801f8053  lea     rcx, [rsp+390h+AppID]; AppID
0x1801f8058  call    cs:__imp_GetCurrentProcessExplicitAppUserModelID
0x1801f805f  nop     dword ptr [rax+rax+00h]
0x1801f8064  mov     ebx, eax
0x1801f8066  test    eax, eax
0x1801f8068  js      loc_1801F8288
0x1801f806e  mov     esi, dword ptr [rsp+390h+var_338]
0x1801f8072  lea     r9, [rsp+390h+var_328]
0x1801f8077  mov     ecx, esi
0x1801f8079  mov     [rsp+390h+var_340], r13d
0x1801f807e  mov     r8d, 4
0x1801f8084  mov     [rsp+390h+var_328], r13
0x1801f8089  lea     rdx, [rsp+390h+var_340]
0x1801f808e  call    cs:__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z; IsoAllocSharedMemoryPerFlags(ulong,ulong *,ulong,void * *)
0x1801f8095  nop     dword ptr [rax+rax+00h]
0x1801f809a  mov     ebx, eax
0x1801f809c  test    eax, eax
0x1801f809e  js      loc_1801F8288
0x1801f80a4  call    cs:__imp_GetCurrentThreadId
0x1801f80ab  nop     dword ptr [rax+rax+00h]
0x1801f80b0  mov     rcx, [rsp+390h+var_328]
0x1801f80b5  lea     r8, [rsp+390h+var_338]
0x1801f80ba  mov     edx, eax
0x1801f80bc  mov     [rsp+390h+var_338], r13
0x1801f80c1  mov     [rcx], eax
0x1801f80c3  mov     ecx, esi
0x1801f80c5  call    _CreateEarlyStartEvent
0x1801f80ca  mov     ebx, eax
0x1801f80cc  test    eax, eax
0x1801f80ce  js      loc_1801F8278
0x1801f80d4  mov     rdx, [rsp+390h+var_328]
0x1801f80d9  lea     r8, [rsp+390h+hObject]
0x1801f80de  mov     ecx, esi
0x1801f80e0  mov     [rsp+390h+hObject], r13
0x1801f80e5  mov     edx, [rdx]
0x1801f80e7  call    _CreateEarlyStartMutex
0x1801f80ec  mov     ebx, eax
0x1801f80ee  test    eax, eax
0x1801f80f0  js      loc_1801F8255
0x1801f80f6  mov     ebx, 278h
0x1801f80fb  lea     rcx, [rbp+290h+var_2D0]; void *
0x1801f80ff  mov     r8d, ebx; Size
0x1801f8102  xor     edx, edx; Val
0x1801f8104  call    memset_0
0x1801f8109  mov     eax, [rsp+390h+var_340]
0x1801f810d  lea     r8, [rbp+290h+var_2D0]; struct _IsoCreationComponentData *
0x1801f8111  mov     r14d, [rsp+390h+var_33C]
0x1801f8116  mov     edx, [r15+74h]; unsigned int
0x1801f811a  mov     ecx, [r15+70h]; unsigned int
0x1801f811e  mov     [rbp+290h+var_138], eax
0x1801f8124  mov     eax, [r15+140h]
0x1801f812b  mov     [rbp+290h+var_2B8], eax
0x1801f812e  mov     [rbp+290h+var_2D0], 14h
0x1801f8132  mov     [rbp+290h+var_2CE], bx
0x1801f8136  mov     [rbp+290h+var_134], 67h ; 'g'
0x1801f8140  mov     [rbp+290h+var_168], 68h ; 'h'
0x1801f814a  mov     [rbp+290h+var_2C0], 69h ; 'i'
0x1801f8151  mov     [rbp+290h+var_2C8], r14d
0x1801f8155  mov     [rbp+290h+var_16C], r13d
0x1801f815c  call    ?IESessionSetTabProcessCompCreDat@@YAXKKPEAU_IsoCreationComponentData@@@Z; IESessionSetTabProcessCompCreDat(ulong,ulong,_IsoCreationComponentData *)
0x1801f8161  mov     r8, [rsp+390h+AppID]
0x1801f8166  lea     rax, [rbp+290h+var_310]
0x1801f816a  mov     [rsp+390h+var_350], r13d
0x1801f816f  lea     r9, [rsp+390h+var_33C]
0x1801f8174  mov     [rsp+390h+var_358], rax
0x1801f8179  lea     rdx, [rbp+290h+var_2D0]
0x1801f817d  lea     rax, [rbp+290h+var_300]
0x1801f8181  mov     [rsp+390h+var_33C], r13d
0x1801f8186  mov     [rsp+390h+var_360], rax
0x1801f818b  mov     ecx, esi
0x1801f818d  mov     [rsp+390h+var_368], r13
0x1801f8192  bts     ecx, 1Dh
0x1801f8196  mov     [rsp+390h+var_370], r13
0x1801f819b  mov     qword ptr [rbp+290h+var_300], r13
0x1801f819f  mov     qword ptr [rbp+290h+var_2F0], r13
0x1801f81a3  mov     byte ptr [rbp+290h+var_300+8], r13b
0x1801f81a7  mov     qword ptr [rbp+290h+var_2F0+8], r13
0x1801f81ab  mov     [rbp+290h+var_2E0], r13
0x1801f81af  mov     [rbp+290h+var_310], r13
0x1801f81b3  call    cs:__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z; IsoCreateComponentByCreDat(ulong,_IsoCreationComponentData *,ushort const *,ulong *,ulong *,ulong *,_IsoWindowsContainer *,unsigned __int64 *,IsoCreationFailureTreatment)
0x1801f81ba  nop     dword ptr [rax+rax+00h]
0x1801f81bf  mov     ebx, eax
0x1801f81c1  test    eax, eax
0x1801f81c3  js      short loc_1801F8218
0x1801f81c5  movups  xmm0, [rbp+290h+var_300]
0x1801f81c9  mov     eax, [rsp+390h+var_330]
0x1801f81cd  movups  xmm1, [rbp+290h+var_2F0]
0x1801f81d1  mov     [rdi+4], eax
0x1801f81d4  mov     rax, [rbp+290h+var_310]
0x1801f81d8  mov     [rdi+40h], rax
0x1801f81dc  mov     eax, [rsp+390h+var_33C]
0x1801f81e0  movups  xmmword ptr [rdi+10h], xmm0
0x1801f81e4  mov     [rdi+38h], eax
0x1801f81e7  mov     rax, [rsp+390h+var_338]
0x1801f81ec  movsd   xmm0, [rbp+290h+var_2E0]
0x1801f81f1  mov     [rdi+48h], rax
0x1801f81f5  mov     rax, [rsp+390h+hObject]
0x1801f81fa  movups  xmmword ptr [rdi+20h], xmm1
0x1801f81fe  mov     [rdi+50h], rax
0x1801f8202  mov     [rdi], esi
0x1801f8204  mov     [rdi+8], r14d
0x1801f8208  movsd   qword ptr [rdi+30h], xmm0
0x1801f820d  mov     byte ptr [r12], 1
0x1801f8212  mov     byte ptr [rbp+290h+var_300+8], r13b
0x1801f8216  jmp     short loc_1801F824A
0x1801f8218  mov     rcx, [rsp+390h+hObject]; hObject
0x1801f821d  call    cs:__imp_CloseHandle
0x1801f8224  nop     dword ptr [rax+rax+00h]
0x1801f8229  mov     ecx, [rsp+390h+var_340]
0x1801f822d  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1801f8234  nop     dword ptr [rax+rax+00h]
0x1801f8239  mov     rcx, [rsp+390h+var_338]; hObject
0x1801f823e  call    cs:__imp_CloseHandle
0x1801f8245  nop     dword ptr [rax+rax+00h]
0x1801f824a  lea     rcx, [rbp+290h+var_300]; this
0x1801f824e  call    ??1_IsoWindowsContainer@@QEAA@XZ; _IsoWindowsContainer::~_IsoWindowsContainer(void)
0x1801f8253  jmp     short loc_1801F8288
0x1801f8255  mov     ecx, [rsp+390h+var_340]
0x1801f8259  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1801f8260  nop     dword ptr [rax+rax+00h]
0x1801f8265  mov     rcx, [rsp+390h+var_338]; hObject
0x1801f826a  call    cs:__imp_CloseHandle
0x1801f8271  nop     dword ptr [rax+rax+00h]
0x1801f8276  jmp     short loc_1801F8288
0x1801f8278  mov     ecx, [rsp+390h+var_340]
0x1801f827c  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1801f8283  nop     dword ptr [rax+rax+00h]
0x1801f8288  mov     rcx, [rsp+390h+AppID]; pv
0x1801f828d  call    cs:__imp_CoTaskMemFree
0x1801f8294  nop     dword ptr [rax+rax+00h]
0x1801f8299  mov     rcx, [rbp+290h+var_308]
0x1801f829d  test    rcx, rcx
0x1801f82a0  jz      short loc_1801F82B3
0x1801f82a2  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1801f82a9  nop     dword ptr [rax+rax+00h]
0x1801f82ae  jmp     short loc_1801F82B3
0x1801f82b0  mov     ebx, r13d
0x1801f82b3  mov     eax, ebx
0x1801f82b5  mov     rcx, [rbp+290h+var_50]
0x1801f82bc  xor     rcx, rsp; StackCookie
0x1801f82bf  call    __security_check_cookie
0x1801f82c4  add     rsp, 358h
0x1801f82cb  pop     r15
0x1801f82cd  pop     r14
0x1801f82cf  pop     r13
0x1801f82d1  pop     r12
0x1801f82d3  pop     rdi
0x1801f82d4  pop     rsi
0x1801f82d5  pop     rbx
0x1801f82d6  pop     rbp
0x1801f82d7  retn
```
