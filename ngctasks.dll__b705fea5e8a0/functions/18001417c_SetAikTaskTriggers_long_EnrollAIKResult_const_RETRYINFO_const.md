# SetAikTaskTriggers(long,EnrollAIKResult const *,_RETRYINFO const *)

- ea: `0x18001417c`
- end: `0x1800142cb`
- name: `?SetAikTaskTriggers@@YAJJPEBUEnrollAIKResult@@PEBU_RETRYINFO@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(int, const struct EnrollAIKResult *, const struct _RETRYINFO *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011028`

## callees

- `0x18000cc34`
- `0x18000ebc0`
- `0x18001417c`
- `0x180015a40`
- `0x180016100`
- `0x1800161f4`
- `0x180016440`
- `0x180016570`

## string_xrefs

- `0x1800141ac`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800141d8`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001428d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800142af`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014274`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
__int64 __fastcall SetAikTaskTriggers(int a1, const struct EnrollAIKResult *a2, const struct _LLFILETIME *a3)
{
  int RetryTimeStamp; // ebx
  __int64 v4; // rdx
  int v6; // eax
  char v7; // zf
  int dwLowDateTime; // edx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-28h]
  struct _LLFILETIME v13; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _LLFILETIME v15; // [rsp+68h] [rbp+20h] BYREF

  if ( a1 >= 0 || *((_DWORD *)a2 + 22) == 1 )
  {
    v9 = reschedRemoveTrigger(TASK_TRIGGER_LOGON);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v9,
        v12);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x49F,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)v10);
    }
    v11 = RemoveAikTimeTrigger();
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4A0,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v11);
  }
  else
  {
    if ( a3->ft.dwLowDateTime >= 5 )
    {
      RetryTimeStamp = -2147024875;
      v4 = 1197;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)RetryTimeStamp,
        v12);
      return (unsigned int)RetryTimeStamp;
    }
    if ( a1 == -2145844841 )
    {
      v6 = RemoveAikTimeTrigger();
      if ( v6 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4B1,
          (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v6);
      RetryTimeStamp = SetAikLogonTrigger();
      if ( RetryTimeStamp < 0 )
      {
        v4 = 1202;
        goto LABEL_5;
      }
    }
    else
    {
      v7 = *((_DWORD *)a2 + 22) == 3;
      dwLowDateTime = a3->ft.dwLowDateTime;
      v13.ll = a3[3].ll;
      v15.ll = 0;
      RetryTimeStamp = GetRetryTimeStamp(v7, dwLowDateTime, &v13, a3 + 3, &v15);
      if ( RetryTimeStamp < 0 )
      {
        v4 = 1216;
        goto LABEL_5;
      }
      RetryTimeStamp = SetAikTimeTrigger((const struct _FILETIME *)&v15);
      if ( RetryTimeStamp < 0 )
      {
        v4 = 1220;
        goto LABEL_5;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001417c  push    rbx
0x18001417e  sub     rsp, 40h
0x180014182  mov     r10, r8
0x180014185  test    ecx, ecx
0x180014187  jns     loc_18001425F
0x18001418d  cmp     dword ptr [rdx+58h], 1
0x180014191  jz      loc_18001425F
0x180014197  cmp     dword ptr [r8], 5
0x18001419b  jb      short loc_1800141C2
0x18001419d  mov     ebx, 80070015h
0x1800141a2  mov     edx, 4ADh; void *
0x1800141a7  mov     rcx, [rsp+48h]; this
0x1800141ac  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800141b3  mov     r9d, ebx; char *
0x1800141b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141bb  mov     eax, ebx
0x1800141bd  jmp     loc_1800142C5
0x1800141c2  cmp     ecx, 80190197h
0x1800141c8  jnz     short loc_180014202
0x1800141ca  call    ?RemoveAikTimeTrigger@@YAJXZ; RemoveAikTimeTrigger(void)
0x1800141cf  test    eax, eax
0x1800141d1  jns     short loc_1800141EC
0x1800141d3  mov     rcx, [rsp+48h]; this
0x1800141d8  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800141df  mov     r9d, eax; char *
0x1800141e2  mov     edx, 4B1h; void *
0x1800141e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800141ec  call    ?SetAikLogonTrigger@@YAJXZ; SetAikLogonTrigger(void)
0x1800141f1  mov     ebx, eax
0x1800141f3  test    eax, eax
0x1800141f5  jns     loc_1800142C3
0x1800141fb  mov     edx, 4B2h
0x180014200  jmp     short loc_1800141A7
0x180014202  cmp     dword ptr [rdx+58h], 3
0x180014206  lea     r9, [r8+18h]; struct _LLFILETIME *
0x18001420a  mov     rax, [r9]
0x18001420d  lea     r8, [rsp+48h+var_18]; struct _LLFILETIME *
0x180014212  mov     edx, [r10]; unsigned int
0x180014215  setz    cl; bool
0x180014218  mov     qword ptr [rsp+48h+var_18], rax
0x18001421d  lea     rax, [rsp+48h+arg_18]
0x180014222  mov     qword ptr [rsp+48h+var_28], rax; struct _LLFILETIME *
0x180014227  mov     qword ptr [rsp+48h+arg_18], 0
0x180014230  call    ?GetRetryTimeStamp@@YAJ_NKPEBU_LLFILETIME@@1PEAU1@@Z; GetRetryTimeStamp(bool,ulong,_LLFILETIME const *,_LLFILETIME const *,_LLFILETIME *)
0x180014235  mov     ebx, eax
0x180014237  test    eax, eax
0x180014239  jns     short loc_180014245
0x18001423b  mov     edx, 4C0h
0x180014240  jmp     loc_1800141A7
0x180014245  lea     rcx, [rsp+48h+arg_18]; struct _FILETIME *
0x18001424a  call    ?SetAikTimeTrigger@@YAJPEBU_FILETIME@@@Z; SetAikTimeTrigger(_FILETIME const *)
0x18001424f  mov     ebx, eax
0x180014251  test    eax, eax
0x180014253  jns     short loc_1800142C3
0x180014255  mov     edx, 4C4h
0x18001425a  jmp     loc_1800141A7
0x18001425f  mov     ecx, 9; enum _TASK_TRIGGER_TYPE2
0x180014264  call    ?reschedRemoveTrigger@@YAJW4_TASK_TRIGGER_TYPE2@@@Z; reschedRemoveTrigger(_TASK_TRIGGER_TYPE2)
0x180014269  mov     ebx, eax
0x18001426b  test    eax, eax
0x18001426d  jns     short loc_1800142A1
0x18001426f  mov     rcx, [rsp+48h]; this
0x180014274  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001427b  mov     r9d, eax; char *
0x18001427e  mov     edx, 205h; void *
0x180014283  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014288  mov     rcx, [rsp+48h]; this
0x18001428d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014294  mov     r9d, ebx; char *
0x180014297  mov     edx, 49Fh; void *
0x18001429c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800142a1  call    ?RemoveAikTimeTrigger@@YAJXZ; RemoveAikTimeTrigger(void)
0x1800142a6  test    eax, eax
0x1800142a8  jns     short loc_1800142C3
0x1800142aa  mov     rcx, [rsp+48h]; this
0x1800142af  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800142b6  mov     r9d, eax; char *
0x1800142b9  mov     edx, 4A0h; void *
0x1800142be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800142c3  xor     eax, eax
0x1800142c5  add     rsp, 40h
0x1800142c9  pop     rbx
0x1800142ca  retn
```
