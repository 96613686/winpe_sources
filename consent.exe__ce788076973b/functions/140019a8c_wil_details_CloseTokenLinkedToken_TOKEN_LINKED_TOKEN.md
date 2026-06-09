# wil::details::CloseTokenLinkedToken(_TOKEN_LINKED_TOKEN *)

- ea: `0x140019a8c`
- end: `0x140019abc`
- name: `?CloseTokenLinkedToken@details@wil@@YAXPEAU_TOKEN_LINKED_TOKEN@@@Z`
- size: `48`
- prototype: `void __fastcall(void **this, struct _TOKEN_LINKED_TOKEN *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140019b34`
- `0x140019fbc`

## callees

- `0x140013684`
- `0x140019a8c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019a9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019a9d`

## pseudocode

```c
void __fastcall wil::details::CloseTokenLinkedToken(void **this, struct _TOKEN_LINKED_TOKEN *a2)
{
  char *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (char *)*this;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA1C, v3, v4);
}

```

## disassembly

```asm
0x140019a8c  sub     rsp, 28h
0x140019a90  mov     rcx, [rcx]; hObject
0x140019a93  lea     rax, [rcx-1]
0x140019a97  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019a9b  ja      short loc_140019AA7
0x140019a9d  call    cs:__imp_CloseHandle
0x140019aa3  test    eax, eax
0x140019aa5  jz      short loc_140019AAC
0x140019aa7  add     rsp, 28h
0x140019aab  retn
0x140019aac  mov     rcx, [rsp+28h]; this
0x140019ab1  mov     edx, 0A1Ch; void *
0x140019ab6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
