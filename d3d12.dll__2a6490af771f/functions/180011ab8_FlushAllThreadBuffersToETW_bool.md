# FlushAllThreadBuffersToETW(bool)

- ea: `0x180011ab8`
- end: `0x180011b35`
- name: `?FlushAllThreadBuffersToETW@@YAX_N@Z`
- size: `125`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011cd0`

## callees

- `0x180011ab8`
- `0x180011b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011b2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011ae6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011ae6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011ad4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011ad4`

## pseudocode

```c
void __fastcall FlushAllThreadBuffersToETW()
{
  LARGE_INTEGER v0; // rsi
  unsigned int v1; // ecx
  __int64 v2; // rdi
  _QWORD *i; // rbx
  __int64 v4; // rdx
  LARGE_INTEGER v5; // [rsp+38h] [rbp+10h] BYREF

  v5.QuadPart = 0;
  QueryPerformanceCounter(&v5);
  v0 = v5;
  AcquireSRWLockExclusive(&SRWLock);
  v2 = qword_18001E8A0;
  for ( i = *(_QWORD **)qword_18001E8A0; i != (_QWORD *)v2; i = (_QWORD *)*i )
  {
    v4 = i[2];
    if ( v4 )
    {
      if ( !*(_DWORD *)(v4 + 20) )
      {
        *(LARGE_INTEGER *)(v4 + 40) = v0;
        PIXRecordTimingCaptureBlob(v1, (unsigned __int8 *)v4);
      }
    }
  }
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180011ab8  mov     rax, rsp
0x180011abb  mov     [rax+8], rbx
0x180011abf  mov     [rax+18h], rsi
0x180011ac3  push    rdi
0x180011ac4  sub     rsp, 20h
0x180011ac8  lea     rcx, [rax+10h]; lpPerformanceCount
0x180011acc  mov     qword ptr [rax+10h], 0
0x180011ad4  call    cs:__imp_QueryPerformanceCounter
0x180011ada  mov     rsi, [rsp+28h+arg_8]
0x180011adf  lea     rcx, SRWLock; SRWLock
0x180011ae6  call    cs:__imp_AcquireSRWLockExclusive
0x180011aec  mov     rdi, cs:qword_18001E8A0
0x180011af3  mov     rbx, [rdi]
0x180011af6  cmp     rbx, rdi
0x180011af9  jz      short loc_180011B18
0x180011afb  mov     rdx, [rbx+10h]; unsigned __int8 *
0x180011aff  test    rdx, rdx
0x180011b02  jz      short loc_180011B13
0x180011b04  cmp     dword ptr [rdx+14h], 0
0x180011b08  jnz     short loc_180011B13
0x180011b0a  mov     [rdx+28h], rsi
0x180011b0e  call    ?PIXRecordTimingCaptureBlob@@YAXIPEAE@Z; PIXRecordTimingCaptureBlob(uint,uchar *)
0x180011b13  mov     rbx, [rbx]
0x180011b16  jmp     short loc_180011AF6
0x180011b18  lea     rcx, SRWLock
0x180011b1f  mov     rbx, [rsp+28h+arg_0]
0x180011b24  mov     rsi, [rsp+28h+arg_10]
0x180011b29  add     rsp, 20h
0x180011b2d  pop     rdi
0x180011b2e  jmp     cs:__imp_ReleaseSRWLockExclusive
```
