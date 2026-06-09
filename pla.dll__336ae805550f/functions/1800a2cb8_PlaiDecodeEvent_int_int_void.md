# PlaiDecodeEvent(int,int,void *)

- ea: `0x1800a2cb8`
- end: `0x1800a3369`
- name: `?PlaiDecodeEvent@@YAJHHPEAX@Z`
- size: `1713`
- prototype: `int(int, int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180052754`
- `0x18005dce8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x1800a2cb8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3016`
- `wevtapi!EvtClose` at `0x1800a3330`
- `wevtapi!EvtClose` at `0x1800a3330`
- `wevtapi!EvtCreateRenderContext` at `0x1800a2d23`
- `wevtapi!EvtCreateRenderContext` at `0x1800a2d23`
- `wevtapi!EvtRender` at `0x1800a2e42`
- `wevtapi!EvtRender` at `0x1800a3005`
- `wevtapi!EvtRender` at `0x1800a2e42`
- `wevtapi!EvtRender` at `0x1800a3005`

## pseudocode

```c
__int64 __fastcall PlaiDecodeEvent(__int64 a1, int a2, void *a3)
{
  const WCHAR *v5; // rax
  EVT_HANDLE RenderContext; // r13
  DWORD v7; // eax
  int v8; // ebx
  __int64 v9; // rax
  _DWORD *v10; // rdi
  DWORD LastError; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  DWORD v14; // eax
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int Buffer; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  DWORD BufferSize; // [rsp+80h] [rbp-80h] BYREF
  DWORD PropertyCount; // [rsp+84h] [rbp-7Ch] BYREF
  LPCWSTR ValuePaths[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v27[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v29[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v30[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v31[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v32[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v33[64]; // [rsp+3A0h] [rbp+2A0h] BYREF

  BufferSize = 0;
  PropertyCount = 0;
  ValuePaths[0] = L"Event/System/EventID";
  v5 = L"Event/UserData/DataCollectorSetStopFailure/Error";
  if ( a2 )
    v5 = L"Event/UserData/DataCollectorSetStartFailed/Error";
  ValuePaths[1] = v5;
  RenderContext = EvtCreateRenderContext(2u, ValuePaths, 0);
  if ( RenderContext )
  {
    v10 = 0;
    if ( EvtRender(RenderContext, a3, 0, 0, 0, &BufferSize, &PropertyCount) )
      goto LABEL_36;
    LastError = GetLastError();
    v8 = PlaiHResultFromWin32(LastError);
    if ( v8 >= 0 )
      goto LABEL_36;
    if ( v8 != -2147024774 )
    {
      v23 = 0;
      v22 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_64;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v28[v12] );
      goto LABEL_18;
    }
    v10 = PlaiAlloc(BufferSize, 1, 0, byte_180147320, Buffer);
    if ( !v10 )
    {
      v8 = -2147024882;
      v22 = -2147024882;
      v23 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_64;
      }
      PlaiWhoAmI(v29, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v29[v13] );
LABEL_18:
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v22);
LABEL_64:
      EvtClose(RenderContext);
      goto LABEL_65;
    }
    if ( EvtRender(RenderContext, a3, 0, BufferSize, v10, &BufferSize, &PropertyCount)
      || (v14 = GetLastError(), v15 = PlaiHResultFromWin32(v14), v8 = v15, v15 >= 0) )
    {
LABEL_36:
      if ( !PropertyCount || !v10 || v10[3] != 6 )
      {
        v8 = -2147467259;
        v22 = -2147467259;
        v23 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v33, 0x4000000000000800uLL);
          v19 = -1;
          do
            ++v19;
          while ( v33[v19] );
          EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v22);
        }
        if ( !v10 )
          goto LABEL_64;
        goto LABEL_63;
      }
      if ( *(_WORD *)v10 == 1003 && a2 || *(_WORD *)v10 == 1005 && !a2 )
      {
        v8 = 0;
        goto LABEL_63;
      }
      if ( PropertyCount >= 2 && v10[7] == 8 )
      {
        v8 = v10[4];
        v22 = v8;
        v23 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_63;
        }
        PlaiWhoAmI(v31, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v31[v17] );
      }
      else
      {
        v8 = -2147467259;
        v22 = -2147467259;
        v23 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_63;
        }
        PlaiWhoAmI(v32, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v32[v18] );
      }
    }
    else
    {
      v23 = 0;
      v22 = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_63;
      }
      PlaiWhoAmI(v30, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v30[v16] );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v22);
LABEL_63:
    PlaiFree(v10, 1);
    goto LABEL_64;
  }
  v7 = GetLastError();
  v8 = PlaiHResultFromWin32(v7);
  v22 = 0;
  v23 = v8;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v27, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v27[v9] );
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v23);
  }
LABEL_65:
  if ( v8 == -2147216609 )
    return (unsigned int)-2144337750;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a2cb8  push    rbp
0x1800a2cba  push    rbx
0x1800a2cbb  push    rsi
0x1800a2cbc  push    rdi
0x1800a2cbd  push    r12
0x1800a2cbf  push    r13
0x1800a2cc1  push    r14
0x1800a2cc3  push    r15
0x1800a2cc5  lea     rbp, [rsp-338h]
0x1800a2ccd  sub     rsp, 438h
0x1800a2cd4  mov     rax, cs:__security_cookie
0x1800a2cdb  xor     rax, rsp
0x1800a2cde  mov     [rbp+370h+var_50], rax
0x1800a2ce5  xor     r14d, r14d
0x1800a2ce8  lea     rcx, aEventUserdataD; "Event/UserData/DataCollectorSetStartFai"...
0x1800a2cef  test    edx, edx
0x1800a2cf1  mov     [rbp+370h+BufferSize], r14d
0x1800a2cf5  lea     rax, aEventSystemEve; "Event/System/EventID"
0x1800a2cfc  mov     [rbp+370h+var_3EC], r14d
0x1800a2d00  mov     [rbp+370h+ValuePaths], rax
0x1800a2d04  mov     r15, r8
0x1800a2d07  mov     esi, edx
0x1800a2d09  lea     rax, aEventUserdataD_0; "Event/UserData/DataCollectorSetStopFail"...
0x1800a2d10  cmovnz  rax, rcx
0x1800a2d14  lea     rdx, [rbp+370h+ValuePaths]; ValuePaths
0x1800a2d18  xor     r8d, r8d; Flags
0x1800a2d1b  mov     [rbp+370h+var_3E0], rax
0x1800a2d1f  lea     ecx, [r14+2]; ValuePathsCount
0x1800a2d23  call    cs:__imp_EvtCreateRenderContext
0x1800a2d29  mov     r13, rax
0x1800a2d2c  test    rax, rax
0x1800a2d2f  jnz     loc_1800A2E1C
0x1800a2d35  call    cs:__imp_GetLastError
0x1800a2d3b  mov     ecx, eax; unsigned int
0x1800a2d3d  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a2d42  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800a2d49  mov     ebx, eax
0x1800a2d4b  mov     [rsp+470h+var_400], r14d
0x1800a2d50  mov     [rsp+470h+var_3F8], eax
0x1800a2d54  jz      loc_1800A3336
0x1800a2d5a  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a2d64  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a2d6b  jz      loc_1800A3336
0x1800a2d71  mov     rax, cs:qword_180169748
0x1800a2d78  and     rax, rdx
0x1800a2d7b  cmp     cs:qword_180169748, rax
0x1800a2d82  jnz     loc_1800A3336
0x1800a2d88  lea     rcx, [rbp+370h+var_3D0]; unsigned __int16 *
0x1800a2d8c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a2d91  lea     rcx, [rbp+370h+var_3D0]
0x1800a2d95  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a2d99  inc     rax
0x1800a2d9c  cmp     [rcx+rax*2], r14w
0x1800a2da1  jnz     short loc_1800A2D99
0x1800a2da3  lea     ecx, [rax+rax]
0x1800a2da6  add     rcx, 2
0x1800a2daa  lea     rax, [rbp+370h+var_3D0]
0x1800a2dae  mov     [rsp+470h+var_410], rcx
0x1800a2db3  lea     r12, byte_180147320
0x1800a2dba  mov     [rsp+470h+var_418], rax
0x1800a2dbf  lea     rcx, [rsp+470h+var_400]
0x1800a2dc4  mov     [rsp+470h+var_420], 10h
0x1800a2dcd  lea     rax, aPlaidecodeeven; "PlaiDecodeEvent"
0x1800a2dd4  mov     [rsp+470h+var_428], rax
0x1800a2dd9  lea     r9, [rsp+470h+var_3F8]
0x1800a2dde  mov     eax, 4
0x1800a2de3  lea     rdx, PLA_EVENT_ERROR
0x1800a2dea  mov     [rsp+470h+var_430], rax
0x1800a2def  mov     [rsp+470h+var_438], rcx
0x1800a2df4  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a2dfb  lea     r14d, [rax-3]
0x1800a2dff  mov     [rsp+470h+PropertyCount], r14
0x1800a2e04  lea     r8d, [rax+1]
0x1800a2e08  mov     [rsp+470h+BufferUsed], r12
0x1800a2e0d  mov     [rsp+470h+Buffer], rax
0x1800a2e12  call    EventingWriteEvent
0x1800a2e17  jmp     loc_1800A3336
0x1800a2e1c  lea     rax, [rbp+370h+var_3EC]
0x1800a2e20  xor     r9d, r9d; BufferSize
0x1800a2e23  mov     [rsp+470h+PropertyCount], rax; PropertyCount
0x1800a2e28  xor     r8d, r8d; Flags
0x1800a2e2b  lea     rax, [rbp+370h+BufferSize]
0x1800a2e2f  mov     rdx, r15; Fragment
0x1800a2e32  mov     [rsp+470h+BufferUsed], rax; BufferUsed
0x1800a2e37  mov     rcx, r13; Context
0x1800a2e3a  mov     [rsp+470h+Buffer], r14; int
0x1800a2e3f  mov     rdi, r14
0x1800a2e42  call    cs:__imp_EvtRender
0x1800a2e48  mov     r14d, 1
0x1800a2e4e  lea     r12, byte_180147320
0x1800a2e55  test    eax, eax
0x1800a2e57  jnz     loc_1800A3103
0x1800a2e5d  call    cs:__imp_GetLastError
0x1800a2e63  mov     ecx, eax; unsigned int
0x1800a2e65  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a2e6a  mov     ebx, eax
0x1800a2e6c  xor     eax, eax
0x1800a2e6e  test    ebx, ebx
0x1800a2e70  jns     loc_1800A3103
0x1800a2e76  cmp     ebx, 8007007Ah
0x1800a2e7c  jz      loc_1800A2F4E
0x1800a2e82  cmp     dword ptr cs:xmmword_180169738, eax
0x1800a2e88  mov     [rsp+470h+var_3F8], eax
0x1800a2e8c  mov     [rsp+470h+var_400], ebx
0x1800a2e90  jz      loc_1800A332D
0x1800a2e96  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a2ea0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a2ea7  jz      loc_1800A332D
0x1800a2ead  mov     rax, cs:qword_180169748
0x1800a2eb4  and     rax, rdx
0x1800a2eb7  cmp     cs:qword_180169748, rax
0x1800a2ebe  jnz     loc_1800A332D
0x1800a2ec4  lea     rcx, [rbp+370h+var_350]; unsigned __int16 *
0x1800a2ec8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a2ecd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a2ed1  lea     rdx, [rbp+370h+var_350]
0x1800a2ed5  xor     ecx, ecx
0x1800a2ed7  inc     rax
0x1800a2eda  cmp     [rdx+rax*2], cx
0x1800a2ede  jnz     short loc_1800A2ED7
0x1800a2ee0  lea     ecx, [rax+rax]
0x1800a2ee3  lea     rax, [rbp+370h+var_350]
0x1800a2ee7  add     rcx, 2
0x1800a2eeb  lea     r9, [rsp+470h+var_400]
0x1800a2ef0  mov     [rsp+470h+var_410], rcx
0x1800a2ef5  lea     rdx, PLA_EVENT_ERROR
0x1800a2efc  mov     [rsp+470h+var_418], rax
0x1800a2f01  lea     rcx, [rsp+470h+var_3F8]
0x1800a2f06  mov     [rsp+470h+var_420], 10h
0x1800a2f0f  lea     rax, aPlaidecodeeven; "PlaiDecodeEvent"
0x1800a2f16  mov     [rsp+470h+var_428], rax
0x1800a2f1b  mov     eax, 4
0x1800a2f20  mov     [rsp+470h+var_430], rax
0x1800a2f25  mov     [rsp+470h+var_438], rcx
0x1800a2f2a  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a2f31  mov     [rsp+470h+PropertyCount], r14
0x1800a2f36  mov     [rsp+470h+BufferUsed], r12
0x1800a2f3b  lea     r8d, [rax+1]
0x1800a2f3f  mov     [rsp+470h+Buffer], rax
0x1800a2f44  call    EventingWriteEvent
0x1800a2f49  jmp     loc_1800A332D
0x1800a2f4e  mov     ecx, [rbp+370h+BufferSize]; dwBytes
0x1800a2f51  mov     r9, r12; char *
0x1800a2f54  xor     r8d, r8d; int
0x1800a2f57  mov     edx, r14d; int
0x1800a2f5a  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800a2f5f  mov     rdi, rax
0x1800a2f62  xor     eax, eax
0x1800a2f64  test    rdi, rdi
0x1800a2f67  jnz     short loc_1800A2FE1
0x1800a2f69  cmp     dword ptr cs:xmmword_180169738, eax
0x1800a2f6f  mov     ebx, 8007000Eh
0x1800a2f74  mov     [rsp+470h+var_400], ebx
0x1800a2f78  mov     [rsp+470h+var_3F8], eax
0x1800a2f7c  jz      loc_1800A332D
0x1800a2f82  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a2f8c  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a2f93  jz      loc_1800A332D
0x1800a2f99  mov     rax, cs:qword_180169748
0x1800a2fa0  and     rax, rdx
0x1800a2fa3  cmp     cs:qword_180169748, rax
0x1800a2faa  jnz     loc_1800A332D
0x1800a2fb0  lea     rcx, [rbp+370h+var_2D0]; unsigned __int16 *
0x1800a2fb7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a2fbc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a2fc0  lea     rdx, [rbp+370h+var_2D0]
0x1800a2fc7  xor     ecx, ecx
0x1800a2fc9  inc     rax
0x1800a2fcc  cmp     [rdx+rax*2], cx
0x1800a2fd0  jnz     short loc_1800A2FC9
0x1800a2fd2  lea     ecx, [rax+rax]
0x1800a2fd5  lea     rax, [rbp+370h+var_2D0]
0x1800a2fdc  jmp     loc_1800A2EE7
0x1800a2fe1  mov     r9d, [rbp+370h+BufferSize]; BufferSize
0x1800a2fe5  lea     rax, [rbp+370h+var_3EC]
0x1800a2fe9  mov     [rsp+470h+PropertyCount], rax; PropertyCount
0x1800a2fee  xor     r8d, r8d; Flags
0x1800a2ff1  lea     rax, [rbp+370h+BufferSize]
0x1800a2ff5  mov     rdx, r15; Fragment
0x1800a2ff8  mov     [rsp+470h+BufferUsed], rax; BufferUsed
0x1800a2ffd  mov     rcx, r13; Context
0x1800a3000  mov     [rsp+470h+Buffer], rdi; Buffer
0x1800a3005  call    cs:__imp_EvtRender
0x1800a300b  xor     r15d, r15d
0x1800a300e  test    eax, eax
0x1800a3010  jnz     loc_1800A3106
0x1800a3016  call    cs:__imp_GetLastError
0x1800a301c  mov     ecx, eax; unsigned int
0x1800a301e  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800a3023  mov     ebx, eax
0x1800a3025  test    eax, eax
0x1800a3027  jns     loc_1800A3106
0x1800a302d  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800a3034  mov     [rsp+470h+var_3F8], r15d
0x1800a3039  mov     [rsp+470h+var_400], eax
0x1800a303d  jz      loc_1800A3322
0x1800a3043  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a304d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a3054  jz      loc_1800A3322
0x1800a305a  mov     rax, cs:qword_180169748
0x1800a3061  and     rax, rdx
0x1800a3064  cmp     cs:qword_180169748, rax
0x1800a306b  jnz     loc_1800A3322
0x1800a3071  lea     rcx, [rbp+370h+var_250]; unsigned __int16 *
0x1800a3078  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a307d  lea     rcx, [rbp+370h+var_250]
0x1800a3084  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3088  inc     rax
0x1800a308b  cmp     [rcx+rax*2], r15w
0x1800a3090  jnz     short loc_1800A3088
0x1800a3092  lea     ecx, [rax+rax]
0x1800a3095  lea     rax, [rbp+370h+var_250]
0x1800a309c  add     rcx, 2
0x1800a30a0  lea     r9, [rsp+470h+var_400]
0x1800a30a5  mov     [rsp+470h+var_410], rcx
0x1800a30aa  lea     rdx, PLA_EVENT_ERROR
0x1800a30b1  mov     [rsp+470h+var_418], rax
0x1800a30b6  lea     rcx, [rsp+470h+var_3F8]
0x1800a30bb  mov     [rsp+470h+var_420], 10h
0x1800a30c4  lea     rax, aPlaidecodeeven; "PlaiDecodeEvent"
0x1800a30cb  mov     [rsp+470h+var_428], rax
0x1800a30d0  mov     eax, 4
0x1800a30d5  mov     [rsp+470h+var_430], rax
0x1800a30da  mov     [rsp+470h+var_438], rcx
0x1800a30df  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800a30e6  mov     [rsp+470h+PropertyCount], r14
0x1800a30eb  mov     [rsp+470h+BufferUsed], r12
0x1800a30f0  lea     r8d, [rax+1]
0x1800a30f4  mov     [rsp+470h+Buffer], rax
0x1800a30f9  call    EventingWriteEvent
0x1800a30fe  jmp     loc_1800A3322
0x1800a3103  xor     r15d, r15d
0x1800a3106  cmp     [rbp+370h+var_3EC], r14d
0x1800a310a  jb      loc_1800A3245
0x1800a3110  test    rdi, rdi
0x1800a3113  jz      loc_1800A3245
0x1800a3119  cmp     dword ptr [rdi+0Ch], 6
0x1800a311d  jnz     loc_1800A3245
0x1800a3123  mov     eax, 3EBh
0x1800a3128  cmp     ax, [rdi]
0x1800a312b  jnz     short loc_1800A3131
0x1800a312d  test    esi, esi
0x1800a312f  jnz     short loc_1800A313F
0x1800a3131  mov     eax, 3EDh
0x1800a3136  cmp     ax, [rdi]
0x1800a3139  jnz     short loc_1800A3147
0x1800a313b  test    esi, esi
0x1800a313d  jnz     short loc_1800A3147
0x1800a313f  mov     ebx, r15d
0x1800a3142  jmp     loc_1800A3322
0x1800a3147  cmp     [rbp+370h+var_3EC], 2
0x1800a314b  jb      short loc_1800A31CA
0x1800a314d  cmp     dword ptr [rdi+1Ch], 8
0x1800a3151  jnz     short loc_1800A31CA
0x1800a3153  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800a315a  mov     ebx, [rdi+10h]
0x1800a315d  mov     [rsp+470h+var_400], ebx
0x1800a3161  mov     [rsp+470h+var_3F8], r15d
0x1800a3166  jz      loc_1800A3322
0x1800a316c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a3176  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a317d  jz      loc_1800A3322
0x1800a3183  mov     rax, cs:qword_180169748
0x1800a318a  and     rax, rdx
0x1800a318d  cmp     cs:qword_180169748, rax
0x1800a3194  jnz     loc_1800A3322
0x1800a319a  lea     rcx, [rbp+370h+var_1D0]; unsigned __int16 *
0x1800a31a1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a31a6  lea     rcx, [rbp+370h+var_1D0]
0x1800a31ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a31b1  inc     rax
0x1800a31b4  cmp     [rcx+rax*2], r15w
0x1800a31b9  jnz     short loc_1800A31B1
0x1800a31bb  lea     ecx, [rax+rax]
0x1800a31be  lea     rax, [rbp+370h+var_1D0]
0x1800a31c5  jmp     loc_1800A309C
0x1800a31ca  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800a31d1  mov     eax, 80004005h
0x1800a31d6  mov     ebx, eax
0x1800a31d8  mov     [rsp+470h+var_400], eax
0x1800a31dc  mov     [rsp+470h+var_3F8], r15d
0x1800a31e1  jz      loc_1800A3322
0x1800a31e7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800a31f1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800a31f8  jz      loc_1800A3322
0x1800a31fe  mov     rax, cs:qword_180169748
0x1800a3205  and     rax, rdx
0x1800a3208  cmp     cs:qword_180169748, rax
0x1800a320f  jnz     loc_1800A3322
0x1800a3215  lea     rcx, [rbp+370h+var_150]; unsigned __int16 *
0x1800a321c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800a3221  lea     rcx, [rbp+370h+var_150]
0x1800a3228  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a322c  inc     rax
0x1800a322f  cmp     [rcx+rax*2], r15w
0x1800a3234  jnz     short loc_1800A322C
0x1800a3236  lea     ecx, [rax+rax]
0x1800a3239  lea     rax, [rbp+370h+var_150]
0x1800a3240  jmp     loc_1800A309C
0x1800a3245  cmp     dword ptr cs:xmmword_180169738, r15d
  ... truncated ...
```
