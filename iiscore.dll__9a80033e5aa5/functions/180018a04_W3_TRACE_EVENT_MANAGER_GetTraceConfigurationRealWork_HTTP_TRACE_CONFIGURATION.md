# W3_TRACE_EVENT_MANAGER::GetTraceConfigurationRealWork(HTTP_TRACE_CONFIGURATION *)

- ea: `0x180018a04`
- end: `0x180018aca`
- name: `?GetTraceConfigurationRealWork@W3_TRACE_EVENT_MANAGER@@QEAAJPEAUHTTP_TRACE_CONFIGURATION@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, struct HTTP_TRACE_CONFIGURATION *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800107d0`
- `0x180014530`

## callees

- `0x180018a04`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018ab7`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018ab7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018a21`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018a21`

## pseudocode

```c
__int64 __fastcall W3_TRACE_EVENT_MANAGER::GetTraceConfigurationRealWork(
        DWORD **this,
        struct HTTP_TRACE_CONFIGURATION *a2)
{
  DWORD *v4; // rcx
  LPCGUID pProviderGuid; // r8

  a2->fProviderEnabled = 0;
  if ( *((_BYTE *)this + 44) )
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)this);
  v4 = this[3];
  if ( v4 != (DWORD *)(this + 3) )
  {
    pProviderGuid = a2->pProviderGuid;
    while ( pProviderGuid != (LPCGUID)(v4 + 12)
         && (!pProviderGuid
          || v4 == (DWORD *)-48LL
          || pProviderGuid->Data1 != v4[12]
          || *(_DWORD *)&pProviderGuid->Data2 != v4[13]
          || *(_DWORD *)pProviderGuid->Data4 != v4[14]
          || *(_DWORD *)&pProviderGuid->Data4[4] != v4[15]) )
    {
      v4 = *(DWORD **)v4;
      if ( v4 == (DWORD *)(this + 3) )
        goto LABEL_15;
    }
    a2->dwAreas = v4[8];
    a2->dwVerbosity = v4[9];
    a2->fProviderEnabled = 1;
  }
LABEL_15:
  if ( !a2->fProviderEnabled && *((_DWORD *)this + 52) )
  {
    *(_OWORD *)&a2->pProviderGuid = *((_OWORD *)this + 12);
    *(_QWORD *)&a2->fProviderEnabled = this[26];
  }
  if ( *((_BYTE *)this + 44) )
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)this);
  return 0;
}

```

## disassembly

```asm
0x180018a04  mov     [rsp+arg_0], rbx
0x180018a09  push    rdi
0x180018a0a  sub     rsp, 20h
0x180018a0e  mov     dword ptr [rdx+10h], 0
0x180018a15  mov     rdi, rdx
0x180018a18  cmp     byte ptr [rcx+2Ch], 0
0x180018a1c  mov     rbx, rcx
0x180018a1f  jz      short loc_180018A27
0x180018a21  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180018a27  lea     r9, [rbx+18h]
0x180018a2b  mov     rcx, [r9]
0x180018a2e  cmp     rcx, r9
0x180018a31  jz      short loc_180018A88
0x180018a33  mov     r8, [rdi]
0x180018a36  lea     rdx, [rcx+30h]
0x180018a3a  cmp     r8, rdx
0x180018a3d  jz      short loc_180018A75
0x180018a3f  test    r8, r8
0x180018a42  jz      short loc_180018A6B
0x180018a44  test    rdx, rdx
0x180018a47  jz      short loc_180018A6B
0x180018a49  mov     eax, [rdx]
0x180018a4b  cmp     [r8], eax
0x180018a4e  jnz     short loc_180018A6B
0x180018a50  mov     eax, [rdx+4]
0x180018a53  cmp     [r8+4], eax
0x180018a57  jnz     short loc_180018A6B
0x180018a59  mov     eax, [rdx+8]
0x180018a5c  cmp     [r8+8], eax
0x180018a60  jnz     short loc_180018A6B
0x180018a62  mov     eax, [rdx+0Ch]
0x180018a65  cmp     [r8+0Ch], eax
0x180018a69  jz      short loc_180018A75
0x180018a6b  mov     rcx, [rcx]
0x180018a6e  cmp     rcx, r9
0x180018a71  jnz     short loc_180018A36
0x180018a73  jmp     short loc_180018A88
0x180018a75  mov     eax, [rcx+20h]
0x180018a78  mov     [rdi+8], eax
0x180018a7b  mov     eax, [rcx+24h]
0x180018a7e  mov     [rdi+0Ch], eax
0x180018a81  mov     dword ptr [rdi+10h], 1
0x180018a88  cmp     dword ptr [rdi+10h], 0
0x180018a8c  jnz     short loc_180018AAE
0x180018a8e  cmp     dword ptr [rbx+0D0h], 0
0x180018a95  jz      short loc_180018AAE
0x180018a97  movups  xmm0, xmmword ptr [rbx+0C0h]
0x180018a9e  movups  xmmword ptr [rdi], xmm0
0x180018aa1  movsd   xmm1, qword ptr [rbx+0D0h]
0x180018aa9  movsd   qword ptr [rdi+10h], xmm1
0x180018aae  cmp     byte ptr [rbx+2Ch], 0
0x180018ab2  jz      short loc_180018ABD
0x180018ab4  mov     rcx, rbx
0x180018ab7  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180018abd  mov     rbx, [rsp+28h+arg_0]
0x180018ac2  xor     eax, eax
0x180018ac4  add     rsp, 20h
0x180018ac8  pop     rdi
0x180018ac9  retn
```
