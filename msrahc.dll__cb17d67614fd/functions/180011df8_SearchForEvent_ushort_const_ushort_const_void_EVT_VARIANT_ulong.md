# SearchForEvent(ushort const *,ushort const *,void * *,_EVT_VARIANT * *,ulong *)

- ea: `0x180011df8`
- end: `0x1800120a8`
- name: `?SearchForEvent@@YAJPEBG0PEAPEAXPEAPEAU_EVT_VARIANT@@PEAK@Z`
- size: `688`
- prototype: `__int64 __fastcall(LPCWSTR Path, LPCWSTR Query, void **, struct _EVT_VARIANT **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011224`
- `0x1800120b0`

## callees

- `0x180011df8`
- `0x180014660`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011f4d`
- `KERNEL32!GetLastError` at `0x180011f4d`
- `KERNEL32!GetProcessHeap` at `0x180011f63`
- `KERNEL32!GetProcessHeap` at `0x18001207a`
- `KERNEL32!GetProcessHeap` at `0x180011f63`
- `KERNEL32!GetProcessHeap` at `0x18001207a`
- `KERNEL32!HeapAlloc` at `0x180011f74`
- `KERNEL32!HeapAlloc` at `0x180011f74`
- `KERNEL32!HeapFree` at `0x180012088`
- `KERNEL32!HeapFree` at `0x180012088`
- `wevtapi!EvtNext` at `0x180011ea6`
- `wevtapi!EvtNext` at `0x180011ea6`
- `wevtapi!EvtCreateRenderContext` at `0x180011ed9`
- `wevtapi!EvtCreateRenderContext` at `0x180011ed9`
- `wevtapi!EvtRender` at `0x180011f17`
- `wevtapi!EvtRender` at `0x180011fd4`
- `wevtapi!EvtRender` at `0x180011f17`
- `wevtapi!EvtRender` at `0x180011fd4`
- `wevtapi!EvtClose` at `0x180012011`
- `wevtapi!EvtClose` at `0x180012061`
- `wevtapi!EvtClose` at `0x18001206f`
- `wevtapi!EvtClose` at `0x180012011`
- `wevtapi!EvtClose` at `0x180012061`
- `wevtapi!EvtClose` at `0x18001206f`
- `wevtapi!EvtQuery` at `0x180011e4d`
- `wevtapi!EvtQuery` at `0x180011e4d`

## pseudocode

```c
__int64 __fastcall SearchForEvent(LPCWSTR Path, LPCWSTR Query, void **a3, struct _EVT_VARIANT **a4, unsigned int *a5)
{
  unsigned int *v5; // rsi
  unsigned int v6; // ebx
  struct _EVT_VARIANT *v9; // rdi
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  EVT_HANDLE v12; // r13
  unsigned int v13; // r9d
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  EVT_HANDLE RenderContext; // rax
  void *v16; // r15
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  unsigned int v19; // r9d
  DWORD v20; // ebx
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  const struct _EVENT_DESCRIPTOR *v24; // rdx
  CEventLogger *v25; // rcx
  HANDLE v26; // rax
  unsigned int v27; // r9d
  HANDLE v28; // rax
  DWORD Returned; // [rsp+40h] [rbp-10h] BYREF
  HANDLE Events; // [rsp+48h] [rbp-8h] BYREF
  DWORD BufferUsed; // [rsp+A0h] [rbp+50h] BYREF
  DWORD PropertyCount; // [rsp+A8h] [rbp+58h] BYREF

  v5 = a5;
  v6 = 0;
  Events = 0;
  Returned = 0;
  BufferUsed = 0;
  v9 = 0;
  PropertyCount = 0;
  *a3 = 0;
  if ( a4 && v5 )
  {
    *a4 = 0;
    *v5 = 0;
  }
  v12 = EvtQuery(0, Path, Query, 2u);
  if ( !v12 )
  {
    v13 = 1162;
LABEL_6:
    CEventLogger::LogError(v11, v10, L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp", v13, L"SearchForEvent", 0);
    v6 = -2147467259;
    goto LABEL_29;
  }
  if ( EvtNext(v12, 1u, &Events, 0x3E8u, 0, &Returned) && Returned == 1 )
  {
    if ( !a4 || !v5 )
    {
      *a3 = Events;
      Events = 0;
LABEL_32:
      EvtClose(v12);
      goto LABEL_33;
    }
    RenderContext = EvtCreateRenderContext(0, 0, 2u);
    v16 = RenderContext;
    if ( !RenderContext )
    {
      v13 = 1210;
      goto LABEL_6;
    }
    if ( EvtRender(RenderContext, Events, 0, BufferUsed, 0, &BufferUsed, &PropertyCount) )
    {
      v19 = 1224;
    }
    else
    {
      if ( GetLastError() == 122 )
      {
        v20 = BufferUsed;
        ProcessHeap = GetProcessHeap();
        v9 = (struct _EVT_VARIANT *)HeapAlloc(ProcessHeap, 8u, v20);
        if ( !v9 )
        {
          v6 = -2147024882;
          CEventLogger::LogError(
            v23,
            v22,
            L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
            0x4CCu,
            L"SearchForEvent",
            0x8007000E);
          goto LABEL_24;
        }
        if ( EvtRender(v16, Events, 0, BufferUsed, v9, &BufferUsed, &PropertyCount) )
        {
          v26 = Events;
          *a4 = v9;
          v9 = 0;
          *a3 = v26;
          v6 = 0;
          *v5 = PropertyCount;
          Events = 0;
          goto LABEL_24;
        }
        CEventLogger::LogError(
          v25,
          v24,
          L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
          0x4D9u,
          L"SearchForEvent",
          0);
LABEL_16:
        v6 = -2147467259;
LABEL_24:
        EvtClose(v16);
        goto LABEL_29;
      }
      v19 = 1226;
    }
    CEventLogger::LogError(v18, v17, L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp", v19, L"SearchForEvent", 0);
    goto LABEL_16;
  }
  v6 = -2147467259;
  v27 = 1178;
  if ( Returned )
    v27 = 1182;
  CEventLogger::LogError(
    (CEventLogger *)Returned,
    v14,
    L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
    v27,
    L"SearchForEvent",
    0);
LABEL_29:
  if ( Events )
    EvtClose(Events);
  if ( v12 )
    goto LABEL_32;
LABEL_33:
  if ( v9 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x180011df8  mov     [rsp-38h+arg_0], rbx
0x180011dfd  push    rbp
0x180011dfe  push    rsi
0x180011dff  push    rdi
0x180011e00  push    r12
0x180011e02  push    r13
0x180011e04  push    r14
0x180011e06  push    r15
0x180011e08  mov     rbp, rsp
0x180011e0b  sub     rsp, 50h
0x180011e0f  mov     rsi, [rbp+arg_20]
0x180011e13  xor     ebx, ebx
0x180011e15  mov     [rbp+Events], rbx
0x180011e19  mov     r14, r9
0x180011e1c  mov     [rbp+var_10], ebx
0x180011e1f  mov     r12, r8
0x180011e22  mov     [rbp+BufferUsed], ebx
0x180011e25  mov     edi, ebx
0x180011e27  mov     [rbp+arg_18], ebx
0x180011e2a  mov     [r8], rbx
0x180011e2d  test    r9, r9
0x180011e30  jz      short loc_180011E3C
0x180011e32  test    rsi, rsi
0x180011e35  jz      short loc_180011E3C
0x180011e37  mov     [r9], rbx
0x180011e3a  mov     [rsi], ebx
0x180011e3c  mov     r8, rdx; Query
0x180011e3f  mov     r15d, 2
0x180011e45  mov     rdx, rcx; Path
0x180011e48  mov     r9d, r15d; Flags
0x180011e4b  xor     ecx, ecx; Session
0x180011e4d  call    cs:__imp_EvtQuery
0x180011e53  mov     r13, rax
0x180011e56  test    rax, rax
0x180011e59  jnz     short loc_180011E87
0x180011e5b  mov     r9d, 48Ah; unsigned int
0x180011e61  lea     rax, aSearchforevent; "SearchForEvent"
0x180011e68  mov     dword ptr [rsp+50h+Returned], ebx; unsigned int
0x180011e6c  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011e73  mov     qword ptr [rsp+50h+Flags], rax; unsigned __int16 *
0x180011e78  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011e7d  mov     ebx, 80004005h
0x180011e82  jmp     loc_180012058
0x180011e87  lea     rax, [rbp+var_10]
0x180011e8b  mov     r9d, 3E8h; Timeout
0x180011e91  mov     [rsp+50h+Returned], rax; Returned
0x180011e96  lea     r8, [rbp+Events]; Events
0x180011e9a  mov     edx, 1; EventsSize
0x180011e9f  mov     [rsp+50h+Flags], ebx; Flags
0x180011ea3  mov     rcx, r13; ResultSet
0x180011ea6  call    cs:__imp_EvtNext
0x180011eac  mov     ecx, [rbp+var_10]; this
0x180011eaf  test    eax, eax
0x180011eb1  jz      loc_180012027
0x180011eb7  cmp     ecx, 1
0x180011eba  jnz     loc_180012027
0x180011ec0  test    r14, r14
0x180011ec3  jz      loc_180012019
0x180011ec9  test    rsi, rsi
0x180011ecc  jz      loc_180012019
0x180011ed2  mov     r8d, r15d; Flags
0x180011ed5  xor     edx, edx; ValuePaths
0x180011ed7  xor     ecx, ecx; ValuePathsCount
0x180011ed9  call    cs:__imp_EvtCreateRenderContext
0x180011edf  mov     r15, rax
0x180011ee2  test    rax, rax
0x180011ee5  jnz     short loc_180011EF2
0x180011ee7  mov     r9d, 4BAh
0x180011eed  jmp     loc_180011E61
0x180011ef2  mov     r9d, [rbp+BufferUsed]; BufferSize
0x180011ef6  lea     rax, [rbp+arg_18]
0x180011efa  mov     rdx, [rbp+Events]; Fragment
0x180011efe  xor     r8d, r8d; Flags
0x180011f01  mov     [rsp+50h+PropertyCount], rax; PropertyCount
0x180011f06  mov     rcx, r15; Context
0x180011f09  lea     rax, [rbp+BufferUsed]
0x180011f0d  mov     [rsp+50h+Returned], rax; BufferUsed
0x180011f12  mov     qword ptr [rsp+50h+Flags], rbx; Buffer
0x180011f17  call    cs:__imp_EvtRender
0x180011f1d  test    eax, eax
0x180011f1f  jz      short loc_180011F4D
0x180011f21  mov     r9d, 4C8h; unsigned int
0x180011f27  mov     dword ptr [rsp+50h+Returned], ebx; unsigned int
0x180011f2b  lea     rax, aSearchforevent; "SearchForEvent"
0x180011f32  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011f39  mov     qword ptr [rsp+50h+Flags], rax; unsigned __int16 *
0x180011f3e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011f43  mov     ebx, 80004005h
0x180011f48  jmp     loc_18001200E
0x180011f4d  call    cs:__imp_GetLastError
0x180011f53  cmp     eax, 7Ah ; 'z'
0x180011f56  jz      short loc_180011F60
0x180011f58  mov     r9d, 4CAh
0x180011f5e  jmp     short loc_180011F27
0x180011f60  mov     ebx, [rbp+BufferUsed]
0x180011f63  call    cs:__imp_GetProcessHeap
0x180011f69  mov     r8d, ebx; dwBytes
0x180011f6c  mov     edx, 8; dwFlags
0x180011f71  mov     rcx, rax; hHeap
0x180011f74  call    cs:__imp_HeapAlloc
0x180011f7a  mov     rdi, rax
0x180011f7d  test    rax, rax
0x180011f80  jnz     short loc_180011FAF
0x180011f82  lea     rax, aSearchforevent; "SearchForEvent"
0x180011f89  mov     dword ptr [rsp+50h+Returned], 8007000Eh; unsigned int
0x180011f91  mov     r9d, 4CCh; unsigned int
0x180011f97  mov     qword ptr [rsp+50h+Flags], rax; unsigned __int16 *
0x180011f9c  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011fa3  mov     ebx, 8007000Eh
0x180011fa8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011fad  jmp     short loc_18001200E
0x180011faf  mov     r9d, [rbp+BufferUsed]; BufferSize
0x180011fb3  lea     rax, [rbp+arg_18]
0x180011fb7  mov     rdx, [rbp+Events]; Fragment
0x180011fbb  xor     r8d, r8d; Flags
0x180011fbe  mov     [rsp+50h+PropertyCount], rax; PropertyCount
0x180011fc3  mov     rcx, r15; Context
0x180011fc6  lea     rax, [rbp+BufferUsed]
0x180011fca  mov     [rsp+50h+Returned], rax; BufferUsed
0x180011fcf  mov     qword ptr [rsp+50h+Flags], rdi; Buffer
0x180011fd4  call    cs:__imp_EvtRender
0x180011fda  cmp     eax, 1
0x180011fdd  jz      short loc_180011FF2
0x180011fdf  mov     dword ptr [rsp+50h+Returned], 0
0x180011fe7  mov     r9d, 4D9h
0x180011fed  jmp     loc_180011F2B
0x180011ff2  mov     rax, [rbp+Events]
0x180011ff6  mov     [r14], rdi
0x180011ff9  xor     edi, edi
0x180011ffb  mov     [r12], rax
0x180011fff  xor     ebx, ebx
0x180012001  mov     eax, [rbp+arg_18]
0x180012004  mov     [rsi], eax
0x180012006  mov     [rbp+Events], 0
0x18001200e  mov     rcx, r15; Object
0x180012011  call    cs:__imp_EvtClose
0x180012017  jmp     short loc_180012058
0x180012019  mov     rax, [rbp+Events]
0x18001201d  mov     [r12], rax
0x180012021  mov     [rbp+Events], rbx
0x180012025  jmp     short loc_18001206C
0x180012027  mov     dword ptr [rsp+50h+Returned], edi; unsigned int
0x18001202b  lea     rax, aSearchforevent; "SearchForEvent"
0x180012032  mov     qword ptr [rsp+50h+Flags], rax; unsigned __int16 *
0x180012037  mov     ebx, 80004005h
0x18001203c  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180012043  mov     r9d, 49Ah
0x180012049  test    ecx, ecx
0x18001204b  jz      short loc_180012053
0x18001204d  mov     r9d, 49Eh; unsigned int
0x180012053  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180012058  mov     rcx, [rbp+Events]; Object
0x18001205c  test    rcx, rcx
0x18001205f  jz      short loc_180012067
0x180012061  call    cs:__imp_EvtClose
0x180012067  test    r13, r13
0x18001206a  jz      short loc_180012075
0x18001206c  mov     rcx, r13; Object
0x18001206f  call    cs:__imp_EvtClose
0x180012075  test    rdi, rdi
0x180012078  jz      short loc_18001208E
0x18001207a  call    cs:__imp_GetProcessHeap
0x180012080  mov     r8, rdi; lpMem
0x180012083  xor     edx, edx; dwFlags
0x180012085  mov     rcx, rax; hHeap
0x180012088  call    cs:__imp_HeapFree
0x18001208e  mov     eax, ebx
0x180012090  mov     rbx, [rsp+50h+arg_0]
0x180012098  add     rsp, 50h
0x18001209c  pop     r15
0x18001209e  pop     r14
0x1800120a0  pop     r13
0x1800120a2  pop     r12
0x1800120a4  pop     rdi
0x1800120a5  pop     rsi
0x1800120a6  pop     rbp
0x1800120a7  retn
```
