# DoNGen_New(NGenOptionsParser *,ushort const *,ulong *)

- ea: `0x140008548`
- end: `0x140008ecd`
- name: `?DoNGen_New@@YAHPEAVNGenOptionsParser@@PEBGPEAK@Z`
- size: `2437`
- prototype: `__int64 __fastcall(struct NGenOptionsParser *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140009104`

## callees

- `0x1400011d4`
- `0x1400016f4`
- `0x140001f28`
- `0x140006e3c`
- `0x140008010`
- `0x140008548`
- `0x14000a10c`
- `0x14000b010`
- `0x14000e4f4`
- `0x14000e5e4`
- `0x14000e708`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x140008be2`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008be2`
- `KERNEL32!HeapFree` at `0x1400087e0`
- `KERNEL32!HeapFree` at `0x1400089d2`
- `KERNEL32!HeapFree` at `0x140008b55`
- `KERNEL32!HeapFree` at `0x140008bc9`
- `KERNEL32!HeapFree` at `0x1400087e0`
- `KERNEL32!HeapFree` at `0x1400089d2`
- `KERNEL32!HeapFree` at `0x140008b55`
- `KERNEL32!HeapFree` at `0x140008bc9`
- `KERNEL32!GetProcessHeap` at `0x1400087cb`
- `KERNEL32!GetProcessHeap` at `0x1400089bd`
- `KERNEL32!GetProcessHeap` at `0x140008b40`
- `KERNEL32!GetProcessHeap` at `0x140008bb4`
- `KERNEL32!GetProcessHeap` at `0x1400087cb`
- `KERNEL32!GetProcessHeap` at `0x1400089bd`
- `KERNEL32!GetProcessHeap` at `0x140008b40`
- `KERNEL32!GetProcessHeap` at `0x140008bb4`
- `OLEAUT32!__imp_SysAllocString` at `0x140008756`
- `OLEAUT32!__imp_SysAllocString` at `0x140008931`
- `OLEAUT32!__imp_SysAllocString` at `0x140008af8`
- `OLEAUT32!__imp_SysAllocString` at `0x140008bf4`
- `OLEAUT32!__imp_SysAllocString` at `0x140008c96`
- `OLEAUT32!__imp_SysAllocString` at `0x140008756`
- `OLEAUT32!__imp_SysAllocString` at `0x140008931`
- `OLEAUT32!__imp_SysAllocString` at `0x140008af8`
- `OLEAUT32!__imp_SysAllocString` at `0x140008bf4`
- `OLEAUT32!__imp_SysAllocString` at `0x140008c96`
- `OLEAUT32!__imp_SysFreeString` at `0x1400087a5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000898f`
- `OLEAUT32!__imp_SysFreeString` at `0x140008b07`
- `OLEAUT32!__imp_SysFreeString` at `0x140008c03`
- `OLEAUT32!__imp_SysFreeString` at `0x140008d68`
- `OLEAUT32!__imp_SysFreeString` at `0x140008da5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400087a5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000898f`
- `OLEAUT32!__imp_SysFreeString` at `0x140008b07`
- `OLEAUT32!__imp_SysFreeString` at `0x140008c03`
- `OLEAUT32!__imp_SysFreeString` at `0x140008d68`
- `OLEAUT32!__imp_SysFreeString` at `0x140008da5`

## string_xrefs

- `0x140008e3d`: `Error: You must specify an assembly to install.`
- `0x140008e18`: `Error: The specified assembly is not installed.`
- `0x140008e92`: `Error: The specified assembly is not installed.`
- `0x140008b80`: `configuration context of the first EXE for all other inputs.\n`

## pseudocode

```c
__int64 __fastcall DoNGen_New(struct NGenOptionsParser *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v4; // r12d
  int v5; // eax
  struct ICorSvcInstaller *CorSvcInstaller; // rsi
  int v7; // r14d
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  OLECHAR *v16; // r15
  int v17; // eax
  OLECHAR *v18; // r14
  HANDLE ProcessHeap; // rax
  int v21; // eax
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // r9
  OLECHAR *v25; // r12
  int v26; // eax
  __int64 v27; // rdx
  OLECHAR *v28; // r14
  HANDLE v29; // rax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  OLECHAR *v33; // r14
  int v34; // ebx
  unsigned int v35; // r15d
  __int64 v36; // r9
  OLECHAR *v37; // r12
  HANDLE v38; // rax
  OLECHAR *v39; // r15
  HANDLE v40; // rax
  __int64 v41; // r9
  int v42; // eax
  OLECHAR *v43; // r9
  unsigned int v44; // edx
  __int64 v45; // r8
  int v46; // eax
  __int64 v47; // rdx
  int v48; // eax
  const struct SString *v49; // rax
  const struct SString *v50; // rax
  const struct SString *v51; // rax
  __int64 v52; // [rsp+48h] [rbp-B8h] BYREF
  int v53; // [rsp+50h] [rbp-B0h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+68h] [rbp-98h]
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  int v57; // [rsp+78h] [rbp-88h]
  __int64 *v58; // [rsp+80h] [rbp-80h]
  OLECHAR *v59; // [rsp+88h] [rbp-78h] BYREF
  int v60; // [rsp+90h] [rbp-70h]
  struct ICorSvcInstaller *v61; // [rsp+A0h] [rbp-60h]
  BOOL v62; // [rsp+A8h] [rbp-58h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  _BYTE v65[24]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v66[24]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int Buffer; // [rsp+F0h] [rbp-10h] BYREF
  __int64 Buffer_4; // [rsp+F4h] [rbp-Ch]
  OLECHAR *psz; // [rsp+100h] [rbp+0h]
  _WORD v70[260]; // [rsp+108h] [rbp+8h] BYREF

  v4 = 0;
  *a3 = 0;
  if ( *((_BYTE *)a1 + 40) )
    return 0;
  if ( *((_BYTE *)a1 + 30) )
  {
    dword_1400270F0 = 1;
  }
  else
  {
    v5 = dword_1400270F0;
    if ( *((_BYTE *)a1 + 33) )
      v5 = 3;
    dword_1400270F0 = v5;
  }
  CorSvcInstaller = GetCorSvcInstaller();
  v61 = CorSvcInstaller;
  v62 = CorSvcInstaller != 0;
  v63 = 0;
  v64 = 0;
  v7 = *((_DWORD *)a1 + 9);
  HIDWORD(v63) = v7;
  v57 = 0;
  v58 = &v56;
  v56 = 0;
  v8 = (**(__int64 (__fastcall ***)(struct ICorSvcInstaller *, GUID *, __int64 *))CorSvcInstaller)(
         CorSvcInstaller,
         &IID_ICorSvcSetPrivateAttributes,
         &v56);
  if ( v8 < 0 )
    ThrowHR(v8);
  v9 = v57;
  if ( v56 )
    v9 = 1;
  v57 = v9;
  LODWORD(bstrString) = 0;
  HIDWORD(bstrString) = v7;
  v55 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v56 + 24LL))(v56, &bstrString);
  if ( v10 < 0 )
    ThrowHR(v10);
  if ( *((_BYTE *)a1 + 24) )
  {
    v53 = 0;
    v58 = &v52;
    v52 = 0;
    v11 = (**(__int64 (__fastcall ***)(struct ICorSvcInstaller *, GUID *, __int64 *))CorSvcInstaller)(
            CorSvcInstaller,
            &IID_ICorSvcOptimizer,
            &v52);
    if ( v11 < 0 )
      ThrowHR(v11);
    v12 = v53;
    if ( v52 )
      v12 = 1;
    v53 = v12;
    if ( *((_QWORD *)a1 + 1) )
    {
      v14 = 0;
      v15 = 0;
      do
      {
        Buffer_4 = 512;
        psz = v70;
        wcscpy((wchar_t *)&Buffer, L"\x02");
        v70[0] = 0;
        CanonicalizePath(*(const unsigned __int16 **)(*(_QWORD *)a1 + 8 * v15), (struct SString *)&Buffer, 1);
        SString::ConvertToUnicode((SString *)&Buffer);
        v16 = SysAllocString(psz);
        bstrString = v16;
        LODWORD(v55) = v16 != 0;
        v17 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64))(*(_QWORD *)v52 + 32LL))(v52, v16, 1);
        if ( v17 < 0 )
          ThrowHR(v17);
        if ( v16 )
        {
          SysFreeString(v16);
          LODWORD(v55) = 0;
        }
        if ( (Buffer_4 & 0x800000000LL) != 0 )
        {
          v18 = psz;
          if ( psz )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v18);
          }
        }
        v15 = ++v14;
      }
      while ( (unsigned __int64)v14 < *((_QWORD *)a1 + 1) );
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v52 + 32LL))(v52, 0, 1);
      if ( v13 < 0 )
        ThrowHR(v13);
    }
    goto LABEL_106;
  }
  if ( *((_BYTE *)a1 + 32) )
  {
    if ( *((_QWORD *)a1 + 1) )
    {
      v53 = 0;
      v58 = &v52;
      v52 = 0;
      v21 = (**(__int64 (__fastcall ***)(struct ICorSvcInstaller *, GUID *, __int64 *))CorSvcInstaller)(
              CorSvcInstaller,
              &IID_ICorSvcAdvancedInstaller,
              &v52);
      if ( v21 < 0 )
        ThrowHR(v21);
      v22 = v53;
      if ( v52 )
        v22 = 1;
      v53 = v22;
      v23 = 0;
      if ( *((_QWORD *)a1 + 1) )
      {
        v24 = 0;
        do
        {
          wcscpy((wchar_t *)&Buffer, L"\x02");
          Buffer_4 = 512;
          psz = v70;
          v70[0] = 0;
          CanonicalizePath(*(const unsigned __int16 **)(*(_QWORD *)a1 + 8 * v24), (struct SString *)&Buffer, 0);
          SString::ConvertToUnicode((SString *)&Buffer);
          v25 = SysAllocString(psz);
          bstrString = v25;
          LODWORD(v55) = v25 != 0;
          v26 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64, _QWORD, int))(*(_QWORD *)v52 + 32LL))(
                  v52,
                  v25,
                  1,
                  0,
                  1);
          if ( v26 == -2147024894 )
          {
            v51 = (const struct SString *)SString::SString(
                                            &v59,
                                            v27,
                                            L"Error: The specified assembly is not installed.");
            ThrowHR(-2147024894, v51);
          }
          if ( v26 < 0 )
            ThrowHR(v26);
          if ( v25 )
          {
            SysFreeString(v25);
            LODWORD(v55) = 0;
          }
          if ( (Buffer_4 & 0x800000000LL) != 0 )
          {
            v28 = psz;
            if ( psz )
            {
              v29 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                v29 = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = v29;
              }
              HeapFree(v29, 0, v28);
            }
          }
          v24 = ++v23;
        }
        while ( (unsigned __int64)v23 < *((_QWORD *)a1 + 1) );
      }
      v30 = (*(__int64 (__fastcall **)(struct ICorSvcInstaller *, void ***, _QWORD))(*(_QWORD *)CorSvcInstaller + 40LL))(
              CorSvcInstaller,
              cCompileProgressNotification,
              0);
      if ( v30 < 0 )
        ThrowHR(v30);
      goto LABEL_106;
    }
    if ( v57 )
    {
      if ( v56 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      v57 = 0;
    }
    if ( CorSvcInstaller )
    {
      (*(void (__fastcall **)(struct ICorSvcInstaller *))(*(_QWORD *)CorSvcInstaller + 16LL))(CorSvcInstaller);
      v62 = 0;
    }
    return 0;
  }
  v53 = 0;
  v58 = &v52;
  v52 = 0;
  v31 = (**(__int64 (__fastcall ***)(struct ICorSvcInstaller *, GUID *, __int64 *))CorSvcInstaller)(
          CorSvcInstaller,
          &IID_ICorSvcAdvancedInstaller,
          &v52);
  if ( v31 < 0 )
    ThrowHR(v31);
  v32 = v53;
  if ( v52 )
    v32 = 1;
  v53 = v32;
  dword_1400270F4 = 1;
  v33 = 0;
  v59 = 0;
  v34 = 0;
  v60 = 0;
  v35 = 0;
  if ( !*((_QWORD *)a1 + 1) )
    goto LABEL_81;
  v36 = 0;
  while ( 1 )
  {
    wcscpy((wchar_t *)&Buffer, L"\x02");
    Buffer_4 = 512;
    psz = v70;
    v70[0] = 0;
    CanonicalizePath(*(const unsigned __int16 **)(*(_QWORD *)a1 + 8 * v36), (struct SString *)&Buffer, 1);
    SString::ConvertToUnicode((SString *)&Buffer);
    if ( (unsigned int)IsExe(psz) )
      break;
LABEL_67:
    if ( (Buffer_4 & 0x800000000LL) != 0 )
    {
      v37 = psz;
      if ( psz )
      {
        v38 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v38 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v38;
        }
        HeapFree(v38, 0, v37);
      }
      v4 = 0;
    }
    v36 = ++v35;
    if ( (unsigned __int64)v35 >= *((_QWORD *)a1 + 1) )
      goto LABEL_80;
  }
  if ( !v33 )
  {
    SString::ConvertToUnicode((SString *)&Buffer);
    v33 = SysAllocString(psz);
    if ( v34 )
    {
      SysFreeString(0);
      v34 = 0;
      v60 = 0;
    }
    v59 = v33;
    if ( v33 )
      v34 = 1;
    v60 = v34;
    goto LABEL_67;
  }
  Output("\nWARNING: Do not specify multiple EXEs as input. NGen uses the\n");
  Output("configuration context of the first EXE for all other inputs.\n");
  Output("Instead, run NGen separately for individual EXEs.\n\n");
  if ( (Buffer_4 & 0x800000000LL) != 0 )
  {
    v39 = psz;
    if ( psz )
    {
      v40 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v40 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v40;
      }
      HeapFree(v40, 0, v39);
    }
  }
LABEL_80:
  if ( !v33 )
  {
LABEL_81:
    if ( !GetCurrentDirectoryW(0x104u, (LPWSTR)&Buffer) )
      ThrowLastError();
    v33 = SysAllocString((const OLECHAR *)&Buffer);
    if ( v34 )
    {
      SysFreeString(0);
      v34 = 0;
      v60 = 0;
    }
    v59 = v33;
    if ( v33 )
      v34 = 1;
    v60 = v34;
  }
  if ( *((_QWORD *)a1 + 1) )
  {
    v41 = 0;
    do
    {
      wcscpy((wchar_t *)&Buffer, L"\x02");
      Buffer_4 = 512;
      psz = v70;
      v70[0] = 0;
      CanonicalizePath(*(const unsigned __int16 **)(*(_QWORD *)a1 + 8 * v41), (struct SString *)&Buffer, 1);
      if ( Buffer >> ((Buffer_4 & 0x100000000LL) == 0) == 1 )
      {
        v50 = (const struct SString *)SString::SString(v66, 1, L"Error: You must specify an assembly to install.");
        ThrowHR(-2147024894, v50);
      }
      SString::ConvertToUnicode((SString *)&Buffer);
      bstrString = SysAllocString(psz);
      LODWORD(v58) = bstrString != 0;
      LODWORD(v55) = (_DWORD)v58;
      SString::ConvertToUnicode((SString *)&Buffer);
      v42 = IsExe(psz);
      v43 = v33;
      if ( v42 )
        v43 = 0;
      v44 = (*((_BYTE *)a1 + 26) != 0 ? 34 : 32) | 8;
      if ( !*((_BYTE *)a1 + 28) )
        v44 = *((_BYTE *)a1 + 26) != 0 ? 34 : 32;
      v45 = v44 | 0x10;
      if ( !*((_BYTE *)a1 + 29) )
        v45 = v44;
      v46 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64, OLECHAR *, int, int))(*(_QWORD *)v52 + 24LL))(
              v52,
              bstrString,
              v45,
              v43,
              1,
              3);
      if ( v46 == -2147024894 )
      {
        v49 = (const struct SString *)SString::SString(v65, v47, L"Error: The specified assembly is not installed.");
        ThrowHR(-2147024894, v49);
      }
      if ( v46 < 0 )
        ThrowHR(v46);
      v48 = (*(__int64 (__fastcall **)(struct ICorSvcInstaller *, void ***, _QWORD))(*(_QWORD *)CorSvcInstaller + 40LL))(
              CorSvcInstaller,
              cCompileProgressNotification,
              0);
      if ( v48 < 0 )
        ThrowHR(v48);
      if ( (_DWORD)v58 )
      {
        SysFreeString(bstrString);
        LODWORD(v55) = 0;
      }
      if ( (Buffer_4 & 0x800000000LL) != 0 )
        operator delete(psz);
      v41 = ++v4;
    }
    while ( (unsigned __int64)v4 < *((_QWORD *)a1 + 1) );
  }
  if ( v34 )
  {
    SysFreeString(v33);
    v60 = 0;
  }
LABEL_106:
  if ( v53 )
  {
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v53 = 0;
  }
  if ( v57 )
  {
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v57 = 0;
  }
  if ( CorSvcInstaller )
  {
    (*(void (__fastcall **)(struct ICorSvcInstaller *))(*(_QWORD *)CorSvcInstaller + 16LL))(CorSvcInstaller);
    v62 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140008548  mov     [rsp-8+arg_8], rbx
0x14000854d  push    rbp
0x14000854e  push    rsi
0x14000854f  push    rdi
0x140008550  push    r12
0x140008552  push    r13
0x140008554  push    r14
0x140008556  push    r15
0x140008558  lea     rbp, [rsp-220h]
0x140008560  sub     rsp, 320h
0x140008567  mov     rax, cs:__security_cookie
0x14000856e  xor     rax, rsp
0x140008571  mov     [rbp+250h+var_40], rax
0x140008578  mov     rdi, rcx
0x14000857b  xor     r12d, r12d
0x14000857e  mov     [rsp+350h+var_310], r12d
0x140008583  mov     [r8], r12d
0x140008586  cmp     [rcx+28h], r12b
0x14000858a  jnz     loc_14000884D
0x140008590  lea     ecx, [r12+3]
0x140008595  lea     r15d, [r12+1]
0x14000859a  cmp     [rdi+1Eh], r12b
0x14000859e  jz      short loc_1400085A9
0x1400085a0  mov     cs:dword_1400270F0, r15d
0x1400085a7  jmp     short loc_1400085BC
0x1400085a9  mov     eax, cs:dword_1400270F0
0x1400085af  cmp     [rdi+21h], r12b
0x1400085b3  cmovnz  eax, ecx
0x1400085b6  mov     cs:dword_1400270F0, eax
0x1400085bc  call    ?GetCorSvcInstaller@@YAPEAUICorSvcInstaller@@XZ; GetCorSvcInstaller(void)
0x1400085c1  mov     rsi, rax
0x1400085c4  mov     [rbp+250h+var_2B0], rax
0x1400085c8  mov     [rbp+250h+var_2A8], r12d
0x1400085cc  mov     r13d, r12d
0x1400085cf  test    rax, rax
0x1400085d2  cmovnz  r13d, r15d
0x1400085d6  mov     [rbp+250h+var_2A8], r13d
0x1400085da  mov     [rbp+250h+var_2A0], r12
0x1400085de  mov     [rbp+250h+var_298], r12
0x1400085e2  mov     r14d, [rdi+24h]
0x1400085e6  mov     dword ptr [rbp+250h+var_2A0+4], r14d
0x1400085ea  mov     [rsp+350h+var_2E0], r12
0x1400085ef  mov     [rsp+350h+var_2D8], r12d
0x1400085f4  lea     rax, [rsp+350h+var_2E0]
0x1400085f9  mov     [rbp+250h+var_2D0], rax
0x1400085fd  mov     [rsp+350h+var_2E0], r12
0x140008602  mov     [rsp+350h+var_310], r15d
0x140008607  mov     rax, [rsi]
0x14000860a  lea     r8, [rsp+350h+var_2E0]
0x14000860f  lea     rdx, IID_ICorSvcSetPrivateAttributes
0x140008616  mov     rcx, rsi
0x140008619  mov     rax, [rax]
0x14000861c  call    cs:__guard_dispatch_icall_fptr
0x140008622  test    eax, eax
0x140008624  js      loc_140008E5A
0x14000862a  mov     ebx, r15d
0x14000862d  and     ebx, 0FFFFFFFEh
0x140008630  mov     [rsp+350h+var_310], ebx
0x140008634  mov     eax, [rsp+350h+var_2D8]
0x140008638  mov     rcx, [rsp+350h+var_2E0]
0x14000863d  test    rcx, rcx
0x140008640  cmovnz  eax, r15d
0x140008644  mov     [rsp+350h+var_2D8], eax
0x140008648  mov     dword ptr [rsp+350h+bstrString], r12d
0x14000864d  mov     dword ptr [rsp+350h+bstrString+4], r14d
0x140008652  mov     [rsp+350h+var_2E8], r12
0x140008657  mov     rax, [rcx]
0x14000865a  lea     rdx, [rsp+350h+bstrString]
0x14000865f  mov     rax, [rax+18h]
0x140008663  call    cs:__guard_dispatch_icall_fptr
0x140008669  test    eax, eax
0x14000866b  js      loc_140008E62
0x140008671  cmp     [rdi+18h], r12b
0x140008675  jz      loc_140008801
0x14000867b  mov     [rsp+350h+var_308], r12
0x140008680  mov     [rsp+350h+var_300], r12d
0x140008685  lea     rax, [rsp+350h+var_308]
0x14000868a  mov     [rbp+250h+var_2D0], rax
0x14000868e  mov     [rsp+350h+var_308], r12
0x140008693  or      ebx, 2
0x140008696  mov     [rsp+350h+var_310], ebx
0x14000869a  mov     rax, [rsi]
0x14000869d  lea     r8, [rsp+350h+var_308]
0x1400086a2  lea     rdx, IID_ICorSvcOptimizer
0x1400086a9  mov     rcx, rsi
0x1400086ac  mov     rax, [rax]
0x1400086af  call    cs:__guard_dispatch_icall_fptr
0x1400086b5  test    eax, eax
0x1400086b7  js      loc_140008E6A
0x1400086bd  and     ebx, 0FFFFFFFDh
0x1400086c0  mov     [rsp+350h+var_310], ebx
0x1400086c4  mov     eax, [rsp+350h+var_300]
0x1400086c8  mov     rcx, [rsp+350h+var_308]
0x1400086cd  test    rcx, rcx
0x1400086d0  cmovnz  eax, r15d
0x1400086d4  mov     [rsp+350h+var_300], eax
0x1400086d8  mov     rax, [rdi+8]
0x1400086dc  test    rax, rax
0x1400086df  jnz     short loc_140008700
0x1400086e1  mov     rax, [rcx]
0x1400086e4  mov     r8d, r15d
0x1400086e7  xor     edx, edx
0x1400086e9  mov     rax, [rax+20h]
0x1400086ed  call    cs:__guard_dispatch_icall_fptr
0x1400086f3  test    eax, eax
0x1400086f5  js      loc_140008E35
0x1400086fb  jmp     loc_1400087FC
0x140008700  mov     ebx, r12d
0x140008703  test    rax, rax
0x140008706  jz      loc_1400087FC
0x14000870c  mov     r9, r12
0x14000870f  mov     qword ptr [rbp+250h+Buffer], r12
0x140008713  mov     qword ptr [rbp+250h+Buffer+4], 200h
0x14000871b  mov     [rbp+250h+psz], r12
0x14000871f  lea     rax, [rbp+250h+var_248]
0x140008723  mov     [rbp+250h+psz], rax
0x140008727  mov     dword ptr [rbp+250h+Buffer], 2
0x14000872e  mov     rax, [rbp+250h+psz]
0x140008732  mov     [rax], r12w
0x140008736  mov     rcx, [rdi]
0x140008739  mov     r8d, r15d; int
0x14000873c  lea     rdx, [rbp+250h+Buffer]; this
0x140008740  mov     rcx, [rcx+r9*8]; unsigned __int16 *
0x140008744  call    ?CanonicalizePath@@YAXPEBGAEAVSString@@H@Z; CanonicalizePath(ushort const *,SString &,int)
0x140008749  lea     rcx, [rbp+250h+Buffer]; this
0x14000874d  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140008752  mov     rcx, [rbp+250h+psz]; psz
0x140008756  call    cs:__imp_SysAllocString
0x14000875c  mov     r15, rax
0x14000875f  mov     [rsp+350h+bstrString], rax
0x140008764  mov     dword ptr [rsp+350h+var_2E8], r12d
0x140008769  mov     r14d, r12d
0x14000876c  test    rax, rax
0x14000876f  mov     edx, 1
0x140008774  cmovnz  r14d, edx
0x140008778  mov     dword ptr [rsp+350h+var_2E8], r14d
0x14000877d  mov     rcx, [rsp+350h+var_308]
0x140008782  mov     rax, [rcx]
0x140008785  mov     r8d, edx
0x140008788  mov     rdx, r15
0x14000878b  mov     rax, [rax+20h]
0x14000878f  call    cs:__guard_dispatch_icall_fptr
0x140008795  test    eax, eax
0x140008797  js      loc_140008E72
0x14000879d  test    r14d, r14d
0x1400087a0  jz      short loc_1400087B0
0x1400087a2  mov     rcx, r15; bstrString
0x1400087a5  call    cs:__imp_SysFreeString
0x1400087ab  mov     dword ptr [rsp+350h+var_2E8], r12d
0x1400087b0  test    byte ptr [rbp+250h+var_258], 8
0x1400087b4  jz      short loc_1400087E6
0x1400087b6  mov     r14, [rbp+250h+psz]
0x1400087ba  test    r14, r14
0x1400087bd  jz      short loc_1400087E6
0x1400087bf  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400087c6  test    rax, rax
0x1400087c9  jnz     short loc_1400087D8
0x1400087cb  call    cs:__imp_GetProcessHeap
0x1400087d1  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400087d8  mov     r8, r14; lpMem
0x1400087db  xor     edx, edx; dwFlags
0x1400087dd  mov     rcx, rax; hHeap
0x1400087e0  call    cs:__imp_HeapFree
0x1400087e6  mov     r15d, 1
0x1400087ec  add     ebx, r15d
0x1400087ef  mov     r9d, ebx
0x1400087f2  cmp     r9, [rdi+8]
0x1400087f6  jb      loc_14000870F
0x1400087fc  jmp     loc_140008DAF
0x140008801  cmp     [rdi+20h], r12b
0x140008805  jz      loc_140008A0E
0x14000880b  cmp     [rdi+8], r12
0x14000880f  jnz     short loc_140008879
0x140008811  cmp     [rsp+350h+var_2D8], r12d
0x140008816  jz      short loc_140008834
0x140008818  mov     rcx, [rsp+350h+var_2E0]
0x14000881d  test    rcx, rcx
0x140008820  jz      short loc_14000882F
0x140008822  mov     rax, [rcx]
0x140008825  mov     rax, [rax+10h]
0x140008829  call    cs:__guard_dispatch_icall_fptr
0x14000882f  mov     [rsp+350h+var_2D8], r12d
0x140008834  test    r13d, r13d
0x140008837  jz      short loc_14000884D
0x140008839  mov     rax, [rsi]
0x14000883c  mov     rcx, rsi
0x14000883f  mov     rax, [rax+10h]
0x140008843  call    cs:__guard_dispatch_icall_fptr
0x140008849  mov     [rbp+250h+var_2A8], r12d
0x14000884d  xor     eax, eax
0x14000884f  mov     rcx, [rbp+250h+var_40]
0x140008856  xor     rcx, rsp; StackCookie
0x140008859  call    __security_check_cookie
0x14000885e  mov     rbx, [rsp+350h+arg_8]
0x140008866  add     rsp, 320h
0x14000886d  pop     r15
0x14000886f  pop     r14
0x140008871  pop     r13
0x140008873  pop     r12
0x140008875  pop     rdi
0x140008876  pop     rsi
0x140008877  pop     rbp
0x140008878  retn
0x140008879  mov     [rsp+350h+var_308], r12
0x14000887e  mov     [rsp+350h+var_300], r12d
0x140008883  lea     rax, [rsp+350h+var_308]
0x140008888  mov     [rbp+250h+var_2D0], rax
0x14000888c  mov     [rsp+350h+var_308], r12
0x140008891  or      ebx, 4
0x140008894  mov     [rsp+350h+var_310], ebx
0x140008898  mov     rax, [rsi]
0x14000889b  lea     r8, [rsp+350h+var_308]
0x1400088a0  lea     rdx, IID_ICorSvcAdvancedInstaller
0x1400088a7  mov     rcx, rsi
0x1400088aa  mov     rax, [rax]
0x1400088ad  call    cs:__guard_dispatch_icall_fptr
0x1400088b3  test    eax, eax
0x1400088b5  js      loc_140008E7A
0x1400088bb  and     ebx, 0FFFFFFFBh
0x1400088be  mov     [rsp+350h+var_310], ebx
0x1400088c2  mov     eax, [rsp+350h+var_300]
0x1400088c6  cmp     [rsp+350h+var_308], r12
0x1400088cb  cmovnz  eax, r15d
0x1400088cf  mov     [rsp+350h+var_300], eax
0x1400088d3  mov     ebx, r12d
0x1400088d6  cmp     [rdi+8], r12
0x1400088da  jbe     loc_1400089E7
0x1400088e0  mov     r9, r12
0x1400088e3  mov     r15d, 80070002h
0x1400088e9  and     qword ptr [rbp+250h+Buffer], 0
0x1400088ee  mov     qword ptr [rbp+250h+Buffer+4], 200h
0x1400088f6  mov     [rbp+250h+psz], r12
0x1400088fa  lea     rax, [rbp+250h+var_248]
0x1400088fe  mov     [rbp+250h+psz], rax
0x140008902  mov     dword ptr [rbp+250h+Buffer], 2
0x140008909  mov     rax, [rbp+250h+psz]
0x14000890d  mov     [rax], r12w
0x140008911  mov     rcx, [rdi]
0x140008914  xor     r8d, r8d; int
0x140008917  lea     rdx, [rbp+250h+Buffer]; this
0x14000891b  mov     rcx, [rcx+r9*8]; unsigned __int16 *
0x14000891f  call    ?CanonicalizePath@@YAXPEBGAEAVSString@@H@Z; CanonicalizePath(ushort const *,SString &,int)
0x140008924  lea     rcx, [rbp+250h+Buffer]; this
0x140008928  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x14000892d  mov     rcx, [rbp+250h+psz]; psz
0x140008931  call    cs:__imp_SysAllocString
0x140008937  mov     r12, rax
0x14000893a  mov     [rsp+350h+bstrString], rax
0x14000893f  xor     eax, eax
0x140008941  mov     dword ptr [rsp+350h+var_2E8], eax
0x140008945  mov     r14d, eax
0x140008948  test    r12, r12
0x14000894b  lea     edx, [rax+1]
0x14000894e  cmovnz  r14d, edx
0x140008952  mov     dword ptr [rsp+350h+var_2E8], r14d
0x140008957  mov     rcx, [rsp+350h+var_308]
0x14000895c  mov     rax, [rcx]
0x14000895f  mov     [rsp+350h+var_330], edx
0x140008963  xor     r9d, r9d
0x140008966  mov     r8d, edx
0x140008969  mov     rdx, r12
0x14000896c  mov     rax, [rax+20h]
0x140008970  call    cs:__guard_dispatch_icall_fptr
0x140008976  cmp     eax, r15d
0x140008979  jz      loc_140008E92
0x14000897f  test    eax, eax
0x140008981  js      loc_140008E8A
0x140008987  test    r14d, r14d
0x14000898a  jz      short loc_14000899F
0x14000898c  mov     rcx, r12; bstrString
0x14000898f  call    cs:__imp_SysFreeString
0x140008995  xor     r12d, r12d
0x140008998  mov     dword ptr [rsp+350h+var_2E8], r12d
0x14000899d  jmp     short loc_1400089A2
0x14000899f  xor     r12d, r12d
0x1400089a2  test    byte ptr [rbp+250h+var_258], 8
0x1400089a6  jz      short loc_1400089D8
0x1400089a8  mov     r14, [rbp+250h+psz]
0x1400089ac  test    r14, r14
0x1400089af  jz      short loc_1400089D8
0x1400089b1  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400089b8  test    rax, rax
0x1400089bb  jnz     short loc_1400089CA
0x1400089bd  call    cs:__imp_GetProcessHeap
0x1400089c3  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400089ca  mov     r8, r14; lpMem
0x1400089cd  xor     edx, edx; dwFlags
0x1400089cf  mov     rcx, rax; hHeap
0x1400089d2  call    cs:__imp_HeapFree
0x1400089d8  inc     ebx
0x1400089da  mov     r9d, ebx
0x1400089dd  cmp     r9, [rdi+8]
0x1400089e1  jb      loc_1400088E9
0x1400089e7  mov     rax, [rsi]
0x1400089ea  xor     r8d, r8d
0x1400089ed  lea     rdx, ?cCompileProgressNotification@@3VCCompileProgressNotification@@A; CCompileProgressNotification cCompileProgressNotification
0x1400089f4  mov     rcx, rsi
0x1400089f7  mov     rax, [rax+28h]
0x1400089fb  call    cs:__guard_dispatch_icall_fptr
0x140008a01  test    eax, eax
  ... truncated ...
```
