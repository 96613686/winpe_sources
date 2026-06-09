# CMsftDiscFormat2TrackAtOnce::CacheCurrentWriteParametersModePage(void)

- ea: `0x18003734c`
- end: `0x180037509`
- name: `?CacheCurrentWriteParametersModePage@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ`
- size: `445`
- prototype: `__int64 __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800389f0`

## callees

- `0x1800140f4`
- `0x180016778`
- `0x1800236b4`
- `0x18003734c`
- `0x180049832`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180037458`
- `ole32!CoTaskMemFree` at `0x180037465`
- `ole32!CoTaskMemFree` at `0x180037458`
- `ole32!CoTaskMemFree` at `0x180037465`
- `ole32!CoTaskMemAlloc` at `0x18003747d`
- `ole32!CoTaskMemAlloc` at `0x18003747d`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::CacheCurrentWriteParametersModePage(CMsftDiscFormat2TrackAtOnce *this)
{
  __int64 v2; // rcx
  unsigned int v3; // edi
  void *v5; // rax
  void *v6; // rbp
  int v7; // ebx
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+10h] BYREF

  pv = 0;
  LODWORD(cb) = 0;
  if ( *((_WORD *)this + 84) || (v2 = *((_QWORD *)this + 24)) == 0 )
  {
LABEL_13:
    v3 = -2147467259;
    goto LABEL_14;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *, SIZE_T *))(*(_QWORD *)v2 + 104LL))(
         v2,
         5,
         0,
         &pv,
         &cb);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 106, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids, v3);
    }
    goto LABEL_14;
  }
  if ( (unsigned int)cb < 0x34 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 42), 107, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
    }
    goto LABEL_13;
  }
  v5 = CoTaskMemAlloc((unsigned int)cb);
  v6 = v5;
  if ( v5 )
  {
    v7 = cb;
    memcpy_0(v5, pv, (unsigned int)cb);
    *((_QWORD *)this + 28) = pv;
    *((_DWORD *)this + 58) = cb;
    *((_QWORD *)this + 30) = v6;
    *((_DWORD *)this + 62) = v7;
    return v3;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 108, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
  }
  v3 = -2147024882;
LABEL_14:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(0);
  return v3;
}

```

## disassembly

```asm
0x18003734c  mov     r11, rsp
0x18003734f  mov     [r11+18h], rbx
0x180037353  push    rbp
0x180037354  push    rsi
0x180037355  push    rdi
0x180037356  sub     rsp, 40h
0x18003735a  xor     ebx, ebx
0x18003735c  mov     rsi, rcx
0x18003735f  mov     [r11+10h], rbx
0x180037363  mov     dword ptr [rsp+58h+cb], ebx
0x180037367  cmp     [rcx+0A8h], bx
0x18003736e  jnz     loc_18003744E
0x180037374  mov     rcx, [rcx+0C0h]
0x18003737b  test    rcx, rcx
0x18003737e  jz      loc_18003744E
0x180037384  mov     rax, [rcx]
0x180037387  lea     rdx, [r11+8]
0x18003738b  mov     [r11-38h], rdx
0x18003738f  lea     r9, [r11+10h]
0x180037393  xor     r8d, r8d
0x180037396  lea     edx, [rbx+5]
0x180037399  mov     rax, [rax+68h]
0x18003739d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373a2  mov     edi, eax
0x1800373a4  test    eax, eax
0x1800373a6  jns     short loc_1800373F0
0x1800373a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373af  lea     rax, WPP_GLOBAL_Control
0x1800373b6  cmp     rcx, rax
0x1800373b9  jz      loc_180037453
0x1800373bf  test    byte ptr [rcx+15Ch], 4
0x1800373c6  jz      loc_180037453
0x1800373cc  cmp     byte ptr [rcx+159h], 3
0x1800373d3  jb      short loc_180037453
0x1800373d5  mov     rcx, [rcx+150h]
0x1800373dc  lea     edx, [rbx+6Ah]
0x1800373df  mov     r9d, edi
0x1800373e2  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800373e9  call    WPP_SF_d
0x1800373ee  jmp     short loc_180037453
0x1800373f0  mov     r8d, dword ptr [rsp+58h+cb]
0x1800373f5  mov     r9d, 34h ; '4'
0x1800373fb  cmp     r8d, r9d
0x1800373fe  jnb     short loc_18003747A
0x180037400  mov     rcx, cs:WPP_GLOBAL_Control
0x180037407  lea     rax, WPP_GLOBAL_Control
0x18003740e  cmp     rcx, rax
0x180037411  jz      short loc_18003744E
0x180037413  test    byte ptr [rcx+15Ch], 4
0x18003741a  jz      short loc_18003744E
0x18003741c  cmp     byte ptr [rcx+159h], 3
0x180037423  jb      short loc_18003744E
0x180037425  mov     rcx, [rcx+150h]
0x18003742c  lea     edx, [r9+37h]
0x180037430  mov     [rsp+58h+var_28], r9d
0x180037435  mov     [rsp+58h+var_30], r9d
0x18003743a  mov     r9d, r8d
0x18003743d  mov     [rsp+58h+var_38], r8d
0x180037442  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180037449  call    WPP_SF_DDDd
0x18003744e  mov     edi, 80004005h
0x180037453  mov     rcx, [rsp+58h+pv]; pv
0x180037458  call    cs:__imp_CoTaskMemFree
0x18003745e  xor     ecx, ecx; pv
0x180037460  mov     [rsp+58h+pv], rbx
0x180037465  call    cs:__imp_CoTaskMemFree
0x18003746b  mov     rbx, [rsp+58h+arg_10]
0x180037470  mov     eax, edi
0x180037472  add     rsp, 40h
0x180037476  pop     rdi
0x180037477  pop     rsi
0x180037478  pop     rbp
0x180037479  retn
0x18003747a  mov     rcx, r8; cb
0x18003747d  call    cs:__imp_CoTaskMemAlloc
0x180037483  mov     rbp, rax
0x180037486  test    rax, rax
0x180037489  jnz     short loc_1800374CD
0x18003748b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037492  lea     rax, WPP_GLOBAL_Control
0x180037499  cmp     rcx, rax
0x18003749c  jz      short loc_1800374C6
0x18003749e  test    byte ptr [rcx+15Ch], 4
0x1800374a5  jz      short loc_1800374C6
0x1800374a7  cmp     byte ptr [rcx+159h], 3
0x1800374ae  jb      short loc_1800374C6
0x1800374b0  mov     rcx, [rcx+150h]
0x1800374b7  lea     edx, [rbp+6Ch]
0x1800374ba  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x1800374c1  call    WPP_SF_
0x1800374c6  mov     edi, 8007000Eh
0x1800374cb  jmp     short loc_180037453
0x1800374cd  mov     ebx, dword ptr [rsp+58h+cb]
0x1800374d1  mov     rcx, rbp; void *
0x1800374d4  mov     rdx, [rsp+58h+pv]; Src
0x1800374d9  mov     r8d, ebx; Size
0x1800374dc  call    memcpy_0
0x1800374e1  mov     rax, [rsp+58h+pv]
0x1800374e6  mov     [rsi+0E0h], rax
0x1800374ed  mov     eax, dword ptr [rsp+58h+cb]
0x1800374f1  mov     [rsi+0E8h], eax
0x1800374f7  mov     [rsi+0F0h], rbp
0x1800374fe  mov     [rsi+0F8h], ebx
0x180037504  jmp     loc_18003746B
```
