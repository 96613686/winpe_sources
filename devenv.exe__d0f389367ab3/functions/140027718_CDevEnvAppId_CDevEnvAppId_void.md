# CDevEnvAppId::CDevEnvAppId(void)

- ea: `0x140027718`
- end: `0x140027975`
- name: `??0CDevEnvAppId@@IEAA@XZ`
- size: `605`
- prototype: `CDevEnvAppId *__fastcall(CDevEnvAppId *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140027620`

## callees

- `0x140002160`
- `0x140002190`
- `0x140002c10`
- `0x140003f60`
- `0x140027718`
- `0x140027978`
- `0x140033ab0`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x140027802`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140027802`
- `KERNEL32!GetLastError` at `0x14002780c`
- `KERNEL32!GetLastError` at `0x14002780c`
- `KERNEL32!DeleteCriticalSection` at `0x140027843`
- `KERNEL32!DeleteCriticalSection` at `0x140027843`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CDevEnvAppId *__fastcall CDevEnvAppId::CDevEnvAppId(CDevEnvAppId *this)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v3; // rax
  const unsigned __int16 *v4; // r9
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  signed int LastError; // eax
  signed int v7; // ecx
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  struct ATL::IAtlStringMgr *v9; // rax
  struct ATL::IAtlStringMgr *v10; // rax
  struct ATL::IAtlStringMgr *v11; // rax
  struct ATL::IAtlStringMgr *v12; // rax
  struct ATL::IAtlStringMgr *v13; // rax

  CAppIdExtImpl::CAppIdExtImpl((__int64)this);
  *((_QWORD *)this + 191) = &CSplash::`vftable';
  *((_BYTE *)this + 1536) = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    goto LABEL_20;
  *((_QWORD *)this + 193) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                          + 24;
  *((_BYTE *)this + 1552) = 0;
  *((_QWORD *)this + 202) = 0;
  v3 = ATL::CAtlStringMgr::GetInstance();
  if ( !v3 )
    goto LABEL_20;
  *((_QWORD *)this + 203) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v3 + 24LL))(v3) + 24;
  *((_DWORD *)this + 408) = -1;
  *((_DWORD *)this + 409) = 0;
  *((_QWORD *)this + 207) = 0;
  *((_QWORD *)this + 208) = 0;
  if ( lpCriticalSection )
  {
    ActivityLog::LogEntry(
      (ActivityLog *)1,
      (int)L"Microsoft Visual Studio Appid Stub",
      L"InitSync should be called only once",
      v4);
  }
  else
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
    if ( v5 )
    {
      *(_OWORD *)&v5->DebugInfo = 0;
      *(_OWORD *)&v5->OwningThread = 0;
      v5->SpinCount = 0;
      if ( !InitializeCriticalSectionEx(v5, 0, 0) )
      {
        LastError = GetLastError();
        v7 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v7 = LastError;
        if ( v7 < 0 )
        {
          _mm_lfence();
          ATL::AtlThrowImpl(v7);
        }
      }
    }
    else
    {
      v5 = 0;
    }
    v8 = lpCriticalSection;
    lpCriticalSection = v5;
    if ( v8 )
    {
      DeleteCriticalSection(v8);
      operator delete(v8, (const struct std::nothrow_t *)0x28);
    }
  }
  *((_QWORD *)this + 211) = 0;
  *((_BYTE *)this + 1696) = 0;
  v9 = ATL::CAtlStringMgr::GetInstance();
  if ( !v9 )
    goto LABEL_20;
  *((_QWORD *)this + 213) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v9 + 24LL))(v9) + 24;
  v10 = ATL::CAtlStringMgr::GetInstance();
  if ( !v10
    || (*((_QWORD *)this + 214) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v10 + 24LL))(v10)
                                + 24,
        (v11 = ATL::CAtlStringMgr::GetInstance()) == 0)
    || (*((_QWORD *)this + 215) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v11 + 24LL))(v11)
                                + 24,
        (v12 = ATL::CAtlStringMgr::GetInstance()) == 0)
    || (*((_QWORD *)this + 216) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v12 + 24LL))(v12)
                                + 24,
        (v13 = ATL::CAtlStringMgr::GetInstance()) == 0) )
  {
LABEL_20:
    ATL::AtlThrowImpl(-2147467259);
  }
  *((_QWORD *)this + 217) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v13 + 24LL))(v13) + 24;
  *((_QWORD *)this + 218) = &CJITHelper::`vftable';
  *((_DWORD *)this + 438) = 1;
  *((_QWORD *)this + 220) = 0;
  *((_QWORD *)this + 221) = 0;
  *((_QWORD *)this + 222) = 0;
  *((_QWORD *)this + 223) = 0;
  *((_BYTE *)this + 1792) = 0;
  return this;
}

```

## disassembly

```asm
0x140027718  mov     rax, rsp
0x14002771b  mov     [rax+10h], rbx
0x14002771f  mov     [rax+18h], rbp
0x140027723  mov     [rax+20h], rsi
0x140027727  push    rdi
0x140027728  sub     rsp, 40h
0x14002772c  mov     rbx, rcx
0x14002772f  mov     [rax-20h], rcx
0x140027733  xor     ebp, ebp
0x140027735  call    ??0CAppIdExtImpl@@QEAA@W4PIDFamily@@@Z; CAppIdExtImpl::CAppIdExtImpl(PIDFamily)
0x14002773a  lea     rdi, [rbx+5F8h]
0x140027741  mov     [rsp+48h+var_28], rdi
0x140027746  lea     rax, ??_7CSplash@@6B@; const CSplash::`vftable'
0x14002774d  mov     [rdi], rax
0x140027750  mov     [rdi+8], bpl
0x140027754  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140027759  mov     rcx, rax
0x14002775c  test    rax, rax
0x14002775f  jz      loc_14002795E
0x140027765  mov     rax, [rax]
0x140027768  call    qword ptr [rax+18h]
0x14002776b  add     rax, 18h
0x14002776f  mov     [rdi+10h], rax
0x140027773  mov     [rdi+18h], bpl
0x140027777  mov     [rdi+58h], rbp
0x14002777b  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140027780  mov     rcx, rax
0x140027783  test    rax, rax
0x140027786  jz      loc_14002795E
0x14002778c  mov     rax, [rax]
0x14002778f  call    qword ptr [rax+18h]
0x140027792  add     rax, 18h
0x140027796  mov     [rdi+60h], rax
0x14002779a  or      dword ptr [rdi+68h], 0FFFFFFFFh
0x14002779e  mov     [rdi+6Ch], ebp
0x1400277a1  mov     [rdi+80h], rbp
0x1400277a8  mov     [rdi+88h], rbp
0x1400277af  cmp     cs:lpCriticalSection, rbp
0x1400277b6  jz      short loc_1400277D3
0x1400277b8  lea     r8, aInitsyncShould; "InitSync should be called only once"
0x1400277bf  lea     rdx, aMicrosoftVisua_1; "Microsoft Visual Studio Appid Stub"
0x1400277c6  lea     ecx, [rbp+1]; this
0x1400277c9  call    ?LogEntry@ActivityLog@@YAJHPEBG0@Z; ActivityLog::LogEntry(int,ushort const *,ushort const *)
0x1400277ce  jmp     loc_140027857
0x1400277d3  mov     ecx, 28h ; '('; Size
0x1400277d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400277dd  mov     rdi, rax
0x1400277e0  mov     [rsp+48h+var_18], rax
0x1400277e5  test    rax, rax
0x1400277e8  jz      short loc_14002782A
0x1400277ea  xorps   xmm0, xmm0
0x1400277ed  xor     eax, eax
0x1400277ef  movups  xmmword ptr [rdi], xmm0
0x1400277f2  movups  xmmword ptr [rdi+10h], xmm0
0x1400277f6  mov     [rdi+20h], rax
0x1400277fa  xor     r8d, r8d; Flags
0x1400277fd  xor     edx, edx; dwSpinCount
0x1400277ff  mov     rcx, rdi; lpCriticalSection
0x140027802  call    cs:__imp_InitializeCriticalSectionEx
0x140027808  test    eax, eax
0x14002780a  jnz     short loc_14002782D
0x14002780c  call    cs:__imp_GetLastError
0x140027812  movzx   ecx, ax
0x140027815  or      ecx, 80070000h
0x14002781b  test    eax, eax
0x14002781d  cmovle  ecx, eax
0x140027820  test    ecx, ecx
0x140027822  js      loc_14002796C
0x140027828  jmp     short loc_14002782D
0x14002782a  mov     rdi, rbp
0x14002782d  mov     rsi, cs:lpCriticalSection
0x140027834  mov     cs:lpCriticalSection, rdi
0x14002783b  test    rsi, rsi
0x14002783e  jz      short loc_140027857
0x140027840  mov     rcx, rsi; lpCriticalSection
0x140027843  call    cs:__imp_DeleteCriticalSection
0x140027849  mov     edx, 28h ; '('; struct std::nothrow_t *
0x14002784e  mov     rcx, rsi; void *
0x140027851  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140027856  nop
0x140027857  mov     [rbx+698h], rbp
0x14002785e  mov     [rbx+6A0h], bpl
0x140027865  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002786a  mov     rcx, rax
0x14002786d  test    rax, rax
0x140027870  jz      loc_14002795E
0x140027876  mov     rax, [rax]
0x140027879  call    qword ptr [rax+18h]
0x14002787c  add     rax, 18h
0x140027880  mov     [rbx+6A8h], rax
0x140027887  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14002788c  mov     rcx, rax
0x14002788f  test    rax, rax
0x140027892  jz      loc_14002795E
0x140027898  mov     rax, [rax]
0x14002789b  call    qword ptr [rax+18h]
0x14002789e  add     rax, 18h
0x1400278a2  mov     [rbx+6B0h], rax
0x1400278a9  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400278ae  mov     rcx, rax
0x1400278b1  test    rax, rax
0x1400278b4  jz      loc_14002795E
0x1400278ba  mov     rax, [rax]
0x1400278bd  call    qword ptr [rax+18h]
0x1400278c0  add     rax, 18h
0x1400278c4  mov     [rbx+6B8h], rax
0x1400278cb  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400278d0  mov     rcx, rax
0x1400278d3  test    rax, rax
0x1400278d6  jz      loc_14002795E
0x1400278dc  mov     rax, [rax]
0x1400278df  call    qword ptr [rax+18h]
0x1400278e2  add     rax, 18h
0x1400278e6  mov     [rbx+6C0h], rax
0x1400278ed  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400278f2  mov     rcx, rax
0x1400278f5  test    rax, rax
0x1400278f8  jz      short loc_14002795E
0x1400278fa  mov     rax, [rax]
0x1400278fd  call    qword ptr [rax+18h]
0x140027900  add     rax, 18h
0x140027904  mov     [rbx+6C8h], rax
0x14002790b  lea     rax, ??_7CJITHelper@@6B@; const CJITHelper::`vftable'
0x140027912  mov     [rbx+6D0h], rax
0x140027919  mov     dword ptr [rbx+6D8h], 1
0x140027923  mov     [rbx+6E0h], rbp
0x14002792a  mov     [rbx+6E8h], rbp
0x140027931  mov     [rbx+6F0h], rbp
0x140027938  mov     [rbx+6F8h], rbp
0x14002793f  mov     [rbx+700h], bpl
0x140027946  mov     rax, rbx
0x140027949  mov     rbx, [rsp+48h+arg_8]
0x14002794e  mov     rbp, [rsp+48h+arg_10]
0x140027953  mov     rsi, [rsp+48h+arg_18]
0x140027958  add     rsp, 40h
0x14002795c  pop     rdi
0x14002795d  retn
0x14002795e  mov     ecx, 80004005h; int
0x140027963  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140027969  jmp     short $+2
0x14002796b  nop
0x14002796c  lfence
0x14002796f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
