# CWbemClassToIdMap::AssignClassId(CWbemObject *,_GUID *,CMemBuffer *)

- ea: `0x18003c534`
- end: `0x18003c8f6`
- name: `?AssignClassId@CWbemClassToIdMap@@QEAAJPEAVCWbemObject@@PEAU_GUID@@PEAVCMemBuffer@@@Z`
- size: `962`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct CWbemObject *, struct _GUID *, struct CMemBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b8f0`

## callees

- `0x180037120`
- `0x18003c0dc`
- `0x18003c534`
- `0x18005cb4c`
- `0x18006fa66`
- `0x180091966`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003c798`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003c798`
- `wbemcomn!GetMemLogObject` at `0x18003c86a`
- `wbemcomn!GetMemLogObject` at `0x18003c86a`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003c6d3`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003c6d3`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003c64a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18003c64a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c875`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c875`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003c843`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003c85a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003c843`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003c85a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003c759`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003c7cf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003c759`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003c7cf`

## pseudocode

```c
__int64 __fastcall CWbemClassToIdMap::AssignClassId(
        struct _RTL_CRITICAL_SECTION *this,
        struct CWbemObject *a2,
        struct _GUID *a3,
        struct CMemBuffer *a4)
{
  HRESULT v6; // edi
  DWORD v7; // r14d
  int v8; // eax
  void *v9; // rsi
  int v10; // r15d
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v14; // r13
  unsigned int v16; // edi
  const void *v17; // r12
  void *v18; // rax
  GUID v19; // xmm6
  CMemoryLog *MemLogObject; // rax
  void *v21; // [rsp+30h] [rbp-98h] BYREF
  __int64 v22; // [rsp+38h] [rbp-90h]
  size_t Size; // [rsp+40h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+48h] [rbp-80h]
  int v25; // [rsp+50h] [rbp-78h] BYREF
  GUID *v26; // [rsp+58h] [rbp-70h]
  char v27[8]; // [rsp+60h] [rbp-68h] BYREF
  GUID pguid; // [rsp+68h] [rbp-60h] BYREF

  v26 = a3;
  v24 = this;
  if ( !a2 || !a3 )
  {
    v6 = -2147217400;
LABEL_40:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    goto LABEL_23;
  }
  LODWORD(Size) = 0;
  v25 = 0;
  v6 = (*(__int64 (__fastcall **)(struct CWbemObject *, _QWORD, _QWORD, __int64, size_t *))(*(_QWORD *)a2 + 568LL))(
         a2,
         0,
         0,
         4,
         &Size);
  if ( v6 == -2147217348 )
  {
    v21 = 0;
    v22 = 0;
    if ( a4 )
    {
      v7 = Size;
      if ( *((_DWORD *)a4 + 2) < (unsigned int)Size )
      {
        v8 = CMemBuffer::Alloc(a4, Size);
        v7 = Size;
      }
      else
      {
        v8 = 1;
      }
      v21 = 0;
      v22 = 0;
      v9 = *(void **)a4;
      v21 = *(void **)a4;
      LODWORD(v22) = v7;
      v10 = 0;
    }
    else
    {
      v16 = Size;
      v7 = 0;
      v22 = 0;
      v10 = 0;
      v9 = CWin32DefaultArena::WbemMemAlloc((unsigned int)Size);
      v21 = v9;
      if ( v9 )
      {
        v7 = v16;
        v22 = v16 | 0x100000000LL;
        v10 = 1;
      }
      v8 = v9 != 0;
    }
    if ( !v8 )
    {
      v6 = -2147217402;
      goto LABEL_20;
    }
    v6 = (*(__int64 (__fastcall **)(struct CWbemObject *, void *, _QWORD, __int64, int *))(*(_QWORD *)a2 + 568LL))(
           a2,
           v9,
           v7,
           4,
           &v25);
    if ( v6 >= 0 )
    {
      v11 = v24;
      CInCritSec::CInCritSec((CInCritSec *)v27, v24);
      v24 = v11 + 1;
      DebugInfo = v11[1].DebugInfo;
      CriticalSection = DebugInfo->CriticalSection;
      v14 = DebugInfo;
      if ( BYTE1(CriticalSection->LockSemaphore) )
        goto LABEL_29;
      while ( 1 )
      {
        if ( LODWORD(CriticalSection[1].DebugInfo) == v7 )
        {
          if ( memcmp_0((const void *)CriticalSection->SpinCount, v9, LODWORD(CriticalSection[1].DebugInfo)) < 0 )
            goto LABEL_42;
        }
        else if ( LODWORD(CriticalSection[1].DebugInfo) < v7 )
        {
LABEL_42:
          CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->OwningThread;
          goto LABEL_14;
        }
        v14 = (PRTL_CRITICAL_SECTION_DEBUG)CriticalSection;
        CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->DebugInfo;
LABEL_14:
        if ( BYTE1(CriticalSection->LockSemaphore) )
        {
          if ( v14 == v24->DebugInfo )
            goto LABEL_29;
          if ( v7 == v14->Flags )
          {
            if ( memcmp_0(v9, *(const void **)&v14->EntryCount, v7) >= 0 )
              goto LABEL_18;
LABEL_29:
            pguid = 0;
            v6 = CoCreateGuid(&pguid);
            if ( v6 >= 0 )
            {
              if ( !a4 )
                goto LABEL_51;
              v17 = v9;
              if ( v9 && v10 )
                CWin32DefaultArena::WbemMemFree(v9);
              v22 = 0;
              v10 = 0;
              v18 = CWin32DefaultArena::WbemMemAlloc(v7);
              v9 = v18;
              v21 = v18;
              if ( v18 )
              {
                v22 = v7 | 0x100000000LL;
                memcpy_0(v18, v17, v7);
LABEL_51:
                if ( __eh34_try(-1, 0) )
                {
                  __eh34_scope_strut(0);
                  v19 = pguid;
                  *(GUID *)std::map<CMemBuffer,_GUID,std::less<CMemBuffer>,wbem_allocator<_GUID>>::operator[](v24, &v21) = v19;
                  *v26 = pguid;
                }
                if ( __eh34_catch(0) )
                {
                  if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
                  {
                    LODWORD(v24) = -2147217402;
                    v6 = -2147217402;
                    __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_18003C8E0);
                  }
                }
                v9 = v21;
                v10 = HIDWORD(v22);
              }
              else
              {
                v6 = -2147217402;
              }
            }
          }
          else
          {
            if ( v7 < v14->Flags )
              goto LABEL_29;
LABEL_18:
            v6 = -2147217407;
          }
          CInCritSec::~CInCritSec((CInCritSec *)v27);
          break;
        }
      }
    }
LABEL_20:
    if ( v9 && v10 )
      CWin32DefaultArena::WbemMemFree(v9);
    v21 = 0;
    v22 = 0;
  }
  if ( v6 < 0 )
    goto LABEL_40;
LABEL_23:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f53bfe3cc5f131955f941a7dc61642fc_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003c534  mov     rax, rsp
0x18003c537  push    rbx
0x18003c538  push    rsi
0x18003c539  push    rdi
0x18003c53a  push    r12
0x18003c53c  push    r13
0x18003c53e  push    r14
0x18003c540  push    r15
0x18003c542  sub     rsp, 90h
0x18003c549  movaps  xmmword ptr [rax-48h], xmm6
0x18003c54d  mov     rax, cs:__security_cookie
0x18003c554  xor     rax, rsp
0x18003c557  mov     [rsp+0C8h+var_50], rax
0x18003c55c  mov     r12, r9
0x18003c55f  mov     rax, r8
0x18003c562  mov     [rsp+0C8h+var_70], rax
0x18003c567  mov     r13, rdx
0x18003c56a  mov     [rsp+0C8h+var_80], rcx
0x18003c56f  xor     ebx, ebx
0x18003c571  test    rdx, rdx
0x18003c574  jz      loc_18003C865
0x18003c57a  test    rax, rax
0x18003c57d  jz      loc_18003C865
0x18003c583  mov     dword ptr [rsp+0C8h+Size], ebx
0x18003c587  mov     [rsp+0C8h+var_78], ebx
0x18003c58b  mov     rax, [rdx]
0x18003c58e  lea     rcx, [rsp+0C8h+Size]
0x18003c593  mov     [rsp+0C8h+var_A8], rcx
0x18003c598  lea     r9d, [rbx+4]
0x18003c59c  xor     r8d, r8d
0x18003c59f  xor     edx, edx
0x18003c5a1  mov     rcx, r13
0x18003c5a4  mov     rax, [rax+238h]
0x18003c5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5b0  mov     edi, eax
0x18003c5b2  cmp     eax, 8004103Ch
0x18003c5b7  jnz     loc_18003C6F1
0x18003c5bd  mov     [rsp+0C8h+var_98], rbx
0x18003c5c2  mov     [rsp+0C8h+var_90], rbx
0x18003c5c7  test    r12, r12
0x18003c5ca  jz      loc_18003C740
0x18003c5d0  mov     r14d, dword ptr [rsp+0C8h+Size]
0x18003c5d5  cmp     [r12+8], r14d
0x18003c5da  jb      loc_18003C8C1
0x18003c5e0  lea     eax, [rbx+1]
0x18003c5e3  mov     [rsp+0C8h+var_98], rbx
0x18003c5e8  mov     [rsp+0C8h+var_90], rbx
0x18003c5ed  mov     rsi, [r12]
0x18003c5f1  mov     [rsp+0C8h+var_98], rsi
0x18003c5f6  mov     dword ptr [rsp+0C8h+var_90], r14d
0x18003c5fb  mov     r15d, ebx
0x18003c5fe  mov     dword ptr [rsp+0C8h+var_90+4], ebx
0x18003c602  test    eax, eax
0x18003c604  jz      loc_18003C8EB
0x18003c60a  mov     rax, [r13+0]
0x18003c60e  lea     rcx, [rsp+0C8h+var_78]
0x18003c613  mov     [rsp+0C8h+var_A8], rcx
0x18003c618  mov     r9d, 4
0x18003c61e  mov     r8d, r14d
0x18003c621  mov     rdx, rsi
0x18003c624  mov     rcx, r13
0x18003c627  mov     rax, [rax+238h]
0x18003c62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c633  mov     edi, eax
0x18003c635  test    eax, eax
0x18003c637  js      loc_18003C6DA
0x18003c63d  mov     rdi, [rsp+0C8h+var_80]
0x18003c642  mov     rdx, rdi
0x18003c645  lea     rcx, [rsp+0C8h+var_68]
0x18003c64a  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18003c650  nop
0x18003c651  lea     rax, [rdi+28h]
0x18003c655  mov     [rsp+0C8h+var_80], rax
0x18003c65a  mov     rax, [rax]
0x18003c65d  mov     rdi, [rax+8]
0x18003c661  mov     r13, rax
0x18003c664  cmp     [rdi+19h], bl
0x18003c667  jnz     loc_18003C78B
0x18003c66d  cmp     [rdi+28h], r14d
0x18003c671  jnz     loc_18003C880
0x18003c677  mov     r8d, [rdi+28h]; Size
0x18003c67b  mov     rdx, rsi; Buf2
0x18003c67e  mov     rcx, [rdi+20h]; Buf1
0x18003c682  call    memcmp_0
0x18003c687  test    eax, eax
0x18003c689  js      loc_18003C886
0x18003c68f  mov     r13, rdi
0x18003c692  mov     rdi, [rdi]
0x18003c695  cmp     [rdi+19h], bl
0x18003c698  jz      short loc_18003C66D
0x18003c69a  mov     rax, [rsp+0C8h+var_80]
0x18003c69f  cmp     r13, [rax]
0x18003c6a2  jz      loc_18003C78B
0x18003c6a8  cmp     r14d, [r13+28h]
0x18003c6ac  jnz     loc_18003C88F
0x18003c6b2  mov     r8d, r14d; Size
0x18003c6b5  mov     rdx, [r13+20h]; Buf2
0x18003c6b9  mov     rcx, rsi; Buf1
0x18003c6bc  call    memcmp_0
0x18003c6c1  test    eax, eax
0x18003c6c3  js      loc_18003C78B
0x18003c6c9  mov     edi, 80041001h
0x18003c6ce  lea     rcx, [rsp+0C8h+var_68]
0x18003c6d3  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18003c6d9  nop
0x18003c6da  test    rsi, rsi
0x18003c6dd  jnz     loc_18003C837
0x18003c6e3  mov     [rsp+0C8h+var_98], rbx
0x18003c6e8  mov     [rsp+0C8h+var_90], 0
0x18003c6f1  test    edi, edi
0x18003c6f3  js      loc_18003C86A
0x18003c6f9  lea     rax, WPP_GLOBAL_Control
0x18003c700  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c707  cmp     rcx, rax
0x18003c70a  jz      short loc_18003C716
0x18003c70c  test    byte ptr [rcx+1Ch], 1
0x18003c710  jnz     loc_18003C89A
0x18003c716  mov     eax, edi
0x18003c718  mov     rcx, [rsp+0C8h+var_50]
0x18003c71d  xor     rcx, rsp; StackCookie
0x18003c720  call    __security_check_cookie
0x18003c725  movaps  xmm6, [rsp+0C8h+var_48]
0x18003c72d  add     rsp, 90h
0x18003c734  pop     r15
0x18003c736  pop     r14
0x18003c738  pop     r13
0x18003c73a  pop     r12
0x18003c73c  pop     rdi
0x18003c73d  pop     rsi
0x18003c73e  pop     rbx
0x18003c73f  retn
0x18003c740  mov     edi, dword ptr [rsp+0C8h+Size]
0x18003c744  mov     [rsp+0C8h+var_98], rbx
0x18003c749  mov     r14d, ebx
0x18003c74c  mov     dword ptr [rsp+0C8h+var_90], ebx
0x18003c750  mov     r15d, ebx
0x18003c753  mov     dword ptr [rsp+0C8h+var_90+4], ebx
0x18003c757  mov     ecx, edi
0x18003c759  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003c75f  mov     rsi, rax
0x18003c762  mov     [rsp+0C8h+var_98], rax
0x18003c767  test    rax, rax
0x18003c76a  jz      short loc_18003C77E
0x18003c76c  mov     r14d, edi
0x18003c76f  mov     dword ptr [rsp+0C8h+var_90], edi
0x18003c773  mov     r15d, 1
0x18003c779  mov     dword ptr [rsp+0C8h+var_90+4], r15d
0x18003c77e  mov     eax, ebx
0x18003c780  test    rsi, rsi
0x18003c783  setnz   al
0x18003c786  jmp     loc_18003C602
0x18003c78b  xorps   xmm0, xmm0
0x18003c78e  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x18003c793  lea     rcx, [rsp+0C8h+pguid]; pguid
0x18003c798  call    cs:__imp_CoCreateGuid
0x18003c79e  mov     edi, eax
0x18003c7a0  test    eax, eax
0x18003c7a2  js      loc_18003C6CE
0x18003c7a8  test    r12, r12
0x18003c7ab  jz      short loc_18003C802
0x18003c7ad  mov     r12, rsi
0x18003c7b0  test    rsi, rsi
0x18003c7b3  jnz     loc_18003C84E
0x18003c7b9  mov     [rsp+0C8h+var_98], rbx
0x18003c7be  mov     dword ptr [rsp+0C8h+var_90], ebx
0x18003c7c2  mov     r15d, ebx
0x18003c7c5  mov     dword ptr [rsp+0C8h+var_90+4], ebx
0x18003c7c9  mov     r13d, r14d
0x18003c7cc  mov     ecx, r14d
0x18003c7cf  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003c7d5  mov     rsi, rax
0x18003c7d8  mov     [rsp+0C8h+var_98], rax
0x18003c7dd  test    rax, rax
0x18003c7e0  jz      loc_18003C8D6
0x18003c7e6  mov     dword ptr [rsp+0C8h+var_90], r14d
0x18003c7eb  mov     dword ptr [rsp+0C8h+var_90+4], 1
0x18003c7f3  mov     r8d, r13d; Size
0x18003c7f6  mov     rdx, r12; Src
0x18003c7f9  mov     rcx, rax; void *
0x18003c7fc  call    memcpy_0
0x18003c801  nop
0x18003c802  movups  xmm6, xmmword ptr [rsp+0C8h+pguid.Data1]
0x18003c807  lea     rdx, [rsp+0C8h+var_98]
0x18003c80c  mov     rcx, [rsp+0C8h+var_80]
0x18003c811  call    ??A?$map@VCMemBuffer@@U_GUID@@U?$less@VCMemBuffer@@@std@@V?$wbem_allocator@U_GUID@@@@@std@@QEAAAEAU_GUID@@AEBVCMemBuffer@@@Z; std::map<CMemBuffer,_GUID,std::less<CMemBuffer>,wbem_allocator<_GUID>>::operator[](CMemBuffer const &)
0x18003c816  movdqu  xmmword ptr [rax], xmm6
0x18003c81a  movups  xmm0, xmmword ptr [rsp+0C8h+pguid.Data1]
0x18003c81f  mov     rax, [rsp+0C8h+var_70]
0x18003c824  movdqu  xmmword ptr [rax], xmm0
0x18003c828  mov     rsi, [rsp+0C8h+var_98]
0x18003c82d  mov     r15d, dword ptr [rsp+0C8h+var_90+4]
0x18003c832  jmp     loc_18003C6CE
0x18003c837  test    r15d, r15d
0x18003c83a  jz      loc_18003C6E3
0x18003c840  mov     rcx, rsi
0x18003c843  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003c849  jmp     loc_18003C6E3
0x18003c84e  test    r15d, r15d
0x18003c851  jz      loc_18003C7B9
0x18003c857  mov     rcx, rsi
0x18003c85a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003c860  jmp     loc_18003C7B9
0x18003c865  mov     edi, 80041008h
0x18003c86a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003c870  mov     edx, edi
0x18003c872  mov     rcx, rax
0x18003c875  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c87b  jmp     loc_18003C6F9
0x18003c880  jnb     loc_18003C68F
0x18003c886  mov     rdi, [rdi+10h]
0x18003c88a  jmp     loc_18003C695
0x18003c88f  jnb     loc_18003C6C9
0x18003c895  jmp     loc_18003C78B
0x18003c89a  cmp     byte ptr [rcx+19h], 2
0x18003c89e  jb      loc_18003C716
0x18003c8a4  mov     edx, 0Bh
0x18003c8a9  mov     r9d, edi
0x18003c8ac  lea     r8, WPP_f53bfe3cc5f131955f941a7dc61642fc_Traceguids
0x18003c8b3  mov     rcx, [rcx+10h]
0x18003c8b7  call    WPP_SF_d
0x18003c8bc  jmp     loc_18003C716
0x18003c8c1  mov     edx, r14d; unsigned int
0x18003c8c4  mov     rcx, r12; this
0x18003c8c7  call    ?Alloc@CMemBuffer@@QEAAHK@Z; CMemBuffer::Alloc(ulong)
0x18003c8cc  mov     r14d, dword ptr [rsp+0C8h+Size]
0x18003c8d1  jmp     loc_18003C5E3
0x18003c8d6  mov     edi, 80041006h
0x18003c8db  jmp     loc_18003C6CE
0x18003c8e0  xor     ebx, ebx
0x18003c8e2  mov     edi, dword ptr [rsp+0C8h+var_80]
0x18003c8e6  jmp     loc_18003C828
0x18003c8eb  mov     edi, 80041006h
0x18003c8f0  jmp     loc_18003C6DA
```
