# LsapRmInitializeServer

- ea: `0x140004324`
- end: `0x140004585`
- name: `LsapRmInitializeServer`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400031bc`

## callees

- `0x1400020c0`
- `0x140002a02`
- `0x140004324`

## import_xrefs

- `ntdll!NtAlpcConnectPort` at `0x140004464`
- `ntdll!NtAlpcConnectPort` at `0x140004464`
- `ntdll!NtAlpcAcceptConnectPort` at `0x14000452e`
- `ntdll!NtAlpcAcceptConnectPort` at `0x14000452e`
- `ntdll!RtlInitUnicodeString` at `0x1400043a0`
- `ntdll!RtlInitUnicodeString` at `0x140004426`
- `ntdll!RtlInitUnicodeString` at `0x1400043a0`
- `ntdll!RtlInitUnicodeString` at `0x140004426`
- `ntdll!NtAlpcCancelMessage` at `0x1400044ef`
- `ntdll!NtAlpcCancelMessage` at `0x1400044ef`
- `ntdll!NtAlpcCreatePort` at `0x1400043e7`
- `ntdll!NtAlpcCreatePort` at `0x1400043e7`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1400044bf`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1400044bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004562`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004554`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004554`

## string_xrefs

- `0x140004380`: `\SeLsaCommandPort`
- `0x140004403`: `\SeRmCommandPort`

## pseudocode

```c
__int64 LsapRmInitializeServer()
{
  __int64 result; // rax
  HANDLE Thread; // rax
  __int64 v2; // [rsp+40h] [rbp-C0h]
  __int64 v3; // [rsp+48h] [rbp-B8h]
  __int64 v4; // [rsp+50h] [rbp-B0h]
  __int64 v5; // [rsp+58h] [rbp-A8h]
  __int64 ThreadId; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v7; // [rsp+68h] [rbp-98h] BYREF
  __int64 v8; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v9[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v10; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+88h] [rbp-78h]
  int v12; // [rsp+90h] [rbp-70h]
  int v13; // [rsp+94h] [rbp-6Ch]
  __int128 v14; // [rsp+98h] [rbp-68h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v16; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v17[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v18; // [rsp+E8h] [rbp-18h]
  _BYTE v19[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v20; // [rsp+F4h] [rbp-Ch]
  int v21; // [rsp+F8h] [rbp-8h]
  __int16 v22; // [rsp+FCh] [rbp-4h]
  __int64 v23; // [rsp+100h] [rbp+0h]
  _BYTE v24[512]; // [rsp+140h] [rbp+40h] BYREF

  memset_0(v24, 0, sizeof(v24));
  v16 = 0;
  DestinationString = 0;
  memset_0(v19, 0, 0x48u);
  LODWORD(ThreadId) = 0;
  v13 = 0;
  v9[1] = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SeLsaCommandPort");
  v9[0] = 48;
  p_DestinationString = &DestinationString;
  v10 = 0;
  v12 = 0;
  v14 = 0;
  memset_0(v19, 0, 0x48u);
  v23 = 512;
  result = NtAlpcCreatePort(&gLsapCommandPortHandle, v9, v19);
  if ( (int)result >= 0 )
  {
    memset_0(v19, 0, 0x48u);
    v23 = 512;
    v20 = 12;
    v21 = 2;
    v22 = 257;
    RtlInitUnicodeString(&v16, L"\\SeRmCommandPort");
    v4 = 0;
    v3 = 0;
    v2 = 0;
    result = NtAlpcConnectPort(&gLsapRmCommandPortHandle, &v16, 0, v19, 0x20000, 0, 0, 0);
    if ( (int)result >= 0 )
    {
      while ( 1 )
      {
        v18 = 0;
        v7 = 512;
        memset(v17, 0, sizeof(v17));
        LODWORD(v17[0]) = 0x20000000;
        result = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _BYTE *, __int64 *, _OWORD *, _QWORD, __int64, __int64, __int64, __int64, __int64))NtAlpcSendWaitReceivePort)(
                   gLsapCommandPortHandle,
                   0,
                   0,
                   0,
                   v24,
                   &v7,
                   v17,
                   0,
                   v2,
                   v3,
                   v4,
                   v5,
                   ThreadId);
        if ( (_DWORD)result != -1073741789 )
        {
          if ( (int)result < 0 )
            return result;
          if ( v24[4] == 10 )
            break;
        }
        NtAlpcCancelMessage(gLsapCommandPortHandle, 0, (char *)v17 + 8);
      }
      LOBYTE(v2) = 1;
      v8 = 0;
      result = NtAlpcAcceptConnectPort(&v8, gLsapCommandPortHandle, 0, 0, 0, 0, v24, 0, v2);
      if ( (int)result >= 0 )
      {
        Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)LsapRmServerThread, 0, 0, (LPDWORD)&ThreadId);
        if ( Thread )
          CloseHandle(Thread);
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004324  push    rbp
0x140004326  push    rbx
0x140004327  push    rsi
0x140004328  push    rdi
0x140004329  lea     rbp, [rsp-258h]
0x140004331  sub     rsp, 358h
0x140004338  mov     rax, cs:__security_cookie
0x14000433f  xor     rax, rsp
0x140004342  mov     [rbp+270h+var_30], rax
0x140004349  mov     edi, 200h
0x14000434e  lea     rcx, [rbp+270h+var_230]; void *
0x140004352  mov     r8d, edi; Size
0x140004355  xor     edx, edx; Val
0x140004357  call    memset_0
0x14000435c  xorps   xmm0, xmm0
0x14000435f  lea     rcx, [rbp+270h+var_280]; void *
0x140004363  xorps   xmm1, xmm1
0x140004366  mov     esi, 48h ; 'H'
0x14000436b  mov     r8d, esi; Size
0x14000436e  xor     edx, edx; Val
0x140004370  movups  xmmword ptr [rbp+270h+var_2B8.Length], xmm0
0x140004374  movups  xmmword ptr [rbp+270h+DestinationString.Length], xmm1
0x140004378  call    memset_0
0x14000437d  xorps   xmm0, xmm0
0x140004380  lea     rdx, aSelsacommandpo; "\\SeLsaCommandPort"
0x140004387  movups  [rbp+270h+var_2E8], xmm0
0x14000438b  xor     ebx, ebx
0x14000438d  lea     rcx, [rbp+270h+DestinationString]; DestinationString
0x140004391  xor     eax, eax
0x140004393  mov     dword ptr [rsp+370h+ThreadId], ebx
0x140004397  movups  [rbp+270h+var_2E8+0Ch], xmm0
0x14000439b  movups  [rsp+370h+var_2F8], xmm0
0x1400043a0  call    cs:__imp_RtlInitUnicodeString
0x1400043a6  lea     rax, [rbp+270h+DestinationString]
0x1400043aa  mov     dword ptr [rsp+370h+var_2F8], 30h ; '0'
0x1400043b2  xorps   xmm0, xmm0
0x1400043b5  mov     qword ptr [rbp+270h+var_2E8], rax
0x1400043b9  mov     r8d, esi; Size
0x1400043bc  mov     qword ptr [rbp+270h+var_2F8+8], rbx
0x1400043c0  xor     edx, edx; Val
0x1400043c2  mov     dword ptr [rbp+270h+var_2E8+8], ebx
0x1400043c5  lea     rcx, [rbp+270h+var_280]; void *
0x1400043c9  movdqu  [rbp+270h+var_2D8], xmm0
0x1400043ce  call    memset_0
0x1400043d3  lea     r8, [rbp+270h+var_280]
0x1400043d7  mov     [rbp+270h+var_270], rdi
0x1400043db  lea     rdx, [rsp+370h+var_2F8]
0x1400043e0  lea     rcx, gLsapCommandPortHandle
0x1400043e7  call    cs:__imp_NtAlpcCreatePort
0x1400043ed  test    eax, eax
0x1400043ef  js      loc_14000456A
0x1400043f5  mov     r8d, esi; Size
0x1400043f8  lea     rcx, [rbp+270h+var_280]; void *
0x1400043fc  xor     edx, edx; Val
0x1400043fe  call    memset_0
0x140004403  lea     rdx, aSermcommandpor; "\\SeRmCommandPort"
0x14000440a  mov     [rbp+270h+var_270], rdi
0x14000440e  lea     rcx, [rbp+270h+var_2B8]; DestinationString
0x140004412  mov     [rbp+270h+var_27C], 0Ch
0x140004419  mov     [rbp+270h+var_278], 2
0x140004420  mov     [rbp+270h+var_274], 101h
0x140004426  call    cs:__imp_RtlInitUnicodeString
0x14000442c  mov     [rsp+370h+var_320], rbx
0x140004431  lea     r9, [rbp+270h+var_280]
0x140004435  mov     [rsp+370h+var_328], rbx
0x14000443a  lea     rdx, [rbp+270h+var_2B8]
0x14000443e  mov     [rsp+370h+var_330], rbx
0x140004443  lea     rcx, gLsapRmCommandPortHandle
0x14000444a  mov     [rsp+370h+var_338], rbx
0x14000444f  xor     r8d, r8d
0x140004452  mov     [rsp+370h+var_340], rbx
0x140004457  mov     [rsp+370h+lpThreadId], rbx
0x14000445c  mov     [rsp+370h+dwCreationFlags], 20000h
0x140004464  call    cs:__imp_NtAlpcConnectPort
0x14000446a  test    eax, eax
0x14000446c  js      loc_14000456A
0x140004472  mov     rcx, cs:gLsapCommandPortHandle
0x140004479  xor     eax, eax
0x14000447b  mov     [rbp+270h+var_288], rax
0x14000447f  xorps   xmm0, xmm0
0x140004482  mov     [rsp+370h+var_338], rbx
0x140004487  lea     rax, [rbp+270h+var_2A8]
0x14000448b  mov     [rsp+370h+var_340], rax
0x140004490  xor     r9d, r9d
0x140004493  lea     rax, [rsp+370h+var_308]
0x140004498  mov     [rsp+370h+var_308], rdi
0x14000449d  mov     [rsp+370h+lpThreadId], rax
0x1400044a2  xor     r8d, r8d
0x1400044a5  lea     rax, [rbp+270h+var_230]
0x1400044a9  xor     edx, edx
0x1400044ab  movups  [rbp+270h+var_2A8], xmm0
0x1400044af  mov     qword ptr [rsp+370h+dwCreationFlags], rax
0x1400044b4  movups  [rbp+270h+var_298], xmm0
0x1400044b8  mov     dword ptr [rbp+270h+var_2A8], 20000000h
0x1400044bf  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1400044c5  cmp     eax, 0C0000023h
0x1400044ca  jz      short loc_1400044E2
0x1400044cc  test    eax, eax
0x1400044ce  js      loc_14000456A
0x1400044d4  movzx   eax, [rbp+270h+var_22C]
0x1400044d8  and     eax, 0FFFF00FFh
0x1400044dd  cmp     eax, 0Ah
0x1400044e0  jz      short loc_1400044FA
0x1400044e2  mov     rcx, cs:gLsapCommandPortHandle
0x1400044e9  lea     r8, [rbp+270h+var_2A8+8]
0x1400044ed  xor     edx, edx
0x1400044ef  call    cs:__imp_NtAlpcCancelMessage
0x1400044f5  jmp     loc_140004472
0x1400044fa  mov     rdx, cs:gLsapCommandPortHandle
0x140004501  lea     rax, [rbp+270h+var_230]
0x140004505  mov     byte ptr [rsp+370h+var_330], 1
0x14000450a  lea     rcx, [rsp+370h+var_300]
0x14000450f  mov     [rsp+370h+var_338], rbx
0x140004514  xor     r9d, r9d
0x140004517  mov     [rsp+370h+var_340], rax
0x14000451c  xor     r8d, r8d
0x14000451f  mov     [rsp+370h+lpThreadId], rbx
0x140004524  mov     qword ptr [rsp+370h+dwCreationFlags], rbx
0x140004529  mov     [rsp+370h+var_300], rbx
0x14000452e  call    cs:__imp_NtAlpcAcceptConnectPort
0x140004534  test    eax, eax
0x140004536  js      short loc_14000456A
0x140004538  lea     rax, [rsp+370h+ThreadId]
0x14000453d  xor     r9d, r9d; lpParameter
0x140004540  mov     [rsp+370h+lpThreadId], rax; lpThreadId
0x140004545  lea     r8, LsapRmServerThread; lpStartAddress
0x14000454c  xor     edx, edx; dwStackSize
0x14000454e  mov     [rsp+370h+dwCreationFlags], ebx; dwCreationFlags
0x140004552  xor     ecx, ecx; lpThreadAttributes
0x140004554  call    cs:__imp_CreateThread
0x14000455a  test    rax, rax
0x14000455d  jz      short loc_140004568
0x14000455f  mov     rcx, rax; hObject
0x140004562  call    cs:__imp_CloseHandle
0x140004568  mov     eax, ebx
0x14000456a  mov     rcx, [rbp+270h+var_30]
0x140004571  xor     rcx, rsp; StackCookie
0x140004574  call    __security_check_cookie
0x140004579  add     rsp, 358h
0x140004580  pop     rdi
0x140004581  pop     rsi
0x140004582  pop     rbx
0x140004583  pop     rbp
0x140004584  retn
```
