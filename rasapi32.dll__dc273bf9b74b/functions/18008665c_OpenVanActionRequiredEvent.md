# OpenVanActionRequiredEvent

- ea: `0x18008665c`
- end: `0x180086879`
- name: `OpenVanActionRequiredEvent`
- size: `541`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180087230`
- `0x18008d66c`
- `0x18008fec0`

## callees

- `0x18004e580`
- `0x18007e548`
- `0x18008665c`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!_wcsupr_s` at `0x18008677d`
- `msvcrt!_wcsupr_s` at `0x18008677d`
- `msvcrt!wcsncat_s` at `0x1800867c5`
- `msvcrt!wcsncat_s` at `0x1800867c5`
- `msvcrt!wcsncpy_s` at `0x180086754`
- `msvcrt!wcsncpy_s` at `0x180086770`
- `msvcrt!wcsncpy_s` at `0x180086754`
- `msvcrt!wcsncpy_s` at `0x180086770`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800867da`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800867da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800867e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800867e8`

## pseudocode

```c
__int64 __fastcall OpenVanActionRequiredEvent(__int64 a1, DWORD a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r9
  DWORD LastError; // eax
  HANDLE v12; // rax
  wchar_t String[264]; // [rsp+30h] [rbp-468h] BYREF
  wchar_t Destination[264]; // [rsp+240h] [rbp-258h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 577, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, a2, 1);
    v7 = WPP_GLOBAL_Control;
  }
  memset_0(Destination, 0, 0x208u);
  memset_0(String, 0, 0x202u);
  if ( a4 )
  {
    *a4 = 0;
    wcsncpy_s(Destination, 0x104u, L"Global\\Microsoft.Windows.RRAS.Van.ActionEvent.", 0xFFFFFFFFFFFFFFFFuLL);
    wcsncpy_s(String, 0x101u, (const wchar_t *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
    LastError = _wcsupr_s(String, 0x101u);
    v8 = LastError;
    if ( LastError )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      v9 = 579;
    }
    else
    {
      wcsncat_s(Destination, 0x104u, String, 0xFFFFFFFFFFFFFFFFuLL);
      v12 = OpenEventW(a2, 1, Destination);
      *a4 = v12;
      if ( v12 )
        goto LABEL_23;
      LastError = GetLastError();
      v8 = LastError;
      if ( !LastError )
        goto LABEL_23;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      v9 = 580;
    }
    v10 = LastError;
LABEL_22:
    WPP_SF_d(v7[2], v9, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v10);
LABEL_23:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_24;
  }
  v8 = 87;
  if ( v7 == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_DWORD *)v7 + 7) & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 2u )
  {
    v9 = 578;
    v10 = 87;
    goto LABEL_22;
  }
LABEL_24:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x800) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 581, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18008665c  mov     [rsp+arg_10], rbx
0x180086661  push    rbp
0x180086662  push    rsi
0x180086663  push    rdi
0x180086664  push    r12
0x180086666  push    r13
0x180086668  push    r14
0x18008666a  push    r15
0x18008666c  sub     rsp, 460h
0x180086673  mov     rax, cs:__security_cookie
0x18008667a  xor     rax, rsp
0x18008667d  mov     [rsp+498h+var_48], rax
0x180086685  mov     rsi, r9
0x180086688  mov     ebp, edx
0x18008668a  mov     rdi, rcx
0x18008668d  mov     rbx, cs:WPP_GLOBAL_Control
0x180086694  lea     r15, WPP_GLOBAL_Control
0x18008669b  lea     r12, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800866a2  mov     r14d, 800h
0x1800866a8  cmp     rbx, r15
0x1800866ab  jz      short loc_1800866D9
0x1800866ad  test    [rbx+1Ch], r14d
0x1800866b1  jz      short loc_1800866D9
0x1800866b3  cmp     byte ptr [rbx+19h], 6
0x1800866b7  jb      short loc_1800866D9
0x1800866b9  mov     rcx, [rbx+10h]
0x1800866bd  mov     edx, 241h
0x1800866c2  mov     r9d, ebp
0x1800866c5  mov     [rsp+498h+var_478], 1
0x1800866ca  mov     r8, r12
0x1800866cd  call    WPP_SF_Dc
0x1800866d2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800866d9  xor     edx, edx; Val
0x1800866db  lea     rcx, [rsp+498h+Destination]; void *
0x1800866e3  mov     r8d, 208h; Size
0x1800866e9  call    memset_0
0x1800866ee  xor     edx, edx; Val
0x1800866f0  lea     rcx, [rsp+498h+String]; void *
0x1800866f5  mov     r8d, 202h; Size
0x1800866fb  call    memset_0
0x180086700  test    rsi, rsi
0x180086703  jnz     short loc_180086732
0x180086705  lea     edi, [rsi+57h]
0x180086708  cmp     rbx, r15
0x18008670b  jz      loc_18008684C
0x180086711  test    [rbx+1Ch], r14d
0x180086715  jz      loc_180086827
0x18008671b  cmp     byte ptr [rbx+19h], 2
0x18008671f  jb      loc_180086827
0x180086725  mov     edx, 242h
0x18008672a  mov     r9d, edi
0x18008672d  jmp     loc_180086814
0x180086732  or      r13, 0FFFFFFFFFFFFFFFFh
0x180086736  mov     qword ptr [rsi], 0
0x18008673d  mov     r9, r13; MaxCount
0x180086740  lea     r8, aGlobalMicrosof_0; "Global\\Microsoft.Windows.RRAS.Van.Acti"...
0x180086747  mov     edx, 104h; SizeInWords
0x18008674c  lea     rcx, [rsp+498h+Destination]; Destination
0x180086754  call    cs:__imp_wcsncpy_s
0x18008675a  mov     ebx, 101h
0x18008675f  lea     r8, [rdi+130h]; Source
0x180086766  mov     edx, ebx; SizeInWords
0x180086768  lea     rcx, [rsp+498h+String]; Destination
0x18008676d  mov     r9, r13; MaxCount
0x180086770  call    cs:__imp_wcsncpy_s
0x180086776  mov     edx, ebx; Size
0x180086778  lea     rcx, [rsp+498h+String]; String
0x18008677d  call    cs:__imp__wcsupr_s
0x180086783  mov     edi, eax
0x180086785  test    eax, eax
0x180086787  jz      short loc_1800867B0
0x180086789  mov     rbx, cs:WPP_GLOBAL_Control
0x180086790  cmp     rbx, r15
0x180086793  jz      loc_18008684C
0x180086799  test    [rbx+1Ch], r14d
0x18008679d  jz      loc_180086827
0x1800867a3  cmp     byte ptr [rbx+19h], 2
0x1800867a7  jb      short loc_180086827
0x1800867a9  mov     edx, 243h
0x1800867ae  jmp     short loc_180086811
0x1800867b0  mov     r9, r13; MaxCount
0x1800867b3  lea     r8, [rsp+498h+String]; Source
0x1800867b8  mov     edx, 104h; SizeInWords
0x1800867bd  lea     rcx, [rsp+498h+Destination]; Destination
0x1800867c5  call    cs:__imp_wcsncat_s
0x1800867cb  lea     r8, [rsp+498h+Destination]; lpName
0x1800867d3  mov     edx, 1; bInheritHandle
0x1800867d8  mov     ecx, ebp; dwDesiredAccess
0x1800867da  call    cs:__imp_OpenEventW
0x1800867e0  mov     [rsi], rax
0x1800867e3  test    rax, rax
0x1800867e6  jnz     short loc_180086820
0x1800867e8  call    cs:__imp_GetLastError
0x1800867ee  mov     edi, eax
0x1800867f0  test    eax, eax
0x1800867f2  jz      short loc_180086820
0x1800867f4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800867fb  cmp     rbx, r15
0x1800867fe  jz      short loc_18008684C
0x180086800  test    [rbx+1Ch], r14d
0x180086804  jz      short loc_180086827
0x180086806  cmp     byte ptr [rbx+19h], 2
0x18008680a  jb      short loc_180086827
0x18008680c  mov     edx, 244h
0x180086811  mov     r9d, eax
0x180086814  mov     rcx, [rbx+10h]
0x180086818  mov     r8, r12
0x18008681b  call    WPP_SF_d
0x180086820  mov     rbx, cs:WPP_GLOBAL_Control
0x180086827  cmp     rbx, r15
0x18008682a  jz      short loc_18008684C
0x18008682c  test    [rbx+1Ch], r14d
0x180086830  jz      short loc_18008684C
0x180086832  cmp     byte ptr [rbx+19h], 6
0x180086836  jb      short loc_18008684C
0x180086838  mov     rcx, [rbx+10h]
0x18008683c  mov     edx, 245h
0x180086841  mov     r9d, edi
0x180086844  mov     r8, r12
0x180086847  call    WPP_SF_d
0x18008684c  mov     eax, edi
0x18008684e  mov     rcx, [rsp+498h+var_48]
0x180086856  xor     rcx, rsp; StackCookie
0x180086859  call    __security_check_cookie
0x18008685e  mov     rbx, [rsp+498h+arg_10]
0x180086866  add     rsp, 460h
0x18008686d  pop     r15
0x18008686f  pop     r14
0x180086871  pop     r13
0x180086873  pop     r12
0x180086875  pop     rdi
0x180086876  pop     rsi
0x180086877  pop     rbp
0x180086878  retn
```
