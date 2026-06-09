# VerifyCallerMembership(WELL_KNOWN_SID_TYPE)

- ea: `0x180025d78`
- end: `0x180025e66`
- name: `?VerifyCallerMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(enum WELL_KNOWN_SID_TYPE)`
- caller_count: `16`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002d7b0`
- `0x18003a2e0`
- `0x18003a540`
- `0x18003af80`
- `0x18003b3b0`
- `0x18003b970`
- `0x18003be80`
- `0x18003f150`
- `0x1800409c0`
- `0x180041af0`
- `0x1800420d0`
- `0x1800450d0`
- `0x1800451e0`
- `0x180045300`
- `0x180045910`
- `0x180045b80`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180025d78`
- `0x180025e6c`
- `0x180027cd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025de7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025dc0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180025dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025dab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025dab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025e42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VerifyCallerMembership(enum WELL_KNOWN_SID_TYPE a1)
{
  HANDLE CurrentThread; // rax
  enum WELL_KNOWN_SID_TYPE v2; // edx
  signed int v3; // ebx
  bool v4; // sf
  __int16 v5; // ax
  signed int LastError; // eax
  enum WELL_KNOWN_SID_TYPE v7; // ecx
  signed int v9; // [rsp+20h] [rbp-40h] BYREF
  __int16 v10; // [rsp+24h] [rbp-3Ch]
  __int16 v11; // [rsp+26h] [rbp-3Ah]
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "VerifyCallerMembership", 0x15Du, 1u);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
  {
    v3 = VerifyTokenMembership(TokenHandle, v2);
    v9 = v3;
    v4 = v3 < 0;
    v5 = 360;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v9 = v3;
      v5 = 365;
      goto LABEL_4;
    }
    v9 = 0;
    v10 = 365;
    v3 = VerifyClientMembership(v7);
    v9 = v3;
    v4 = v3 < 0;
    v5 = 366;
  }
  if ( v4 )
  {
LABEL_4:
    v11 = v5;
    goto LABEL_11;
  }
  v10 = v5;
LABEL_11:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180025d78  mov     [rsp-8+arg_0], rbx
0x180025d7d  push    rbp
0x180025d7e  mov     rbp, rsp
0x180025d81  sub     rsp, 60h
0x180025d85  mov     ebx, 1
0x180025d8a  lea     rdx, aVerifycallerme; "VerifyCallerMembership"
0x180025d91  mov     r9d, ebx; unsigned __int16
0x180025d94  lea     rcx, [rbp+var_40]; this
0x180025d98  mov     r8d, 15Dh; unsigned __int16
0x180025d9e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180025da3  mov     [rbp+TokenHandle], 0
0x180025dab  call    cs:__imp_GetCurrentThread
0x180025db1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180025db5  mov     r8d, ebx; OpenAsSelf
0x180025db8  mov     rcx, rax; ThreadHandle
0x180025dbb  mov     edx, 2000Ch; DesiredAccess
0x180025dc0  call    cs:__imp_OpenThreadToken
0x180025dc6  test    eax, eax
0x180025dc8  jz      short loc_180025DE7
0x180025dca  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180025dce  call    ?VerifyTokenMembership@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@@Z; VerifyTokenMembership(void *,WELL_KNOWN_SID_TYPE)
0x180025dd3  mov     ebx, eax
0x180025dd5  mov     [rbp+var_40], eax
0x180025dd8  test    eax, eax
0x180025dda  mov     eax, 168h
0x180025ddf  jns     short loc_180025E30
0x180025de1  mov     [rbp+var_3A], ax
0x180025de5  jmp     short loc_180025E34
0x180025de7  call    cs:__imp_GetLastError
0x180025ded  mov     ebx, eax
0x180025def  cmp     eax, 3F0h
0x180025df4  jz      short loc_180025E0D
0x180025df6  test    eax, eax
0x180025df8  jle     short loc_180025E03
0x180025dfa  movzx   ebx, ax
0x180025dfd  or      ebx, 80070000h
0x180025e03  mov     [rbp+var_40], ebx
0x180025e06  mov     eax, 16Dh
0x180025e0b  jmp     short loc_180025DE1
0x180025e0d  mov     eax, 16Dh
0x180025e12  mov     [rbp+var_40], 0
0x180025e19  mov     [rbp+var_3C], ax
0x180025e1d  call    ?VerifyClientMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z; VerifyClientMembership(WELL_KNOWN_SID_TYPE)
0x180025e22  mov     ebx, eax
0x180025e24  mov     [rbp+var_40], eax
0x180025e27  test    eax, eax
0x180025e29  mov     eax, 16Eh
0x180025e2e  jmp     short loc_180025DDF
0x180025e30  mov     [rbp+var_3C], ax
0x180025e34  mov     rcx, [rbp+TokenHandle]; hObject
0x180025e38  lea     rdx, [rcx-1]
0x180025e3c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180025e40  ja      short loc_180025E50
0x180025e42  call    cs:__imp_CloseHandle
0x180025e48  mov     [rbp+TokenHandle], 0
0x180025e50  lea     rcx, [rbp+var_40]; this
0x180025e54  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180025e59  mov     eax, ebx
0x180025e5b  mov     rbx, [rsp+60h+arg_0]
0x180025e60  add     rsp, 60h
0x180025e64  pop     rbp
0x180025e65  retn
```
