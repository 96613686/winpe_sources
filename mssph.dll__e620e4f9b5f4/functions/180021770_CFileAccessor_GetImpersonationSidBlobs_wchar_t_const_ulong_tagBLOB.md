# CFileAccessor::GetImpersonationSidBlobs(wchar_t const *,ulong *,tagBLOB * *)

- ea: `0x180021770`
- end: `0x18002192c`
- name: `?GetImpersonationSidBlobs@CFileAccessor@@UEAAJPEB_WPEAKPEAPEAUtagBLOB@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CFileAccessor *__hidden this, const wchar_t *, unsigned int *, struct tagBLOB **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003110`
- `0x180005a50`
- `0x18000c164`
- `0x18001ea7c`
- `0x180021770`
- `0x1800219a0`
- `0x180021f14`
- `0x180023aac`
- `0x180024bec`
- `0x180024c74`
- `0x180024ce4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800218ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800218ad`
- `efswrt!FreeIdentityProtectorList` at `0x180021909`
- `efswrt!FreeIdentityProtectorList` at `0x180021909`
- `efswrt!QueryIdentityProtectors` at `0x180021830`
- `efswrt!QueryIdentityProtectors` at `0x180021830`

## pseudocode

```c
__int64 __fastcall CFileAccessor::GetImpersonationSidBlobs(
        CFileAccessor *this,
        const wchar_t *a2,
        unsigned int *a3,
        struct tagBLOB **a4)
{
  int CanAccessAndDecrypt; // r14d
  int v9; // eax
  void *v10; // rbx
  DWORD LengthSid; // eax
  const unsigned __int8 *v12; // rdx
  struct tagBLOB *v13; // rbx
  int v15; // [rsp+20h] [rbp-48h]
  CSidBlob *v16; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v19; // [rsp+88h] [rbp+20h] BYREF

  if ( !*((_DWORD *)this + 234)
    || (*((_DWORD *)this + 226) & 0x4000) == 0
    || !*((_DWORD *)this + 235)
    || CFileAccessor::IsFileFANCIOrSuperHidden(this) )
  {
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  }
  if ( !*((_QWORD *)this + 116) )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  *a3 = 0;
  *a4 = 0;
  if ( (unsigned int)CFileAccessor::IsOplockBroken(this) )
  {
    CanAccessAndDecrypt = -2147024864;
LABEL_20:
    CFileAccessor::Reset(this);
    return (unsigned int)CanAccessAndDecrypt;
  }
  if ( IsCDPLEnabled() )
  {
    v19 = 0;
    v9 = QueryIdentityProtectors(a2, &v19);
    CanAccessAndDecrypt = v9;
    if ( v9 >= 0 )
    {
      if ( *(_DWORD *)v19 )
      {
        if ( *(_DWORD *)v19 != 1 )
          MicrosoftTelemetryAssertTriggeredNoArgs(retaddr);
        try
        {
          v16 = 0;
          v17 = 0;
          CSidContainer::Allocate((CSidContainer *)&v16, 1u);
          v10 = *(void **)(**(_QWORD **)(v19 + 8) + 8LL);
          LengthSid = GetLengthSid(v10);
          v12 = (const unsigned __int8 *)v10;
          v13 = (struct tagBLOB *)v16;
          CSidBlob::InitDeepCopy(v16, v12, LengthSid);
          *a4 = v13;
          *a3 = v17;
          v16 = 0;
          v17 = 0;
          CSidContainer::FreeBlobs((CSidContainer *)&v16);
        }
        catch ( ... )
        {
          indexer::result::details::result_from_caught_exception<1>(
            retaddr,
            404,
            "onecoreuap\\base\\appmodel\\search\\mssph\\file\\fileacc.cxx");
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssph\\file\\fileacc.cxx",
        (const char *)(unsigned int)v9,
        v15);
    }
    if ( v19 )
      FreeIdentityProtectorList();
  }
  else
  {
    CanAccessAndDecrypt = CFileAccessor::GetUsersWhoCanAccessAndDecrypt(
                            (CFileHandler **)this,
                            a2,
                            *((void **)this + 116),
                            a3,
                            a4);
  }
  if ( CanAccessAndDecrypt < 0 )
    goto LABEL_20;
  return (unsigned int)CanAccessAndDecrypt;
}

```

## disassembly

```asm
0x180021770  mov     [rsp+arg_0], rcx
0x180021775  push    rbx
0x180021776  push    rsi
0x180021777  push    r12
0x180021779  push    r14
0x18002177b  push    r15
0x18002177d  sub     rsp, 40h
0x180021781  mov     r15, r9
0x180021784  mov     r12, r8
0x180021787  mov     rbx, rdx
0x18002178a  mov     rsi, rcx
0x18002178d  cmp     dword ptr [rcx+3A8h], 0
0x180021794  jz      short loc_1800217B4
0x180021796  test    dword ptr [rcx+388h], 4000h
0x1800217a0  jz      short loc_1800217B4
0x1800217a2  cmp     dword ptr [rcx+3ACh], 0
0x1800217a9  jz      short loc_1800217B4
0x1800217ab  call    ?IsFileFANCIOrSuperHidden@CFileAccessor@@AEAA_NXZ; CFileAccessor::IsFileFANCIOrSuperHidden(void)
0x1800217b0  test    al, al
0x1800217b2  jz      short loc_1800217B9
0x1800217b4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800217b9  cmp     qword ptr [rsi+3A0h], 0
0x1800217c1  jnz     short loc_1800217C8
0x1800217c3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800217c8  mov     dword ptr [r12], 0
0x1800217d0  mov     qword ptr [r15], 0
0x1800217d7  mov     rcx, rsi; this
0x1800217da  call    ?IsOplockBroken@CFileAccessor@@AEAAHXZ; CFileAccessor::IsOplockBroken(void)
0x1800217df  test    eax, eax
0x1800217e1  jz      short loc_1800217EE
0x1800217e3  mov     r14d, 80070020h
0x1800217e9  jmp     loc_180021914
0x1800217ee  call    ?IsCDPLEnabled@@YA_NXZ; IsCDPLEnabled(void)
0x1800217f3  test    al, al
0x1800217f5  jnz     short loc_180021819
0x1800217f7  mov     qword ptr [rsp+68h+var_48], r15; struct tagBLOB **
0x1800217fc  mov     r9, r12; unsigned int *
0x1800217ff  mov     r8, [rsi+3A0h]; void *
0x180021806  mov     rdx, rbx; wchar_t *
0x180021809  mov     rcx, rsi; this
0x18002180c  call    ?GetUsersWhoCanAccessAndDecrypt@CFileAccessor@@AEAAJPEB_WPEAXPEAKPEAPEAUtagBLOB@@@Z; CFileAccessor::GetUsersWhoCanAccessAndDecrypt(wchar_t const *,void *,ulong *,tagBLOB * *)
0x180021811  mov     r14d, eax
0x180021814  jmp     loc_18002190F
0x180021819  mov     [rsp+68h+arg_18], 0
0x180021825  lea     rdx, [rsp+68h+arg_18]
0x18002182d  mov     rcx, rbx
0x180021830  call    cs:__imp_QueryIdentityProtectors
0x180021836  mov     r14d, eax
0x180021839  mov     rcx, [rsp+68h]; this
0x18002183e  test    eax, eax
0x180021840  jns     short loc_18002185B
0x180021842  mov     r9d, eax; char *
0x180021845  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18002184c  mov     edx, 182h; void *
0x180021851  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021856  jmp     loc_1800218FC
0x18002185b  mov     rax, [rsp+68h+arg_18]
0x180021863  cmp     dword ptr [rax], 0
0x180021866  jbe     loc_1800218FC
0x18002186c  cmp     dword ptr [rax], 1
0x18002186f  jz      short loc_180021877
0x180021871  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021876  nop
0x180021877  mov     [rsp+68h+var_38], 0
0x180021880  mov     [rsp+68h+var_30], 0
0x180021888  mov     edx, 1; unsigned int
0x18002188d  lea     rcx, [rsp+68h+var_38]; this
0x180021892  call    ?Allocate@CSidContainer@@QEAAXK@Z; CSidContainer::Allocate(ulong)
0x180021897  mov     rax, [rsp+68h+arg_18]
0x18002189f  mov     rcx, [rax+8]
0x1800218a3  mov     rax, [rcx]
0x1800218a6  mov     rbx, [rax+8]
0x1800218aa  mov     rcx, rbx; pSid
0x1800218ad  call    cs:__imp_GetLengthSid
0x1800218b3  mov     r8d, eax; unsigned int
0x1800218b6  mov     rdx, rbx; unsigned __int8 *
0x1800218b9  mov     rbx, [rsp+68h+var_38]
0x1800218be  mov     rcx, rbx; this
0x1800218c1  call    ?InitDeepCopy@CSidBlob@@QEAAXPEBEK@Z; CSidBlob::InitDeepCopy(uchar const *,ulong)
0x1800218c6  mov     [r15], rbx
0x1800218c9  mov     eax, [rsp+68h+var_30]
0x1800218cd  mov     [r12], eax
0x1800218d1  mov     [rsp+68h+var_38], 0
0x1800218da  mov     [rsp+68h+var_30], 0
0x1800218e2  lea     rcx, [rsp+68h+var_38]; this
0x1800218e7  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x1800218ec  nop
0x1800218ed  jmp     short loc_1800218FC
0x1800218ef  mov     rsi, [rsp+68h+arg_0]
0x1800218f4  mov     r14d, [rsp+68h+arg_10]
0x1800218fc  mov     rcx, [rsp+68h+arg_18]
0x180021904  test    rcx, rcx
0x180021907  jz      short loc_18002190F
0x180021909  call    cs:__imp_FreeIdentityProtectorList
0x18002190f  test    r14d, r14d
0x180021912  jns     short loc_18002191C
0x180021914  mov     rcx, rsi; this
0x180021917  call    ?Reset@CFileAccessor@@QEAAJXZ; CFileAccessor::Reset(void)
0x18002191c  mov     eax, r14d
0x18002191f  add     rsp, 40h
0x180021923  pop     r15
0x180021925  pop     r14
0x180021927  pop     r12
0x180021929  pop     rsi
0x18002192a  pop     rbx
0x18002192b  retn
```
