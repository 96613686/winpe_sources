# W3_TRACE_EVENT_MANAGER::ShouldNotifyTraceModule(void *,HTTP_TRACE_EVENT *)

- ea: `0x180032b34`
- end: `0x180032c1c`
- name: `?ShouldNotifyTraceModule@W3_TRACE_EVENT_MANAGER@@QEAAHPEAXPEAUHTTP_TRACE_EVENT@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, void *, struct HTTP_TRACE_EVENT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180031a40`
- `0x180031a60`

## callees

- `0x180032b34`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032c02`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180032c02`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180032b50`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180032b50`

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
0x180032b34  push    rbx
0x180032b36  push    rbp
0x180032b37  push    rsi
0x180032b38  push    rdi
0x180032b39  push    r14
0x180032b3b  sub     rsp, 20h
0x180032b3f  xor     edi, edi
0x180032b41  mov     rsi, r8
0x180032b44  mov     rbp, rdx
0x180032b47  mov     rbx, rcx
0x180032b4a  cmp     [rcx+2Ch], dil
0x180032b4e  jz      short loc_180032B5C
0x180032b50  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180032b57  nop     dword ptr [rax+rax+00h]
0x180032b5c  mov     r10d, dword ptr cs:GUID_IIS_ALL_TRACE_PROVIDERS.Data4+4
0x180032b63  lea     r9, [rbx+8]
0x180032b67  mov     r8, [r9]
0x180032b6a  mov     r11d, dword ptr cs:GUID_IIS_ALL_TRACE_PROVIDERS.Data4
0x180032b71  mov     r14d, dword ptr cs:GUID_IIS_ALL_TRACE_PROVIDERS.Data2
0x180032b78  cmp     r8, r9
0x180032b7b  jz      short loc_180032BF9
0x180032b7d  cmp     rbp, [r8+10h]
0x180032b81  jnz     short loc_180032BEF
0x180032b83  mov     eax, [r8+24h]
0x180032b87  cmp     [rsi+2Ch], eax
0x180032b8a  ja      short loc_180032BEF
0x180032b8c  mov     eax, [rsi+8]
0x180032b8f  test    eax, eax
0x180032b91  jz      short loc_180032B99
0x180032b93  test    [r8+20h], eax
0x180032b97  jz      short loc_180032BEF
0x180032b99  mov     rdx, [rsi]
0x180032b9c  mov     rcx, [r8+18h]
0x180032ba0  cmp     rcx, rdx
0x180032ba3  jz      short loc_180032BF4
0x180032ba5  test    rcx, rcx
0x180032ba8  jz      short loc_180032BEF
0x180032baa  test    rdx, rdx
0x180032bad  jz      short loc_180032BCD
0x180032baf  mov     eax, [rdx]
0x180032bb1  cmp     [rcx], eax
0x180032bb3  jnz     short loc_180032BCD
0x180032bb5  mov     eax, [rdx+4]
0x180032bb8  cmp     [rcx+4], eax
0x180032bbb  jnz     short loc_180032BCD
0x180032bbd  mov     eax, [rdx+8]
0x180032bc0  cmp     [rcx+8], eax
0x180032bc3  jnz     short loc_180032BCD
0x180032bc5  mov     eax, [rdx+0Ch]
0x180032bc8  cmp     [rcx+0Ch], eax
0x180032bcb  jz      short loc_180032BF4
0x180032bcd  lea     rax, GUID_IIS_ALL_TRACE_PROVIDERS
0x180032bd4  cmp     rcx, rax
0x180032bd7  jz      short loc_180032BF4
0x180032bd9  cmp     [rcx], edi
0x180032bdb  jnz     short loc_180032BEF
0x180032bdd  cmp     [rcx+4], r14d
0x180032be1  jnz     short loc_180032BEF
0x180032be3  cmp     [rcx+8], r11d
0x180032be7  jnz     short loc_180032BEF
0x180032be9  cmp     [rcx+0Ch], r10d
0x180032bed  jz      short loc_180032BF4
0x180032bef  mov     r8, [r8]
0x180032bf2  jmp     short loc_180032B78
0x180032bf4  mov     edi, 1
0x180032bf9  cmp     byte ptr [rbx+2Ch], 0
0x180032bfd  jz      short loc_180032C0E
0x180032bff  mov     rcx, rbx
0x180032c02  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180032c09  nop     dword ptr [rax+rax+00h]
0x180032c0e  mov     eax, edi
0x180032c10  add     rsp, 20h
0x180032c14  pop     r14
0x180032c16  pop     rdi
0x180032c17  pop     rsi
0x180032c18  pop     rbp
0x180032c19  pop     rbx
0x180032c1a  retn
```
