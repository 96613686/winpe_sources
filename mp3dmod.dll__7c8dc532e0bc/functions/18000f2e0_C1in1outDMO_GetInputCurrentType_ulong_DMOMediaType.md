# C1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x18000f2e0`
- end: `0x18000f33d`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `93`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f32c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f32c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2fb`
- `msdmo!MoCopyMediaType` at `0x18000f31a`
- `msdmo!MoCopyMediaType` at `0x18000f31a`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetInputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  if ( a2 )
  {
    v7 = -2147220991;
  }
  else if ( *((_DWORD *)this + 2) )
  {
    v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 16));
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
0x18000f2e0  push    rbx
0x18000f2e2  push    rbp
0x18000f2e3  push    rsi
0x18000f2e4  push    rdi
0x18000f2e5  sub     rsp, 28h
0x18000f2e9  lea     rsi, [rcx+0C8h]
0x18000f2f0  mov     rdi, rcx
0x18000f2f3  mov     rcx, rsi; lpCriticalSection
0x18000f2f6  mov     rbp, r8
0x18000f2f9  mov     ebx, edx
0x18000f2fb  call    cs:__imp_EnterCriticalSection
0x18000f301  cmp     ebx, 1
0x18000f304  jb      short loc_18000F30D
0x18000f306  mov     ebx, 80040201h
0x18000f30b  jmp     short loc_18000F329
0x18000f30d  cmp     dword ptr [rdi+8], 0
0x18000f311  jz      short loc_18000F324
0x18000f313  lea     rdx, [rdi+10h]; pmtSrc
0x18000f317  mov     rcx, rbp; pmtDest
0x18000f31a  call    cs:__imp_MoCopyMediaType
0x18000f320  mov     ebx, eax
0x18000f322  jmp     short loc_18000F329
0x18000f324  mov     ebx, 80040203h
0x18000f329  mov     rcx, rsi; lpCriticalSection
0x18000f32c  call    cs:__imp_LeaveCriticalSection
0x18000f332  mov     eax, ebx
0x18000f334  add     rsp, 28h
0x18000f338  pop     rdi
0x18000f339  pop     rsi
0x18000f33a  pop     rbp
0x18000f33b  pop     rbx
0x18000f33c  retn
```
