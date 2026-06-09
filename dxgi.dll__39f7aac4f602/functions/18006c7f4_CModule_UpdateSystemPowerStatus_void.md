# CModule::UpdateSystemPowerStatus(void)

- ea: `0x18006c7f4`
- end: `0x18006c849`
- name: `?UpdateSystemPowerStatus@CModule@@QEAAJXZ`
- size: `85`
- prototype: `int(CModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800650dc`
- `0x18008eecc`
- `0x18009d400`

## callees

- `0x180067d2c`
- `0x18006c7f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c80b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c80b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18006c801`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18006c801`

## string_xrefs

- `0x18006c829`: `onecoreuap\windows\directx\dxg\dxgi\dll\dxgi.cpp`

## pseudocode

```c
__int64 __fastcall CModule::UpdateSystemPowerStatus(CModule *this)
{
  signed int LastError; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( GetSystemPowerStatus((LPSYSTEM_POWER_STATUS)((char *)this + 1036)) )
    return 0;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBDE,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\dxgi.cpp",
      (const char *)v2,
      v4);
  return v2;
}

```

## disassembly

```asm
0x18006c7f4  push    rbx; int
0x18006c7f6  sub     rsp, 20h
0x18006c7fa  add     rcx, 40Ch; lpSystemPowerStatus
0x18006c801  call    cs:__imp_GetSystemPowerStatus
0x18006c807  test    eax, eax
0x18006c809  jnz     short loc_18006C841
0x18006c80b  call    cs:__imp_GetLastError
0x18006c811  mov     ebx, eax
0x18006c813  test    eax, eax
0x18006c815  jle     short loc_18006C820
0x18006c817  movzx   ebx, ax
0x18006c81a  or      ebx, 80070000h
0x18006c820  test    ebx, ebx
0x18006c822  jns     short loc_18006C83D
0x18006c824  mov     rcx, [rsp+28h]; this
0x18006c829  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18006c830  mov     r9d, ebx; char *
0x18006c833  mov     edx, 0BDEh; void *
0x18006c838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c83d  mov     eax, ebx
0x18006c83f  jmp     short loc_18006C843
0x18006c841  xor     eax, eax
0x18006c843  add     rsp, 20h
0x18006c847  pop     rbx
0x18006c848  retn
```
