# CSemExclusive::CSemExclusive(ulong)

- ea: `0x140002fac`
- end: `0x140003056`
- name: `??0CSemExclusive@@QEAA@K@Z`
- size: `170`
- prototype: `CSemExclusive *__fastcall(CSemExclusive *this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010a0`
- `0x1400010d0`
- `0x140001100`
- `0x140001130`
- `0x140001180`
- `0x1400011b0`

## callees

- `0x140002fac`
- `0x140004640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fd9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140002fcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140002fcf`

## string_xrefs

- `0x140003003`: `com\complus\src\shared\util\utsem.cpp`

## pseudocode

```c
CSemExclusive *__fastcall CSemExclusive::CSemExclusive(CSemExclusive *this)
{
  signed int LastError; // eax
  signed int v4; // [rsp+20h] [rbp-38h] BYREF
  __int16 v5; // [rsp+24h] [rbp-34h]
  int v6; // [rsp+28h] [rbp-30h]
  const unsigned __int16 *v7; // [rsp+30h] [rbp-28h]
  __int64 v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+40h] [rbp-18h]
  int v10; // [rsp+48h] [rbp-10h]
  int v11; // [rsp+4Ch] [rbp-Ch]

  *((_DWORD *)this + 12) = 0;
  *(_QWORD *)this = &CSemExclusive::`vftable';
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8), 0x1F4u) )
  {
    *((_DWORD *)this + 12) = 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
    v6 = -1073606063;
    v5 = 21;
    v7 = L"InitializeCriticalSectionAndSpinCount";
    v8 = 0;
    v9 = 0;
    v11 = 1;
    v10 = 1;
    CError::WriteToLog(
      (CError *)&v4,
      L"com\\complus\\src\\shared\\util\\utsem.cpp",
      0x94u,
      L"InitializeCriticalSectionAndSpinCount");
  }
  return this;
}

```

## disassembly

```asm
0x140002fac  push    rbx
0x140002fae  sub     rsp, 50h
0x140002fb2  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x140002fb9  mov     dword ptr [rcx+30h], 0
0x140002fc0  mov     [rcx], rax
0x140002fc3  mov     rbx, rcx
0x140002fc6  add     rcx, 8; lpCriticalSection
0x140002fca  mov     edx, 1F4h; dwSpinCount
0x140002fcf  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140002fd5  test    eax, eax
0x140002fd7  jnz     short loc_140003046
0x140002fd9  call    cs:__imp_GetLastError
0x140002fdf  test    eax, eax
0x140002fe1  jle     short loc_140002FEB
0x140002fe3  movzx   eax, ax
0x140002fe6  or      eax, 80070000h
0x140002feb  mov     [rsp+58h+var_38], eax
0x140002fef  lea     r9, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x140002ff6  mov     eax, 15h
0x140002ffb  mov     [rsp+58h+var_30], 0C0021251h
0x140003003  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x14000300a  mov     [rsp+58h+var_34], ax
0x14000300f  lea     rcx, [rsp+58h+var_38]; this
0x140003014  mov     [rsp+58h+var_28], r9
0x140003019  mov     [rsp+58h+var_20], 0
0x140003022  lea     r8d, [rax+7Fh]; unsigned int
0x140003026  mov     [rsp+58h+var_18], 0
0x14000302f  mov     [rsp+58h+var_C], 1
0x140003037  mov     [rsp+58h+var_10], 1
0x14000303f  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x140003044  jmp     short loc_14000304D
0x140003046  mov     dword ptr [rbx+30h], 1
0x14000304d  mov     rax, rbx
0x140003050  add     rsp, 50h
0x140003054  pop     rbx
0x140003055  retn
```
