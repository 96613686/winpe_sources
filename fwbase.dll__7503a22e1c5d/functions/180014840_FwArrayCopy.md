# FwArrayCopy

- ea: `0x180014840`
- end: `0x180014b65`
- name: `FwArrayCopy`
- size: `805`
- prototype: `__int64 __fastcall(unsigned __int64, __int64 (__fastcall *)(unsigned __int64, unsigned __int64), void (__fastcall *)(char *), unsigned int *, _OWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a900`
- `0x18002abe0`

## callees

- `0x180014268`
- `0x180014840`
- `0x180017b58`
- `0x1800293a0`
- `0x18002f43c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014944`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014944`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014962`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b13`

## string_xrefs

- `0x180014914`: `FwArrayCopy`
- `0x18001499a`: `FwArrayCopy`
- `0x180014a52`: `FwArrayCopy`
- `0x180014b3d`: `FwArrayCopy`

## pseudocode

```c
__int64 __fastcall FwArrayCopy(
        unsigned __int64 a1,
        __int64 (__fastcall *a2)(unsigned __int64, unsigned __int64),
        void (__fastcall *a3)(char *),
        unsigned int *a4,
        _OWORD *a5)
{
  unsigned int v5; // ebx
  char *v6; // rdi
  unsigned __int64 v10; // rdx
  int v11; // r8d
  int v12; // r14d
  unsigned int v13; // eax
  __int128 v14; // xmm1
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v17; // r15d
  int v18; // eax
  unsigned int v19; // esi
  HANDLE v20; // rax
  __int128 v22; // [rsp+30h] [rbp-68h]

  v5 = 0;
  v6 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a4 || *a4 && !*((_QWORD *)a4 + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl)
    || a4 && (!*a4 || *((_QWORD *)a4 + 1)) )
  {
    v12 = 0;
    *a5 = 0;
    v14 = 0;
    *(_QWORD *)&v22 = 0;
    if ( *a4 )
    {
      v13 = *a4;
      if ( a1 )
      {
        v10 = 0xFFFFFFFFFFFFFFFFuLL % a1;
        if ( v13 > 0xFFFFFFFFFFFFFFFFuLL / a1 )
        {
          v12 = -2147024362;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (unsigned int)"FwArrayCopy", 22);
          v6 = 0;
          v5 = 0;
          goto LABEL_42;
        }
      }
      v15 = a1 * v13;
      if ( !v15 )
      {
        SetLastError(0x57u);
        v6 = 0;
        goto LABEL_22;
      }
      ProcessHeap = GetProcessHeap();
      *((_QWORD *)&v22 + 1) = HeapAlloc(ProcessHeap, 8u, v15);
      v6 = (char *)*((_QWORD *)&v22 + 1);
      if ( !*((_QWORD *)&v22 + 1) )
      {
LABEL_22:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_ssL(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (unsigned int)"FwArrayCopy", (__int64)"FwAlloc", 8);
        v5 = 0;
        v12 = -2147024888;
        goto LABEL_42;
      }
      v5 = 0;
      v17 = 0;
      if ( *a4 )
      {
        while ( 1 )
        {
          if ( !a1 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          if ( *a4 && !*((_QWORD *)a4 + 1) )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( v17 >= *a4 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v18 = a2(*((_QWORD *)a4 + 1) + a1 * v17, *((_QWORD *)&v22 + 1) + a1 * v5);
          v12 = v18;
          if ( v18 < 0 )
            break;
          ++v5;
          ++v17;
          LODWORD(v22) = v5;
          if ( v17 >= *a4 )
            goto LABEL_36;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (unsigned int)"FwArrayCopy", v18);
        goto LABEL_42;
      }
LABEL_36:
      v14 = v22;
    }
    else
    {
      v6 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v5 = _mm_cvtsi128_si32((__m128i)0LL);
    }
    *a5 = v14;
    if ( v12 >= 0 )
      return (unsigned int)v12;
    goto LABEL_42;
  }
  v12 = -2147024809;
LABEL_42:
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v5 )
  {
    if ( !v6 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v19 = 0;
    if ( a1 )
    {
      do
      {
        if ( !v6 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v19 >= v5 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        a3(&v6[a1 * v19++]);
      }
      while ( v19 < v5 );
    }
    else
    {
      do
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( !v6 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( v19 >= v5 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        a3(&v6[a1 * v19++]);
      }
      while ( v19 < v5 );
    }
  }
  if ( v6 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (unsigned int)"FwArrayCopy", v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014840  push    rbx
0x180014842  push    rbp
0x180014843  push    rsi
0x180014844  push    rdi
0x180014845  push    r12
0x180014847  push    r13
0x180014849  push    r15
0x18001484b  sub     rsp, 60h
0x18001484f  mov     r13, [rsp+98h+arg_20]
0x180014857  xor     eax, eax
0x180014859  xor     ebx, ebx
0x18001485b  mov     [rsp+98h+var_58], rdx
0x180014860  xor     edi, edi
0x180014862  mov     dword ptr [rsp+98h+var_68+4], eax
0x180014866  mov     rsi, r9
0x180014869  mov     r12, r8
0x18001486c  mov     rbp, rcx
0x18001486f  test    rcx, rcx
0x180014872  jnz     short loc_180014879
0x180014874  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x180014879  test    rsi, rsi
0x18001487c  jz      short loc_180014888
0x18001487e  cmp     [rsi], ebx
0x180014880  jz      short loc_18001488D
0x180014882  cmp     [rsi+8], rbx
0x180014886  jnz     short loc_18001488D
0x180014888  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FwArrayIsValid(src)")
0x18001488d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x180014894  mov     [rsp+98h+var_40], r14
0x180014899  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18001489e  lea     r15, WPP_GLOBAL_Control
0x1800148a5  test    al, al
0x1800148a7  jz      short loc_1800148C3
0x1800148a9  test    rsi, rsi
0x1800148ac  jz      short loc_1800148B8
0x1800148ae  cmp     [rsi], ebx
0x1800148b0  jz      short loc_1800148C3
0x1800148b2  cmp     [rsi+8], rbx
0x1800148b6  jnz     short loc_1800148C3
0x1800148b8  mov     r14d, 80070057h
0x1800148be  jmp     loc_180014A80
0x1800148c3  xorps   xmm0, xmm0
0x1800148c6  xor     r14d, r14d
0x1800148c9  movups  xmmword ptr [r13+0], xmm0
0x1800148ce  mov     eax, [rsi]
0x1800148d0  xorps   xmm1, xmm1
0x1800148d3  movups  xmmword ptr [rsp+30h], xmm1
0x1800148d8  test    eax, eax
0x1800148da  jz      loc_180014A64
0x1800148e0  mov     ebx, eax
0x1800148e2  test    rbp, rbp
0x1800148e5  jz      short loc_180014936
0x1800148e7  xor     edx, edx
0x1800148e9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800148f0  div     rbp
0x1800148f3  cmp     rbx, rax
0x1800148f6  jbe     short loc_180014936
0x1800148f8  mov     r14d, 80070216h
0x1800148fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014905  cmp     rcx, r15
0x180014908  jz      short loc_180014928
0x18001490a  test    byte ptr [rcx+1Ch], 1
0x18001490e  jz      short loc_180014928
0x180014910  mov     rcx, [rcx+10h]
0x180014914  lea     r9, aFwarraycopy_0; "FwArrayCopy"
0x18001491b  mov     dword ptr [rsp+98h+var_78], 80070216h
0x180014923  call    WPP_SF_sD
0x180014928  mov     rdi, qword ptr [rsp+98h+var_68+8]
0x18001492d  mov     ebx, dword ptr [rsp+98h+var_68]
0x180014931  jmp     loc_180014A80
0x180014936  imul    rbx, rbp
0x18001493a  test    rbx, rbx
0x18001493d  jnz     short loc_180014951
0x18001493f  mov     ecx, 57h ; 'W'; dwErrCode
0x180014944  call    cs:__imp_SetLastError
0x18001494a  mov     rdi, qword ptr [rsp+98h+var_68+8]
0x18001494f  jmp     short loc_180014975
0x180014951  call    cs:__imp_GetProcessHeap
0x180014957  mov     r8, rbx; dwBytes
0x18001495a  mov     edx, 8; dwFlags
0x18001495f  mov     rcx, rax; hHeap
0x180014962  call    cs:__imp_HeapAlloc
0x180014968  mov     qword ptr [rsp+98h+var_68+8], rax
0x18001496d  mov     rdi, rax
0x180014970  test    rax, rax
0x180014973  jnz     short loc_1800149BA
0x180014975  mov     rcx, cs:WPP_GLOBAL_Control
0x18001497c  cmp     rcx, r15
0x18001497f  jz      short loc_1800149AB
0x180014981  test    byte ptr [rcx+1Ch], 1
0x180014985  jz      short loc_1800149AB
0x180014987  mov     rcx, [rcx+10h]
0x18001498b  lea     rax, aFwalloc_0; "FwAlloc"
0x180014992  mov     [rsp+98h+var_70], 8
0x18001499a  lea     r9, aFwarraycopy_0; "FwArrayCopy"
0x1800149a1  mov     [rsp+98h+var_78], rax
0x1800149a6  call    WPP_SF_ssL
0x1800149ab  mov     ebx, dword ptr [rsp+98h+var_68]
0x1800149af  mov     r14d, 80070008h
0x1800149b5  jmp     loc_180014A80
0x1800149ba  mov     ebx, dword ptr [rsp+98h+var_68]
0x1800149be  xor     r15d, r15d
0x1800149c1  cmp     [rsi], r14d
0x1800149c4  jbe     short loc_180014A27
0x1800149c6  test    rbp, rbp
0x1800149c9  jnz     short loc_1800149D5
0x1800149cb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x1800149d0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x1800149d5  mov     r14d, ebx
0x1800149d8  imul    r14, rbp
0x1800149dc  add     r14, rdi
0x1800149df  cmp     dword ptr [rsi], 0
0x1800149e2  jz      short loc_1800149F0
0x1800149e4  cmp     qword ptr [rsi+8], 0
0x1800149e9  jnz     short loc_1800149F0
0x1800149eb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FwArrayIsValid(array)")
0x1800149f0  cmp     r15d, [rsi]
0x1800149f3  jb      short loc_1800149FA
0x1800149f5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "index < array->numElements")
0x1800149fa  mov     rax, [rsp+98h+var_58]
0x1800149ff  mov     rdx, r14
0x180014a02  mov     ecx, r15d
0x180014a05  imul    rcx, rbp
0x180014a09  add     rcx, [rsi+8]
0x180014a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a12  mov     r14d, eax
0x180014a15  test    eax, eax
0x180014a17  js      short loc_180014A35
0x180014a19  inc     ebx
0x180014a1b  inc     r15d
0x180014a1e  mov     dword ptr [rsp+98h+var_68], ebx
0x180014a22  cmp     r15d, [rsi]
0x180014a25  jb      short loc_1800149C6
0x180014a27  movups  xmm1, [rsp+98h+var_68]
0x180014a2c  lea     r15, WPP_GLOBAL_Control
0x180014a33  jmp     short loc_180014A72
0x180014a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a3c  lea     r15, WPP_GLOBAL_Control
0x180014a43  cmp     rcx, r15
0x180014a46  jz      short loc_180014A80
0x180014a48  test    byte ptr [rcx+1Ch], 1
0x180014a4c  jz      short loc_180014A80
0x180014a4e  mov     rcx, [rcx+10h]
0x180014a52  lea     r9, aFwarraycopy_0; "FwArrayCopy"
0x180014a59  mov     dword ptr [rsp+98h+var_78], eax
0x180014a5d  call    WPP_SF_sD
0x180014a62  jmp     short loc_180014A80
0x180014a64  psrldq  xmm0, 8
0x180014a69  movq    rdi, xmm0
0x180014a6e  movd    ebx, xmm1
0x180014a72  movups  xmmword ptr [r13+0], xmm1
0x180014a77  test    r14d, r14d
0x180014a7a  jns     loc_180014B4E
0x180014a80  test    rbp, rbp
0x180014a83  jnz     short loc_180014A8A
0x180014a85  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x180014a8a  test    ebx, ebx
0x180014a8c  jz      loc_180014B0E
0x180014a92  test    rdi, rdi
0x180014a95  jnz     short loc_180014A9C
0x180014a97  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FwArrayIsValid(array)")
0x180014a9c  test    ebx, ebx
0x180014a9e  jz      short loc_180014B0E
0x180014aa0  xor     esi, esi
0x180014aa2  test    rbp, rbp
0x180014aa5  jnz     short loc_180014AE0
0x180014aa7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x180014aac  test    ebx, ebx
0x180014aae  jz      short loc_180014ABA
0x180014ab0  test    rdi, rdi
0x180014ab3  jnz     short loc_180014ABA
0x180014ab5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FwArrayIsValid(array)")
0x180014aba  cmp     esi, ebx
0x180014abc  jb      short loc_180014AC3
0x180014abe  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "index < array->numElements")
0x180014ac3  mov     ecx, esi
0x180014ac5  mov     rax, r12
0x180014ac8  imul    rcx, rbp
0x180014acc  add     rcx, rdi
0x180014acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ad4  inc     esi
0x180014ad6  cmp     esi, ebx
0x180014ad8  jb      short loc_180014AA7
0x180014ada  jmp     short loc_180014B0E
0x180014ae0  test    ebx, ebx
0x180014ae2  jz      short loc_180014AEE
0x180014ae4  test    rdi, rdi
0x180014ae7  jnz     short loc_180014AEE
0x180014ae9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014aee  cmp     esi, ebx
0x180014af0  jb      short loc_180014AF7
0x180014af2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014af7  mov     ecx, esi
0x180014af9  mov     rax, r12
0x180014afc  imul    rcx, rbp
0x180014b00  add     rcx, rdi
0x180014b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b08  inc     esi
0x180014b0a  cmp     esi, ebx
0x180014b0c  jb      short loc_180014AE0
0x180014b0e  test    rdi, rdi
0x180014b11  jz      short loc_180014B27
0x180014b13  call    cs:__imp_GetProcessHeap
0x180014b19  mov     r8, rdi; lpMem
0x180014b1c  xor     edx, edx; dwFlags
0x180014b1e  mov     rcx, rax; hHeap
0x180014b21  call    cs:__imp_HeapFree
0x180014b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b2e  cmp     rcx, r15
0x180014b31  jz      short loc_180014B4E
0x180014b33  test    byte ptr [rcx+1Ch], 1
0x180014b37  jz      short loc_180014B4E
0x180014b39  mov     rcx, [rcx+10h]
0x180014b3d  lea     r9, aFwarraycopy_0; "FwArrayCopy"
0x180014b44  mov     dword ptr [rsp+98h+var_78], r14d
0x180014b49  call    WPP_SF_sD
0x180014b4e  mov     eax, r14d
0x180014b51  mov     r14, [rsp+98h+var_40]
0x180014b56  add     rsp, 60h
0x180014b5a  pop     r15
0x180014b5c  pop     r13
0x180014b5e  pop     r12
0x180014b60  pop     rdi
0x180014b61  pop     rsi
0x180014b62  pop     rbp
0x180014b63  pop     rbx
0x180014b64  retn
```
