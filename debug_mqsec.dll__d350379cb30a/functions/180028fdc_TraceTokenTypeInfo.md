# TraceTokenTypeInfo

- ea: `0x180028fdc`
- end: `0x1800290e5`
- name: `TraceTokenTypeInfo`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028cc0`

## callees

- `0x1800049ac`
- `0x18001353c`
- `0x180028fdc`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180029009`
- `ADVAPI32!GetTokenInformation` at `0x180029009`
- `KERNEL32!GetLastError` at `0x180029013`
- `KERNEL32!GetLastError` at `0x180029013`

## pseudocode

```c
DWORD __fastcall TraceTokenTypeInfo(void *a1)
{
  DWORD result; // eax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(a1, TokenType, &TokenInformation, 4u, &ReturnLength) )
  {
    result = TokenInformation - 1;
    if ( (unsigned int)(TokenInformation - 1) > 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        return WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 32),
                 25,
                 &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids,
                 TokenInformation);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    {
      return WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 32));
    }
  }
  else
  {
    result = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      return WPP_SF_d(
               *((_QWORD *)WPP_GLOBAL_Control + 32),
               23,
               &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids,
               result);
  }
  return result;
}

```

## disassembly

```asm
0x180028fdc  sub     rsp, 38h
0x180028fe0  mov     r9d, 4; TokenInformationLength
0x180028fe6  mov     [rsp+38h+arg_10], 0
0x180028fee  lea     rax, [rsp+38h+arg_10]
0x180028ff3  mov     [rsp+38h+TokenInformation], 0
0x180028ffb  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180029000  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180029005  lea     edx, [r9+4]; TokenInformationClass
0x180029009  call    cs:__imp_GetTokenInformation
0x18002900f  test    eax, eax
0x180029011  jnz     short loc_18002905D
0x180029013  call    cs:__imp_GetLastError
0x180029019  mov     rcx, cs:WPP_GLOBAL_Control
0x180029020  lea     rdx, WPP_GLOBAL_Control
0x180029027  cmp     rcx, rdx
0x18002902a  jz      loc_1800290E0
0x180029030  test    byte ptr [rcx+10Ch], 1
0x180029037  jz      loc_1800290E0
0x18002903d  mov     rcx, [rcx+100h]
0x180029044  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x18002904b  mov     edx, 17h
0x180029050  mov     r9d, eax
0x180029053  call    WPP_SF_d
0x180029058  jmp     loc_1800290E0
0x18002905d  movsxd  r9, [rsp+38h+TokenInformation]
0x180029062  lea     eax, [r9-1]
0x180029066  cmp     eax, 1
0x180029069  ja      short loc_1800290AC
0x18002906b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029072  lea     rdx, WPP_GLOBAL_Control
0x180029079  cmp     rcx, rdx
0x18002907c  jz      short loc_1800290E0
0x18002907e  test    byte ptr [rcx+10Ch], 4
0x180029085  jz      short loc_1800290E0
0x180029087  mov     rcx, [rcx+100h]; LoggerHandle
0x18002908e  lea     rax, off_180032850
0x180029095  mov     r9, [rax+r9*8]
0x180029099  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x1800290a0  mov     edx, 18h
0x1800290a5  call    WPP_SF_S
0x1800290aa  jmp     short loc_1800290E0
0x1800290ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290b3  lea     rdx, WPP_GLOBAL_Control
0x1800290ba  cmp     rcx, rdx
0x1800290bd  jz      short loc_1800290E0
0x1800290bf  test    byte ptr [rcx+10Ch], 4
0x1800290c6  jz      short loc_1800290E0
0x1800290c8  mov     rcx, [rcx+100h]
0x1800290cf  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x1800290d6  mov     edx, 19h
0x1800290db  call    WPP_SF_d
0x1800290e0  add     rsp, 38h
0x1800290e4  retn
```
