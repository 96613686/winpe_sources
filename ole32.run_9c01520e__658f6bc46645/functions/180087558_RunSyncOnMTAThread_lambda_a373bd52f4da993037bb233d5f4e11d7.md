# RunSyncOnMTAThread__lambda_a373bd52f4da993037bb233d5f4e11d7_

- ea: `0x180087558`
- end: `0x1800875f6`
- name: `RunSyncOnMTAThread__lambda_a373bd52f4da993037bb233d5f4e11d7___`
- size: `158`
- prototype: `HRESULT __fastcall(RenderFormat::__l36::<lambda_a373bd52f4da993037bb233d5f4e11d7> operation)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003b5f8`

## callees

- `0x180087558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008759e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008759e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800875bf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800875bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008758a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18008758a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800875df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800875df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800875d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800875d0`

## pseudocode

```c
__int64 __fastcall RunSyncOnMTAThread__lambda_a373bd52f4da993037bb233d5f4e11d7_(
        RenderFormat::__l36::<lambda_a373bd52f4da993037bb233d5f4e11d7> operation)
{
  _TP_WORK *v1; // rax
  _TP_WORK *v2; // rbx
  signed int LastError; // eax
  RunSyncOnMTAThread::__l2::<lambda_1f33e66c4d719b5f6d4f05584bc2ec2e> hrHandlerOverOperation; // [rsp+20h] [rbp-18h] BYREF
  tagSTGMEDIUM *medium; // [rsp+40h] [rbp+8h] BYREF
  HRESULT hr; // [rsp+48h] [rbp+10h] BYREF

  medium = operation.medium;
  hr = 0;
  hrHandlerOverOperation.operation = (RenderFormat::__l36::<lambda_a373bd52f4da993037bb233d5f4e11d7> *)&medium;
  hrHandlerOverOperation.hr = &hr;
  v1 = CreateThreadpoolWork(MTAThreadPoolWorker__lambda_1f33e66c4d719b5f6d4f05584bc2ec2e_, &hrHandlerOverOperation, 0);
  v2 = v1;
  if ( v1 )
  {
    SubmitThreadpoolWork(v1);
    WaitForThreadpoolWorkCallbacks(v2, 0);
    CloseThreadpoolWork(v2);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x180087558  mov     r11, rsp
0x18008755b  mov     [r11+8], operation
0x18008755f  push    rbx
0x180087560  sub     rsp, 30h
0x180087564  lea     rax, [r11+8]
0x180087568  mov     [rsp+38h+hr], 0
0x180087570  mov     [r11-18h], rax
0x180087574  lea     rdx, [r11-18h]; pv
0x180087578  lea     rax, [r11+10h]
0x18008757c  xor     r8d, r8d; pcbe
0x18008757f  lea     operation, MTAThreadPoolWorker__lambda_1f33e66c4d719b5f6d4f05584bc2ec2e___; pfnwk
0x180087586  mov     [r11-10h], rax
0x18008758a  call    cs:__imp_CreateThreadpoolWork
0x180087591  nop     dword ptr [rax+rax+00h]
0x180087596  mov     rbx, rax
0x180087599  test    rax, rax
0x18008759c  jnz     short loc_1800875BC
0x18008759e  call    cs:__imp_GetLastError
0x1800875a5  nop     dword ptr [rax+rax+00h]
0x1800875aa  test    eax, eax
0x1800875ac  jle     short loc_1800875B6
0x1800875ae  movzx   eax, ax
0x1800875b1  or      eax, 80070000h
0x1800875b6  mov     [rsp+38h+hr], eax
0x1800875ba  jmp     short loc_1800875EB
0x1800875bc  mov     operation, rbx; pwk
0x1800875bf  call    cs:__imp_SubmitThreadpoolWork
0x1800875c6  nop     dword ptr [rax+rax+00h]
0x1800875cb  xor     edx, edx; fCancelPendingCallbacks
0x1800875cd  mov     operation, rbx; pwk
0x1800875d0  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800875d7  nop     dword ptr [rax+rax+00h]
0x1800875dc  mov     operation, rbx; pwk
0x1800875df  call    cs:__imp_CloseThreadpoolWork
0x1800875e6  nop     dword ptr [rax+rax+00h]
0x1800875eb  mov     eax, [rsp+38h+hr]
0x1800875ef  add     rsp, 30h
0x1800875f3  pop     rbx
0x1800875f4  retn
```
