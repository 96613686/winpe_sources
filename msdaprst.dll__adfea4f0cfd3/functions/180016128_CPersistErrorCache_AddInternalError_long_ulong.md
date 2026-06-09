# CPersistErrorCache::AddInternalError(long,ulong)

- ea: `0x180016128`
- end: `0x1800164d6`
- name: `?AddInternalError@CPersistErrorCache@@QEAAXJK@Z`
- size: `942`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800164dc`
- `0x180016698`

## callees

- `0x180001db8`
- `0x180002770`
- `0x180015988`
- `0x180016128`
- `0x180016764`
- `0x180016b60`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001616d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001648e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001616d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001648e`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180016189`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180016189`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CPersistErrorCache::AddInternalError(CPersistErrorCache *this, unsigned int a2, unsigned int a3)
{
  OLECHAR *v6; // rdi
  unsigned __int16 *v7; // rcx
  HRESULT v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // ebx
  unsigned __int16 *ErrorDescription; // rax
  unsigned __int16 *v15; // rbx
  int v16; // eax
  int v17; // esi
  __int64 ErrorDescriptionSDK; // rax
  int v19; // eax
  int v20; // esi
  unsigned __int16 *v21; // rax
  int v22; // eax
  int v23; // esi
  int v24; // eax
  int v25; // esi
  struct IErrorInfo *v26; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-50h]
  OLECHAR *v28; // [rsp+40h] [rbp-48h]
  __int64 v29[8]; // [rsp+48h] [rbp-40h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+A8h] [rbp+20h] BYREF

  pperrinfo = 0;
  v26 = 0;
  v29[0] = 0;
  v27 = 0;
  v6 = 0;
  v28 = 0;
  if ( a2 )
  {
    v8 = CreateErrorInfo(&pperrinfo);
    try
    {
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A88[0] )
          bidTraceW(off_1800491E8[0], 397312, off_180049A88[0], (unsigned int)v8, 388);
        ThrowHR(v9);
      }
      v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &GUID_NULL);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A80[0] )
          bidTraceW(off_1800491E8[0], 399360, off_180049A80[0], (unsigned int)v10, 390);
        ThrowHR(v11);
      }
      v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
              pperrinfo,
              L"Microsoft OLEDB Persistence Provider");
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A78[0] )
          bidTraceW(off_1800491E8[0], 400384, off_180049A78[0], (unsigned int)v12, 391);
        ThrowHR(v13);
      }
      ErrorDescription = CPersistErrorCache::GetErrorDescription(this, a2, a3);
      v15 = ErrorDescription;
      v27 = ErrorDescription;
      if ( ErrorDescription )
      {
        v16 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
                pperrinfo,
                ErrorDescription);
        v17 = v16;
        if ( v16 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049A70[0] )
            bidTraceW(off_1800491E8[0], 404480, off_180049A70[0], (unsigned int)v16, 395);
          ThrowHR(v17);
        }
      }
      else
      {
        a3 = 136;
        ErrorDescriptionSDK = GetErrorDescriptionSDK(a2);
        v6 = (OLECHAR *)ErrorDescriptionSDK;
        v28 = (OLECHAR *)ErrorDescriptionSDK;
        if ( ErrorDescriptionSDK )
        {
          v19 = ((__int64 (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetDescription)(
                  pperrinfo,
                  ErrorDescriptionSDK);
          v20 = v19;
          if ( v19 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180049A68[0] )
              bidTraceW(off_1800491E8[0], 412672, off_180049A68[0], (unsigned int)v19, 403);
            ThrowHR(v20);
          }
        }
        else
        {
          v21 = CPersistErrorCache::GetErrorDescription(this, a2, 0x88u);
          v15 = v21;
          v27 = v21;
          if ( v21 )
          {
            v22 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
                    pperrinfo,
                    v21);
            v23 = v22;
            if ( v22 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180049A60[0] )
                bidTraceW(off_1800491E8[0], 418816, off_180049A60[0], (unsigned int)v22, 409);
              ThrowHR(v23);
            }
          }
        }
      }
      v24 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, struct IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
              pperrinfo,
              &IID_IErrorInfo,
              &v26);
      v25 = v24;
      if ( v24 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A58[0] )
          bidTraceW(off_1800491E8[0], 423936, off_180049A58[0], (unsigned int)v24, 414);
        ThrowHR(v25);
      }
      CPersistErrorCache::AddError(this, a2, a3, v26);
    }
    catch ( long )
    {
      v15 = v27;
      v6 = v28;
    }
    SysFreeString(v6);
    v7 = v15;
  }
  else
  {
    SysFreeString(0);
    v7 = 0;
  }
  operator delete(v7);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v29);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v26);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
}

```

## disassembly

```asm
0x180016128  mov     rax, rsp
0x18001612b  push    rbx
0x18001612c  push    rsi
0x18001612d  push    rdi
0x18001612e  push    r12
0x180016130  push    r14
0x180016132  push    r15
0x180016134  sub     rsp, 58h
0x180016138  mov     r15d, r8d
0x18001613b  mov     r14d, edx
0x18001613e  mov     r12, rcx
0x180016141  mov     qword ptr [rax+20h], 0
0x180016149  mov     qword ptr [rax-58h], 0
0x180016151  mov     qword ptr [rax-40h], 0
0x180016159  mov     qword ptr [rax-50h], 0
0x180016161  xor     edi, edi
0x180016163  mov     [rax-48h], rdi
0x180016167  test    edx, edx
0x180016169  jnz     short loc_180016181
0x18001616b  xor     ecx, ecx; bstrString
0x18001616d  call    cs:__imp_SysFreeString
0x180016174  nop     dword ptr [rax+rax+00h]
0x180016179  nop
0x18001617a  xor     ecx, ecx
0x18001617c  jmp     loc_18001649E
0x180016181  lea     rcx, [rsp+88h+pperrinfo]; pperrinfo
0x180016189  call    cs:__imp_CreateErrorInfo
0x180016190  nop     dword ptr [rax+rax+00h]
0x180016195  mov     ebx, eax
0x180016197  test    eax, eax
0x180016199  jns     short loc_1800161DA
0x18001619b  test    byte ptr cs:_bidGblFlags, 2
0x1800161a2  jz      short loc_1800161D3
0x1800161a4  mov     rcx, cs:off_180049A88; "<CPersistErrorCache::AddInternalError|A"...
0x1800161ab  test    rcx, rcx
0x1800161ae  jz      short loc_1800161D3
0x1800161b0  mov     [rsp+88h+var_68], 184h
0x1800161b8  mov     r9d, eax
0x1800161bb  mov     r8, cs:off_180049A88; "<CPersistErrorCache::AddInternalError|A"...
0x1800161c2  mov     edx, 61000h
0x1800161c7  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800161ce  call    _bidTraceW
0x1800161d3  mov     ecx, ebx; int
0x1800161d5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800161da  mov     rcx, [rsp+88h+pperrinfo]
0x1800161e2  mov     rax, [rcx]
0x1800161e5  lea     rdx, GUID_NULL
0x1800161ec  mov     rax, [rax+18h]
0x1800161f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161f5  mov     ebx, eax
0x1800161f7  test    eax, eax
0x1800161f9  jns     short loc_18001623A
0x1800161fb  test    byte ptr cs:_bidGblFlags, 2
0x180016202  jz      short loc_180016233
0x180016204  mov     rcx, cs:off_180049A80; "<CPersistErrorCache::AddInternalError|A"...
0x18001620b  test    rcx, rcx
0x18001620e  jz      short loc_180016233
0x180016210  mov     [rsp+88h+var_68], 186h
0x180016218  mov     r9d, eax
0x18001621b  mov     r8, cs:off_180049A80; "<CPersistErrorCache::AddInternalError|A"...
0x180016222  mov     edx, 61800h
0x180016227  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001622e  call    _bidTraceW
0x180016233  mov     ecx, ebx; int
0x180016235  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001623a  mov     rcx, [rsp+88h+pperrinfo]
0x180016242  mov     rax, [rcx]
0x180016245  lea     rdx, aMicrosoftOledb; "Microsoft OLEDB Persistence Provider"
0x18001624c  mov     rax, [rax+20h]
0x180016250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016255  mov     ebx, eax
0x180016257  test    eax, eax
0x180016259  jns     short loc_18001629A
0x18001625b  test    byte ptr cs:_bidGblFlags, 2
0x180016262  jz      short loc_180016293
0x180016264  mov     rcx, cs:off_180049A78; "<CPersistErrorCache::AddInternalError|A"...
0x18001626b  test    rcx, rcx
0x18001626e  jz      short loc_180016293
0x180016270  mov     [rsp+88h+var_68], 187h
0x180016278  mov     r9d, eax
0x18001627b  mov     r8, cs:off_180049A78; "<CPersistErrorCache::AddInternalError|A"...
0x180016282  mov     edx, 61C00h
0x180016287  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001628e  call    _bidTraceW
0x180016293  mov     ecx, ebx; int
0x180016295  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001629a  mov     r8d, r15d; unsigned int
0x18001629d  mov     edx, r14d; int
0x1800162a0  mov     rcx, r12; this
0x1800162a3  call    ?GetErrorDescription@CPersistErrorCache@@AEAAPEAGJK@Z; CPersistErrorCache::GetErrorDescription(long,ulong)
0x1800162a8  mov     rbx, rax
0x1800162ab  mov     [rsp+88h+var_50], rax
0x1800162b0  test    rax, rax
0x1800162b3  jz      short loc_180016315
0x1800162b5  mov     rcx, [rsp+88h+pperrinfo]
0x1800162bd  mov     rax, [rcx]
0x1800162c0  mov     rdx, rbx
0x1800162c3  mov     rax, [rax+28h]
0x1800162c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162cc  mov     esi, eax
0x1800162ce  test    eax, eax
0x1800162d0  jns     loc_180016407
0x1800162d6  test    byte ptr cs:_bidGblFlags, 2
0x1800162dd  jz      short loc_18001630E
0x1800162df  mov     rcx, cs:off_180049A70; "<CPersistErrorCache::AddInternalError|A"...
0x1800162e6  test    rcx, rcx
0x1800162e9  jz      short loc_18001630E
0x1800162eb  mov     [rsp+88h+var_68], 18Bh
0x1800162f3  mov     r9d, eax
0x1800162f6  mov     r8, cs:off_180049A70; "<CPersistErrorCache::AddInternalError|A"...
0x1800162fd  mov     edx, 62C00h
0x180016302  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016309  call    _bidTraceW
0x18001630e  mov     ecx, esi; int
0x180016310  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016315  mov     r15d, 88h
0x18001631b  mov     ecx, r14d
0x18001631e  call    GetErrorDescriptionSDK
0x180016323  mov     rdi, rax
0x180016326  mov     [rsp+88h+var_48], rax
0x18001632b  test    rax, rax
0x18001632e  jz      short loc_180016390
0x180016330  mov     rcx, [rsp+88h+pperrinfo]
0x180016338  mov     rax, [rcx]
0x18001633b  mov     rdx, rdi
0x18001633e  mov     rax, [rax+28h]
0x180016342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016347  mov     esi, eax
0x180016349  test    eax, eax
0x18001634b  jns     loc_180016407
0x180016351  test    byte ptr cs:_bidGblFlags, 2
0x180016358  jz      short loc_180016389
0x18001635a  mov     rcx, cs:off_180049A68; "<CPersistErrorCache::AddInternalError|A"...
0x180016361  test    rcx, rcx
0x180016364  jz      short loc_180016389
0x180016366  mov     [rsp+88h+var_68], 193h
0x18001636e  mov     r9d, eax
0x180016371  mov     r8, cs:off_180049A68; "<CPersistErrorCache::AddInternalError|A"...
0x180016378  mov     edx, 64C00h
0x18001637d  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016384  call    _bidTraceW
0x180016389  mov     ecx, esi; int
0x18001638b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016390  mov     r8d, r15d; unsigned int
0x180016393  mov     edx, r14d; int
0x180016396  mov     rcx, r12; this
0x180016399  call    ?GetErrorDescription@CPersistErrorCache@@AEAAPEAGJK@Z; CPersistErrorCache::GetErrorDescription(long,ulong)
0x18001639e  mov     rbx, rax
0x1800163a1  mov     [rsp+88h+var_50], rax
0x1800163a6  test    rax, rax
0x1800163a9  jz      short loc_180016407
0x1800163ab  mov     rcx, [rsp+88h+pperrinfo]
0x1800163b3  mov     rax, [rcx]
0x1800163b6  mov     rdx, rbx
0x1800163b9  mov     rax, [rax+28h]
0x1800163bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c2  mov     esi, eax
0x1800163c4  test    eax, eax
0x1800163c6  jns     short loc_180016407
0x1800163c8  test    byte ptr cs:_bidGblFlags, 2
0x1800163cf  jz      short loc_180016400
0x1800163d1  mov     rcx, cs:off_180049A60; "<CPersistErrorCache::AddInternalError|A"...
0x1800163d8  test    rcx, rcx
0x1800163db  jz      short loc_180016400
0x1800163dd  mov     [rsp+88h+var_68], 199h
0x1800163e5  mov     r9d, eax
0x1800163e8  mov     r8, cs:off_180049A60; "<CPersistErrorCache::AddInternalError|A"...
0x1800163ef  mov     edx, 66400h
0x1800163f4  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800163fb  call    _bidTraceW
0x180016400  mov     ecx, esi; int
0x180016402  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016407  mov     rcx, [rsp+88h+pperrinfo]
0x18001640f  mov     rax, [rcx]
0x180016412  lea     r8, [rsp+88h+var_58]
0x180016417  lea     rdx, IID_IErrorInfo
0x18001641e  mov     rax, [rax]
0x180016421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016426  mov     esi, eax
0x180016428  test    eax, eax
0x18001642a  jns     short loc_18001646B
0x18001642c  test    byte ptr cs:_bidGblFlags, 2
0x180016433  jz      short loc_180016464
0x180016435  mov     rcx, cs:off_180049A58; "<CPersistErrorCache::AddInternalError|A"...
0x18001643c  test    rcx, rcx
0x18001643f  jz      short loc_180016464
0x180016441  mov     [rsp+88h+var_68], 19Eh
0x180016449  mov     r9d, eax
0x18001644c  mov     r8, cs:off_180049A58; "<CPersistErrorCache::AddInternalError|A"...
0x180016453  mov     edx, 67800h
0x180016458  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001645f  call    _bidTraceW
0x180016464  mov     ecx, esi; int
0x180016466  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001646b  mov     r9, [rsp+88h+var_58]; struct IErrorInfo *
0x180016470  mov     r8d, r15d; unsigned int
0x180016473  mov     edx, r14d; int
0x180016476  mov     rcx, r12; this
0x180016479  call    ?AddError@CPersistErrorCache@@AEAAXJKPEAUIErrorInfo@@@Z; CPersistErrorCache::AddError(long,ulong,IErrorInfo *)
0x18001647e  nop
0x18001647f  jmp     short loc_18001648B
0x180016481  mov     rbx, [rsp+88h+var_50]
0x180016486  mov     rdi, [rsp+88h+var_48]
0x18001648b  mov     rcx, rdi; bstrString
0x18001648e  call    cs:__imp_SysFreeString
0x180016495  nop     dword ptr [rax+rax+00h]
0x18001649a  nop
0x18001649b  mov     rcx, rbx; void *
0x18001649e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800164a3  nop
0x1800164a4  lea     rcx, [rsp+88h+var_40]
0x1800164a9  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800164ae  nop
0x1800164af  lea     rcx, [rsp+88h+var_58]
0x1800164b4  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800164b9  nop
0x1800164ba  lea     rcx, [rsp+88h+pperrinfo]
0x1800164c2  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800164c7  add     rsp, 58h
0x1800164cb  pop     r15
0x1800164cd  pop     r14
0x1800164cf  pop     r12
0x1800164d1  pop     rdi
0x1800164d2  pop     rsi
0x1800164d3  pop     rbx
0x1800164d4  retn
```
