# WinHttpHelper::ReceiveResponse(char * *,ulong *)

- ea: `0x180020440`
- end: `0x1800206a0`
- name: `?ReceiveResponse@WinHttpHelper@@QEAAJPEAPEADPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(WinHttpHelper *__hidden this, char **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180052e0c`
- `0x18005363c`

## callees

- `0x18000dd20`
- `0x18000de50`
- `0x1800140d0`
- `0x180020440`
- `0x1800206a8`
- `0x180030fa5`
- `0x18003b118`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002064f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002064f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020659`
- `WINHTTP!WinHttpReadData` at `0x18002053d`
- `WINHTTP!WinHttpReadData` at `0x18002053d`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800204b5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180020606`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800204b5`
- `WINHTTP!WinHttpQueryHeaders` at `0x180020606`

## pseudocode

```c
__int64 __fastcall WinHttpHelper::ReceiveResponse(WinHttpHelper *this, char **a2, unsigned int *a3)
{
  void *v6; // rdi
  unsigned int v7; // esi
  void *v8; // rcx
  __int64 v9; // rdx
  signed int LastError; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  bool v13; // cf
  void *v14; // r14
  unsigned __int64 v15; // rcx
  int v16; // ebx
  DWORD dwNumberOfBytesRead; // [rsp+30h] [rbp-30h] BYREF
  DWORD dwBufferLength; // [rsp+34h] [rbp-2Ch] BYREF
  void *v20; // [rsp+38h] [rbp-28h] BYREF
  void *v21; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-18h] BYREF
  signed int v23; // [rsp+A0h] [rbp+40h] BYREF
  signed int Buffer; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v25; // [rsp+B8h] [rbp+58h] BYREF

  v22[0] = "WinHttpHelper::ReceiveResponse";
  v23 = 0;
  v22[1] = &v23;
  v21 = 0;
  v6 = 0;
  v20 = 0;
  v7 = 0;
  dwNumberOfBytesRead = 0;
  v25 = 0;
  *a3 = 0;
  do
  {
    v8 = (void *)*((_QWORD *)this + 2);
    Buffer = 0;
    dwBufferLength = 4;
    if ( !WinHttpQueryHeaders(v8, 0x20000005u, 0, &Buffer, &dwBufferLength, 0) )
      goto LABEL_29;
    if ( !Buffer )
      goto LABEL_22;
    v23 = ULongLongToULong(3LL * (unsigned int)Buffer, &v25);
    LastError = v23;
    if ( v23 < 0 )
      goto LABEL_34;
    v11 = v25;
    v9 = 0xFFFFFFFFLL;
    v12 = v25 + 1;
    v13 = v25 + 1 < v25;
    if ( v25 + 1 >= v25 )
      v9 = v12;
    LastError = v12 < v25 ? 0x80070216 : 0;
    v25 = v9;
    v23 = v13 ? 0x80070216 : 0;
    if ( v12 < v11 )
      goto LABEL_34;
    v14 = SafeHeapAlloc((unsigned int)v9);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v21);
    LastError = 0;
    v21 = v14;
    if ( !v14 )
      goto LABEL_25;
    if ( !WinHttpReadData(*((HINTERNET *)this + 2), v14, Buffer, &dwNumberOfBytesRead) )
      goto LABEL_29;
    if ( dwNumberOfBytesRead )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, DataReceivedEvent, (unsigned int)Buffer);
      if ( v7 )
        goto LABEL_27;
      v15 = (unsigned int)(Buffer + 1);
      if ( (unsigned int)v15 < Buffer )
      {
        LastError = -2147024362;
        v15 = 0xFFFFFFFFLL;
      }
      v25 = v15;
      v23 = LastError;
      if ( LastError < 0 )
        goto LABEL_34;
      v6 = SafeHeapAlloc(v15);
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v20);
      v20 = v6;
      if ( !v6 )
      {
LABEL_25:
        LastError = -2147024882;
        goto LABEL_33;
      }
      memcpy_0(v6, v14, (unsigned int)Buffer);
      v7 = Buffer;
      v23 = 0;
    }
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v21);
    if ( !Buffer )
      goto LABEL_22;
  }
  while ( dwNumberOfBytesRead );
  if ( !Buffer )
  {
LABEL_22:
    if ( WinHttpQueryHeaders(*((HINTERNET *)this + 2), 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
    {
      LastError = Buffer;
      if ( Buffer <= 0 )
        goto LABEL_33;
      v16 = (unsigned __int16)Buffer;
    }
    else
    {
LABEL_29:
      if ( (int)GetLastError() <= 0 )
      {
        LastError = GetLastError();
        goto LABEL_33;
      }
      v16 = (unsigned __int16)GetLastError();
    }
    LastError = v16 | 0x80190000;
    goto LABEL_33;
  }
  if ( v6 )
  {
    v20 = 0;
    *((_BYTE *)v6 + v7) = 0;
    LastError = v23;
    *a2 = (char *)v6;
    *a3 = v7;
    goto LABEL_34;
  }
LABEL_27:
  LastError = -2147467259;
LABEL_33:
  v23 = LastError;
LABEL_34:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v22, v9);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v20);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v21);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180020440  mov     [rsp-38h+arg_8], rbx
0x180020445  push    rbp
0x180020446  push    rsi
0x180020447  push    rdi
0x180020448  push    r12
0x18002044a  push    r13
0x18002044c  push    r14
0x18002044e  push    r15
0x180020450  mov     rbp, rsp
0x180020453  sub     rsp, 60h
0x180020457  xor     ebx, ebx
0x180020459  lea     rax, aWinhttphelperR; "WinHttpHelper::ReceiveResponse"
0x180020460  mov     [rbp+var_18], rax
0x180020464  mov     r12, r8
0x180020467  lea     rax, [rbp+arg_0]
0x18002046b  mov     [rbp+arg_0], ebx
0x18002046e  mov     [rbp+var_10], rax
0x180020472  mov     r13, rdx
0x180020475  mov     r15, rcx
0x180020478  mov     [rbp+var_20], rbx
0x18002047c  mov     edi, ebx
0x18002047e  mov     [rbp+var_28], rbx
0x180020482  mov     esi, ebx
0x180020484  mov     [rbp+dwNumberOfBytesRead], ebx
0x180020487  mov     [rbp+arg_18], ebx
0x18002048a  mov     [r8], ebx
0x18002048d  mov     rcx, [r15+10h]; hRequest
0x180020491  lea     rax, [rbp+dwBufferLength]
0x180020495  mov     [rsp+60h+lpdwIndex], rbx; lpdwIndex
0x18002049a  lea     r9, [rbp+Buffer]; lpBuffer
0x18002049e  xor     r8d, r8d; pwszName
0x1800204a1  mov     [rsp+60h+lpdwBufferLength], rax; lpdwBufferLength
0x1800204a6  mov     edx, 20000005h; dwInfoLevel
0x1800204ab  mov     [rbp+Buffer], ebx
0x1800204ae  mov     [rbp+dwBufferLength], 4
0x1800204b5  call    cs:__imp_WinHttpQueryHeaders
0x1800204bb  test    eax, eax
0x1800204bd  jz      loc_180020645
0x1800204c3  mov     eax, [rbp+Buffer]
0x1800204c6  test    eax, eax
0x1800204c8  jz      loc_1800205E8
0x1800204ce  lea     rcx, [rax+rax*2]; unsigned __int64
0x1800204d2  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800204d6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800204db  mov     [rbp+arg_0], eax
0x1800204de  mov     ebx, eax
0x1800204e0  test    eax, eax
0x1800204e2  js      loc_18002066B
0x1800204e8  mov     ecx, [rbp+arg_18]
0x1800204eb  or      edx, 0FFFFFFFFh
0x1800204ee  lea     eax, [rcx+1]
0x1800204f1  cmp     eax, ecx
0x1800204f3  cmovnb  edx, eax
0x1800204f6  sbb     ebx, ebx
0x1800204f8  and     ebx, 80070216h
0x1800204fe  mov     [rbp+arg_18], edx
0x180020501  mov     [rbp+arg_0], ebx
0x180020504  cmp     eax, ecx
0x180020506  jb      loc_18002066B
0x18002050c  mov     ecx, edx; unsigned __int64
0x18002050e  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180020513  lea     rcx, [rbp+var_20]
0x180020517  mov     r14, rax
0x18002051a  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18002051f  xor     ebx, ebx
0x180020521  mov     [rbp+var_20], r14
0x180020525  test    r14, r14
0x180020528  jz      loc_18002061C
0x18002052e  mov     r8d, [rbp+Buffer]; dwNumberOfBytesToRead
0x180020532  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180020536  mov     rcx, [r15+10h]; hRequest
0x18002053a  mov     rdx, r14; lpBuffer
0x18002053d  call    cs:__imp_WinHttpReadData
0x180020543  test    eax, eax
0x180020545  jz      loc_180020645
0x18002054b  cmp     [rbp+dwNumberOfBytesRead], ebx
0x18002054e  jz      short loc_1800205CB
0x180020550  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x180020557  jz      short loc_180020570
0x180020559  mov     r8d, [rbp+Buffer]
0x18002055d  lea     rdx, DataReceivedEvent
0x180020564  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002056b  call    McTemplateU0q_EventWriteTransfer
0x180020570  test    esi, esi
0x180020572  jnz     loc_180020628
0x180020578  mov     eax, [rbp+Buffer]
0x18002057b  lea     ecx, [rax+1]
0x18002057e  cmp     ecx, eax
0x180020580  jnb     short loc_18002058C
0x180020582  mov     ebx, 80070216h
0x180020587  mov     ecx, 0FFFFFFFFh; unsigned __int64
0x18002058c  mov     [rbp+arg_18], ecx
0x18002058f  mov     [rbp+arg_0], ebx
0x180020592  test    ebx, ebx
0x180020594  js      loc_18002066B
0x18002059a  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18002059f  lea     rcx, [rbp+var_28]
0x1800205a3  mov     rdi, rax
0x1800205a6  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800205ab  xor     ebx, ebx
0x1800205ad  mov     [rbp+var_28], rdi
0x1800205b1  test    rdi, rdi
0x1800205b4  jz      short loc_18002061C
0x1800205b6  mov     r8d, [rbp+Buffer]; Size
0x1800205ba  mov     rdx, r14; Src
0x1800205bd  mov     rcx, rdi; void *
0x1800205c0  call    memcpy_0
0x1800205c5  mov     esi, [rbp+Buffer]
0x1800205c8  mov     [rbp+arg_0], ebx
0x1800205cb  lea     rcx, [rbp+var_20]
0x1800205cf  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800205d4  mov     eax, [rbp+Buffer]
0x1800205d7  test    eax, eax
0x1800205d9  jz      short loc_1800205E8
0x1800205db  cmp     [rbp+dwNumberOfBytesRead], ebx
0x1800205de  jnz     loc_18002048D
0x1800205e4  test    eax, eax
0x1800205e6  jnz     short loc_180020623
0x1800205e8  mov     rcx, [r15+10h]; hRequest
0x1800205ec  lea     rax, [rbp+dwBufferLength]
0x1800205f0  mov     [rsp+60h+lpdwIndex], rbx; lpdwIndex
0x1800205f5  lea     r9, [rbp+Buffer]; lpBuffer
0x1800205f9  xor     r8d, r8d; pwszName
0x1800205fc  mov     [rsp+60h+lpdwBufferLength], rax; lpdwBufferLength
0x180020601  mov     edx, 20000013h; dwInfoLevel
0x180020606  call    cs:__imp_WinHttpQueryHeaders
0x18002060c  test    eax, eax
0x18002060e  jz      short loc_180020645
0x180020610  mov     ebx, [rbp+Buffer]
0x180020613  test    ebx, ebx
0x180020615  jle     short loc_180020668
0x180020617  movzx   ebx, bx
0x18002061a  jmp     short loc_180020662
0x18002061c  mov     ebx, 8007000Eh
0x180020621  jmp     short loc_180020668
0x180020623  test    rdi, rdi
0x180020626  jnz     short loc_18002062F
0x180020628  mov     ebx, 80004005h
0x18002062d  jmp     short loc_180020668
0x18002062f  mov     eax, esi
0x180020631  mov     [rbp+var_28], rbx
0x180020635  mov     [rax+rdi], bl
0x180020638  mov     ebx, [rbp+arg_0]
0x18002063b  mov     [r13+0], rdi
0x18002063f  mov     [r12], esi
0x180020643  jmp     short loc_18002066B
0x180020645  call    cs:__imp_GetLastError
0x18002064b  test    eax, eax
0x18002064d  jg      short loc_180020659
0x18002064f  call    cs:__imp_GetLastError
0x180020655  mov     ebx, eax
0x180020657  jmp     short loc_180020668
0x180020659  call    cs:__imp_GetLastError
0x18002065f  movzx   ebx, ax
0x180020662  or      ebx, 80190000h
0x180020668  mov     [rbp+arg_0], ebx
0x18002066b  lea     rcx, [rbp+var_18]; this
0x18002066f  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180020674  lea     rcx, [rbp+var_28]
0x180020678  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18002067d  lea     rcx, [rbp+var_20]
0x180020681  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180020686  mov     eax, ebx
0x180020688  mov     rbx, [rsp+60h+arg_8]
0x180020690  add     rsp, 60h
0x180020694  pop     r15
0x180020696  pop     r14
0x180020698  pop     r13
0x18002069a  pop     r12
0x18002069c  pop     rdi
0x18002069d  pop     rsi
0x18002069e  pop     rbp
0x18002069f  retn
```
