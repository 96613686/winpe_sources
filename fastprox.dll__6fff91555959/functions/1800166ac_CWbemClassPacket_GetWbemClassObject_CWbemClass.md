# CWbemClassPacket::GetWbemClassObject(CWbemClass * *)

- ea: `0x1800166ac`
- end: `0x1800168c6`
- name: `?GetWbemClassObject@CWbemClassPacket@@QEAAJPEAPEAVCWbemClass@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(CWbemClassPacket *__hidden this, struct CWbemClass **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800158e0`
- `0x180062c60`

## callees

- `0x1800166ac`
- `0x180017e20`
- `0x180018ab0`
- `0x180020440`
- `0x180035b08`
- `0x180037120`
- `0x18006fa4c`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800167da`
- `wbemcomn!GetMemLogObject` at `0x1800167f4`
- `wbemcomn!GetMemLogObject` at `0x180016836`
- `wbemcomn!GetMemLogObject` at `0x1800167da`
- `wbemcomn!GetMemLogObject` at `0x1800167f4`
- `wbemcomn!GetMemLogObject` at `0x180016836`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800167e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016804`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016844`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800167e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016804`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180016844`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800166e2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800166e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemClassPacket::GetWbemClassObject(CWbemClassPacket *this, struct CWbemClass **a2)
{
  unsigned int v4; // ebx
  CWbemClass *v5; // rax
  struct CWbemClass *v6; // rdi
  unsigned int v7; // eax
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rbp
  CWbemRefreshingSvc *v10; // rcx
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *MemLogObject; // rax
  CWbemClass *pExceptionObject; // [rsp+48h] [rbp+10h] BYREF
  struct CWbemClass *v18; // [rsp+50h] [rbp+18h]

  if ( a2 )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = -2147217402;
      v5 = (CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x360u);
      pExceptionObject = v5;
      if ( v5 )
        v6 = CWbemClass::CWbemClass(v5);
      else
        v6 = 0;
      if ( v6 )
      {
        v18 = v6;
        v7 = *((_DWORD *)this + 6);
        if ( v7 < 8 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
              "SafeIntException(ERROR_INVALID_DATA)");
          }
          LODWORD(pExceptionObject) = 13;
          throw (SafeIntException *)&pExceptionObject;
        }
        CWbemClass::ValidateBuffer((unsigned __int8 *)(*((_QWORD *)this + 2) + 8LL), v7 - 8);
        v8 = CBasicBlobControl::sAllocate(*(_DWORD *)(*((_QWORD *)this + 2) + 4LL));
        v9 = v8;
        if ( v8 )
        {
          memcpy_0(
            v8,
            (const void *)(*((_QWORD *)this + 2) + **((unsigned int **)this + 2)),
            *(unsigned int *)(*((_QWORD *)this + 2) + 4LL));
          (*(void (__fastcall **)(struct CWbemClass *, unsigned __int8 *, _QWORD))(*(_QWORD *)v6 + 1152LL))(
            v6,
            v9,
            *(unsigned int *)(*((_QWORD *)this + 2) + 4LL));
          *a2 = v6;
          (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v6 + 8LL))(v6);
          v4 = 0;
        }
        (*(void (__fastcall **)(struct CWbemClass *))(*(_QWORD *)v6 + 16LL))(v6);
        v18 = 0;
        if ( (v4 & 0x80000000) == 0 )
        {
LABEL_10:
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 19;
            v15 = v4;
            goto LABEL_27;
          }
          return v4;
        }
      }
    }
    else
    {
      v4 = -2147217386;
    }
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v4);
    goto LABEL_10;
  }
  v13 = GetMemLogObject();
  v4 = -2147217400;
  CMemoryLog::Write(v13, -2147217400);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 17;
    v15 = 2147749896LL;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v10 + 2), v14, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, v15);
  }
  return v4;
}

```

## disassembly

```asm
0x1800166ac  mov     [rsp+arg_0], rbx
0x1800166b1  mov     [rsp+arg_18], rbp
0x1800166b6  push    rsi
0x1800166b7  push    rdi
0x1800166b8  push    r14
0x1800166ba  sub     rsp, 20h
0x1800166be  mov     r14, rdx
0x1800166c1  mov     rsi, rcx
0x1800166c4  test    rdx, rdx
0x1800166c7  jz      loc_1800167F4
0x1800166cd  cmp     qword ptr [rcx+10h], 0
0x1800166d2  jz      loc_1800167D5
0x1800166d8  mov     ebx, 80041006h
0x1800166dd  mov     ecx, 360h
0x1800166e2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800166e8  mov     [rsp+38h+pExceptionObject], rax
0x1800166ed  test    rax, rax
0x1800166f0  jz      loc_1800167ED
0x1800166f6  mov     rcx, rax; this
0x1800166f9  call    ??0CWbemClass@@QEAA@XZ; CWbemClass::CWbemClass(void)
0x1800166fe  mov     rdi, rax
0x180016701  test    rdi, rdi
0x180016704  jz      loc_1800167DA
0x18001670a  mov     [rsp+38h+arg_10], rdi
0x18001670f  mov     eax, [rsi+18h]
0x180016712  cmp     eax, 8
0x180016715  jb      loc_180016836
0x18001671b  add     eax, 0FFFFFFF8h
0x18001671e  mov     edx, eax; unsigned __int64
0x180016720  mov     rcx, [rsi+10h]
0x180016724  add     rcx, 8; unsigned __int8 *
0x180016728  call    ?ValidateBuffer@CWbemClass@@SA_KPEAE_K@Z; CWbemClass::ValidateBuffer(uchar *,unsigned __int64)
0x18001672d  mov     rcx, [rsi+10h]
0x180016731  mov     ecx, [rcx+4]; int
0x180016734  call    ?sAllocate@CBasicBlobControl@@SAPEAEH@Z; CBasicBlobControl::sAllocate(int)
0x180016739  mov     rbp, rax
0x18001673c  test    rax, rax
0x18001673f  jz      short loc_180016787
0x180016741  mov     rcx, [rsi+10h]
0x180016745  mov     r8d, [rcx+4]; Size
0x180016749  mov     edx, [rcx]
0x18001674b  add     rdx, rcx; Src
0x18001674e  mov     rcx, rax; void *
0x180016751  call    memcpy_0
0x180016756  mov     rcx, [rdi]
0x180016759  mov     r8, [rsi+10h]
0x18001675d  mov     rax, [rcx+480h]
0x180016764  mov     r8d, [r8+4]
0x180016768  mov     rdx, rbp
0x18001676b  mov     rcx, rdi
0x18001676e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016773  mov     [r14], rdi
0x180016776  mov     rax, [rdi]
0x180016779  mov     rcx, rdi
0x18001677c  mov     rax, [rax+8]
0x180016780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016785  xor     ebx, ebx
0x180016787  mov     rax, [rdi]
0x18001678a  mov     rcx, rdi
0x18001678d  mov     rax, [rax+10h]
0x180016791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016796  mov     [rsp+38h+arg_10], 0
0x18001679f  test    ebx, ebx
0x1800167a1  js      short loc_1800167DA
0x1800167a3  lea     rax, WPP_GLOBAL_Control
0x1800167aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167b1  cmp     rcx, rax
0x1800167b4  jz      short loc_1800167C0
0x1800167b6  test    byte ptr [rcx+1Ch], 1
0x1800167ba  jnz     loc_18001689F
0x1800167c0  mov     eax, ebx
0x1800167c2  mov     rbx, [rsp+38h+arg_0]
0x1800167c7  mov     rbp, [rsp+38h+arg_18]
0x1800167cc  add     rsp, 20h
0x1800167d0  pop     r14
0x1800167d2  pop     rdi
0x1800167d3  pop     rsi
0x1800167d4  retn
0x1800167d5  mov     ebx, 80041016h
0x1800167da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800167e0  mov     edx, ebx
0x1800167e2  mov     rcx, rax
0x1800167e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800167eb  jmp     short loc_1800167A3
0x1800167ed  xor     edi, edi
0x1800167ef  jmp     loc_180016701
0x1800167f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800167fa  mov     ebx, 80041008h
0x1800167ff  mov     edx, ebx
0x180016801  mov     rcx, rax
0x180016804  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001680a  lea     rax, WPP_GLOBAL_Control
0x180016811  mov     rcx, cs:WPP_GLOBAL_Control
0x180016818  cmp     rcx, rax
0x18001681b  jz      short loc_1800167C0
0x18001681d  test    byte ptr [rcx+1Ch], 1
0x180016821  jz      short loc_1800167C0
0x180016823  cmp     byte ptr [rcx+19h], 2
0x180016827  jb      short loc_1800167C0
0x180016829  mov     edx, 11h
0x18001682e  mov     r9d, 80041008h
0x180016834  jmp     short loc_1800168B1
0x180016836  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001683c  mov     edx, 0FFFFFFFEh
0x180016841  mov     rcx, rax
0x180016844  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001684a  lea     rax, WPP_GLOBAL_Control
0x180016851  mov     rcx, cs:WPP_GLOBAL_Control
0x180016858  cmp     rcx, rax
0x18001685b  jz      short loc_180016885
0x18001685d  test    byte ptr [rcx+1Ch], 1
0x180016861  jz      short loc_180016885
0x180016863  cmp     byte ptr [rcx+19h], 2
0x180016867  jb      short loc_180016885
0x180016869  mov     edx, 12h
0x18001686e  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180016875  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001687c  mov     rcx, [rcx+10h]
0x180016880  call    WPP_SF_s
0x180016885  mov     dword ptr [rsp+38h+pExceptionObject], 0Dh
0x18001688d  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180016894  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180016899  call    _CxxThrowException_0
0x18001689f  cmp     byte ptr [rcx+19h], 2
0x1800168a3  jb      loc_1800167C0
0x1800168a9  mov     edx, 13h
0x1800168ae  mov     r9d, ebx
0x1800168b1  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800168b8  mov     rcx, [rcx+10h]
0x1800168bc  call    WPP_SF_d
0x1800168c1  jmp     loc_1800167C0
```
