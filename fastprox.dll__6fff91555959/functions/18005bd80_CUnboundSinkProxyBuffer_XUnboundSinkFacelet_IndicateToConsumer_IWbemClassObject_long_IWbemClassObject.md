# CUnboundSinkProxyBuffer::XUnboundSinkFacelet::IndicateToConsumer(IWbemClassObject *,long,IWbemClassObject * *)

- ea: `0x18005bd80`
- end: `0x18005c2c5`
- name: `?IndicateToConsumer@XUnboundSinkFacelet@CUnboundSinkProxyBuffer@@UEAAJPEAUIWbemClassObject@@JPEAPEAU3@@Z`
- size: `1349`
- prototype: `int(CUnboundSinkProxyBuffer::XUnboundSinkFacelet *__hidden this, struct IWbemClassObject *, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x18005bd80`
- `0x18005c2cc`
- `0x18005c460`
- `0x18005f8cc`
- `0x18006c9a4`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18005bdad`
- `wbemcomn!GetMemLogObject` at `0x18005be03`
- `wbemcomn!GetMemLogObject` at `0x18005be40`
- `wbemcomn!GetMemLogObject` at `0x18005bf49`
- `wbemcomn!GetMemLogObject` at `0x18005c043`
- `wbemcomn!GetMemLogObject` at `0x18005c0d0`
- `wbemcomn!GetMemLogObject` at `0x18005c1e2`
- `wbemcomn!GetMemLogObject` at `0x18005c240`
- `wbemcomn!GetMemLogObject` at `0x18005bdad`
- `wbemcomn!GetMemLogObject` at `0x18005be03`
- `wbemcomn!GetMemLogObject` at `0x18005be40`
- `wbemcomn!GetMemLogObject` at `0x18005bf49`
- `wbemcomn!GetMemLogObject` at `0x18005c043`
- `wbemcomn!GetMemLogObject` at `0x18005c0d0`
- `wbemcomn!GetMemLogObject` at `0x18005c1e2`
- `wbemcomn!GetMemLogObject` at `0x18005c240`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005c2a9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005c2a9`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005be9f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005be9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005bdbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005be11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005be4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005bf54`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c04e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c0db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c1ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c250`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005bdbb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005be11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005be4e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005bf54`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c04e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c0db`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c1ed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c250`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18005c22e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18005c238`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18005c22e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18005c238`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18005bfbf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18005bfd7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18005bfbf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18005bfd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUnboundSinkProxyBuffer::XUnboundSinkFacelet::IndicateToConsumer(
        CUnboundSinkProxyBuffer::XUnboundSinkFacelet *this,
        struct IWbemClassObject *a2,
        int a3,
        struct IWbemClassObject **a4)
{
  struct IWbemClassObject **v4; // r14
  int v5; // edi
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v9; // rcx
  __int64 v10; // rdx
  CMemoryLog *v11; // rax
  CMemoryLog *v12; // rax
  __int64 v14; // rcx
  signed int v15; // ebx
  __int64 v16; // rax
  CMemoryLog *v17; // rax
  struct _GUID *v18; // r13
  CWbemUnboundSinkIndicatePacket *v19; // rcx
  void *v20; // r12
  CMemoryLog *v21; // rax
  CWbemRefreshingSvc *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  bool v25; // r9
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  void *v29[2]; // [rsp+40h] [rbp-79h] BYREF
  void *v30[2]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v31[8]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v32; // [rsp+68h] [rbp-51h] BYREF
  int v33; // [rsp+70h] [rbp-49h]
  __int64 v34; // [rsp+78h] [rbp-41h]
  _BYTE v35[16]; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int8 *v36; // [rsp+90h] [rbp-29h]
  unsigned int v37; // [rsp+98h] [rbp-21h]
  int v38; // [rsp+9Ch] [rbp-1Dh]
  unsigned int v39; // [rsp+130h] [rbp+77h] BYREF

  v4 = a4;
  v5 = a3;
  if ( a3 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v10 = 14;
LABEL_17:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_af9a9a087171375eab42b5e13cd24811_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  if ( a3 )
  {
    if ( !a4 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, -2147217400);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749896LL;
      }
      v10 = 16;
      goto LABEL_17;
    }
  }
  else if ( a4 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2147217400);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v10 = 15;
    goto LABEL_17;
  }
  CInCritSec::CInCritSec((CInCritSec *)v31, (struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v14 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v14 + 24) )
  {
    if ( *(_DWORD *)(v14 + 24) == 2 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, __int64, struct IWbemClassObject **))(**(_QWORD **)(v14 + 16) + 24LL))(
              *(_QWORD *)(v14 + 16),
              a2,
              1,
              v4);
      --v5;
      ++v4;
      v16 = *((_QWORD *)this + 2);
      if ( v15 != 262399 )
      {
        *(_DWORD *)(v16 + 24) = 0;
        if ( v5 > 0 )
          v15 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))(**(_QWORD **)(*((_QWORD *)this + 2) + 16LL) + 24LL))(
                  *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
                  a2,
                  (unsigned int)v5,
                  v4);
        if ( v15 < 0 )
        {
          v17 = GetMemLogObject();
          CMemoryLog::Write(v17, v15);
        }
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_af9a9a087171375eab42b5e13cd24811_Traceguids,
            (unsigned int)v15);
        }
        goto LABEL_68;
      }
      *(_DWORD *)(v16 + 24) = 1;
    }
    if ( v5 < 1 )
    {
      v15 = 0;
      goto LABEL_68;
    }
    v39 = 0;
    v18 = (struct _GUID *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v5, 0x10u));
    v20 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v5, 4u));
    v30[0] = v18;
    v30[1] = 0;
    v29[0] = v20;
    v29[1] = 0;
    if ( !v18 || !v20 )
    {
      v28 = GetMemLogObject();
      v15 = -2147217402;
      CMemoryLog::Write(v28, -2147217402);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v23 = 18;
      v24 = 2147749894LL;
      goto LABEL_66;
    }
    v34 = 0;
    v32 = 0;
    v33 = 0;
    v15 = CWbemUnboundSinkIndicatePacket::CalculateLength(
            v19,
            a2,
            v5,
            v4,
            &v39,
            (struct CWbemClassToIdMap *)(*((_QWORD *)this + 2) + 32LL),
            v18,
            (int *)v20);
    if ( v15 < 0 )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v15);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v23 = 19;
      goto LABEL_41;
    }
    memset_0(v35, 0, 0x50u);
    v37 = v39;
    v38 = 3;
    v15 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, GUID *))(**(_QWORD **)(*((_QWORD *)this + 2) + 184LL) + 24LL))(
            *(_QWORD *)(*((_QWORD *)this + 2) + 184LL),
            v35,
            &IID_IWbemUnboundObjectSink);
    if ( v15 < 0 )
    {
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, v15);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_67;
      }
      v23 = 20;
LABEL_41:
      v24 = (unsigned int)v15;
LABEL_66:
      WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_af9a9a087171375eab42b5e13cd24811_Traceguids, v24);
LABEL_67:
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v29);
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v30);
      goto LABEL_68;
    }
    CWbemUnboundSinkIndicatePacket::SetData((CWbemUnboundSinkIndicatePacket *)&v32, v36, v39, v25);
    v15 = CWbemUnboundSinkIndicatePacket::MarshalPacket(
            (CWbemUnboundSinkIndicatePacket *)&v32,
            a2,
            v5,
            v4,
            v18,
            (int *)v20);
    if ( v15 < 0 )
    {
      if ( v36 )
        (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(*((_QWORD *)this + 2) + 184LL) + 40LL))(
          *(_QWORD *)(*((_QWORD *)this + 2) + 184LL),
          v35);
    }
    else
    {
      v39 = 0;
      if ( (*(int (__fastcall **)(_QWORD, _BYTE *, unsigned int *))(**(_QWORD **)(*((_QWORD *)this + 2) + 184LL) + 32LL))(
             *(_QWORD *)(*((_QWORD *)this + 2) + 184LL),
             v35,
             &v39) < 0 )
      {
        if ( v36 )
          (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(*((_QWORD *)this + 2) + 184LL) + 40LL))(
            *(_QWORD *)(*((_QWORD *)this + 2) + 184LL),
            v35);
        v15 = v39;
        goto LABEL_67;
      }
      v15 = *(_DWORD *)v36;
      (*(void (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(*((_QWORD *)this + 2) + 184LL) + 40LL))(
        *(_QWORD *)(*((_QWORD *)this + 2) + 184LL),
        v35);
      if ( v15 >= 0 )
      {
LABEL_57:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_af9a9a087171375eab42b5e13cd24811_Traceguids,
            (unsigned int)v15);
        }
        CWin32DefaultArena::WbemMemFree(v20);
        CWin32DefaultArena::WbemMemFree(v18);
        goto LABEL_68;
      }
    }
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, v15);
    goto LABEL_57;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, _QWORD, struct IWbemClassObject **))(**(_QWORD **)(v14 + 16) + 24LL))(
          *(_QWORD *)(v14 + 16),
          a2,
          (unsigned int)v5,
          v4);
LABEL_68:
  CInCritSec::~CInCritSec((CInCritSec *)v31);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18005bd80  push    rbp
0x18005bd82  push    rbx
0x18005bd83  push    rsi
0x18005bd84  push    rdi
0x18005bd85  push    r12
0x18005bd87  push    r13
0x18005bd89  push    r14
0x18005bd8b  push    r15
0x18005bd8d  lea     rbp, [rsp-1Fh]
0x18005bd92  sub     rsp, 0D8h
0x18005bd99  mov     r14, r9
0x18005bd9c  mov     edi, r8d
0x18005bd9f  mov     r15, rdx
0x18005bda2  mov     rsi, rcx
0x18005bda5  xor     r12d, r12d
0x18005bda8  test    r8d, r8d
0x18005bdab  jns     short loc_18005BDF6
0x18005bdad  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005bdb3  mov     edx, 80041008h
0x18005bdb8  mov     rcx, rax
0x18005bdbb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005bdc1  lea     rax, WPP_GLOBAL_Control
0x18005bdc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bdcf  cmp     rcx, rax
0x18005bdd2  jz      loc_18005BE8D
0x18005bdd8  test    byte ptr [rcx+1Ch], 1
0x18005bddc  jz      loc_18005BE8D
0x18005bde2  cmp     byte ptr [rcx+19h], 2
0x18005bde6  jb      loc_18005BE8D
0x18005bdec  lea     edx, [r12+0Eh]
0x18005bdf1  jmp     loc_18005BE77
0x18005bdf6  test    edi, edi
0x18005bdf8  jnz     short loc_18005BE3B
0x18005bdfa  test    r14, r14
0x18005bdfd  jz      loc_18005BE97
0x18005be03  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005be09  mov     edx, 80041008h
0x18005be0e  mov     rcx, rax
0x18005be11  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005be17  lea     rax, WPP_GLOBAL_Control
0x18005be1e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be25  cmp     rcx, rax
0x18005be28  jz      short loc_18005BE8D
0x18005be2a  test    byte ptr [rcx+1Ch], 1
0x18005be2e  jz      short loc_18005BE8D
0x18005be30  cmp     byte ptr [rcx+19h], 2
0x18005be34  jb      short loc_18005BE8D
0x18005be36  lea     edx, [rdi+0Fh]
0x18005be39  jmp     short loc_18005BE77
0x18005be3b  test    r14, r14
0x18005be3e  jnz     short loc_18005BE97
0x18005be40  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005be46  mov     edx, 80041008h
0x18005be4b  mov     rcx, rax
0x18005be4e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005be54  lea     rax, WPP_GLOBAL_Control
0x18005be5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be62  cmp     rcx, rax
0x18005be65  jz      short loc_18005BE8D
0x18005be67  test    byte ptr [rcx+1Ch], 1
0x18005be6b  jz      short loc_18005BE8D
0x18005be6d  cmp     byte ptr [rcx+19h], 2
0x18005be71  jb      short loc_18005BE8D
0x18005be73  lea     edx, [r14+10h]
0x18005be77  mov     r9d, 80041008h
0x18005be7d  lea     r8, WPP_af9a9a087171375eab42b5e13cd24811_Traceguids
0x18005be84  mov     rcx, [rcx+10h]
0x18005be88  call    WPP_SF_d
0x18005be8d  mov     eax, 80041008h
0x18005be92  jmp     loc_18005C2B1
0x18005be97  lea     rdx, [rcx+18h]
0x18005be9b  lea     rcx, [rbp+57h+var_B0]
0x18005be9f  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18005bea5  nop
0x18005bea6  mov     rcx, [rsi+10h]
0x18005beaa  cmp     [rcx+18h], r12d
0x18005beae  jnz     short loc_18005BED0
0x18005beb0  mov     rcx, [rcx+10h]
0x18005beb4  mov     rax, [rcx]
0x18005beb7  mov     r9, r14
0x18005beba  mov     r8d, edi
0x18005bebd  mov     rdx, r15
0x18005bec0  mov     rax, [rax+18h]
0x18005bec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bec9  mov     ebx, eax
0x18005becb  jmp     loc_18005C2A5
0x18005bed0  cmp     dword ptr [rcx+18h], 2
0x18005bed4  jnz     short loc_18005BF0D
0x18005bed6  mov     rcx, [rcx+10h]
0x18005beda  mov     rax, [rcx]
0x18005bedd  mov     r9, r14
0x18005bee0  mov     r8d, 1
0x18005bee6  mov     rdx, r15
0x18005bee9  mov     rax, [rax+18h]
0x18005beed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bef2  mov     ebx, eax
0x18005bef4  dec     edi
0x18005bef6  add     r14, 8
0x18005befa  mov     rax, [rsi+10h]
0x18005befe  cmp     ebx, 400FFh
0x18005bf04  jnz     short loc_18005BF1E
0x18005bf06  mov     dword ptr [rax+18h], 1
0x18005bf0d  cmp     edi, 1
0x18005bf10  jge     loc_18005BFA2
0x18005bf16  mov     ebx, r12d
0x18005bf19  jmp     loc_18005C2A5
0x18005bf1e  mov     [rax+18h], r12d
0x18005bf22  test    edi, edi
0x18005bf24  jle     short loc_18005BF45
0x18005bf26  mov     rax, [rsi+10h]
0x18005bf2a  mov     rcx, [rax+10h]
0x18005bf2e  mov     rax, [rcx]
0x18005bf31  mov     r9, r14
0x18005bf34  mov     r8d, edi
0x18005bf37  mov     rdx, r15
0x18005bf3a  mov     rax, [rax+18h]
0x18005bf3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf43  mov     ebx, eax
0x18005bf45  test    ebx, ebx
0x18005bf47  jns     short loc_18005BF5A
0x18005bf49  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005bf4f  mov     edx, ebx
0x18005bf51  mov     rcx, rax
0x18005bf54  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005bf5a  lea     rax, WPP_GLOBAL_Control
0x18005bf61  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bf68  cmp     rcx, rax
0x18005bf6b  jz      loc_18005C2A5
0x18005bf71  test    byte ptr [rcx+1Ch], 1
0x18005bf75  jz      loc_18005C2A5
0x18005bf7b  cmp     byte ptr [rcx+19h], 2
0x18005bf7f  jb      loc_18005C2A5
0x18005bf85  mov     edx, 11h
0x18005bf8a  mov     r9d, ebx
0x18005bf8d  lea     r8, WPP_af9a9a087171375eab42b5e13cd24811_Traceguids
0x18005bf94  mov     rcx, [rcx+10h]
0x18005bf98  call    WPP_SF_d
0x18005bf9d  jmp     loc_18005C2A5
0x18005bfa2  mov     [rbp+57h+arg_10], r12d
0x18005bfa6  movsxd  rbx, edi
0x18005bfa9  mov     eax, 10h
0x18005bfae  mul     rbx
0x18005bfb1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18005bfb8  cmovb   rax, r12
0x18005bfbc  mov     rcx, rax
0x18005bfbf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18005bfc5  mov     r13, rax
0x18005bfc8  lea     eax, [r12+5]
0x18005bfcd  mul     rbx
0x18005bfd0  cmovb   rax, r12
0x18005bfd4  mov     rcx, rax
0x18005bfd7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18005bfdd  mov     r12, rax
0x18005bfe0  mov     [rbp+57h+var_C0], r13
0x18005bfe4  xor     eax, eax
0x18005bfe6  mov     [rbp+57h+var_B8], rax
0x18005bfea  mov     [rbp+57h+var_D0], r12
0x18005bfee  mov     [rbp+57h+var_C8], rax
0x18005bff2  test    r13, r13
0x18005bff5  jz      loc_18005C240
0x18005bffb  test    r12, r12
0x18005bffe  jz      loc_18005C240
0x18005c004  mov     [rbp+57h+var_98], rax
0x18005c008  mov     [rbp+57h+var_A8], rax
0x18005c00c  mov     [rbp+57h+var_A0], eax
0x18005c00f  mov     rax, [rsi+10h]
0x18005c013  add     rax, 20h ; ' '
0x18005c017  mov     [rsp+110h+var_D8], r12; int *
0x18005c01c  mov     [rsp+110h+var_E0], r13; struct _GUID *
0x18005c021  mov     [rsp+110h+var_E8], rax; struct CWbemClassToIdMap *
0x18005c026  lea     rax, [rbp+57h+arg_10]
0x18005c02a  mov     [rsp+110h+var_F0], rax; unsigned int *
0x18005c02f  mov     r9, r14; struct IWbemClassObject **
0x18005c032  mov     r8d, edi; int
0x18005c035  mov     rdx, r15; struct IWbemClassObject *
0x18005c038  call    ?CalculateLength@CWbemUnboundSinkIndicatePacket@@QEAAJPEAUIWbemClassObject@@JPEAPEAU2@PEAKAEAVCWbemClassToIdMap@@PEAU_GUID@@PEAH@Z; CWbemUnboundSinkIndicatePacket::CalculateLength(IWbemClassObject *,long,IWbemClassObject * *,ulong *,CWbemClassToIdMap &,_GUID *,int *)
0x18005c03d  mov     ebx, eax
0x18005c03f  test    eax, eax
0x18005c041  jns     short loc_18005C08C
0x18005c043  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005c049  mov     edx, ebx
0x18005c04b  mov     rcx, rax
0x18005c04e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005c054  lea     rax, WPP_GLOBAL_Control
0x18005c05b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c062  cmp     rcx, rax
0x18005c065  jz      loc_18005C291
0x18005c06b  test    byte ptr [rcx+1Ch], 1
0x18005c06f  jz      loc_18005C291
0x18005c075  cmp     byte ptr [rcx+19h], 2
0x18005c079  jb      loc_18005C291
0x18005c07f  mov     edx, 13h
0x18005c084  mov     r9d, ebx
0x18005c087  jmp     loc_18005C280
0x18005c08c  xor     edx, edx; Val
0x18005c08e  lea     r8d, [rdx+50h]; Size
0x18005c092  lea     rcx, [rbp+57h+var_90]; void *
0x18005c096  call    memset_0
0x18005c09b  mov     eax, [rbp+57h+arg_10]
0x18005c09e  mov     [rbp+57h+var_78], eax
0x18005c0a1  mov     [rbp+57h+var_74], 3
0x18005c0a8  mov     rax, [rsi+10h]
0x18005c0ac  mov     rcx, [rax+0B8h]
0x18005c0b3  mov     rax, [rcx]
0x18005c0b6  lea     r8, IID_IWbemUnboundObjectSink
0x18005c0bd  lea     rdx, [rbp+57h+var_90]
0x18005c0c1  mov     rax, [rax+18h]
0x18005c0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0ca  mov     ebx, eax
0x18005c0cc  test    eax, eax
0x18005c0ce  jns     short loc_18005C116
0x18005c0d0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005c0d6  mov     edx, ebx
0x18005c0d8  mov     rcx, rax
0x18005c0db  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005c0e1  lea     rax, WPP_GLOBAL_Control
0x18005c0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0ef  cmp     rcx, rax
0x18005c0f2  jz      loc_18005C291
0x18005c0f8  test    byte ptr [rcx+1Ch], 1
0x18005c0fc  jz      loc_18005C291
0x18005c102  cmp     byte ptr [rcx+19h], 2
0x18005c106  jb      loc_18005C291
0x18005c10c  mov     edx, 14h
0x18005c111  jmp     loc_18005C084
0x18005c116  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x18005c11a  mov     rdx, [rbp+57h+var_80]; unsigned __int8 *
0x18005c11e  lea     rcx, [rbp+57h+var_A8]; this
0x18005c122  call    ?SetData@CWbemUnboundSinkIndicatePacket@@QEAAXPEAEK_N@Z; CWbemUnboundSinkIndicatePacket::SetData(uchar *,ulong,bool)
0x18005c127  mov     [rsp+110h+var_E8], r12; int *
0x18005c12c  mov     [rsp+110h+var_F0], r13; struct _GUID *
0x18005c131  mov     r9, r14; struct IWbemClassObject **
0x18005c134  mov     r8d, edi; int
0x18005c137  mov     rdx, r15; struct IWbemClassObject *
0x18005c13a  lea     rcx, [rbp+57h+var_A8]; this
0x18005c13e  call    ?MarshalPacket@CWbemUnboundSinkIndicatePacket@@QEAAJPEAUIWbemClassObject@@JPEAPEAU2@PEAU_GUID@@PEAH@Z; CWbemUnboundSinkIndicatePacket::MarshalPacket(IWbemClassObject *,long,IWbemClassObject * *,_GUID *,int *)
0x18005c143  mov     ebx, eax
0x18005c145  xor     edi, edi
0x18005c147  test    eax, eax
0x18005c149  js      short loc_18005C1C1
0x18005c14b  mov     [rbp+57h+arg_10], edi
0x18005c14e  mov     rax, [rsi+10h]
0x18005c152  mov     rcx, [rax+0B8h]
0x18005c159  mov     rax, [rcx]
0x18005c15c  lea     r8, [rbp+57h+arg_10]
0x18005c160  lea     rdx, [rbp+57h+var_90]
0x18005c164  mov     rax, [rax+20h]
0x18005c168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c16d  test    eax, eax
0x18005c16f  jns     short loc_18005C19A
0x18005c171  cmp     [rbp+57h+var_80], rdi
0x18005c175  jz      short loc_18005C192
0x18005c177  mov     rax, [rsi+10h]
0x18005c17b  mov     rcx, [rax+0B8h]
0x18005c182  mov     rax, [rcx]
0x18005c185  lea     rdx, [rbp+57h+var_90]
0x18005c189  mov     rax, [rax+28h]
0x18005c18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c192  mov     ebx, [rbp+57h+arg_10]
0x18005c195  jmp     loc_18005C291
0x18005c19a  mov     rax, [rbp+57h+var_80]
0x18005c19e  mov     ebx, [rax]
0x18005c1a0  mov     rax, [rsi+10h]
0x18005c1a4  mov     rcx, [rax+0B8h]
0x18005c1ab  mov     rax, [rcx]
0x18005c1ae  lea     rdx, [rbp+57h+var_90]
0x18005c1b2  mov     rax, [rax+28h]
0x18005c1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1bb  test    ebx, ebx
0x18005c1bd  js      short loc_18005C1E2
0x18005c1bf  jmp     short loc_18005C1F3
0x18005c1c1  cmp     [rbp+57h+var_80], rdi
0x18005c1c5  jz      short loc_18005C1E2
0x18005c1c7  mov     rax, [rsi+10h]
0x18005c1cb  mov     rcx, [rax+0B8h]
0x18005c1d2  mov     rax, [rcx]
0x18005c1d5  lea     rdx, [rbp+57h+var_90]
0x18005c1d9  mov     rax, [rax+28h]
0x18005c1dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c1e2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005c1e8  mov     edx, ebx
0x18005c1ea  mov     rcx, rax
0x18005c1ed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005c1f3  lea     rax, WPP_GLOBAL_Control
0x18005c1fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c201  cmp     rcx, rax
0x18005c204  jz      short loc_18005C22B
0x18005c206  test    byte ptr [rcx+1Ch], 1
0x18005c20a  jz      short loc_18005C22B
0x18005c20c  cmp     byte ptr [rcx+19h], 2
0x18005c210  jb      short loc_18005C22B
0x18005c212  mov     edx, 16h
0x18005c217  mov     r9d, ebx
0x18005c21a  lea     r8, WPP_af9a9a087171375eab42b5e13cd24811_Traceguids
0x18005c221  mov     rcx, [rcx+10h]
0x18005c225  call    WPP_SF_d
0x18005c22a  nop
0x18005c22b  mov     rcx, r12
0x18005c22e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18005c234  nop
  ... truncated ...
```
