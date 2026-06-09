# CApiPortClient::~CApiPortClient(void)

- ea: `0x18000b808`
- end: `0x18000b85c`
- name: `??1CApiPortClient@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CApiPortClient *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a5a0`

## callees

- `0x18000b808`
- `0x18000b864`
- `0x18000b880`
- `0x18000bab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b83b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b83b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b832`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b832`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b81c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b81c`

## pseudocode

```c
void __fastcall CApiPortClient::~CApiPortClient(CApiPortClient *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CApiPortClient::Disconnect(this);
  if ( v1 )
    LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)this + 8);
  std::unique_ptr<CPortClient>::~unique_ptr<CPortClient>(this);
}

```

## disassembly

```asm
0x18000b808  mov     [rsp+arg_0], rbx
0x18000b80d  push    rdi
0x18000b80e  sub     rsp, 20h
0x18000b812  lea     rbx, [rcx+10h]
0x18000b816  mov     rdi, rcx
0x18000b819  mov     rcx, rbx; lpCriticalSection
0x18000b81c  call    cs:__imp_EnterCriticalSection
0x18000b822  mov     rcx, rdi; this
0x18000b825  call    ?Disconnect@CApiPortClient@@AEAAXXZ; CApiPortClient::Disconnect(void)
0x18000b82a  test    rbx, rbx
0x18000b82d  jz      short loc_18000B838
0x18000b82f  mov     rcx, rbx; lpCriticalSection
0x18000b832  call    cs:__imp_LeaveCriticalSection
0x18000b838  mov     rcx, rbx; lpCriticalSection
0x18000b83b  call    cs:__imp_DeleteCriticalSection
0x18000b841  lea     rcx, [rdi+8]
0x18000b845  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x18000b84a  mov     rcx, rdi
0x18000b84d  mov     rbx, [rsp+28h+arg_0]
0x18000b852  add     rsp, 20h
0x18000b856  pop     rdi
0x18000b857  jmp     ??1?$unique_ptr@VCPortClient@@U?$default_delete@VCPortClient@@@std@@@std@@QEAA@XZ; std::unique_ptr<CPortClient>::~unique_ptr<CPortClient>(void)
```
