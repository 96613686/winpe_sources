# WriteQoSPoliciesToRegsitry

- ea: `0x1800383ac`
- end: `0x18003857f`
- name: `WriteQoSPoliciesToRegsitry`
- size: `467`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180037e0c`
- `0x18003f104`
- `0x1800416fc`

## callees

- `0x1800383ac`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `KERNEL32!RegDeleteValueW` at `0x180038455`
- `KERNEL32!RegDeleteValueW` at `0x18003847c`
- `KERNEL32!RegDeleteValueW` at `0x180038455`
- `KERNEL32!RegDeleteValueW` at `0x18003847c`
- `ADVAPI32!RegSetValueExW` at `0x1800384ef`
- `ADVAPI32!RegSetValueExW` at `0x1800384ef`

## string_xrefs

- `0x180038516`: `WriteQoSPoliciesToRegsitry`

## pseudocode

```c
__int64 __fastcall WriteQoSPoliciesToRegsitry(HKEY hKey, unsigned int *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // edx
  int v6; // esi
  int v7; // r9d
  __int64 v8; // rcx
  unsigned int v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  const WCHAR *v12; // rbp
  __int64 i; // rsi
  unsigned int v14; // ecx
  const WCHAR *v15; // rax
  int v17; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v18[2044]; // [rsp+34h] [rbp-824h] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( !a2 || !hKey )
  {
    v4 = 87;
    goto LABEL_33;
  }
  v4 = 0;
  v5 = 0;
  v6 = 1;
  v7 = 1;
  if ( !*a2 )
    goto LABEL_13;
  v8 = 0;
  do
  {
    v9 = a2[3 * v8 + 2];
    if ( v9 )
    {
      if ( v9 == 1 && a2[3 * v8 + 1] )
        v6 = 0;
    }
    else if ( a2[3 * v8 + 1] )
    {
      v7 = 0;
    }
    ++v5;
    ++v8;
  }
  while ( v5 < *a2 );
  if ( v7 )
  {
LABEL_13:
    v10 = RegDeleteValueW(hKey, L"TxBandwidthKbps");
    v4 = v10;
    if ( v10 == 2 )
    {
      v4 = 0;
    }
    else if ( v10 )
    {
      goto LABEL_33;
    }
  }
  if ( v6 )
  {
    v11 = RegDeleteValueW(hKey, L"RxBandwidthKbps");
    v4 = v11;
    if ( v11 == 2 )
    {
      v4 = 0;
      goto LABEL_20;
    }
    if ( !v11 )
      goto LABEL_20;
LABEL_33:
    if ( (_QWORD)xmmword_180071090 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"%s: failed: %d.", L"WriteQoSPoliciesToRegsitry", v4);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180071090,
        &v17);
    }
    return v4;
  }
LABEL_20:
  v12 = 0;
  for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
  {
    v14 = a2[3 * i + 2];
    if ( v14 )
    {
      v15 = L"RxBandwidthKbps";
      if ( v14 != 1 )
        v15 = v12;
      v12 = v15;
    }
    else
    {
      v12 = L"TxBandwidthKbps";
    }
    if ( a2[3 * i + 1] )
    {
      v4 = RegSetValueExW(hKey, v12, 0, 4u, (const BYTE *)&a2[3 * i + 1], 4u);
      if ( v4 )
        goto LABEL_33;
    }
  }
  if ( v4 )
    goto LABEL_33;
  return v4;
}

```

## disassembly

```asm
0x1800383ac  mov     [rsp+arg_10], rbx
0x1800383b1  mov     [rsp+arg_18], rbp
0x1800383b6  push    rsi
0x1800383b7  push    rdi
0x1800383b8  push    r14
0x1800383ba  sub     rsp, 840h
0x1800383c1  mov     rax, cs:__security_cookie
0x1800383c8  xor     rax, rsp
0x1800383cb  mov     [rsp+858h+var_28], rax
0x1800383d3  mov     rdi, rdx
0x1800383d6  mov     r14, rcx
0x1800383d9  xor     eax, eax
0x1800383db  lea     rcx, [rsp+858h+var_824]; void *
0x1800383e0  xor     edx, edx; Val
0x1800383e2  mov     [rsp+858h+var_828], eax
0x1800383e6  mov     r8d, 7FCh; Size
0x1800383ec  call    memset_0
0x1800383f1  test    rdi, rdi
0x1800383f4  jz      loc_180038505
0x1800383fa  test    r14, r14
0x1800383fd  jz      loc_180038505
0x180038403  xor     ebx, ebx
0x180038405  xor     edx, edx
0x180038407  mov     esi, 1
0x18003840c  mov     r9d, esi
0x18003840f  cmp     [rdi], edx
0x180038411  jbe     short loc_18003844B
0x180038413  xor     ecx, ecx
0x180038415  lea     r8, [rcx+rcx*2]
0x180038419  mov     eax, [rdi+r8*4+8]
0x18003841e  test    eax, eax
0x180038420  jnz     short loc_18003842E
0x180038422  cmp     [rdi+r8*4+4], ebx
0x180038427  jz      short loc_18003843D
0x180038429  xor     r9d, r9d
0x18003842c  jmp     short loc_18003843D
0x18003842e  cmp     eax, 1
0x180038431  jnz     short loc_18003843D
0x180038433  xor     eax, eax
0x180038435  cmp     [rdi+r8*4+4], eax
0x18003843a  cmovnz  esi, eax
0x18003843d  inc     edx
0x18003843f  inc     rcx
0x180038442  cmp     edx, [rdi]
0x180038444  jb      short loc_180038415
0x180038446  test    r9d, r9d
0x180038449  jz      short loc_18003846E
0x18003844b  lea     rdx, aTxbandwidthkbp; "TxBandwidthKbps"
0x180038452  mov     rcx, r14; hKey
0x180038455  call    cs:__imp_RegDeleteValueW
0x18003845b  mov     ebx, eax
0x18003845d  cmp     eax, 2
0x180038460  jnz     short loc_180038466
0x180038462  xor     ebx, ebx
0x180038464  jmp     short loc_18003846E
0x180038466  test    eax, eax
0x180038468  jnz     loc_18003850A
0x18003846e  test    esi, esi
0x180038470  jz      short loc_180038491
0x180038472  lea     rdx, aRxbandwidthkbp; "RxBandwidthKbps"
0x180038479  mov     rcx, r14; hKey
0x18003847c  call    cs:__imp_RegDeleteValueW
0x180038482  mov     ebx, eax
0x180038484  cmp     eax, 2
0x180038487  jnz     short loc_18003848D
0x180038489  xor     ebx, ebx
0x18003848b  jmp     short loc_180038491
0x18003848d  test    eax, eax
0x18003848f  jnz     short loc_18003850A
0x180038491  xor     ebp, ebp
0x180038493  xor     esi, esi
0x180038495  mov     eax, ebx
0x180038497  cmp     esi, [rdi]
0x180038499  jnb     short loc_1800384FF
0x18003849b  lea     rdx, [rsi+rsi*2]
0x18003849f  mov     ecx, [rdi+rdx*4+8]
0x1800384a3  test    ecx, ecx
0x1800384a5  jnz     short loc_1800384B0
0x1800384a7  lea     rbp, aTxbandwidthkbp; "TxBandwidthKbps"
0x1800384ae  jmp     short loc_1800384C1
0x1800384b0  cmp     ecx, 1
0x1800384b3  lea     rax, aRxbandwidthkbp; "RxBandwidthKbps"
0x1800384ba  cmovnz  rax, rbp
0x1800384be  mov     rbp, rax
0x1800384c1  lea     rax, [rdi+4]
0x1800384c5  lea     rax, [rax+rdx*4]
0x1800384c9  cmp     dword ptr [rax], 0
0x1800384cc  jz      short loc_1800384FB
0x1800384ce  cmp     dword ptr [rax], 1
0x1800384d1  jb      short loc_180038505
0x1800384d3  mov     [rsp+858h+cbData], 4; cbData
0x1800384db  mov     r9d, 4; dwType
0x1800384e1  xor     r8d, r8d; Reserved
0x1800384e4  mov     [rsp+858h+lpData], rax; lpData
0x1800384e9  mov     rdx, rbp; lpValueName
0x1800384ec  mov     rcx, r14; hKey
0x1800384ef  call    cs:__imp_RegSetValueExW
0x1800384f5  mov     ebx, eax
0x1800384f7  test    eax, eax
0x1800384f9  jnz     short loc_18003850A
0x1800384fb  inc     esi
0x1800384fd  jmp     short loc_180038495
0x1800384ff  test    eax, eax
0x180038501  jz      short loc_180038555
0x180038503  jmp     short loc_18003850A
0x180038505  mov     ebx, 57h ; 'W'
0x18003850a  cmp     qword ptr cs:xmmword_180071090, 0
0x180038512  jz      short loc_180038555
0x180038514  xor     eax, eax
0x180038516  lea     r8, aWriteqospolici; "WriteQoSPoliciesToRegsitry"
0x18003851d  mov     r9d, ebx
0x180038520  mov     word ptr [rsp+858h+var_828], ax
0x180038525  lea     rdx, aSFailedD; "%s: failed: %d."
0x18003852c  lea     rcx, [rsp+858h+var_828]
0x180038531  call    FormatRRASErrorString
0x180038536  mov     rdx, qword ptr cs:xmmword_180071090
0x18003853d  lea     r8, [rsp+858h+var_828]
0x180038542  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180038549  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180038550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038555  mov     eax, ebx
0x180038557  mov     rcx, [rsp+858h+var_28]
0x18003855f  xor     rcx, rsp; StackCookie
0x180038562  call    __security_check_cookie
0x180038567  lea     r11, [rsp+858h+var_18]
0x18003856f  mov     rbx, [r11+30h]
0x180038573  mov     rbp, [r11+38h]
0x180038577  mov     rsp, r11
0x18003857a  pop     r14
0x18003857c  pop     rdi
0x18003857d  pop     rsi
0x18003857e  retn
```
