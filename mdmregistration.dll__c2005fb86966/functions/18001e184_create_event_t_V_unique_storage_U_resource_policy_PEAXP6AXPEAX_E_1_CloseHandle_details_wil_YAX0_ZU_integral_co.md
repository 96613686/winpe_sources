# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18001e184`
- end: `0x18001e21a`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aadc`
- `0x180044f4c`

## callees

- `0x180008700`
- `0x18000cc00`
- `0x18001e184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001e19d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001e19d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e1c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e1e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e1e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e1d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e1d6`

## pseudocode

```c
__int64 __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1)
{
  wil::details *v2; // rcx
  HANDLE Event; // rbp
  void *v4; // rbx
  DWORD LastError; // esi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v2);
  GetLastError();
  v4 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v4) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
    SetLastError(LastError);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x18001e184  push    rbx
0x18001e186  push    rbp
0x18001e187  push    rsi
0x18001e188  push    rdi
0x18001e189  sub     rsp, 28h
0x18001e18d  mov     rdi, rcx
0x18001e190  mov     r9d, 1F0003h; dwDesiredAccess
0x18001e196  xor     ecx, ecx; lpEventAttributes
0x18001e198  xor     r8d, r8d; dwFlags
0x18001e19b  xor     edx, edx; lpName
0x18001e19d  call    cs:__imp_CreateEventExW
0x18001e1a4  nop     dword ptr [rax+rax+00h]
0x18001e1a9  mov     rbp, rax
0x18001e1ac  test    rax, rax
0x18001e1af  jz      short loc_18001E1FB
0x18001e1b1  call    cs:__imp_GetLastError
0x18001e1b8  nop     dword ptr [rax+rax+00h]
0x18001e1bd  mov     rbx, [rdi]
0x18001e1c0  test    rbx, rbx
0x18001e1c3  jz      short loc_18001E1F4
0x18001e1c5  call    cs:__imp_GetLastError
0x18001e1cc  nop     dword ptr [rax+rax+00h]
0x18001e1d1  mov     rcx, rbx; hObject
0x18001e1d4  mov     esi, eax
0x18001e1d6  call    cs:__imp_CloseHandle
0x18001e1dd  nop     dword ptr [rax+rax+00h]
0x18001e1e2  test    eax, eax
0x18001e1e4  jz      short loc_18001E20A
0x18001e1e6  mov     ecx, esi; dwErrCode
0x18001e1e8  call    cs:__imp_SetLastError
0x18001e1ef  nop     dword ptr [rax+rax+00h]
0x18001e1f4  mov     [rdi], rbp
0x18001e1f7  xor     eax, eax
0x18001e1f9  jmp     short loc_18001E200
0x18001e1fb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001e200  add     rsp, 28h
0x18001e204  pop     rdi
0x18001e205  pop     rsi
0x18001e206  pop     rbp
0x18001e207  pop     rbx
0x18001e208  retn
0x18001e20a  mov     rcx, [rsp+48h]; this
0x18001e20f  mov     edx, 0A0Bh; void *
0x18001e214  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
