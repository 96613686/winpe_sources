# AsyncDriverRequest

- ea: `0x180088d74`
- end: `0x1800890a9`
- name: `AsyncDriverRequest`
- size: `821`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpMem)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18008b5f8`
- `0x18008b828`
- `0x18008c2d8`
- `0x18008d130`

## callees

- `0x1800755b8`
- `0x180088d74`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180088f05`
- `KERNEL32!DeleteCriticalSection` at `0x180089043`
- `KERNEL32!DeleteCriticalSection` at `0x180088f05`
- `KERNEL32!DeleteCriticalSection` at `0x180089043`
- `KERNEL32!DeviceIoControl` at `0x180088ed0`
- `KERNEL32!DeviceIoControl` at `0x180088ed0`
- `KERNEL32!GetProcessHeap` at `0x180088f11`
- `KERNEL32!GetProcessHeap` at `0x18008904f`
- `KERNEL32!GetProcessHeap` at `0x180088f11`
- `KERNEL32!GetProcessHeap` at `0x18008904f`
- `KERNEL32!GetLastError` at `0x180088f4b`
- `KERNEL32!GetLastError` at `0x180088f4b`
- `KERNEL32!LeaveCriticalSection` at `0x180088e9c`
- `KERNEL32!LeaveCriticalSection` at `0x180088ef6`
- `KERNEL32!LeaveCriticalSection` at `0x180088f36`
- `KERNEL32!LeaveCriticalSection` at `0x180089034`
- `KERNEL32!LeaveCriticalSection` at `0x180089071`
- `KERNEL32!LeaveCriticalSection` at `0x180088e9c`
- `KERNEL32!LeaveCriticalSection` at `0x180088ef6`
- `KERNEL32!LeaveCriticalSection` at `0x180088f36`
- `KERNEL32!LeaveCriticalSection` at `0x180089034`
- `KERNEL32!LeaveCriticalSection` at `0x180089071`
- `KERNEL32!EnterCriticalSection` at `0x180088e8a`
- `KERNEL32!EnterCriticalSection` at `0x180088ee1`
- `KERNEL32!EnterCriticalSection` at `0x18008901f`
- `KERNEL32!EnterCriticalSection` at `0x180088e8a`
- `KERNEL32!EnterCriticalSection` at `0x180088ee1`
- `KERNEL32!EnterCriticalSection` at `0x18008901f`
- `KERNEL32!HeapFree` at `0x180088f25`
- `KERNEL32!HeapFree` at `0x180089063`
- `KERNEL32!HeapFree` at `0x180088f25`
- `KERNEL32!HeapFree` at `0x180089063`
- `rtutils!TracePrintfA` at `0x180088e71`
- `rtutils!TracePrintfA` at `0x180088fe4`
- `rtutils!TracePrintfA` at `0x180088e71`
- `rtutils!TracePrintfA` at `0x180088fe4`

## pseudocode

```c
void __fastcall AsyncDriverRequest(DWORD dwIoControlCode, char *lpMem)
{
  char *lpOverlapped; // rdi
  _DWORD *lpOutBuffer; // rsi
  __int64 v5; // r9
  int v6; // eax
  char *v7; // r8
  DWORD v8; // ebx
  BOOL v9; // ebx
  bool v10; // zf
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  int v14; // ecx
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  HANDLE v16; // rax
  int nOutBufferSize; // [rsp+28h] [rbp-870h]
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-858h] BYREF
  int v19; // [rsp+50h] [rbp-848h] BYREF
  _BYTE v20[2044]; // [rsp+54h] [rbp-844h] BYREF

  lpOverlapped = lpMem;
  lpOutBuffer = lpMem + 104;
  BytesReturned[0] = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      v5 = (unsigned int)lpOutBuffer[9];
      nOutBufferSize = lpOutBuffer[13];
      v6 = lpOutBuffer[12];
      v7 = off_180096DC0[lpOutBuffer[8] - 117637377];
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"AsyncDriverRequest: Oid(%hs), devID(0x%x), reqID(0x%x), hCall(0x%x)",
        v7,
        v5,
        v6,
        nOutBufferSize);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v19);
    }
  }
  else if ( dwTraceId != -1 )
  {
    TracePrintfA(
      dwTraceId,
      "AsyncDriverRequest: Oid(%hs), devID(0x%x), reqID(0x%x), hCall(0x%x)",
      off_180096DC0[lpOutBuffer[8] - 117637377],
      lpOutBuffer[9],
      lpOutBuffer[12],
      lpOutBuffer[13]);
  }
  v8 = lpOutBuffer[10] + 55;
  EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  ++*((_DWORD *)lpOverlapped + 22);
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  v9 = DeviceIoControl(
         g_hDriverAsync,
         dwIoControlCode,
         lpOutBuffer,
         v8,
         lpOutBuffer,
         v8,
         BytesReturned,
         (LPOVERLAPPED)lpOverlapped);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
  v10 = (*((_DWORD *)lpOverlapped + 22))-- == 1;
  v11 = (struct _RTL_CRITICAL_SECTION *)(lpOverlapped + 48);
  if ( v10 )
  {
    LeaveCriticalSection(v11);
    DeleteCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpOverlapped);
    lpOverlapped = 0;
  }
  else
  {
    LeaveCriticalSection(v11);
  }
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          v14 = lpOutBuffer[8] - 117637377;
          LOWORD(v19) = 0;
          FormatRRASErrorString(
            &v19,
            L"AsyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
            off_180096DC0[v14],
            LastError);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v19);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "AsyncDriverRequest: IoCtl (Oid %hs) failed (0x%x)",
          off_180096DC0[lpOutBuffer[8] - 117637377],
          LastError);
      }
      ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, __int64, _QWORD))g_pfnCallback)(
        0,
        12,
        0,
        (unsigned int)lpOutBuffer[12],
        2147483720LL,
        0);
      EnterCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
      v10 = (*((_DWORD *)lpOverlapped + 22))-- == 1;
      v15 = (struct _RTL_CRITICAL_SECTION *)(lpOverlapped + 48);
      if ( v10 )
      {
        LeaveCriticalSection(v15);
        DeleteCriticalSection((LPCRITICAL_SECTION)(lpOverlapped + 48));
        v16 = GetProcessHeap();
        HeapFree(v16, 0, lpOverlapped);
      }
      else
      {
        LeaveCriticalSection(v15);
      }
    }
  }
}

```

## disassembly

```asm
0x180088d74  mov     [rsp+arg_10], rbx
0x180088d79  push    rbp
0x180088d7a  push    rsi
0x180088d7b  push    rdi
0x180088d7c  push    r12
0x180088d7e  push    r13
0x180088d80  push    r14
0x180088d82  push    r15
0x180088d84  sub     rsp, 860h
0x180088d8b  mov     rax, cs:__security_cookie
0x180088d92  xor     rax, rsp
0x180088d95  mov     [rsp+898h+var_48], rax
0x180088d9d  mov     rdi, rdx
0x180088da0  lea     rsi, [rdx+68h]
0x180088da4  mov     r14d, ecx
0x180088da7  xor     r15d, r15d
0x180088daa  xor     edx, edx; Val
0x180088dac  mov     [rsp+898h+BytesReturned], r15d
0x180088db1  lea     rcx, [rsp+898h+var_844]; void *
0x180088db6  mov     [rsp+898h+var_848], r15d
0x180088dbb  mov     r8d, 7FCh; Size
0x180088dc1  call    memset_0
0x180088dc6  or      r12d, 0FFFFFFFFh
0x180088dca  lea     rdx, off_180096DC0; "Accept"
0x180088dd1  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180088dd8  mov     r13d, 7030101h
0x180088dde  jz      short loc_180088E42
0x180088de0  cmp     qword ptr cs:xmmword_1800D0BE0, r15
0x180088de7  jz      loc_180088E7D
0x180088ded  mov     r8d, [rsi+20h]
0x180088df1  lea     rcx, [rsp+898h+var_848]
0x180088df6  mov     eax, [rsi+34h]
0x180088df9  sub     r8d, r13d
0x180088dfc  mov     r9d, [rsi+24h]
0x180088e00  mov     [rsp+898h+nOutBufferSize], eax
0x180088e04  mov     eax, [rsi+30h]
0x180088e07  mov     r8, [rdx+r8*8]
0x180088e0b  lea     rdx, aAsyncdriverreq; "AsyncDriverRequest: Oid(%hs), devID(0x%"...
0x180088e12  mov     word ptr [rsp+898h+var_848], r15w
0x180088e18  mov     dword ptr [rsp+898h+lpOutBuffer], eax
0x180088e1c  call    FormatRRASErrorString
0x180088e21  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x180088e28  lea     r8, [rsp+898h+var_848]
0x180088e2d  mov     rcx, cs:gNdpspEtwContext
0x180088e34  mov     rax, cs:gNdpspTemplateFunc
0x180088e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e40  jmp     short loc_180088E7D
0x180088e42  mov     ecx, cs:dwTraceId; dwTraceID
0x180088e48  cmp     ecx, r12d
0x180088e4b  jz      short loc_180088E7D
0x180088e4d  mov     r8d, [rsi+20h]
0x180088e51  mov     eax, [rsi+34h]
0x180088e54  sub     r8d, r13d
0x180088e57  mov     r9d, [rsi+24h]
0x180088e5b  mov     [rsp+898h+nOutBufferSize], eax
0x180088e5f  mov     eax, [rsi+30h]
0x180088e62  mov     r8, [rdx+r8*8]
0x180088e66  lea     rdx, szFormat; "AsyncDriverRequest: Oid(%hs), devID(0x%"...
0x180088e6d  mov     dword ptr [rsp+898h+lpOutBuffer], eax
0x180088e71  call    cs:__imp_TracePrintfA
0x180088e78  nop     dword ptr [rax+rax+00h]
0x180088e7d  mov     ebx, [rsi+28h]
0x180088e80  lea     rbp, [rdi+30h]
0x180088e84  mov     rcx, rbp; lpCriticalSection
0x180088e87  add     ebx, 37h ; '7'
0x180088e8a  call    cs:__imp_EnterCriticalSection
0x180088e91  nop     dword ptr [rax+rax+00h]
0x180088e96  inc     dword ptr [rdi+58h]
0x180088e99  mov     rcx, rbp; lpCriticalSection
0x180088e9c  call    cs:__imp_LeaveCriticalSection
0x180088ea3  nop     dword ptr [rax+rax+00h]
0x180088ea8  mov     rcx, cs:g_hDriverAsync; hDevice
0x180088eaf  lea     rax, [rsp+898h+BytesReturned]
0x180088eb4  mov     [rsp+898h+lpOverlapped], rdi; lpOverlapped
0x180088eb9  mov     r9d, ebx; nInBufferSize
0x180088ebc  mov     [rsp+898h+lpBytesReturned], rax; lpBytesReturned
0x180088ec1  mov     r8, rsi; lpInBuffer
0x180088ec4  mov     [rsp+898h+nOutBufferSize], ebx; nOutBufferSize
0x180088ec8  mov     edx, r14d; dwIoControlCode
0x180088ecb  mov     [rsp+898h+lpOutBuffer], rsi; lpOutBuffer
0x180088ed0  call    cs:__imp_DeviceIoControl
0x180088ed7  nop     dword ptr [rax+rax+00h]
0x180088edc  mov     rcx, rbp; lpCriticalSection
0x180088edf  mov     ebx, eax
0x180088ee1  call    cs:__imp_EnterCriticalSection
0x180088ee8  nop     dword ptr [rax+rax+00h]
0x180088eed  add     [rdi+58h], r12d
0x180088ef1  mov     rcx, rbp; lpCriticalSection
0x180088ef4  jnz     short loc_180088F36
0x180088ef6  call    cs:__imp_LeaveCriticalSection
0x180088efd  nop     dword ptr [rax+rax+00h]
0x180088f02  mov     rcx, rbp; lpCriticalSection
0x180088f05  call    cs:__imp_DeleteCriticalSection
0x180088f0c  nop     dword ptr [rax+rax+00h]
0x180088f11  call    cs:__imp_GetProcessHeap
0x180088f18  nop     dword ptr [rax+rax+00h]
0x180088f1d  mov     r8, rdi; lpMem
0x180088f20  xor     edx, edx; dwFlags
0x180088f22  mov     rcx, rax; hHeap
0x180088f25  call    cs:__imp_HeapFree
0x180088f2c  nop     dword ptr [rax+rax+00h]
0x180088f31  mov     rdi, r15
0x180088f34  jmp     short loc_180088F42
0x180088f36  call    cs:__imp_LeaveCriticalSection
0x180088f3d  nop     dword ptr [rax+rax+00h]
0x180088f42  cmp     ebx, 1
0x180088f45  jz      loc_18008907D
0x180088f4b  call    cs:__imp_GetLastError
0x180088f52  nop     dword ptr [rax+rax+00h]
0x180088f57  mov     r9d, eax
0x180088f5a  cmp     eax, 3E5h
0x180088f5f  jz      loc_18008907D
0x180088f65  cmp     cs:gIsndpspEtwTracingAvailable, r15d
0x180088f6c  jz      short loc_180088FC0
0x180088f6e  cmp     qword ptr cs:xmmword_1800D0BE0, r15
0x180088f75  jz      short loc_180088FF0
0x180088f77  mov     ecx, [rsi+20h]
0x180088f7a  lea     rax, off_180096DC0; "Accept"
0x180088f81  sub     ecx, r13d
0x180088f84  mov     word ptr [rsp+898h+var_848], r15w
0x180088f8a  lea     rdx, aAsyncdriverreq_1; "AsyncDriverRequest: IoCtl (Oid %hs) fai"...
0x180088f91  mov     r8, [rax+rcx*8]
0x180088f95  lea     rcx, [rsp+898h+var_848]
0x180088f9a  call    FormatRRASErrorString
0x180088f9f  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x180088fa6  lea     r8, [rsp+898h+var_848]
0x180088fab  mov     rcx, cs:gNdpspEtwContext
0x180088fb2  mov     rax, cs:gNdpspTemplateFunc
0x180088fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088fbe  jmp     short loc_180088FF0
0x180088fc0  mov     ecx, cs:dwTraceId; dwTraceID
0x180088fc6  cmp     ecx, r12d
0x180088fc9  jz      short loc_180088FF0
0x180088fcb  mov     r8d, [rsi+20h]
0x180088fcf  lea     rax, off_180096DC0; "Accept"
0x180088fd6  sub     r8d, r13d
0x180088fd9  lea     rdx, aAsyncdriverreq_2; "AsyncDriverRequest: IoCtl (Oid %hs) fai"...
0x180088fe0  mov     r8, [rax+r8*8]
0x180088fe4  call    cs:__imp_TracePrintfA
0x180088feb  nop     dword ptr [rax+rax+00h]
0x180088ff0  mov     r9d, [rsi+30h]
0x180088ff4  xor     r8d, r8d
0x180088ff7  mov     eax, 80000048h
0x180088ffc  mov     qword ptr [rsp+898h+nOutBufferSize], r15
0x180089001  mov     [rsp+898h+lpOutBuffer], rax
0x180089006  xor     ecx, ecx
0x180089008  mov     rax, cs:g_pfnCallback
0x18008900f  lea     edx, [r8+0Ch]
0x180089013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089018  lea     rbx, [rdi+30h]
0x18008901c  mov     rcx, rbx; lpCriticalSection
0x18008901f  call    cs:__imp_EnterCriticalSection
0x180089026  nop     dword ptr [rax+rax+00h]
0x18008902b  add     [rdi+58h], r12d
0x18008902f  mov     rcx, rbx; lpCriticalSection
0x180089032  jnz     short loc_180089071
0x180089034  call    cs:__imp_LeaveCriticalSection
0x18008903b  nop     dword ptr [rax+rax+00h]
0x180089040  mov     rcx, rbx; lpCriticalSection
0x180089043  call    cs:__imp_DeleteCriticalSection
0x18008904a  nop     dword ptr [rax+rax+00h]
0x18008904f  call    cs:__imp_GetProcessHeap
0x180089056  nop     dword ptr [rax+rax+00h]
0x18008905b  mov     r8, rdi; lpMem
0x18008905e  xor     edx, edx; dwFlags
0x180089060  mov     rcx, rax; hHeap
0x180089063  call    cs:__imp_HeapFree
0x18008906a  nop     dword ptr [rax+rax+00h]
0x18008906f  jmp     short loc_18008907D
0x180089071  call    cs:__imp_LeaveCriticalSection
0x180089078  nop     dword ptr [rax+rax+00h]
0x18008907d  mov     rcx, [rsp+898h+var_48]
0x180089085  xor     rcx, rsp; StackCookie
0x180089088  call    __security_check_cookie
0x18008908d  mov     rbx, [rsp+898h+arg_10]
0x180089095  add     rsp, 860h
0x18008909c  pop     r15
0x18008909e  pop     r14
0x1800890a0  pop     r13
0x1800890a2  pop     r12
0x1800890a4  pop     rdi
0x1800890a5  pop     rsi
0x1800890a6  pop     rbp
0x1800890a7  retn
```
