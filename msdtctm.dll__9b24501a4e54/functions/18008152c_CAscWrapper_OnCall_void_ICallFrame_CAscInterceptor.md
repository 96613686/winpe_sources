# CAscWrapper::OnCall(void *,ICallFrame *,CAscInterceptor *)

- ea: `0x18008152c`
- end: `0x1800819b7`
- name: `?OnCall@CAscWrapper@@QEAAJPEAXPEAUICallFrame@@PEAVCAscInterceptor@@@Z`
- size: `1163`
- prototype: `__int64 __fastcall(CAscWrapper *__hidden this, void *, struct ICallFrame *, struct CAscInterceptor *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180081f50`

## callees

- `0x18001d1e4`
- `0x1800813c8`
- `0x180081490`
- `0x18008152c`
- `0x1800820a8`
- `0x180082170`
- `0x180082224`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800816ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180081923`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800816ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180081923`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800816a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800816a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008192d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008192d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081935`

## string_xrefs

- `0x18008158d`: `com\complus\dtc\dtc\asc\ascwrapper.cpp`
- `0x1800816cb`: `com\complus\dtc\dtc\asc\ascwrapper.cpp`
- `0x180081718`: `com\complus\dtc\dtc\asc\ascwrapper.cpp`
- `0x180081733`: `com\complus\dtc\dtc\asc\ascwrapper.cpp`
- `0x1800818bf`: `com\complus\dtc\dtc\asc\ascwrapper.cpp`
- `0x18008194c`: `com\complus\dtc\dtc\asc\ascwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAscWrapper::OnCall(CAscWrapper *this, void *a2, struct ICallFrame *a3, struct CAscInterceptor *a4)
{
  struct ICallFrame *v5; // rsi
  void *v6; // r12
  unsigned int v8; // eax
  __int64 v9; // r15
  CAscCall *Instance; // rsi
  int v11; // ebx
  char *v12; // rbx
  int v13; // eax
  char *v14; // rcx
  void (__fastcall **v15)(_QWORD); // rax
  struct CAscCall *v16; // r14
  DWORD LastError; // ebx
  DWORD v18; // eax
  DWORD v19; // ebx
  DWORD v20; // eax
  int v21; // eax
  int v22; // eax
  char *v23; // rsi
  char *v24; // rbx
  __int64 v25; // rcx
  _QWORD *v26; // r12
  void (__fastcall ***v27)(char *); // r14
  DWORD v28; // ebx
  DWORD v29; // eax
  __int64 v31; // [rsp+38h] [rbp-49h] BYREF
  LPVOID lpTlsValue; // [rsp+40h] [rbp-41h]
  _BYTE v33[56]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v34; // [rsp+80h] [rbp-1h]

  v5 = a3;
  v6 = a2;
  v31 = 0;
  CAscCall::CAscCall((CAscCall *)v33, a2, a3, a4);
  v8 = CAscCall::ChangeCallContext((CAscCall *)v33);
  v9 = v8;
  if ( !v8 )
  {
    if ( _InterlockedExchange((volatile __int32 *)this + 68, 1) == 1 )
    {
      Instance = CAscCall::CreateInstance(v6, v5, a4);
      DELLogCriticalErrorHelperWithHr(
        0,
        0xC0001089,
        Instance != 0,
        -2147024882,
        "com\\complus\\dtc\\dtc\\asc\\ascwrapper.cpp",
        518);
      v11 = CAscCall::MakeLocalCopyOfCallFrame(Instance);
      if ( v11 )
      {
        (*(void (__fastcall **)(CAscCall *))(*(_QWORD *)Instance + 16LL))(Instance);
        LODWORD(v9) = v11;
        goto LABEL_34;
      }
      v12 = (char *)this + 184;
      (**((void (__fastcall ***)(char *))this + 23))((char *)this + 184);
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 19) + 24LL))(
        (char *)this + 152,
        (__int64)Instance + 8);
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 23) + 8LL))((char *)this + 184);
      if ( _InterlockedExchange((volatile __int32 *)this + 68, 1) == 1 )
        goto LABEL_34;
      (**(void (__fastcall ***)(char *))v12)((char *)this + 184);
      v13 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 19) + 40LL))((char *)this + 152, &v31);
      v14 = (char *)this + 184;
      if ( !v13 )
      {
        v15 = *(void (__fastcall ***)(_QWORD))v12;
LABEL_33:
        *((_DWORD *)this + 68) = v9;
        ((void (__fastcall **)(char *))v15)[1](v14);
        goto LABEL_34;
      }
      v16 = *(struct CAscCall **)(v31 + 8);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v14);
      v5 = a3;
    }
    else
    {
      v16 = (struct CAscCall *)v33;
    }
    lpTlsValue = TlsGetValue(g_iTls);
    LastError = GetLastError();
    v18 = GetLastError();
    DELLogCriticalErrorHelperWithHr(
      0,
      0xC0001071,
      v18 == 0,
      LastError,
      "com\\complus\\dtc\\dtc\\asc\\ascwrapper.cpp",
      574);
    if ( !TlsSetValue(g_iTls, this) )
    {
      v19 = GetLastError();
      v20 = GetLastError();
      DELLogCriticalErrorHelperWithHr(0, 0xC0001071, v20 == 0, v19, "com\\complus\\dtc\\dtc\\asc\\ascwrapper.cpp", 578);
    }
    while ( 1 )
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v16 + 7) + 168LL))(
              *((_QWORD *)v16 + 7),
              *((_QWORD *)v16 + 8));
      DELLogCriticalErrorHelperWithHr(0, 0xC0001071, v21 == 0, v21, "com\\complus\\dtc\\dtc\\asc\\ascwrapper.cpp", 586);
      if ( (*((_BYTE *)this + 276) & 1) != 0 )
      {
        if ( v16 == (struct CAscCall *)v33 )
        {
          v16 = CAscCall::CreateInstance(v6, v5, a4);
          DELLogCriticalErrorHelperWithHr(
            0,
            0xC0001089,
            v16 != 0,
            -2147024882,
            "com\\complus\\dtc\\dtc\\asc\\ascwrapper.cpp",
            604);
          v22 = CAscCall::MakeLocalCopyOfCallFrame(v16);
          if ( v22 )
          {
            LODWORD(v9) = v22;
            goto LABEL_34;
          }
        }
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 30) + 24LL))((char *)this + 240, (__int64)v16 + 8);
        *((_DWORD *)this + 69) &= ~1u;
      }
      else if ( v16 != (struct CAscCall *)v33 )
      {
        (*(void (__fastcall **)(struct CAscCall *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v23 = (char *)this + 184;
      if ( (*((_BYTE *)this + 276) & 2) != 0 )
      {
        (**(void (__fastcall ***)(char *))v23)((char *)this + 184);
        v24 = (char *)this + 264;
        if ( *((_DWORD *)this + 62) <= (unsigned int)v9 )
        {
          v26 = (_QWORD *)((char *)this + 256);
          v27 = (void (__fastcall ***)(char *))((char *)this + 184);
        }
        else
        {
          *(_QWORD *)(*(_QWORD *)v24 + 16LL) = *((_QWORD *)this + 21);
          v25 = *(_QWORD *)v24;
          if ( *((_DWORD *)this + 40) == (_DWORD)v9 )
            *((_QWORD *)this + 22) = v25;
          else
            *(_QWORD *)(*((_QWORD *)this + 21) + 24LL) = v25;
          v26 = (_QWORD *)((char *)this + 256);
          *((_QWORD *)this + 21) = *((_QWORD *)this + 32);
          *((_DWORD *)this + 40) += *((_DWORD *)this + 62);
          v27 = (void (__fastcall ***)(char *))((char *)this + 184);
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))((char *)this + 184);
        *v26 = v9;
        *(_QWORD *)v24 = v9;
        *((_DWORD *)this + 62) = v9;
        *((_DWORD *)this + 69) &= ~2u;
        v6 = a2;
      }
      else
      {
        v27 = (void (__fastcall ***)(char *))((char *)this + 184);
      }
      (**v27)((char *)this + 184);
      if ( !(*(unsigned int (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 19) + 40LL))(
              (char *)this + 152,
              &v31) )
        break;
      v16 = *(struct CAscCall **)(v31 + 8);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))((char *)this + 184);
      v5 = a3;
    }
    if ( !TlsSetValue(g_iTls, lpTlsValue) )
    {
      v28 = GetLastError();
      v29 = GetLastError();
      DELLogCriticalErrorHelperWithHr(0, 0xC0001071, v29 == 0, v28, "com\\complus\\dtc\\dtc\\asc\\ascwrapper.cpp", 676);
    }
    v15 = *(void (__fastcall ***)(_QWORD))v23;
    v14 = (char *)this + 184;
    goto LABEL_33;
  }
LABEL_34:
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 64LL))(v34, (unsigned int)v9);
  CAscCall::~CAscCall((CAscCall *)v33);
  return 0;
}

```

## disassembly

```asm
0x18008152c  mov     rax, rsp
0x18008152f  mov     [rax+8], rbx
0x180081533  mov     [rax+18h], r8
0x180081537  mov     [rax+10h], rdx
0x18008153b  push    rbp
0x18008153c  push    rsi
0x18008153d  push    rdi
0x18008153e  push    r12
0x180081540  push    r13
0x180081542  push    r14
0x180081544  push    r15
0x180081546  lea     rbp, [rax-5Fh]
0x18008154a  sub     rsp, 0A0h
0x180081551  mov     r13, r9
0x180081554  mov     rsi, r8
0x180081557  mov     r12, rdx
0x18008155a  mov     rdi, rcx
0x18008155d  mov     [rbp+57h+var_A0], 0
0x180081565  lea     rcx, [rbp+57h+var_90]; this
0x180081569  call    ??0CAscCall@@QEAA@PEAXPEAUICallFrame@@PEAVCAscInterceptor@@@Z; CAscCall::CAscCall(void *,ICallFrame *,CAscInterceptor *)
0x18008156e  nop
0x18008156f  lea     rcx, [rbp+57h+var_90]; this
0x180081573  call    ?ChangeCallContext@CAscCall@@QEAAJXZ; CAscCall::ChangeCallContext(void)
0x180081578  mov     r15d, eax
0x18008157b  test    eax, eax
0x18008157d  jnz     loc_18008197D
0x180081583  lea     eax, [r15+1]
0x180081587  xchg    eax, [rdi+110h]
0x18008158d  lea     rbx, aComComplusDtcD_60; "com\\complus\\dtc\\dtc\\asc\\ascwrapper"...
0x180081594  cmp     eax, 1
0x180081597  jnz     loc_180081698
0x18008159d  mov     r8, r13; struct CAscInterceptor *
0x1800815a0  mov     rdx, rsi; struct ICallFrame *
0x1800815a3  mov     rcx, r12; void *
0x1800815a6  call    ?CreateInstance@CAscCall@@SAPEAV1@PEAXPEAUICallFrame@@PEAVCAscInterceptor@@@Z; CAscCall::CreateInstance(void *,ICallFrame *,CAscInterceptor *)
0x1800815ab  mov     rsi, rax
0x1800815ae  xor     r8d, r8d
0x1800815b1  test    rax, rax
0x1800815b4  setnz   r8b; int
0x1800815b8  mov     dword ptr [rsp+28h], 206h; int
0x1800815c0  mov     [rsp+0D0h+var_B0], rbx; char *
0x1800815c5  mov     edx, 0C0001089h; unsigned int
0x1800815ca  xor     ecx, ecx; struct ITmInstance *
0x1800815cc  mov     r9d, 8007000Eh; int
0x1800815d2  call    ?DELLogCriticalErrorHelperWithHr@@YAXPEAUITmInstance@@KHJPEADH@Z; DELLogCriticalErrorHelperWithHr(ITmInstance *,ulong,int,long,char *,int)
0x1800815d7  mov     rcx, rsi; this
0x1800815da  call    ?MakeLocalCopyOfCallFrame@CAscCall@@QEAAJXZ; CAscCall::MakeLocalCopyOfCallFrame(void)
0x1800815df  mov     ebx, eax
0x1800815e1  test    eax, eax
0x1800815e3  jz      short loc_1800815FC
0x1800815e5  mov     rcx, [rsi]
0x1800815e8  mov     rax, [rcx+10h]
0x1800815ec  mov     rcx, rsi
0x1800815ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800815f4  mov     r15d, ebx
0x1800815f7  jmp     loc_18008197D
0x1800815fc  lea     rbx, [rdi+0B8h]
0x180081603  mov     rax, [rbx]
0x180081606  mov     rcx, rbx
0x180081609  mov     rax, [rax]
0x18008160c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081611  lea     r14, [rdi+98h]
0x180081618  mov     rax, [r14]
0x18008161b  lea     rdx, [rsi+8]
0x18008161f  mov     rcx, r14
0x180081622  mov     rax, [rax+18h]
0x180081626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008162b  mov     rax, [rbx]
0x18008162e  mov     rcx, rbx
0x180081631  mov     rax, [rax+8]
0x180081635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008163a  mov     eax, 1
0x18008163f  xchg    eax, [rdi+110h]
0x180081645  cmp     eax, 1
0x180081648  jz      loc_18008197D
0x18008164e  mov     rax, [rbx]
0x180081651  mov     rcx, rbx
0x180081654  mov     rax, [rax]
0x180081657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008165c  mov     rax, [r14]
0x18008165f  lea     rdx, [rbp+57h+var_A0]
0x180081663  mov     rcx, r14
0x180081666  mov     rax, [rax+28h]
0x18008166a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008166f  mov     rcx, rbx
0x180081672  test    eax, eax
0x180081674  jnz     short loc_18008167E
0x180081676  mov     rax, [rbx]
0x180081679  jmp     loc_18008196D
0x18008167e  mov     rax, [rbp+57h+var_A0]
0x180081682  mov     r14, [rax+8]
0x180081686  mov     rax, [rbx]
0x180081689  mov     rax, [rax+8]
0x18008168d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081692  mov     rsi, [rbp+57h+arg_10]
0x180081696  jmp     short loc_18008169C
0x180081698  lea     r14, [rbp+57h+var_90]
0x18008169c  mov     ecx, cs:?g_iTls@@3KA; dwTlsIndex
0x1800816a2  call    cs:__imp_TlsGetValue
0x1800816a8  mov     [rbp+57h+lpTlsValue], rax
0x1800816ac  call    cs:__imp_GetLastError
0x1800816b2  mov     ebx, eax
0x1800816b4  call    cs:__imp_GetLastError
0x1800816ba  xor     r8d, r8d
0x1800816bd  test    eax, eax
0x1800816bf  setz    r8b; int
0x1800816c3  mov     dword ptr [rsp+28h], 23Eh; int
0x1800816cb  lea     rax, aComComplusDtcD_60; "com\\complus\\dtc\\dtc\\asc\\ascwrapper"...
0x1800816d2  mov     [rsp+0D0h+var_B0], rax; char *
0x1800816d7  mov     r9d, ebx; int
0x1800816da  mov     edx, 0C0001071h; unsigned int
0x1800816df  xor     ecx, ecx; struct ITmInstance *
0x1800816e1  call    ?DELLogCriticalErrorHelperWithHr@@YAXPEAUITmInstance@@KHJPEADH@Z; DELLogCriticalErrorHelperWithHr(ITmInstance *,ulong,int,long,char *,int)
0x1800816e6  mov     rdx, rdi; lpTlsValue
0x1800816e9  mov     ecx, cs:?g_iTls@@3KA; dwTlsIndex
0x1800816ef  call    cs:__imp_TlsSetValue
0x1800816f5  test    eax, eax
0x1800816f7  jnz     short loc_180081733
0x1800816f9  call    cs:__imp_GetLastError
0x1800816ff  mov     ebx, eax
0x180081701  call    cs:__imp_GetLastError
0x180081707  xor     r8d, r8d
0x18008170a  test    eax, eax
0x18008170c  setz    r8b; int
0x180081710  mov     dword ptr [rsp+28h], 242h; int
0x180081718  lea     rax, aComComplusDtcD_60; "com\\complus\\dtc\\dtc\\asc\\ascwrapper"...
0x18008171f  mov     [rsp+0D0h+var_B0], rax; char *
0x180081724  mov     r9d, ebx; int
0x180081727  mov     edx, 0C0001071h; unsigned int
0x18008172c  xor     ecx, ecx; struct ITmInstance *
0x18008172e  call    ?DELLogCriticalErrorHelperWithHr@@YAXPEAUITmInstance@@KHJPEADH@Z; DELLogCriticalErrorHelperWithHr(ITmInstance *,ulong,int,long,char *,int)
0x180081733  lea     rbx, aComComplusDtcD_60; "com\\complus\\dtc\\dtc\\asc\\ascwrapper"...
0x18008173a  mov     rcx, [r14+38h]
0x18008173e  mov     rax, [rcx]
0x180081741  mov     rdx, [r14+40h]
0x180081745  mov     rax, [rax+0A8h]
0x18008174c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081751  xor     r8d, r8d
0x180081754  test    eax, eax
0x180081756  setz    r8b; int
0x18008175a  mov     dword ptr [rsp+28h], 24Ah; int
0x180081762  mov     [rsp+0D0h+var_B0], rbx; char *
0x180081767  mov     r9d, eax; int
0x18008176a  mov     edx, 0C0001071h; unsigned int
0x18008176f  xor     ecx, ecx; struct ITmInstance *
0x180081771  call    ?DELLogCriticalErrorHelperWithHr@@YAXPEAUITmInstance@@KHJPEADH@Z; DELLogCriticalErrorHelperWithHr(ITmInstance *,ulong,int,long,char *,int)
0x180081776  lea     rax, [rbp+57h+var_90]
0x18008177a  test    byte ptr [rdi+114h], 1
0x180081781  jz      short loc_1800817F2
0x180081783  cmp     r14, rax
0x180081786  jnz     short loc_1800817D2
0x180081788  mov     r8, r13; struct CAscInterceptor *
0x18008178b  mov     rdx, rsi; struct ICallFrame *
0x18008178e  mov     rcx, r12; void *
0x180081791  call    ?CreateInstance@CAscCall@@SAPEAV1@PEAXPEAUICallFrame@@PEAVCAscInterceptor@@@Z; CAscCall::CreateInstance(void *,ICallFrame *,CAscInterceptor *)
0x180081796  mov     r14, rax
0x180081799  xor     r8d, r8d
0x18008179c  test    rax, rax
0x18008179f  setnz   r8b; int
0x1800817a3  mov     dword ptr [rsp+28h], 25Ch; int
0x1800817ab  mov     [rsp+0D0h+var_B0], rbx; char *
0x1800817b0  mov     edx, 0C0001089h; unsigned int
0x1800817b5  xor     ecx, ecx; struct ITmInstance *
0x1800817b7  mov     r9d, 8007000Eh; int
0x1800817bd  call    ?DELLogCriticalErrorHelperWithHr@@YAXPEAUITmInstance@@KHJPEADH@Z; DELLogCriticalErrorHelperWithHr(ITmInstance *,ulong,int,long,char *,int)
0x1800817c2  mov     rcx, r14; this
0x1800817c5  call    ?MakeLocalCopyOfCallFrame@CAscCall@@QEAAJXZ; CAscCall::MakeLocalCopyOfCallFrame(void)
0x1800817ca  test    eax, eax
0x1800817cc  jnz     loc_180081914
0x1800817d2  lea     rcx, [rdi+0F0h]
0x1800817d9  mov     rax, [rcx]
0x1800817dc  lea     rdx, [r14+8]
0x1800817e0  mov     rax, [rax+18h]
0x1800817e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817e9  and     dword ptr [rdi+114h], 0FFFFFFFEh
0x1800817f0  jmp     short loc_180081806
0x1800817f2  cmp     r14, rax
0x1800817f5  jz      short loc_180081806
0x1800817f7  mov     rax, [r14]
0x1800817fa  mov     rcx, r14
0x1800817fd  mov     rax, [rax+10h]
0x180081801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081806  lea     rsi, [rdi+0B8h]
0x18008180d  test    byte ptr [rdi+114h], 2
0x180081814  jz      loc_1800818C8
0x18008181a  mov     rax, [rsi]
0x18008181d  mov     rcx, rsi
0x180081820  mov     rax, [rax]
0x180081823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081828  lea     rbx, [rdi+108h]
0x18008182f  cmp     [rdi+0F8h], r15d
0x180081836  jbe     short loc_18008188D
0x180081838  mov     rcx, [rbx]
0x18008183b  mov     rax, [rdi+0A8h]
0x180081842  mov     [rcx+10h], rax
0x180081846  mov     rcx, [rbx]
0x180081849  cmp     [rdi+0A0h], r15d
0x180081850  jz      short loc_18008185F
0x180081852  mov     rax, [rdi+0A8h]
0x180081859  mov     [rax+18h], rcx
0x18008185d  jmp     short loc_180081866
0x18008185f  mov     [rdi+0B0h], rcx
0x180081866  lea     r12, [rdi+100h]
0x18008186d  mov     rax, [r12]
0x180081871  mov     [rdi+0A8h], rax
0x180081878  mov     eax, [rdi+0F8h]
0x18008187e  add     [rdi+0A0h], eax
0x180081884  lea     r14, [rdi+0B8h]
0x18008188b  jmp     short loc_180081897
0x18008188d  lea     r12, [rdi+100h]
0x180081894  mov     r14, rsi
0x180081897  mov     rax, [rsi]
0x18008189a  mov     rcx, rsi
0x18008189d  mov     rax, [rax+8]
0x1800818a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800818a6  mov     [r12], r15
0x1800818aa  mov     [rbx], r15
0x1800818ad  mov     [rdi+0F8h], r15d
0x1800818b4  and     dword ptr [rdi+114h], 0FFFFFFFDh
0x1800818bb  mov     r12, [rbp+57h+arg_8]
0x1800818bf  lea     rbx, aComComplusDtcD_60; "com\\complus\\dtc\\dtc\\asc\\ascwrapper"...
0x1800818c6  jmp     short loc_1800818CB
0x1800818c8  mov     r14, rsi
0x1800818cb  mov     rax, [r14]
0x1800818ce  mov     rcx, rsi
0x1800818d1  mov     rax, [rax]
0x1800818d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800818d9  lea     rcx, [rdi+98h]
0x1800818e0  mov     rax, [rcx]
0x1800818e3  lea     rdx, [rbp+57h+var_A0]
0x1800818e7  mov     rax, [rax+28h]
0x1800818eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800818f0  test    eax, eax
0x1800818f2  jz      short loc_180081919
0x1800818f4  mov     rax, [rbp+57h+var_A0]
0x1800818f8  mov     r14, [rax+8]
0x1800818fc  mov     rax, [rsi]
0x1800818ff  mov     rcx, rsi
0x180081902  mov     rax, [rax+8]
0x180081906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008190b  mov     rsi, [rbp+57h+arg_10]
0x18008190f  jmp     loc_18008173A
0x180081914  mov     r15d, eax
0x180081917  jmp     short loc_18008197D
0x180081919  mov     rdx, [rbp+57h+lpTlsValue]; lpTlsValue
0x18008191d  mov     ecx, cs:?g_iTls@@3KA; dwTlsIndex
0x180081923  call    cs:__imp_TlsSetValue
0x180081929  test    eax, eax
0x18008192b  jnz     short loc_180081967
0x18008192d  call    cs:__imp_GetLastError
0x180081933  mov     ebx, eax
0x180081935  call    cs:__imp_GetLastError
0x18008193b  xor     r8d, r8d
0x18008193e  test    eax, eax
0x180081940  setz    r8b; int
0x180081944  mov     dword ptr [rsp+28h], 2A4h; int
0x18008194c  lea     rax, aComComplusDtcD_60; "com\\complus\\dtc\\dtc\\asc\\ascwrapper"...
0x180081953  mov     [rsp+0D0h+var_B0], rax; char *
0x180081958  mov     r9d, ebx; int
0x18008195b  mov     edx, 0C0001071h; unsigned int
0x180081960  xor     ecx, ecx; struct ITmInstance *
0x180081962  call    ?DELLogCriticalErrorHelperWithHr@@YAXPEAUITmInstance@@KHJPEADH@Z; DELLogCriticalErrorHelperWithHr(ITmInstance *,ulong,int,long,char *,int)
0x180081967  mov     rax, [rsi]
0x18008196a  mov     rcx, rsi
0x18008196d  mov     [rdi+110h], r15d
0x180081974  mov     rax, [rax+8]
0x180081978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008197d  mov     rcx, [rbp+57h+var_58]
0x180081981  mov     rax, [rcx]
0x180081984  mov     edx, r15d
0x180081987  mov     rax, [rax+40h]
0x18008198b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081990  nop
0x180081991  lea     rcx, [rbp+57h+var_90]; this
0x180081995  call    ??1CAscCall@@QEAA@XZ; CAscCall::~CAscCall(void)
0x18008199a  xor     eax, eax
0x18008199c  mov     rbx, [rsp+0D0h+arg_0]
0x1800819a4  add     rsp, 0A0h
0x1800819ab  pop     r15
0x1800819ad  pop     r14
0x1800819af  pop     r13
0x1800819b1  pop     r12
0x1800819b3  pop     rdi
0x1800819b4  pop     rsi
0x1800819b5  pop     rbp
0x1800819b6  retn
```
