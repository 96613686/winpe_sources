# C1in1outDMO::GetInputCurrentType(ulong,_DMOMediaType *)

- ea: `0x18000cfd0`
- end: `0x18000d039`
- name: `?GetInputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `105`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000cfd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cfeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cfeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d028`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d028`
- `msdmo!MoCopyMediaType` at `0x18000d01d`
- `msdmo!MoCopyMediaType` at `0x18000d01d`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetInputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( a2 )
  {
    v7 = -2147220991;
  }
  else if ( a3 )
  {
    if ( *((_DWORD *)this + 2) )
      v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 16));
    else
      v7 = -2147220989;
  }
  else
  {
    v7 = -2147467261;
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000cfd0  push    rbx
0x18000cfd2  push    rbp
0x18000cfd3  push    rsi
0x18000cfd4  push    rdi
0x18000cfd5  sub     rsp, 28h
0x18000cfd9  lea     rbp, [rcx+0D8h]
0x18000cfe0  mov     rdi, rcx
0x18000cfe3  mov     rcx, rbp; lpCriticalSection
0x18000cfe6  mov     rsi, r8
0x18000cfe9  mov     ebx, edx
0x18000cfeb  call    cs:__imp_EnterCriticalSection
0x18000cff1  cmp     ebx, 1
0x18000cff4  jb      short loc_18000CFFD
0x18000cff6  mov     ebx, 80040201h
0x18000cffb  jmp     short loc_18000D025
0x18000cffd  test    rsi, rsi
0x18000d000  jnz     short loc_18000D009
0x18000d002  mov     ebx, 80004003h
0x18000d007  jmp     short loc_18000D025
0x18000d009  cmp     dword ptr [rdi+8], 0
0x18000d00d  jnz     short loc_18000D016
0x18000d00f  mov     ebx, 80040203h
0x18000d014  jmp     short loc_18000D025
0x18000d016  lea     rdx, [rdi+10h]; pmtSrc
0x18000d01a  mov     rcx, rsi; pmtDest
0x18000d01d  call    cs:__imp_MoCopyMediaType
0x18000d023  mov     ebx, eax
0x18000d025  mov     rcx, rbp; lpCriticalSection
0x18000d028  call    cs:__imp_LeaveCriticalSection
0x18000d02e  mov     eax, ebx
0x18000d030  add     rsp, 28h
0x18000d034  pop     rdi
0x18000d035  pop     rsi
0x18000d036  pop     rbp
0x18000d037  pop     rbx
0x18000d038  retn
```
