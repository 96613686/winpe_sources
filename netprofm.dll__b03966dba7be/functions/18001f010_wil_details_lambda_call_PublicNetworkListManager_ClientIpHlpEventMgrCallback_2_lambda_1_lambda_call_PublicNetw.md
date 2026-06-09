# wil::details::lambda_call__PublicNetworkListManager::ClientIpHlpEventMgrCallback_::_2_::_lambda_1___::_lambda_call__PublicNetworkListManager::ClientIpHlpEventMgrCallback_::_2_::_lambda_1___

- ea: `0x18001f010`
- end: `0x18001f040`
- name: `wil::details::lambda_call__PublicNetworkListManager::ClientIpHlpEventMgrCallback_::_2_::_lambda_1___::_lambda_call__PublicNetworkListManager::ClientIpHlpEventMgrCallback_::_2_::_lambda_1___`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180040fff`

## callees

- `0x18001f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f035`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f035`

## pseudocode

```c
void __fastcall wil::details::lambda_call__PublicNetworkListManager::ClientIpHlpEventMgrCallback_::_2_::_lambda_1___::_lambda_call__PublicNetworkListManager::ClientIpHlpEventMgrCallback_::_2_::_lambda_1___(
        _BYTE *a1)
{
  if ( a1[8] )
  {
    a1[8] = 0;
    SetThreadpoolWait(*(PTP_WAIT *)(**(_QWORD **)a1 + 704LL), *(HANDLE *)(**(_QWORD **)a1 + 768LL), 0);
  }
}

```

## disassembly

```asm
0x18001f010  sub     rsp, 28h
0x18001f014  cmp     byte ptr [rcx+8], 0
0x18001f018  jz      short loc_18001F03B
0x18001f01a  mov     byte ptr [rcx+8], 0
0x18001f01e  xor     r8d, r8d; pftTimeout
0x18001f021  mov     rax, [rcx]
0x18001f024  mov     rcx, [rax]
0x18001f027  mov     rdx, [rcx+300h]; h
0x18001f02e  mov     rcx, [rcx+2C0h]; pwa
0x18001f035  call    cs:__imp_SetThreadpoolWait
0x18001f03b  add     rsp, 28h
0x18001f03f  retn
```
