# BthServListenForAsyncEvents(int)

- ea: `0x18000cf18`
- end: `0x18000d210`
- name: `?BthServListenForAsyncEvents@@YAHH@Z`
- size: `760`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000db08`

## callees

- `0x18000cf18`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d0fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d0fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cff3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d064`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cff3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000d064`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d0dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d0dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d199`

## pseudocode

```c
__int64 __fastcall BthServListenForAsyncEvents(int a1)
{
  _BYTE *v2; // rax
  char v3; // bl
  bool v4; // dl
  bool v5; // dl
  HANDLE EventW; // rsi
  bool v7; // dl
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  bool v10; // dl
  bool v11; // r8
  bool v12; // dl

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  v5 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)v2 + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5));
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v8 = 1;
    goto LABEL_51;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( hEvent )
    {
      hObject = CreateThread(0, 0, BthServAsyncThread, EventW, 0, (LPDWORD)&hObject + 2);
      if ( hObject )
      {
        WaitForSingleObject(EventW, 0xFFFFFFFF);
        v8 = 1;
        v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        goto LABEL_49;
      }
      v9 = WPP_GLOBAL_Control;
      v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v10 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_48:
        v8 = 0;
LABEL_49:
        CloseHandle(EventW);
        v2 = WPP_GLOBAL_Control;
        goto LABEL_51;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v10 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_48;
    }
    WPP_RECORDER_AND_TRACE_SF_s(v9[2], v10, v11, v9[5]);
    goto LABEL_48;
  }
  v2 = WPP_GLOBAL_Control;
  v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  v8 = 0;
LABEL_51:
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || v2[25] < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5));
  return v8;
}

```

## disassembly

```asm
0x18000cf18  mov     [rsp+arg_0], rbx
0x18000cf1d  mov     [rsp+arg_8], rbp
0x18000cf22  mov     [rsp+arg_10], rsi
0x18000cf27  push    rdi
0x18000cf28  push    r14
0x18000cf2a  push    r15
0x18000cf2c  sub     rsp, 50h
0x18000cf30  mov     edi, ecx
0x18000cf32  mov     rax, cs:WPP_GLOBAL_Control
0x18000cf39  lea     rbp, WPP_GLOBAL_Control
0x18000cf40  mov     ebx, 1
0x18000cf45  cmp     rax, rbp
0x18000cf48  jz      short loc_18000CF54
0x18000cf4a  cmp     byte ptr [rax+19h], 5
0x18000cf4e  jb      short loc_18000CF54
0x18000cf50  mov     dl, bl
0x18000cf52  jmp     short loc_18000CF56
0x18000cf54  xor     dl, dl
0x18000cf56  lea     r14, WPP_RECORDER_INITIALIZED
0x18000cf5d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000cf64  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000cf6b  setnz   r8b
0x18000cf6f  test    dl, dl
0x18000cf71  jnz     short loc_18000CF78
0x18000cf73  test    r8b, r8b
0x18000cf76  jz      short loc_18000CF98
0x18000cf78  mov     r9, [rax+28h]
0x18000cf7c  mov     rcx, [rax+10h]
0x18000cf80  mov     [rsp+68h+var_30], r15
0x18000cf85  mov     [rsp+68h+var_38], 6Ah ; 'j'
0x18000cf8c  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000cf91  mov     rax, cs:WPP_GLOBAL_Control
0x18000cf98  cmp     rax, rbp
0x18000cf9b  jz      short loc_18000CFA7
0x18000cf9d  cmp     byte ptr [rax+19h], 4
0x18000cfa1  jb      short loc_18000CFA7
0x18000cfa3  mov     dl, bl
0x18000cfa5  jmp     short loc_18000CFA9
0x18000cfa7  xor     dl, dl
0x18000cfa9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000cfb0  setnz   r8b
0x18000cfb4  test    dl, dl
0x18000cfb6  jnz     short loc_18000CFBD
0x18000cfb8  test    r8b, r8b
0x18000cfbb  jz      short loc_18000CFE1
0x18000cfbd  mov     r9, [rax+28h]
0x18000cfc1  mov     rcx, [rax+10h]
0x18000cfc5  mov     dword ptr [rsp+68h+var_20], edi
0x18000cfc9  mov     [rsp+68h+var_30], r15
0x18000cfce  mov     [rsp+68h+var_38], 6Bh ; 'k'
0x18000cfd5  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000cfda  mov     rax, cs:WPP_GLOBAL_Control
0x18000cfe1  test    edi, edi
0x18000cfe3  jz      loc_18000D1AE
0x18000cfe9  xor     r9d, r9d; lpName
0x18000cfec  xor     r8d, r8d; bInitialState
0x18000cfef  xor     edx, edx; bManualReset
0x18000cff1  xor     ecx, ecx; lpEventAttributes
0x18000cff3  call    cs:__imp_CreateEventW
0x18000cffa  nop     dword ptr [rax+rax+00h]
0x18000cfff  mov     rsi, rax
0x18000d002  test    rax, rax
0x18000d005  jnz     short loc_18000D05A
0x18000d007  mov     rax, cs:WPP_GLOBAL_Control
0x18000d00e  cmp     rax, rbp
0x18000d011  jz      short loc_18000D01D
0x18000d013  cmp     byte ptr [rax+19h], 3
0x18000d017  jb      short loc_18000D01D
0x18000d019  mov     dl, bl
0x18000d01b  jmp     short loc_18000D01F
0x18000d01d  xor     dl, dl
0x18000d01f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d026  setnz   r8b
0x18000d02a  test    dl, dl
0x18000d02c  jnz     short loc_18000D033
0x18000d02e  test    r8b, r8b
0x18000d031  jz      short loc_18000D053
0x18000d033  mov     r9, [rax+28h]
0x18000d037  mov     rcx, [rax+10h]
0x18000d03b  mov     [rsp+68h+var_30], r15
0x18000d040  mov     [rsp+68h+var_38], 6Ch ; 'l'
0x18000d047  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d04c  mov     rax, cs:WPP_GLOBAL_Control
0x18000d053  xor     edi, edi
0x18000d055  jmp     loc_18000D1B0
0x18000d05a  xor     r9d, r9d; lpName
0x18000d05d  xor     r8d, r8d; bInitialState
0x18000d060  mov     edx, ebx; bManualReset
0x18000d062  xor     ecx, ecx; lpEventAttributes
0x18000d064  call    cs:__imp_CreateEventW
0x18000d06b  nop     dword ptr [rax+rax+00h]
0x18000d070  mov     cs:hEvent, rax
0x18000d077  test    rax, rax
0x18000d07a  jnz     short loc_18000D0BD
0x18000d07c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d083  cmp     rcx, rbp
0x18000d086  jz      short loc_18000D092
0x18000d088  cmp     byte ptr [rcx+19h], 3
0x18000d08c  jb      short loc_18000D092
0x18000d08e  mov     dl, bl
0x18000d090  jmp     short loc_18000D094
0x18000d092  xor     dl, dl
0x18000d094  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d09b  setnz   r8b
0x18000d09f  test    dl, dl
0x18000d0a1  jnz     short loc_18000D0AC
0x18000d0a3  test    r8b, r8b
0x18000d0a6  jz      loc_18000D194
0x18000d0ac  mov     [rsp+68h+var_30], r15
0x18000d0b1  mov     [rsp+68h+var_38], 6Dh ; 'm'
0x18000d0b8  jmp     loc_18000D187
0x18000d0bd  lea     rax, hObject+8
0x18000d0c4  mov     r9, rsi; lpParameter
0x18000d0c7  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18000d0cc  lea     r8, ?BthServAsyncThread@@YAKPEAX@Z; lpStartAddress
0x18000d0d3  and     [rsp+68h+var_48], 0
0x18000d0d8  xor     edx, edx; dwStackSize
0x18000d0da  xor     ecx, ecx; lpThreadAttributes
0x18000d0dc  call    cs:__imp_CreateThread
0x18000d0e3  nop     dword ptr [rax+rax+00h]
0x18000d0e8  mov     qword ptr cs:hObject, rax
0x18000d0ef  test    rax, rax
0x18000d0f2  jz      short loc_18000D14F
0x18000d0f4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d0f7  mov     rcx, rsi; hHandle
0x18000d0fa  call    cs:__imp_WaitForSingleObject
0x18000d101  nop     dword ptr [rax+rax+00h]
0x18000d106  mov     edi, ebx
0x18000d108  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d10f  cmp     rcx, rbp
0x18000d112  jz      short loc_18000D11E
0x18000d114  cmp     byte ptr [rcx+19h], 3
0x18000d118  jb      short loc_18000D11E
0x18000d11a  mov     dl, bl
0x18000d11c  jmp     short loc_18000D120
0x18000d11e  xor     dl, dl
0x18000d120  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d127  setnz   r8b
0x18000d12b  test    dl, dl
0x18000d12d  jnz     short loc_18000D134
0x18000d12f  test    r8b, r8b
0x18000d132  jz      short loc_18000D196
0x18000d134  mov     r9, [rcx+28h]
0x18000d138  mov     rcx, [rcx+10h]
0x18000d13c  mov     [rsp+68h+var_30], r15
0x18000d141  mov     [rsp+68h+var_38], 6Eh ; 'n'
0x18000d148  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d14d  jmp     short loc_18000D196
0x18000d14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d156  cmp     rcx, rbp
0x18000d159  jz      short loc_18000D165
0x18000d15b  cmp     byte ptr [rcx+19h], 3
0x18000d15f  jb      short loc_18000D165
0x18000d161  mov     dl, bl
0x18000d163  jmp     short loc_18000D167
0x18000d165  xor     dl, dl
0x18000d167  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d16e  setnz   r8b
0x18000d172  test    dl, dl
0x18000d174  jnz     short loc_18000D17B
0x18000d176  test    r8b, r8b
0x18000d179  jz      short loc_18000D194
0x18000d17b  mov     [rsp+68h+var_30], r15
0x18000d180  mov     [rsp+68h+var_38], 6Fh ; 'o'
0x18000d187  mov     r9, [rcx+28h]
0x18000d18b  mov     rcx, [rcx+10h]
0x18000d18f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000d194  xor     edi, edi
0x18000d196  mov     rcx, rsi; hObject
0x18000d199  call    cs:__imp_CloseHandle
0x18000d1a0  nop     dword ptr [rax+rax+00h]
0x18000d1a5  mov     rax, cs:WPP_GLOBAL_Control
0x18000d1ac  jmp     short loc_18000D1B0
0x18000d1ae  mov     edi, ebx
0x18000d1b0  cmp     rax, rbp
0x18000d1b3  jz      short loc_18000D1BB
0x18000d1b5  cmp     byte ptr [rax+19h], 5
0x18000d1b9  jnb     short loc_18000D1BD
0x18000d1bb  xor     bl, bl
0x18000d1bd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000d1c4  setnz   r8b
0x18000d1c8  test    bl, bl
0x18000d1ca  jnz     short loc_18000D1D1
0x18000d1cc  test    r8b, r8b
0x18000d1cf  jz      short loc_18000D1F3
0x18000d1d1  mov     r9, [rax+28h]
0x18000d1d5  mov     dl, bl
0x18000d1d7  mov     ecx, edi
0x18000d1d9  mov     [rsp+68h+var_20], rcx
0x18000d1de  mov     rcx, [rax+10h]
0x18000d1e2  mov     [rsp+68h+var_30], r15
0x18000d1e7  mov     [rsp+68h+var_38], 70h ; 'p'
0x18000d1ee  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000d1f3  lea     r11, [rsp+68h+var_18]
0x18000d1f8  mov     eax, edi
0x18000d1fa  mov     rbx, [r11+20h]
0x18000d1fe  mov     rbp, [r11+28h]
0x18000d202  mov     rsi, [r11+30h]
0x18000d206  mov     rsp, r11
0x18000d209  pop     r15
0x18000d20b  pop     r14
0x18000d20d  pop     rdi
0x18000d20e  retn
```
