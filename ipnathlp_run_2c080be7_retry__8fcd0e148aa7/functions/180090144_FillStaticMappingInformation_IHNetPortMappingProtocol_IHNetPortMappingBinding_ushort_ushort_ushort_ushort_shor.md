# FillStaticMappingInformation(IHNetPortMappingProtocol *,IHNetPortMappingBinding *,ushort *,ushort * *,ushort *,ushort * *,short *,ushort * *)

- ea: `0x180090144`
- end: `0x180090521`
- name: `?FillStaticMappingInformation@@YAJPEAUIHNetPortMappingProtocol@@PEAUIHNetPortMappingBinding@@PEAGPEAPEAG23PEAF3@Z`
- size: `989`
- prototype: `__int64 __fastcall(struct IHNetPortMappingProtocol *, struct IHNetPortMappingBinding *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 *, unsigned __int16 **, __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008f760`
- `0x1800907a0`
- `0x180090b60`

## callees

- `0x180037994`
- `0x180042b8c`
- `0x180090144`
- `0x180092600`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009048b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009048b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090430`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009047b`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090430`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009047b`
- `OLEAUT32!__imp_SysAllocString` at `0x180090243`
- `OLEAUT32!__imp_SysAllocString` at `0x180090324`
- `OLEAUT32!__imp_SysAllocString` at `0x1800904fd`
- `OLEAUT32!__imp_SysAllocString` at `0x180090243`
- `OLEAUT32!__imp_SysAllocString` at `0x180090324`
- `OLEAUT32!__imp_SysAllocString` at `0x1800904fd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800901f9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800901f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18009029a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800902b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800902cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18009029a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800902b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800902cb`
- `WS2_32!__imp_htonl` at `0x18009040d`
- `WS2_32!__imp_htonl` at `0x18009040d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009026d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009026d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009045d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800904da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009045d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800904da`

## pseudocode

```c
__int64 __fastcall FillStaticMappingInformation(
        struct IHNetPortMappingProtocol *a1,
        struct IHNetPortMappingBinding *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6,
        __int16 *a7,
        unsigned __int16 **a8)
{
  unsigned __int16 **v8; // r13
  unsigned __int16 **v9; // r12
  __int16 *v11; // rcx
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct IHNetPortMappingProtocol *, OLECHAR **); // rax
  signed int v16; // ebx
  __int64 v17; // rax
  __int16 v18; // r15
  __int64 v19; // rax
  int v20; // ebx
  unsigned __int16 *v21; // rax
  unsigned int v22; // r11d
  unsigned __int16 *v23; // rax
  const OLECHAR *v25; // rcx
  unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  void *v28; // rax
  signed int LastError; // eax
  _WORD *v30; // rax
  BSTR v31; // rax
  int v32; // ecx
  _BYTE v33[4]; // [rsp+20h] [rbp-20h] BYREF
  u_long hostlong; // [rsp+24h] [rbp-1Ch] BYREF
  LPVOID pv; // [rsp+28h] [rbp-18h] BYREF
  OLECHAR *psz; // [rsp+30h] [rbp-10h] BYREF
  char v37; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *nSize; // [rsp+90h] [rbp+50h] BYREF
  char v39; // [rsp+98h] [rbp+58h] BYREF

  nSize = a3;
  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a3 = 0;
  *a4 = 0;
  *v8 = 0;
  *v11 = 0;
  *v9 = 0;
  v14 = *(_QWORD *)a1;
  v37 = 0;
  pv = 0;
  psz = 0;
  v15 = *(__int64 (__fastcall **)(struct IHNetPortMappingProtocol *, OLECHAR **))(v14 + 24);
  v39 = 0;
  v33[0] = 0;
  hostlong = 0;
  v16 = v15(a1, &psz);
  if ( v16 < 0 )
    goto LABEL_11;
  v17 = *(_QWORD *)a1;
  LOBYTE(a6) = 0;
  (*(void (__fastcall **)(struct IHNetPortMappingProtocol *, unsigned __int16 ***))(v17 + 72))(a1, &a6);
  v18 = -1;
  if ( (_BYTE)a6 )
  {
    v19 = -1;
    do
      ++v19;
    while ( psz[v19] );
    v20 = v19 + 12;
    v21 = SysAllocStringLen(0, (int)v19 + 12);
    *v9 = v21;
    if ( v21 )
    {
      StringCchCopyW(v21, (unsigned int)(v20 + 1), psz);
      StringCchCatW(*v9, v22, L" [MICROSOFT]");
      v23 = *v9;
    }
    else
    {
      v23 = 0;
    }
  }
  else
  {
    v23 = SysAllocString(psz);
    *v9 = v23;
  }
  if ( !v23 )
    goto LABEL_10;
  (*(void (__fastcall **)(struct IHNetPortMappingProtocol *, char *))(*(_QWORD *)a1 + 40LL))(a1, &v37);
  if ( v37 == 6 )
  {
    v25 = L"TCP";
  }
  else
  {
    if ( v37 != 17 )
      goto LABEL_28;
    v25 = L"UDP";
  }
  *a4 = SysAllocString(v25);
LABEL_28:
  if ( !*a4 )
  {
LABEL_10:
    v16 = -2147024882;
    goto LABEL_11;
  }
  v16 = (*(__int64 (__fastcall **)(struct IHNetPortMappingProtocol *, unsigned __int16 *))(*(_QWORD *)a1 + 56LL))(
          a1,
          nSize);
  if ( v16 >= 0 && a2 )
  {
    (*(void (__fastcall **)(struct IHNetPortMappingBinding *, char *))(*(_QWORD *)a2 + 40LL))(a2, &v39);
    if ( v39 != 1 )
      v18 = 0;
    v26 = a5;
    *a7 = v18;
    v16 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
            a2,
            v26);
    if ( v16 >= 0 )
    {
      v16 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, _BYTE *))(*(_QWORD *)a2 + 56LL))(a2, v33);
      if ( v16 < 0 )
      {
LABEL_53:
        v31 = SysAllocString((const OLECHAR *)pv);
        v32 = v16;
        *v8 = v31;
        if ( !v31 )
          v32 = -2147024882;
        v16 = v32;
        goto LABEL_11;
      }
      v27 = *(_QWORD *)a2;
      if ( v33[0] == 1 )
      {
        v16 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, LPVOID *))(v27 + 64))(a2, &pv);
        if ( v16 < 0 )
          goto LABEL_11;
        goto LABEL_53;
      }
      v16 = (*(__int64 (__fastcall **)(struct IHNetPortMappingBinding *, u_long *))(v27 + 80))(a2, &hostlong);
      if ( v16 < 0 )
        goto LABEL_11;
      if ( htonl(hostlong) == 2130706433 )
      {
        LODWORD(nSize) = 0;
        if ( !GetComputerNameExW(ComputerNameDnsHostname, 0, (LPDWORD)&nSize) )
        {
          if ( GetLastError() != 234 )
          {
            v16 = -2147467259;
            goto LABEL_11;
          }
          v28 = CoTaskMemAlloc(2LL * (unsigned int)nSize);
          pv = v28;
          if ( !v28 )
            goto LABEL_46;
          if ( !GetComputerNameExW(ComputerNameDnsHostname, (LPWSTR)v28, (LPDWORD)&nSize) )
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_11;
          }
        }
      }
      else if ( hostlong )
      {
        pv = INET_NTOW_TS(hostlong);
      }
      else
      {
        v30 = CoTaskMemAlloc(2u);
        pv = v30;
        if ( v30 )
          *v30 = 0;
      }
      if ( pv )
        goto LABEL_53;
LABEL_46:
      v16 = -2147024882;
    }
  }
LABEL_11:
  if ( psz )
    CoTaskMemFree(psz);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v16 < 0 )
  {
    if ( *a4 )
    {
      SysFreeString(*a4);
      *a4 = 0;
    }
    if ( *v8 )
    {
      SysFreeString(*v8);
      *v8 = 0;
    }
    if ( *v9 )
    {
      SysFreeString(*v9);
      *v9 = 0;
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180090144  mov     [rsp-38h+arg_8], rbx
0x180090149  mov     [rsp-38h+nSize], r8
0x18009014e  push    rbp
0x18009014f  push    rsi
0x180090150  push    rdi
0x180090151  push    r12
0x180090153  push    r13
0x180090155  push    r14
0x180090157  push    r15
0x180090159  mov     rbp, rsp
0x18009015c  sub     rsp, 40h
0x180090160  mov     r13, [rbp+arg_28]
0x180090164  xor     r15d, r15d
0x180090167  mov     r12, [rbp+arg_38]
0x18009016b  mov     rsi, rcx
0x18009016e  mov     rcx, [rbp+arg_30]
0x180090172  mov     rdi, rdx
0x180090175  mov     [r8], r15w
0x180090179  lea     rdx, [rbp+psz]
0x18009017d  mov     [r9], r15
0x180090180  mov     r14, r9
0x180090183  mov     [r13+0], r15
0x180090187  mov     [rcx], r15w
0x18009018b  mov     rcx, rsi
0x18009018e  mov     [r12], r15
0x180090192  mov     rax, [rsi]
0x180090195  mov     [rbp+arg_0], r15b
0x180090199  mov     [rbp+pv], r15
0x18009019d  mov     [rbp+psz], r15
0x1800901a1  mov     rax, [rax+18h]
0x1800901a5  mov     [rbp+arg_18], r15b
0x1800901a9  mov     [rbp+var_20], r15b
0x1800901ad  mov     [rbp+hostlong], r15d
0x1800901b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800901b6  mov     ebx, eax
0x1800901b8  test    eax, eax
0x1800901ba  js      loc_180090264
0x1800901c0  mov     rax, [rsi]
0x1800901c3  lea     rdx, [rbp+arg_28]
0x1800901c7  mov     rcx, rsi
0x1800901ca  mov     byte ptr [rbp+arg_28], r15b
0x1800901ce  mov     rax, [rax+48h]
0x1800901d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800901d7  mov     rcx, [rbp+psz]; psz
0x1800901db  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800901df  xor     ebx, ebx
0x1800901e1  cmp     byte ptr [rbp+arg_28], bl
0x1800901e4  jz      short loc_180090243
0x1800901e6  mov     rax, r15
0x1800901e9  inc     rax
0x1800901ec  cmp     [rcx+rax*2], bx
0x1800901f0  jnz     short loc_1800901E9
0x1800901f2  lea     ebx, [rax+0Ch]
0x1800901f5  xor     ecx, ecx; strIn
0x1800901f7  mov     edx, ebx; ui
0x1800901f9  call    cs:__imp_SysAllocStringLen
0x180090200  nop     dword ptr [rax+rax+00h]
0x180090205  mov     [r12], rax
0x180090209  test    rax, rax
0x18009020c  jz      short loc_18009023D
0x18009020e  mov     r8, [rbp+psz]; unsigned __int16 *
0x180090212  lea     ecx, [rbx+1]
0x180090215  mov     r11d, ecx
0x180090218  mov     edx, ecx; unsigned __int64
0x18009021a  mov     rcx, rax; unsigned __int16 *
0x18009021d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180090222  mov     rcx, [r12]; unsigned __int16 *
0x180090226  lea     r8, aMicrosoft; " [MICROSOFT]"
0x18009022d  mov     edx, r11d; unsigned __int64
0x180090230  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180090235  mov     rax, [r12]
0x180090239  xor     ebx, ebx
0x18009023b  jmp     short loc_180090253
0x18009023d  xor     ebx, ebx
0x18009023f  mov     eax, ebx
0x180090241  jmp     short loc_180090253
0x180090243  call    cs:__imp_SysAllocString
0x18009024a  nop     dword ptr [rax+rax+00h]
0x18009024f  mov     [r12], rax
0x180090253  test    rax, rax
0x180090256  jnz     loc_1800902F6
0x18009025c  mov     ebx, 8007000Eh
0x180090261  xor     r15d, r15d
0x180090264  mov     rcx, [rbp+psz]; pv
0x180090268  test    rcx, rcx
0x18009026b  jz      short loc_180090279
0x18009026d  call    cs:__imp_CoTaskMemFree
0x180090274  nop     dword ptr [rax+rax+00h]
0x180090279  mov     rcx, [rbp+pv]; pv
0x18009027d  test    rcx, rcx
0x180090280  jz      short loc_18009028E
0x180090282  call    cs:__imp_CoTaskMemFree
0x180090289  nop     dword ptr [rax+rax+00h]
0x18009028e  test    ebx, ebx
0x180090290  jns     short loc_1800902DB
0x180090292  mov     rcx, [r14]; bstrString
0x180090295  test    rcx, rcx
0x180090298  jz      short loc_1800902A9
0x18009029a  call    cs:__imp_SysFreeString
0x1800902a1  nop     dword ptr [rax+rax+00h]
0x1800902a6  mov     [r14], r15
0x1800902a9  mov     rcx, [r13+0]; bstrString
0x1800902ad  test    rcx, rcx
0x1800902b0  jz      short loc_1800902C2
0x1800902b2  call    cs:__imp_SysFreeString
0x1800902b9  nop     dword ptr [rax+rax+00h]
0x1800902be  mov     [r13+0], r15
0x1800902c2  mov     rcx, [r12]; bstrString
0x1800902c6  test    rcx, rcx
0x1800902c9  jz      short loc_1800902DB
0x1800902cb  call    cs:__imp_SysFreeString
0x1800902d2  nop     dword ptr [rax+rax+00h]
0x1800902d7  mov     [r12], r15
0x1800902db  mov     eax, ebx
0x1800902dd  mov     rbx, [rsp+40h+arg_8]
0x1800902e5  add     rsp, 40h
0x1800902e9  pop     r15
0x1800902eb  pop     r14
0x1800902ed  pop     r13
0x1800902ef  pop     r12
0x1800902f1  pop     rdi
0x1800902f2  pop     rsi
0x1800902f3  pop     rbp
0x1800902f4  retn
0x1800902f6  mov     rax, [rsi]
0x1800902f9  lea     rdx, [rbp+arg_0]
0x1800902fd  mov     rcx, rsi
0x180090300  mov     rax, [rax+28h]
0x180090304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090309  mov     al, [rbp+arg_0]
0x18009030c  cmp     al, 6
0x18009030e  jnz     short loc_180090319
0x180090310  lea     rcx, aTcp; "TCP"
0x180090317  jmp     short loc_180090324
0x180090319  cmp     al, 11h
0x18009031b  jnz     short loc_180090333
0x18009031d  lea     rcx, aUdp; "UDP"
0x180090324  call    cs:__imp_SysAllocString
0x18009032b  nop     dword ptr [rax+rax+00h]
0x180090330  mov     [r14], rax
0x180090333  cmp     [r14], rbx
0x180090336  jz      loc_18009025C
0x18009033c  mov     rax, [rsi]
0x18009033f  mov     rcx, rsi
0x180090342  mov     rdx, [rbp+nSize]
0x180090346  mov     rax, [rax+38h]
0x18009034a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009034f  mov     ebx, eax
0x180090351  test    eax, eax
0x180090353  js      loc_180090261
0x180090359  test    rdi, rdi
0x18009035c  jz      loc_180090261
0x180090362  mov     rax, [rdi]
0x180090365  lea     rdx, [rbp+arg_18]
0x180090369  mov     rcx, rdi
0x18009036c  mov     rax, [rax+28h]
0x180090370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090375  mov     esi, 1
0x18009037a  cmp     [rbp+arg_18], sil
0x18009037e  jz      short loc_180090386
0x180090380  xor     eax, eax
0x180090382  movzx   r15d, ax
0x180090386  mov     rax, [rbp+arg_30]
0x18009038a  mov     rcx, rdi
0x18009038d  mov     rdx, [rbp+arg_20]
0x180090391  mov     [rax], r15w
0x180090395  mov     rax, [rdi]
0x180090398  mov     rax, [rax+60h]
0x18009039c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903a1  xor     r15d, r15d
0x1800903a4  mov     ebx, eax
0x1800903a6  test    eax, eax
0x1800903a8  js      loc_180090264
0x1800903ae  mov     rax, [rdi]
0x1800903b1  lea     rdx, [rbp+var_20]
0x1800903b5  mov     rcx, rdi
0x1800903b8  mov     rax, [rax+38h]
0x1800903bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903c1  mov     ebx, eax
0x1800903c3  test    eax, eax
0x1800903c5  js      loc_1800904F9
0x1800903cb  mov     rcx, rdi
0x1800903ce  mov     rax, [rdi]
0x1800903d1  cmp     [rbp+var_20], sil
0x1800903d5  jnz     short loc_1800903F3
0x1800903d7  mov     rax, [rax+40h]
0x1800903db  lea     rdx, [rbp+pv]
0x1800903df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903e4  mov     ebx, eax
0x1800903e6  test    eax, eax
0x1800903e8  js      loc_180090264
0x1800903ee  jmp     loc_1800904F9
0x1800903f3  mov     rax, [rax+50h]
0x1800903f7  lea     rdx, [rbp+hostlong]
0x1800903fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090400  mov     ebx, eax
0x180090402  test    eax, eax
0x180090404  js      loc_180090264
0x18009040a  mov     ecx, [rbp+hostlong]; hostlong
0x18009040d  call    cs:__imp_htonl
0x180090414  nop     dword ptr [rax+rax+00h]
0x180090419  cmp     eax, 7F000001h
0x18009041e  jnz     loc_1800904C3
0x180090424  lea     r8, [rbp+nSize]; nSize
0x180090428  mov     dword ptr [rbp+nSize], r15d
0x18009042c  xor     edx, edx; lpBuffer
0x18009042e  mov     ecx, esi; NameType
0x180090430  call    cs:__imp_GetComputerNameExW
0x180090437  nop     dword ptr [rax+rax+00h]
0x18009043c  test    eax, eax
0x18009043e  jnz     loc_1800904F3
0x180090444  call    cs:__imp_GetLastError
0x18009044b  nop     dword ptr [rax+rax+00h]
0x180090450  cmp     eax, 0EAh
0x180090455  jnz     short loc_1800904B9
0x180090457  mov     ecx, dword ptr [rbp+nSize]
0x18009045a  add     rcx, rcx; cb
0x18009045d  call    cs:__imp_CoTaskMemAlloc
0x180090464  nop     dword ptr [rax+rax+00h]
0x180090469  mov     [rbp+pv], rax
0x18009046d  test    rax, rax
0x180090470  jz      short loc_1800904AF
0x180090472  lea     r8, [rbp+nSize]; nSize
0x180090476  mov     rdx, rax; lpBuffer
0x180090479  mov     ecx, esi; NameType
0x18009047b  call    cs:__imp_GetComputerNameExW
0x180090482  nop     dword ptr [rax+rax+00h]
0x180090487  test    eax, eax
0x180090489  jnz     short loc_1800904F3
0x18009048b  call    cs:__imp_GetLastError
0x180090492  nop     dword ptr [rax+rax+00h]
0x180090497  mov     ebx, eax
0x180090499  test    eax, eax
0x18009049b  jle     loc_180090264
0x1800904a1  movzx   ebx, ax
0x1800904a4  or      ebx, 80070000h
0x1800904aa  jmp     loc_180090264
0x1800904af  mov     ebx, 8007000Eh
0x1800904b4  jmp     loc_180090264
0x1800904b9  mov     ebx, 80004005h
0x1800904be  jmp     loc_180090264
0x1800904c3  mov     ecx, [rbp+hostlong]; unsigned int
0x1800904c6  test    ecx, ecx
0x1800904c8  jz      short loc_1800904D5
0x1800904ca  call    ?INET_NTOW_TS@@YAPEAGK@Z; INET_NTOW_TS(ulong)
0x1800904cf  mov     [rbp+pv], rax
0x1800904d3  jmp     short loc_1800904F3
0x1800904d5  mov     ecx, 2; cb
0x1800904da  call    cs:__imp_CoTaskMemAlloc
0x1800904e1  nop     dword ptr [rax+rax+00h]
0x1800904e6  mov     [rbp+pv], rax
0x1800904ea  test    rax, rax
0x1800904ed  jz      short loc_1800904F3
0x1800904ef  mov     [rax], r15w
0x1800904f3  cmp     [rbp+pv], r15
0x1800904f7  jz      short loc_1800904AF
0x1800904f9  mov     rcx, [rbp+pv]; psz
0x1800904fd  call    cs:__imp_SysAllocString
0x180090504  nop     dword ptr [rax+rax+00h]
0x180090509  mov     ecx, ebx
0x18009050b  mov     ebx, 8007000Eh
0x180090510  test    rax, rax
0x180090513  mov     [r13+0], rax
0x180090517  cmovz   ecx, ebx
0x18009051a  mov     ebx, ecx
0x18009051c  jmp     loc_180090264
```
