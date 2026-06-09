# wil::details::lambda_call__PrivateNlm::GetConnectivity_::_2_::_lambda_1___::_lambda_call__PrivateNlm::GetConnectivity_::_2_::_lambda_1___

- ea: `0x180034c88`
- end: `0x180034cef`
- name: `wil::details::lambda_call__PrivateNlm::GetConnectivity_::_2_::_lambda_1___::_lambda_call__PrivateNlm::GetConnectivity_::_2_::_lambda_1___`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800403ee`

## callees

- `0x180034c88`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034cdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::lambda_call__PrivateNlm::GetConnectivity_::_2_::_lambda_1___::_lambda_call__PrivateNlm::GetConnectivity_::_2_::_lambda_1___(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rcx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    if ( **(_QWORD **)a1 )
    {
      for ( i = 0; (unsigned int)i < **(_DWORD **)(a1 + 8); i = (unsigned int)(i + 1) )
      {
        v3 = *(_QWORD *)(**(_QWORD **)a1 + 8 * i);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
      CoTaskMemFree(**(LPVOID **)a1);
    }
  }
}

```

## disassembly

```asm
0x180034c88  mov     [rsp+arg_0], rbx
0x180034c8d  push    rdi
0x180034c8e  sub     rsp, 20h
0x180034c92  mov     rbx, rcx
0x180034c95  cmp     byte ptr [rcx+10h], 0
0x180034c99  jz      short loc_180034CE4
0x180034c9b  mov     byte ptr [rcx+10h], 0
0x180034c9f  mov     rax, [rcx]
0x180034ca2  cmp     qword ptr [rax], 0
0x180034ca6  jz      short loc_180034CE4
0x180034ca8  xor     edi, edi
0x180034caa  mov     rax, [rcx+8]
0x180034cae  cmp     [rax], edi
0x180034cb0  jbe     short loc_180034CD7
0x180034cb2  mov     rax, [rbx]
0x180034cb5  mov     rcx, [rax]
0x180034cb8  mov     rcx, [rcx+rdi*8]
0x180034cbc  test    rcx, rcx
0x180034cbf  jz      short loc_180034CCD
0x180034cc1  mov     rax, [rcx]
0x180034cc4  mov     rax, [rax+10h]
0x180034cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ccd  inc     edi
0x180034ccf  mov     rax, [rbx+8]
0x180034cd3  cmp     edi, [rax]
0x180034cd5  jb      short loc_180034CB2
0x180034cd7  mov     rcx, [rbx]
0x180034cda  mov     rcx, [rcx]; pv
0x180034cdd  call    cs:__imp_CoTaskMemFree
0x180034ce3  nop
0x180034ce4  mov     rbx, [rsp+28h+arg_0]
0x180034ce9  add     rsp, 20h
0x180034ced  pop     rdi
0x180034cee  retn
```
