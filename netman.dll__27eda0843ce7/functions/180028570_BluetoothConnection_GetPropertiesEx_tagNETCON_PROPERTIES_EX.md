# BluetoothConnection::GetPropertiesEx(tagNETCON_PROPERTIES_EX * *)

- ea: `0x180028570`
- end: `0x1800287e6`
- name: `?GetPropertiesEx@BluetoothConnection@@UEAAJPEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x18000538c`
- `0x180028570`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800285d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800285d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028638`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002866b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002877c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002866b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002877c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028789`
- `OLEAUT32!__imp_SysAllocString` at `0x18002867e`
- `OLEAUT32!__imp_SysAllocString` at `0x180028690`
- `OLEAUT32!__imp_SysAllocString` at `0x18002867e`
- `OLEAUT32!__imp_SysAllocString` at `0x180028690`
- `OLEAUT32!__imp_SysFreeString` at `0x18002872a`
- `OLEAUT32!__imp_SysFreeString` at `0x180028739`
- `OLEAUT32!__imp_SysFreeString` at `0x18002874c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002872a`
- `OLEAUT32!__imp_SysFreeString` at `0x180028739`
- `OLEAUT32!__imp_SysFreeString` at `0x18002874c`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800286a0`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800286a0`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::GetPropertiesEx(BluetoothConnection *this, struct tagNETCON_PROPERTIES_EX **a2)
{
  bool v2; // zf
  int v5; // ebx
  char *v6; // rax
  char *v7; // rdi
  CHAR *v8; // rsi
  BSTR v9; // rax
  OLECHAR *v10; // rcx
  __int128 v11; // xmm1
  OLECHAR *v12; // rcx
  OLECHAR *v13; // rcx
  bool v14; // sf
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  SIZE_T cb; // [rsp+28h] [rbp-18h] BYREF

  v2 = *((_DWORD *)this + 20) == 0;
  pv = 0;
  LODWORD(cb) = 0;
  if ( v2 )
  {
    v5 = -2147418113;
LABEL_26:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids,
        (unsigned int)v5);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_26;
  }
  *a2 = 0;
  v6 = (char *)CoTaskMemAlloc(0x68u);
  v7 = v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    goto LABEL_26;
  }
  memset_0(v6, 0, 0x68u);
  v5 = (*(__int64 (__fastcall **)(char *, LPVOID *))(*((_QWORD *)this - 3) + 56LL))((char *)this - 24, &pv);
  if ( v5 )
    goto LABEL_24;
  v5 = (*(__int64 (__fastcall **)(char *, SIZE_T *))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16, &cb);
  if ( !v5 )
  {
    v8 = (CHAR *)CoTaskMemAlloc((unsigned int)cb);
    if ( v8 )
    {
      v5 = (*(__int64 (__fastcall **)(char *, CHAR *, _QWORD))(*((_QWORD *)this - 2) + 48LL))(
             (char *)this - 16,
             v8,
             (unsigned int)cb);
      if ( !v5 )
      {
        *((_QWORD *)v7 + 3) = SysAllocString(*((const OLECHAR **)pv + 2));
        *((_QWORD *)v7 + 4) = SysAllocString(*((const OLECHAR **)pv + 3));
        v9 = SysAllocStringByteLen(v8, cb);
        v10 = (OLECHAR *)*((_QWORD *)v7 + 3);
        *((_QWORD *)v7 + 12) = v9;
        if ( v10 && *((_QWORD *)v7 + 4) && v9 )
        {
          *(_DWORD *)v7 = 104;
          *(_OWORD *)(v7 + 4) = *(_OWORD *)pv;
          *((_DWORD *)v7 + 10) = *((_DWORD *)pv + 8);
          *((_DWORD *)v7 + 11) = *((_DWORD *)pv + 9);
          *((_DWORD *)v7 + 12) = 7;
          *((_DWORD *)v7 + 13) = *((_DWORD *)pv + 10);
          *(_OWORD *)(v7 + 56) = *(_OWORD *)((char *)pv + 44);
          v11 = *(_OWORD *)((char *)pv + 60);
          *((_QWORD *)v7 + 11) = 0;
          *(_OWORD *)(v7 + 72) = v11;
          *a2 = (struct tagNETCON_PROPERTIES_EX *)v7;
        }
        else
        {
          v5 = -2147024882;
          if ( v10 )
            SysFreeString(v10);
          v12 = (OLECHAR *)*((_QWORD *)v7 + 4);
          if ( v12 )
            SysFreeString(v12);
          v13 = (OLECHAR *)*((_QWORD *)v7 + 12);
          if ( v13 )
            SysFreeString(v13);
        }
      }
      CoTaskMemFree(v8);
    }
    else
    {
      v5 = -2147024882;
    }
  }
  CoTaskMemFree(*((LPVOID *)pv + 2));
  CoTaskMemFree(*((LPVOID *)pv + 3));
  CoTaskMemFree(pv);
  v14 = v5 < 0;
  if ( v5 )
  {
LABEL_24:
    CoTaskMemFree(v7);
    v14 = v5 < 0;
  }
  if ( v14 )
    goto LABEL_26;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028570  mov     [rsp-28h+arg_10], rbx
0x180028575  push    rbp
0x180028576  push    rsi
0x180028577  push    rdi
0x180028578  push    r14
0x18002857a  push    r15
0x18002857c  mov     rbp, rsp
0x18002857f  sub     rsp, 40h
0x180028583  mov     rax, cs:__security_cookie
0x18002858a  xor     rax, rsp
0x18002858d  mov     [rbp+var_10], rax
0x180028591  cmp     dword ptr [rcx+50h], 0
0x180028595  mov     r15, rdx
0x180028598  mov     r14, rcx
0x18002859b  mov     [rbp+pv], 0
0x1800285a3  mov     dword ptr [rbp+cb], 0
0x1800285aa  jnz     short loc_1800285B6
0x1800285ac  mov     ebx, 8000FFFFh
0x1800285b1  jmp     loc_180028793
0x1800285b6  test    r15, r15
0x1800285b9  jnz     short loc_1800285C5
0x1800285bb  mov     ebx, 80004003h
0x1800285c0  jmp     loc_180028793
0x1800285c5  mov     ecx, 68h ; 'h'; cb
0x1800285ca  mov     qword ptr [rdx], 0
0x1800285d1  call    cs:__imp_CoTaskMemAlloc
0x1800285d7  mov     rdi, rax
0x1800285da  test    rax, rax
0x1800285dd  jnz     short loc_1800285E9
0x1800285df  mov     ebx, 8007000Eh
0x1800285e4  jmp     loc_180028793
0x1800285e9  xor     edx, edx; Val
0x1800285eb  mov     rcx, rdi; void *
0x1800285ee  lea     r8d, [rdx+68h]; Size
0x1800285f2  call    memset_0
0x1800285f7  mov     rax, [r14-18h]
0x1800285fb  lea     rdx, [rbp+pv]
0x1800285ff  lea     rcx, [r14-18h]
0x180028603  mov     rax, [rax+38h]
0x180028607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002860c  mov     ebx, eax
0x18002860e  test    eax, eax
0x180028610  jnz     loc_180028786
0x180028616  mov     rax, [r14-10h]
0x18002861a  lea     rdx, [rbp+cb]
0x18002861e  lea     rcx, [r14-10h]
0x180028622  mov     rax, [rax+20h]
0x180028626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002862b  mov     ebx, eax
0x18002862d  test    eax, eax
0x18002862f  jnz     loc_18002875C
0x180028635  mov     ecx, dword ptr [rbp+cb]; cb
0x180028638  call    cs:__imp_CoTaskMemAlloc
0x18002863e  mov     rsi, rax
0x180028641  test    rax, rax
0x180028644  jz      loc_180028757
0x18002864a  mov     rdx, [r14-10h]
0x18002864e  lea     rcx, [r14-10h]
0x180028652  mov     r8d, dword ptr [rbp+cb]
0x180028656  mov     rax, [rdx+30h]
0x18002865a  mov     rdx, rsi
0x18002865d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028662  mov     ebx, eax
0x180028664  test    eax, eax
0x180028666  jz      short loc_180028676
0x180028668  mov     rcx, rsi; pv
0x18002866b  call    cs:__imp_CoTaskMemFree
0x180028671  jmp     loc_18002875C
0x180028676  mov     rcx, [rbp+pv]
0x18002867a  mov     rcx, [rcx+10h]; psz
0x18002867e  call    cs:__imp_SysAllocString
0x180028684  mov     [rdi+18h], rax
0x180028688  mov     rcx, [rbp+pv]
0x18002868c  mov     rcx, [rcx+18h]; psz
0x180028690  call    cs:__imp_SysAllocString
0x180028696  mov     [rdi+20h], rax
0x18002869a  mov     rcx, rsi; psz
0x18002869d  mov     edx, dword ptr [rbp+cb]; len
0x1800286a0  call    cs:__imp_SysAllocStringByteLen
0x1800286a6  mov     rcx, [rdi+18h]; bstrString
0x1800286aa  mov     [rdi+60h], rax
0x1800286ae  test    rcx, rcx
0x1800286b1  jz      short loc_180028720
0x1800286b3  cmp     qword ptr [rdi+20h], 0
0x1800286b8  jz      short loc_180028720
0x1800286ba  test    rax, rax
0x1800286bd  jz      short loc_180028720
0x1800286bf  mov     dword ptr [rdi], 68h ; 'h'
0x1800286c5  mov     rax, [rbp+pv]
0x1800286c9  movups  xmm0, xmmword ptr [rax]
0x1800286cc  movdqu  xmmword ptr [rdi+4], xmm0
0x1800286d1  mov     rax, [rbp+pv]
0x1800286d5  mov     ecx, [rax+20h]
0x1800286d8  mov     [rdi+28h], ecx
0x1800286db  mov     rax, [rbp+pv]
0x1800286df  mov     ecx, [rax+24h]
0x1800286e2  mov     [rdi+2Ch], ecx
0x1800286e5  mov     dword ptr [rdi+30h], 7
0x1800286ec  mov     rax, [rbp+pv]
0x1800286f0  mov     ecx, [rax+28h]
0x1800286f3  mov     [rdi+34h], ecx
0x1800286f6  mov     rax, [rbp+pv]
0x1800286fa  movups  xmm0, xmmword ptr [rax+2Ch]
0x1800286fe  movdqu  xmmword ptr [rdi+38h], xmm0
0x180028703  mov     rax, [rbp+pv]
0x180028707  movups  xmm1, xmmword ptr [rax+3Ch]
0x18002870b  mov     qword ptr [rdi+58h], 0
0x180028713  movdqu  xmmword ptr [rdi+48h], xmm1
0x180028718  mov     [r15], rdi
0x18002871b  jmp     loc_180028668
0x180028720  mov     ebx, 8007000Eh
0x180028725  test    rcx, rcx
0x180028728  jz      short loc_180028730
0x18002872a  call    cs:__imp_SysFreeString
0x180028730  mov     rcx, [rdi+20h]; bstrString
0x180028734  test    rcx, rcx
0x180028737  jz      short loc_18002873F
0x180028739  call    cs:__imp_SysFreeString
0x18002873f  mov     rcx, [rdi+60h]; bstrString
0x180028743  test    rcx, rcx
0x180028746  jz      loc_180028668
0x18002874c  call    cs:__imp_SysFreeString
0x180028752  jmp     loc_180028668
0x180028757  mov     ebx, 8007000Eh
0x18002875c  mov     rcx, [rbp+pv]
0x180028760  mov     rcx, [rcx+10h]; pv
0x180028764  call    cs:__imp_CoTaskMemFree
0x18002876a  mov     rcx, [rbp+pv]
0x18002876e  mov     rcx, [rcx+18h]; pv
0x180028772  call    cs:__imp_CoTaskMemFree
0x180028778  mov     rcx, [rbp+pv]; pv
0x18002877c  call    cs:__imp_CoTaskMemFree
0x180028782  test    ebx, ebx
0x180028784  jz      short loc_180028791
0x180028786  mov     rcx, rdi; pv
0x180028789  call    cs:__imp_CoTaskMemFree
0x18002878f  test    ebx, ebx
0x180028791  jns     short loc_1800287C4
0x180028793  mov     rcx, cs:WPP_GLOBAL_Control
0x18002879a  lea     rax, WPP_GLOBAL_Control
0x1800287a1  cmp     rcx, rax
0x1800287a4  jz      short loc_1800287C4
0x1800287a6  test    byte ptr [rcx+1Ch], 1
0x1800287aa  jz      short loc_1800287C4
0x1800287ac  mov     rcx, [rcx+10h]
0x1800287b0  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x1800287b7  mov     edx, 3Ah ; ':'
0x1800287bc  mov     r9d, ebx
0x1800287bf  call    WPP_SF_d
0x1800287c4  mov     eax, ebx
0x1800287c6  mov     rcx, [rbp+var_10]
0x1800287ca  xor     rcx, rsp; StackCookie
0x1800287cd  call    __security_check_cookie
0x1800287d2  mov     rbx, [rsp+40h+arg_10]
0x1800287da  add     rsp, 40h
0x1800287de  pop     r15
0x1800287e0  pop     r14
0x1800287e2  pop     rdi
0x1800287e3  pop     rsi
0x1800287e4  pop     rbp
0x1800287e5  retn
```
