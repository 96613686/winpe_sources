# ESIMPM::WwanTimerDeleteTimer(void *)

- ea: `0x14002327c`
- end: `0x1400233fe`
- name: `?WwanTimerDeleteTimer@ESIMPM@@YAXPEAX@Z`
- size: `386`
- prototype: `void __fastcall(ESIMPM *__hidden this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140023ba0`

## callees

- `0x14002327c`
- `0x1400355d8`
- `0x1400356cc`
- `0x14003570c`
- `0x140035c54`
- `0x1400360bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002333c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002333c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x140023332`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x140023332`

## string_xrefs

- `0x1400233be`: `DeleteTimer`

## pseudocode

```c
void __fastcall ESIMPM::WwanTimerDeleteTimer(ESIMPM *this, void *a2)
{
  _QWORD *v3; // rcx
  unsigned int v4; // edi
  int v5; // eax
  void *v6; // rdx
  void *v7; // rcx
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  ESIMPM *v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = this;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( this )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
    {
      WPP_SF_q(v3[2], 29, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, this);
      v3 = WPP_GLOBAL_Control;
    }
    v5 = *((_DWORD *)this + 2);
    if ( (v5 & 1) != 0 )
    {
      v6 = (void *)*((_QWORD *)this + 6);
      v7 = *(void **)this;
      *((_DWORD *)this + 2) = v5 & 0xFFFFFFFD;
      if ( DeleteTimerQueueTimer(v7, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        v4 = 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, LastError, this);
      }
      *((_DWORD *)this + 2) &= ~1u;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, this);
    }
    else
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 4) != 0 )
        WPP_SF_q(v3[2], 32, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, this);
      v4 = 0;
    }
    FreeMemory(&v11, "DeleteTimer", 214);
    goto LABEL_25;
  }
  if ( v3 == &WPP_GLOBAL_Control )
    return;
  v4 = 87;
  if ( (*((_BYTE *)v3 + 28) & 4) != 0 )
  {
    WPP_SF_(v3[2], 28, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
LABEL_25:
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(v3[2], 33, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v4);
}

```

## disassembly

```asm
0x14002327c  push    rbx
0x14002327e  push    rbp
0x14002327f  push    rsi
0x140023280  push    rdi
0x140023281  sub     rsp, 38h
0x140023285  mov     rbx, rcx
0x140023288  mov     [rsp+58h+arg_0], rcx
0x14002328d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023294  lea     rsi, WPP_GLOBAL_Control
0x14002329b  lea     rbp, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x1400232a2  cmp     rcx, rsi
0x1400232a5  jz      short loc_1400232C5
0x1400232a7  test    byte ptr [rcx+1Ch], 8
0x1400232ab  jz      short loc_1400232C5
0x1400232ad  mov     rcx, [rcx+10h]
0x1400232b1  mov     edx, 1Bh
0x1400232b6  mov     r8, rbp
0x1400232b9  call    WPP_SF_
0x1400232be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232c5  test    rbx, rbx
0x1400232c8  jnz     short loc_1400232F4
0x1400232ca  cmp     rcx, rsi
0x1400232cd  jz      loc_1400233F5
0x1400232d3  test    byte ptr [rcx+1Ch], 4
0x1400232d7  lea     edi, [rbx+57h]
0x1400232da  jz      loc_1400233D6
0x1400232e0  mov     rcx, [rcx+10h]
0x1400232e4  lea     edx, [rbx+1Ch]
0x1400232e7  mov     r8, rbp
0x1400232ea  call    WPP_SF_
0x1400232ef  jmp     loc_1400233CF
0x1400232f4  cmp     rcx, rsi
0x1400232f7  jz      short loc_14002331A
0x1400232f9  test    byte ptr [rcx+1Ch], 2
0x1400232fd  jz      short loc_14002331A
0x1400232ff  mov     rcx, [rcx+10h]
0x140023303  mov     edx, 1Dh
0x140023308  mov     r9, rbx
0x14002330b  mov     r8, rbp
0x14002330e  call    WPP_SF_q
0x140023313  mov     rcx, cs:WPP_GLOBAL_Control
0x14002331a  mov     eax, [rbx+8]
0x14002331d  test    al, 1
0x14002331f  jz      short loc_140023397
0x140023321  mov     rdx, [rbx+30h]; Timer
0x140023325  and     eax, 0FFFFFFFDh
0x140023328  mov     rcx, [rbx]; TimerQueue
0x14002332b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x14002332f  mov     [rbx+8], eax
0x140023332  call    cs:__imp_DeleteTimerQueueTimer
0x140023338  test    eax, eax
0x14002333a  jnz     short loc_140023369
0x14002333c  call    cs:__imp_GetLastError
0x140023342  mov     edi, eax
0x140023344  mov     rcx, cs:WPP_GLOBAL_Control
0x14002334b  cmp     rcx, rsi
0x14002334e  jz      short loc_14002336B
0x140023350  test    byte ptr [rcx+1Ch], 4
0x140023354  jz      short loc_14002336B
0x140023356  mov     rcx, [rcx+10h]
0x14002335a  mov     r9d, eax
0x14002335d  mov     [rsp+58h+var_38], rbx
0x140023362  call    WPP_SF_dq
0x140023367  jmp     short loc_14002336B
0x140023369  xor     edi, edi
0x14002336b  and     dword ptr [rbx+8], 0FFFFFFFEh
0x14002336f  mov     rcx, cs:WPP_GLOBAL_Control
0x140023376  cmp     rcx, rsi
0x140023379  jz      short loc_1400233B8
0x14002337b  test    byte ptr [rcx+1Ch], 2
0x14002337f  jz      short loc_1400233B8
0x140023381  mov     rcx, [rcx+10h]
0x140023385  mov     edx, 1Fh
0x14002338a  mov     r9, rbx
0x14002338d  mov     r8, rbp
0x140023390  call    WPP_SF_q
0x140023395  jmp     short loc_1400233B8
0x140023397  cmp     rcx, rsi
0x14002339a  jz      short loc_1400233B6
0x14002339c  test    byte ptr [rcx+1Ch], 4
0x1400233a0  jz      short loc_1400233B6
0x1400233a2  mov     rcx, [rcx+10h]
0x1400233a6  mov     edx, 20h ; ' '
0x1400233ab  mov     r9, rbx
0x1400233ae  mov     r8, rbp
0x1400233b1  call    WPP_SF_q
0x1400233b6  xor     edi, edi
0x1400233b8  mov     r8d, 0D6h
0x1400233be  lea     rdx, aDeletetimer; "DeleteTimer"
0x1400233c5  lea     rcx, [rsp+58h+arg_0]
0x1400233ca  call    FreeMemory
0x1400233cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233d6  cmp     rcx, rsi
0x1400233d9  jz      short loc_1400233F5
0x1400233db  test    byte ptr [rcx+1Ch], 8
0x1400233df  jz      short loc_1400233F5
0x1400233e1  mov     rcx, [rcx+10h]
0x1400233e5  mov     edx, 21h ; '!'
0x1400233ea  mov     r9d, edi
0x1400233ed  mov     r8, rbp
0x1400233f0  call    WPP_SF_d
0x1400233f5  add     rsp, 38h
0x1400233f9  pop     rdi
0x1400233fa  pop     rsi
0x1400233fb  pop     rbp
0x1400233fc  pop     rbx
0x1400233fd  retn
```
