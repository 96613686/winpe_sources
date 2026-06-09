# W3_TRACE_EVENT_MANAGER::GetTraceConfigurationRealWork(HTTP_TRACE_CONFIGURATION *)

- ea: `0x180019f10`
- end: `0x180019fe3`
- name: `?GetTraceConfigurationRealWork@W3_TRACE_EVENT_MANAGER@@QEAAJPEAUHTTP_TRACE_CONFIGURATION@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, struct HTTP_TRACE_CONFIGURATION *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011570`
- `0x180015630`

## callees

- `0x180019f10`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019fc9`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180019fc9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019f2d`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180019f2d`

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
0x180019f10  mov     [rsp+arg_0], rbx
0x180019f15  push    rdi
0x180019f16  sub     rsp, 20h
0x180019f1a  mov     dword ptr [rdx+10h], 0
0x180019f21  mov     rdi, rdx
0x180019f24  cmp     byte ptr [rcx+2Ch], 0
0x180019f28  mov     rbx, rcx
0x180019f2b  jz      short loc_180019F39
0x180019f2d  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180019f34  nop     dword ptr [rax+rax+00h]
0x180019f39  lea     r9, [rbx+18h]
0x180019f3d  mov     rcx, [r9]
0x180019f40  cmp     rcx, r9
0x180019f43  jz      short loc_180019F9A
0x180019f45  mov     r8, [rdi]
0x180019f48  lea     rdx, [rcx+30h]
0x180019f4c  cmp     r8, rdx
0x180019f4f  jz      short loc_180019F87
0x180019f51  test    r8, r8
0x180019f54  jz      short loc_180019F7D
0x180019f56  test    rdx, rdx
0x180019f59  jz      short loc_180019F7D
0x180019f5b  mov     eax, [rdx]
0x180019f5d  cmp     [r8], eax
0x180019f60  jnz     short loc_180019F7D
0x180019f62  mov     eax, [rdx+4]
0x180019f65  cmp     [r8+4], eax
0x180019f69  jnz     short loc_180019F7D
0x180019f6b  mov     eax, [rdx+8]
0x180019f6e  cmp     [r8+8], eax
0x180019f72  jnz     short loc_180019F7D
0x180019f74  mov     eax, [rdx+0Ch]
0x180019f77  cmp     [r8+0Ch], eax
0x180019f7b  jz      short loc_180019F87
0x180019f7d  mov     rcx, [rcx]
0x180019f80  cmp     rcx, r9
0x180019f83  jnz     short loc_180019F48
0x180019f85  jmp     short loc_180019F9A
0x180019f87  mov     eax, [rcx+20h]
0x180019f8a  mov     [rdi+8], eax
0x180019f8d  mov     eax, [rcx+24h]
0x180019f90  mov     [rdi+0Ch], eax
0x180019f93  mov     dword ptr [rdi+10h], 1
0x180019f9a  cmp     dword ptr [rdi+10h], 0
0x180019f9e  jnz     short loc_180019FC0
0x180019fa0  cmp     dword ptr [rbx+0D0h], 0
0x180019fa7  jz      short loc_180019FC0
0x180019fa9  movups  xmm0, xmmword ptr [rbx+0C0h]
0x180019fb0  movups  xmmword ptr [rdi], xmm0
0x180019fb3  movsd   xmm1, qword ptr [rbx+0D0h]
0x180019fbb  movsd   qword ptr [rdi+10h], xmm1
0x180019fc0  cmp     byte ptr [rbx+2Ch], 0
0x180019fc4  jz      short loc_180019FD5
0x180019fc6  mov     rcx, rbx
0x180019fc9  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180019fd0  nop     dword ptr [rax+rax+00h]
0x180019fd5  mov     rbx, [rsp+28h+arg_0]
0x180019fda  xor     eax, eax
0x180019fdc  add     rsp, 20h
0x180019fe0  pop     rdi
0x180019fe1  retn
```
