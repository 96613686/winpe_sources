# IsThisTheComputerName

- ea: `0x180063214`
- end: `0x1800633a8`
- name: `IsThisTheComputerName`
- size: `404`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800630e4`

## callees

- `0x18000282c`
- `0x1800058bc`
- `0x180063214`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800632f0`
- `msvcrt!_wcsicmp` at `0x180063391`
- `msvcrt!_wcsicmp` at `0x1800632f0`
- `msvcrt!_wcsicmp` at `0x180063391`
- `KERNEL32!GetComputerNameExW` at `0x1800632ab`
- `KERNEL32!GetComputerNameExW` at `0x18006331b`
- `KERNEL32!GetComputerNameExW` at `0x1800632ab`
- `KERNEL32!GetComputerNameExW` at `0x18006331b`
- `KERNEL32!GetLastError` at `0x1800632bb`
- `KERNEL32!GetLastError` at `0x18006332b`
- `KERNEL32!GetLastError` at `0x1800632bb`
- `KERNEL32!GetLastError` at `0x18006332b`

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
0x180063214  mov     [rsp+arg_8], rbx
0x180063219  mov     [rsp+arg_10], rsi
0x18006321e  push    rdi
0x18006321f  sub     rsp, 2A0h
0x180063226  mov     rax, cs:__security_cookie
0x18006322d  xor     rax, rsp
0x180063230  mov     [rsp+2A8h+var_18], rax
0x180063238  mov     rbx, rcx
0x18006323b  mov     rcx, cs:WPP_GLOBAL_Control
0x180063242  lea     rsi, WPP_GLOBAL_Control
0x180063249  cmp     rcx, rsi
0x18006324c  jz      short loc_18006326F
0x18006324e  test    dword ptr [rcx+1Ch], 8000h
0x180063255  jz      short loc_18006326F
0x180063257  mov     rcx, [rcx+10h]
0x18006325b  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x180063262  mov     edx, 18h
0x180063267  mov     r9, rbx
0x18006326a  call    WPP_SF_S
0x18006326f  xor     edi, edi
0x180063271  test    rbx, rbx
0x180063274  jz      loc_180063361
0x18006327a  cmp     [rbx], di
0x18006327d  jz      loc_180063361
0x180063283  cmp     word ptr [rbx], 5Ch ; '\'
0x180063287  jnz     short loc_180063294
0x180063289  cmp     word ptr [rbx+2], 5Ch ; '\'
0x18006328e  jnz     short loc_180063294
0x180063290  add     rbx, 4
0x180063294  lea     r8, [rsp+2A8h+nSize]; nSize
0x180063299  mov     [rsp+2A8h+nSize], 12Ch
0x1800632a1  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x1800632a6  mov     ecx, 1; NameType
0x1800632ab  call    cs:__imp_GetComputerNameExW
0x1800632b2  nop     dword ptr [rax+rax+00h]
0x1800632b7  test    eax, eax
0x1800632b9  jnz     short loc_1800632E8
0x1800632bb  call    cs:__imp_GetLastError
0x1800632c2  nop     dword ptr [rax+rax+00h]
0x1800632c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800632ce  cmp     rcx, rsi
0x1800632d1  jz      loc_180063361
0x1800632d7  test    byte ptr [rcx+1Ch], 10h
0x1800632db  jz      loc_180063361
0x1800632e1  mov     edx, 19h
0x1800632e6  jmp     short loc_18006334E
0x1800632e8  lea     rdx, [rsp+2A8h+Buffer]; String2
0x1800632ed  mov     rcx, rbx; String1
0x1800632f0  call    cs:__imp__wcsicmp
0x1800632f7  nop     dword ptr [rax+rax+00h]
0x1800632fc  test    eax, eax
0x1800632fe  jz      loc_1800633A1
0x180063304  lea     r8, [rsp+2A8h+nSize]; nSize
0x180063309  mov     [rsp+2A8h+nSize], 12Ch
0x180063311  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x180063316  mov     ecx, 3; NameType
0x18006331b  call    cs:__imp_GetComputerNameExW
0x180063322  nop     dword ptr [rax+rax+00h]
0x180063327  test    eax, eax
0x180063329  jnz     short loc_180063389
0x18006332b  call    cs:__imp_GetLastError
0x180063332  nop     dword ptr [rax+rax+00h]
0x180063337  mov     rcx, cs:WPP_GLOBAL_Control
0x18006333e  cmp     rcx, rsi
0x180063341  jz      short loc_180063361
0x180063343  test    byte ptr [rcx+1Ch], 10h
0x180063347  jz      short loc_180063361
0x180063349  mov     edx, 1Ah
0x18006334e  mov     rcx, [rcx+10h]
0x180063352  lea     r8, WPP_ccf2d3be9f843dc4101c18afe604a400_Traceguids
0x180063359  mov     r9d, eax
0x18006335c  call    WPP_SF_D
0x180063361  xor     eax, eax
0x180063363  mov     rcx, [rsp+2A8h+var_18]
0x18006336b  xor     rcx, rsp; StackCookie
0x18006336e  call    __security_check_cookie
0x180063373  lea     r11, [rsp+2A8h+var_8]
0x18006337b  mov     rbx, [r11+18h]
0x18006337f  mov     rsi, [r11+20h]
0x180063383  mov     rsp, r11
0x180063386  pop     rdi
0x180063387  retn
0x180063389  lea     rdx, [rsp+2A8h+Buffer]; String2
0x18006338e  mov     rcx, rbx; String1
0x180063391  call    cs:__imp__wcsicmp
0x180063398  nop     dword ptr [rax+rax+00h]
0x18006339d  test    eax, eax
0x18006339f  jnz     short loc_180063361
0x1800633a1  mov     eax, 1
0x1800633a6  jmp     short loc_180063363
```
