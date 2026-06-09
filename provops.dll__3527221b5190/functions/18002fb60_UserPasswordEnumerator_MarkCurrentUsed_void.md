# UserPasswordEnumerator::MarkCurrentUsed(void)

- ea: `0x18002fb60`
- end: `0x18002fbb4`
- name: `?MarkCurrentUsed@UserPasswordEnumerator@@UEAAXXZ`
- size: `84`
- prototype: `void __fastcall(UserPasswordEnumerator *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002fb60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb86`

## pseudocode

```c
void __fastcall UserPasswordEnumerator::MarkCurrentUsed(UserPasswordEnumerator *this)
{
  void *v1; // rsi
  DWORD LastError; // ebx

  v1 = (void *)*((_QWORD *)this + 5);
  if ( v1 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v1);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x18002fb60  mov     [rsp+arg_0], rbx
0x18002fb65  mov     [rsp+arg_8], rsi
0x18002fb6a  push    rdi
0x18002fb6b  sub     rsp, 20h
0x18002fb6f  mov     rsi, [rcx+28h]
0x18002fb73  mov     rdi, rcx
0x18002fb76  test    rsi, rsi
0x18002fb79  jz      short loc_18002FB94
0x18002fb7b  call    cs:__imp_GetLastError
0x18002fb81  mov     rcx, rsi; pv
0x18002fb84  mov     ebx, eax
0x18002fb86  call    cs:__imp_CoTaskMemFree
0x18002fb8c  mov     ecx, ebx; dwErrCode
0x18002fb8e  call    cs:__imp_SetLastError
0x18002fb94  mov     rbx, [rsp+28h+arg_0]
0x18002fb99  mov     rsi, [rsp+28h+arg_8]
0x18002fb9e  mov     qword ptr [rdi+28h], 0
0x18002fba6  mov     qword ptr [rdi+30h], 0
0x18002fbae  add     rsp, 20h
0x18002fbb2  pop     rdi
0x18002fbb3  retn
```
