# _AttemptEarlyStartTab

- ea: `0x1801df0d8`
- end: `0x1801df3b8`
- name: `_AttemptEarlyStartTab`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801d7bbc`

## callees

- `0x1801b5614`
- `0x1801d68fc`
- `0x1801df0d8`
- `0x1801e145c`
- `0x1801e1524`
- `0x1801eb1fc`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801df32d`
- `KERNEL32!CloseHandle` at `0x1801df342`
- `KERNEL32!CloseHandle` at `0x1801df362`
- `KERNEL32!CloseHandle` at `0x1801df32d`
- `KERNEL32!CloseHandle` at `0x1801df342`
- `KERNEL32!CloseHandle` at `0x1801df362`
- `KERNEL32!GetCurrentThreadId` at `0x1801df1c0`
- `KERNEL32!GetCurrentThreadId` at `0x1801df1c0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801df167`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801df167`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801df171`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801df171`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801df379`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801df379`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1801df180`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x1801df180`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x1801df1b0`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x1801df1b0`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801df337`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801df357`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801df36e`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801df337`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801df357`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x1801df36e`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1801df2c9`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x1801df2c9`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801df388`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x1801df388`

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
0x1801df0d8  push    rbp
0x1801df0da  push    rbx
0x1801df0db  push    rsi
0x1801df0dc  push    rdi
0x1801df0dd  push    r12
0x1801df0df  push    r13
0x1801df0e1  push    r14
0x1801df0e3  push    r15
0x1801df0e5  lea     rbp, [rsp-258h]
0x1801df0ed  sub     rsp, 358h
0x1801df0f4  mov     rax, cs:__security_cookie
0x1801df0fb  xor     rax, rsp
0x1801df0fe  mov     [rbp+290h+var_50], rax
0x1801df105  mov     rax, [rbp+290h+arg_20]
0x1801df10c  xor     r13d, r13d
0x1801df10f  mov     [rsp+390h+var_360], rax
0x1801df114  mov     r12, r8
0x1801df117  mov     [rsp+390h+var_368], r9
0x1801df11c  lea     rax, [rbp+290h+var_308]
0x1801df120  mov     rdi, rdx
0x1801df123  mov     [r8], r13b
0x1801df126  lea     r9, [rsp+390h+var_33C]
0x1801df12b  mov     [rsp+390h+var_370], rax
0x1801df130  lea     r8, [rsp+390h+var_330]
0x1801df135  mov     dword ptr [rsp+390h+var_338], r13d
0x1801df13a  lea     rdx, [rsp+390h+var_338]
0x1801df13f  mov     [rsp+390h+var_330], r13d
0x1801df144  mov     r15, rcx
0x1801df147  mov     [rsp+390h+var_33C], r13d
0x1801df14c  mov     [rbp+290h+var_308], r13
0x1801df150  call    _ShouldStartTabProcessEarly
0x1801df155  test    al, al
0x1801df157  jz      loc_1801DF390
0x1801df15d  mov     ecx, 10000009h
0x1801df162  mov     [rsp+390h+AppID], r13
0x1801df167  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801df16d  test    al, al
0x1801df16f  jnz     short loc_1801DF17B
0x1801df171  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801df177  test    al, al
0x1801df179  jz      short loc_1801DF190
0x1801df17b  lea     rcx, [rsp+390h+AppID]; AppID
0x1801df180  call    cs:__imp_GetCurrentProcessExplicitAppUserModelID
0x1801df186  mov     ebx, eax
0x1801df188  test    eax, eax
0x1801df18a  js      loc_1801DF374
0x1801df190  mov     esi, dword ptr [rsp+390h+var_338]
0x1801df194  lea     r9, [rsp+390h+var_328]
0x1801df199  mov     ecx, esi
0x1801df19b  mov     [rsp+390h+var_340], r13d
0x1801df1a0  mov     r8d, 4
0x1801df1a6  mov     [rsp+390h+var_328], r13
0x1801df1ab  lea     rdx, [rsp+390h+var_340]
0x1801df1b0  call    cs:__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z; IsoAllocSharedMemoryPerFlags(ulong,ulong *,ulong,void * *)
0x1801df1b6  mov     ebx, eax
0x1801df1b8  test    eax, eax
0x1801df1ba  js      loc_1801DF374
0x1801df1c0  call    cs:__imp_GetCurrentThreadId
0x1801df1c6  mov     rcx, [rsp+390h+var_328]
0x1801df1cb  lea     r8, [rsp+390h+var_338]
0x1801df1d0  mov     edx, eax
0x1801df1d2  mov     [rsp+390h+var_338], r13
0x1801df1d7  mov     [rcx], eax
0x1801df1d9  mov     ecx, esi
0x1801df1db  call    _CreateEarlyStartEvent
0x1801df1e0  mov     ebx, eax
0x1801df1e2  test    eax, eax
0x1801df1e4  js      loc_1801DF36A
0x1801df1ea  mov     rdx, [rsp+390h+var_328]
0x1801df1ef  lea     r8, [rsp+390h+hObject]
0x1801df1f4  mov     ecx, esi
0x1801df1f6  mov     [rsp+390h+hObject], r13
0x1801df1fb  mov     edx, [rdx]
0x1801df1fd  call    _CreateEarlyStartMutex
0x1801df202  mov     ebx, eax
0x1801df204  test    eax, eax
0x1801df206  js      loc_1801DF353
0x1801df20c  mov     ebx, 278h
0x1801df211  lea     rcx, [rbp+290h+var_2D0]; void *
0x1801df215  mov     r8d, ebx; Size
0x1801df218  xor     edx, edx; Val
0x1801df21a  call    memset_0
0x1801df21f  mov     eax, [rsp+390h+var_340]
0x1801df223  lea     r8, [rbp+290h+var_2D0]; struct _IsoCreationComponentData *
0x1801df227  mov     r14d, [rsp+390h+var_33C]
0x1801df22c  mov     edx, [r15+74h]; unsigned int
0x1801df230  mov     ecx, [r15+70h]; unsigned int
0x1801df234  mov     [rbp+290h+var_138], eax
0x1801df23a  mov     eax, [r15+140h]
0x1801df241  mov     [rbp+290h+var_2B8], eax
0x1801df244  mov     [rbp+290h+var_2D0], 14h
0x1801df248  mov     [rbp+290h+var_2CE], bx
0x1801df24c  mov     [rbp+290h+var_134], 67h ; 'g'
0x1801df256  mov     [rbp+290h+var_168], 68h ; 'h'
0x1801df260  mov     [rbp+290h+var_2C0], 69h ; 'i'
0x1801df267  mov     [rbp+290h+var_2C8], r14d
0x1801df26b  mov     [rbp+290h+var_16C], r13d
0x1801df272  call    ?IESessionSetTabProcessCompCreDat@@YAXKKPEAU_IsoCreationComponentData@@@Z; IESessionSetTabProcessCompCreDat(ulong,ulong,_IsoCreationComponentData *)
0x1801df277  mov     r8, [rsp+390h+AppID]
0x1801df27c  lea     rax, [rbp+290h+var_310]
0x1801df280  mov     [rsp+390h+var_350], r13d
0x1801df285  lea     r9, [rsp+390h+var_33C]
0x1801df28a  mov     [rsp+390h+var_358], rax
0x1801df28f  lea     rdx, [rbp+290h+var_2D0]
0x1801df293  lea     rax, [rbp+290h+var_300]
0x1801df297  mov     [rsp+390h+var_33C], r13d
0x1801df29c  mov     [rsp+390h+var_360], rax
0x1801df2a1  mov     ecx, esi
0x1801df2a3  mov     [rsp+390h+var_368], r13
0x1801df2a8  bts     ecx, 1Dh
0x1801df2ac  mov     [rsp+390h+var_370], r13
0x1801df2b1  mov     qword ptr [rbp+290h+var_300], r13
0x1801df2b5  mov     qword ptr [rbp+290h+var_2F0], r13
0x1801df2b9  mov     byte ptr [rbp+290h+var_300+8], r13b
0x1801df2bd  mov     qword ptr [rbp+290h+var_2F0+8], r13
0x1801df2c1  mov     [rbp+290h+var_2E0], r13
0x1801df2c5  mov     [rbp+290h+var_310], r13
0x1801df2c9  call    cs:__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z; IsoCreateComponentByCreDat(ulong,_IsoCreationComponentData *,ushort const *,ulong *,ulong *,ulong *,_IsoWindowsContainer *,unsigned __int64 *,IsoCreationFailureTreatment)
0x1801df2cf  mov     ebx, eax
0x1801df2d1  test    eax, eax
0x1801df2d3  js      short loc_1801DF328
0x1801df2d5  movups  xmm0, [rbp+290h+var_300]
0x1801df2d9  mov     eax, [rsp+390h+var_330]
0x1801df2dd  movups  xmm1, [rbp+290h+var_2F0]
0x1801df2e1  mov     [rdi+4], eax
0x1801df2e4  mov     rax, [rbp+290h+var_310]
0x1801df2e8  mov     [rdi+40h], rax
0x1801df2ec  mov     eax, [rsp+390h+var_33C]
0x1801df2f0  movups  xmmword ptr [rdi+10h], xmm0
0x1801df2f4  mov     [rdi+38h], eax
0x1801df2f7  mov     rax, [rsp+390h+var_338]
0x1801df2fc  movsd   xmm0, [rbp+290h+var_2E0]
0x1801df301  mov     [rdi+48h], rax
0x1801df305  mov     rax, [rsp+390h+hObject]
0x1801df30a  movups  xmmword ptr [rdi+20h], xmm1
0x1801df30e  mov     [rdi+50h], rax
0x1801df312  mov     [rdi], esi
0x1801df314  mov     [rdi+8], r14d
0x1801df318  movsd   qword ptr [rdi+30h], xmm0
0x1801df31d  mov     byte ptr [r12], 1
0x1801df322  mov     byte ptr [rbp+290h+var_300+8], r13b
0x1801df326  jmp     short loc_1801DF348
0x1801df328  mov     rcx, [rsp+390h+hObject]; hObject
0x1801df32d  call    cs:__imp_CloseHandle
0x1801df333  mov     ecx, [rsp+390h+var_340]
0x1801df337  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1801df33d  mov     rcx, [rsp+390h+var_338]; hObject
0x1801df342  call    cs:__imp_CloseHandle
0x1801df348  lea     rcx, [rbp+290h+var_300]; this
0x1801df34c  call    ??1_IsoWindowsContainer@@QEAA@XZ; _IsoWindowsContainer::~_IsoWindowsContainer(void)
0x1801df351  jmp     short loc_1801DF374
0x1801df353  mov     ecx, [rsp+390h+var_340]
0x1801df357  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1801df35d  mov     rcx, [rsp+390h+var_338]; hObject
0x1801df362  call    cs:__imp_CloseHandle
0x1801df368  jmp     short loc_1801DF374
0x1801df36a  mov     ecx, [rsp+390h+var_340]
0x1801df36e  call    cs:__imp_?IsoFreeSharedMemory@@YAJK@Z; IsoFreeSharedMemory(ulong)
0x1801df374  mov     rcx, [rsp+390h+AppID]; pv
0x1801df379  call    cs:__imp_CoTaskMemFree
0x1801df37f  mov     rcx, [rbp+290h+var_308]
0x1801df383  test    rcx, rcx
0x1801df386  jz      short loc_1801DF393
0x1801df388  call    cs:__imp_?IsoRemoveDependency@@YAJ_K@Z; IsoRemoveDependency(unsigned __int64)
0x1801df38e  jmp     short loc_1801DF393
0x1801df390  mov     ebx, r13d
0x1801df393  mov     eax, ebx
0x1801df395  mov     rcx, [rbp+290h+var_50]
0x1801df39c  xor     rcx, rsp; StackCookie
0x1801df39f  call    __security_check_cookie
0x1801df3a4  add     rsp, 358h
0x1801df3ab  pop     r15
0x1801df3ad  pop     r14
0x1801df3af  pop     r13
0x1801df3b1  pop     r12
0x1801df3b3  pop     rdi
0x1801df3b4  pop     rsi
0x1801df3b5  pop     rbx
0x1801df3b6  pop     rbp
0x1801df3b7  retn
```
