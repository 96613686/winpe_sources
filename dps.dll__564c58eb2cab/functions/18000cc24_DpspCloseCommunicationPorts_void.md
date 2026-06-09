# DpspCloseCommunicationPorts(void)

- ea: `0x18000cc24`
- end: `0x18000ccdc`
- name: `?DpspCloseCommunicationPorts@@YAXXZ`
- size: `184`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f774`

## callees

- `0x18000cc24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ccbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cc8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ccaa`

## pseudocode

```c
void DpspCloseCommunicationPorts(void)
{
  __int64 i; // rbx
  char *v1; // rcx
  struct __SESSIONINFO *j; // rbx
  char *v3; // rcx

  for ( i = g_pHostHead; i; i = *(_QWORD *)(i + 136) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(i + 72));
    v1 = *(char **)(i + 128);
    *(_DWORD *)i = 0;
    if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v1);
      *(_QWORD *)(i + 128) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(i + 72));
  }
  for ( j = g_pSessionHead; j; j = (struct __SESSIONINFO *)*((_QWORD *)j + 23) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)j + 64));
    v3 = (char *)*((_QWORD *)j + 21);
    *((_DWORD *)j + 6) = 0;
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v3);
      *((_QWORD *)j + 21) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)j + 64));
  }
}

```

## disassembly

```asm
0x18000cc24  mov     [rsp+arg_0], rbx
0x18000cc29  push    rdi
0x18000cc2a  sub     rsp, 20h
0x18000cc2e  mov     rbx, cs:g_pHostHead
0x18000cc35  jmp     short loc_18000CC7A
0x18000cc37  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000cc3b  call    cs:__imp_EnterCriticalSection
0x18000cc41  mov     rcx, [rbx+80h]; hObject
0x18000cc48  mov     dword ptr [rbx], 0
0x18000cc4e  lea     rax, [rcx-1]
0x18000cc52  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cc56  ja      short loc_18000CC69
0x18000cc58  call    cs:__imp_CloseHandle
0x18000cc5e  mov     qword ptr [rbx+80h], 0
0x18000cc69  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000cc6d  call    cs:__imp_LeaveCriticalSection
0x18000cc73  mov     rbx, [rbx+88h]
0x18000cc7a  test    rbx, rbx
0x18000cc7d  jnz     short loc_18000CC37
0x18000cc7f  mov     rbx, cs:g_pSessionHead
0x18000cc86  jmp     short loc_18000CCCC
0x18000cc88  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000cc8c  call    cs:__imp_EnterCriticalSection
0x18000cc92  mov     rcx, [rbx+0A8h]; hObject
0x18000cc99  mov     dword ptr [rbx+18h], 0
0x18000cca0  lea     rax, [rcx-1]
0x18000cca4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cca8  ja      short loc_18000CCBB
0x18000ccaa  call    cs:__imp_CloseHandle
0x18000ccb0  mov     qword ptr [rbx+0A8h], 0
0x18000ccbb  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000ccbf  call    cs:__imp_LeaveCriticalSection
0x18000ccc5  mov     rbx, [rbx+0B8h]
0x18000cccc  test    rbx, rbx
0x18000cccf  jnz     short loc_18000CC88
0x18000ccd1  mov     rbx, [rsp+28h+arg_0]
0x18000ccd6  add     rsp, 20h
0x18000ccda  pop     rdi
0x18000ccdb  retn
```
