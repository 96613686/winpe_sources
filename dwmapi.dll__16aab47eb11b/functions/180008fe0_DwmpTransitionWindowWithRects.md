# DwmpTransitionWindowWithRects

- ea: `0x180008fe0`
- end: `0x180009092`
- name: `DwmpTransitionWindowWithRects`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008fb0`

## callees

- `0x180005b5c`
- `0x180008fe0`
- `0x18000c2ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009063`
- `USER32!SetWindowCompositionTransition` at `0x18000902f`
- `USER32!SetWindowCompositionTransition` at `0x18000902f`

## pseudocode

```c
__int64 __fastcall DwmpTransitionWindowWithRects(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v11; // ebx
  signed int LastError; // eax

  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0pd_EtwEventWriteTransfer(a1, ApipTransitionWindow_Start, a1, a2);
  if ( (unsigned int)SetWindowCompositionTransition(a1, a2, a3, a4, a5, a6, a7) )
  {
    v11 = 0;
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApipTransitionWindow_Stop);
  return v11;
}

```

## disassembly

```asm
0x180008fe0  push    rbx
0x180008fe2  push    rbp
0x180008fe3  push    rsi
0x180008fe4  push    rdi
0x180008fe5  sub     rsp, 48h
0x180008fe9  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180008ff0  mov     rsi, r9
0x180008ff3  mov     rbp, r8
0x180008ff6  mov     ebx, edx
0x180008ff8  mov     rdi, rcx
0x180008ffb  jnz     short loc_18000904F
0x180008ffd  mov     rax, [rsp+68h+arg_30]
0x180009005  mov     r9, rsi
0x180009008  mov     [rsp+68h+var_38], rax
0x18000900d  mov     r8, rbp
0x180009010  mov     rax, [rsp+68h+arg_28]
0x180009018  mov     edx, ebx
0x18000901a  mov     [rsp+68h+var_40], rax
0x18000901f  mov     rcx, rdi
0x180009022  mov     rax, [rsp+68h+arg_20]
0x18000902a  mov     [rsp+68h+var_48], rax
0x18000902f  call    cs:__imp_SetWindowCompositionTransition
0x180009035  test    eax, eax
0x180009037  jz      short loc_180009063
0x180009039  xor     ebx, ebx
0x18000903b  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180009042  jnz     short loc_18000907A
0x180009044  mov     eax, ebx
0x180009046  add     rsp, 48h
0x18000904a  pop     rdi
0x18000904b  pop     rsi
0x18000904c  pop     rbp
0x18000904d  pop     rbx
0x18000904e  retn
0x18000904f  mov     r9d, ebx
0x180009052  lea     rdx, ApipTransitionWindow_Start
0x180009059  mov     r8, rdi
0x18000905c  call    McTemplateU0pd_EtwEventWriteTransfer
0x180009061  jmp     short loc_180008FFD
0x180009063  call    cs:__imp_GetLastError
0x180009069  mov     ebx, eax
0x18000906b  test    eax, eax
0x18000906d  jle     short loc_18000903B
0x18000906f  movzx   ebx, ax
0x180009072  or      ebx, 80070000h
0x180009078  jmp     short loc_18000903B
0x18000907a  mov     r8d, ebx
0x18000907d  lea     rdx, ApipTransitionWindow_Stop
0x180009084  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000908b  call    McTemplateU0q_EtwEventWriteTransfer
0x180009090  jmp     short loc_180009044
```
