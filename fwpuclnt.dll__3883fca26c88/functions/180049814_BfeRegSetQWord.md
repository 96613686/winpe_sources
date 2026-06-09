# BfeRegSetQWord

- ea: `0x180049814`
- end: `0x1800498a4`
- name: `BfeRegSetQWord`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001df08`

## callees

- `0x1800030a8`
- `0x1800034e0`
- `0x180007e38`
- `0x180012bd0`
- `0x180049814`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049850`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049850`

## string_xrefs

- `0x180049863`: `RegSetValueExW`
- `0x18004987e`: `BfeRegSetQWord`

## pseudocode

```c
__int64 __fastcall BfeRegSetQWord(HKEY a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  unsigned int v5; // eax
  __int64 v6; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)Data = a4;
  v4 = 0;
  v5 = RegSetValueExW(a1, L"MatchAnyKeyword", 0, 0xBu, Data, 8u);
  if ( v5 )
    v4 = WfpReportSysErrorAsWinError(v6, "RegSetValueExW", v5);
  BfeRegCloseKey(0);
  if ( v4 )
    WfpReportError(v4, "BfeRegSetQWord");
  return v4;
}

```

## disassembly

```asm
0x180049814  push    rbx
0x180049816  sub     rsp, 40h
0x18004981a  mov     rax, cs:__security_cookie
0x180049821  xor     rax, rsp
0x180049824  mov     [rsp+48h+var_10], rax
0x180049829  mov     qword ptr [rsp+48h+Data], r9
0x18004982e  lea     rax, [rsp+48h+Data]
0x180049833  xor     ebx, ebx
0x180049835  mov     [rsp+48h+cbData], 8; cbData
0x18004983d  xor     r8d, r8d; Reserved
0x180049840  mov     [rsp+48h+lpData], rax; lpData
0x180049845  lea     rdx, ValueName; "MatchAnyKeyword"
0x18004984c  lea     r9d, [rbx+0Bh]; dwType
0x180049850  call    cs:__imp_RegSetValueExW
0x180049857  nop     dword ptr [rax+rax+00h]
0x18004985c  test    eax, eax
0x18004985e  jz      short loc_180049872
0x180049860  mov     r8d, eax
0x180049863  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x18004986a  call    WfpReportSysErrorAsWinError
0x18004986f  mov     rbx, rax
0x180049872  xor     ecx, ecx
0x180049874  call    BfeRegCloseKey
0x180049879  test    rbx, rbx
0x18004987c  jz      short loc_18004988D
0x18004987e  lea     rdx, aBferegsetqword; "BfeRegSetQWord"
0x180049885  mov     rcx, rbx
0x180049888  call    WfpReportError
0x18004988d  mov     rax, rbx
0x180049890  mov     rcx, [rsp+48h+var_10]
0x180049895  xor     rcx, rsp; StackCookie
0x180049898  call    __security_check_cookie
0x18004989d  add     rsp, 40h
0x1800498a1  pop     rbx
0x1800498a2  retn
```
