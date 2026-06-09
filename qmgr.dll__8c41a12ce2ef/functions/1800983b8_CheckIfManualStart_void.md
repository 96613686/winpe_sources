# CheckIfManualStart(void)

- ea: `0x1800983b8`
- end: `0x18009854d`
- name: `?CheckIfManualStart@@YAXXZ`
- size: `405`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008fbfc`

## callees

- `0x1800983b8`
- `0x18009d024`
- `0x18009e9c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800983fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098492`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009845b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009845b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800983d5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800983d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180098537`

## string_xrefs

- `0x1800983c7`: `Global\SC_AutoStartComplete`

## pseudocode

```c
void CheckIfManualStart(void)
{
  HANDLE v0; // rax
  void *v1; // rsi
  EVENT_LOG *v2; // rcx
  DWORD v3; // eax
  DWORD v4; // eax
  int v5; // edi
  EVENT_LOG *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rdx

  v0 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
  v1 = v0;
  if ( v0 )
  {
    v4 = WaitForSingleObject(v0, 0);
    v5 = 1;
    if ( v4 )
    {
      if ( v4 == 258 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_533829f6437c324cb0547291f5f8d64b_Traceguids);
        v5 = 0;
        goto LABEL_25;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, LastError);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 4) == 0 )
      {
LABEL_25:
        g_IsManualStart = v5;
        CloseHandle(v1);
        return;
      }
      v8 = 29;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v8 = 26;
    }
    WPP_SF_(*((_QWORD *)v6 + 2), v8, &WPP_533829f6437c324cb0547291f5f8d64b_Traceguids);
    goto LABEL_25;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v3 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, v3);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v2 + 2), 25, &WPP_533829f6437c324cb0547291f5f8d64b_Traceguids);
  }
  g_IsManualStart = 1;
}

```

## disassembly

```asm
0x1800983b8  mov     [rsp+arg_0], rbx
0x1800983bd  mov     [rsp+arg_8], rsi
0x1800983c2  push    rdi
0x1800983c3  sub     rsp, 20h
0x1800983c7  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x1800983ce  xor     edx, edx; bInheritHandle
0x1800983d0  mov     ecx, 100000h; dwDesiredAccess
0x1800983d5  call    cs:__imp_OpenEventW
0x1800983db  mov     rsi, rax
0x1800983de  test    rax, rax
0x1800983e1  jnz     short loc_180098456
0x1800983e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800983ea  lea     rbx, WPP_GLOBAL_Control
0x1800983f1  cmp     rcx, rbx
0x1800983f4  jz      short loc_180098446
0x1800983f6  test    byte ptr [rcx+1Ch], 4
0x1800983fa  jz      short loc_180098426
0x1800983fc  call    cs:__imp_GetLastError
0x180098402  mov     rcx, cs:WPP_GLOBAL_Control
0x180098409  lea     edx, [rsi+18h]
0x18009840c  mov     r9d, eax
0x18009840f  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x180098416  mov     rcx, [rcx+10h]
0x18009841a  call    WPP_SF_d
0x18009841f  mov     rcx, cs:WPP_GLOBAL_Control
0x180098426  cmp     rcx, rbx
0x180098429  jz      short loc_180098446
0x18009842b  test    byte ptr [rcx+1Ch], 4
0x18009842f  jz      short loc_180098446
0x180098431  mov     rcx, [rcx+10h]
0x180098435  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x18009843c  mov     edx, 19h
0x180098441  call    WPP_SF_
0x180098446  mov     edi, 1
0x18009844b  mov     cs:?g_IsManualStart@@3HA, edi; int g_IsManualStart
0x180098451  jmp     loc_18009853D
0x180098456  xor     edx, edx; dwMilliseconds
0x180098458  mov     rcx, rsi; hHandle
0x18009845b  call    cs:__imp_WaitForSingleObject
0x180098461  mov     edi, 1
0x180098466  test    eax, eax
0x180098468  jz      loc_180098500
0x18009846e  cmp     eax, 102h
0x180098473  jz      short loc_1800984CE
0x180098475  mov     rcx, cs:WPP_GLOBAL_Control
0x18009847c  lea     rbx, WPP_GLOBAL_Control
0x180098483  cmp     rcx, rbx
0x180098486  jz      loc_18009852E
0x18009848c  test    byte ptr [rcx+1Ch], 4
0x180098490  jz      short loc_1800984BC
0x180098492  call    cs:__imp_GetLastError
0x180098498  mov     rcx, cs:WPP_GLOBAL_Control
0x18009849f  lea     edx, [rdi+1Bh]
0x1800984a2  mov     r9d, eax
0x1800984a5  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x1800984ac  mov     rcx, [rcx+10h]
0x1800984b0  call    WPP_SF_d
0x1800984b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800984bc  cmp     rcx, rbx
0x1800984bf  jz      short loc_18009852E
0x1800984c1  test    byte ptr [rcx+1Ch], 4
0x1800984c5  jz      short loc_18009852E
0x1800984c7  mov     edx, 1Dh
0x1800984cc  jmp     short loc_18009851E
0x1800984ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800984d5  lea     rbx, WPP_GLOBAL_Control
0x1800984dc  cmp     rcx, rbx
0x1800984df  jz      short loc_1800984FC
0x1800984e1  test    [rcx+1Ch], dil
0x1800984e5  jz      short loc_1800984FC
0x1800984e7  mov     rcx, [rcx+10h]
0x1800984eb  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x1800984f2  mov     edx, 1Bh
0x1800984f7  call    WPP_SF_
0x1800984fc  xor     edi, edi
0x1800984fe  jmp     short loc_18009852E
0x180098500  mov     rcx, cs:WPP_GLOBAL_Control
0x180098507  lea     rbx, WPP_GLOBAL_Control
0x18009850e  cmp     rcx, rbx
0x180098511  jz      short loc_18009852E
0x180098513  test    [rcx+1Ch], dil
0x180098517  jz      short loc_18009852E
0x180098519  mov     edx, 1Ah
0x18009851e  mov     rcx, [rcx+10h]
0x180098522  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x180098529  call    WPP_SF_
0x18009852e  mov     rcx, rsi; hObject
0x180098531  mov     cs:?g_IsManualStart@@3HA, edi; int g_IsManualStart
0x180098537  call    cs:__imp_CloseHandle
0x18009853d  mov     rbx, [rsp+28h+arg_0]
0x180098542  mov     rsi, [rsp+28h+arg_8]
0x180098547  add     rsp, 20h
0x18009854b  pop     rdi
0x18009854c  retn
```
