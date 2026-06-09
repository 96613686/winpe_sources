# Memory::RecyclerParallelThread::StaticThreadProc(void *)

- ea: `0x180369ee0`
- end: `0x180369ff0`
- name: `?StaticThreadProc@RecyclerParallelThread@Memory@@CAIPEAX@Z`
- size: `272`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180369ee0`
- `0x180395ca0`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180369f58`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180369f58`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180369f6f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180369fa8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180369f6f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180369fa8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180369f82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180369f82`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180369f2d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180369f2d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibraryAndExitThread` at `0x180369fc0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibraryAndExitThread` at `0x180369fc0`

## pseudocode

```c
__int64 __fastcall Memory::RecyclerParallelThread::StaticThreadProc(int *a1)
{
  __int64 v2; // rdi
  void (__fastcall *v3)(__int64); // rsi
  __int64 v4; // r14
  char i; // al
  HMODULE hLibModule; // [rsp+28h] [rbp-50h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-40h] BYREF

  v2 = *((_QWORD *)a1 + 3);
  v3 = *(void (__fastcall **)(__int64))a1;
  v4 = a1[2];
  hLibModule = 0;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)Memory::RecyclerParallelThread::StaticThreadProc, &hLibModule) )
    hLibModule = 0;
  ActivityId = 0;
  EventActivityIdControl(5u, &ActivityId);
  for ( i = *((_BYTE *)a1 + 56); ; i = 1 )
  {
    if ( i )
    {
      SetEvent(*((HANDLE *)a1 + 5));
      WaitForSingleObject(*((HANDLE *)a1 + 4), 0xFFFFFFFF);
    }
    if ( *(_DWORD *)(v2 + 32) == 4 )
      break;
    v3(v2 + v4);
  }
  SetEvent(*((HANDLE *)a1 + 5));
  if ( hLibModule )
    FreeLibraryAndExitThread(hLibModule, 0);
  return 0;
}

```

## disassembly

```asm
0x180369ee0  mov     r11, rsp
0x180369ee3  mov     [r11+8], rcx
0x180369ee7  push    rbx
0x180369ee8  push    rsi
0x180369ee9  push    rdi
0x180369eea  push    r14
0x180369eec  sub     rsp, 58h
0x180369ef0  mov     rax, cs:__security_cookie
0x180369ef7  xor     rax, rsp
0x180369efa  mov     [rsp+78h+var_30], rax
0x180369eff  mov     rbx, rcx
0x180369f02  mov     [rsp+78h+var_58], 0FFFFFFFFh
0x180369f0a  mov     rdi, [rcx+18h]
0x180369f0e  mov     rsi, [rcx]
0x180369f11  movsxd  r14, dword ptr [rcx+8]
0x180369f15  mov     qword ptr [r11-50h], 0
0x180369f1d  lea     r8, [r11-50h]; phModule
0x180369f21  lea     rdx, ?StaticThreadProc@RecyclerParallelThread@Memory@@CAIPEAX@Z; lpModuleName
0x180369f28  mov     ecx, 4; dwFlags
0x180369f2d  call    cs:__imp_GetModuleHandleExW
0x180369f34  nop     dword ptr [rax+rax+00h]
0x180369f39  test    eax, eax
0x180369f3b  jnz     short loc_180369F46
0x180369f3d  mov     [rsp+78h+hLibModule], 0
0x180369f46  xorps   xmm0, xmm0
0x180369f49  movups  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x180369f4e  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x180369f53  mov     ecx, 5; ControlCode
0x180369f58  call    cs:__imp_EventActivityIdControl
0x180369f5f  nop     dword ptr [rax+rax+00h]
0x180369f64  mov     al, [rbx+38h]
0x180369f67  test    al, al
0x180369f69  jz      short loc_180369F8E
0x180369f6b  mov     rcx, [rbx+28h]; hEvent
0x180369f6f  call    cs:__imp_SetEvent
0x180369f76  nop     dword ptr [rax+rax+00h]
0x180369f7b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180369f7e  mov     rcx, [rbx+20h]; hHandle
0x180369f82  call    cs:__imp_WaitForSingleObject
0x180369f89  nop     dword ptr [rax+rax+00h]
0x180369f8e  cmp     dword ptr [rdi+20h], 4
0x180369f92  jz      short loc_180369FA4
0x180369f94  lea     rcx, [rdi+r14]
0x180369f98  mov     rax, rsi
0x180369f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180369fa0  mov     al, 1
0x180369fa2  jmp     short loc_180369F67
0x180369fa4  mov     rcx, [rbx+28h]; hEvent
0x180369fa8  call    cs:__imp_SetEvent
0x180369faf  nop     dword ptr [rax+rax+00h]
0x180369fb4  mov     rcx, [rsp+78h+hLibModule]; hLibModule
0x180369fb9  test    rcx, rcx
0x180369fbc  jz      short loc_180369FCC
0x180369fbe  xor     edx, edx; dwExitCode
0x180369fc0  call    cs:__imp_FreeLibraryAndExitThread
0x180369fc7  nop     dword ptr [rax+rax+00h]
0x180369fcc  xor     eax, eax
0x180369fce  mov     [rsp+78h+var_58], eax
0x180369fd2  jmp     short loc_180369FD8
0x180369fd4  mov     eax, [rsp+78h+var_58]
0x180369fd8  mov     rcx, [rsp+78h+var_30]
0x180369fdd  xor     rcx, rsp; StackCookie
0x180369fe0  call    __security_check_cookie
0x180369fe5  add     rsp, 58h
0x180369fe9  pop     r14
0x180369feb  pop     rdi
0x180369fec  pop     rsi
0x180369fed  pop     rbx
0x180369fee  retn
0x1805b5d10  mov     [rsp+arg_0], rcx
0x1805b5d15  mov     [rsp+arg_8], rdx
0x1805b5d1a  push    rbp
0x1805b5d1b  sub     rsp, 20h
0x1805b5d1f  mov     rbp, rdx
0x1805b5d22  mov     [rbp+30h], rcx
0x1805b5d26  call    ?Flush@Output@@SAXXZ; Output::Flush(void)
0x1805b5d2b  mov     dword ptr [rbp+24h], 0
0x1805b5d32  mov     eax, [rbp+24h]
0x1805b5d35  add     rsp, 20h
0x1805b5d39  pop     rbp
0x1805b5d3a  retn
```
