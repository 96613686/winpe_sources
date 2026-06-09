# DhcpUndoRequestParams

- ea: `0x18000beb0`
- end: `0x18000bf6f`
- name: `DhcpUndoRequestParams`
- size: `191`
- prototype: `DWORD __stdcall(DWORD Flags, LPVOID Reserved, LPWSTR AdapterName, LPWSTR RequestIdStr)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002760`
- `0x180006300`
- `0x18000beb0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000becd`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000becd`

## pseudocode

```c
DWORD __stdcall DhcpUndoRequestParams(DWORD Flags, LPVOID Reserved, LPWSTR AdapterName, LPWSTR RequestIdStr)
{
  int v5; // edi
  LPWSTR CommandLineW; // rax
  int v9; // ecx
  DWORD v10; // ebx

  v5 = (int)AdapterName;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(v9, 119, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v5, (__int64)CommandLineW);
  }
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v10 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 120, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else if ( Flags || Reserved || !RequestIdStr )
  {
    v10 = 87;
  }
  else
  {
    v10 = DhcpDelPersistentRequestParams(v5, RequestIdStr);
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 121, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v5, v10);
  return v10;
}

```

## disassembly

```asm
0x18000beb0  push    rbx
0x18000beb2  push    rbp
0x18000beb3  push    rsi
0x18000beb4  push    rdi
0x18000beb5  sub     rsp, 38h
0x18000beb9  mov     rbx, r9
0x18000bebc  mov     rdi, r8
0x18000bebf  mov     rsi, rdx
0x18000bec2  mov     ebp, ecx
0x18000bec4  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000becb  jz      short loc_18000BEEC
0x18000becd  call    cs:__imp_GetCommandLineW
0x18000bed3  mov     edx, 77h ; 'w'
0x18000bed8  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bedf  mov     r9, rdi
0x18000bee2  mov     [rsp+58h+var_38], rax
0x18000bee7  call    WPP_SF_SS
0x18000beec  call    DhcpIsFSEGuestSystem
0x18000bef1  test    eax, eax
0x18000bef3  jnz     short loc_18000BF19
0x18000bef5  test    ebp, ebp
0x18000bef7  jz      short loc_18000BF00
0x18000bef9  mov     ebx, 57h ; 'W'
0x18000befe  jmp     short loc_18000BF3E
0x18000bf00  test    rsi, rsi
0x18000bf03  jnz     short loc_18000BEF9
0x18000bf05  test    rbx, rbx
0x18000bf08  jz      short loc_18000BEF9
0x18000bf0a  mov     rdx, rbx
0x18000bf0d  mov     rcx, rdi
0x18000bf10  call    DhcpDelPersistentRequestParams
0x18000bf15  mov     ebx, eax
0x18000bf17  jmp     short loc_18000BF3E
0x18000bf19  mov     ebx, 32h ; '2'
0x18000bf1e  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000bf25  jz      short loc_18000BF3E
0x18000bf27  lea     edx, [rbx+46h]
0x18000bf2a  mov     ecx, 401h
0x18000bf2f  mov     r9d, ebx
0x18000bf32  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bf39  call    WPP_SF_d
0x18000bf3e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bf45  jz      short loc_18000BF64
0x18000bf47  mov     edx, 79h ; 'y'
0x18000bf4c  mov     dword ptr [rsp+58h+var_38], ebx
0x18000bf50  mov     ecx, 404h
0x18000bf55  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bf5c  mov     r9, rdi
0x18000bf5f  call    WPP_SF_SD
0x18000bf64  mov     eax, ebx
0x18000bf66  add     rsp, 38h
0x18000bf6a  pop     rdi
0x18000bf6b  pop     rsi
0x18000bf6c  pop     rbp
0x18000bf6d  pop     rbx
0x18000bf6e  retn
```
