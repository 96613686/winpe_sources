# C1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x18000d100`
- end: `0x18000d15d`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d14c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d14c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d11b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d11b`
- `msdmo!MoCopyMediaType` at `0x18000d13a`
- `msdmo!MoCopyMediaType` at `0x18000d13a`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetOutputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v7 = -2147220991;
  }
  else if ( *((_DWORD *)this + 3) )
  {
    v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 104));
  }
  else
  {
    v7 = -2147220989;
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000d100  push    rbx
0x18000d102  push    rbp
0x18000d103  push    rsi
0x18000d104  push    rdi
0x18000d105  sub     rsp, 28h
0x18000d109  lea     rsi, [rcx+0C8h]
0x18000d110  mov     rdi, rcx
0x18000d113  mov     rcx, rsi; lpCriticalSection
0x18000d116  mov     rbp, r8
0x18000d119  mov     ebx, edx
0x18000d11b  call    cs:__imp_EnterCriticalSection
0x18000d121  cmp     ebx, 1
0x18000d124  jb      short loc_18000D12D
0x18000d126  mov     ebx, 80040201h
0x18000d12b  jmp     short loc_18000D149
0x18000d12d  cmp     dword ptr [rdi+0Ch], 0
0x18000d131  jz      short loc_18000D144
0x18000d133  lea     rdx, [rdi+68h]; pmtSrc
0x18000d137  mov     rcx, rbp; pmtDest
0x18000d13a  call    cs:__imp_MoCopyMediaType
0x18000d140  mov     ebx, eax
0x18000d142  jmp     short loc_18000D149
0x18000d144  mov     ebx, 80040203h
0x18000d149  mov     rcx, rsi; lpCriticalSection
0x18000d14c  call    cs:__imp_LeaveCriticalSection
0x18000d152  mov     eax, ebx
0x18000d154  add     rsp, 28h
0x18000d158  pop     rdi
0x18000d159  pop     rsi
0x18000d15a  pop     rbp
0x18000d15b  pop     rbx
0x18000d15c  retn
```
