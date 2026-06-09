# ESIMPM::WwanTimerInit(void * *)

- ea: `0x140023404`
- end: `0x140023527`
- name: `?WwanTimerInit@ESIMPM@@YAKPEAPEAX@Z`
- size: `291`
- prototype: `unsigned int __fastcall(ESIMPM *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140024d88`

## callees

- `0x140014f64`
- `0x140020620`
- `0x140023404`
- `0x1400355d8`
- `0x1400356cc`
- `0x14003570c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023451`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x140023441`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x140023441`

## string_xrefs

- `0x140023500`: `Timer Library Initialization Completed`

## pseudocode

```c
__int64 __fastcall ESIMPM::WwanTimerInit(ESIMPM *this, void **a2)
{
  DWORD v2; // ebx
  HANDLE TimerQueue; // rdi
  DWORD LastError; // eax
  _QWORD *v5; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
  v2 = 0;
  TimerQueue = CreateTimerQueue();
  if ( TimerQueue || (LastError = GetLastError(), (v2 = LastError) == 0) )
  {
    g_hTimerContext = TimerQueue;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, TimerQueue);
      goto LABEL_12;
    }
LABEL_13:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
      WPP_SF_d(v5[2], 14, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v2);
    if ( v2 )
      goto LABEL_17;
LABEL_18:
    ESIMPM::Log::Info("ESIMPM::WwanTimerInit", 0, L"Timer Library Initialization Completed");
    return v2;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, LastError);
LABEL_12:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_13;
    }
    goto LABEL_13;
  }
LABEL_17:
  ESIMPM::Log::Error("ESIMPM::WwanTimerInit", 0, L"Timer Library Initializaton Failed [%d]", v2);
  return v2;
}

```

## disassembly

```asm
0x140023404  mov     [rsp+arg_0], rbx
0x140023409  mov     [rsp+arg_8], rsi
0x14002340e  push    rdi
0x14002340f  sub     rsp, 20h
0x140023413  mov     rcx, cs:WPP_GLOBAL_Control
0x14002341a  lea     rsi, WPP_GLOBAL_Control
0x140023421  cmp     rcx, rsi
0x140023424  jz      short loc_140023441
0x140023426  test    byte ptr [rcx+1Ch], 8
0x14002342a  jz      short loc_140023441
0x14002342c  mov     rcx, [rcx+10h]
0x140023430  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023437  mov     edx, 0Ah
0x14002343c  call    WPP_SF_
0x140023441  call    cs:__imp_CreateTimerQueue
0x140023447  xor     ebx, ebx
0x140023449  mov     rdi, rax
0x14002344c  test    rax, rax
0x14002344f  jnz     short loc_140023487
0x140023451  call    cs:__imp_GetLastError
0x140023457  mov     ebx, eax
0x140023459  test    eax, eax
0x14002345b  jz      short loc_140023487
0x14002345d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023464  cmp     rcx, rsi
0x140023467  jz      short loc_1400234E6
0x140023469  test    byte ptr [rcx+1Ch], 4
0x14002346d  jz      short loc_1400234BF
0x14002346f  mov     rcx, [rcx+10h]
0x140023473  lea     edx, [rdi+0Ch]
0x140023476  mov     r9d, eax
0x140023479  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140023480  call    WPP_SF_d
0x140023485  jmp     short loc_1400234B8
0x140023487  mov     cs:?g_hTimerContext@@3PEAXEA, rdi; void * g_hTimerContext
0x14002348e  mov     rcx, cs:WPP_GLOBAL_Control
0x140023495  cmp     rcx, rsi
0x140023498  jz      short loc_140023500
0x14002349a  test    byte ptr [rcx+1Ch], 2
0x14002349e  jz      short loc_1400234BF
0x1400234a0  mov     rcx, [rcx+10h]
0x1400234a4  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1400234ab  mov     edx, 0Dh
0x1400234b0  mov     r9, rdi
0x1400234b3  call    WPP_SF_q
0x1400234b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234bf  cmp     rcx, rsi
0x1400234c2  jz      short loc_1400234E2
0x1400234c4  test    byte ptr [rcx+1Ch], 8
0x1400234c8  jz      short loc_1400234E2
0x1400234ca  mov     rcx, [rcx+10h]
0x1400234ce  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1400234d5  mov     edx, 0Eh
0x1400234da  mov     r9d, ebx
0x1400234dd  call    WPP_SF_d
0x1400234e2  test    ebx, ebx
0x1400234e4  jz      short loc_140023500
0x1400234e6  mov     r9d, ebx
0x1400234e9  lea     r8, aTimerLibraryIn; "Timer Library Initializaton Failed [%d]"
0x1400234f0  xor     edx, edx; struct _GUID *
0x1400234f2  lea     rcx, aEsimpmWwantime_0; "ESIMPM::WwanTimerInit"
0x1400234f9  call    ?Error@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Error(char const *,_GUID const *,ushort const *,...)
0x1400234fe  jmp     short loc_140023515
0x140023500  lea     r8, aTimerLibraryIn_0; "Timer Library Initialization Completed"
0x140023507  xor     edx, edx; struct _GUID *
0x140023509  lea     rcx, aEsimpmWwantime_0; "ESIMPM::WwanTimerInit"
0x140023510  call    ?Info@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Info(char const *,_GUID const *,ushort const *,...)
0x140023515  mov     rsi, [rsp+28h+arg_8]
0x14002351a  mov     eax, ebx
0x14002351c  mov     rbx, [rsp+28h+arg_0]
0x140023521  add     rsp, 20h
0x140023525  pop     rdi
0x140023526  retn
```
