# DdmConnectionTable::EnableOrDisableSleepTimer(int)

- ea: `0x18002df8c`
- end: `0x18002e0e4`
- name: `?EnableOrDisableSleepTimer@DdmConnectionTable@@AEAAXH@Z`
- size: `344`
- prototype: `void __fastcall(DdmConnectionTable *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002d844`
- `0x18002e2a8`

## callees

- `0x180007b7c`
- `0x18002df8c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x18002dfe2`
- `KERNEL32!SetThreadExecutionState` at `0x18002e046`
- `KERNEL32!SetThreadExecutionState` at `0x18002dfe2`
- `KERNEL32!SetThreadExecutionState` at `0x18002e046`

## string_xrefs

- `0x18002e005`: `EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d`
- `0x18002e061`: `EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d`

## pseudocode

```c
void __fastcall DdmConnectionTable::EnableOrDisableSleepTimer(DdmConnectionTable *this, unsigned int a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  _BYTE v6[16]; // [rsp+30h] [rbp-D0h] BYREF
  int *v7; // [rsp+40h] [rbp-C0h]
  int v8; // [rsp+48h] [rbp-B8h]
  int v9; // [rsp+4Ch] [rbp-B4h]
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( a2 )
  {
    if ( *((_QWORD *)this + 3) == 1 && !SetThreadExecutionState(0x80000001) && (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d", a2);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)&v11[2 * v5 - 4] );
LABEL_15:
        v9 = 0;
        v8 = 2 * v5 + 2;
        v7 = &v10;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v4, 2, v6);
      }
    }
  }
  else if ( !*((_QWORD *)this + 3) && !SetThreadExecutionState(0x80000000) && (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v10) = 0;
    FormatRRASErrorString(&v10, L"EnableOrDisableSleepTimer: SetThreadExecutionState failed. fDisable=%d", 0);
    if ( (byte_1800C8404 & 8) != 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&v11[2 * v5 - 4] );
      goto LABEL_15;
    }
  }
}

```

## disassembly

```asm
0x18002df8c  push    rbp
0x18002df8e  push    rbx
0x18002df8f  push    rsi
0x18002df90  push    rdi
0x18002df91  lea     rbp, [rsp-768h]
0x18002df99  sub     rsp, 868h
0x18002dfa0  mov     rax, cs:__security_cookie
0x18002dfa7  xor     rax, rsp
0x18002dfaa  mov     [rbp+780h+var_30], rax
0x18002dfb1  mov     edi, edx
0x18002dfb3  mov     rbx, rcx
0x18002dfb6  xor     esi, esi
0x18002dfb8  lea     rcx, [rsp+880h+var_82C]; void *
0x18002dfbd  xor     edx, edx; Val
0x18002dfbf  mov     [rsp+880h+var_830], esi
0x18002dfc3  mov     r8d, 7FCh; Size
0x18002dfc9  call    memset_0
0x18002dfce  test    edi, edi
0x18002dfd0  jz      short loc_18002E037
0x18002dfd2  cmp     qword ptr [rbx+18h], 1
0x18002dfd7  jnz     loc_18002E0C9
0x18002dfdd  mov     ecx, 80000001h; esFlags
0x18002dfe2  call    cs:__imp_SetThreadExecutionState
0x18002dfe8  test    eax, eax
0x18002dfea  jnz     loc_18002E0C9
0x18002dff0  test    cs:byte_1800C8404, 8
0x18002dff7  jz      loc_18002E0C9
0x18002dffd  mov     r8d, edi
0x18002e000  mov     word ptr [rsp+880h+var_830], si
0x18002e005  lea     rdx, aEnableordisabl; "EnableOrDisableSleepTimer: SetThreadExe"...
0x18002e00c  lea     rcx, [rsp+880h+var_830]
0x18002e011  call    FormatRRASErrorString
0x18002e016  test    cs:byte_1800C8404, 8
0x18002e01d  jz      loc_18002E0C9
0x18002e023  lea     rcx, [rsp+880h+var_830]
0x18002e028  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e02c  inc     rax
0x18002e02f  cmp     [rcx+rax*2], si
0x18002e033  jnz     short loc_18002E02C
0x18002e035  jmp     short loc_18002E08D
0x18002e037  cmp     [rbx+18h], rsi
0x18002e03b  jnz     loc_18002E0C9
0x18002e041  mov     ecx, 80000000h; esFlags
0x18002e046  call    cs:__imp_SetThreadExecutionState
0x18002e04c  test    eax, eax
0x18002e04e  jnz     short loc_18002E0C9
0x18002e050  test    cs:byte_1800C8404, 8
0x18002e057  jz      short loc_18002E0C9
0x18002e059  mov     r8d, edi
0x18002e05c  mov     word ptr [rsp+880h+var_830], si
0x18002e061  lea     rdx, aEnableordisabl; "EnableOrDisableSleepTimer: SetThreadExe"...
0x18002e068  lea     rcx, [rsp+880h+var_830]
0x18002e06d  call    FormatRRASErrorString
0x18002e072  test    cs:byte_1800C8404, 8
0x18002e079  jz      short loc_18002E0C9
0x18002e07b  lea     rcx, [rsp+880h+var_830]
0x18002e080  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e084  inc     rax
0x18002e087  cmp     [rcx+rax*2], si
0x18002e08b  jnz     short loc_18002E084
0x18002e08d  lea     eax, ds:2[rax*2]
0x18002e094  mov     [rsp+880h+var_834], esi
0x18002e098  lea     rcx, [rsp+880h+var_830]
0x18002e09d  mov     [rsp+880h+var_838], eax
0x18002e0a1  lea     rax, [rsp+880h+var_850]
0x18002e0a6  mov     [rsp+880h+var_840], rcx
0x18002e0ab  mov     r9d, 2
0x18002e0b1  mov     [rsp+880h+var_860], rax
0x18002e0b6  lea     rdx, RasDdmTraceError
0x18002e0bd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e0c4  call    McGenEventWrite_EventWriteTransfer
0x18002e0c9  mov     rcx, [rbp+780h+var_30]
0x18002e0d0  xor     rcx, rsp; StackCookie
0x18002e0d3  call    __security_check_cookie
0x18002e0d8  add     rsp, 868h
0x18002e0df  pop     rdi
0x18002e0e0  pop     rsi
0x18002e0e1  pop     rbx
0x18002e0e2  pop     rbp
0x18002e0e3  retn
```
