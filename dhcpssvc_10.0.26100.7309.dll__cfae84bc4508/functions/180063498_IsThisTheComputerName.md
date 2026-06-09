# IsThisTheComputerName

- ea: `0x180063498`
- end: `0x18006362c`
- name: `IsThisTheComputerName`
- size: `404`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180063368`

## callees

- `0x180002854`
- `0x1800058cc`
- `0x180063498`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180063574`
- `msvcrt!_wcsicmp` at `0x180063615`
- `msvcrt!_wcsicmp` at `0x180063574`
- `msvcrt!_wcsicmp` at `0x180063615`
- `KERNEL32!GetComputerNameExW` at `0x18006352f`
- `KERNEL32!GetComputerNameExW` at `0x18006359f`
- `KERNEL32!GetComputerNameExW` at `0x18006352f`
- `KERNEL32!GetComputerNameExW` at `0x18006359f`
- `KERNEL32!GetLastError` at `0x18006353f`
- `KERNEL32!GetLastError` at `0x1800635af`
- `KERNEL32!GetLastError` at `0x18006353f`
- `KERNEL32!GetLastError` at `0x1800635af`

## pseudocode

```c
__int64 __fastcall IsThisTheComputerName(wchar_t *String1)
{
  wchar_t *v1; // rbx
  DWORD LastError; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  DWORD nSize[4]; // [rsp+20h] [rbp-288h] BYREF
  WCHAR Buffer[304]; // [rsp+30h] [rbp-278h] BYREF

  v1 = String1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids, String1);
  if ( !v1 || !*v1 )
    return 0;
  if ( *v1 == 92 && v1[1] == 92 )
    v1 += 2;
  nSize[0] = 300;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return 0;
    v4 = 25;
    goto LABEL_18;
  }
  if ( _wcsicmp(v1, Buffer) )
  {
    nSize[0] = 300;
    if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, nSize) )
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return 0;
      v4 = 26;
LABEL_18:
      WPP_SF_D(v3[2], v4, &WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids, LastError);
      return 0;
    }
    if ( _wcsicmp(v1, Buffer) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180063498  mov     [rsp+arg_8], rbx
0x18006349d  mov     [rsp+arg_10], rsi
0x1800634a2  push    rdi
0x1800634a3  sub     rsp, 2A0h
0x1800634aa  mov     rax, cs:__security_cookie
0x1800634b1  xor     rax, rsp
0x1800634b4  mov     [rsp+2A8h+var_18], rax
0x1800634bc  mov     rbx, rcx
0x1800634bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800634c6  lea     rsi, WPP_GLOBAL_Control
0x1800634cd  cmp     rcx, rsi
0x1800634d0  jz      short loc_1800634F3
0x1800634d2  test    dword ptr [rcx+1Ch], 8000h
0x1800634d9  jz      short loc_1800634F3
0x1800634db  mov     rcx, [rcx+10h]
0x1800634df  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x1800634e6  mov     edx, 18h
0x1800634eb  mov     r9, rbx
0x1800634ee  call    WPP_SF_S
0x1800634f3  xor     edi, edi
0x1800634f5  test    rbx, rbx
0x1800634f8  jz      loc_1800635E5
0x1800634fe  cmp     [rbx], di
0x180063501  jz      loc_1800635E5
0x180063507  cmp     word ptr [rbx], 5Ch ; '\'
0x18006350b  jnz     short loc_180063518
0x18006350d  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180063512  jnz     short loc_180063518
0x180063514  add     rbx, 4
0x180063518  lea     r8, [rsp+2A8h+nSize]; nSize
0x18006351d  mov     [rsp+2A8h+nSize], 12Ch
0x180063525  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x18006352a  mov     ecx, 1; NameType
0x18006352f  call    cs:__imp_GetComputerNameExW
0x180063536  nop     dword ptr [rax+rax+00h]
0x18006353b  test    eax, eax
0x18006353d  jnz     short loc_18006356C
0x18006353f  call    cs:__imp_GetLastError
0x180063546  nop     dword ptr [rax+rax+00h]
0x18006354b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063552  cmp     rcx, rsi
0x180063555  jz      loc_1800635E5
0x18006355b  test    byte ptr [rcx+1Ch], 10h
0x18006355f  jz      loc_1800635E5
0x180063565  mov     edx, 19h
0x18006356a  jmp     short loc_1800635D2
0x18006356c  lea     rdx, [rsp+2A8h+Buffer]; String2
0x180063571  mov     rcx, rbx; String1
0x180063574  call    cs:__imp__wcsicmp
0x18006357b  nop     dword ptr [rax+rax+00h]
0x180063580  test    eax, eax
0x180063582  jz      loc_180063625
0x180063588  lea     r8, [rsp+2A8h+nSize]; nSize
0x18006358d  mov     [rsp+2A8h+nSize], 12Ch
0x180063595  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x18006359a  mov     ecx, 3; NameType
0x18006359f  call    cs:__imp_GetComputerNameExW
0x1800635a6  nop     dword ptr [rax+rax+00h]
0x1800635ab  test    eax, eax
0x1800635ad  jnz     short loc_18006360D
0x1800635af  call    cs:__imp_GetLastError
0x1800635b6  nop     dword ptr [rax+rax+00h]
0x1800635bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800635c2  cmp     rcx, rsi
0x1800635c5  jz      short loc_1800635E5
0x1800635c7  test    byte ptr [rcx+1Ch], 10h
0x1800635cb  jz      short loc_1800635E5
0x1800635cd  mov     edx, 1Ah
0x1800635d2  mov     rcx, [rcx+10h]
0x1800635d6  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x1800635dd  mov     r9d, eax
0x1800635e0  call    WPP_SF_D
0x1800635e5  xor     eax, eax
0x1800635e7  mov     rcx, [rsp+2A8h+var_18]
0x1800635ef  xor     rcx, rsp; StackCookie
0x1800635f2  call    __security_check_cookie
0x1800635f7  lea     r11, [rsp+2A8h+var_8]
0x1800635ff  mov     rbx, [r11+18h]
0x180063603  mov     rsi, [r11+20h]
0x180063607  mov     rsp, r11
0x18006360a  pop     rdi
0x18006360b  retn
0x18006360d  lea     rdx, [rsp+2A8h+Buffer]; String2
0x180063612  mov     rcx, rbx; String1
0x180063615  call    cs:__imp__wcsicmp
0x18006361c  nop     dword ptr [rax+rax+00h]
0x180063621  test    eax, eax
0x180063623  jnz     short loc_1800635E5
0x180063625  mov     eax, 1
0x18006362a  jmp     short loc_1800635E7
```
