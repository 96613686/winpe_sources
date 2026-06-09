# AllocCallObj

- ea: `0x1800026b8`
- end: `0x180002744`
- name: `AllocCallObj`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ba8`
- `0x1800063b0`

## callees

- `0x1800026b8`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180002704`
- `KERNEL32!LocalAlloc` at `0x180002704`
- `KERNEL32!LeaveCriticalSection` at `0x18000272e`
- `KERNEL32!LeaveCriticalSection` at `0x18000272e`
- `KERNEL32!EnterCriticalSection` at `0x1800026d8`
- `KERNEL32!EnterCriticalSection` at `0x1800026d8`

## pseudocode

```c
HLOCAL AllocCallObj()
{
  HLOCAL v0; // rbx

  if ( !(_DWORD)Size )
    LODWORD(Size) = 80;
  EnterCriticalSection(&stru_18000E388);
  v0 = qword_18000E380;
  if ( qword_18000E380 )
  {
    qword_18000E380 = *(HLOCAL *)qword_18000E380;
  }
  else
  {
    v0 = LocalAlloc(0x40u, 0x50u);
    if ( !v0 )
      TspLog(1, "AllocCallObj: failed to alloc a call obj");
  }
  LeaveCriticalSection(&stru_18000E388);
  return v0;
}

```

## disassembly

```asm
0x1800026b8  push    rbx
0x1800026ba  sub     rsp, 20h
0x1800026be  cmp     cs:Size, 0
0x1800026c5  jnz     short loc_1800026D1
0x1800026c7  mov     cs:Size, 50h ; 'P'
0x1800026d1  lea     rcx, stru_18000E388; lpCriticalSection
0x1800026d8  call    cs:__imp_EnterCriticalSection
0x1800026df  nop     dword ptr [rax+rax+00h]
0x1800026e4  mov     rbx, cs:qword_18000E380
0x1800026eb  test    rbx, rbx
0x1800026ee  jz      short loc_1800026FC
0x1800026f0  mov     rax, [rbx]
0x1800026f3  mov     cs:qword_18000E380, rax
0x1800026fa  jmp     short loc_180002727
0x1800026fc  mov     edx, 50h ; 'P'; uBytes
0x180002701  lea     ecx, [rdx-10h]; uFlags
0x180002704  call    cs:__imp_LocalAlloc
0x18000270b  nop     dword ptr [rax+rax+00h]
0x180002710  mov     rbx, rax
0x180002713  test    rax, rax
0x180002716  jnz     short loc_180002727
0x180002718  lea     rdx, aAlloccallobjFa; "AllocCallObj: failed to alloc a call ob"...
0x18000271f  lea     ecx, [rax+1]
0x180002722  call    TspLog
0x180002727  lea     rcx, stru_18000E388; lpCriticalSection
0x18000272e  call    cs:__imp_LeaveCriticalSection
0x180002735  nop     dword ptr [rax+rax+00h]
0x18000273a  mov     rax, rbx
0x18000273d  add     rsp, 20h
0x180002741  pop     rbx
0x180002742  retn
```
