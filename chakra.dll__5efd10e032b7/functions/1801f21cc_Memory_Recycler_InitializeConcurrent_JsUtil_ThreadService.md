# Memory::Recycler::InitializeConcurrent(JsUtil::ThreadService *)

- ea: `0x1801f21cc`
- end: `0x1801f229e`
- name: `?InitializeConcurrent@Recycler@Memory@@AEAA_NPEAVThreadService@JsUtil@@@Z`
- size: `210`
- prototype: `bool __fastcall(Memory::Recycler *__hidden this, struct JsUtil::ThreadService *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1801f1f74`

## callees

- `0x180167544`
- `0x1801f21cc`
- `0x1805a9a91`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f21ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f2234`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f2267`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f21ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f2234`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f2267`

## pseudocode

```c
char __fastcall Memory::Recycler::InitializeConcurrent(Memory::Recycler *this, struct JsUtil::ThreadService *a2)
{
  HANDLE EventW; // rax
  HANDLE v3; // rax
  HANDLE v4; // rax
  char pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  char v7; // [rsp+21h] [rbp-17h] BYREF
  char v8; // [rsp+22h] [rbp-16h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = -2;
  try
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 272) = EventW;
    if ( !EventW )
      throw (Js::OutOfMemoryException *)&pExceptionObject;
    if ( !JsUtil::ThreadService::HasCallback(a2) )
    {
      v3 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 2166) = v3;
      if ( !v3 )
        throw (Js::OutOfMemoryException *)&v7;
      v4 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 271) = v4;
      if ( !v4 )
        throw (Js::OutOfMemoryException *)&v8;
    }
  }
  catch ( Js::OutOfMemoryException )
  {
    if ( *((_QWORD *)this + 272) )
    {
      CloseHandle(*((HANDLE *)this + 272));
      *((_QWORD *)this + 272) = 0;
    }
    if ( *((_QWORD *)this + 2166) )
    {
      CloseHandle(*((HANDLE *)this + 2166));
      *((_QWORD *)this + 2166) = 0;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1801f21cc  mov     [rsp+arg_8], rdx
0x1801f21d1  mov     [rsp+arg_0], rcx
0x1801f21d6  push    rbx
0x1801f21d7  sub     rsp, 30h
0x1801f21db  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x1801f21e4  xor     r9d, r9d; lpName
0x1801f21e7  xor     r8d, r8d; bInitialState
0x1801f21ea  xor     edx, edx; bManualReset
0x1801f21ec  xor     ecx, ecx; lpEventAttributes
0x1801f21ee  call    cs:__imp_CreateEventW
0x1801f21f5  nop     dword ptr [rax+rax+00h]
0x1801f21fa  mov     rbx, [rsp+38h+arg_0]
0x1801f21ff  mov     [rbx+880h], rax
0x1801f2206  test    rax, rax
0x1801f2209  jnz     short loc_1801F221C
0x1801f220b  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x1801f2212  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1801f2217  call    _CxxThrowException_0
0x1801f221c  mov     rcx, [rsp+38h+arg_8]; this
0x1801f2221  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x1801f2226  test    al, al
0x1801f2228  jnz     short loc_1801F2291
0x1801f222a  xor     r9d, r9d; lpName
0x1801f222d  xor     r8d, r8d; bInitialState
0x1801f2230  xor     edx, edx; bManualReset
0x1801f2232  xor     ecx, ecx; lpEventAttributes
0x1801f2234  call    cs:__imp_CreateEventW
0x1801f223b  nop     dword ptr [rax+rax+00h]
0x1801f2240  mov     [rbx+43B0h], rax
0x1801f2247  test    rax, rax
0x1801f224a  jnz     short loc_1801F225D
0x1801f224c  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x1801f2253  lea     rcx, [rsp+38h+var_17]; pExceptionObject
0x1801f2258  call    _CxxThrowException_0
0x1801f225d  xor     r9d, r9d; lpName
0x1801f2260  xor     r8d, r8d; bInitialState
0x1801f2263  xor     edx, edx; bManualReset
0x1801f2265  xor     ecx, ecx; lpEventAttributes
0x1801f2267  call    cs:__imp_CreateEventW
0x1801f226e  nop     dword ptr [rax+rax+00h]
0x1801f2273  mov     [rbx+878h], rax
0x1801f227a  test    rax, rax
0x1801f227d  jnz     short loc_1801F2291
0x1801f227f  lea     rdx, _TI2?AVOutOfMemoryException@Js@@; pThrowInfo
0x1801f2286  lea     rcx, [rsp+38h+var_16]; pExceptionObject
0x1801f228b  call    _CxxThrowException_0
0x1801f2291  mov     al, 1
0x1801f2293  jmp     short loc_1801F2297
0x1801f2295  xor     al, al
0x1801f2297  add     rsp, 30h
0x1801f229b  pop     rbx
0x1801f229c  retn
```
