# FaxMsgBox

- ea: `0x18000edb0`
- end: `0x18000ef57`
- name: `FaxMsgBox`
- size: `423`
- prototype: ``
- caller_count: `17`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e8a8`
- `0x18000eaec`
- `0x1800101a0`
- `0x180010e30`
- `0x180011310`
- `0x1800115b0`
- `0x180011710`
- `0x1800117e0`
- `0x180011cb0`
- `0x1800122c0`
- `0x180012978`
- `0x180012a40`
- `0x180012ce0`
- `0x18001352c`
- `0x180014920`
- `0x180014df8`
- `0x180015200`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000dc34`
- `0x18000edb0`
- `0x18000f2c4`
- `0x180015cbe`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ee3e`
- `KERNEL32!GetModuleHandleW` at `0x18000ee3e`
- `KERNEL32!GetLastError` at `0x18000ee54`
- `KERNEL32!GetLastError` at `0x18000ee9d`
- `KERNEL32!GetLastError` at `0x18000eedf`
- `KERNEL32!GetLastError` at `0x18000ee54`
- `KERNEL32!GetLastError` at `0x18000ee9d`
- `KERNEL32!GetLastError` at `0x18000eedf`
- `USER32!LoadStringW` at `0x18000ee93`
- `USER32!LoadStringW` at `0x18000eed5`
- `USER32!LoadStringW` at `0x18000ee93`
- `USER32!LoadStringW` at `0x18000eed5`

## pseudocode

```c
__int64 __fastcall FaxMsgBox(__int64 a1, HMODULE ResInst, UINT a3, UINT a4, unsigned int a5)
{
  HMODULE ModuleHandleW; // rax
  __int64 v10; // rcx
  DWORD LastError; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-658h] BYREF
  WCHAR v16[520]; // [rsp+230h] [rbp-448h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v16, 0, sizeof(v16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids);
  }
  if ( !ResInst )
  {
    ModuleHandleW = GetModuleHandleW(0);
    ResInst = GetResInst(v10, ModuleHandleW);
    if ( !ResInst )
    {
      LastError = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 3;
      }
      v13 = 13;
LABEL_21:
      WPP_SF_d(v12[2], v13, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids, LastError);
      return 3;
    }
  }
  if ( !LoadStringW(ResInst, a3, Buffer, 259) )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 3;
    }
    v13 = 14;
    goto LABEL_21;
  }
  if ( !LoadStringW(ResInst, a4, v16, 519) )
  {
    LastError = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 3;
    }
    v13 = 15;
    goto LABEL_21;
  }
  return AlignedMessageBox(a1, v16, Buffer, a5);
}

```

## disassembly

```asm
0x18000edb0  push    rbx
0x18000edb2  push    rbp
0x18000edb3  push    rsi
0x18000edb4  push    rdi
0x18000edb5  push    r12
0x18000edb7  sub     rsp, 650h
0x18000edbe  mov     rax, cs:__security_cookie
0x18000edc5  xor     rax, rsp
0x18000edc8  mov     [rsp+678h+var_38], rax
0x18000edd0  mov     esi, r8d
0x18000edd3  mov     rbx, rdx
0x18000edd6  mov     rdi, rcx
0x18000edd9  xor     edx, edx; Val
0x18000eddb  mov     r8d, 208h; Size
0x18000ede1  lea     rcx, [rsp+678h+Buffer]; void *
0x18000ede6  mov     ebp, r9d
0x18000ede9  call    memset_0
0x18000edee  xor     edx, edx; Val
0x18000edf0  lea     rcx, [rsp+678h+var_448]; void *
0x18000edf8  mov     r8d, 410h; Size
0x18000edfe  call    memset_0
0x18000ee03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee0a  lea     r12, WPP_GLOBAL_Control
0x18000ee11  cmp     rcx, r12
0x18000ee14  jz      short loc_18000EE37
0x18000ee16  test    byte ptr [rcx+1Ch], 2
0x18000ee1a  jz      short loc_18000EE37
0x18000ee1c  cmp     byte ptr [rcx+19h], 5
0x18000ee20  jb      short loc_18000EE37
0x18000ee22  mov     rcx, [rcx+10h]
0x18000ee26  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x18000ee2d  mov     edx, 0Ch
0x18000ee32  call    WPP_SF_
0x18000ee37  test    rbx, rbx
0x18000ee3a  jnz     short loc_18000EE83
0x18000ee3c  xor     ecx, ecx; lpModuleName
0x18000ee3e  call    cs:__imp_GetModuleHandleW
0x18000ee44  mov     rdx, rax
0x18000ee47  call    GetResInst
0x18000ee4c  mov     rbx, rax
0x18000ee4f  test    rax, rax
0x18000ee52  jnz     short loc_18000EE83
0x18000ee54  call    cs:__imp_GetLastError
0x18000ee5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee61  cmp     rcx, r12
0x18000ee64  jz      loc_18000EF15
0x18000ee6a  test    byte ptr [rcx+1Ch], 2
0x18000ee6e  jz      loc_18000EF15
0x18000ee74  cmp     byte ptr [rcx+19h], 2
0x18000ee78  jb      loc_18000EF15
0x18000ee7e  lea     edx, [rbx+0Dh]
0x18000ee81  jmp     short loc_18000EF02
0x18000ee83  mov     r9d, 103h; cchBufferMax
0x18000ee89  lea     r8, [rsp+678h+Buffer]; lpBuffer
0x18000ee8e  mov     edx, esi; uID
0x18000ee90  mov     rcx, rbx; hInstance
0x18000ee93  call    cs:__imp_LoadStringW
0x18000ee99  test    eax, eax
0x18000ee9b  jnz     short loc_18000EEC2
0x18000ee9d  call    cs:__imp_GetLastError
0x18000eea3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeaa  cmp     rcx, r12
0x18000eead  jz      short loc_18000EF15
0x18000eeaf  test    byte ptr [rcx+1Ch], 2
0x18000eeb3  jz      short loc_18000EF15
0x18000eeb5  cmp     byte ptr [rcx+19h], 2
0x18000eeb9  jb      short loc_18000EF15
0x18000eebb  mov     edx, 0Eh
0x18000eec0  jmp     short loc_18000EF02
0x18000eec2  mov     r9d, 207h; cchBufferMax
0x18000eec8  lea     r8, [rsp+678h+var_448]; lpBuffer
0x18000eed0  mov     edx, ebp; uID
0x18000eed2  mov     rcx, rbx; hInstance
0x18000eed5  call    cs:__imp_LoadStringW
0x18000eedb  test    eax, eax
0x18000eedd  jnz     short loc_18000EF1C
0x18000eedf  call    cs:__imp_GetLastError
0x18000eee5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeec  cmp     rcx, r12
0x18000eeef  jz      short loc_18000EF15
0x18000eef1  test    byte ptr [rcx+1Ch], 2
0x18000eef5  jz      short loc_18000EF15
0x18000eef7  cmp     byte ptr [rcx+19h], 2
0x18000eefb  jb      short loc_18000EF15
0x18000eefd  mov     edx, 0Fh
0x18000ef02  mov     rcx, [rcx+10h]
0x18000ef06  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x18000ef0d  mov     r9d, eax
0x18000ef10  call    WPP_SF_d
0x18000ef15  mov     eax, 3
0x18000ef1a  jmp     short loc_18000EF39
0x18000ef1c  mov     r9d, [rsp+678h+arg_20]
0x18000ef24  lea     r8, [rsp+678h+Buffer]
0x18000ef29  lea     rdx, [rsp+678h+var_448]
0x18000ef31  mov     rcx, rdi
0x18000ef34  call    AlignedMessageBox
0x18000ef39  mov     rcx, [rsp+678h+var_38]
0x18000ef41  xor     rcx, rsp; StackCookie
0x18000ef44  call    __security_check_cookie
0x18000ef49  add     rsp, 650h
0x18000ef50  pop     r12
0x18000ef52  pop     rdi
0x18000ef53  pop     rsi
0x18000ef54  pop     rbp
0x18000ef55  pop     rbx
0x18000ef56  retn
```
