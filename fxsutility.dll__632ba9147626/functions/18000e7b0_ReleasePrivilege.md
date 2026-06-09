# ReleasePrivilege

- ea: `0x18000e7b0`
- end: `0x18000e8a1`
- name: `ReleasePrivilege`
- size: `241`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180013ce0`
- `0x180013fa0`
- `0x180014200`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000e7b0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000e84f`
- `KERNEL32!CloseHandle` at `0x18000e84f`
- `KERNEL32!GetLastError` at `0x18000e822`
- `KERNEL32!GetLastError` at `0x18000e871`
- `KERNEL32!GetLastError` at `0x18000e822`
- `KERNEL32!GetLastError` at `0x18000e871`
- `ADVAPI32!SetThreadToken` at `0x18000e800`
- `ADVAPI32!SetThreadToken` at `0x18000e800`

## pseudocode

```c
void __fastcall ReleasePrivilege(HANDLE hObject)
{
  DWORD LastError; // eax
  DWORD v3; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
  }
  if ( hObject != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, hObject)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
    }
    if ( hObject
      && !CloseHandle(hObject)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v3);
    }
  }
}

```

## disassembly

```asm
0x18000e7b0  mov     [rsp+arg_0], rbx
0x18000e7b5  push    rsi
0x18000e7b6  sub     rsp, 20h
0x18000e7ba  mov     rbx, rcx
0x18000e7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7c4  lea     rsi, WPP_GLOBAL_Control
0x18000e7cb  cmp     rcx, rsi
0x18000e7ce  jz      short loc_18000E7F1
0x18000e7d0  test    byte ptr [rcx+1Ch], 2
0x18000e7d4  jz      short loc_18000E7F1
0x18000e7d6  cmp     byte ptr [rcx+19h], 5
0x18000e7da  jb      short loc_18000E7F1
0x18000e7dc  mov     rcx, [rcx+10h]
0x18000e7e0  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x18000e7e7  mov     edx, 0Ch
0x18000e7ec  call    WPP_SF_
0x18000e7f1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e7f5  jz      loc_18000E896
0x18000e7fb  mov     rdx, rbx; Token
0x18000e7fe  xor     ecx, ecx; Thread
0x18000e800  call    cs:__imp_SetThreadToken
0x18000e806  test    eax, eax
0x18000e808  jnz     short loc_18000E847
0x18000e80a  mov     rax, cs:WPP_GLOBAL_Control
0x18000e811  cmp     rax, rsi
0x18000e814  jz      short loc_18000E847
0x18000e816  test    byte ptr [rax+1Ch], 2
0x18000e81a  jz      short loc_18000E847
0x18000e81c  cmp     byte ptr [rax+19h], 2
0x18000e820  jb      short loc_18000E847
0x18000e822  call    cs:__imp_GetLastError
0x18000e828  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e82f  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x18000e836  mov     edx, 0Dh
0x18000e83b  mov     r9d, eax
0x18000e83e  mov     rcx, [rcx+10h]
0x18000e842  call    WPP_SF_d
0x18000e847  test    rbx, rbx
0x18000e84a  jz      short loc_18000E896
0x18000e84c  mov     rcx, rbx; hObject
0x18000e84f  call    cs:__imp_CloseHandle
0x18000e855  test    eax, eax
0x18000e857  jnz     short loc_18000E896
0x18000e859  mov     rax, cs:WPP_GLOBAL_Control
0x18000e860  cmp     rax, rsi
0x18000e863  jz      short loc_18000E896
0x18000e865  test    byte ptr [rax+1Ch], 2
0x18000e869  jz      short loc_18000E896
0x18000e86b  cmp     byte ptr [rax+19h], 2
0x18000e86f  jb      short loc_18000E896
0x18000e871  call    cs:__imp_GetLastError
0x18000e877  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e87e  lea     r8, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x18000e885  mov     edx, 0Eh
0x18000e88a  mov     r9d, eax
0x18000e88d  mov     rcx, [rcx+10h]
0x18000e891  call    WPP_SF_d
0x18000e896  mov     rbx, [rsp+28h+arg_0]
0x18000e89b  add     rsp, 20h
0x18000e89f  pop     rsi
0x18000e8a0  retn
```
