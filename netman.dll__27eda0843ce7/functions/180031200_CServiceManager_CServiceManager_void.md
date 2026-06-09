# CServiceManager::~CServiceManager(void)

- ea: `0x180031200`
- end: `0x180031233`
- name: `??1CServiceManager@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180031328`
- `0x180035852`

## callees

- `0x180031200`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x180031220`
- `ADVAPI32!CloseServiceHandle` at `0x180031220`

## pseudocode

```c
void __fastcall CServiceManager::~CServiceManager(CServiceManager *this)
{
  SC_HANDLE v2; // rcx

  if ( *((_QWORD *)this + 1) )
    *((_QWORD *)this + 1) = 0;
  v2 = *(SC_HANDLE *)this;
  if ( v2 )
  {
    CloseServiceHandle(v2);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180031200  push    rbx
0x180031202  sub     rsp, 20h
0x180031206  mov     rbx, rcx
0x180031209  cmp     qword ptr [rcx+8], 0
0x18003120e  jz      short loc_180031218
0x180031210  mov     qword ptr [rcx+8], 0
0x180031218  mov     rcx, [rcx]; hSCObject
0x18003121b  test    rcx, rcx
0x18003121e  jz      short loc_18003122D
0x180031220  call    cs:__imp_CloseServiceHandle
0x180031226  mov     qword ptr [rbx], 0
0x18003122d  add     rsp, 20h
0x180031231  pop     rbx
0x180031232  retn
```
