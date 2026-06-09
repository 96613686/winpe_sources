# HPerformanceCounterDataCollector::Cycle(void)

- ea: `0x180049f60`
- end: `0x18004a259`
- name: `?Cycle@HPerformanceCounterDataCollector@@UEAAJXZ`
- size: `761`
- prototype: `__int64 __fastcall(HPerformanceCounterDataCollector *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x180049f60`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a134`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a06e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a122`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a06e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a122`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a22a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a22a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049fa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049fa1`
- `pdh!PdhUpdateLogW` at `0x180049fb9`
- `pdh!PdhUpdateLogW` at `0x180049fb9`

## pseudocode

```c
__int64 __fastcall HPerformanceCounterDataCollector::Cycle(HPerformanceCounterDataCollector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // ebx
  void *v4; // rcx
  PDH_STATUS updated; // eax
  int v6; // eax
  __int64 v7; // rax
  int *v8; // r9
  int *v9; // rcx
  DWORD LastError; // eax
  int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  DWORD v14; // eax
  int v15; // eax
  __int64 v16; // rax
  int v18; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v20[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v21[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v22[64]; // [rsp+180h] [rbp+80h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v4 = (void *)*((_QWORD *)this + 30);
  if ( !v4 )
    goto LABEL_31;
  updated = PdhUpdateLogW(v4, 0);
  if ( updated != -2147481643 )
  {
    if ( updated == 112 )
    {
      if ( !SetEvent(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 64LL)) )
      {
        LastError = GetLastError();
        v11 = PlaiHResultFromWin32(LastError);
        v3 = v11;
        if ( v11 < 0 )
        {
          v19 = 0;
          v18 = v11;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_31;
          }
          PlaiWhoAmI(v21, 0x4000000000000800uLL);
          v12 = -1;
          do
            ++v12;
          while ( v21[v12] );
LABEL_29:
          v8 = &v18;
          v9 = &v19;
LABEL_30:
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            v8,
            4,
            qword_180147320,
            1,
            v9,
            4,
            "HPerformanceCounterDataCollector::Cycle",
            40);
          goto LABEL_31;
        }
      }
    }
    else
    {
      v6 = PlaiHResultFromWin32(updated);
      v3 = v6;
      if ( v6 < 0 )
      {
        v18 = 0;
        v19 = v6;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v20, 0x4000000000000800uLL);
          v7 = -1;
          do
            ++v7;
          while ( v20[v7] );
          v8 = &v19;
          v9 = &v18;
          goto LABEL_30;
        }
        goto LABEL_31;
      }
    }
  }
  ++*((_DWORD *)this + 66);
  v13 = *((_DWORD *)this + 52);
  if ( v13 && *((_DWORD *)this + 66) >= v13 )
  {
    if ( SetEvent(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 64LL)) )
    {
      v3 = 0;
      goto LABEL_31;
    }
    v14 = GetLastError();
    v15 = PlaiHResultFromWin32(v14);
    v3 = v15;
    if ( v15 < 0 )
    {
      v19 = 0;
      v18 = v15;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v22, 0x4000000000000800uLL);
          v16 = -1;
          do
            ++v16;
          while ( v22[v16] );
          goto LABEL_29;
        }
      }
    }
  }
LABEL_31:
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x180049f60  mov     [rsp-8+arg_8], rbx
0x180049f65  mov     [rsp-8+arg_10], rsi
0x180049f6a  push    rbp
0x180049f6b  push    rdi
0x180049f6c  push    r14
0x180049f6e  lea     rbp, [rsp-110h]
0x180049f76  sub     rsp, 210h
0x180049f7d  mov     rax, cs:__security_cookie
0x180049f84  xor     rax, rsp
0x180049f87  mov     [rbp+120h+var_20], rax
0x180049f8e  lea     rsi, [rcx+90h]
0x180049f95  mov     rdi, rcx
0x180049f98  xor     r14d, r14d
0x180049f9b  mov     rcx, rsi; lpCriticalSection
0x180049f9e  mov     ebx, r14d
0x180049fa1  call    cs:__imp_EnterCriticalSection
0x180049fa7  mov     rcx, [rdi+0F0h]; hLog
0x180049fae  test    rcx, rcx
0x180049fb1  jz      loc_18004A227
0x180049fb7  xor     edx, edx; szUserString
0x180049fb9  call    cs:__imp_PdhUpdateLogW
0x180049fbf  cmp     eax, 800007D5h
0x180049fc4  jz      loc_18004A0F6
0x180049fca  cmp     eax, 70h ; 'p'
0x180049fcd  jz      loc_18004A062
0x180049fd3  mov     ecx, eax; unsigned int
0x180049fd5  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180049fda  mov     ebx, eax
0x180049fdc  test    eax, eax
0x180049fde  jns     loc_18004A0F6
0x180049fe4  cmp     dword ptr cs:xmmword_180169738, r14d
0x180049feb  mov     [rsp+220h+var_1B0], r14d
0x180049ff0  mov     [rsp+220h+var_1A8], eax
0x180049ff4  jz      loc_18004A227
0x180049ffa  mov     rdx, 4000000000000800h; unsigned __int64
0x18004a004  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004a00b  jz      loc_18004A227
0x18004a011  mov     rax, cs:qword_180169748
0x18004a018  and     rax, rdx
0x18004a01b  cmp     cs:qword_180169748, rax
0x18004a022  jnz     loc_18004A227
0x18004a028  lea     rcx, [rbp+120h+var_1A0]; unsigned __int16 *
0x18004a02c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004a031  lea     rcx, [rbp+120h+var_1A0]
0x18004a035  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a039  inc     rax
0x18004a03c  cmp     [rcx+rax*2], r14w
0x18004a041  jnz     short loc_18004A039
0x18004a043  lea     ecx, [rax+rax]
0x18004a046  add     rcx, 2
0x18004a04a  lea     rax, [rbp+120h+var_1A0]
0x18004a04e  mov     [rsp+220h+var_1C0], rcx
0x18004a053  lea     r9, [rsp+220h+var_1A8]
0x18004a058  lea     rcx, [rsp+220h+var_1B0]
0x18004a05d  jmp     loc_18004A1CD
0x18004a062  mov     rax, [rdi+48h]
0x18004a066  mov     rcx, [rax+38h]
0x18004a06a  mov     rcx, [rcx+40h]; hEvent
0x18004a06e  call    cs:__imp_SetEvent
0x18004a074  test    eax, eax
0x18004a076  jnz     short loc_18004A0F6
0x18004a078  call    cs:__imp_GetLastError
0x18004a07e  mov     ecx, eax; unsigned int
0x18004a080  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004a085  mov     ebx, eax
0x18004a087  test    eax, eax
0x18004a089  jns     short loc_18004A0F6
0x18004a08b  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004a092  mov     [rsp+220h+var_1A8], r14d
0x18004a097  mov     [rsp+220h+var_1B0], eax
0x18004a09b  jz      loc_18004A227
0x18004a0a1  mov     rdx, 4000000000000800h; unsigned __int64
0x18004a0ab  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004a0b2  jz      loc_18004A227
0x18004a0b8  mov     rax, cs:qword_180169748
0x18004a0bf  and     rax, rdx
0x18004a0c2  cmp     cs:qword_180169748, rax
0x18004a0c9  jnz     loc_18004A227
0x18004a0cf  lea     rcx, [rbp+120h+var_120]; unsigned __int16 *
0x18004a0d3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004a0d8  lea     rcx, [rbp+120h+var_120]
0x18004a0dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a0e0  inc     rax
0x18004a0e3  cmp     [rcx+rax*2], r14w
0x18004a0e8  jnz     short loc_18004A0E0
0x18004a0ea  lea     ecx, [rax+rax]
0x18004a0ed  lea     rax, [rbp+120h+var_120]
0x18004a0f1  jmp     loc_18004A1BA
0x18004a0f6  inc     dword ptr [rdi+108h]
0x18004a0fc  mov     eax, [rdi+0D0h]
0x18004a102  test    eax, eax
0x18004a104  jz      loc_18004A227
0x18004a10a  cmp     [rdi+108h], eax
0x18004a110  jb      loc_18004A227
0x18004a116  mov     rax, [rdi+48h]
0x18004a11a  mov     rcx, [rax+38h]
0x18004a11e  mov     rcx, [rcx+40h]; hEvent
0x18004a122  call    cs:__imp_SetEvent
0x18004a128  test    eax, eax
0x18004a12a  jz      short loc_18004A134
0x18004a12c  mov     ebx, r14d
0x18004a12f  jmp     loc_18004A227
0x18004a134  call    cs:__imp_GetLastError
0x18004a13a  mov     ecx, eax; unsigned int
0x18004a13c  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004a141  mov     ebx, eax
0x18004a143  test    eax, eax
0x18004a145  jns     loc_18004A227
0x18004a14b  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004a152  mov     [rsp+220h+var_1A8], r14d
0x18004a157  mov     [rsp+220h+var_1B0], eax
0x18004a15b  jz      loc_18004A227
0x18004a161  mov     rdx, 4000000000000800h; unsigned __int64
0x18004a16b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004a172  jz      loc_18004A227
0x18004a178  mov     rax, cs:qword_180169748
0x18004a17f  and     rax, rdx
0x18004a182  cmp     cs:qword_180169748, rax
0x18004a189  jnz     loc_18004A227
0x18004a18f  lea     rcx, [rbp+120h+var_A0]; unsigned __int16 *
0x18004a196  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004a19b  lea     rcx, [rbp+120h+var_A0]
0x18004a1a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a1a6  inc     rax
0x18004a1a9  cmp     [rcx+rax*2], r14w
0x18004a1ae  jnz     short loc_18004A1A6
0x18004a1b0  lea     ecx, [rax+rax]
0x18004a1b3  lea     rax, [rbp+120h+var_A0]
0x18004a1ba  add     rcx, 2
0x18004a1be  lea     r9, [rsp+220h+var_1B0]
0x18004a1c3  mov     [rsp+220h+var_1C0], rcx
0x18004a1c8  lea     rcx, [rsp+220h+var_1A8]
0x18004a1cd  mov     [rsp+220h+var_1C8], rax
0x18004a1d2  lea     rdx, PLA_EVENT_ERROR
0x18004a1d9  mov     [rsp+220h+var_1D0], 28h ; '('
0x18004a1e2  lea     rax, aHperformanceco; "HPerformanceCounterDataCollector::Cycle"
0x18004a1e9  mov     [rsp+220h+var_1D8], rax
0x18004a1ee  mov     eax, 4
0x18004a1f3  mov     [rsp+220h+var_1E0], rax
0x18004a1f8  mov     [rsp+220h+var_1E8], rcx
0x18004a1fd  lea     rcx, qword_180147320
0x18004a204  mov     [rsp+220h+var_1F0], 1
0x18004a20d  mov     [rsp+220h+var_1F8], rcx
0x18004a212  lea     r8d, [rax+1]
0x18004a216  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004a21d  mov     [rsp+220h+var_200], rax
0x18004a222  call    EventingWriteEvent
0x18004a227  mov     rcx, rsi; lpCriticalSection
0x18004a22a  call    cs:__imp_LeaveCriticalSection
0x18004a230  mov     eax, ebx
0x18004a232  mov     rcx, [rbp+120h+var_20]
0x18004a239  xor     rcx, rsp; StackCookie
0x18004a23c  call    __security_check_cookie
0x18004a241  lea     r11, [rsp+220h+var_10]
0x18004a249  mov     rbx, [r11+28h]
0x18004a24d  mov     rsi, [r11+30h]
0x18004a251  mov     rsp, r11
0x18004a254  pop     r14
0x18004a256  pop     rdi
0x18004a257  pop     rbp
0x18004a258  retn
```
