# SourceSelector_Log_OnCompleted

- ea: `0x180021780`
- end: `0x18002197d`
- name: `SourceSelector_Log_OnCompleted`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e64`
- `0x1800077a0`
- `0x180007800`
- `0x180007c80`
- `0x180021780`
- `0x180021990`
- `0x180022204`
- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x18004370c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800217d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800218b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800217d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800218b2`

## string_xrefs

- `0x1800217c1`: `mpunits.dll`
- `0x1800218a1`: `mpunits.dll`

## pseudocode

```c
char __fastcall SourceSelector_Log_OnCompleted(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rdi
  HMODULE ModuleHandleA; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  unsigned int ArbiterForJob; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdi
  HMODULE v13; // rax
  unsigned int v14; // eax
  __int64 *v16; // [rsp+70h] [rbp+28h] BYREF

  v1 = a1 + 152;
  if ( *(_BYTE *)(a1 + 305) && !*(_BYTE *)(a1 + 304) )
  {
    v16 = 0;
    v3 = EnableErrorDetails();
    v4 = *(_QWORD *)(v1 + 64);
    v5 = v3;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2139, v4);
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    CatchErrorDetails(v5, &v16);
    v7 = 4;
LABEL_4:
    LOBYTE(v8) = SourceSelector_Log_OnError(a1, v7, v16);
    if ( v16 )
    {
      v8 = *v16;
      if ( *v16 )
        LOBYTE(v8) = (*(__int64 (**)(void))(v8 + 16))();
    }
    return v8;
  }
  ArbiterForJob = SourceSelector_QueryArbiterForJob(a1 + 152);
  if ( ArbiterForJob )
  {
    LOBYTE(v8) = SourceSelector_Log_OnError(a1, ArbiterForJob, 0);
    return v8;
  }
  if ( !*(_BYTE *)(v1 + 80) )
  {
    v16 = 0;
    v10 = EnableErrorDetails();
    v11 = *(_QWORD *)(v1 + 64);
    v12 = v10;
    v13 = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(v13, 2140, v11);
    MI_ReportErrorDetails_ForCustomError(1, (int)L"MI", 0, 0);
    CatchErrorDetails(v12, &v16);
    v7 = 1;
    goto LABEL_4;
  }
  if ( !(unsigned int)TryAcquireWrite(v1 + 8) )
    QueueAcquireWrite(v1 + 8);
  if ( *(_QWORD *)v1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 24LL))(**(_QWORD **)v1);
  v14 = *(_DWORD *)(v1 + 48) & 0xFFFFFFF9;
  *(_QWORD *)v1 = 0;
  *(_DWORD *)(v1 + 48) = v14 | 1;
  ReadWriteLock_ReleaseWrite(v1 + 8);
  LOBYTE(v8) = *(_DWORD *)(v1 + 48) & 7;
  if ( (_BYTE)v8 == 1 )
    LOBYTE(v8) = CondLock_Broadcast(v1 + 48);
  return v8;
}

```

## disassembly

```asm
0x180021780  push    rbp
0x180021782  push    rbx
0x180021783  push    rsi
0x180021784  push    rdi
0x180021785  mov     rbp, rsp
0x180021788  sub     rsp, 48h
0x18002178c  lea     rbx, [rcx+98h]
0x180021793  mov     rsi, rcx
0x180021796  cmp     byte ptr [rbx+99h], 0
0x18002179d  jz      loc_180021868
0x1800217a3  cmp     byte ptr [rbx+98h], 0
0x1800217aa  jnz     loc_180021868
0x1800217b0  mov     [rbp+arg_0], 0
0x1800217b8  call    EnableErrorDetails
0x1800217bd  mov     rbx, [rbx+40h]
0x1800217c1  lea     rcx, ModuleName; "mpunits.dll"
0x1800217c8  xorps   xmm0, xmm0
0x1800217cb  mov     rdi, rax
0x1800217ce  movups  [rbp+var_18], xmm0
0x1800217d2  call    cs:__imp_GetModuleHandleA
0x1800217d8  mov     r8, rbx
0x1800217db  mov     edx, 85Bh
0x1800217e0  mov     rcx, rax
0x1800217e3  call    _Intlstr_FormatString_FormatMessage
0x1800217e8  mov     qword ptr [rbp+var_18], rax
0x1800217ec  lea     r9, [rbp+var_18]
0x1800217f0  mov     byte ptr [rbp+var_18+8], 1
0x1800217f4  lea     rdx, aMi; "MI"
0x1800217fb  movaps  xmm0, [rbp+var_18]
0x1800217ff  mov     r8d, 5
0x180021805  mov     [rsp+48h+var_20], 0; __int64
0x18002180e  movdqa  [rbp+var_18], xmm0
0x180021813  mov     [rsp+48h+var_28], 0; __int64
0x18002181c  lea     ebx, [r8-1]
0x180021820  mov     ecx, ebx; int
0x180021822  call    MI_ReportErrorDetails_ForCustomError
0x180021827  lea     rdx, [rbp+arg_0]
0x18002182b  mov     rcx, rdi
0x18002182e  call    CatchErrorDetails
0x180021833  mov     edx, ebx
0x180021835  mov     r8, [rbp+arg_0]
0x180021839  mov     rcx, rsi
0x18002183c  call    SourceSelector_Log_OnError
0x180021841  mov     rcx, [rbp+arg_0]
0x180021845  test    rcx, rcx
0x180021848  jz      loc_180021974
0x18002184e  mov     rax, [rcx]
0x180021851  test    rax, rax
0x180021854  jz      loc_180021974
0x18002185a  mov     rax, [rax+10h]
0x18002185e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021863  jmp     loc_180021974
0x180021868  mov     rcx, rbx
0x18002186b  call    SourceSelector_QueryArbiterForJob
0x180021870  test    eax, eax
0x180021872  jz      short loc_180021886
0x180021874  xor     r8d, r8d
0x180021877  mov     edx, eax
0x180021879  mov     rcx, rsi
0x18002187c  call    SourceSelector_Log_OnError
0x180021881  jmp     loc_180021974
0x180021886  cmp     byte ptr [rbx+50h], 0
0x18002188a  jnz     loc_18002191B
0x180021890  mov     [rbp+arg_0], 0
0x180021898  call    EnableErrorDetails
0x18002189d  mov     rbx, [rbx+40h]
0x1800218a1  lea     rcx, ModuleName; "mpunits.dll"
0x1800218a8  xorps   xmm0, xmm0
0x1800218ab  mov     rdi, rax
0x1800218ae  movups  [rbp+var_18], xmm0
0x1800218b2  call    cs:__imp_GetModuleHandleA
0x1800218b8  mov     r8, rbx
0x1800218bb  mov     edx, 85Ch
0x1800218c0  mov     rcx, rax
0x1800218c3  call    _Intlstr_FormatString_FormatMessage
0x1800218c8  mov     qword ptr [rbp+var_18], rax
0x1800218cc  lea     r9, [rbp+var_18]
0x1800218d0  mov     byte ptr [rbp+var_18+8], 1
0x1800218d4  lea     rdx, aMi; "MI"
0x1800218db  movaps  xmm0, [rbp+var_18]
0x1800218df  mov     r8d, 0Eh
0x1800218e5  mov     [rsp+48h+var_20], 0; __int64
0x1800218ee  movdqa  [rbp+var_18], xmm0
0x1800218f3  mov     [rsp+48h+var_28], 0; __int64
0x1800218fc  lea     ecx, [r8-0Dh]; int
0x180021900  call    MI_ReportErrorDetails_ForCustomError
0x180021905  lea     rdx, [rbp+arg_0]
0x180021909  mov     rcx, rdi
0x18002190c  call    CatchErrorDetails
0x180021911  mov     edx, 1
0x180021916  jmp     loc_180021835
0x18002191b  lea     rdi, [rbx+8]
0x18002191f  mov     rcx, rdi
0x180021922  call    TryAcquireWrite
0x180021927  test    eax, eax
0x180021929  jnz     short loc_180021933
0x18002192b  mov     rcx, rdi
0x18002192e  call    QueueAcquireWrite
0x180021933  mov     rax, [rbx]
0x180021936  test    rax, rax
0x180021939  jz      short loc_180021947
0x18002193b  mov     rcx, [rax]
0x18002193e  mov     rax, [rax+18h]
0x180021942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021947  mov     eax, [rbx+30h]
0x18002194a  mov     rcx, rdi
0x18002194d  and     eax, 0FFFFFFF9h
0x180021950  mov     qword ptr [rbx], 0
0x180021957  or      eax, 1
0x18002195a  mov     [rbx+30h], eax
0x18002195d  call    ReadWriteLock_ReleaseWrite
0x180021962  mov     eax, [rbx+30h]
0x180021965  and     al, 7
0x180021967  cmp     al, 1
0x180021969  jnz     short loc_180021974
0x18002196b  lea     rcx, [rbx+30h]
0x18002196f  call    CondLock_Broadcast
0x180021974  add     rsp, 48h
0x180021978  pop     rdi
0x180021979  pop     rsi
0x18002197a  pop     rbx
0x18002197b  pop     rbp
0x18002197c  retn
```
