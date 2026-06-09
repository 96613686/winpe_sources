# RequestQueue::Init(void)

- ea: `0x180018100`
- end: `0x18001818f`
- name: `?Init@RequestQueue@@QEAAJXZ`
- size: `143`
- prototype: `__int64 __fastcall(RequestQueue *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e240`

## callees

- `0x18000f1c4`
- `0x180018100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180018128`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180018128`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001815e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001815e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001816d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001816d`

## pseudocode

```c
__int64 __fastcall RequestQueue::Init(HANDLE *this)
{
  HANDLE Semaphore; // rbx
  unsigned int v3; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax

  Semaphore = CreateSemaphoreExW(0, 0, 101, 0, 0, 0x1F0003u);
  if ( (char *)*this - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*this);
  *this = Semaphore;
  if ( (((unsigned __int64)Semaphore + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    || (v3 = 0, EventW = CreateEventW(0, 0, 0, 0), (this[6] = EventW) == 0) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180018100  mov     [rsp+arg_0], rbx
0x180018105  push    rdi
0x180018106  sub     rsp, 30h
0x18001810a  xor     r9d, r9d; lpName
0x18001810d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180018115  mov     rdi, rcx
0x180018118  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180018120  xor     edx, edx; lInitialCount
0x180018122  xor     ecx, ecx; lpSemaphoreAttributes
0x180018124  lea     r8d, [r9+65h]; lMaximumCount
0x180018128  call    cs:__imp_CreateSemaphoreExW
0x18001812e  mov     rcx, [rdi]; hObject
0x180018131  mov     rbx, rax
0x180018134  lea     rdx, [rcx-1]
0x180018138  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001813c  ja      short loc_180018143
0x18001813e  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180018143  lea     rax, [rbx+1]
0x180018147  mov     [rdi], rbx
0x18001814a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180018150  jz      short loc_18001816D
0x180018152  xor     r9d, r9d; lpName
0x180018155  xor     r8d, r8d; bInitialState
0x180018158  xor     edx, edx; bManualReset
0x18001815a  xor     ecx, ecx; lpEventAttributes
0x18001815c  xor     ebx, ebx
0x18001815e  call    cs:__imp_CreateEventW
0x180018164  mov     [rdi+30h], rax
0x180018168  test    rax, rax
0x18001816b  jnz     short loc_180018182
0x18001816d  call    cs:__imp_GetLastError
0x180018173  mov     ebx, eax
0x180018175  test    eax, eax
0x180018177  jle     short loc_180018182
0x180018179  movzx   ebx, ax
0x18001817c  or      ebx, 80070000h
0x180018182  mov     eax, ebx
0x180018184  mov     rbx, [rsp+38h+arg_0]
0x180018189  add     rsp, 30h
0x18001818d  pop     rdi
0x18001818e  retn
```
