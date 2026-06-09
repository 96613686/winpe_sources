# RtpOneTimeThreadInit(void)

- ea: `0x180014458`
- end: `0x1800144c2`
- name: `?RtpOneTimeThreadInit@@YAJXZ`
- size: `106`
- prototype: `__int64(void)`
- caller_count: `44`
- callee_count: `4`
- tags: ``

## callers

- `0x1800055e0`
- `0x180005680`
- `0x180008490`
- `0x180008550`
- `0x180009b20`
- `0x18000a120`
- `0x18000a8b8`
- `0x18000ac70`
- `0x18000acd0`
- `0x18000ad40`
- `0x18000adf0`
- `0x18000af00`
- `0x18000e200`
- `0x18000e520`
- `0x18000e590`
- `0x18000ec20`
- `0x18000ee60`
- `0x18000f250`
- `0x18000f600`
- `0x18000f6a0`
- `0x18000f7a0`
- `0x18000f990`
- `0x18000fa60`
- `0x18000fb60`
- `0x18000fcf0`
- `0x180010260`
- `0x180010300`
- `0x1800106c0`
- `0x180010b10`
- `0x180010c70`
- `0x180010f00`
- `0x180011050`
- `0x180011200`
- `0x1800112b0`
- `0x1800114c0`
- `0x1800120b0`
- `0x180012700`
- `0x180012cb0`
- `0x180015a80`
- `0x180015c30`
- `0x180017728`
- `0x180017c30`
- `0x180018800`
- `0x180019530`

## callees

- `0x180013bbc`
- `0x180013e88`
- `0x1800140e4`
- `0x180014458`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180014488`
- `KERNEL32!LeaveCriticalSection` at `0x1800144a0`
- `KERNEL32!LeaveCriticalSection` at `0x180014488`
- `KERNEL32!LeaveCriticalSection` at `0x1800144a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 RtpOneTimeThreadInit(void)
{
  __int64 result; // rax
  signed int v1; // eax
  int v2; // eax
  const bad_win32_error *v3; // [rsp+20h] [rbp-18h] BYREF
  const bad_hresult *v4; // [rsp+28h] [rbp-10h] BYREF
  unsigned int v5; // [rsp+40h] [rbp+8h]
  unsigned int v6; // [rsp+40h] [rbp+8h]

  try
  {
    if ( !byte_18003DD19 )
    {
      CCriticalSection::Lock((CCriticalSection *)&stru_18003D1C8);
      if ( !byte_18003DD19 )
      {
        OneTimeInit();
        byte_18003DD19 = 1;
      }
      LeaveCriticalSection(&stru_18003D1C8);
    }
    OneTimeThreadInit();
    result = 0;
  }
  catch ( const bad_win32_error *v3 )
  {
    v1 = (*(__int64 (__fastcall **)(const bad_win32_error *))(*(_QWORD *)v3 + 16LL))(v3);
    if ( v1 > 0 )
      v1 = (unsigned __int16)v1 | 0x80070000;
    v5 = v1;
    if ( v1 < 0 )
      LogMsgHR(v1, (wchar_t *)L"rt/rtmain", 0x461u);
    return v5;
  }
  catch ( const bad_hresult *v4 )
  {
    v2 = (*(__int64 (__fastcall **)(const bad_hresult *))(*(_QWORD *)v4 + 16LL))(v4);
    v6 = v2;
    if ( v2 < 0 )
      LogMsgHR(v2, (wchar_t *)L"rt/rtmain", 0x462u);
    return v6;
  }
  catch ( std::bad_alloc )
  {
    LogMsgHR(-1072824281, (wchar_t *)L"rt/rtmain", 0x463u);
    return 3222143015LL;
  }
  catch ( exception )
  {
    LogMsgHR(-1072824281, (wchar_t *)L"rt/rtmain", 0x464u);
    return 3222143015LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014458  push    rbx
0x18001445a  sub     rsp, 30h
0x18001445e  cmp     cs:byte_18003DD19, 0
0x180014465  jnz     short loc_1800144A7
0x180014467  lea     rbx, stru_18003D1C8
0x18001446e  mov     [rsp+38h+arg_0], rbx
0x180014473  mov     rcx, rbx; this
0x180014476  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001447b  nop
0x18001447c  cmp     cs:byte_18003DD19, 0
0x180014483  jz      short loc_180014491
0x180014485  mov     rcx, rbx; lpCriticalSection
0x180014488  call    cs:__imp_LeaveCriticalSection
0x18001448e  nop
0x18001448f  jmp     short loc_1800144A7
0x180014491  call    OneTimeInit
0x180014496  mov     cs:byte_18003DD19, 1
0x18001449d  mov     rcx, rbx; lpCriticalSection
0x1800144a0  call    cs:__imp_LeaveCriticalSection
0x1800144a6  nop
0x1800144a7  call    OneTimeThreadInit
0x1800144ac  xor     eax, eax
0x1800144ae  jmp     short loc_1800144BB
0x1800144b0  mov     eax, dword ptr [rsp+38h+arg_0]
0x1800144b4  jmp     short loc_1800144BB
0x1800144b6  mov     eax, 0C00E0027h
0x1800144bb  add     rsp, 30h
0x1800144bf  pop     rbx
0x1800144c0  retn
```
