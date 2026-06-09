# CThreadLocalValue::SetValue(void *)

- ea: `0x18001b1d0`
- end: `0x18001b261`
- name: `?SetValue@CThreadLocalValue@@QEAAJPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(CThreadLocalValue *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017fb0`
- `0x180018170`

## callees

- `0x180008630`
- `0x18001b1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b213`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b209`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001b209`

## pseudocode

```c
__int64 __fastcall CThreadLocalValue::SetValue(CThreadLocalValue *this, void *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // rdx
  signed int LastError; // eax

  if ( g_tlvModalLoopCount == -1 )
  {
    v2 = dword_18002E66C;
    v3 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v4 = 15;
LABEL_11:
      WPP_SF_d(*(_QWORD *)(v3 + 16), v4, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids, v2);
    }
  }
  else
  {
    v2 = 0;
    if ( !TlsSetValue(g_tlvModalLoopCount, a2) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v4 = 16;
        goto LABEL_11;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001b1d0  push    rbx
0x18001b1d2  sub     rsp, 20h
0x18001b1d6  mov     ecx, cs:?g_tlvModalLoopCount@@3V?$TThreadLocalValue@H@@A; dwTlsIndex
0x18001b1dc  cmp     ecx, 0FFFFFFFFh
0x18001b1df  jnz     short loc_18001B207
0x18001b1e1  mov     ebx, cs:dword_18002E66C
0x18001b1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1ee  lea     rax, WPP_GLOBAL_Control
0x18001b1f5  cmp     rcx, rax
0x18001b1f8  jz      short loc_18001B259
0x18001b1fa  cmp     byte ptr [rcx+19h], 2
0x18001b1fe  jb      short loc_18001B259
0x18001b200  mov     edx, 0Fh; lpTlsValue
0x18001b205  jmp     short loc_18001B246
0x18001b207  xor     ebx, ebx
0x18001b209  call    cs:__imp_TlsSetValue
0x18001b20f  test    eax, eax
0x18001b211  jnz     short loc_18001B259
0x18001b213  call    cs:__imp_GetLastError
0x18001b219  mov     ebx, eax
0x18001b21b  test    eax, eax
0x18001b21d  jle     short loc_18001B228
0x18001b21f  movzx   ebx, ax
0x18001b222  or      ebx, 80070000h
0x18001b228  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b22f  lea     rax, WPP_GLOBAL_Control
0x18001b236  cmp     rcx, rax
0x18001b239  jz      short loc_18001B259
0x18001b23b  cmp     byte ptr [rcx+19h], 2
0x18001b23f  jb      short loc_18001B259
0x18001b241  mov     edx, 10h
0x18001b246  mov     rcx, [rcx+10h]
0x18001b24a  lea     r8, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids
0x18001b251  mov     r9d, ebx
0x18001b254  call    WPP_SF_d
0x18001b259  mov     eax, ebx
0x18001b25b  add     rsp, 20h
0x18001b25f  pop     rbx
0x18001b260  retn
```
