# CWbemInstance::Clone(IWbemClassObject * *)

- ea: `0x18001fa20`
- end: `0x18001fff1`
- name: `?Clone@CWbemInstance@@UEAAJPEAPEAUIWbemClassObject@@@Z`
- size: `1489`
- prototype: `__int64 __fastcall(CWbemInstance *__hidden this, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180013e80`
- `0x18001d3b0`
- `0x18001e490`
- `0x18001f6e0`
- `0x18001f9d0`
- `0x18001fa20`
- `0x180020060`
- `0x180037120`
- `0x180050490`
- `0x18005bd10`
- `0x18006fa66`
- `0x18006fa72`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001fbf3`
- `wbemcomn!GetMemLogObject` at `0x18001fcc8`
- `wbemcomn!GetMemLogObject` at `0x18001fd2c`
- `wbemcomn!GetMemLogObject` at `0x18001fe8a`
- `wbemcomn!GetMemLogObject` at `0x18001ff42`
- `wbemcomn!GetMemLogObject` at `0x18001fbf3`
- `wbemcomn!GetMemLogObject` at `0x18001fcc8`
- `wbemcomn!GetMemLogObject` at `0x18001fd2c`
- `wbemcomn!GetMemLogObject` at `0x18001fe8a`
- `wbemcomn!GetMemLogObject` at `0x18001ff42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fc01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fcd6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fd3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe95`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ff50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fc01`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fcd6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fd3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe95`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ff50`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001fb53`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001fb53`

## pseudocode

```c
__int64 __fastcall CWbemInstance::Clone(CWbemInstance *this, struct IWbemClassObject **a2)
{
  __int64 v4; // r14
  const void *v5; // rdx
  __int64 v6; // r14
  __int64 v7; // rcx
  unsigned int *v8; // rdi
  char *v9; // rdi
  int *v10; // r14
  char *v11; // r14
  _QWORD *v12; // rdi
  CWbemInstance *v13; // r15
  CWbemInstance *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  unsigned __int8 *v18; // r15
  void *v19; // r9
  CWbemInstance *v20; // rax
  CWbemInstance *v21; // r14
  int v22; // eax
  int v23; // edi
  __int64 result; // rax
  CMemoryLog *v25; // rax
  int v26; // ecx
  int v27; // eax
  char *v28; // rax
  int v29; // eax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  unsigned __int8 *v32; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  char v36[8]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v37; // [rsp+40h] [rbp-48h]
  void (__fastcall *v38)(__int64, __int64); // [rsp+48h] [rbp-40h]
  __int64 v39; // [rsp+50h] [rbp-38h]
  CWbemInstance *v40; // [rsp+A0h] [rbp+18h] BYREF
  CWbemInstance *v41; // [rsp+A8h] [rbp+20h]

  try
  {
    v40 = this;
    (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
    if ( a2 )
    {
      if ( (*((_BYTE *)this + 60) & 4) != 0 )
      {
        v4 = *((_QWORD *)this + 27) + 9LL;
        v5 = (const void *)*((_QWORD *)this + 28);
        if ( (const void *)v4 != v5 )
        {
          memmove_0((void *)(*((_QWORD *)this + 27) + 9LL), v5, *((unsigned int *)this + 60));
          v29 = *((_DWORD *)this + 58) - *((_DWORD *)this + 56);
          *((_QWORD *)this + 28) = v4;
          *((_QWORD *)this + 29) = v4 + v29;
        }
        v6 = *((_QWORD *)this + 28) + *((unsigned int *)this + 60);
        v7 = *((_QWORD *)this + 34);
        v8 = (unsigned int *)((char *)this + 264);
        if ( v6 != v7 - 4 )
        {
          memmove_0((void *)(*((_QWORD *)this + 28) + *((unsigned int *)this + 60)), (const void *)(v7 - 4), *v8);
          v7 = v6 + 4;
          *((_QWORD *)this + 34) = v6 + 4;
        }
        v9 = (char *)(v7 + *v8 - 4LL);
        v10 = (int *)((char *)this + 340);
        if ( v9 == *((char **)this + 43) )
        {
          v9 = (char *)*((_QWORD *)this + 43);
        }
        else
        {
          memmove_0(v9, *((const void **)this + 43), *v10);
          *((_QWORD *)this + 43) = v9;
        }
        v11 = &v9[*v10];
        v12 = (_QWORD *)((char *)this + 360);
        v13 = (CWbemInstance *)((char *)this + 376);
        v14 = (CWbemInstance *)*((_QWORD *)this + 46);
        if ( v14 == (CWbemInstance *)((char *)this + 376) )
          v15 = *v12 - 4LL;
        else
          v15 = *((_QWORD *)this + 46);
        if ( v11 != (char *)v15 )
        {
          v26 = *(_DWORD *)v14;
          if ( v14 == v13 )
          {
            v14 = (CWbemInstance *)(*v12 - 4LL);
            v27 = 0;
          }
          else
          {
            v27 = 8;
          }
          memmove_0(v11, v14, (unsigned int)(v26 + v27 + 4));
          if ( *((CWbemInstance **)this + 46) == v13 )
          {
            v28 = v11 + 4;
          }
          else
          {
            *((_QWORD *)this + 46) = v11;
            v28 = v11 + 12;
          }
          *v12 = v28;
        }
        CFastHeap::Trim((CWbemInstance *)((char *)this + 360));
        v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 8LL))(
                *((_QWORD *)this + 15),
                *((unsigned int *)this + 42));
        v18 = (unsigned __int8 *)v16;
        if ( v16 )
        {
          MakeObjGuard<CBlobControl,void (CBlobControl::*)(unsigned char *),unsigned char *>(
            v36,
            *((_QWORD *)this + 15),
            v17,
            v16);
          memcpy_0(v19, *((const void **)this + 9), *((unsigned int *)this + 42));
          v20 = (CWbemInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
          v41 = v20;
          if ( v20 )
            v21 = CWbemInstance::CWbemInstance(v20);
          else
            v21 = 0;
          if ( v21 )
          {
            v22 = *((_DWORD *)this + 15);
            if ( (v22 & 4) != 0 )
            {
              if ( (v22 & 8) != 0 )
              {
                v36[0] = 1;
                (*(void (__fastcall **)(CWbemInstance *, unsigned __int8 *, _QWORD))(*(_QWORD *)v21 + 1152LL))(
                  v21,
                  v18,
                  *((unsigned int *)this + 42));
              }
              else if ( (v22 & 0x10) != 0 )
              {
                v36[0] = 1;
                CDecorationPart::SetData((CWbemInstance *)((char *)v21 + 72), v18);
                v32 = (unsigned __int8 *)EndOf<CDecorationPart>((char *)v21 + 72);
                CInstancePart::SetData(
                  (CWbemInstance *)((char *)v21 + 176),
                  v32,
                  (CWbemInstance *)((char *)v21 + 152),
                  (CWbemInstance *)((char *)this + 400),
                  **((int **)this + 27));
                *((_DWORD *)v21 + 15) = 3;
                v23 = (*(__int64 (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)v21 + 592LL))(
                        v21,
                        *((_QWORD *)this + 8));
                if ( v23 < 0 )
                {
                  (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)v21 + 848LL))(v21, 1);
                  MemLogObject = GetMemLogObject();
                  CMemoryLog::Write(MemLogObject, v23);
                  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      45,
                      WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
                      (unsigned int)v23);
                  }
                  if ( !v36[0] )
                    v38(v37, v39);
                  goto LABEL_20;
                }
                *((_DWORD *)v21 + 15) = *((_DWORD *)this + 15);
                *((_DWORD *)v21 + 42) = *((_DWORD *)this + 42);
              }
            }
            (*(void (__fastcall **)(CWbemInstance *))(*(_QWORD *)v21 + 1128LL))(v21);
            *((_DWORD *)v21 + 10) = 0;
            v23 = (**(__int64 (__fastcall ***)(CWbemInstance *, GUID *, struct IWbemClassObject **))v21)(
                    v21,
                    &IID_IWbemClassObject,
                    a2);
            if ( !v36[0] )
              v38(v37, v39);
LABEL_20:
            (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
            return (unsigned int)v23;
          }
          v34 = GetMemLogObject();
          CMemoryLog::Write(v34, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              46,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749894LL);
          }
          ObjScopeGuardImpl1<CBlobControl,void (CBlobControl::*)(unsigned char *),unsigned char *>::~ObjScopeGuardImpl1<CBlobControl,void (CBlobControl::*)(unsigned char *),unsigned char *>(v36);
          CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v40);
          result = 2147749894LL;
        }
        else
        {
          v30 = GetMemLogObject();
          CMemoryLog::Write(v30, -2147217402);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749894LL);
          }
          (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
          result = 2147749894LL;
        }
      }
      else
      {
        v25 = GetMemLogObject();
        CMemoryLog::Write(v25, -2147217386);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
            2147749910LL);
        }
        (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
        result = 2147749910LL;
      }
    }
    else
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, -2147217400);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749896LL);
      }
      (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      result = 2147749896LL;
    }
  }
  catch ( CX_MemoryException )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v40 = this;
}

```

## disassembly

```asm
0x18001fa20  mov     [rsp+arg_0], rbx
0x18001fa25  push    rsi
0x18001fa26  push    rdi
0x18001fa27  push    r12
0x18001fa29  push    r14
0x18001fa2b  push    r15
0x18001fa2d  sub     rsp, 60h
0x18001fa31  mov     rsi, rdx
0x18001fa34  mov     rbx, rcx
0x18001fa37  xor     r12d, r12d
0x18001fa3a  mov     [rsp+88h+arg_10], rcx
0x18001fa42  mov     rax, [rcx]
0x18001fa45  mov     edx, 1
0x18001fa4a  mov     rax, [rax+118h]
0x18001fa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa56  nop
0x18001fa57  test    rsi, rsi
0x18001fa5a  jz      loc_18001FD2C
0x18001fa60  test    byte ptr [rbx+3Ch], 4
0x18001fa64  jz      loc_18001FBF3
0x18001fa6a  mov     r14, [rbx+0D8h]
0x18001fa71  add     r14, 9
0x18001fa75  mov     rdx, [rbx+0E0h]; Src
0x18001fa7c  cmp     r14, rdx
0x18001fa7f  jnz     loc_18001FC84
0x18001fa85  mov     r14d, [rbx+0F0h]
0x18001fa8c  add     r14, [rbx+0E0h]
0x18001fa93  mov     rcx, [rbx+110h]
0x18001fa9a  lea     rdx, [rcx-4]; Src
0x18001fa9e  lea     rdi, [rbx+108h]
0x18001faa5  cmp     r14, rdx
0x18001faa8  jnz     loc_18001FD11
0x18001faae  mov     edi, [rdi]
0x18001fab0  add     rdi, 0FFFFFFFFFFFFFFFCh
0x18001fab4  add     rdi, rcx
0x18001fab7  mov     rax, [rbx+158h]
0x18001fabe  lea     r14, [rbx+154h]
0x18001fac5  cmp     rdi, rax
0x18001fac8  jnz     loc_18001FD71
0x18001face  mov     rdi, rax
0x18001fad1  movsxd  r14, dword ptr [r14]
0x18001fad4  add     r14, rdi
0x18001fad7  lea     rdi, [rbx+168h]
0x18001fade  lea     r15, [rdi+10h]
0x18001fae2  mov     rdx, [rdi+8]
0x18001fae6  cmp     rdx, r15
0x18001fae9  jnz     loc_18001FBEB
0x18001faef  mov     rax, [rdi]
0x18001faf2  sub     rax, 4
0x18001faf6  cmp     r14, rax
0x18001faf9  jnz     loc_18001FC52
0x18001faff  mov     rcx, rdi; this
0x18001fb02  call    ?Trim@CFastHeap@@QEAAXXZ; CFastHeap::Trim(void)
0x18001fb07  mov     rcx, [rbx+78h]
0x18001fb0b  mov     rax, [rcx]
0x18001fb0e  mov     edx, [rbx+0A8h]
0x18001fb14  mov     rax, [rax+8]
0x18001fb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb1d  mov     r15, rax
0x18001fb20  test    rax, rax
0x18001fb23  jz      loc_18001FCC8
0x18001fb29  mov     r9, rax
0x18001fb2c  mov     rdx, [rbx+78h]
0x18001fb30  lea     rcx, [rsp+88h+var_50]
0x18001fb35  call    ??$MakeObjGuard@VCBlobControl@@P81@EAAXPEAE@ZPEAE@@YA?AV?$ObjScopeGuardImpl1@VCBlobControl@@P81@EAAXPEAE@ZPEAE@@AEAVCBlobControl@@P81@EAAXPEAE@Z1@Z; MakeObjGuard<CBlobControl,void (CBlobControl::*)(uchar *),uchar *>(CBlobControl &,void (CBlobControl::*)(uchar *),uchar *)
0x18001fb3a  nop
0x18001fb3b  mov     r8d, [rbx+0A8h]; Size
0x18001fb42  mov     rdx, [rbx+48h]; Src
0x18001fb46  mov     rcx, r9; void *
0x18001fb49  call    memcpy_0
0x18001fb4e  mov     ecx, 2A0h
0x18001fb53  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001fb59  mov     [rsp+88h+arg_18], rax
0x18001fb61  test    rax, rax
0x18001fb64  jz      loc_18001FD8B
0x18001fb6a  mov     rcx, rax; this
0x18001fb6d  call    ??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x18001fb72  mov     r14, rax
0x18001fb75  test    r14, r14
0x18001fb78  jz      loc_18001FF42
0x18001fb7e  mov     eax, [rbx+3Ch]
0x18001fb81  test    al, 4
0x18001fb83  jnz     loc_18001FF0B
0x18001fb89  mov     rax, [r14]
0x18001fb8c  mov     rcx, r14
0x18001fb8f  mov     rax, [rax+468h]
0x18001fb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb9b  mov     [r14+28h], r12d
0x18001fb9f  mov     rax, [r14]
0x18001fba2  mov     r8, rsi
0x18001fba5  lea     rdx, IID_IWbemClassObject
0x18001fbac  mov     rcx, r14
0x18001fbaf  mov     rax, [rax]
0x18001fbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbb7  mov     edi, eax
0x18001fbb9  cmp     [rsp+88h+var_50], 0
0x18001fbbe  jz      short loc_18001FC39
0x18001fbc0  mov     rax, [rbx]
0x18001fbc3  xor     edx, edx
0x18001fbc5  mov     rcx, rbx
0x18001fbc8  mov     rax, [rax+120h]
0x18001fbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbd4  mov     eax, edi
0x18001fbd6  mov     rbx, [rsp+88h+arg_0]
0x18001fbde  add     rsp, 60h
0x18001fbe2  pop     r15
0x18001fbe4  pop     r14
0x18001fbe6  pop     r12
0x18001fbe8  pop     rdi
0x18001fbe9  pop     rsi
0x18001fbea  retn
0x18001fbeb  mov     rax, rdx
0x18001fbee  jmp     loc_18001FAF6
0x18001fbf3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fbf9  mov     edx, 80041016h
0x18001fbfe  mov     rcx, rax
0x18001fc01  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fc07  lea     rax, WPP_GLOBAL_Control
0x18001fc0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc15  cmp     rcx, rax
0x18001fc18  jnz     loc_18001FDBC
0x18001fc1e  mov     rcx, [rbx]
0x18001fc21  mov     rax, [rcx+120h]
0x18001fc28  xor     edx, edx
0x18001fc2a  mov     rcx, rbx
0x18001fc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc32  mov     eax, 80041016h
0x18001fc37  jmp     short loc_18001FBD6
0x18001fc39  mov     rdx, [rsp+88h+var_38]
0x18001fc3e  mov     rcx, [rsp+88h+var_48]
0x18001fc43  mov     rax, [rsp+88h+var_40]
0x18001fc48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc4d  jmp     loc_18001FBC0
0x18001fc52  mov     ecx, [rdx]
0x18001fc54  cmp     rdx, r15
0x18001fc57  jnz     short loc_18001FCB7
0x18001fc59  mov     rdx, [rdi]
0x18001fc5c  sub     rdx, 4; Src
0x18001fc60  mov     eax, r12d
0x18001fc63  lea     r8d, [rax+4]
0x18001fc67  add     r8d, ecx; Size
0x18001fc6a  mov     rcx, r14; void *
0x18001fc6d  call    memmove_0
0x18001fc72  cmp     [rdi+8], r15
0x18001fc76  jnz     short loc_18001FCBE
0x18001fc78  lea     rax, [r14+4]
0x18001fc7c  mov     [rdi], rax
0x18001fc7f  jmp     loc_18001FAFF
0x18001fc84  mov     r8d, [rbx+0F0h]; Size
0x18001fc8b  mov     rcx, r14; void *
0x18001fc8e  call    memmove_0
0x18001fc93  mov     eax, [rbx+0E8h]
0x18001fc99  sub     eax, [rbx+0E0h]
0x18001fc9f  mov     [rbx+0E0h], r14
0x18001fca6  cdqe
0x18001fca8  add     rax, r14
0x18001fcab  mov     [rbx+0E8h], rax
0x18001fcb2  jmp     loc_18001FA85
0x18001fcb7  mov     eax, 8
0x18001fcbc  jmp     short loc_18001FC63
0x18001fcbe  mov     [rdi+8], r14
0x18001fcc2  lea     rax, [r14+0Ch]
0x18001fcc6  jmp     short loc_18001FC7C
0x18001fcc8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fcce  mov     edx, 80041006h
0x18001fcd3  mov     rcx, rax
0x18001fcd6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fcdc  lea     rax, WPP_GLOBAL_Control
0x18001fce3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcea  cmp     rcx, rax
0x18001fced  jnz     loc_18001FFB3
0x18001fcf3  mov     rax, [rbx]
0x18001fcf6  xor     edx, edx
0x18001fcf8  mov     rcx, rbx
0x18001fcfb  mov     rax, [rax+120h]
0x18001fd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd07  mov     eax, 80041006h
0x18001fd0c  jmp     loc_18001FBD6
0x18001fd11  mov     r8d, [rdi]; Size
0x18001fd14  mov     rcx, r14; void *
0x18001fd17  call    memmove_0
0x18001fd1c  lea     rcx, [r14+4]
0x18001fd20  mov     [rbx+110h], rcx
0x18001fd27  jmp     loc_18001FAAE
0x18001fd2c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fd32  mov     edx, 80041008h
0x18001fd37  mov     rcx, rax
0x18001fd3a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fd40  lea     rax, WPP_GLOBAL_Control
0x18001fd47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd4e  cmp     rcx, rax
0x18001fd51  jnz     short loc_18001FD93
0x18001fd53  mov     rcx, [rbx]
0x18001fd56  mov     rax, [rcx+120h]
0x18001fd5d  xor     edx, edx
0x18001fd5f  mov     rcx, rbx
0x18001fd62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd67  mov     eax, 80041008h
0x18001fd6c  jmp     loc_18001FBD6
0x18001fd71  movsxd  r8, dword ptr [r14]; Size
0x18001fd74  mov     rdx, rax; Src
0x18001fd77  mov     rcx, rdi; void *
0x18001fd7a  call    memmove_0
0x18001fd7f  mov     [rbx+158h], rdi
0x18001fd86  jmp     loc_18001FAD1
0x18001fd8b  mov     r14, r12
0x18001fd8e  jmp     loc_18001FB75
0x18001fd93  test    byte ptr [rcx+1Ch], 1
0x18001fd97  jz      short loc_18001FD53
0x18001fd99  cmp     byte ptr [rcx+19h], 2
0x18001fd9d  jb      short loc_18001FD53
0x18001fd9f  mov     edx, 2Bh ; '+'
0x18001fda4  mov     r9d, 80041008h
0x18001fdaa  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001fdb1  mov     rcx, [rcx+10h]
0x18001fdb5  call    WPP_SF_d
0x18001fdba  jmp     short loc_18001FD53
0x18001fdbc  test    byte ptr [rcx+1Ch], 1
0x18001fdc0  jz      loc_18001FC1E
0x18001fdc6  cmp     byte ptr [rcx+19h], 2
0x18001fdca  jb      loc_18001FC1E
0x18001fdd0  mov     edx, 2Ch ; ','
0x18001fdd5  mov     r9d, 80041016h
0x18001fddb  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001fde2  mov     rcx, [rcx+10h]
0x18001fde6  call    WPP_SF_d
0x18001fdeb  jmp     loc_18001FC1E
0x18001fdf0  mov     [rsp+88h+var_50], 1
0x18001fdf5  mov     rdx, r15; unsigned __int8 *
0x18001fdf8  lea     rcx, [r14+48h]; this
0x18001fdfc  call    ?SetData@CDecorationPart@@QEAAXPEAE@Z; CDecorationPart::SetData(uchar *)
0x18001fe01  lea     rcx, [r14+48h]
0x18001fe05  call    ??$EndOf@VCDecorationPart@@@@YAPEAEAEAVCDecorationPart@@@Z; EndOf<CDecorationPart>(CDecorationPart &)
0x18001fe0a  mov     rcx, [rbx+0D8h]
0x18001fe11  movsxd  rdx, dword ptr [rcx]
0x18001fe14  lea     r9, [rbx+190h]; struct CClassPart *
0x18001fe1b  lea     r8, [r14+98h]; struct CInstancePartContainer *
0x18001fe22  lea     rcx, [r14+0B0h]; this
0x18001fe29  mov     [rsp+88h+pExceptionObject], rdx; pExceptionObject
0x18001fe2e  mov     rdx, rax; unsigned __int8 *
0x18001fe31  call    ?SetData@CInstancePart@@QEAAXPEAEPEAVCInstancePartContainer@@AEAVCClassPart@@_K@Z; CInstancePart::SetData(uchar *,CInstancePartContainer *,CClassPart &,unsigned __int64)
0x18001fe36  mov     dword ptr [r14+3Ch], 3
0x18001fe3e  mov     rax, [r14]
0x18001fe41  mov     rdx, [rbx+40h]
0x18001fe45  mov     rcx, r14
0x18001fe48  mov     rax, [rax+250h]
0x18001fe4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe54  mov     edi, eax
0x18001fe56  test    eax, eax
0x18001fe58  js      short loc_18001FE73
0x18001fe5a  mov     eax, [rbx+3Ch]
0x18001fe5d  mov     [r14+3Ch], eax
0x18001fe61  mov     eax, [rbx+0A8h]
0x18001fe67  mov     [r14+0A8h], eax
0x18001fe6e  jmp     loc_18001FB89
0x18001fe73  mov     rcx, [r14]
0x18001fe76  mov     rax, [rcx+350h]
0x18001fe7d  mov     edx, 1
0x18001fe82  mov     rcx, r14
0x18001fe85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe8a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001fe90  mov     edx, edi
0x18001fe92  mov     rcx, rax
0x18001fe95  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001fe9b  lea     rax, WPP_GLOBAL_Control
0x18001fea2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fea9  cmp     rcx, rax
0x18001feac  jz      short loc_18001FED3
0x18001feae  test    byte ptr [rcx+1Ch], 1
0x18001feb2  jz      short loc_18001FED3
0x18001feb4  cmp     byte ptr [rcx+19h], 2
0x18001feb8  jb      short loc_18001FED3
0x18001feba  mov     edx, 2Dh ; '-'
0x18001febf  mov     r9d, edi
0x18001fec2  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18001fec9  mov     rcx, [rcx+10h]
0x18001fecd  call    WPP_SF_d
0x18001fed2  nop
0x18001fed3  cmp     [rsp+88h+var_50], 0
0x18001fed8  jz      short loc_18001FEF5
0x18001feda  mov     rax, [rbx]
0x18001fedd  xor     edx, edx
0x18001fedf  mov     rcx, rbx
0x18001fee2  mov     rax, [rax+120h]
0x18001fee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feee  mov     eax, edi
0x18001fef0  jmp     loc_18001FBD6
0x18001fef5  mov     rdx, [rsp+88h+var_38]
0x18001fefa  mov     rcx, [rsp+88h+var_48]
0x18001feff  mov     rax, [rsp+88h+var_40]
0x18001ff04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff09  jmp     short loc_18001FEDA
0x18001ff0b  test    al, 8
0x18001ff0d  jz      short loc_18001FF35
0x18001ff0f  mov     [rsp+88h+var_50], 1
0x18001ff14  mov     rax, [r14]
0x18001ff17  mov     r8d, [rbx+0A8h]
0x18001ff1e  mov     rdx, r15
0x18001ff21  mov     rcx, r14
0x18001ff24  mov     rax, [rax+480h]
  ... truncated ...
```
