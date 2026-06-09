# SetScheduledTaskState(ushort const *,ushort const *,int,int,int *)

- ea: `0x180098b54`
- end: `0x180098da5`
- name: `?SetScheduledTaskState@@YAJPEBG0HHPEAH@Z`
- size: `593`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, int, int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004eeb0`
- `0x180054738`
- `0x18009b4dc`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x180098664`
- `0x180098b54`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180098d73`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180098d73`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180098bf0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180098bf0`

## string_xrefs

- `0x180098c3b`: `GetScheduledTask`
- `0x180098bbd`: `taskName`
- `0x180098bd8`: `taskName`
- `0x180098b80`: `SetScheduledTaskState`
- `0x180098cba`: `%s: The task "%s\%s" is already in the specified state.`
- `0x180098c98`: `%s: IRegisteredTask::get_Enabled failed with error 0x%08x. Cannot check the state of task "%s\%s". Ignore this failure and continue to set the task state.`
- `0x180098d53`: `%s: IRegisteredTask::put_Enabled failed with error 0x%08x. Failed to %s task "%s\%s".`
- `0x180098d13`: `%s: Successfuly %s task "%s\%s".`

## pseudocode

```c
__int64 __fastcall SetScheduledTaskState(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        int *a5)
{
  int *v7; // r14
  unsigned int v8; // ebx
  HRESULT v9; // eax
  const unsigned __int16 *v10; // rcx
  int ScheduledTask; // eax
  struct IRegisteredTask *v12; // rdi
  unsigned __int16 v13; // r15
  int v14; // eax
  const wchar_t *v15; // r8
  const wchar_t *v16; // r9
  struct IRegisteredTask *v18; // [rsp+90h] [rbp+8h] BYREF
  int v19; // [rsp+A8h] [rbp+20h] BYREF

  v19 = a4;
  v18 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"SetScheduledTaskState");
  v7 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"SetScheduledTaskState", L"taskName");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"SetScheduledTaskState", L"taskName");
    goto LABEL_24;
  }
  v9 = CoInitializeEx(0, 0);
  v8 = v9;
  if ( v9 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"SetScheduledTaskState",
      L"CoInitializeEx",
      (unsigned int)v9);
    goto LABEL_24;
  }
  ScheduledTask = GetScheduledTask(v10, a2, &v18);
  v12 = v18;
  v8 = ScheduledTask;
  if ( ScheduledTask >= 0 )
  {
    LOWORD(v19) = 0;
    v13 = -(a3 != 0);
    v14 = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))v18->lpVtbl->get_Enabled)(v18, &v19);
    v8 = v14;
    if ( v14 >= 0 )
    {
      if ( (_WORD)v19 == v13 )
      {
        Logger::TraceVerbose(
          (wchar_t *)L"%s: The task \"%s\\%s\" is already in the specified state.",
          L"SetScheduledTaskState",
          L"\\Microsoft\\Windows\\Workplace Join",
          a2);
        if ( (_WORD)v19 == v13 )
          goto LABEL_21;
      }
    }
    else
    {
      Logger::TraceWarning(
        (wchar_t *)L"%s: IRegisteredTask::get_Enabled failed with error 0x%08x. Cannot check the state of task \"%s\\%s\"."
                    " Ignore this failure and continue to set the task state.",
        L"SetScheduledTaskState",
        (unsigned int)v14,
        L"\\Microsoft\\Windows\\Workplace Join",
        a2);
    }
    v8 = ((__int64 (__fastcall *)(struct IRegisteredTask *, _QWORD))v12->lpVtbl->put_Enabled)(v12, v13);
    if ( (v8 & 0x80000000) != 0 )
    {
      v16 = L"enable";
      if ( !a3 )
        v16 = L"disable";
      Logger::TraceError(
        L"%s: IRegisteredTask::put_Enabled failed with error 0x%08x. Failed to %s task \"%s\\%s\".",
        L"SetScheduledTaskState",
        v8,
        v16,
        L"\\Microsoft\\Windows\\Workplace Join",
        a2);
    }
    else
    {
      v15 = L"enabled";
      if ( !a3 )
        v15 = L"disabled";
      Logger::TraceInformation(
        L"%s: Successfuly %s task \"%s\\%s\".",
        L"SetScheduledTaskState",
        v15,
        L"\\Microsoft\\Windows\\Workplace Join",
        a2);
      if ( v7 )
        *v7 = 1;
    }
    goto LABEL_21;
  }
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"SetScheduledTaskState",
    L"GetScheduledTask",
    (unsigned int)ScheduledTask);
LABEL_21:
  if ( v12 )
    ((void (__fastcall *)(struct IRegisteredTask *))v12->lpVtbl->Release)(v12);
  CoUninitialize();
LABEL_24:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"SetScheduledTaskState", v8);
  return v8;
}

```

## disassembly

```asm
0x180098b54  mov     r11, rsp
0x180098b57  mov     [r11+10h], rbx
0x180098b5b  mov     [r11+20h], r9d
0x180098b5f  mov     [r11+8], rcx
0x180098b63  push    rbp
0x180098b64  push    rsi
0x180098b65  push    rdi
0x180098b66  push    r12
0x180098b68  push    r13
0x180098b6a  push    r14
0x180098b6c  push    r15
0x180098b6e  sub     rsp, 50h
0x180098b72  xorps   xmm0, xmm0
0x180098b75  mov     qword ptr [r11+8], 0
0x180098b7d  mov     rsi, rdx
0x180098b80  lea     r13, aSetscheduledta; "SetScheduledTaskState"
0x180098b87  xor     eax, eax
0x180098b89  lea     rcx, aSStarted; "%s started"
0x180098b90  movups  [rsp+88h+var_58], xmm0
0x180098b95  mov     rdx, r13
0x180098b98  mov     [r11-48h], rax
0x180098b9c  mov     r12d, r8d
0x180098b9f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098ba4  mov     r14, [rsp+88h+arg_20]
0x180098bac  test    r14, r14
0x180098baf  jz      short loc_180098BB8
0x180098bb1  mov     dword ptr [r14], 0
0x180098bb8  test    rsi, rsi
0x180098bbb  jnz     short loc_180098BEC
0x180098bbd  lea     r8, aTaskname; "taskName"
0x180098bc4  mov     rdx, r13
0x180098bc7  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180098bce  mov     ebx, 80070057h
0x180098bd3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098bd8  lea     rdx, aTaskname; "taskName"
0x180098bdf  mov     rcx, r13; unsigned __int16 *
0x180098be2  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180098be7  jmp     loc_180098D79
0x180098bec  xor     edx, edx; dwCoInit
0x180098bee  xor     ecx, ecx; pvReserved
0x180098bf0  call    cs:__imp_CoInitializeEx
0x180098bf6  mov     ebx, eax
0x180098bf8  test    eax, eax
0x180098bfa  jns     short loc_180098C1A
0x180098bfc  mov     r9d, eax
0x180098bff  lea     r8, aCoinitializeex_0; "CoInitializeEx"
0x180098c06  mov     rdx, r13
0x180098c09  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180098c10  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098c15  jmp     loc_180098D79
0x180098c1a  lea     r8, [rsp+88h+arg_0]; struct IRegisteredTask **
0x180098c22  mov     rdx, rsi; unsigned __int16 *
0x180098c25  call    ?GetScheduledTask@@YAJPEBG0PEAPEAUIRegisteredTask@@@Z; GetScheduledTask(ushort const *,ushort const *,IRegisteredTask * *)
0x180098c2a  mov     rdi, [rsp+88h+arg_0]
0x180098c32  mov     ebx, eax
0x180098c34  test    eax, eax
0x180098c36  jns     short loc_180098C56
0x180098c38  mov     r9d, eax
0x180098c3b  lea     r8, aGetscheduledta; "GetScheduledTask"
0x180098c42  mov     rdx, r13
0x180098c45  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180098c4c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098c51  jmp     loc_180098D5F
0x180098c56  xor     eax, eax
0x180098c58  lea     rdx, [rsp+88h+arg_18]
0x180098c60  mov     word ptr [rsp+88h+arg_18], ax
0x180098c68  mov     rcx, rdi
0x180098c6b  mov     eax, r12d
0x180098c6e  neg     eax
0x180098c70  mov     rax, [rdi]
0x180098c73  sbb     r15w, r15w
0x180098c77  mov     rax, [rax+50h]
0x180098c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c80  lea     rbp, psz; "\\Microsoft\\Windows\\Workplace Join"
0x180098c87  mov     ebx, eax
0x180098c89  test    eax, eax
0x180098c8b  jns     short loc_180098CA9
0x180098c8d  mov     r9, rbp
0x180098c90  mov     [rsp+88h+var_68], rsi
0x180098c95  mov     r8d, eax
0x180098c98  lea     rcx, aSIregisteredta; "%s: IRegisteredTask::get_Enabled failed"...
0x180098c9f  mov     rdx, r13
0x180098ca2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180098ca7  jmp     short loc_180098CDE
0x180098ca9  movzx   eax, word ptr [rsp+88h+arg_18]
0x180098cb1  cmp     ax, r15w
0x180098cb5  jnz     short loc_180098CDE
0x180098cb7  mov     r9, rsi
0x180098cba  lea     rcx, aSTheTaskSSIsAl; "%s: The task \"%s\\%s\" is already in t"...
0x180098cc1  mov     r8, rbp
0x180098cc4  mov     rdx, r13
0x180098cc7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098ccc  movzx   eax, word ptr [rsp+88h+arg_18]
0x180098cd4  cmp     ax, r15w
0x180098cd8  jz      loc_180098D5F
0x180098cde  mov     rax, [rdi]
0x180098ce1  movzx   edx, r15w
0x180098ce5  mov     rcx, rdi
0x180098ce8  mov     rax, [rax+58h]
0x180098cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cf1  mov     ebx, eax
0x180098cf3  mov     rdx, r13
0x180098cf6  test    eax, eax
0x180098cf8  js      short loc_180098D31
0x180098cfa  lea     rax, aDisabled_0; "disabled"
0x180098d01  mov     [rsp+88h+var_68], rsi
0x180098d06  test    r12d, r12d
0x180098d09  lea     r8, aEnabled_1; "enabled"
0x180098d10  mov     r9, rbp
0x180098d13  lea     rcx, aSSuccessfulyST; "%s: Successfuly %s task \"%s\\%s\"."
0x180098d1a  cmovz   r8, rax
0x180098d1e  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180098d23  test    r14, r14
0x180098d26  jz      short loc_180098D5F
0x180098d28  mov     dword ptr [r14], 1
0x180098d2f  jmp     short loc_180098D5F
0x180098d31  test    r12d, r12d
0x180098d34  mov     [rsp+88h+var_60], rsi
0x180098d39  lea     rax, aDisable; "disable"
0x180098d40  mov     [rsp+88h+var_68], rbp
0x180098d45  lea     r9, aEnable; "enable"
0x180098d4c  mov     r8d, ebx
0x180098d4f  cmovz   r9, rax
0x180098d53  lea     rcx, aSIregisteredta_0; "%s: IRegisteredTask::put_Enabled failed"...
0x180098d5a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098d5f  test    rdi, rdi
0x180098d62  jz      short loc_180098D73
0x180098d64  mov     rax, [rdi]
0x180098d67  mov     rcx, rdi
0x180098d6a  mov     rax, [rax+10h]
0x180098d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d73  call    cs:__imp_CoUninitialize
0x180098d79  mov     r8d, ebx
0x180098d7c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180098d83  mov     rdx, r13
0x180098d86  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180098d8b  mov     eax, ebx
0x180098d8d  mov     rbx, [rsp+88h+arg_8]
0x180098d95  add     rsp, 50h
0x180098d99  pop     r15
0x180098d9b  pop     r14
0x180098d9d  pop     r13
0x180098d9f  pop     r12
0x180098da1  pop     rdi
0x180098da2  pop     rsi
0x180098da3  pop     rbp
0x180098da4  retn
```
