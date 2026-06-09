# ISAPI_CONTEXT::IsapiDoRevertHack(void * *,int)

- ea: `0x180005e88`
- end: `0x180005ec8`
- name: `?IsapiDoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAXH@Z`
- size: `64`
- prototype: `void(ISAPI_CONTEXT *__hidden this, void **, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180005e88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005eb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005eb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005e9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005e9d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005ebc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005ebc`

## pseudocode

```c
void __fastcall ISAPI_CONTEXT::IsapiDoRevertHack(ISAPI_CONTEXT *this, void **a2, int a3)
{
  HANDLE CurrentThread; // rax

  *a2 = 0;
  if ( a3 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, a2) )
      RevertToSelf();
  }
}

```

## disassembly

```asm
0x180005e88  push    rbx
0x180005e8a  sub     rsp, 20h
0x180005e8e  mov     qword ptr [rdx], 0
0x180005e95  mov     rbx, rdx
0x180005e98  test    r8d, r8d
0x180005e9b  jz      short loc_180005EC2
0x180005e9d  call    cs:__imp_GetCurrentThread
0x180005ea3  mov     edx, 4; DesiredAccess
0x180005ea8  mov     r9, rbx; TokenHandle
0x180005eab  mov     rcx, rax; ThreadHandle
0x180005eae  lea     r8d, [rdx-3]; OpenAsSelf
0x180005eb2  call    cs:__imp_OpenThreadToken
0x180005eb8  test    eax, eax
0x180005eba  jz      short loc_180005EC2
0x180005ebc  call    cs:__imp_RevertToSelf
0x180005ec2  add     rsp, 20h
0x180005ec6  pop     rbx
0x180005ec7  retn
```
