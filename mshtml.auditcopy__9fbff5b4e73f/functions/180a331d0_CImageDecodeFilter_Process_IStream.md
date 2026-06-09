# CImageDecodeFilter::Process(IStream *)

- ea: `0x180a331d0`
- end: `0x180a33533`
- name: `?Process@CImageDecodeFilter@@UEAAJPEAUIStream@@@Z`
- size: `867`
- prototype: `__int64 __fastcall(CImageDecodeFilter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18006b2e8`
- `0x1800c5000`
- `0x1800ea428`
- `0x180157d14`
- `0x180157d3c`
- `0x18015a504`
- `0x1803e4730`
- `0x18041e404`
- `0x18041e43c`
- `0x180a32ad4`
- `0x180a331d0`
- `0x1810f64f2`
- `0x1810f6516`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x180a334a9`
- `KERNEL32!GetExitCodeThread` at `0x180a334a9`
- `KERNEL32!CreateThread` at `0x180a33409`
- `KERNEL32!CreateThread` at `0x180a33409`
- `KERNEL32!CreateEventW` at `0x180a333a3`
- `KERNEL32!CreateEventW` at `0x180a333c9`
- `KERNEL32!CreateEventW` at `0x180a333a3`
- `KERNEL32!CreateEventW` at `0x180a333c9`
- `KERNEL32!CloseHandle` at `0x180a334b8`
- `KERNEL32!CloseHandle` at `0x180a334cb`
- `KERNEL32!CloseHandle` at `0x180a334de`
- `KERNEL32!CloseHandle` at `0x180a334b8`
- `KERNEL32!CloseHandle` at `0x180a334cb`
- `KERNEL32!CloseHandle` at `0x180a334de`
- `KERNEL32!WaitForSingleObject` at `0x180a33434`
- `KERNEL32!WaitForSingleObject` at `0x180a33496`
- `KERNEL32!WaitForSingleObject` at `0x180a33434`
- `KERNEL32!WaitForSingleObject` at `0x180a33496`
- `iertutil!CreateUri` at `0x180a3325e`
- `iertutil!CreateUri` at `0x180a3325e`

## pseudocode

```c
__int64 __fastcall CImageDecodeFilter::Process(CImageDecodeFilter *this, struct IStream *a2)
{
  MemoryProtection *v4; // rcx
  CDwnDoc *v5; // rax
  CDwnDoc *v6; // rax
  CBaseFT *v7; // rbx
  unsigned int v8; // esi
  unsigned int v9; // r15d
  const void *v10; // r14
  __int64 *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // ecx
  __int64 *v14; // rax
  CBaseFT *v15; // rsi
  CBaseFT *v16; // r14
  CBaseFT *v17; // rcx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rax
  HANDLE EventW; // rax
  HANDLE v21; // rax
  HANDLE v22; // rsi
  DWORD v23; // ebx
  int v24; // eax
  IUri *ppURI; // [rsp+30h] [rbp-18h] BYREF
  __int64 v27[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+48h] BYREF
  DWORD ThreadId; // [rsp+98h] [rbp+50h] BYREF
  unsigned __int64 v30; // [rsp+A0h] [rbp+58h]
  CBaseFT *v31; // [rsp+A8h] [rbp+60h] BYREF

  ExitCode = -2147467259;
  ThreadId = 0;
  v31 = 0;
  ppURI = 0;
  v27[0] = 0;
  memset_0((char *)this + 80, 0, 0xA8u);
  v4 = (MemoryProtection *)g_hProcessHeap;
  *((_QWORD *)this + 15) = a2;
  v5 = (CDwnDoc *)MemoryProtection::HeapAllocClear<1>(v4, 0x340u);
  if ( v5 && (v6 = CDwnDoc::CDwnDoc(v5), (v7 = v6) != 0) )
  {
    *((_QWORD *)this + 11) = v6;
    ExitCode = CreateUri(&Source, 0x3002B81u, 0, &ppURI);
    if ( !ExitCode )
    {
      *((_QWORD *)this + 14) = ppURI;
      if ( *((_DWORD *)this + 5) )
      {
        v8 = 0;
        while ( 2 )
        {
          v9 = 0;
          v10 = (const void *)(*((_QWORD *)this + 3) + 16LL * v8);
          while ( v9 < 7 )
          {
            if ( !memcmp_0((const void *)qword_1811D5CD0[2 * v9 + 1], v10, 0x10u) )
            {
              v11 = &qword_1811D5CD0[2 * v9];
              if ( v11 )
              {
                v12 = *((_QWORD *)v7 + 21);
                v13 = v12 & 0xFFFFFFC0 | *(_DWORD *)v11 & 0x3F;
                v30 = __PAIR64__(HIDWORD(v12), v13);
                BYTE3(v30) = HIBYTE(v13) | 8;
                BYTE1(v30) = BYTE1(v13) | 1;
                *((_QWORD *)v7 + 21) = v30;
                v14 = TSmartPointer<IDwnInfoManager>::operator&(v27);
                ExitCode = GetDwnInfoManager((struct IDwnInfoManager **)v14);
                if ( (ExitCode & 0x80000000) == 0 )
                {
                  ExitCode = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, char *, CBaseFT **))(*(_QWORD *)v27[0] + 24LL))(
                               v27[0],
                               1,
                               0,
                               (char *)this + 80,
                               &v31);
                  if ( (ExitCode & 0x80000000) == 0 )
                  {
                    v15 = v31;
                    v16 = 0;
                    v17 = v31;
                    *((_QWORD *)this + 6) = v31;
                    CBaseFT::EnterCriticalSection(v17);
                    v18 = *((_QWORD *)v15 + 12);
                    if ( v18 )
                    {
                      v19 = *(volatile signed __int32 **)(v18 + 280);
                      if ( v19 )
                      {
                        v16 = (CBaseFT *)v19;
                        _InterlockedAdd(v19 + 4, 1u);
                      }
                    }
                    CBaseFT::LeaveCriticalSection(v15);
                    EventW = CreateEventW(0, 0, 0, 0);
                    *((_QWORD *)this + 34) = EventW;
                    if ( EventW )
                    {
                      v21 = CreateEventW(0, 0, 0, 0);
                      *((_QWORD *)this + 35) = v21;
                      if ( v21 )
                      {
                        *((_DWORD *)this + 66) = 0;
                        v22 = CreateThread(0, 0, CImageDecodeFilter::ThreadProc, (char *)this - 24, 0, &ThreadId);
                        if ( v22 )
                        {
                          if ( *((_DWORD *)this + 66) != 2 )
                          {
                            do
                            {
                              WaitForSingleObject(*((HANDLE *)this + 34), 0xFFFFFFFF);
                              while ( 1 )
                              {
                                v24 = *((_DWORD *)this + 66);
                                if ( v24 != 1 )
                                  break;
                                *((_DWORD *)this + 66) = 0;
                                CImageDecodeFilter::ImageCallback((CImageDecodeFilter *)((char *)this - 24));
                              }
                            }
                            while ( v24 != 2 );
                          }
                          WaitForSingleObject(v22, 0xFFFFFFFF);
                          GetExitCodeThread(v22, &ExitCode);
                          CloseHandle(v22);
                        }
                        CloseHandle(*((HANDLE *)this + 35));
                      }
                      CloseHandle(*((HANDLE *)this + 34));
                    }
                    if ( v16 )
                      CBaseFT::Release(v16);
                    if ( v31 )
                      CBaseFT::Release(v31);
                  }
                }
                goto LABEL_23;
              }
              break;
            }
            ++v9;
          }
          if ( ++v8 < *((_DWORD *)this + 5) )
            continue;
          break;
        }
      }
      ExitCode = -2147467259;
    }
LABEL_23:
    CBaseFT::Release(v7);
    ReleaseInterface((struct IUnknown *)ppURI);
    v23 = ExitCode;
  }
  else
  {
    v23 = -2147024882;
    ExitCode = -2147024882;
  }
  TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(v27);
  return v23;
}

```

## disassembly

```asm
0x180a331d0  push    rbp
0x180a331d2  push    rbx
0x180a331d3  push    rsi
0x180a331d4  push    rdi
0x180a331d5  push    r12
0x180a331d7  push    r13
0x180a331d9  push    r14
0x180a331db  push    r15
0x180a331dd  mov     rbp, rsp
0x180a331e0  sub     rsp, 48h
0x180a331e4  xor     r12d, r12d
0x180a331e7  mov     [rbp+ExitCode], 80004005h
0x180a331ee  mov     rbx, rdx
0x180a331f1  mov     [rbp+ThreadId], r12d
0x180a331f5  mov     rdi, rcx
0x180a331f8  mov     [rbp+arg_18], r12
0x180a331fc  xor     edx, edx; Val
0x180a331fe  mov     [rbp+ppURI], r12
0x180a33202  add     rcx, 50h ; 'P'; void *
0x180a33206  mov     [rbp+var_10], r12
0x180a3320a  mov     r8d, 0A8h; Size
0x180a33210  call    memset_0
0x180a33215  mov     rcx, cs:g_hProcessHeap
0x180a3321c  mov     edx, 340h
0x180a33221  mov     [rdi+78h], rbx
0x180a33225  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x180a3322a  test    rax, rax
0x180a3322d  jz      loc_180A3350E
0x180a33233  mov     rcx, rax; this
0x180a33236  call    ??0CDwnDoc@@QEAA@XZ; CDwnDoc::CDwnDoc(void)
0x180a3323b  mov     rbx, rax
0x180a3323e  test    rax, rax
0x180a33241  jz      loc_180A3350E
0x180a33247  lea     r9, [rbp+ppURI]; ppURI
0x180a3324b  mov     [rdi+58h], rax
0x180a3324f  xor     r8d, r8d; dwReserved
0x180a33252  lea     rcx, Source; pwzURI
0x180a33259  mov     edx, 3002B81h; dwFlags
0x180a3325e  call    cs:__imp_CreateUri
0x180a33265  nop     dword ptr [rax+rax+00h]
0x180a3326a  mov     [rbp+ExitCode], eax
0x180a3326d  test    eax, eax
0x180a3326f  jnz     loc_180A33457
0x180a33275  mov     rax, [rbp+ppURI]
0x180a33279  mov     [rdi+70h], rax
0x180a3327d  cmp     [rdi+14h], r12d
0x180a33281  jbe     loc_180A33450
0x180a33287  mov     esi, r12d
0x180a3328a  lea     rax, qword_1811D5CD0
0x180a33291  mov     r14d, esi
0x180a33294  mov     r15d, r12d
0x180a33297  shl     r14, 4
0x180a3329b  add     r14, [rdi+18h]
0x180a3329f  cmp     r15d, 7
0x180a332a3  jnb     loc_180A33442
0x180a332a9  mov     r12d, r15d
0x180a332ac  mov     r8d, 10h; Size
0x180a332b2  add     r12, r12
0x180a332b5  mov     rdx, r14; Buf2
0x180a332b8  mov     rcx, [rax+r12*8+8]; Buf1
0x180a332bd  call    memcmp_0
0x180a332c2  test    eax, eax
0x180a332c4  lea     rax, qword_1811D5CD0
0x180a332cb  jz      short loc_180A332D2
0x180a332cd  inc     r15d
0x180a332d0  jmp     short loc_180A3329F
0x180a332d2  lea     rcx, [rax+r12*8]
0x180a332d6  xor     r12d, r12d
0x180a332d9  test    rcx, rcx
0x180a332dc  jz      loc_180A33445
0x180a332e2  mov     ecx, [rcx]
0x180a332e4  mov     rax, [rbx+0A8h]
0x180a332eb  and     ecx, 3Fh
0x180a332ee  mov     [rbp+arg_10], rax
0x180a332f2  and     eax, 0FFFFFFC0h
0x180a332f5  or      ecx, eax
0x180a332f7  mov     dword ptr [rbp+arg_10], ecx
0x180a332fa  or      byte ptr [rbp+arg_10+3], 8
0x180a332fe  shr     ecx, 8
0x180a33301  or      cl, 1
0x180a33304  mov     byte ptr [rbp+arg_10+1], cl
0x180a33307  lea     rcx, [rbp+var_10]
0x180a3330b  mov     rax, [rbp+arg_10]
0x180a3330f  mov     [rbx+0A8h], rax
0x180a33316  call    ??I?$TSmartPointer@UIDwnInfoManager@@@@QEAAPEAPEAUIDwnInfoManager@@XZ; TSmartPointer<IDwnInfoManager>::operator&(void)
0x180a3331b  mov     rcx, rax; struct IDwnInfoManager **
0x180a3331e  call    ?GetDwnInfoManager@@YAJPEAPEAUIDwnInfoManager@@@Z; GetDwnInfoManager(IDwnInfoManager * *)
0x180a33323  mov     [rbp+ExitCode], eax
0x180a33326  test    eax, eax
0x180a33328  js      loc_180A33457
0x180a3332e  mov     rcx, [rbp+var_10]
0x180a33332  lea     rdx, [rbp+arg_18]
0x180a33336  mov     qword ptr [rsp+48h+dwCreationFlags], rdx
0x180a3333b  lea     r13d, [r12+1]
0x180a33340  lea     r9, [rdi+50h]
0x180a33344  xor     r8d, r8d
0x180a33347  mov     edx, r13d
0x180a3334a  mov     rax, [rcx]
0x180a3334d  mov     rax, [rax+18h]
0x180a33351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180a33356  mov     [rbp+ExitCode], eax
0x180a33359  test    eax, eax
0x180a3335b  js      loc_180A33457
0x180a33361  mov     rsi, [rbp+arg_18]
0x180a33365  mov     r14d, r12d
0x180a33368  mov     rcx, rsi; this
0x180a3336b  mov     [rdi+30h], rsi
0x180a3336f  call    ?EnterCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::EnterCriticalSection(void)
0x180a33374  mov     rax, [rsi+60h]
0x180a33378  test    rax, rax
0x180a3337b  jz      short loc_180A33391
0x180a3337d  mov     rax, [rax+118h]
0x180a33384  test    rax, rax
0x180a33387  jz      short loc_180A33391
0x180a33389  mov     r14, rax
0x180a3338c  lock add [rax+10h], r13d
0x180a33391  mov     rcx, rsi; this
0x180a33394  call    ?LeaveCriticalSection@CBaseFT@@QEAAXXZ; CBaseFT::LeaveCriticalSection(void)
0x180a33399  xor     r9d, r9d; lpName
0x180a3339c  xor     r8d, r8d; bInitialState
0x180a3339f  xor     edx, edx; bManualReset
0x180a333a1  xor     ecx, ecx; lpEventAttributes
0x180a333a3  call    cs:__imp_CreateEventW
0x180a333aa  nop     dword ptr [rax+rax+00h]
0x180a333af  mov     [rdi+110h], rax
0x180a333b6  test    rax, rax
0x180a333b9  jz      loc_180A334EA
0x180a333bf  xor     r9d, r9d; lpName
0x180a333c2  xor     r8d, r8d; bInitialState
0x180a333c5  xor     edx, edx; bManualReset
0x180a333c7  xor     ecx, ecx; lpEventAttributes
0x180a333c9  call    cs:__imp_CreateEventW
0x180a333d0  nop     dword ptr [rax+rax+00h]
0x180a333d5  mov     [rdi+118h], rax
0x180a333dc  test    rax, rax
0x180a333df  jz      loc_180A334D7
0x180a333e5  lea     rax, [rbp+ThreadId]
0x180a333e9  mov     [rdi+108h], r12d
0x180a333f0  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180a333f5  lea     r9, [rdi-18h]; lpParameter
0x180a333f9  lea     r8, ?ThreadProc@CImageDecodeFilter@@CAKPEAX@Z; lpStartAddress
0x180a33400  mov     [rsp+48h+dwCreationFlags], r12d; dwCreationFlags
0x180a33405  xor     edx, edx; dwStackSize
0x180a33407  xor     ecx, ecx; lpThreadAttributes
0x180a33409  call    cs:__imp_CreateThread
0x180a33410  nop     dword ptr [rax+rax+00h]
0x180a33415  mov     rsi, rax
0x180a33418  test    rax, rax
0x180a3341b  jz      loc_180A334C4
0x180a33421  cmp     dword ptr [rdi+108h], 2
0x180a33428  jz      short loc_180A33490
0x180a3342a  mov     rcx, [rdi+110h]; hHandle
0x180a33431  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180a33434  call    cs:__imp_WaitForSingleObject
0x180a3343b  nop     dword ptr [rax+rax+00h]
0x180a33440  jmp     short loc_180A33480
0x180a33442  xor     r12d, r12d
0x180a33445  inc     esi
0x180a33447  cmp     esi, [rdi+14h]
0x180a3344a  jb      loc_180A33291
0x180a33450  mov     [rbp+ExitCode], 80004005h
0x180a33457  mov     rcx, rbx; this
0x180a3345a  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180a3345f  mov     rcx, [rbp+ppURI]; struct IUnknown *
0x180a33463  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x180a33468  mov     ebx, [rbp+ExitCode]
0x180a3346b  jmp     loc_180A33516
0x180a33470  lea     rcx, [rdi-18h]; this
0x180a33474  mov     [rdi+108h], r12d
0x180a3347b  call    ?ImageCallback@CImageDecodeFilter@@AEAAXXZ; CImageDecodeFilter::ImageCallback(void)
0x180a33480  mov     eax, [rdi+108h]
0x180a33486  cmp     eax, r13d
0x180a33489  jz      short loc_180A33470
0x180a3348b  cmp     eax, 2
0x180a3348e  jnz     short loc_180A3342A
0x180a33490  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180a33493  mov     rcx, rsi; hHandle
0x180a33496  call    cs:__imp_WaitForSingleObject
0x180a3349d  nop     dword ptr [rax+rax+00h]
0x180a334a2  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180a334a6  mov     rcx, rsi; hThread
0x180a334a9  call    cs:__imp_GetExitCodeThread
0x180a334b0  nop     dword ptr [rax+rax+00h]
0x180a334b5  mov     rcx, rsi; hObject
0x180a334b8  call    cs:__imp_CloseHandle
0x180a334bf  nop     dword ptr [rax+rax+00h]
0x180a334c4  mov     rcx, [rdi+118h]; hObject
0x180a334cb  call    cs:__imp_CloseHandle
0x180a334d2  nop     dword ptr [rax+rax+00h]
0x180a334d7  mov     rcx, [rdi+110h]; hObject
0x180a334de  call    cs:__imp_CloseHandle
0x180a334e5  nop     dword ptr [rax+rax+00h]
0x180a334ea  test    r14, r14
0x180a334ed  jz      short loc_180A334F7
0x180a334ef  mov     rcx, r14; this
0x180a334f2  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180a334f7  mov     rcx, [rbp+arg_18]; this
0x180a334fb  test    rcx, rcx
0x180a334fe  jz      loc_180A33457
0x180a33504  call    ?Release@CBaseFT@@QEAAKXZ; CBaseFT::Release(void)
0x180a33509  jmp     loc_180A33457
0x180a3350e  mov     ebx, 8007000Eh
0x180a33513  mov     [rbp+ExitCode], ebx
0x180a33516  lea     rcx, [rbp+var_10]; void *
0x180a3351a  call    ??1?$TSmartPointer@UIWebPlatformPermanentSecurityManagerInternal@@@@QEAA@XZ; TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>::~TSmartPointer<IWebPlatformPermanentSecurityManagerInternal>(void)
0x180a3351f  mov     eax, ebx
0x180a33521  add     rsp, 48h
0x180a33525  pop     r15
0x180a33527  pop     r14
0x180a33529  pop     r13
0x180a3352b  pop     r12
0x180a3352d  pop     rdi
0x180a3352e  pop     rsi
0x180a3352f  pop     rbx
0x180a33530  pop     rbp
0x180a33531  retn
```
