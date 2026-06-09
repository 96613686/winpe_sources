# CDefragEngine::_StartNotificationThread(void)

- ea: `0x18004631c`
- end: `0x18004648e`
- name: `?_StartNotificationThread@CDefragEngine@@AEAAJXZ`
- size: `370`
- prototype: `__int64 __fastcall(CDefragEngine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d560`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18004631c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800463bb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800463bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046409`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180046409`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046423`

## string_xrefs

- `0x18004633d`: `CDefragEngine::_StartNotificationThread`

## pseudocode

```c
__int64 __fastcall CDefragEngine::_StartNotificationThread(CDefragEngine *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, LPVOID *); // rax
  int LastFailureAsHRESULT; // ebx
  __int16 v4; // ax
  LPVOID v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  HANDLE v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  char *v13; // rcx
  char *v14; // rdx
  int v16; // [rsp+30h] [rbp-40h] BYREF
  __int16 v17; // [rsp+34h] [rbp-3Ch]
  __int16 v18; // [rsp+36h] [rbp-3Ah]
  DWORD ThreadId; // [rsp+80h] [rbp+10h] BYREF
  LPVOID lpParameter; // [rsp+88h] [rbp+18h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CDefragEngine::_StartNotificationThread", 4240, 1);
  lpParameter = 0;
  ThreadId = 0;
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))(*(__int64 (__fastcall **)(CDefragEngine *))(*(_QWORD *)this + 216LL))(this);
  LastFailureAsHRESULT = (**v2)(v2, &IID_IDefragEnginePriv, &lpParameter);
  v16 = LastFailureAsHRESULT;
  v4 = 4248;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_2;
  v17 = 4248;
  *((_DWORD *)this + 60) = 0;
  if ( !ResetEvent(*((HANDLE *)this + 17)) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7, v6, v8, v9);
    v16 = LastFailureAsHRESULT;
    v4 = 4252;
LABEL_2:
    v18 = v4;
    v5 = lpParameter;
    goto LABEL_10;
  }
  v16 = 0;
  v17 = 4252;
  v10 = CreateThread(0, 0x8000u, (LPTHREAD_START_ROUTINE)CDefragEngine::_NotificationThread, lpParameter, 0, &ThreadId);
  v13 = (char *)*((_QWORD *)this + 18);
  v14 = v13 - 1;
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v13);
  *((_QWORD *)this + 18) = v10;
  if ( !v10 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13, v14, v11, v12);
    v16 = LastFailureAsHRESULT;
    v4 = 4258;
    goto LABEL_2;
  }
  LastFailureAsHRESULT = 0;
  v16 = 0;
  v17 = 4258;
  v5 = 0;
  lpParameter = 0;
LABEL_10:
  if ( v5 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    LastFailureAsHRESULT = v16;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18004631c  mov     [rsp-8+arg_10], rbx
0x180046321  mov     [rsp-8+arg_18], rdi
0x180046326  push    rbp
0x180046327  mov     rbp, rsp
0x18004632a  sub     rsp, 70h
0x18004632e  mov     rdi, rcx
0x180046331  mov     r9d, 1; unsigned __int16
0x180046337  mov     r8d, 1090h; unsigned __int16
0x18004633d  lea     rdx, aCdefragengineS_4; "CDefragEngine::_StartNotificationThread"
0x180046344  lea     rcx, [rbp+var_40]; this
0x180046348  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004634d  nop
0x18004634e  mov     [rbp+lpParameter], 0
0x180046356  mov     [rbp+ThreadId], 0
0x18004635d  mov     rax, [rdi]
0x180046360  mov     rcx, rdi
0x180046363  mov     rax, [rax+0D8h]
0x18004636a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004636f  mov     r9, rax
0x180046372  mov     rcx, [rax]
0x180046375  mov     rax, [rcx]
0x180046378  lea     r8, [rbp+lpParameter]
0x18004637c  lea     rdx, IID_IDefragEnginePriv
0x180046383  mov     rcx, r9
0x180046386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004638b  mov     ebx, eax
0x18004638d  mov     [rbp+var_40], eax
0x180046390  test    eax, eax
0x180046392  mov     eax, 1098h
0x180046397  jns     short loc_1800463A6
0x180046399  mov     [rbp+var_3A], ax
0x18004639d  mov     rcx, [rbp+lpParameter]
0x1800463a1  jmp     loc_18004645D
0x1800463a6  mov     [rbp+var_3C], ax
0x1800463aa  mov     dword ptr [rdi+0F0h], 0
0x1800463b4  mov     rcx, [rdi+88h]; hEvent
0x1800463bb  call    cs:__imp_ResetEvent
0x1800463c1  test    eax, eax
0x1800463c3  jnz     short loc_1800463D6
0x1800463c5  call    GetLastFailureAsHRESULT
0x1800463ca  mov     ebx, eax
0x1800463cc  mov     [rbp+var_40], eax
0x1800463cf  mov     eax, 109Ch
0x1800463d4  jmp     short loc_180046399
0x1800463d6  mov     [rbp+var_40], 0
0x1800463dd  mov     eax, 109Ch
0x1800463e2  mov     [rbp+var_3C], ax
0x1800463e6  lea     rax, [rbp+ThreadId]
0x1800463ea  mov     [rsp+70h+lpThreadId], rax; lpThreadId
0x1800463ef  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x1800463f7  mov     r9, [rbp+lpParameter]; lpParameter
0x1800463fb  lea     r8, ?_NotificationThread@CDefragEngine@@CAKPEAX@Z; lpStartAddress
0x180046402  mov     edx, 8000h; dwStackSize
0x180046407  xor     ecx, ecx; lpThreadAttributes
0x180046409  call    cs:__imp_CreateThread
0x18004640f  mov     rbx, rax
0x180046412  mov     rcx, [rdi+90h]; hObject
0x180046419  lea     rdx, [rcx-1]
0x18004641d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180046421  ja      short loc_180046429
0x180046423  call    cs:__imp_CloseHandle
0x180046429  mov     [rdi+90h], rbx
0x180046430  test    rbx, rbx
0x180046433  jnz     short loc_180046449
0x180046435  call    GetLastFailureAsHRESULT
0x18004643a  mov     ebx, eax
0x18004643c  mov     [rbp+var_40], eax
0x18004643f  mov     eax, 10A2h
0x180046444  jmp     loc_180046399
0x180046449  xor     ebx, ebx
0x18004644b  mov     [rbp+var_40], ebx
0x18004644e  mov     eax, 10A2h
0x180046453  mov     [rbp+var_3C], ax
0x180046457  xor     ecx, ecx
0x180046459  mov     [rbp+lpParameter], rcx
0x18004645d  test    rcx, rcx
0x180046460  jz      short loc_180046471
0x180046462  mov     rax, [rcx]
0x180046465  mov     rax, [rax+10h]
0x180046469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004646e  mov     ebx, [rbp+var_40]
0x180046471  lea     rcx, [rbp+var_40]; this
0x180046475  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004647a  mov     eax, ebx
0x18004647c  lea     r11, [rsp+70h+var_s0]
0x180046481  mov     rbx, [r11+20h]
0x180046485  mov     rdi, [r11+28h]
0x180046489  mov     rsp, r11
0x18004648c  pop     rbp
0x18004648d  retn
```
