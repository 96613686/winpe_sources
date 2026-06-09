# CWbemInstancePacket::GetWbemInstanceObject(CWbemInstance * *,_GUID &)

- ea: `0x180015590`
- end: `0x1800158d2`
- name: `?GetWbemInstanceObject@CWbemInstancePacket@@QEAAJPEAPEAVCWbemInstance@@AEAU_GUID@@@Z`
- size: `834`
- prototype: `__int64 __fastcall(CWbemInstancePacket *__hidden this, struct CWbemInstance **, struct _GUID *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800150c0`
- `0x1800158e0`
- `0x180017910`

## callees

- `0x180013e80`
- `0x180015590`
- `0x180035b08`
- `0x180037120`
- `0x18006fa4c`
- `0x18006fa66`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015757`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015757`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001563c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001563c`
- `wbemcomn!GetMemLogObject` at `0x18001570f`
- `wbemcomn!GetMemLogObject` at `0x180015722`
- `wbemcomn!GetMemLogObject` at `0x18001577a`
- `wbemcomn!GetMemLogObject` at `0x180015803`
- `wbemcomn!GetMemLogObject` at `0x18001570f`
- `wbemcomn!GetMemLogObject` at `0x180015722`
- `wbemcomn!GetMemLogObject` at `0x18001577a`
- `wbemcomn!GetMemLogObject` at `0x180015803`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001571a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001572e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015788`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015811`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001571a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001572e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015788`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180015811`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800155cd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800155cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemInstancePacket::GetWbemInstanceObject(
        CWbemInstancePacket *this,
        struct CWbemInstance **a2,
        struct _GUID *a3)
{
  int v6; // esi
  CWbemInstance *v7; // rax
  struct CWbemInstance *v8; // rbx
  int v9; // ecx
  void *v10; // rax
  void *v11; // rbp
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *MemLogObject; // rax
  CWbemInstance *pExceptionObject; // [rsp+78h] [rbp+10h] BYREF
  struct CWbemInstance *v18; // [rsp+88h] [rbp+20h]

  if ( a2 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      v6 = -2147217402;
      v7 = (CWbemInstance *)CWin32DefaultArena::WbemMemAlloc(0x2A0u);
      pExceptionObject = v7;
      if ( v7 )
        v8 = CWbemInstance::CWbemInstance(v7);
      else
        v8 = 0;
      if ( v8 )
      {
        v18 = v8;
        if ( *((_DWORD *)this + 8) < 0x18u )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
              "SafeIntException(ERROR_INVALID_DATA)");
          }
          LODWORD(pExceptionObject) = 13;
          throw (SafeIntException *)&pExceptionObject;
        }
        v9 = *(_DWORD *)(*((_QWORD *)this + 3) + 4LL);
        if ( v9 < 0 )
        {
          LODWORD(pExceptionObject) = 87;
          throw (SafeIntException *)&pExceptionObject;
        }
        if ( v9 + 4 < (unsigned int)v9 )
        {
          LODWORD(pExceptionObject) = 534;
          throw (SafeIntException *)&pExceptionObject;
        }
        v10 = HeapAlloc(CBasicBlobControl::m_Heap, 0, (unsigned int)(v9 + 4));
        v11 = v10;
        if ( v10 )
        {
          memcpy_0(
            v10,
            (const void *)(*((_QWORD *)this + 3) + **((unsigned int **)this + 3)),
            *(unsigned int *)(*((_QWORD *)this + 3) + 4LL));
          v6 = (*(__int64 (__fastcall **)(CWbemInstancePacket *, struct CWbemInstance *, void *, _QWORD))(*(_QWORD *)this + 16LL))(
                 this,
                 v8,
                 v11,
                 *(unsigned int *)(*((_QWORD *)this + 3) + 4LL));
          if ( v6 < 0 )
          {
            v14 = GetMemLogObject();
            CMemoryLog::Write(v14, v6);
            if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
                (unsigned int)v6);
            }
            HeapFree(CBasicBlobControl::m_Heap, 0, v11);
            (*(void (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)v8 + 16LL))(v8);
            v18 = 0;
            return (unsigned int)v6;
          }
          (*(void (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)v8 + 8LL))(v8);
          *a3 = *(struct _GUID *)(*((_QWORD *)this + 3) + 8LL);
          *a2 = v8;
          v6 = 0;
        }
        (*(void (__fastcall **)(struct CWbemInstance *))(*(_QWORD *)v8 + 16LL))(v8);
        v18 = 0;
        if ( v6 >= 0 )
        {
LABEL_13:
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
              (unsigned int)v6);
          }
          return (unsigned int)v6;
        }
      }
    }
    else
    {
      v6 = -2147217386;
    }
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v6);
    goto LABEL_13;
  }
  v15 = GetMemLogObject();
  CMemoryLog::Write(v15, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x180015590  mov     [rsp+arg_0], rbx
0x180015595  mov     [rsp+arg_10], rbp
0x18001559a  push    rsi
0x18001559b  push    rdi
0x18001559c  push    r12
0x18001559e  push    r14
0x1800155a0  push    r15
0x1800155a2  sub     rsp, 40h
0x1800155a6  mov     r15, r8
0x1800155a9  mov     r14, rdx
0x1800155ac  mov     rdi, rcx
0x1800155af  test    rdx, rdx
0x1800155b2  jz      loc_18001577A
0x1800155b8  cmp     qword ptr [rcx+18h], 0
0x1800155bd  jz      loc_18001570A
0x1800155c3  mov     esi, 80041006h
0x1800155c8  mov     ecx, 2A0h
0x1800155cd  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800155d3  mov     [rsp+68h+pExceptionObject], rax
0x1800155d8  xor     r12d, r12d
0x1800155db  test    rax, rax
0x1800155de  jz      loc_1800157FB
0x1800155e4  mov     rcx, rax; this
0x1800155e7  call    ??0CWbemInstance@@QEAA@XZ; CWbemInstance::CWbemInstance(void)
0x1800155ec  mov     rbx, rax
0x1800155ef  test    rbx, rbx
0x1800155f2  jz      loc_18001570F
0x1800155f8  mov     [rsp+68h+arg_18], rbx
0x180015600  cmp     dword ptr [rdi+20h], 18h
0x180015604  jb      loc_180015803
0x18001560a  mov     rax, [rdi+18h]
0x18001560e  mov     ecx, [rax+4]
0x180015611  test    ecx, ecx
0x180015613  js      loc_18001586C
0x180015619  cmp     ecx, 7FFFFFFFh
0x18001561f  ja      loc_1800156B6
0x180015625  lea     eax, [rcx+4]
0x180015628  cmp     eax, ecx
0x18001562a  jb      loc_180015886
0x180015630  mov     r8d, eax; dwBytes
0x180015633  xor     edx, edx; dwFlags
0x180015635  mov     rcx, cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A; hHeap
0x18001563c  call    cs:__imp_HeapAlloc
0x180015642  mov     rbp, rax
0x180015645  test    rax, rax
0x180015648  jz      short loc_1800156B6
0x18001564a  mov     [rsp+68h+var_38], rax
0x18001564f  mov     [rsp+68h+var_30], 0
0x180015654  mov     rcx, [rdi+18h]
0x180015658  mov     r8d, [rcx+4]; Size
0x18001565c  mov     edx, [rcx]
0x18001565e  add     rdx, rcx; Src
0x180015661  mov     rcx, rax; void *
0x180015664  call    memcpy_0
0x180015669  mov     rax, [rdi]
0x18001566c  mov     r9, [rdi+18h]
0x180015670  mov     r9d, [r9+4]
0x180015674  mov     r8, rbp
0x180015677  mov     rdx, rbx
0x18001567a  mov     rcx, rdi
0x18001567d  mov     rax, [rax+10h]
0x180015681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015686  mov     esi, eax
0x180015688  test    eax, eax
0x18001568a  js      loc_180015722
0x180015690  mov     rax, [rbx]
0x180015693  mov     rcx, rbx
0x180015696  mov     rax, [rax+8]
0x18001569a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001569f  mov     [rsp+68h+var_30], 1
0x1800156a4  mov     rax, [rdi+18h]
0x1800156a8  movups  xmm0, xmmword ptr [rax+8]
0x1800156ac  movups  xmmword ptr [r15], xmm0
0x1800156b0  mov     [r14], rbx
0x1800156b3  mov     esi, r12d
0x1800156b6  mov     rax, [rbx]
0x1800156b9  mov     rcx, rbx
0x1800156bc  mov     rax, [rax+10h]
0x1800156c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c5  mov     [rsp+68h+arg_18], r12
0x1800156cd  test    esi, esi
0x1800156cf  js      short loc_18001570F
0x1800156d1  lea     rax, WPP_GLOBAL_Control
0x1800156d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156df  cmp     rcx, rax
0x1800156e2  jz      short loc_1800156EE
0x1800156e4  test    byte ptr [rcx+1Ch], 1
0x1800156e8  jnz     loc_1800157AB
0x1800156ee  mov     eax, esi
0x1800156f0  mov     rbx, [rsp+68h+arg_0]
0x1800156f5  mov     rbp, [rsp+68h+arg_10]
0x1800156fd  add     rsp, 40h
0x180015701  pop     r15
0x180015703  pop     r14
0x180015705  pop     r12
0x180015707  pop     rdi
0x180015708  pop     rsi
0x180015709  retn
0x18001570a  mov     esi, 80041016h
0x18001570f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015715  mov     edx, esi
0x180015717  mov     rcx, rax
0x18001571a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015720  jmp     short loc_1800156D1
0x180015722  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015728  nop
0x180015729  mov     edx, esi
0x18001572b  mov     rcx, rax
0x18001572e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015734  lea     rax, WPP_GLOBAL_Control
0x18001573b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015742  cmp     rcx, rax
0x180015745  jnz     loc_1800158A0
0x18001574b  mov     r8, rbp; lpMem
0x18001574e  xor     edx, edx; dwFlags
0x180015750  mov     rcx, cs:?m_Heap@CBasicBlobControl@@2VCGetHeap@@A; hHeap
0x180015757  call    cs:__imp_HeapFree
0x18001575d  nop
0x18001575e  mov     rax, [rbx]
0x180015761  mov     rcx, rbx
0x180015764  mov     rax, [rax+10h]
0x180015768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576d  mov     [rsp+68h+arg_18], r12
0x180015775  jmp     loc_1800156EE
0x18001577a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015780  mov     edx, 80041008h
0x180015785  mov     rcx, rax
0x180015788  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001578e  lea     rax, WPP_GLOBAL_Control
0x180015795  mov     rcx, cs:WPP_GLOBAL_Control
0x18001579c  cmp     rcx, rax
0x18001579f  jnz     short loc_1800157D2
0x1800157a1  mov     eax, 80041008h
0x1800157a6  jmp     loc_1800156F0
0x1800157ab  cmp     byte ptr [rcx+19h], 2
0x1800157af  jb      loc_1800156EE
0x1800157b5  mov     edx, 1Dh
0x1800157ba  mov     r9d, esi
0x1800157bd  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800157c4  mov     rcx, [rcx+10h]
0x1800157c8  call    WPP_SF_d
0x1800157cd  jmp     loc_1800156EE
0x1800157d2  test    byte ptr [rcx+1Ch], 1
0x1800157d6  jz      short loc_1800157A1
0x1800157d8  cmp     byte ptr [rcx+19h], 2
0x1800157dc  jb      short loc_1800157A1
0x1800157de  mov     edx, 1Ah
0x1800157e3  mov     r9d, 80041008h
0x1800157e9  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800157f0  mov     rcx, [rcx+10h]
0x1800157f4  call    WPP_SF_d
0x1800157f9  jmp     short loc_1800157A1
0x1800157fb  mov     rbx, r12
0x1800157fe  jmp     loc_1800155EF
0x180015803  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180015809  mov     edx, 0FFFFFFFEh
0x18001580e  mov     rcx, rax
0x180015811  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015817  lea     rax, WPP_GLOBAL_Control
0x18001581e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015825  cmp     rcx, rax
0x180015828  jz      short loc_180015852
0x18001582a  test    byte ptr [rcx+1Ch], 1
0x18001582e  jz      short loc_180015852
0x180015830  cmp     byte ptr [rcx+19h], 2
0x180015834  jb      short loc_180015852
0x180015836  mov     edx, 1Bh
0x18001583b  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x180015842  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x180015849  mov     rcx, [rcx+10h]
0x18001584d  call    WPP_SF_s
0x180015852  mov     dword ptr [rsp+68h+pExceptionObject], 0Dh
0x18001585a  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180015861  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180015866  call    _CxxThrowException_0
0x18001586c  mov     dword ptr [rsp+68h+pExceptionObject], 57h ; 'W'
0x180015874  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001587b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180015880  call    _CxxThrowException_0
0x180015886  mov     dword ptr [rsp+68h+pExceptionObject], 216h
0x18001588e  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180015895  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001589a  call    _CxxThrowException_0
0x1800158a0  test    byte ptr [rcx+1Ch], 1
0x1800158a4  jz      loc_18001574B
0x1800158aa  cmp     byte ptr [rcx+19h], 2
0x1800158ae  jb      loc_18001574B
0x1800158b4  mov     edx, 1Ch
0x1800158b9  mov     r9d, esi
0x1800158bc  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x1800158c3  mov     rcx, [rcx+10h]
0x1800158c7  call    WPP_SF_d
0x1800158cc  jmp     loc_18001574B
```
