# CCrashDetector::HrInit(void)

- ea: `0x1801123f0`
- end: `0x180112708`
- name: `?HrInit@CCrashDetector@@QEAAJXZ`
- size: `792`
- prototype: `__int64 __fastcall(CCrashDetector *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180112960`

## callees

- `0x1800264b4`
- `0x180026664`
- `0x180030a94`
- `0x180037cf4`
- `0x18003e690`
- `0x180111638`
- `0x1801116c0`
- `0x180111a34`
- `0x1801123f0`
- `0x180112708`
- `0x180112914`
- `0x1801223c0`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1801125c2`
- `KERNEL32!GetCurrentProcessId` at `0x1801125c2`
- `KERNEL32!CloseHandle` at `0x1801126be`
- `KERNEL32!CloseHandle` at `0x1801126cf`
- `KERNEL32!CloseHandle` at `0x1801126be`
- `KERNEL32!CloseHandle` at `0x1801126cf`
- `KERNEL32!CreateEventW` at `0x18011254f`
- `KERNEL32!CreateEventW` at `0x18011254f`
- `KERNEL32!ReleaseMutex` at `0x180112682`
- `KERNEL32!ReleaseMutex` at `0x1801126b0`
- `KERNEL32!ReleaseMutex` at `0x180112682`
- `KERNEL32!ReleaseMutex` at `0x1801126b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CCrashDetector::HrInit(CCrashDetector *this, unsigned int *a2)
{
  char v3; // r13
  void *v4; // r14
  int Instance; // edi
  void *v7; // rcx
  __int64 v8; // rdx
  HANDLE EventW; // rdi
  __int64 v10; // r12
  __int64 i; // rbx
  __int64 v12; // rdx
  DWORD CurrentProcessId; // edi
  BOOL v14; // eax
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+30h] [rbp-D8h]
  void *v16; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE hMutex; // [rsp+50h] [rbp-B8h] BYREF
  void *v18; // [rsp+58h] [rbp-B0h] BYREF
  char v19[1024]; // [rsp+68h] [rbp-A0h] BYREF

  v3 = 0;
  hMutex = 0;
  v4 = 0;
  v18 = 0;
  LODWORD(v16) = 0x2000;
  Mso::Security::HrGetEffectiveIL((Mso::Security *)&v16, a2);
  if ( (unsigned int)v16 < 0x2000 )
  {
    MsoShipAssertTagProc(507556290);
    return 2147500037LL;
  }
  if ( *((_QWORD *)this + 10) )
  {
LABEL_25:
    Instance = -2147467259;
    goto LABEL_26;
  }
  v16 = 0;
  Instance = CSingletonBase::HrGetInstance((CSingletonBase *)&CSingleton<CThreadManager>::m_gSingleton, &v16, 1);
  v7 = v16;
  *((_QWORD *)this + 10) = v16;
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(void *, __int64, unsigned __int64, char *))(*(_QWORD *)v7 + 48LL))(
                 v7,
                 536903940,
                 ((unsigned __int64)this + 16) & -(__int64)(this != 0),
                 (char *)this + 64);
    if ( Instance >= 0 )
    {
      _mm_lfence();
      Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, char *))(**((_QWORD **)this + 10) + 48LL))(
                   *((_QWORD *)this + 10),
                   536903940,
                   (char *)this + 16,
                   (char *)this + 72);
      if ( Instance >= 0 )
      {
        _mm_lfence();
        BuildSharedNameSec(v19, v8, *(_QWORD *)(*((_QWORD *)this + 6) + 1080LL), "_BootMutex", *((_DWORD *)this + 15));
        Instance = CRootMutexWrapper::HrInit(&hMutex, v19, *((unsigned int *)this + 15));
        if ( Instance >= 0 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)this + 88);
          *((_QWORD *)this + 11) = EventW;
          if ( EventW && CRootMutexWrapper::FEnter((CRootMutexWrapper *)&hMutex) )
          {
            _mm_lfence();
            v3 = 1;
            Instance = CGlobalSharedData::HrInit(
                         (char *)this + 24,
                         *(_QWORD *)(*((_QWORD *)this + 6) + 1080LL),
                         *((unsigned int *)this + 15));
            if ( Instance < 0 )
              goto LABEL_26;
            _mm_lfence();
            v10 = *((_QWORD *)this + 3);
            for ( i = 0; (unsigned int)i < 0x7F6; i = (unsigned int)(i + 1) )
            {
              LODWORD(v16) = 0;
              CurrentProcessId = GetCurrentProcessId();
              if ( !CurrentProcessId )
                goto LABEL_25;
              if ( !*(_DWORD *)(v10 + 4 * i + 28) && (_DWORD)i )
              {
                LODWORD(v15) = *((_DWORD *)this + 15);
                sub_180111638(v19, v12, *(_QWORD *)(*((_QWORD *)this + 6) + 1080LL), (unsigned int)i, CurrentProcessId);
                v14 = MsoFOpenCreateEvent(
                        &v18,
                        v19,
                        1,
                        1,
                        (int *)&v16,
                        v15,
                        *((_DWORD *)&vdwSecurityModes + *((int *)this + 15)));
                v4 = v18;
                if ( !v14 || !v18 || !(_DWORD)v16 )
                  goto LABEL_25;
                *(_DWORD *)(v10 + 4 * i + 28) = CurrentProcessId;
                *((_DWORD *)this + 14) = i;
                break;
              }
            }
            if ( *((_DWORD *)this + 14) >= 0x1FDu )
              MsoShipAssertTagProc(507556258);
            if ( (unsigned int)(*((_DWORD *)this + 14) - 1) <= 0x7F4 )
            {
              _mm_lfence();
              Instance = 0;
              ReleaseMutex(hMutex);
              Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear((char *)this + 96);
              *((_QWORD *)this + 12) = v4;
              goto LABEL_30;
            }
          }
          goto LABEL_25;
        }
      }
    }
  }
LABEL_26:
  MsoShipAssertTagProc(507556256);
  if ( v3 )
    ReleaseMutex(hMutex);
  if ( v4 )
    CloseHandle(v4);
LABEL_30:
  if ( hMutex )
    CloseHandle(hMutex);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801123f0  mov     rax, rsp
0x1801123f3  mov     [rax+10h], rbx
0x1801123f7  mov     [rax+18h], rsi
0x1801123fb  mov     [rax+20h], rdi
0x1801123ff  push    rbp
0x180112400  push    r12
0x180112402  push    r13
0x180112404  push    r14
0x180112406  push    r15
0x180112408  lea     rbp, [rax-398h]
0x18011240f  sub     rsp, 470h
0x180112416  mov     rax, cs:__security_cookie
0x18011241d  xor     rax, rsp
0x180112420  mov     [rbp+390h+var_30], rax
0x180112427  mov     rsi, rcx
0x18011242a  xor     r13b, r13b
0x18011242d  mov     [rsp+490h+hMutex], 0
0x180112436  xor     r14d, r14d
0x180112439  mov     [rsp+490h+var_440], r14
0x18011243e  mov     ebx, 2000h
0x180112443  mov     dword ptr [rsp+490h+var_450], ebx
0x180112447  lea     rcx, [rsp+490h+var_450]; this
0x18011244c  call    ?HrGetEffectiveIL@Security@Mso@@YAJPEAK@Z; Mso::Security::HrGetEffectiveIL(ulong *)
0x180112451  cmp     dword ptr [rsp+490h+var_450], ebx
0x180112455  jnb     short loc_18011246B
0x180112457  mov     ecx, 1E40B1C2h
0x18011245c  call    MsoShipAssertTagProc
0x180112461  mov     eax, 80004005h
0x180112466  jmp     loc_1801126D8
0x18011246b  cmp     [rsi+50h], r14
0x18011246f  jnz     loc_180112697
0x180112475  mov     [rsp+490h+var_450], r14
0x18011247a  mov     r8b, 1; bool
0x18011247d  lea     rdx, [rsp+490h+var_450]; void **
0x180112482  lea     rcx, ?m_gSingleton@?$CSingleton@VCThreadManager@@@@2V1@A; this
0x180112489  call    ?HrGetInstance@CSingletonBase@@IEAAJPEAPEAX_N@Z; CSingletonBase::HrGetInstance(void * *,bool)
0x18011248e  mov     edi, eax
0x180112490  mov     rcx, [rsp+490h+var_450]
0x180112495  mov     [rsi+50h], rcx
0x180112499  test    eax, eax
0x18011249b  js      loc_18011269C
0x1801124a1  mov     rax, [rcx]
0x1801124a4  mov     r10, [rax+30h]
0x1801124a8  lea     rbx, [rsi+10h]
0x1801124ac  lea     r9, [rsi+40h]
0x1801124b0  mov     rax, rsi
0x1801124b3  neg     rax
0x1801124b6  sbb     r8, r8
0x1801124b9  and     r8, rbx
0x1801124bc  mov     r15d, 20008104h
0x1801124c2  mov     edx, r15d
0x1801124c5  mov     rax, r10
0x1801124c8  call    cs:__guard_dispatch_icall_fptr
0x1801124ce  mov     edi, eax
0x1801124d0  test    eax, eax
0x1801124d2  js      loc_18011269C
0x1801124d8  lfence
0x1801124db  mov     rcx, [rsi+50h]
0x1801124df  mov     rax, [rcx]
0x1801124e2  lea     r9, [rsi+48h]
0x1801124e6  mov     r8, rbx
0x1801124e9  mov     edx, r15d
0x1801124ec  mov     rax, [rax+30h]
0x1801124f0  call    cs:__guard_dispatch_icall_fptr
0x1801124f6  mov     edi, eax
0x1801124f8  test    eax, eax
0x1801124fa  js      loc_18011269C
0x180112500  lfence
0x180112503  mov     ecx, [rsi+3Ch]
0x180112506  mov     rax, [rsi+30h]
0x18011250a  mov     dword ptr [rsp+490h+var_470], ecx
0x18011250e  lea     r9, aBootmutex; "_BootMutex"
0x180112515  mov     r8, [rax+438h]
0x18011251c  lea     rcx, [rsp+490h+var_430]
0x180112521  call    ?BuildSharedNameSec@@YA_KPEAD_KPEBD2W4eSharedLockSecurity@@@Z; BuildSharedNameSec(char *,unsigned __int64,char const *,char const *,eSharedLockSecurity)
0x180112526  mov     r8d, [rsi+3Ch]
0x18011252a  lea     rdx, [rsp+490h+var_430]
0x18011252f  lea     rcx, [rsp+490h+hMutex]
0x180112534  call    ?HrInit@CRootMutexWrapper@@QEAAJPEBDW4eSharedLockSecurity@@@Z; CRootMutexWrapper::HrInit(char const *,eSharedLockSecurity)
0x180112539  mov     edi, eax
0x18011253b  test    eax, eax
0x18011253d  js      loc_18011269C
0x180112543  xor     r9d, r9d; lpName
0x180112546  xor     r8d, r8d; bInitialState
0x180112549  lea     edx, [r9+1]; bManualReset
0x18011254d  xor     ecx, ecx; lpEventAttributes
0x18011254f  call    cs:__imp_CreateEventW
0x180112555  mov     rdi, rax
0x180112558  lea     rcx, [rsi+58h]
0x18011255c  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x180112561  mov     [rsi+58h], rdi
0x180112565  test    rdi, rdi
0x180112568  jz      loc_180112697
0x18011256e  lea     rcx, [rsp+490h+hMutex]; this
0x180112573  call    ?FEnter@CRootMutexWrapper@@QEAA_NXZ; CRootMutexWrapper::FEnter(void)
0x180112578  test    al, al
0x18011257a  jz      loc_180112697
0x180112580  lfence
0x180112583  mov     r13b, 1
0x180112586  mov     rax, [rsi+30h]
0x18011258a  mov     r8d, [rsi+3Ch]
0x18011258e  mov     rdx, [rax+438h]
0x180112595  lea     rcx, [rsi+18h]
0x180112599  call    ?HrInit@CGlobalSharedData@@QEAAJPEBDW4eSharedLockSecurity@@@Z; CGlobalSharedData::HrInit(char const *,eSharedLockSecurity)
0x18011259e  mov     edi, eax
0x1801125a0  test    eax, eax
0x1801125a2  js      loc_18011269C
0x1801125a8  lfence
0x1801125ab  mov     r12, [rsi+18h]
0x1801125af  xor     ebx, ebx
0x1801125b1  cmp     ebx, 7F6h
0x1801125b7  jnb     loc_180112659
0x1801125bd  mov     dword ptr [rsp+490h+var_450], r14d
0x1801125c2  call    cs:__imp_GetCurrentProcessId
0x1801125c8  mov     edi, eax
0x1801125ca  test    eax, eax
0x1801125cc  jz      loc_180112697
0x1801125d2  mov     ecx, [r12+rbx*4+1Ch]
0x1801125d7  test    ecx, ecx
0x1801125d9  jnz     short loc_1801125DF
0x1801125db  test    ebx, ebx
0x1801125dd  jnz     short loc_1801125E3
0x1801125df  inc     ebx
0x1801125e1  jmp     short loc_1801125B1
0x1801125e3  mov     ecx, [rsi+3Ch]
0x1801125e6  mov     rax, [rsi+30h]
0x1801125ea  mov     dword ptr [rsp+490h+var_468], ecx; struct _SECURITY_ATTRIBUTES *
0x1801125ee  mov     dword ptr [rsp+490h+var_470], edi
0x1801125f2  mov     r9d, ebx
0x1801125f5  mov     r8, [rax+438h]
0x1801125fc  lea     rcx, [rsp+490h+var_430]
0x180112601  call    sub_180111638
0x180112606  movsxd  rax, dword ptr [rsi+3Ch]
0x18011260a  lea     rcx, ?vdwSecurityModes@@3QBKB; ulong const near * const vdwSecurityModes
0x180112611  mov     eax, [rcx+rax*4]
0x180112614  mov     [rsp+490h+var_460], eax; unsigned int
0x180112618  lea     rax, [rsp+490h+var_450]
0x18011261d  mov     [rsp+490h+var_470], rax; int *
0x180112622  mov     eax, 1
0x180112627  mov     r9d, eax; int
0x18011262a  mov     r8d, eax; int
0x18011262d  lea     rdx, [rsp+490h+var_430]; char *
0x180112632  lea     rcx, [rsp+490h+var_440]; void **
0x180112637  call    ?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z; MsoFOpenCreateEvent(void * *,char const *,int,int,int *,_SECURITY_ATTRIBUTES *,ulong)
0x18011263c  mov     r14, [rsp+490h+var_440]
0x180112641  test    eax, eax
0x180112643  jz      short loc_180112697
0x180112645  test    r14, r14
0x180112648  jz      short loc_180112697
0x18011264a  cmp     dword ptr [rsp+490h+var_450], 0
0x18011264f  jz      short loc_180112697
0x180112651  mov     [r12+rbx*4+1Ch], edi
0x180112656  mov     [rsi+38h], ebx
0x180112659  cmp     dword ptr [rsi+38h], 1FDh
0x180112660  jb      short loc_18011266C
0x180112662  mov     ecx, 1E40B1A2h
0x180112667  call    MsoShipAssertTagProc
0x18011266c  mov     eax, [rsi+38h]
0x18011266f  dec     eax
0x180112671  cmp     eax, 7F4h
0x180112676  ja      short loc_180112697
0x180112678  lfence
0x18011267b  xor     edi, edi
0x18011267d  mov     rcx, [rsp+490h+hMutex]; hMutex
0x180112682  call    cs:__imp_ReleaseMutex
0x180112688  lea     rcx, [rsi+60h]
0x18011268c  call    ?clear@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXXZ; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::clear(void)
0x180112691  mov     [rsi+60h], r14
0x180112695  jmp     short loc_1801126C5
0x180112697  mov     edi, 80004005h
0x18011269c  mov     ecx, 1E40B1A0h
0x1801126a1  call    MsoShipAssertTagProc
0x1801126a6  test    r13b, r13b
0x1801126a9  jz      short loc_1801126B6
0x1801126ab  mov     rcx, [rsp+490h+hMutex]; hMutex
0x1801126b0  call    cs:__imp_ReleaseMutex
0x1801126b6  test    r14, r14
0x1801126b9  jz      short loc_1801126C5
0x1801126bb  mov     rcx, r14; hObject
0x1801126be  call    cs:__imp_CloseHandle
0x1801126c4  nop
0x1801126c5  mov     rcx, [rsp+490h+hMutex]; hObject
0x1801126ca  test    rcx, rcx
0x1801126cd  jz      short loc_1801126D6
0x1801126cf  call    cs:__imp_CloseHandle
0x1801126d5  nop
0x1801126d6  mov     eax, edi
0x1801126d8  mov     rcx, [rbp+390h+var_30]
0x1801126df  xor     rcx, rsp; StackCookie
0x1801126e2  call    __security_check_cookie
0x1801126e7  lea     r11, [rsp+490h+var_20]
0x1801126ef  mov     rbx, [r11+38h]
0x1801126f3  mov     rsi, [r11+40h]
0x1801126f7  mov     rdi, [r11+48h]
0x1801126fb  mov     rsp, r11
0x1801126fe  pop     r15
0x180112700  pop     r14
0x180112702  pop     r13
0x180112704  pop     r12
0x180112706  pop     rbp
0x180112707  retn
```
