# CreateTimer

- ea: `0x14003574c`
- end: `0x14003598e`
- name: `CreateTimer`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140024220`

## callees

- `0x1400355d8`
- `0x1400356cc`
- `0x14003570c`
- `0x14003574c`
- `0x140035d64`
- `0x140035fa8`
- `0x1400360bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035880`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x140035876`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x140035876`

## string_xrefs

- `0x140035938`: `CreateTimer`

## pseudocode

```c
__int64 __fastcall CreateTimer(_QWORD *a1, void *a2, __int64 a3, __int64 a4)
{
  _QWORD *v8; // rcx
  void *v9; // rcx
  DWORD LastError; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rdi
  PVOID Parameter; // [rsp+78h] [rbp+10h] BYREF

  Parameter = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 || !a1 || !a3 )
  {
    v11 = 87;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_(v8[2], 21, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    goto LABEL_28;
  }
  *a1 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, a3, a4, ESIMPM::CoreFSM::s_TimerExpirationCallBack, a2);
  LastError = AllocateMemory(v9, &Parameter);
  v11 = LastError;
  if ( LastError )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_28;
    v13 = 23;
LABEL_14:
    WPP_SF_d(v12[2], v13, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, LastError);
LABEL_28:
    FreeMemory(&Parameter, "CreateTimer", 161);
    goto LABEL_29;
  }
  v14 = Parameter;
  if ( !CreateTimerQueueTimer((PHANDLE)Parameter + 6, a2, TimerTimeout, Parameter, 0x7CFFF060u, 0x7FFFFFFFu, 0) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_28;
      v13 = 24;
      goto LABEL_14;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v14);
  *v14 = a2;
  v14[2] = a3;
  v14[3] = a4;
  v14[4] = ESIMPM::CoreFSM::s_TimerExpirationCallBack;
  *((_DWORD *)v14 + 2) = 1;
  v14[5] = 0;
  *((_DWORD *)v14 + 14) = 2097148000;
  *a1 = v14;
  if ( v11 )
    goto LABEL_28;
LABEL_29:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x14003574c  mov     [rsp+arg_0], rbx
0x140035751  mov     [rsp+arg_10], rbp
0x140035756  push    rsi
0x140035757  push    rdi
0x140035758  push    r13
0x14003575a  push    r14
0x14003575c  push    r15
0x14003575e  sub     rsp, 40h
0x140035762  mov     r15, r9
0x140035765  mov     [rsp+68h+Parameter], 0
0x14003576e  mov     rbp, r8
0x140035771  mov     rsi, rdx
0x140035774  mov     r14, rcx
0x140035777  mov     rcx, cs:WPP_GLOBAL_Control
0x14003577e  lea     r13, WPP_GLOBAL_Control
0x140035785  lea     rdi, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x14003578c  cmp     rcx, r13
0x14003578f  jz      short loc_1400357AF
0x140035791  test    byte ptr [rcx+1Ch], 8
0x140035795  jz      short loc_1400357AF
0x140035797  mov     rcx, [rcx+10h]
0x14003579b  mov     edx, 14h
0x1400357a0  mov     r8, rdi
0x1400357a3  call    WPP_SF_
0x1400357a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357af  test    rsi, rsi
0x1400357b2  jz      loc_140035913
0x1400357b8  test    r14, r14
0x1400357bb  jz      loc_140035913
0x1400357c1  test    rbp, rbp
0x1400357c4  jz      loc_140035913
0x1400357ca  mov     qword ptr [r14], 0
0x1400357d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400357d8  lea     rax, ?s_TimerExpirationCallBack@CoreFSM@ESIMPM@@CAXPEAX0@Z; ESIMPM::CoreFSM::s_TimerExpirationCallBack(void *,void *)
0x1400357df  cmp     rcx, r13
0x1400357e2  jz      short loc_140035805
0x1400357e4  test    byte ptr [rcx+1Ch], 2
0x1400357e8  jz      short loc_140035805
0x1400357ea  mov     rcx, [rcx+10h]
0x1400357ee  mov     edx, 16h
0x1400357f3  mov     qword ptr [rsp+68h+Period], rsi
0x1400357f8  mov     r9, r15
0x1400357fb  mov     qword ptr [rsp+68h+DueTime], rax
0x140035800  call    WPP_SF_qqq
0x140035805  lea     rdx, [rsp+68h+Parameter]
0x14003580a  call    AllocateMemory
0x14003580f  mov     ebx, eax
0x140035811  test    eax, eax
0x140035813  jz      short loc_140035848
0x140035815  mov     rcx, cs:WPP_GLOBAL_Control
0x14003581c  cmp     rcx, r13
0x14003581f  jz      loc_140035932
0x140035825  test    byte ptr [rcx+1Ch], 4
0x140035829  jz      loc_140035932
0x14003582f  mov     edx, 17h
0x140035834  mov     r8, rdi
0x140035837  mov     rcx, [rcx+10h]
0x14003583b  mov     r9d, eax
0x14003583e  call    WPP_SF_d
0x140035843  jmp     loc_140035932
0x140035848  mov     rdi, [rsp+68h+Parameter]
0x14003584d  lea     r8, TimerTimeout; Callback
0x140035854  mov     [rsp+68h+Flags], 0; Flags
0x14003585c  mov     r9, rdi; Parameter
0x14003585f  mov     [rsp+68h+Period], 7FFFFFFFh; Period
0x140035867  mov     rdx, rsi; TimerQueue
0x14003586a  mov     [rsp+68h+DueTime], 7CFFF060h; DueTime
0x140035872  lea     rcx, [rdi+30h]; phNewTimer
0x140035876  call    cs:__imp_CreateTimerQueueTimer
0x14003587c  test    eax, eax
0x14003587e  jnz     short loc_1400358B4
0x140035880  call    cs:__imp_GetLastError
0x140035886  mov     ebx, eax
0x140035888  test    eax, eax
0x14003588a  jz      short loc_1400358B4
0x14003588c  mov     rcx, cs:WPP_GLOBAL_Control
0x140035893  cmp     rcx, r13
0x140035896  jz      loc_140035932
0x14003589c  test    byte ptr [rcx+1Ch], 4
0x1400358a0  jz      loc_140035932
0x1400358a6  mov     edx, 18h
0x1400358ab  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1400358b2  jmp     short loc_140035837
0x1400358b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400358bb  cmp     rcx, r13
0x1400358be  jz      short loc_1400358DE
0x1400358c0  test    byte ptr [rcx+1Ch], 2
0x1400358c4  jz      short loc_1400358DE
0x1400358c6  mov     rcx, [rcx+10h]
0x1400358ca  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1400358d1  mov     edx, 19h
0x1400358d6  mov     r9, rdi
0x1400358d9  call    WPP_SF_q
0x1400358de  mov     [rdi], rsi
0x1400358e1  lea     rax, ?s_TimerExpirationCallBack@CoreFSM@ESIMPM@@CAXPEAX0@Z; ESIMPM::CoreFSM::s_TimerExpirationCallBack(void *,void *)
0x1400358e8  mov     [rdi+10h], rbp
0x1400358ec  mov     [rdi+18h], r15
0x1400358f0  mov     [rdi+20h], rax
0x1400358f4  mov     dword ptr [rdi+8], 1
0x1400358fb  mov     qword ptr [rdi+28h], 0
0x140035903  mov     dword ptr [rdi+38h], 7CFFF060h
0x14003590a  mov     [r14], rdi
0x14003590d  test    ebx, ebx
0x14003590f  jz      short loc_140035949
0x140035911  jmp     short loc_140035932
0x140035913  mov     ebx, 57h ; 'W'
0x140035918  cmp     rcx, r13
0x14003591b  jz      short loc_140035932
0x14003591d  test    byte ptr [rcx+1Ch], 4
0x140035921  jz      short loc_140035932
0x140035923  mov     rcx, [rcx+10h]
0x140035927  lea     edx, [rbx-42h]
0x14003592a  mov     r8, rdi
0x14003592d  call    WPP_SF_
0x140035932  mov     r8d, 0A1h
0x140035938  lea     rdx, aCreatetimer; "CreateTimer"
0x14003593f  lea     rcx, [rsp+68h+Parameter]
0x140035944  call    FreeMemory
0x140035949  mov     rcx, cs:WPP_GLOBAL_Control
0x140035950  cmp     rcx, r13
0x140035953  jz      short loc_140035973
0x140035955  test    byte ptr [rcx+1Ch], 8
0x140035959  jz      short loc_140035973
0x14003595b  mov     rcx, [rcx+10h]
0x14003595f  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x140035966  mov     edx, 1Ah
0x14003596b  mov     r9d, ebx
0x14003596e  call    WPP_SF_d
0x140035973  lea     r11, [rsp+68h+var_28]
0x140035978  mov     eax, ebx
0x14003597a  mov     rbx, [r11+30h]
0x14003597e  mov     rbp, [r11+40h]
0x140035982  mov     rsp, r11
0x140035985  pop     r15
0x140035987  pop     r14
0x140035989  pop     r13
0x14003598b  pop     rdi
0x14003598c  pop     rsi
0x14003598d  retn
```
