# CSemExclusive::CSemExclusive(ulong)

- ea: `0x18000e64c`
- end: `0x18000e6f6`
- name: `??0CSemExclusive@@QEAA@K@Z`
- size: `170`
- prototype: `CSemExclusive *__fastcall(CSemExclusive *this)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010d0`
- `0x180001100`
- `0x180001130`
- `0x180001160`
- `0x1800011b0`
- `0x1800011e0`
- `0x1800051f8`
- `0x180005d78`
- `0x180008aa0`
- `0x180009e6c`
- `0x18000c918`

## callees

- `0x18000e64c`
- `0x18000fca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e679`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000e66f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000e66f`

## string_xrefs

- `0x18000e6a3`: `com\complus\src\shared\util\utsem.cpp`

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
0x18000e64c  push    rbx
0x18000e64e  sub     rsp, 50h
0x18000e652  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18000e659  mov     dword ptr [rcx+30h], 0
0x18000e660  mov     [rcx], rax
0x18000e663  mov     rbx, rcx
0x18000e666  add     rcx, 8; lpCriticalSection
0x18000e66a  mov     edx, 1F4h; dwSpinCount
0x18000e66f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000e675  test    eax, eax
0x18000e677  jnz     short loc_18000E6E6
0x18000e679  call    cs:__imp_GetLastError
0x18000e67f  test    eax, eax
0x18000e681  jle     short loc_18000E68B
0x18000e683  movzx   eax, ax
0x18000e686  or      eax, 80070000h
0x18000e68b  mov     [rsp+58h+var_38], eax
0x18000e68f  lea     r9, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x18000e696  mov     eax, 15h
0x18000e69b  mov     [rsp+58h+var_30], 0C0021251h
0x18000e6a3  lea     rdx, aComComplusSrcS; "com\\complus\\src\\shared\\util\\utsem."...
0x18000e6aa  mov     [rsp+58h+var_34], ax
0x18000e6af  lea     rcx, [rsp+58h+var_38]; this
0x18000e6b4  mov     [rsp+58h+var_28], r9
0x18000e6b9  mov     [rsp+58h+var_20], 0
0x18000e6c2  lea     r8d, [rax+7Fh]; unsigned int
0x18000e6c6  mov     [rsp+58h+var_18], 0
0x18000e6cf  mov     [rsp+58h+var_C], 1
0x18000e6d7  mov     [rsp+58h+var_10], 1
0x18000e6df  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000e6e4  jmp     short loc_18000E6ED
0x18000e6e6  mov     dword ptr [rbx+30h], 1
0x18000e6ed  mov     rax, rbx
0x18000e6f0  add     rsp, 50h
0x18000e6f4  pop     rbx
0x18000e6f5  retn
```
