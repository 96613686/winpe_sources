# CEnumProxyBuffer::XEnumFacelet::Next(long,ulong,IWbemClassObject * *,ulong *)

- ea: `0x180035e90`
- end: `0x180036221`
- name: `?Next@XEnumFacelet@CEnumProxyBuffer@@UEAAJJKPEAPEAUIWbemClassObject@@PEAK@Z`
- size: `913`
- prototype: `int(CEnumProxyBuffer::XEnumFacelet *__hidden this, int, unsigned int, struct IWbemClassObject **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180035e90`
- `0x180036230`
- `0x180036b90`
- `0x180037120`
- `0x18003b8c0`
- `0x18006fa66`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800360a1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800360a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035fd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035fd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036100`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036100`
- `wbemcomn!GetMemLogObject` at `0x180035fda`
- `wbemcomn!GetMemLogObject` at `0x180036122`
- `wbemcomn!GetMemLogObject` at `0x180036138`
- `wbemcomn!GetMemLogObject` at `0x180035fda`
- `wbemcomn!GetMemLogObject` at `0x180036122`
- `wbemcomn!GetMemLogObject` at `0x180036138`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035fe5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003612d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036148`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035fe5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003612d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036148`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036047`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036047`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEnumProxyBuffer::XEnumFacelet::Next(
        CEnumProxyBuffer::XEnumFacelet *this,
        signed int a2,
        int a3,
        struct IWbemClassObject **a4,
        unsigned int *a5)
{
  unsigned int v6; // r15d
  __int64 v8; // rdi
  HRESULT v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r10
  int v12; // ebx
  CMemoryLog *v13; // rax
  CWbemRefreshingSvc *v14; // rcx
  void *v16; // rdi
  char v17; // r15
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r9
  unsigned int v22; // [rsp+40h] [rbp-41h] BYREF
  int v23; // [rsp+44h] [rbp-3Dh] BYREF
  void *Src; // [rsp+48h] [rbp-39h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-31h] BYREF
  char v26; // [rsp+60h] [rbp-21h]
  GUID pguid; // [rsp+68h] [rbp-19h] BYREF

  v23 = a3;
  v6 = a2;
  v22 = a2;
  if ( a2 >= -1 && a5 && a4 )
  {
    v8 = *((_QWORD *)this + 2);
    v9 = 0;
    if ( !*(_QWORD *)(v8 + 96) )
    {
      pv[0] = 0;
      if ( (***(int (__fastcall ****)(_QWORD, GUID *, LPVOID *))(v8 + 16))(
             *(_QWORD *)(v8 + 16),
             &IID_IWbemFetchSmartEnum,
             pv) >= 0 )
      {
        Src = 0;
        pguid = 0;
        v9 = (*(__int64 (__fastcall **)(LPVOID, void **))(*(_QWORD *)pv[0] + 24LL))(pv[0], &Src);
        if ( v9 >= 0 )
        {
          v9 = CoCreateGuid(&pguid);
          if ( v9 < 0 )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
          }
          else
          {
            pv[1] = (LPVOID)(v8 + 104);
            v26 = 0;
            v17 = CriticalSection::acquire_write((CriticalSection *)(v8 + 104));
            v26 = v17;
            if ( *(_QWORD *)(v8 + 96) )
            {
              (*(void (__fastcall **)(void *))(*(_QWORD *)Src + 16LL))(Src);
            }
            else
            {
              *(_QWORD *)(v8 + 96) = Src;
              *(GUID *)(v8 + 80) = pguid;
              *(_DWORD *)(v8 + 76) = 1;
            }
            if ( v17 )
            {
              v26 = 0;
              if ( *(_BYTE *)(v8 + 144) )
                LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 104));
            }
            v6 = v22;
          }
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv[0] + 16LL))(pv[0]);
        if ( v9 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v9);
        }
      }
    }
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_f248701d70f73d91610ece89a4c9960f_Traceguids,
        (unsigned int)v9);
    }
    v10 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v10 + 76) && (v11 = *(_QWORD *)(v10 + 96)) != 0 )
    {
      pv[0] = 0;
      v22 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned int *, unsigned int *, LPVOID *))(*(_QWORD *)v11 + 24LL))(
              v11,
              v10 + 80,
              v6,
              (unsigned int)v23,
              a5,
              &v22,
              pv);
      if ( v12 < 0 )
      {
LABEL_15:
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, v12);
        goto LABEL_16;
      }
      if ( !*a5 )
      {
LABEL_16:
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = 16;
          v21 = (unsigned int)v12;
          goto LABEL_41;
        }
        return (unsigned int)v12;
      }
      *(_QWORD *)&pguid.Data1 = 0;
      *(_DWORD *)pguid.Data4 = 0;
      CWbemSmartEnumNextPacket::SetData((CWbemSmartEnumNextPacket *)&pguid, (unsigned __int8 *)pv[0], v22, 1);
      v23 = 0;
      Src = 0;
      if ( (int)CWbemSmartEnumNextPacket::UnmarshalPacket(
                  (CWbemSmartEnumNextPacket *)&pguid,
                  &v23,
                  (struct IWbemClassObject ***)&Src,
                  (CEnumProxyBuffer::XEnumFacelet *)((char *)this + 24)) >= 0
        && v23 > 0
        && (v16 = Src) != 0 )
      {
        memcpy_0(a4, Src, 8LL * *a5);
        CWin32DefaultArena::WbemMemFree(v16);
      }
      else
      {
        v12 = -2147217379;
      }
      CoTaskMemFree(pv[0]);
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IWbemClassObject **, unsigned int *))(**(_QWORD **)(v10 + 64) + 32LL))(
              *(_QWORD *)(v10 + 64),
              v6,
              (unsigned int)v23,
              a4,
              a5);
    }
    if ( v12 < 0 )
      goto LABEL_15;
    goto LABEL_16;
  }
  v19 = GetMemLogObject();
  v12 = -2147217400;
  CMemoryLog::Write(v19, -2147217400);
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = 15;
    v21 = 2147749896LL;
LABEL_41:
    WPP_SF_d(*((_QWORD *)v14 + 2), v20, WPP_f248701d70f73d91610ece89a4c9960f_Traceguids, v21);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180035e90  push    rbp
0x180035e92  push    rbx
0x180035e93  push    rsi
0x180035e94  push    rdi
0x180035e95  push    r12
0x180035e97  push    r13
0x180035e99  push    r14
0x180035e9b  push    r15
0x180035e9d  lea     rbp, [rsp-17h]
0x180035ea2  sub     rsp, 98h
0x180035ea9  mov     rax, cs:__security_cookie
0x180035eb0  xor     rax, rsp
0x180035eb3  mov     [rbp+4Fh+var_50], rax
0x180035eb7  mov     r12, r9
0x180035eba  mov     [rbp+4Fh+var_8C], r8d
0x180035ebe  mov     r15d, edx
0x180035ec1  mov     [rbp+4Fh+var_90], edx
0x180035ec4  mov     r13, rcx
0x180035ec7  mov     r14, [rbp+4Fh+arg_20]
0x180035ecb  cmp     edx, 0FFFFFFFFh
0x180035ece  jl      loc_180036138
0x180035ed4  xor     esi, esi
0x180035ed6  test    r14, r14
0x180035ed9  jz      loc_180036138
0x180035edf  test    r9, r9
0x180035ee2  jz      loc_180036138
0x180035ee8  mov     rdi, [rcx+10h]
0x180035eec  mov     ebx, esi
0x180035eee  cmp     [rdi+60h], rsi
0x180035ef2  jz      loc_180036052
0x180035ef8  lea     rsi, WPP_GLOBAL_Control
0x180035eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f06  cmp     rcx, rsi
0x180035f09  jz      short loc_180035F15
0x180035f0b  test    byte ptr [rcx+1Ch], 1
0x180035f0f  jnz     loc_1800361E8
0x180035f15  mov     rcx, [r13+10h]
0x180035f19  cmp     dword ptr [rcx+4Ch], 0
0x180035f1d  jz      loc_18003619B
0x180035f23  mov     r10, [rcx+60h]
0x180035f27  test    r10, r10
0x180035f2a  jz      loc_18003619B
0x180035f30  mov     [rbp+4Fh+pv], 0
0x180035f38  mov     [rbp+4Fh+var_90], 0
0x180035f3f  mov     rax, [r10]
0x180035f42  lea     rdx, [rcx+50h]
0x180035f46  lea     rcx, [rbp+4Fh+pv]
0x180035f4a  mov     [rsp+0D0h+var_A0], rcx
0x180035f4f  lea     rcx, [rbp+4Fh+var_90]
0x180035f53  mov     [rsp+0D0h+var_A8], rcx
0x180035f58  mov     [rsp+0D0h+var_B0], r14
0x180035f5d  mov     r9d, [rbp+4Fh+var_8C]
0x180035f61  mov     r8d, r15d
0x180035f64  mov     rcx, r10
0x180035f67  mov     rax, [rax+18h]
0x180035f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f70  mov     ebx, eax
0x180035f72  test    eax, eax
0x180035f74  js      short loc_180035FDA
0x180035f76  cmp     dword ptr [r14], 0
0x180035f7a  jbe     short loc_180035FEB
0x180035f7c  mov     qword ptr [rbp+4Fh+pguid.Data1], 0
0x180035f84  mov     dword ptr [rbp+4Fh+pguid.Data4], 0
0x180035f8b  mov     r9b, 1; bool
0x180035f8e  mov     r8d, [rbp+4Fh+var_90]; unsigned int
0x180035f92  mov     rdx, [rbp+4Fh+pv]; unsigned __int8 *
0x180035f96  lea     rcx, [rbp+4Fh+pguid]; this
0x180035f9a  call    ?SetData@CWbemSmartEnumNextPacket@@QEAAXPEAEK_N@Z; CWbemSmartEnumNextPacket::SetData(uchar *,ulong,bool)
0x180035f9f  mov     [rbp+4Fh+var_8C], 0
0x180035fa6  mov     [rbp+4Fh+Src], 0
0x180035fae  lea     r9, [r13+18h]; struct CWbemClassCache *
0x180035fb2  lea     r8, [rbp+4Fh+Src]; struct IWbemClassObject ***
0x180035fb6  lea     rdx, [rbp+4Fh+var_8C]; int *
0x180035fba  lea     rcx, [rbp+4Fh+pguid]; this
0x180035fbe  call    ?UnmarshalPacket@CWbemSmartEnumNextPacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z; CWbemSmartEnumNextPacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)
0x180035fc3  test    eax, eax
0x180035fc5  jns     short loc_180036023
0x180035fc7  mov     ebx, 8004101Dh
0x180035fcc  mov     rcx, [rbp+4Fh+pv]; pv
0x180035fd0  call    cs:__imp_CoTaskMemFree
0x180035fd6  test    ebx, ebx
0x180035fd8  jns     short loc_180035FEB
0x180035fda  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035fe0  mov     edx, ebx
0x180035fe2  mov     rcx, rax
0x180035fe5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035ff2  cmp     rcx, rsi
0x180035ff5  jz      short loc_180036001
0x180035ff7  test    byte ptr [rcx+1Ch], 1
0x180035ffb  jnz     loc_1800361C1
0x180036001  mov     eax, ebx
0x180036003  mov     rcx, [rbp+4Fh+var_50]
0x180036007  xor     rcx, rsp; StackCookie
0x18003600a  call    __security_check_cookie
0x18003600f  add     rsp, 98h
0x180036016  pop     r15
0x180036018  pop     r14
0x18003601a  pop     r13
0x18003601c  pop     r12
0x18003601e  pop     rdi
0x18003601f  pop     rsi
0x180036020  pop     rbx
0x180036021  pop     rbp
0x180036022  retn
0x180036023  cmp     [rbp+4Fh+var_8C], 0
0x180036027  jle     short loc_180035FC7
0x180036029  mov     rdi, [rbp+4Fh+Src]
0x18003602d  test    rdi, rdi
0x180036030  jz      short loc_180035FC7
0x180036032  mov     r8d, [r14]
0x180036035  shl     r8, 3; Size
0x180036039  mov     rdx, rdi; Src
0x18003603c  mov     rcx, r12; void *
0x18003603f  call    memcpy_0
0x180036044  mov     rcx, rdi
0x180036047  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003604d  jmp     loc_180035FCC
0x180036052  mov     [rbp+4Fh+pv], rsi
0x180036056  mov     rcx, [rdi+10h]
0x18003605a  mov     rax, [rcx]
0x18003605d  lea     r8, [rbp+4Fh+pv]
0x180036061  lea     rdx, IID_IWbemFetchSmartEnum
0x180036068  mov     rax, [rax]
0x18003606b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036070  test    eax, eax
0x180036072  js      loc_180035EF8
0x180036078  mov     [rbp+4Fh+Src], rsi
0x18003607c  xorps   xmm0, xmm0
0x18003607f  movups  xmmword ptr [rbp+4Fh+pguid.Data1], xmm0
0x180036083  mov     rcx, [rbp+4Fh+pv]
0x180036087  mov     rax, [rcx]
0x18003608a  lea     rdx, [rbp+4Fh+Src]
0x18003608e  mov     rax, [rax+18h]
0x180036092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036097  mov     ebx, eax
0x180036099  test    eax, eax
0x18003609b  js      short loc_18003610A
0x18003609d  lea     rcx, [rbp+4Fh+pguid]; pguid
0x1800360a1  call    cs:__imp_CoCreateGuid
0x1800360a7  mov     ebx, eax
0x1800360a9  test    eax, eax
0x1800360ab  js      loc_180036186
0x1800360b1  lea     rsi, [rdi+68h]
0x1800360b5  mov     [rbp+4Fh+var_78], rsi
0x1800360b9  mov     [rbp+4Fh+var_70], 0
0x1800360bd  mov     rcx, rsi; this
0x1800360c0  call    ?acquire_write@CriticalSection@@QEAA_NXZ; CriticalSection::acquire_write(void)
0x1800360c5  mov     r15b, al
0x1800360c8  mov     [rbp+4Fh+var_70], al
0x1800360cb  mov     rcx, [rbp+4Fh+Src]
0x1800360cf  cmp     qword ptr [rdi+60h], 0
0x1800360d4  jnz     loc_18003620F
0x1800360da  mov     [rdi+60h], rcx
0x1800360de  movups  xmm0, xmmword ptr [rbp+4Fh+pguid.Data1]
0x1800360e2  movdqu  xmmword ptr [rdi+50h], xmm0
0x1800360e7  mov     dword ptr [rdi+4Ch], 1
0x1800360ee  test    r15b, r15b
0x1800360f1  jz      short loc_180036106
0x1800360f3  mov     [rbp+4Fh+var_70], 0
0x1800360f7  cmp     byte ptr [rsi+28h], 0
0x1800360fb  jz      short loc_180036106
0x1800360fd  mov     rcx, rsi; lpCriticalSection
0x180036100  call    cs:__imp_LeaveCriticalSection
0x180036106  mov     r15d, [rbp+4Fh+var_90]
0x18003610a  mov     rcx, [rbp+4Fh+pv]
0x18003610e  mov     rax, [rcx]
0x180036111  mov     rax, [rax+10h]
0x180036115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003611a  test    ebx, ebx
0x18003611c  jns     loc_180035EF8
0x180036122  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036128  mov     edx, ebx
0x18003612a  mov     rcx, rax
0x18003612d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036133  jmp     loc_180035EF8
0x180036138  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003613e  mov     ebx, 80041008h
0x180036143  mov     edx, ebx
0x180036145  mov     rcx, rax
0x180036148  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003614e  lea     rsi, WPP_GLOBAL_Control
0x180036155  mov     rcx, cs:WPP_GLOBAL_Control
0x18003615c  cmp     rcx, rsi
0x18003615f  jz      loc_180036001
0x180036165  test    byte ptr [rcx+1Ch], 1
0x180036169  jz      loc_180036001
0x18003616f  cmp     byte ptr [rcx+19h], 2
0x180036173  jb      loc_180036001
0x180036179  mov     edx, 0Fh
0x18003617e  mov     r9d, 80041008h
0x180036184  jmp     short loc_1800361D3
0x180036186  mov     rcx, [rbp+4Fh+Src]
0x18003618a  mov     rax, [rcx]
0x18003618d  mov     rax, [rax+10h]
0x180036191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036196  jmp     loc_18003610A
0x18003619b  mov     rcx, [rcx+40h]
0x18003619f  mov     rax, [rcx]
0x1800361a2  mov     [rsp+0D0h+var_B0], r14
0x1800361a7  mov     r9, r12
0x1800361aa  mov     r8d, [rbp+4Fh+var_8C]
0x1800361ae  mov     edx, r15d
0x1800361b1  mov     rax, [rax+20h]
0x1800361b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361ba  mov     ebx, eax
0x1800361bc  jmp     loc_180035FD6
0x1800361c1  cmp     byte ptr [rcx+19h], 2
0x1800361c5  jb      loc_180036001
0x1800361cb  mov     edx, 10h
0x1800361d0  mov     r9d, ebx
0x1800361d3  lea     r8, WPP_f248701d70f73d91610ece89a4c9960f_Traceguids
0x1800361da  mov     rcx, [rcx+10h]
0x1800361de  call    WPP_SF_d
0x1800361e3  jmp     loc_180036001
0x1800361e8  cmp     byte ptr [rcx+19h], 2
0x1800361ec  jb      loc_180035F15
0x1800361f2  mov     edx, 12h
0x1800361f7  mov     r9d, ebx
0x1800361fa  lea     r8, WPP_f248701d70f73d91610ece89a4c9960f_Traceguids
0x180036201  mov     rcx, [rcx+10h]
0x180036205  call    WPP_SF_d
0x18003620a  jmp     loc_180035F15
0x18003620f  mov     rax, [rcx]
0x180036212  mov     rax, [rax+10h]
0x180036216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003621b  jmp     loc_1800360EE
```
