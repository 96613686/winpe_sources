# FillStaticMappingInformation(IHNetPortMappingProtocol *,IHNetPortMappingBinding *,ushort *,ushort * *,ushort *,ushort * *,short *,ushort * *)

- ea: `0x1800893d0`
- end: `0x180089748`
- name: `?FillStaticMappingInformation@@YAJPEAUIHNetPortMappingProtocol@@PEAUIHNetPortMappingBinding@@PEAGPEAPEAG23PEAF3@Z`
- size: `888`
- prototype: `__int64 __fastcall(struct IHNetPortMappingProtocol *, struct IHNetPortMappingBinding *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 *, unsigned __int16 **, __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180088aa0`
- `0x180089980`
- `0x180089d10`

## callees

- `0x180034eb8`
- `0x18003f5a0`
- `0x1800893d0`
- `0x18008b5c8`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008968f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800896c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008968f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800896c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180089681`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800896ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180089681`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800896ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800894c9`
- `OLEAUT32!__imp_SysAllocString` at `0x180089581`
- `OLEAUT32!__imp_SysAllocString` at `0x18008972a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800894c9`
- `OLEAUT32!__imp_SysAllocString` at `0x180089581`
- `OLEAUT32!__imp_SysAllocString` at `0x18008972a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180089485`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180089485`
- `OLEAUT32!__imp_SysFreeString` at `0x18008950a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008951c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008952f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008950a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008951c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008952f`
- `WS2_32!__imp_htonl` at `0x180089664`
- `WS2_32!__imp_htonl` at `0x180089664`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800894e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800894f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800894e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800894f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800896a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008970d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800896a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008970d`

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
0x1800893d0  mov     [rsp-38h+arg_8], rbx
0x1800893d5  mov     [rsp-38h+nSize], r8
0x1800893da  push    rbp
0x1800893db  push    rsi
0x1800893dc  push    rdi
0x1800893dd  push    r12
0x1800893df  push    r13
0x1800893e1  push    r14
0x1800893e3  push    r15
0x1800893e5  mov     rbp, rsp
0x1800893e8  sub     rsp, 40h
0x1800893ec  mov     r13, [rbp+arg_28]
0x1800893f0  xor     r15d, r15d
0x1800893f3  mov     r12, [rbp+arg_38]
0x1800893f7  mov     rsi, rcx
0x1800893fa  mov     rcx, [rbp+arg_30]
0x1800893fe  mov     rdi, rdx
0x180089401  mov     [r8], r15w
0x180089405  lea     rdx, [rbp+psz]
0x180089409  mov     [r9], r15
0x18008940c  mov     r14, r9
0x18008940f  mov     [r13+0], r15
0x180089413  mov     [rcx], r15w
0x180089417  mov     rcx, rsi
0x18008941a  mov     [r12], r15
0x18008941e  mov     rax, [rsi]
0x180089421  mov     [rbp+arg_0], r15b
0x180089425  mov     [rbp+pv], r15
0x180089429  mov     [rbp+psz], r15
0x18008942d  mov     rax, [rax+18h]
0x180089431  mov     [rbp+arg_18], r15b
0x180089435  mov     [rbp+var_20], r15b
0x180089439  mov     [rbp+hostlong], r15d
0x18008943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089442  mov     ebx, eax
0x180089444  test    eax, eax
0x180089446  js      loc_1800894E0
0x18008944c  mov     rax, [rsi]
0x18008944f  lea     rdx, [rbp+arg_28]
0x180089453  mov     rcx, rsi
0x180089456  mov     byte ptr [rbp+arg_28], r15b
0x18008945a  mov     rax, [rax+48h]
0x18008945e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089463  mov     rcx, [rbp+psz]; psz
0x180089467  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008946b  xor     ebx, ebx
0x18008946d  cmp     byte ptr [rbp+arg_28], bl
0x180089470  jz      short loc_1800894C9
0x180089472  mov     rax, r15
0x180089475  inc     rax
0x180089478  cmp     [rcx+rax*2], bx
0x18008947c  jnz     short loc_180089475
0x18008947e  lea     ebx, [rax+0Ch]
0x180089481  xor     ecx, ecx; strIn
0x180089483  mov     edx, ebx; ui
0x180089485  call    cs:__imp_SysAllocStringLen
0x18008948b  mov     [r12], rax
0x18008948f  test    rax, rax
0x180089492  jz      short loc_1800894C3
0x180089494  mov     r8, [rbp+psz]; unsigned __int16 *
0x180089498  lea     ecx, [rbx+1]
0x18008949b  mov     r11d, ecx
0x18008949e  mov     edx, ecx; unsigned __int64
0x1800894a0  mov     rcx, rax; unsigned __int16 *
0x1800894a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800894a8  mov     rcx, [r12]; unsigned __int16 *
0x1800894ac  lea     r8, aMicrosoft; " [MICROSOFT]"
0x1800894b3  mov     edx, r11d; unsigned __int64
0x1800894b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800894bb  mov     rax, [r12]
0x1800894bf  xor     ebx, ebx
0x1800894c1  jmp     short loc_1800894D3
0x1800894c3  xor     ebx, ebx
0x1800894c5  mov     eax, ebx
0x1800894c7  jmp     short loc_1800894D3
0x1800894c9  call    cs:__imp_SysAllocString
0x1800894cf  mov     [r12], rax
0x1800894d3  test    rax, rax
0x1800894d6  jnz     short loc_180089553
0x1800894d8  mov     ebx, 8007000Eh
0x1800894dd  xor     r15d, r15d
0x1800894e0  mov     rcx, [rbp+psz]; pv
0x1800894e4  test    rcx, rcx
0x1800894e7  jz      short loc_1800894EF
0x1800894e9  call    cs:__imp_CoTaskMemFree
0x1800894ef  mov     rcx, [rbp+pv]; pv
0x1800894f3  test    rcx, rcx
0x1800894f6  jz      short loc_1800894FE
0x1800894f8  call    cs:__imp_CoTaskMemFree
0x1800894fe  test    ebx, ebx
0x180089500  jns     short loc_180089539
0x180089502  mov     rcx, [r14]; bstrString
0x180089505  test    rcx, rcx
0x180089508  jz      short loc_180089513
0x18008950a  call    cs:__imp_SysFreeString
0x180089510  mov     [r14], r15
0x180089513  mov     rcx, [r13+0]; bstrString
0x180089517  test    rcx, rcx
0x18008951a  jz      short loc_180089526
0x18008951c  call    cs:__imp_SysFreeString
0x180089522  mov     [r13+0], r15
0x180089526  mov     rcx, [r12]; bstrString
0x18008952a  test    rcx, rcx
0x18008952d  jz      short loc_180089539
0x18008952f  call    cs:__imp_SysFreeString
0x180089535  mov     [r12], r15
0x180089539  mov     eax, ebx
0x18008953b  mov     rbx, [rsp+40h+arg_8]
0x180089543  add     rsp, 40h
0x180089547  pop     r15
0x180089549  pop     r14
0x18008954b  pop     r13
0x18008954d  pop     r12
0x18008954f  pop     rdi
0x180089550  pop     rsi
0x180089551  pop     rbp
0x180089552  retn
0x180089553  mov     rax, [rsi]
0x180089556  lea     rdx, [rbp+arg_0]
0x18008955a  mov     rcx, rsi
0x18008955d  mov     rax, [rax+28h]
0x180089561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089566  mov     al, [rbp+arg_0]
0x180089569  cmp     al, 6
0x18008956b  jnz     short loc_180089576
0x18008956d  lea     rcx, aTcp; "TCP"
0x180089574  jmp     short loc_180089581
0x180089576  cmp     al, 11h
0x180089578  jnz     short loc_18008958A
0x18008957a  lea     rcx, aUdp; "UDP"
0x180089581  call    cs:__imp_SysAllocString
0x180089587  mov     [r14], rax
0x18008958a  cmp     [r14], rbx
0x18008958d  jz      loc_1800894D8
0x180089593  mov     rax, [rsi]
0x180089596  mov     rcx, rsi
0x180089599  mov     rdx, [rbp+nSize]
0x18008959d  mov     rax, [rax+38h]
0x1800895a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895a6  mov     ebx, eax
0x1800895a8  test    eax, eax
0x1800895aa  js      loc_1800894DD
0x1800895b0  test    rdi, rdi
0x1800895b3  jz      loc_1800894DD
0x1800895b9  mov     rax, [rdi]
0x1800895bc  lea     rdx, [rbp+arg_18]
0x1800895c0  mov     rcx, rdi
0x1800895c3  mov     rax, [rax+28h]
0x1800895c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895cc  mov     esi, 1
0x1800895d1  cmp     [rbp+arg_18], sil
0x1800895d5  jz      short loc_1800895DD
0x1800895d7  xor     eax, eax
0x1800895d9  movzx   r15d, ax
0x1800895dd  mov     rax, [rbp+arg_30]
0x1800895e1  mov     rcx, rdi
0x1800895e4  mov     rdx, [rbp+arg_20]
0x1800895e8  mov     [rax], r15w
0x1800895ec  mov     rax, [rdi]
0x1800895ef  mov     rax, [rax+60h]
0x1800895f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895f8  xor     r15d, r15d
0x1800895fb  mov     ebx, eax
0x1800895fd  test    eax, eax
0x1800895ff  js      loc_1800894E0
0x180089605  mov     rax, [rdi]
0x180089608  lea     rdx, [rbp+var_20]
0x18008960c  mov     rcx, rdi
0x18008960f  mov     rax, [rax+38h]
0x180089613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089618  mov     ebx, eax
0x18008961a  test    eax, eax
0x18008961c  js      loc_180089726
0x180089622  mov     rcx, rdi
0x180089625  mov     rax, [rdi]
0x180089628  cmp     [rbp+var_20], sil
0x18008962c  jnz     short loc_18008964A
0x18008962e  mov     rax, [rax+40h]
0x180089632  lea     rdx, [rbp+pv]
0x180089636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008963b  mov     ebx, eax
0x18008963d  test    eax, eax
0x18008963f  js      loc_1800894E0
0x180089645  jmp     loc_180089726
0x18008964a  mov     rax, [rax+50h]
0x18008964e  lea     rdx, [rbp+hostlong]
0x180089652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089657  mov     ebx, eax
0x180089659  test    eax, eax
0x18008965b  js      loc_1800894E0
0x180089661  mov     ecx, [rbp+hostlong]; hostlong
0x180089664  call    cs:__imp_htonl
0x18008966a  cmp     eax, 7F000001h
0x18008966f  jnz     loc_1800896F6
0x180089675  lea     r8, [rbp+nSize]; nSize
0x180089679  mov     dword ptr [rbp+nSize], r15d
0x18008967d  xor     edx, edx; lpBuffer
0x18008967f  mov     ecx, esi; NameType
0x180089681  call    cs:__imp_GetComputerNameExW
0x180089687  test    eax, eax
0x180089689  jnz     loc_180089720
0x18008968f  call    cs:__imp_GetLastError
0x180089695  cmp     eax, 0EAh
0x18008969a  jnz     short loc_1800896EC
0x18008969c  mov     ecx, dword ptr [rbp+nSize]
0x18008969f  add     rcx, rcx; cb
0x1800896a2  call    cs:__imp_CoTaskMemAlloc
0x1800896a8  mov     [rbp+pv], rax
0x1800896ac  test    rax, rax
0x1800896af  jz      short loc_1800896E2
0x1800896b1  lea     r8, [rbp+nSize]; nSize
0x1800896b5  mov     rdx, rax; lpBuffer
0x1800896b8  mov     ecx, esi; NameType
0x1800896ba  call    cs:__imp_GetComputerNameExW
0x1800896c0  test    eax, eax
0x1800896c2  jnz     short loc_180089720
0x1800896c4  call    cs:__imp_GetLastError
0x1800896ca  mov     ebx, eax
0x1800896cc  test    eax, eax
0x1800896ce  jle     loc_1800894E0
0x1800896d4  movzx   ebx, ax
0x1800896d7  or      ebx, 80070000h
0x1800896dd  jmp     loc_1800894E0
0x1800896e2  mov     ebx, 8007000Eh
0x1800896e7  jmp     loc_1800894E0
0x1800896ec  mov     ebx, 80004005h
0x1800896f1  jmp     loc_1800894E0
0x1800896f6  mov     ecx, [rbp+hostlong]; unsigned int
0x1800896f9  test    ecx, ecx
0x1800896fb  jz      short loc_180089708
0x1800896fd  call    ?INET_NTOW_TS@@YAPEAGK@Z; INET_NTOW_TS(ulong)
0x180089702  mov     [rbp+pv], rax
0x180089706  jmp     short loc_180089720
0x180089708  mov     ecx, 2; cb
0x18008970d  call    cs:__imp_CoTaskMemAlloc
0x180089713  mov     [rbp+pv], rax
0x180089717  test    rax, rax
0x18008971a  jz      short loc_180089720
0x18008971c  mov     [rax], r15w
0x180089720  cmp     [rbp+pv], r15
0x180089724  jz      short loc_1800896E2
0x180089726  mov     rcx, [rbp+pv]; psz
0x18008972a  call    cs:__imp_SysAllocString
0x180089730  mov     ecx, ebx
0x180089732  mov     ebx, 8007000Eh
0x180089737  test    rax, rax
0x18008973a  mov     [r13+0], rax
0x18008973e  cmovz   ecx, ebx
0x180089741  mov     ebx, ecx
0x180089743  jmp     loc_1800894E0
```
