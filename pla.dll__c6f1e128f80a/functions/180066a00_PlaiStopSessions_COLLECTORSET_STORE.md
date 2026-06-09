# PlaiStopSessions(_COLLECTORSET_STORE *)

- ea: `0x180066a00`
- end: `0x180066cd3`
- name: `?PlaiStopSessions@@YAXPEAU_COLLECTORSET_STORE@@@Z`
- size: `723`
- prototype: `void __fastcall(struct _COLLECTORSET_STORE *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800be7e0`
- `0x18012cd00`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x180066a00`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066a57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066bb8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066a46`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066baa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066a46`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180066baa`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x180066b99`
- `api-ms-win-eventing-controller-l1-1-0!StopTraceW` at `0x180066b99`

## pseudocode

```c
void __fastcall PlaiStopSessions(HANDLE *a1)
{
  DWORD v2; // eax
  int v3; // eax
  __int64 v4; // rax
  __int64 *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rsi
  TRACEHANDLE v8; // rcx
  DWORD LastError; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // [rsp+70h] [rbp-90h] BYREF
  int v13; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v15[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v16[64]; // [rsp+180h] [rbp+80h] BYREF

  memset_0(&Properties, 0, sizeof(Properties));
  if ( SetThreadToken(0, a1[7]) || (v2 = GetLastError(), v3 = PlaiHResultFromWin32(v2), v3 >= 0) )
  {
    v5 = (__int64 *)(a1 + 9);
    v6 = 0;
    v7 = *v5;
    do
    {
      if ( !v7 )
        break;
      if ( ((1LL << v6) & v7) != 0 )
      {
        v7 &= ~(1LL << v6);
        memset_0(&Properties, 0, sizeof(Properties));
        Properties.Wnode.BufferSize = 120;
        v8 = 0xFFFF;
        Properties.Wnode.Flags = 0x20000;
        if ( v6 )
          v8 = v6;
        StopTraceW(v8, 0, &Properties);
      }
      ++v6;
    }
    while ( v6 < 0x40 );
    if ( !SetThreadToken(0, 0) )
    {
      LastError = GetLastError();
      v10 = PlaiHResultFromWin32(LastError);
      if ( v10 < 0 )
      {
        v13 = 0;
        v12 = v10;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v16, 0x4000000000000800uLL);
            v11 = -1;
            do
              ++v11;
            while ( v16[v11] );
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              &v12,
              4,
              qword_180147320,
              1,
              &v13,
              4,
              "PlaiStopSessions",
              17);
          }
        }
      }
    }
  }
  else
  {
    v12 = 0;
    v13 = v3;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v15, 0x4000000000000800uLL);
      v4 = -1;
      do
        ++v4;
      while ( v15[v4] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v13, 4, qword_180147320, 1, &v12, 4, "PlaiStopSessions", 17);
    }
    v5 = (__int64 *)(a1 + 9);
  }
  *v5 = 0;
}

```

## disassembly

```asm
0x180066a00  mov     [rsp-8+arg_8], rbx
0x180066a05  mov     [rsp-8+arg_10], rsi
0x180066a0a  push    rbp
0x180066a0b  push    rdi
0x180066a0c  push    r15
0x180066a0e  lea     rbp, [rsp-110h]
0x180066a16  sub     rsp, 210h
0x180066a1d  mov     rax, cs:__security_cookie
0x180066a24  xor     rax, rsp
0x180066a27  mov     [rbp+120h+var_20], rax
0x180066a2e  xor     edx, edx; Val
0x180066a30  mov     rbx, rcx
0x180066a33  lea     rcx, [rbp+120h+Properties]; void *
0x180066a37  lea     r8d, [rdx+78h]; Size
0x180066a3b  call    memset_0
0x180066a40  mov     rdx, [rbx+38h]; Token
0x180066a44  xor     ecx, ecx; Thread
0x180066a46  call    cs:__imp_SetThreadToken
0x180066a4c  xor     r15d, r15d
0x180066a4f  test    eax, eax
0x180066a51  jnz     loc_180066B48
0x180066a57  call    cs:__imp_GetLastError
0x180066a5d  mov     ecx, eax; unsigned int
0x180066a5f  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180066a64  test    eax, eax
0x180066a66  jns     loc_180066B48
0x180066a6c  cmp     dword ptr cs:xmmword_180169738, r15d
0x180066a73  mov     [rsp+220h+var_1B0], r15d
0x180066a78  mov     [rsp+220h+var_1A8], eax
0x180066a7c  jz      loc_180066B3F
0x180066a82  mov     rdx, 4000000000000800h; unsigned __int64
0x180066a8c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180066a93  jz      loc_180066B3F
0x180066a99  mov     rax, cs:qword_180169748
0x180066aa0  and     rax, rdx
0x180066aa3  cmp     cs:qword_180169748, rax
0x180066aaa  jnz     loc_180066B3F
0x180066ab0  lea     rcx, [rbp+120h+var_120]; unsigned __int16 *
0x180066ab4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180066ab9  lea     rcx, [rbp+120h+var_120]
0x180066abd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066ac1  inc     rax
0x180066ac4  cmp     [rcx+rax*2], r15w
0x180066ac9  jnz     short loc_180066AC1
0x180066acb  lea     ecx, [rax+rax]
0x180066ace  add     rcx, 2
0x180066ad2  lea     rax, [rbp+120h+var_120]
0x180066ad6  mov     [rsp+220h+var_1C0], rcx
0x180066adb  lea     r9, [rsp+220h+var_1A8]
0x180066ae0  mov     [rsp+220h+var_1C8], rax
0x180066ae5  lea     rcx, [rsp+220h+var_1B0]
0x180066aea  mov     [rsp+220h+var_1D0], 11h
0x180066af3  lea     rax, aPlaistopsessio; "PlaiStopSessions"
0x180066afa  mov     [rsp+220h+var_1D8], rax
0x180066aff  lea     rdx, PLA_EVENT_ERROR
0x180066b06  mov     eax, 4
0x180066b0b  mov     [rsp+220h+var_1E0], rax
0x180066b10  mov     [rsp+220h+var_1E8], rcx
0x180066b15  lea     rcx, qword_180147320
0x180066b1c  mov     [rsp+220h+var_1F0], 1
0x180066b25  mov     [rsp+220h+var_1F8], rcx
0x180066b2a  lea     r8d, [rax+1]
0x180066b2e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180066b35  mov     [rsp+220h+var_200], rax
0x180066b3a  call    EventingWriteEvent
0x180066b3f  add     rbx, 48h ; 'H'
0x180066b43  jmp     loc_180066CA9
0x180066b48  add     rbx, 48h ; 'H'
0x180066b4c  mov     edi, r15d
0x180066b4f  mov     rsi, [rbx]
0x180066b52  test    rsi, rsi
0x180066b55  jz      short loc_180066BA6
0x180066b57  mov     ecx, edi
0x180066b59  mov     eax, 1
0x180066b5e  shl     rax, cl
0x180066b61  test    rsi, rax
0x180066b64  jz      short loc_180066B9F
0x180066b66  xor     edx, edx; Val
0x180066b68  lea     rcx, [rbp+120h+Properties]; void *
0x180066b6c  not     rax
0x180066b6f  and     rsi, rax
0x180066b72  lea     r8d, [rdx+78h]; Size
0x180066b76  call    memset_0
0x180066b7b  test    edi, edi
0x180066b7d  mov     [rbp+120h+Properties.Wnode.BufferSize], 78h ; 'x'
0x180066b84  mov     ecx, 0FFFFh
0x180066b89  mov     [rbp+120h+Properties.Wnode.Flags], 20000h
0x180066b90  cmovnz  ecx, edi; TraceHandle
0x180066b93  lea     r8, [rbp+120h+Properties]; Properties
0x180066b97  xor     edx, edx; InstanceName
0x180066b99  call    cs:__imp_StopTraceW
0x180066b9f  inc     edi
0x180066ba1  cmp     edi, 40h ; '@'
0x180066ba4  jb      short loc_180066B52
0x180066ba6  xor     edx, edx; Token
0x180066ba8  xor     ecx, ecx; Thread
0x180066baa  call    cs:__imp_SetThreadToken
0x180066bb0  test    eax, eax
0x180066bb2  jnz     loc_180066CA9
0x180066bb8  call    cs:__imp_GetLastError
0x180066bbe  mov     ecx, eax; unsigned int
0x180066bc0  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180066bc5  test    eax, eax
0x180066bc7  jns     loc_180066CA9
0x180066bcd  cmp     dword ptr cs:xmmword_180169738, r15d
0x180066bd4  mov     [rsp+220h+var_1A8], r15d
0x180066bd9  mov     [rsp+220h+var_1B0], eax
0x180066bdd  jz      loc_180066CA9
0x180066be3  mov     rdx, 4000000000000800h; unsigned __int64
0x180066bed  test    qword ptr cs:xmmword_180169738+8, rdx
0x180066bf4  jz      loc_180066CA9
0x180066bfa  mov     rax, cs:qword_180169748
0x180066c01  and     rax, rdx
0x180066c04  cmp     cs:qword_180169748, rax
0x180066c0b  jnz     loc_180066CA9
0x180066c11  lea     rcx, [rbp+120h+var_A0]; unsigned __int16 *
0x180066c18  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180066c1d  lea     rcx, [rbp+120h+var_A0]
0x180066c24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066c28  inc     rax
0x180066c2b  cmp     [rcx+rax*2], r15w
0x180066c30  jnz     short loc_180066C28
0x180066c32  lea     ecx, [rax+rax]
0x180066c35  add     rcx, 2
0x180066c39  lea     rax, [rbp+120h+var_A0]
0x180066c40  mov     [rsp+220h+var_1C0], rcx
0x180066c45  lea     r9, [rsp+220h+var_1B0]
0x180066c4a  mov     [rsp+220h+var_1C8], rax
0x180066c4f  lea     rcx, [rsp+220h+var_1A8]
0x180066c54  mov     [rsp+220h+var_1D0], 11h
0x180066c5d  lea     rax, aPlaistopsessio; "PlaiStopSessions"
0x180066c64  mov     [rsp+220h+var_1D8], rax
0x180066c69  lea     rdx, PLA_EVENT_ERROR
0x180066c70  mov     eax, 4
0x180066c75  mov     [rsp+220h+var_1E0], rax
0x180066c7a  mov     [rsp+220h+var_1E8], rcx
0x180066c7f  lea     rcx, qword_180147320
0x180066c86  mov     [rsp+220h+var_1F0], 1
0x180066c8f  mov     [rsp+220h+var_1F8], rcx
0x180066c94  lea     r8d, [rax+1]
0x180066c98  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180066c9f  mov     [rsp+220h+var_200], rax
0x180066ca4  call    EventingWriteEvent
0x180066ca9  mov     [rbx], r15
0x180066cac  mov     rcx, [rbp+120h+var_20]
0x180066cb3  xor     rcx, rsp; StackCookie
0x180066cb6  call    __security_check_cookie
0x180066cbb  lea     r11, [rsp+220h+var_10]
0x180066cc3  mov     rbx, [r11+28h]
0x180066cc7  mov     rsi, [r11+30h]
0x180066ccb  mov     rsp, r11
0x180066cce  pop     r15
0x180066cd0  pop     rdi
0x180066cd1  pop     rbp
0x180066cd2  retn
```
