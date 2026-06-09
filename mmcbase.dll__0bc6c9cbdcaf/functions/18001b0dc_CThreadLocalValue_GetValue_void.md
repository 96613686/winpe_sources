# CThreadLocalValue::GetValue(void * *)

- ea: `0x18001b0dc`
- end: `0x18001b1c9`
- name: `?GetValue@CThreadLocalValue@@QEBAJPEAPEAX@Z`
- size: `237`
- prototype: `__int64 __fastcall(CThreadLocalValue *__hidden this, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017f70`

## callees

- `0x180008630`
- `0x18000bd34`
- `0x18001b0dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b16a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b16a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b15c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b15c`

## pseudocode

```c
__int64 __fastcall CThreadLocalValue::GetValue(CThreadLocalValue *this, void **a2)
{
  unsigned int v3; // ebx
  void *Value; // rdi
  __int64 v5; // rcx
  __int64 v6; // rdx
  signed int LastError; // eax

  if ( a2 )
  {
    if ( g_tlvModalLoopCount == -1 )
    {
      v3 = dword_18002E66C;
      Value = 0;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        goto LABEL_18;
      v6 = 13;
    }
    else
    {
      v3 = 0;
      Value = TlsGetValue(g_tlvModalLoopCount);
      if ( Value )
        goto LABEL_18;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        goto LABEL_18;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        goto LABEL_18;
      v6 = 14;
    }
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids, v3);
LABEL_18:
    *a2 = Value;
    return v3;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids);
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x18001b0dc  mov     [rsp+arg_0], rbx
0x18001b0e1  mov     [rsp+arg_8], rsi
0x18001b0e6  push    rdi
0x18001b0e7  sub     rsp, 20h
0x18001b0eb  mov     rsi, rdx
0x18001b0ee  test    rdx, rdx
0x18001b0f1  jnz     short loc_18001B129
0x18001b0f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0fa  lea     rax, WPP_GLOBAL_Control
0x18001b101  cmp     rcx, rax
0x18001b104  jz      short loc_18001B11F
0x18001b106  cmp     byte ptr [rcx+19h], 2
0x18001b10a  jb      short loc_18001B11F
0x18001b10c  mov     rcx, [rcx+10h]
0x18001b110  lea     edx, [rsi+0Ch]
0x18001b113  lea     r8, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids
0x18001b11a  call    WPP_SF_
0x18001b11f  mov     ebx, 80004003h
0x18001b124  jmp     loc_18001B1B7
0x18001b129  mov     ecx, cs:?g_tlvModalLoopCount@@3V?$TThreadLocalValue@H@@A; dwTlsIndex
0x18001b12f  cmp     ecx, 0FFFFFFFFh
0x18001b132  jnz     short loc_18001B15A
0x18001b134  mov     ebx, cs:dword_18002E66C
0x18001b13a  xor     edi, edi
0x18001b13c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b143  lea     rax, WPP_GLOBAL_Control
0x18001b14a  cmp     rcx, rax
0x18001b14d  jz      short loc_18001B1B4
0x18001b14f  cmp     byte ptr [rcx+19h], 2
0x18001b153  jb      short loc_18001B1B4
0x18001b155  lea     edx, [rdi+0Dh]
0x18001b158  jmp     short loc_18001B1A1
0x18001b15a  xor     ebx, ebx
0x18001b15c  call    cs:__imp_TlsGetValue
0x18001b162  mov     rdi, rax
0x18001b165  test    rax, rax
0x18001b168  jnz     short loc_18001B1B4
0x18001b16a  call    cs:__imp_GetLastError
0x18001b170  mov     ebx, eax
0x18001b172  test    eax, eax
0x18001b174  jle     short loc_18001B17F
0x18001b176  movzx   ebx, ax
0x18001b179  or      ebx, 80070000h
0x18001b17f  test    ebx, ebx
0x18001b181  jns     short loc_18001B1B4
0x18001b183  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b18a  lea     rax, WPP_GLOBAL_Control
0x18001b191  cmp     rcx, rax
0x18001b194  jz      short loc_18001B1B4
0x18001b196  cmp     byte ptr [rcx+19h], 2
0x18001b19a  jb      short loc_18001B1B4
0x18001b19c  mov     edx, 0Eh
0x18001b1a1  mov     rcx, [rcx+10h]
0x18001b1a5  lea     r8, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids
0x18001b1ac  mov     r9d, ebx
0x18001b1af  call    WPP_SF_d
0x18001b1b4  mov     [rsi], rdi
0x18001b1b7  mov     rsi, [rsp+28h+arg_8]
0x18001b1bc  mov     eax, ebx
0x18001b1be  mov     rbx, [rsp+28h+arg_0]
0x18001b1c3  add     rsp, 20h
0x18001b1c7  pop     rdi
0x18001b1c8  retn
```
