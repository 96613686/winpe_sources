# CCheckBase::_Initialize(HCCHECK const *)

- ea: `0x180002770`
- end: `0x180002d83`
- name: `?_Initialize@CCheckBase@@IEAAJPEBUHCCHECK@@@Z`
- size: `1555`
- prototype: `int(CCheckBase *__hidden this, const struct HCCHECK *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002650`
- `0x180008768`

## callees

- `0x180002770`
- `0x180002d90`
- `0x180002eb0`
- `0x180004a4c`
- `0x180009e16`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000284c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800028be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000292a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000284c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800028be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000292a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002795`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002795`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800027e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800027e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800029cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ba9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800029cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ba9`

## pseudocode

```c
__int64 __fastcall CCheckBase::_Initialize(CCheckBase *this, const IID *a2)
{
  unsigned int Data1; // edi
  HRESULT v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int64 v8; // r8
  int v9; // r12d
  unsigned __int128 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r14
  int v14; // esi
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // r8
  int StringW; // eax
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r14
  char *v23; // rdi
  __int64 v24; // r9
  unsigned __int64 v25; // r14
  char *v26; // rdi
  __int64 v27; // r9
  unsigned __int64 v28; // r14
  char *v29; // rdi
  _WORD *v30; // rax
  unsigned __int64 v31; // rcx
  _WORD *v32; // rdx
  __int64 v33; // r9
  unsigned __int64 v34; // r14
  int Error; // eax
  WCHAR v36[8]; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+10h] BYREF
  char *Buffer; // [rsp+90h] [rbp+18h] BYREF
  char *v39; // [rsp+98h] [rbp+20h] BYREF

  Data1 = a2[1].Data1;
  pv = 0;
  v5 = StringFromCLSID(a2, (LPOLESTR *)&pv);
  if ( v5 >= 0 )
  {
    v5 = StringCchPrintfW((unsigned __int16 *)this + 12, 0x39u, L"%s%s%u", pv, L".check.", Data1);
    CoTaskMemFree(pv);
    if ( v5 >= 0 )
    {
      v8 = *(_QWORD *)a2[1].Data4;
      *((_QWORD *)this + 20) = 0;
      if ( !v8 )
        return (unsigned int)-2147467259;
      v9 = -2147024882;
      if ( v8 >= 0x10000 )
      {
        LODWORD(v10) = _AllocString<CTCoAllocPolicy>(v7, v6, v8, (char *)this + 160);
      }
      else
      {
        Buffer = 0;
        LODWORD(v10) = LoadStringW(g_hinst, v8, (LPWSTR)&Buffer, 0);
        if ( (int)v10 > 0 )
        {
          v12 = (int)v10;
          *((_QWORD *)this + 20) = 0;
          v13 = (int)v10 + 1LL;
          if ( v13 >= (int)v10 && (v39 = 0, v10 = v13 * (unsigned __int128)2uLL, is_mul_ok(v13, 2u)) )
          {
            v23 = Buffer;
            *(_QWORD *)&v10 = CoTaskMemAlloc(2 * v13);
            *((_QWORD *)this + 20) = v10;
            v14 = -2147024882;
            if ( (_QWORD)v10 )
              v14 = 0;
            if ( v14 < 0 )
              return (unsigned int)v14;
            if ( !(_QWORD)v10 && v13 || v13 > 0x7FFFFFFF )
            {
              *(_WORD *)v10 = 0;
            }
            else if ( v12 >= 0x7FFFFFFF )
            {
              if ( v13 )
                *(_WORD *)v10 = 0;
            }
            else
            {
              if ( !v23 )
              {
                v23 = byte_18000DBA8;
                v12 = 0;
              }
              if ( v13 )
              {
                v11 = v13;
                *((_QWORD *)&v10 + 1) = v10;
                v24 = 0;
                while ( v12 && *(_WORD *)v23 )
                {
                  **((_WORD **)&v10 + 1) = *(_WORD *)v23;
                  v23 += 2;
                  *((_QWORD *)&v10 + 1) += 2LL;
                  --v12;
                  ++v24;
                  if ( !--v11 )
                  {
                    *(_WORD *)(*((_QWORD *)&v10 + 1) - 2LL) = 0;
                    goto LABEL_8;
                  }
                }
                v25 = v13 - v24;
                **((_WORD **)&v10 + 1) = 0;
                if ( v25 > 1 && 2 * v25 > 2 )
                  memset_0((void *)(v10 + 2 + 2 * v24), 0, 2 * v25 - 2);
              }
            }
          }
          else
          {
            v14 = -2147024362;
          }
LABEL_8:
          if ( v14 < 0 )
            return (unsigned int)v14;
          v15 = *(_QWORD *)&a2[2].Data1;
          *((_QWORD *)this + 18) = 0;
          if ( !v15 )
            goto LABEL_15;
          if ( v15 >= 0x10000 )
          {
            LODWORD(v10) = _AllocString<CTCoAllocPolicy>(v11, *((_QWORD *)&v10 + 1), v15, (char *)this + 144);
          }
          else
          {
            v39 = 0;
            LODWORD(v10) = LoadStringW(g_hinst, v15, (LPWSTR)&v39, 0);
            if ( (int)v10 > 0 )
            {
              v16 = (int)v10;
              *((_QWORD *)this + 18) = 0;
              v17 = (int)v10 + 1LL;
              if ( v17 >= (int)v10 && (*(_QWORD *)v36 = 0, v10 = v17 * (unsigned __int128)2uLL, is_mul_ok(v17, 2u)) )
              {
                v26 = v39;
                *(_QWORD *)&v10 = CoTaskMemAlloc(2 * v17);
                *((_QWORD *)this + 18) = v10;
                v14 = -2147024882;
                if ( (_QWORD)v10 )
                  v14 = 0;
                if ( v14 < 0 )
                  return (unsigned int)v14;
                if ( !(_QWORD)v10 && v17 || v17 > 0x7FFFFFFF )
                {
                  *(_WORD *)v10 = 0;
                }
                else if ( v16 >= 0x7FFFFFFF )
                {
                  if ( v17 )
                    *(_WORD *)v10 = 0;
                }
                else
                {
                  if ( !v26 )
                  {
                    v26 = byte_18000DBA8;
                    v16 = 0;
                  }
                  if ( v17 )
                  {
                    v11 = v17;
                    *((_QWORD *)&v10 + 1) = v10;
                    v27 = 0;
                    while ( v16 && *(_WORD *)v26 )
                    {
                      **((_WORD **)&v10 + 1) = *(_WORD *)v26;
                      v26 += 2;
                      *((_QWORD *)&v10 + 1) += 2LL;
                      --v16;
                      ++v27;
                      if ( !--v11 )
                      {
                        *(_WORD *)(*((_QWORD *)&v10 + 1) - 2LL) = 0;
                        goto LABEL_14;
                      }
                    }
                    v28 = v17 - v27;
                    **((_WORD **)&v10 + 1) = 0;
                    if ( v28 > 1 && 2 * v28 > 2 )
                      memset_0((void *)(v10 + 2 + 2 * v27), 0, 2 * v28 - 2);
                  }
                }
              }
              else
              {
                v14 = -2147024362;
              }
              goto LABEL_14;
            }
            LODWORD(v10) = ResultFromKnownLastError();
          }
          v14 = v10;
LABEL_14:
          if ( v14 >= 0 )
          {
LABEL_15:
            v18 = *(_QWORD *)a2[2].Data4;
            *((_QWORD *)this + 19) = 0;
            if ( !v18 )
            {
LABEL_21:
              *((_DWORD *)this + 43) = BYTE1(a2[3].Data1);
              *((_DWORD *)this + 42) = LOBYTE(a2[3].Data1);
              return (*(__int64 (__fastcall **)(CCheckBase *))(*(_QWORD *)this + 128LL))(this);
            }
            if ( v18 >= 0x10000 )
            {
              Error = _AllocString<CTCoAllocPolicy>(v11, *((_QWORD *)&v10 + 1), v18, (char *)this + 152);
            }
            else
            {
              *(_QWORD *)v36 = 0;
              StringW = LoadStringW(g_hinst, v18, v36, 0);
              if ( StringW > 0 )
              {
                v20 = StringW;
                *((_QWORD *)this + 19) = 0;
                v21 = StringW + 1LL;
                if ( v21 >= StringW && is_mul_ok(v21, 2u) )
                {
                  v29 = *(char **)v36;
                  v30 = CoTaskMemAlloc(2 * v21);
                  *((_QWORD *)this + 19) = v30;
                  if ( v30 )
                    v9 = 0;
                  if ( v9 < 0 )
                    return (unsigned int)v9;
                  if ( !v30 && v21 || v21 > 0x7FFFFFFF )
                  {
                    *v30 = 0;
                  }
                  else if ( v20 >= 0x7FFFFFFF )
                  {
                    if ( v21 )
                      *v30 = 0;
                  }
                  else
                  {
                    if ( !v29 )
                    {
                      v29 = byte_18000DBA8;
                      v20 = 0;
                    }
                    if ( v21 )
                    {
                      v31 = v21;
                      v32 = v30;
                      v33 = 0;
                      while ( v20 && *(_WORD *)v29 )
                      {
                        *v32 = *(_WORD *)v29;
                        v29 += 2;
                        ++v32;
                        --v20;
                        ++v33;
                        if ( !--v31 )
                        {
                          *(v32 - 1) = 0;
                          goto LABEL_20;
                        }
                      }
                      v34 = v21 - v33;
                      *v32 = 0;
                      if ( v34 > 1 && 2 * v34 > 2 )
                        memset_0(&v30[v33 + 1], 0, 2 * v34 - 2);
                    }
                  }
                }
                else
                {
                  v9 = -2147024362;
                }
LABEL_20:
                if ( v9 >= 0 )
                  goto LABEL_21;
                return (unsigned int)v9;
              }
              Error = ResultFromKnownLastError();
            }
            v9 = Error;
            goto LABEL_20;
          }
          return (unsigned int)v14;
        }
        LODWORD(v10) = ResultFromKnownLastError();
      }
      v14 = v10;
      goto LABEL_8;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002770  mov     rax, rsp
0x180002773  push    rbx
0x180002774  push    rbp
0x180002775  push    rdi
0x180002776  push    r13
0x180002778  push    r15
0x18000277a  sub     rsp, 50h
0x18000277e  mov     edi, [rdx+10h]
0x180002781  mov     rbp, rdx
0x180002784  mov     r15, rcx
0x180002787  lea     rdx, [rax+10h]; lplpsz
0x18000278b  xor     r13d, r13d
0x18000278e  mov     rcx, rbp; rclsid
0x180002791  mov     [rax+10h], r13
0x180002795  call    cs:__imp_StringFromCLSID
0x18000279c  nop     dword ptr [rax+rax+00h]
0x1800027a1  mov     ebx, eax
0x1800027a3  test    eax, eax
0x1800027a5  js      loc_180002D7C
0x1800027ab  mov     r9, [rsp+78h+pv]
0x1800027b3  lea     rax, aCheck; ".check."
0x1800027ba  lea     rcx, [r15+18h]; unsigned __int16 *
0x1800027be  mov     [rsp+78h+var_50], edi
0x1800027c2  lea     r8, aSSU; "%s%s%u"
0x1800027c9  mov     [rsp+78h+var_58], rax
0x1800027ce  mov     edx, 39h ; '9'; unsigned __int64
0x1800027d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800027d8  mov     rcx, [rsp+78h+pv]; pv
0x1800027e0  mov     ebx, eax
0x1800027e2  call    cs:__imp_CoTaskMemFree
0x1800027e9  nop     dword ptr [rax+rax+00h]
0x1800027ee  test    ebx, ebx
0x1800027f0  js      loc_180002D7C
0x1800027f6  mov     r8, [rbp+18h]
0x1800027fa  mov     [rsp+78h+arg_0], rsi
0x180002802  mov     [rsp+78h+var_30], r12
0x180002807  mov     [rsp+78h+var_38], r14
0x18000280c  mov     [r15+0A0h], r13
0x180002813  test    r8, r8
0x180002816  jz      loc_180002C9F
0x18000281c  mov     r12d, 8007000Eh
0x180002822  cmp     r8, 10000h
0x180002829  jnb     loc_180002CDE
0x18000282f  mov     rcx, cs:g_hinst; hInstance
0x180002836  mov     edx, r8d; uID
0x180002839  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180002841  mov     [rsp+78h+Buffer], r13
0x180002849  xor     r9d, r9d; cchBufferMax
0x18000284c  call    cs:__imp_LoadStringW
0x180002853  nop     dword ptr [rax+rax+00h]
0x180002858  test    eax, eax
0x18000285a  jle     loc_180002C7A
0x180002860  movsxd  rbx, eax
0x180002863  mov     [r15+0A0h], r13
0x18000286a  lea     r14, [rbx+1]
0x18000286e  cmp     r14, rbx
0x180002871  jnb     loc_1800029AB
0x180002877  mov     esi, 80070216h
0x18000287c  test    esi, esi
0x18000287e  js      loc_180002CA4
0x180002884  mov     r8, [rbp+20h]
0x180002888  mov     [r15+90h], r13
0x18000288f  test    r8, r8
0x180002892  jz      short loc_1800028F6
0x180002894  cmp     r8, 10000h
0x18000289b  jnb     loc_180002D1F
0x1800028a1  mov     rcx, cs:g_hinst; hInstance
0x1800028a8  mov     edx, r8d; uID
0x1800028ab  lea     r8, [rsp+78h+arg_18]; lpBuffer
0x1800028b3  mov     [rsp+78h+arg_18], r13
0x1800028bb  xor     r9d, r9d; cchBufferMax
0x1800028be  call    cs:__imp_LoadStringW
0x1800028c5  nop     dword ptr [rax+rax+00h]
0x1800028ca  test    eax, eax
0x1800028cc  jle     loc_180002C86
0x1800028d2  movsxd  rbx, eax
0x1800028d5  mov     [r15+90h], r13
0x1800028dc  lea     r14, [rbx+1]
0x1800028e0  cmp     r14, rbx
0x1800028e3  jnb     loc_180002A9F
0x1800028e9  mov     esi, 80070216h
0x1800028ee  test    esi, esi
0x1800028f0  js      loc_180002CA4
0x1800028f6  mov     r8, [rbp+28h]
0x1800028fa  mov     [r15+98h], r13
0x180002901  test    r8, r8
0x180002904  jz      short loc_180002964
0x180002906  cmp     r8, 10000h
0x18000290d  jnb     loc_180002D63
0x180002913  mov     rcx, cs:g_hinst; hInstance
0x18000291a  mov     edx, r8d; uID
0x18000291d  lea     r8, [rsp+78h+var_48]; lpBuffer
0x180002922  mov     qword ptr [rsp+78h+var_48], r13
0x180002927  xor     r9d, r9d; cchBufferMax
0x18000292a  call    cs:__imp_LoadStringW
0x180002931  nop     dword ptr [rax+rax+00h]
0x180002936  test    eax, eax
0x180002938  jle     loc_180002C92
0x18000293e  movsxd  rbx, eax
0x180002941  mov     [r15+98h], r13
0x180002948  lea     r14, [rbx+1]
0x18000294c  cmp     r14, rbx
0x18000294f  jnb     loc_180002B90
0x180002955  mov     r12d, 80070216h
0x18000295b  test    r12d, r12d
0x18000295e  js      loc_180002D74
0x180002964  movzx   eax, byte ptr [rbp+31h]
0x180002968  mov     rcx, r15
0x18000296b  mov     [r15+0ACh], eax
0x180002972  movzx   eax, byte ptr [rbp+30h]
0x180002976  mov     [r15+0A8h], eax
0x18000297d  mov     rax, [r15]
0x180002980  mov     rax, [rax+80h]
0x180002987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298c  mov     r12, [rsp+78h+var_30]
0x180002991  mov     r14, [rsp+78h+var_38]
0x180002996  mov     rsi, [rsp+78h+arg_0]
0x18000299e  add     rsp, 50h
0x1800029a2  pop     r15
0x1800029a4  pop     r13
0x1800029a6  pop     rdi
0x1800029a7  pop     rbp
0x1800029a8  pop     rbx
0x1800029a9  retn
0x1800029ab  mov     eax, 2
0x1800029b0  mov     [rsp+78h+arg_18], r13
0x1800029b8  mul     r14
0x1800029bb  test    rdx, rdx
0x1800029be  jnz     loc_180002877
0x1800029c4  mov     rdi, [rsp+78h+Buffer]
0x1800029cc  mov     rcx, rax; cb
0x1800029cf  call    cs:__imp_CoTaskMemAlloc
0x1800029d6  nop     dword ptr [rax+rax+00h]
0x1800029db  test    rax, rax
0x1800029de  mov     [r15+0A0h], rax
0x1800029e5  mov     esi, r12d
0x1800029e8  mov     r10, rax
0x1800029eb  cmovnz  esi, r13d
0x1800029ef  test    esi, esi
0x1800029f1  js      loc_180002CA4
0x1800029f7  test    rax, rax
0x1800029fa  jz      loc_180002CAB
0x180002a00  cmp     r14, 7FFFFFFFh
0x180002a07  ja      loc_180002CB4
0x180002a0d  cmp     rbx, 7FFFFFFFh
0x180002a14  jnb     loc_180002CBD
0x180002a1a  test    rdi, rdi
0x180002a1d  jz      loc_180002CCF
0x180002a23  test    r14, r14
0x180002a26  jz      loc_18000287C
0x180002a2c  mov     rcx, r14
0x180002a2f  mov     rdx, r10
0x180002a32  mov     r9, r13
0x180002a35  test    rbx, rbx
0x180002a38  jz      short loc_180002A68
0x180002a3a  movzx   eax, word ptr [rdi]
0x180002a3d  test    ax, ax
0x180002a40  jz      short loc_180002A63
0x180002a42  mov     [rdx], ax
0x180002a45  add     rdi, 2
0x180002a49  add     rdx, 2
0x180002a4d  dec     rbx
0x180002a50  inc     r9
0x180002a53  sub     rcx, 1
0x180002a57  jnz     short loc_180002A35
0x180002a59  mov     [rdx-2], r13w
0x180002a5e  jmp     loc_18000287C
0x180002a63  test    rcx, rcx
0x180002a66  jz      short loc_180002A59
0x180002a68  sub     r14, r9
0x180002a6b  mov     [rdx], r13w
0x180002a6f  cmp     r14, 1
0x180002a73  jbe     loc_18000287C
0x180002a79  lea     r8, [r14+r14]
0x180002a7d  cmp     r8, 2
0x180002a81  jbe     loc_18000287C
0x180002a87  add     r10, 2
0x180002a8b  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180002a8f  xor     edx, edx; Val
0x180002a91  lea     rcx, [r10+r9*2]; void *
0x180002a95  call    memset_0
0x180002a9a  jmp     loc_18000287C
0x180002a9f  mov     eax, 2
0x180002aa4  mov     qword ptr [rsp+78h+var_48], r13
0x180002aa9  mul     r14
0x180002aac  test    rdx, rdx
0x180002aaf  jnz     loc_1800028E9
0x180002ab5  mov     rdi, [rsp+78h+arg_18]
0x180002abd  mov     rcx, rax; cb
0x180002ac0  call    cs:__imp_CoTaskMemAlloc
0x180002ac7  nop     dword ptr [rax+rax+00h]
0x180002acc  test    rax, rax
0x180002acf  mov     [r15+90h], rax
0x180002ad6  mov     esi, r12d
0x180002ad9  mov     r10, rax
0x180002adc  cmovnz  esi, r13d
0x180002ae0  test    esi, esi
0x180002ae2  js      loc_180002CA4
0x180002ae8  test    rax, rax
0x180002aeb  jz      loc_180002CEC
0x180002af1  cmp     r14, 7FFFFFFFh
0x180002af8  ja      loc_180002CF5
0x180002afe  cmp     rbx, 7FFFFFFFh
0x180002b05  jnb     loc_180002CFE
0x180002b0b  test    rdi, rdi
0x180002b0e  jz      loc_180002D10
0x180002b14  test    r14, r14
0x180002b17  jz      loc_1800028EE
0x180002b1d  mov     rcx, r14
0x180002b20  mov     rdx, r10
0x180002b23  mov     r9, r13
0x180002b26  test    rbx, rbx
0x180002b29  jz      short loc_180002B59
0x180002b2b  movzx   eax, word ptr [rdi]
0x180002b2e  test    ax, ax
0x180002b31  jz      short loc_180002B54
0x180002b33  mov     [rdx], ax
0x180002b36  add     rdi, 2
0x180002b3a  add     rdx, 2
0x180002b3e  dec     rbx
0x180002b41  inc     r9
0x180002b44  sub     rcx, 1
0x180002b48  jnz     short loc_180002B26
0x180002b4a  mov     [rdx-2], r13w
0x180002b4f  jmp     loc_1800028EE
0x180002b54  test    rcx, rcx
0x180002b57  jz      short loc_180002B4A
0x180002b59  sub     r14, r9
0x180002b5c  mov     [rdx], r13w
0x180002b60  cmp     r14, 1
0x180002b64  jbe     loc_1800028EE
0x180002b6a  lea     r8, [r14+r14]
0x180002b6e  cmp     r8, 2
0x180002b72  jbe     loc_1800028EE
0x180002b78  add     r10, 2
0x180002b7c  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180002b80  xor     edx, edx; Val
0x180002b82  lea     rcx, [r10+r9*2]; void *
0x180002b86  call    memset_0
0x180002b8b  jmp     loc_1800028EE
0x180002b90  mov     eax, 2
0x180002b95  mul     r14
0x180002b98  test    rdx, rdx
0x180002b9b  jnz     loc_180002955
0x180002ba1  mov     rdi, qword ptr [rsp+78h+var_48]
0x180002ba6  mov     rcx, rax; cb
0x180002ba9  call    cs:__imp_CoTaskMemAlloc
0x180002bb0  nop     dword ptr [rax+rax+00h]
0x180002bb5  test    rax, rax
0x180002bb8  mov     [r15+98h], rax
0x180002bbf  mov     r10, rax
0x180002bc2  cmovnz  r12d, r13d
0x180002bc6  test    r12d, r12d
0x180002bc9  js      loc_180002D74
0x180002bcf  test    rax, rax
0x180002bd2  jz      loc_180002D30
0x180002bd8  cmp     r14, 7FFFFFFFh
0x180002bdf  ja      loc_180002D39
0x180002be5  cmp     rbx, 7FFFFFFFh
0x180002bec  jnb     loc_180002D42
0x180002bf2  test    rdi, rdi
0x180002bf5  jz      loc_180002D54
0x180002bfb  test    r14, r14
0x180002bfe  jz      loc_18000295B
0x180002c04  mov     rcx, r14
0x180002c07  mov     rdx, r10
0x180002c0a  mov     r9, r13
0x180002c0d  nop     dword ptr [rax]
0x180002c10  test    rbx, rbx
0x180002c13  jz      short loc_180002C43
0x180002c15  movzx   eax, word ptr [rdi]
0x180002c18  test    ax, ax
0x180002c1b  jz      short loc_180002C3E
0x180002c1d  mov     [rdx], ax
0x180002c20  add     rdi, 2
0x180002c24  add     rdx, 2
0x180002c28  dec     rbx
0x180002c2b  inc     r9
0x180002c2e  sub     rcx, 1
0x180002c32  jnz     short loc_180002C10
0x180002c34  mov     [rdx-2], r13w
0x180002c39  jmp     loc_18000295B
0x180002c3e  test    rcx, rcx
0x180002c41  jz      short loc_180002C34
0x180002c43  sub     r14, r9
0x180002c46  mov     [rdx], r13w
0x180002c4a  cmp     r14, 1
0x180002c4e  jbe     loc_18000295B
0x180002c54  lea     r8, [r14+r14]
0x180002c58  cmp     r8, 2
0x180002c5c  jbe     loc_18000295B
0x180002c62  add     r10, 2
0x180002c66  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180002c6a  xor     edx, edx; Val
0x180002c6c  lea     rcx, [r10+r9*2]; void *
0x180002c70  call    memset_0
0x180002c75  jmp     loc_18000295B
0x180002c7a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180002c7f  mov     esi, eax
0x180002c81  jmp     loc_18000287C
  ... truncated ...
```
