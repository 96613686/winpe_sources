# CPersistErrorCache::AddHMODULEError(HINSTANCE__ *,long,ulong)

- ea: `0x180015e94`
- end: `0x18001611f`
- name: `?AddHMODULEError@CPersistErrorCache@@QEAAXPEAUHINSTANCE__@@JK@Z`
- size: `651`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this, HINSTANCE, int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180022240`

## callees

- `0x180002770`
- `0x180015988`
- `0x180015e94`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180015ee0`
- `KERNEL32!FormatMessageW` at `0x180015ee0`
- `KERNEL32!LocalFree` at `0x180016102`
- `KERNEL32!LocalFree` at `0x180016102`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180015f0b`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180015f0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPersistErrorCache::AddHMODULEError(CPersistErrorCache *this, ICreateErrorInfo *a2, DWORD a3)
{
  DWORD v5; // eax
  HRESULT v6; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int v15; // ebx
  struct IErrorInfo *v16; // [rsp+40h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-10h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+68h] [rbp+10h] BYREF

  pperrinfo = a2;
  hMem[0] = 0;
  v5 = FormatMessageW(0x900u, CPersistSession::m_hURLMON, a3, 0x400u, (LPWSTR)hMem, 0, 0);
  try
  {
    if ( v5 )
    {
      pperrinfo = 0;
      v16 = 0;
      v6 = CreateErrorInfo(&pperrinfo);
      v7 = v6;
      if ( v6 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180049AB0[0] )
            bidTraceW(off_1800491E8[0], 294912, off_180049AB0[0], (unsigned int)v6, 288);
        }
        ThrowHR(v7);
      }
      v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &GUID_NULL);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049AA8[0] )
          bidTraceW(off_1800491E8[0], 296960, off_180049AA8[0], (unsigned int)v8, 290);
        ThrowHR(v9);
      }
      v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
              pperrinfo,
              L"Microsoft OLEDB Persistence Provider");
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049AA0[0] )
          bidTraceW(off_1800491E8[0], 297984, off_180049AA0[0], (unsigned int)v10, 291);
        ThrowHR(v11);
      }
      v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, HLOCAL))pperrinfo->lpVtbl->SetDescription)(pperrinfo, hMem[0]);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A98[0] )
          bidTraceW(off_1800491E8[0], 299008, off_180049A98[0], (unsigned int)v12, 292);
        ThrowHR(v13);
      }
      v14 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, struct IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
              pperrinfo,
              &IID_IErrorInfo,
              &v16);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A90[0] )
          bidTraceW(off_1800491E8[0], 301056, off_180049A90[0], (unsigned int)v14, 294);
        ThrowHR(v15);
      }
      CPersistErrorCache::AddError(this, a3, a3, v16);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v16);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
    }
  }
  catch ( long )
  {
  }
  LocalFree(hMem[0]);
}

```

## disassembly

```asm
0x180015e94  mov     rax, rsp
0x180015e97  mov     [rax+8], rbx
0x180015e9b  mov     [rax+18h], rsi
0x180015e9f  mov     [rax+10h], rdx
0x180015ea3  push    rdi
0x180015ea4  sub     rsp, 50h
0x180015ea8  mov     edi, r8d
0x180015eab  mov     rsi, rcx
0x180015eae  mov     qword ptr [rax-10h], 0
0x180015eb6  mov     qword ptr [rax-28h], 0
0x180015ebe  mov     dword ptr [rax-30h], 0
0x180015ec5  lea     rax, [rax-10h]
0x180015ec9  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x180015ece  mov     r9d, 400h; dwLanguageId
0x180015ed4  mov     rdx, cs:?m_hURLMON@CPersistSession@@0PEAUHINSTANCE__@@EA; lpSource
0x180015edb  mov     ecx, 900h; dwFlags
0x180015ee0  call    cs:__imp_FormatMessageW
0x180015ee7  nop     dword ptr [rax+rax+00h]
0x180015eec  test    eax, eax
0x180015eee  jz      loc_1800160FB
0x180015ef4  mov     [rsp+58h+pperrinfo], 0
0x180015efd  mov     [rsp+58h+var_18], 0
0x180015f06  lea     rcx, [rsp+58h+pperrinfo]; pperrinfo
0x180015f0b  call    cs:__imp_CreateErrorInfo
0x180015f12  nop     dword ptr [rax+rax+00h]
0x180015f17  mov     ebx, eax
0x180015f19  test    eax, eax
0x180015f1b  jns     short loc_180015F5C
0x180015f1d  test    byte ptr cs:_bidGblFlags, 2
0x180015f24  jz      short loc_180015F55
0x180015f26  mov     rcx, cs:off_180049AB0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015f2d  test    rcx, rcx
0x180015f30  jz      short loc_180015F55
0x180015f32  mov     dword ptr [rsp+58h+lpBuffer], 120h
0x180015f3a  mov     r9d, eax
0x180015f3d  mov     r8, cs:off_180049AB0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015f44  mov     edx, 48000h
0x180015f49  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015f50  call    _bidTraceW
0x180015f55  mov     ecx, ebx; int
0x180015f57  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015f5c  mov     rcx, [rsp+58h+pperrinfo]
0x180015f61  mov     rax, [rcx]
0x180015f64  lea     rdx, GUID_NULL
0x180015f6b  mov     rax, [rax+18h]
0x180015f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f74  mov     ebx, eax
0x180015f76  test    eax, eax
0x180015f78  jns     short loc_180015FB9
0x180015f7a  test    byte ptr cs:_bidGblFlags, 2
0x180015f81  jz      short loc_180015FB2
0x180015f83  mov     rcx, cs:off_180049AA8; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015f8a  test    rcx, rcx
0x180015f8d  jz      short loc_180015FB2
0x180015f8f  mov     dword ptr [rsp+58h+lpBuffer], 122h
0x180015f97  mov     r9d, eax
0x180015f9a  mov     r8, cs:off_180049AA8; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015fa1  mov     edx, 48800h
0x180015fa6  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015fad  call    _bidTraceW
0x180015fb2  mov     ecx, ebx; int
0x180015fb4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015fb9  mov     rcx, [rsp+58h+pperrinfo]
0x180015fbe  mov     rax, [rcx]
0x180015fc1  lea     rdx, aMicrosoftOledb; "Microsoft OLEDB Persistence Provider"
0x180015fc8  mov     rax, [rax+20h]
0x180015fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fd1  mov     ebx, eax
0x180015fd3  test    eax, eax
0x180015fd5  jns     short loc_180016016
0x180015fd7  test    byte ptr cs:_bidGblFlags, 2
0x180015fde  jz      short loc_18001600F
0x180015fe0  mov     rcx, cs:off_180049AA0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015fe7  test    rcx, rcx
0x180015fea  jz      short loc_18001600F
0x180015fec  mov     dword ptr [rsp+58h+lpBuffer], 123h
0x180015ff4  mov     r9d, eax
0x180015ff7  mov     r8, cs:off_180049AA0; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180015ffe  mov     edx, 48C00h
0x180016003  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001600a  call    _bidTraceW
0x18001600f  mov     ecx, ebx; int
0x180016011  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016016  mov     rcx, [rsp+58h+pperrinfo]
0x18001601b  mov     rax, [rcx]
0x18001601e  mov     rdx, [rsp+58h+hMem]
0x180016023  mov     rax, [rax+28h]
0x180016027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001602c  mov     ebx, eax
0x18001602e  test    eax, eax
0x180016030  jns     short loc_180016071
0x180016032  test    byte ptr cs:_bidGblFlags, 2
0x180016039  jz      short loc_18001606A
0x18001603b  mov     rcx, cs:off_180049A98; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180016042  test    rcx, rcx
0x180016045  jz      short loc_18001606A
0x180016047  mov     dword ptr [rsp+58h+lpBuffer], 124h
0x18001604f  mov     r9d, eax
0x180016052  mov     r8, cs:off_180049A98; "<CPersistErrorCache::AddHMODULEError|AD"...
0x180016059  mov     edx, 49000h
0x18001605e  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016065  call    _bidTraceW
0x18001606a  mov     ecx, ebx; int
0x18001606c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016071  mov     rcx, [rsp+58h+pperrinfo]
0x180016076  mov     rax, [rcx]
0x180016079  lea     r8, [rsp+58h+var_18]
0x18001607e  lea     rdx, IID_IErrorInfo
0x180016085  mov     rax, [rax]
0x180016088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001608d  mov     ebx, eax
0x18001608f  test    eax, eax
0x180016091  jns     short loc_1800160D2
0x180016093  test    byte ptr cs:_bidGblFlags, 2
0x18001609a  jz      short loc_1800160CB
0x18001609c  mov     rcx, cs:off_180049A90; "<CPersistErrorCache::AddHMODULEError|AD"...
0x1800160a3  test    rcx, rcx
0x1800160a6  jz      short loc_1800160CB
0x1800160a8  mov     dword ptr [rsp+58h+lpBuffer], 126h
0x1800160b0  mov     r9d, eax
0x1800160b3  mov     r8, cs:off_180049A90; "<CPersistErrorCache::AddHMODULEError|AD"...
0x1800160ba  mov     edx, 49800h
0x1800160bf  mov     rcx, cs:off_1800491E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800160c6  call    _bidTraceW
0x1800160cb  mov     ecx, ebx; int
0x1800160cd  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800160d2  mov     r9, [rsp+58h+var_18]; struct IErrorInfo *
0x1800160d7  mov     r8d, edi; unsigned int
0x1800160da  mov     edx, edi; int
0x1800160dc  mov     rcx, rsi; this
0x1800160df  call    ?AddError@CPersistErrorCache@@AEAAXJKPEAUIErrorInfo@@@Z; CPersistErrorCache::AddError(long,ulong,IErrorInfo *)
0x1800160e4  nop
0x1800160e5  lea     rcx, [rsp+58h+var_18]
0x1800160ea  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800160ef  nop
0x1800160f0  lea     rcx, [rsp+58h+pperrinfo]
0x1800160f5  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800160fa  nop
0x1800160fb  jmp     short $+2
0x1800160fd  mov     rcx, [rsp+58h+hMem]; hMem
0x180016102  call    cs:__imp_LocalFree
0x180016109  nop     dword ptr [rax+rax+00h]
0x18001610e  mov     rbx, [rsp+58h+arg_0]
0x180016113  mov     rsi, [rsp+58h+arg_10]
0x180016118  add     rsp, 50h
0x18001611c  pop     rdi
0x18001611d  retn
```
