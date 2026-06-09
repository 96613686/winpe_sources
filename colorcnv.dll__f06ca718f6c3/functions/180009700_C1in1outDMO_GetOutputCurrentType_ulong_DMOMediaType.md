# C1in1outDMO::GetOutputCurrentType(ulong,_DMOMediaType *)

- ea: `0x180009700`
- end: `0x180009769`
- name: `?GetOutputCurrentType@C1in1outDMO@@UEAAJKPEAU_DMOMediaType@@@Z`
- size: `105`
- prototype: `int(C1in1outDMO *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180009700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000971b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000971b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009758`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009758`
- `msdmo!MoCopyMediaType` at `0x18000974d`
- `msdmo!MoCopyMediaType` at `0x18000974d`

## pseudocode

```c
__int64 __fastcall C1in1outDMO::GetOutputCurrentType(C1in1outDMO *this, int a2, DMO_MEDIA_TYPE *a3)
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
    if ( *((_DWORD *)this + 3) )
      v7 = MoCopyMediaType(a3, (const DMO_MEDIA_TYPE *)((char *)this + 104));
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
0x180009700  push    rbx
0x180009702  push    rbp
0x180009703  push    rsi
0x180009704  push    rdi
0x180009705  sub     rsp, 28h
0x180009709  lea     rbp, [rcx+0D8h]
0x180009710  mov     rdi, rcx
0x180009713  mov     rcx, rbp; lpCriticalSection
0x180009716  mov     rsi, r8
0x180009719  mov     ebx, edx
0x18000971b  call    cs:__imp_EnterCriticalSection
0x180009721  cmp     ebx, 1
0x180009724  jb      short loc_18000972D
0x180009726  mov     ebx, 80040201h
0x18000972b  jmp     short loc_180009755
0x18000972d  test    rsi, rsi
0x180009730  jnz     short loc_180009739
0x180009732  mov     ebx, 80004003h
0x180009737  jmp     short loc_180009755
0x180009739  cmp     dword ptr [rdi+0Ch], 0
0x18000973d  jnz     short loc_180009746
0x18000973f  mov     ebx, 80040203h
0x180009744  jmp     short loc_180009755
0x180009746  lea     rdx, [rdi+68h]; pmtSrc
0x18000974a  mov     rcx, rsi; pmtDest
0x18000974d  call    cs:__imp_MoCopyMediaType
0x180009753  mov     ebx, eax
0x180009755  mov     rcx, rbp; lpCriticalSection
0x180009758  call    cs:__imp_LeaveCriticalSection
0x18000975e  mov     eax, ebx
0x180009760  add     rsp, 28h
0x180009764  pop     rdi
0x180009765  pop     rsi
0x180009766  pop     rbp
0x180009767  pop     rbx
0x180009768  retn
```
