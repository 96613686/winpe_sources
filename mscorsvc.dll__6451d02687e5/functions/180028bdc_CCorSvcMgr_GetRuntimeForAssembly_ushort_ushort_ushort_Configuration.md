# CCorSvcMgr::GetRuntimeForAssembly(ushort *,ushort *,ushort * *,Configuration *)

- ea: `0x180028bdc`
- end: `0x180029441`
- name: `?GetRuntimeForAssembly@CCorSvcMgr@@AEAAXPEAG0PEAPEAGPEAVConfiguration@@@Z`
- size: `2149`
- prototype: `void(CCorSvcMgr *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, struct Configuration *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024700`

## callees

- `0x180002468`
- `0x18000c80c`
- `0x18000c8a8`
- `0x18000d138`
- `0x18000d394`
- `0x18000d5f0`
- `0x180028bdc`
- `0x180029524`
- `0x1800298dc`
- `0x18002dc24`
- `0x1800304ec`
- `0x180030568`
- `0x180030d84`
- `0x180032948`
- `0x180032f44`
- `0x180032fe8`
- `0x180034fd4`
- `0x1800351e8`
- `0x180035228`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180028f17`
- `KERNEL32!GetFileAttributesW` at `0x180028f17`
- `KERNEL32!HeapFree` at `0x180028e38`
- `KERNEL32!HeapFree` at `0x1800291ef`
- `KERNEL32!HeapFree` at `0x18002922c`
- `KERNEL32!HeapFree` at `0x1800293df`
- `KERNEL32!HeapFree` at `0x18002941c`
- `KERNEL32!HeapFree` at `0x180028e38`
- `KERNEL32!HeapFree` at `0x1800291ef`
- `KERNEL32!HeapFree` at `0x18002922c`
- `KERNEL32!HeapFree` at `0x1800293df`
- `KERNEL32!HeapFree` at `0x18002941c`
- `KERNEL32!GetProcessHeap` at `0x180028e23`
- `KERNEL32!GetProcessHeap` at `0x1800291da`
- `KERNEL32!GetProcessHeap` at `0x180029217`
- `KERNEL32!GetProcessHeap` at `0x1800293ca`
- `KERNEL32!GetProcessHeap` at `0x180029407`
- `KERNEL32!GetProcessHeap` at `0x180028e23`
- `KERNEL32!GetProcessHeap` at `0x1800291da`
- `KERNEL32!GetProcessHeap` at `0x180029217`
- `KERNEL32!GetProcessHeap` at `0x1800293ca`
- `KERNEL32!GetProcessHeap` at `0x180029407`
- `ucrtbase_clr0400!wcscpy_s` at `0x180028da7`
- `ucrtbase_clr0400!wcscpy_s` at `0x180028e8c`
- `ucrtbase_clr0400!wcscpy_s` at `0x18002906a`
- `ucrtbase_clr0400!wcscpy_s` at `0x180028da7`
- `ucrtbase_clr0400!wcscpy_s` at `0x180028e8c`
- `ucrtbase_clr0400!wcscpy_s` at `0x18002906a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002930b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002930b`
- `mscoree!CLRCreateInstance` at `0x180028c8d`
- `mscoree!CLRCreateInstance` at `0x180028ce7`
- `mscoree!CLRCreateInstance` at `0x180028c8d`
- `mscoree!CLRCreateInstance` at `0x180028ce7`

## string_xrefs

- `0x1800290b5`: `. Assembly %s is configured for version %s of the runtime.\n`
- `0x1800290d3`: `. Assembly %s requires a version of the runtime which is not installed. The file has version %s burned into it, but also check whether there is an exe.config that might be altering the runtime version being requested.\n`
- `0x18002910a`: `Assembly will be compiled once the correct runtime is installed.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
void __fastcall CCorSvcMgr::GetRuntimeForAssembly(
        CCorSvcMgr *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        struct Configuration *a5)
{
  wchar_t *v6; // rdi
  BOOL v7; // r12d
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned __int16 *v12; // r15
  int v13; // ebx
  wchar_t *v14; // r12
  HANDLE ProcessHeap; // rax
  CCorSvcMgr *v16; // rcx
  int v17; // r9d
  unsigned __int16 *v18; // r8
  int v19; // r8d
  unsigned __int16 *v20; // r12
  __int64 v21; // rbx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rbx
  CCorSvcMgr *v24; // rbx
  wchar_t *v25; // rbx
  HANDLE v26; // rax
  void *v27; // rbx
  HANDLE v28; // rax
  BSTR v29; // rax
  wchar_t *v30; // rbx
  HANDLE v31; // rax
  void *v32; // rbx
  HANDLE v33; // rax
  unsigned int SizeInWords; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE SizeInWords_4[12]; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+80h] [rbp-80h]
  BOOL v39; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h]
  __int64 *v41; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+A0h] [rbp-60h]
  CCorSvcMgr *v43; // [rsp+A8h] [rbp-58h]
  unsigned __int16 **v44; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v45; // [rsp+B8h] [rbp-48h]
  BOOL v46; // [rsp+C0h] [rbp-40h]
  wchar_t *v47; // [rsp+C8h] [rbp-38h]
  BOOL v48; // [rsp+D0h] [rbp-30h]
  unsigned int v49; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v50; // [rsp+E4h] [rbp-1Ch]
  wchar_t *Source; // [rsp+F0h] [rbp-10h]
  _WORD v52[260]; // [rsp+F8h] [rbp-8h] BYREF
  int v53; // [rsp+300h] [rbp+200h] BYREF
  __int64 v54; // [rsp+304h] [rbp+204h]
  LPVOID lpMem; // [rsp+310h] [rbp+210h]
  __int16 v56; // [rsp+318h] [rbp+218h] BYREF

  v44 = a4;
  v40 = a3;
  v43 = this;
  v6 = (wchar_t *)operator new(0x40u);
  v47 = v6;
  v7 = v6 != 0;
  v39 = v7;
  v48 = v7;
  *v6 = 0;
  SizeInWords = 32;
  v36 = 0;
  v41 = (__int64 *)&SizeInWords_4[4];
  *(_DWORD *)&SizeInWords_4[8] = 0;
  *(_QWORD *)SizeInWords_4 = 1;
  v8 = CLRCreateInstance(&CLSID_CLRMetaHostPolicy, &IID_ICLRMetaHostPolicy, &SizeInWords_4[4]);
  if ( v8 < 0 )
    ThrowHR(v8);
  *(_DWORD *)SizeInWords_4 = 0;
  v9 = v36;
  if ( *(_QWORD *)&SizeInWords_4[4] )
    v9 = 1;
  v36 = v9;
  v38 = 0;
  v41 = &v37;
  v37 = 0;
  *(_DWORD *)SizeInWords_4 = 2;
  v10 = CLRCreateInstance(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v37);
  if ( v10 < 0 )
    ThrowHR(v10);
  *(_DWORD *)SizeInWords_4 = 0;
  v11 = v38;
  if ( v37 )
    v11 = 1;
  v38 = v11;
  v12 = (unsigned __int16 *)operator new(0x208u);
  v45 = v12;
  v46 = v12 != 0;
  if ( *((_BYTE *)a5 + 640) )
  {
    v50 = 512;
    Source = v52;
    v49 = 2;
    v52[0] = 0;
    SBuffer::Set((SBuffer *)&v49, (struct Configuration *)((char *)a5 + 616));
    HIDWORD(v50) = *((_DWORD *)a5 + 156) & 7 | HIDWORD(v50) & 0xFFFFFFF8;
    HIDWORD(v50) &= ~0x100u;
    SString::ConvertToUnicode((SString *)&v49);
    wcscpy_s(v6, SizeInWords, Source);
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, wchar_t *, unsigned int *, _QWORD, _QWORD, _QWORD, GUID *, _QWORD))(**(_QWORD **)&SizeInWords_4[4] + 24LL))(
            *(_QWORD *)&SizeInWords_4[4],
            24,
            0,
            0,
            v6,
            &SizeInWords,
            0,
            0,
            0,
            &GUID_NULL,
            0);
    LODWORD(v40) = v13;
    if ( (v50 & 0x800000000LL) != 0 )
    {
      v14 = Source;
      if ( Source )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v14);
        v7 = v39;
      }
      else
      {
        v7 = v39;
      }
    }
  }
  else
  {
    if ( (unsigned int)IsExe(a2) || (unsigned int)IsDll(a2) )
    {
      if ( GetFileAttributesW(a2) == -1 )
        ThrowLastError();
      v18 = a2;
    }
    else
    {
      if ( (unsigned int)IsWinMD(a2) )
      {
        SizeInWords = 11;
        wcscpy_s(v6, 0x20u, L"v4.0.30319");
        goto LABEL_75;
      }
      if ( v40 )
        CCorSvcMgr::AssemblyNameAndAppBaseToFileName(v16, a2, v40, v12);
      else
        CCorSvcMgr::AssemblyNameToFileName(v43, a2, v12, v17);
      *v6 = 0;
      v18 = v12;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**(_QWORD **)&SizeInWords_4[4] + 24LL))(
            *(_QWORD *)&SizeInWords_4[4],
            24,
            v18);
    LODWORD(v40) = v13;
  }
  if ( v13 == -2146232576 )
  {
    SizeInWords = 32;
    *v6 = 0;
    if ( (unsigned int)IsExe(a2) || (unsigned int)IsDll(a2) || (v20 = v12, (unsigned int)IsWinMD(a2)) )
      v20 = a2;
    v21 = -1;
    if ( *((_BYTE *)a5 + 640) )
      goto LABEL_35;
    if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, wchar_t *, unsigned int *))(*(_QWORD *)v37 + 32LL))(
           v37,
           v20,
           v6,
           &SizeInWords) >= 0 )
    {
      v22 = -1;
      do
        ++v22;
      while ( v6[v22] );
      if ( v22 )
      {
LABEL_35:
        v53 = 2;
        v54 = 512;
        lpMem = &v56;
        v56 = 0;
        GetHRMsg(0x80131700, (struct SString *)&v53, v19);
        v50 = 512;
        Source = v52;
        v49 = 2;
        v52[0] = 0;
        if ( *v6 )
        {
          do
            ++v21;
          while ( v6[v21] );
          SString::Resize(&v49, v21, 4);
          wcscpy_s(Source, (unsigned __int64)v49 >> ((v50 & 0x100000000LL) == 0), v6);
        }
        else
        {
          SString::Clear((SString *)&v49);
        }
        if ( *((_BYTE *)a5 + 640) )
        {
          SBuffer::Set((SBuffer *)&v49, (struct Configuration *)((char *)a5 + 616));
          HIDWORD(v50) = HIDWORD(v50) & 0xFFFFFFF8 | *((_DWORD *)a5 + 156) & 7;
          HIDWORD(v50) &= ~0x100u;
          v23 = L". Assembly %s is configured for version %s of the runtime.\n";
        }
        else if ( (unsigned int)IsDll(v20) )
        {
          v23 = L". Assembly %s requires version %s of the runtime to run.\n";
        }
        else
        {
          v23 = L". Assembly %s requires a version of the runtime which is not installed. The file has version %s burned i"
                 "nto it, but also check whether there is an exe.config that might be altering the runtime version being requested.\n";
          a2 = v20;
        }
        SString::ConvertToUnicode((SString *)&v49);
        SString::AppendPrintf((SString *)&v53, v23, a2, Source);
        v24 = v43;
        if ( *((_DWORD *)v43 + 317) )
          SString::AppendPrintf((SString *)&v53, L"Assembly will be compiled once the correct runtime is installed.\n");
        SString::ConvertToUnicode((SString *)&v53);
        Logger::Log((char *)v24 + 208, lpMem, 2);
        if ( *((_DWORD *)v24 + 317) )
        {
          if ( *((_DWORD *)a5 + 162) != 1 )
          {
            v41 = 0;
            v42 = 0;
            Node::GetRegKeyThrowing(a5, &v41);
            *((_DWORD *)a5 + 162) = 1;
            (*(void (__fastcall **)(__int64 *, const wchar_t *, __int64))(*v41 + 72))(v41, L"RuntimeMissing", 1);
            if ( v42 )
            {
              if ( v41 )
                (*(void (__fastcall **)(__int64 *, __int64))*v41)(v41, 1);
              v42 = 0;
            }
          }
          Node::SetStatus(a5, 3);
          if ( (v50 & 0x800000000LL) != 0 )
          {
            v25 = Source;
            if ( Source )
            {
              v26 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                v26 = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = v26;
              }
              HeapFree(v26, 0, v25);
            }
          }
          if ( (v54 & 0x800000000LL) != 0 )
          {
            v27 = lpMem;
            if ( lpMem )
            {
              v28 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                v28 = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = v28;
              }
              HeapFree(v28, 0, v27);
            }
          }
          if ( v12 )
          {
            operator delete(v12);
            v46 = 0;
          }
          if ( v38 )
          {
            if ( v37 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            v38 = 0;
          }
          if ( v36 )
          {
            if ( *(_QWORD *)&SizeInWords_4[4] )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SizeInWords_4[4] + 16LL))(*(_QWORD *)&SizeInWords_4[4]);
            v36 = 0;
          }
          if ( v39 )
          {
            operator delete(v6);
            v48 = 0;
          }
          return;
        }
        if ( (v50 & 0x800000000LL) != 0 )
        {
          v30 = Source;
          if ( Source )
          {
            v31 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v31 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v31;
            }
            HeapFree(v31, 0, v30);
          }
        }
        if ( (v54 & 0x800000000LL) != 0 )
        {
          v32 = lpMem;
          if ( lpMem )
          {
            v33 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v33 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v33;
            }
            HeapFree(v33, 0, v32);
          }
        }
      }
    }
LABEL_112:
    ThrowHR((int)v40);
  }
  if ( v13 < 0 )
    goto LABEL_112;
LABEL_75:
  if ( *((_BYTE *)a5 + 640) )
  {
    *v44 = 0;
    if ( v12 )
    {
      operator delete(v12);
      v46 = 0;
    }
    if ( v38 )
    {
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v38 = 0;
    }
    if ( v36 )
    {
      if ( *(_QWORD *)&SizeInWords_4[4] )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SizeInWords_4[4] + 16LL))(*(_QWORD *)&SizeInWords_4[4]);
      v36 = 0;
    }
  }
  else
  {
    v29 = SysAllocString(v6);
    *v44 = v29;
    if ( !v29 )
      ThrowHR(-2147024882);
    if ( v12 )
    {
      operator delete(v12);
      v46 = 0;
    }
    if ( v38 )
    {
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v38 = 0;
    }
    if ( v36 )
    {
      if ( *(_QWORD *)&SizeInWords_4[4] )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SizeInWords_4[4] + 16LL))(*(_QWORD *)&SizeInWords_4[4]);
      v36 = 0;
    }
  }
  if ( v7 )
  {
    operator delete(v6);
    v48 = 0;
  }
}

```

## disassembly

```asm
0x180028bdc  push    rbp
0x180028bde  push    rbx
0x180028bdf  push    rsi
0x180028be0  push    rdi
0x180028be1  push    r12
0x180028be3  push    r13
0x180028be5  push    r14
0x180028be7  push    r15
0x180028be9  lea     rbp, [rsp-438h]
0x180028bf1  sub     rsp, 538h
0x180028bf8  mov     rax, cs:__security_cookie
0x180028bff  xor     rax, rsp
0x180028c02  mov     [rbp+470h+var_50], rax
0x180028c09  mov     [rbp+470h+var_4C0], r9
0x180028c0d  mov     [rbp+470h+var_4E0], r8
0x180028c11  mov     rsi, rdx
0x180028c14  mov     [rbp+470h+var_4C8], rcx
0x180028c18  mov     r14, [rbp+470h+arg_20]
0x180028c1f  xor     r15d, r15d
0x180028c22  mov     dword ptr [rsp+570h+SizeInWords+4], r15d
0x180028c27  lea     ecx, [r15+40h]; dwBytes
0x180028c2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028c30  mov     rdi, rax
0x180028c33  mov     [rbp+470h+var_4A8], rax
0x180028c37  mov     [rbp+470h+var_4A0], r15d
0x180028c3b  mov     r12d, r15d
0x180028c3e  lea     r13d, [r15+1]
0x180028c42  test    rax, rax
0x180028c45  cmovnz  r12d, r13d
0x180028c49  mov     [rbp+470h+var_4E8], r12d
0x180028c4d  mov     [rbp+470h+var_4A0], r12d
0x180028c51  mov     [rax], r15w
0x180028c55  mov     dword ptr [rsp+570h+SizeInWords], 20h ; ' '
0x180028c5d  mov     [rsp+570h+var_508], r15
0x180028c62  mov     [rsp+570h+var_500], r15d
0x180028c67  lea     rax, [rsp+570h+var_508]
0x180028c6c  mov     [rbp+470h+var_4D8], rax
0x180028c70  mov     [rsp+570h+var_508], r15
0x180028c75  mov     dword ptr [rsp+570h+SizeInWords+4], r13d
0x180028c7a  lea     r8, [rsp+570h+var_508]
0x180028c7f  lea     rdx, IID_ICLRMetaHostPolicy
0x180028c86  lea     rcx, CLSID_CLRMetaHostPolicy
0x180028c8d  call    cs:__imp_CLRCreateInstance
0x180028c93  test    eax, eax
0x180028c95  js      loc_18002942B
0x180028c9b  mov     ebx, r13d
0x180028c9e  and     ebx, 0FFFFFFFEh
0x180028ca1  mov     dword ptr [rsp+570h+SizeInWords+4], ebx
0x180028ca5  mov     eax, [rsp+570h+var_500]
0x180028ca9  cmp     [rsp+570h+var_508], r15
0x180028cae  cmovnz  eax, r13d
0x180028cb2  mov     [rsp+570h+var_500], eax
0x180028cb6  mov     [rsp+570h+var_4F8], r15
0x180028cbb  mov     [rbp+470h+var_4F0], r15d
0x180028cbf  lea     rax, [rsp+570h+var_4F8]
0x180028cc4  mov     [rbp+470h+var_4D8], rax
0x180028cc8  mov     [rsp+570h+var_4F8], r15
0x180028ccd  or      ebx, 2
0x180028cd0  mov     dword ptr [rsp+570h+SizeInWords+4], ebx
0x180028cd4  lea     r8, [rsp+570h+var_4F8]
0x180028cd9  lea     rdx, IID_ICLRMetaHost
0x180028ce0  lea     rcx, CLSID_CLRMetaHost
0x180028ce7  call    cs:__imp_CLRCreateInstance
0x180028ced  test    eax, eax
0x180028cef  js      loc_180029433
0x180028cf5  and     ebx, 0FFFFFFFDh
0x180028cf8  mov     dword ptr [rsp+570h+SizeInWords+4], ebx
0x180028cfc  mov     eax, [rbp+470h+var_4F0]
0x180028cff  xor     ebx, ebx
0x180028d01  cmp     [rsp+570h+var_4F8], rbx
0x180028d06  cmovnz  eax, r13d
0x180028d0a  mov     [rbp+470h+var_4F0], eax
0x180028d0d  mov     ecx, 208h; dwBytes
0x180028d12  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028d17  mov     r15, rax
0x180028d1a  mov     [rbp+470h+var_4B8], rax
0x180028d1e  mov     [rbp+470h+var_4B0], ebx
0x180028d21  mov     r13d, ebx
0x180028d24  test    rax, rax
0x180028d27  lea     eax, [rbx+1]
0x180028d2a  cmovnz  r13d, eax
0x180028d2e  mov     [rbp+470h+var_4B0], r13d
0x180028d32  cmp     [r14+280h], bl
0x180028d39  jz      loc_180028E49
0x180028d3f  mov     [rbp+470h+var_490], rbx
0x180028d43  mov     [rbp+470h+var_490+4], 200h
0x180028d4b  mov     [rbp+470h+Source], rbx
0x180028d4f  lea     rax, [rbp+470h+var_478]
0x180028d53  mov     [rbp+470h+Source], rax
0x180028d57  mov     dword ptr [rbp+470h+var_490], 2
0x180028d5e  mov     rax, [rbp+470h+Source]
0x180028d62  mov     [rax], bx
0x180028d65  lea     rbx, [r14+268h]
0x180028d6c  mov     rdx, rbx; struct SBuffer *
0x180028d6f  lea     rcx, [rbp+470h+var_490]; this
0x180028d73  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x180028d78  mov     eax, [rbx+8]
0x180028d7b  and     eax, 7
0x180028d7e  mov     ecx, [rbp+470h+var_488]
0x180028d81  and     ecx, 0FFFFFFF8h
0x180028d84  mov     [rbp+470h+var_488], ecx
0x180028d87  or      ecx, eax
0x180028d89  mov     [rbp+470h+var_488], ecx
0x180028d8c  btr     ecx, 8
0x180028d90  mov     [rbp+470h+var_488], ecx
0x180028d93  lea     rcx, [rbp+470h+var_490]; this
0x180028d97  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180028d9c  mov     edx, dword ptr [rsp+570h+SizeInWords]; SizeInWords
0x180028da0  mov     r8, [rbp+470h+Source]; Source
0x180028da4  mov     rcx, rdi; Destination
0x180028da7  call    cs:__imp_wcscpy_s
0x180028dad  mov     rcx, [rsp+570h+var_508]
0x180028db2  mov     rax, [rcx]
0x180028db5  xor     ebx, ebx
0x180028db7  mov     [rsp+570h+var_520], rbx
0x180028dbc  lea     rdx, GUID_NULL
0x180028dc3  mov     [rsp+570h+var_528], rdx
0x180028dc8  mov     [rsp+570h+var_530], rbx
0x180028dcd  mov     [rsp+570h+var_538], rbx
0x180028dd2  mov     [rsp+570h+var_540], rbx
0x180028dd7  lea     rdx, [rsp+570h+SizeInWords]
0x180028ddc  mov     [rsp+570h+var_548], rdx
0x180028de1  mov     [rsp+570h+var_550], rdi
0x180028de6  xor     r9d, r9d
0x180028de9  xor     r8d, r8d
0x180028dec  lea     edx, [rbx+18h]
0x180028def  mov     rax, [rax+18h]
0x180028df3  call    cs:__guard_dispatch_icall_fptr
0x180028df9  mov     ebx, eax
0x180028dfb  mov     dword ptr [rbp+470h+var_4E0], eax
0x180028dfe  xor     ecx, ecx
0x180028e00  test    byte ptr [rbp+470h+var_488], 8
0x180028e04  jz      loc_180028F2F
0x180028e0a  mov     r12, [rbp+470h+Source]
0x180028e0e  test    r12, r12
0x180028e11  jz      loc_180028F2B
0x180028e17  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180028e1e  test    rax, rax
0x180028e21  jnz     short loc_180028E30
0x180028e23  call    cs:__imp_GetProcessHeap
0x180028e29  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180028e30  mov     r8, r12; lpMem
0x180028e33  xor     edx, edx; dwFlags
0x180028e35  mov     rcx, rax; hHeap
0x180028e38  call    cs:__imp_HeapFree
0x180028e3e  mov     r12d, [rbp+470h+var_4E8]
0x180028e42  xor     ecx, ecx
0x180028e44  jmp     loc_180028F2F
0x180028e49  mov     rcx, rsi; unsigned __int16 *
0x180028e4c  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x180028e51  test    eax, eax
0x180028e53  jnz     loc_180028F14
0x180028e59  mov     rcx, rsi; unsigned __int16 *
0x180028e5c  call    ?IsDll@@YAHPEBG@Z; IsDll(ushort const *)
0x180028e61  test    eax, eax
0x180028e63  jnz     loc_180028F14
0x180028e69  mov     rcx, rsi; unsigned __int16 *
0x180028e6c  call    ?IsWinMD@@YAHPEBG@Z; IsWinMD(ushort const *)
0x180028e71  test    eax, eax
0x180028e73  jz      short loc_180028E97
0x180028e75  mov     dword ptr [rsp+570h+SizeInWords], 0Bh
0x180028e7d  lea     r8, aV4030319; "v4.0.30319"
0x180028e84  mov     edx, 20h ; ' '; SizeInWords
0x180028e89  mov     rcx, rdi; Destination
0x180028e8c  call    cs:__imp_wcscpy_s
0x180028e92  jmp     loc_1800292A6
0x180028e97  mov     rax, [rbp+470h+var_4E0]
0x180028e9b  mov     rdx, rsi; unsigned __int16 *
0x180028e9e  test    rax, rax
0x180028ea1  jz      short loc_180028EB0
0x180028ea3  mov     r9, r15; unsigned __int16 *
0x180028ea6  mov     r8, rax; unsigned __int16 *
0x180028ea9  call    ?AssemblyNameAndAppBaseToFileName@CCorSvcMgr@@AEAAXPEAG00K@Z; CCorSvcMgr::AssemblyNameAndAppBaseToFileName(ushort *,ushort *,ushort *,ulong)
0x180028eae  jmp     short loc_180028EBC
0x180028eb0  mov     r8, r15; unsigned __int16 *
0x180028eb3  mov     rcx, [rbp+470h+var_4C8]; this
0x180028eb7  call    ?AssemblyNameToFileName@CCorSvcMgr@@AEAAXPEAG0K@Z; CCorSvcMgr::AssemblyNameToFileName(ushort *,ushort *,ulong)
0x180028ebc  mov     [rdi], bx
0x180028ebf  mov     r8, r15
0x180028ec2  mov     [rsp+570h+var_520], rbx
0x180028ec7  lea     rdx, GUID_NULL
0x180028ece  mov     [rsp+570h+var_528], rdx
0x180028ed3  mov     [rsp+570h+var_530], rbx
0x180028ed8  mov     [rsp+570h+var_538], rbx
0x180028edd  mov     [rsp+570h+var_540], rbx
0x180028ee2  lea     rdx, [rsp+570h+SizeInWords]
0x180028ee7  mov     [rsp+570h+var_548], rdx
0x180028eec  mov     rcx, [rsp+570h+var_508]
0x180028ef1  xor     r9d, r9d
0x180028ef4  mov     [rsp+570h+var_550], rdi
0x180028ef9  mov     rax, [rcx]
0x180028efc  lea     edx, [r9+18h]
0x180028f00  mov     rax, [rax+18h]
0x180028f04  call    cs:__guard_dispatch_icall_fptr
0x180028f0a  mov     ebx, eax
0x180028f0c  mov     dword ptr [rbp+470h+var_4E0], eax
0x180028f0f  jmp     loc_180028E42
0x180028f14  mov     rcx, rsi; lpFileName
0x180028f17  call    cs:__imp_GetFileAttributesW
0x180028f1d  cmp     eax, 0FFFFFFFFh
0x180028f20  jz      loc_18002943B
0x180028f26  mov     r8, rsi
0x180028f29  jmp     short loc_180028EC2
0x180028f2b  mov     r12d, [rbp+470h+var_4E8]
0x180028f2f  cmp     ebx, 80131700h
0x180028f35  jnz     loc_18002929C
0x180028f3b  mov     dword ptr [rsp+570h+SizeInWords], 20h ; ' '
0x180028f43  mov     [rdi], cx
0x180028f46  mov     rcx, rsi; unsigned __int16 *
0x180028f49  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x180028f4e  xor     ecx, ecx
0x180028f50  test    eax, eax
0x180028f52  jnz     short loc_180028F73
0x180028f54  mov     rcx, rsi; unsigned __int16 *
0x180028f57  call    ?IsDll@@YAHPEBG@Z; IsDll(ushort const *)
0x180028f5c  xor     ecx, ecx
0x180028f5e  test    eax, eax
0x180028f60  jnz     short loc_180028F73
0x180028f62  mov     rcx, rsi; unsigned __int16 *
0x180028f65  call    ?IsWinMD@@YAHPEBG@Z; IsWinMD(ushort const *)
0x180028f6a  xor     ecx, ecx
0x180028f6c  test    eax, eax
0x180028f6e  mov     r12, r15
0x180028f71  jz      short loc_180028F76
0x180028f73  mov     r12, rsi
0x180028f76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028f7a  cmp     [r14+280h], cl
0x180028f81  jnz     short loc_180028FBF
0x180028f83  mov     rcx, [rsp+570h+var_4F8]
0x180028f88  mov     rax, [rcx]
0x180028f8b  lea     r9, [rsp+570h+SizeInWords]
0x180028f90  mov     r8, rdi
0x180028f93  mov     rdx, r12
0x180028f96  mov     rax, [rax+20h]
0x180028f9a  call    cs:__guard_dispatch_icall_fptr
0x180028fa0  xor     ecx, ecx
0x180028fa2  test    eax, eax
0x180028fa4  js      loc_180029422
0x180028faa  mov     rax, rbx
0x180028fad  inc     rax
0x180028fb0  cmp     [rdi+rax*2], cx
0x180028fb4  jnz     short loc_180028FAD
0x180028fb6  test    rax, rax
0x180028fb9  jz      loc_180029422
0x180028fbf  and     [rbp+470h+var_270], 0
0x180028fc7  mov     [rbp+470h+var_270+4], 200h
0x180028fd2  mov     [rbp+470h+lpMem], rcx
0x180028fd9  lea     rax, [rbp+470h+var_258]
0x180028fe0  mov     [rbp+470h+lpMem], rax
0x180028fe7  mov     dword ptr [rbp+470h+var_270], 2
0x180028ff1  mov     rax, [rbp+470h+lpMem]
0x180028ff8  mov     [rax], cx
0x180028ffb  lea     rdx, [rbp+470h+var_270]; this
0x180029002  mov     ecx, 80131700h; unsigned int
0x180029007  call    ?GetHRMsg@@YAXJAEAVSString@@H@Z; GetHRMsg(long,SString &,int)
0x18002900c  xor     ecx, ecx
0x18002900e  mov     [rbp+470h+var_490], rcx
0x180029012  mov     [rbp+470h+var_490+4], 200h
0x18002901a  mov     [rbp+470h+Source], rcx
0x18002901e  lea     rax, [rbp+470h+var_478]
0x180029022  mov     [rbp+470h+Source], rax
0x180029026  mov     dword ptr [rbp+470h+var_490], 2
0x18002902d  mov     rax, [rbp+470h+Source]
0x180029031  mov     [rax], cx
0x180029034  cmp     [rdi], cx
0x180029037  jz      short loc_180029072
0x180029039  inc     rbx
0x18002903c  cmp     [rdi+rbx*2], cx
0x180029040  jnz     short loc_180029039
0x180029042  mov     rdx, rbx
0x180029045  xor     r9d, r9d
0x180029048  lea     r8d, [r9+4]
0x18002904c  lea     rcx, [rbp+470h+var_490]
0x180029050  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180029055  mov     ecx, [rbp+470h+var_488]
0x180029058  not     ecx
0x18002905a  and     cl, 1
0x18002905d  mov     edx, dword ptr [rbp+470h+var_490]
0x180029060  shr     rdx, cl; SizeInWords
0x180029063  mov     r8, rdi; Source
0x180029066  mov     rcx, [rbp+470h+Source]; Destination
0x18002906a  call    cs:__imp_wcscpy_s
0x180029070  jmp     short loc_18002907C
0x180029072  lea     rcx, [rbp+470h+var_490]; this
0x180029076  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x18002907b  nop
0x18002907c  xor     ebx, ebx
0x18002907e  cmp     [r14+280h], bl
0x180029085  jz      short loc_1800290BE
0x180029087  lea     rbx, [r14+268h]
0x18002908e  mov     rdx, rbx; struct SBuffer *
0x180029091  lea     rcx, [rbp+470h+var_490]; this
0x180029095  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x18002909a  mov     ecx, [rbx+8]
0x18002909d  and     ecx, 7
0x1800290a0  mov     eax, [rbp+470h+var_488]
0x1800290a3  and     eax, 0FFFFFFF8h
0x1800290a6  mov     [rbp+470h+var_488], eax
0x1800290a9  or      ecx, eax
0x1800290ab  mov     [rbp+470h+var_488], ecx
  ... truncated ...
```
