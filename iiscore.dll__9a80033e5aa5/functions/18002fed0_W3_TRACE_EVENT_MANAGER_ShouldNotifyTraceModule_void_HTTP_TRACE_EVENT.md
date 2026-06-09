# W3_TRACE_EVENT_MANAGER::ShouldNotifyTraceModule(void *,HTTP_TRACE_EVENT *)

- ea: `0x18002fed0`
- end: `0x18002ffab`
- name: `?ShouldNotifyTraceModule@W3_TRACE_EVENT_MANAGER@@QEAAHPEAXPEAUHTTP_TRACE_EVENT@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, void *, struct HTTP_TRACE_EVENT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002edf0`
- `0x18002ee10`

## callees

- `0x18002fed0`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ff98`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002ff98`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002feec`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002feec`

## pseudocode

```c
__int64 __fastcall W3_TRACE_EVENT_MANAGER::ShouldNotifyTraceModule(
        W3_TRACE_EVENT_MANAGER *this,
        void *a2,
        struct HTTP_TRACE_EVENT *a3)
{
  unsigned int v3; // edi
  __int64 *i; // r8
  DWORD dwArea; // eax
  LPCGUID pProviderGuid; // rdx
  __int64 v10; // rcx

  v3 = 0;
  if ( *((_BYTE *)this + 44) )
    CReaderWriterLock3::ReadLock(this);
  for ( i = (__int64 *)*((_QWORD *)this + 1); i != (__int64 *)((char *)this + 8); i = (__int64 *)*i )
  {
    if ( a2 == (void *)i[2] && a3->dwVerbosity <= *((_DWORD *)i + 9) )
    {
      dwArea = a3->dwArea;
      if ( !dwArea || (dwArea & (_DWORD)i[4]) != 0 )
      {
        pProviderGuid = a3->pProviderGuid;
        v10 = i[3];
        if ( (LPCGUID)v10 == a3->pProviderGuid
          || v10
          && (pProviderGuid
           && *(_DWORD *)v10 == pProviderGuid->Data1
           && *(_DWORD *)(v10 + 4) == *(_DWORD *)&pProviderGuid->Data2
           && *(_DWORD *)(v10 + 8) == *(_DWORD *)pProviderGuid->Data4
           && *(_DWORD *)(v10 + 12) == *(_DWORD *)&pProviderGuid->Data4[4]
           || (GUID *)v10 == &GUID_IIS_ALL_TRACE_PROVIDERS
           || !*(_DWORD *)v10
           && *(_DWORD *)(v10 + 4) == *(_DWORD *)&GUID_IIS_ALL_TRACE_PROVIDERS.Data2
           && *(_DWORD *)(v10 + 8) == *(_DWORD *)GUID_IIS_ALL_TRACE_PROVIDERS.Data4
           && *(_DWORD *)(v10 + 12) == *(_DWORD *)&GUID_IIS_ALL_TRACE_PROVIDERS.Data4[4]) )
        {
          v3 = 1;
          break;
        }
      }
    }
  }
  if ( *((_BYTE *)this + 44) )
    CReaderWriterLock3::ReadUnlock(this);
  return v3;
}

```

## disassembly

```asm
0x18002fed0  push    rbx
0x18002fed2  push    rbp
0x18002fed3  push    rsi
0x18002fed4  push    rdi
0x18002fed5  push    r14
0x18002fed7  sub     rsp, 20h
0x18002fedb  xor     edi, edi
0x18002fedd  mov     rsi, r8
0x18002fee0  mov     rbp, rdx
0x18002fee3  mov     rbx, rcx
0x18002fee6  cmp     [rcx+2Ch], dil
0x18002feea  jz      short loc_18002FEF2
0x18002feec  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18002fef2  mov     r10d, dword ptr cs:GUID_IIS_ALL_TRACE_PROVIDERS.Data4+4
0x18002fef9  lea     r9, [rbx+8]
0x18002fefd  mov     r8, [r9]
0x18002ff00  mov     r11d, dword ptr cs:GUID_IIS_ALL_TRACE_PROVIDERS.Data4
0x18002ff07  mov     r14d, dword ptr cs:GUID_IIS_ALL_TRACE_PROVIDERS.Data2
0x18002ff0e  cmp     r8, r9
0x18002ff11  jz      short loc_18002FF8F
0x18002ff13  cmp     rbp, [r8+10h]
0x18002ff17  jnz     short loc_18002FF85
0x18002ff19  mov     eax, [r8+24h]
0x18002ff1d  cmp     [rsi+2Ch], eax
0x18002ff20  ja      short loc_18002FF85
0x18002ff22  mov     eax, [rsi+8]
0x18002ff25  test    eax, eax
0x18002ff27  jz      short loc_18002FF2F
0x18002ff29  test    [r8+20h], eax
0x18002ff2d  jz      short loc_18002FF85
0x18002ff2f  mov     rdx, [rsi]
0x18002ff32  mov     rcx, [r8+18h]
0x18002ff36  cmp     rcx, rdx
0x18002ff39  jz      short loc_18002FF8A
0x18002ff3b  test    rcx, rcx
0x18002ff3e  jz      short loc_18002FF85
0x18002ff40  test    rdx, rdx
0x18002ff43  jz      short loc_18002FF63
0x18002ff45  mov     eax, [rdx]
0x18002ff47  cmp     [rcx], eax
0x18002ff49  jnz     short loc_18002FF63
0x18002ff4b  mov     eax, [rdx+4]
0x18002ff4e  cmp     [rcx+4], eax
0x18002ff51  jnz     short loc_18002FF63
0x18002ff53  mov     eax, [rdx+8]
0x18002ff56  cmp     [rcx+8], eax
0x18002ff59  jnz     short loc_18002FF63
0x18002ff5b  mov     eax, [rdx+0Ch]
0x18002ff5e  cmp     [rcx+0Ch], eax
0x18002ff61  jz      short loc_18002FF8A
0x18002ff63  lea     rax, GUID_IIS_ALL_TRACE_PROVIDERS
0x18002ff6a  cmp     rcx, rax
0x18002ff6d  jz      short loc_18002FF8A
0x18002ff6f  cmp     [rcx], edi
0x18002ff71  jnz     short loc_18002FF85
0x18002ff73  cmp     [rcx+4], r14d
0x18002ff77  jnz     short loc_18002FF85
0x18002ff79  cmp     [rcx+8], r11d
0x18002ff7d  jnz     short loc_18002FF85
0x18002ff7f  cmp     [rcx+0Ch], r10d
0x18002ff83  jz      short loc_18002FF8A
0x18002ff85  mov     r8, [r8]
0x18002ff88  jmp     short loc_18002FF0E
0x18002ff8a  mov     edi, 1
0x18002ff8f  cmp     byte ptr [rbx+2Ch], 0
0x18002ff93  jz      short loc_18002FF9E
0x18002ff95  mov     rcx, rbx
0x18002ff98  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002ff9e  mov     eax, edi
0x18002ffa0  add     rsp, 20h
0x18002ffa4  pop     r14
0x18002ffa6  pop     rdi
0x18002ffa7  pop     rsi
0x18002ffa8  pop     rbp
0x18002ffa9  pop     rbx
0x18002ffaa  retn
```
