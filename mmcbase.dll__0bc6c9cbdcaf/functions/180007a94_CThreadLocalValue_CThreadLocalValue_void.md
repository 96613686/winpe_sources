# CThreadLocalValue::CThreadLocalValue(void)

- ea: `0x180007a94`
- end: `0x180007b12`
- name: `??0CThreadLocalValue@@QEAA@XZ`
- size: `126`
- prototype: `CThreadLocalValue *__fastcall(CThreadLocalValue *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180007a94`
- `0x180008630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007abd`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180007aac`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180007aac`

## pseudocode

```c
CThreadLocalValue *__fastcall CThreadLocalValue::CThreadLocalValue(CThreadLocalValue *this)
{
  signed int LastError; // eax

  g_tlvModalLoopCount = -1;
  dword_18002E66C = 0;
  g_tlvModalLoopCount = TlsAlloc();
  if ( g_tlvModalLoopCount == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    dword_18002E66C = LastError;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids,
        (unsigned int)LastError);
  }
  return (CThreadLocalValue *)&g_tlvModalLoopCount;
}

```

## disassembly

```asm
0x180007a94  sub     rsp, 28h
0x180007a98  mov     cs:?g_tlvModalLoopCount@@3V?$TThreadLocalValue@H@@A, 0FFFFFFFFh; TThreadLocalValue<int> g_tlvModalLoopCount
0x180007aa2  mov     cs:dword_18002E66C, 0
0x180007aac  call    cs:__imp_TlsAlloc
0x180007ab2  mov     cs:?g_tlvModalLoopCount@@3V?$TThreadLocalValue@H@@A, eax; TThreadLocalValue<int> g_tlvModalLoopCount
0x180007ab8  cmp     eax, 0FFFFFFFFh
0x180007abb  jnz     short loc_180007B06
0x180007abd  call    cs:__imp_GetLastError
0x180007ac3  test    eax, eax
0x180007ac5  jle     short loc_180007ACF
0x180007ac7  movzx   eax, ax
0x180007aca  or      eax, 80070000h
0x180007acf  mov     cs:dword_18002E66C, eax
0x180007ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180007adc  lea     rdx, WPP_GLOBAL_Control
0x180007ae3  cmp     rcx, rdx
0x180007ae6  jz      short loc_180007B06
0x180007ae8  cmp     byte ptr [rcx+19h], 1
0x180007aec  jb      short loc_180007B06
0x180007aee  mov     rcx, [rcx+10h]
0x180007af2  lea     r8, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids
0x180007af9  mov     edx, 0Ah
0x180007afe  mov     r9d, eax
0x180007b01  call    WPP_SF_d
0x180007b06  lea     rax, ?g_tlvModalLoopCount@@3V?$TThreadLocalValue@H@@A; TThreadLocalValue<int> g_tlvModalLoopCount
0x180007b0d  add     rsp, 28h
0x180007b11  retn
```
