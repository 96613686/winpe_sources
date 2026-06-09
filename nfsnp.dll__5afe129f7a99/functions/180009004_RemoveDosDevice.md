# RemoveDosDevice

- ea: `0x180009004`
- end: `0x1800090d6`
- name: `RemoveDosDevice`
- size: `210`
- prototype: `int __fastcall(LPCWSTR lpDeviceName, LPCWSTR lpTargetPath, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004a40`
- `0x180005c40`

## callees

- `0x180002508`
- `0x180002538`
- `0x180009004`
- `0x180009144`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009079`
- `KERNEL32!GetLastError` at `0x180009079`
- `KERNEL32!DefineDosDeviceW` at `0x180009053`
- `KERNEL32!DefineDosDeviceW` at `0x180009053`

## pseudocode

```c
int __fastcall RemoveDosDevice(LPCWSTR lpDeviceName, LPCWSTR lpTargetPath, int a3)
{
  int result; // eax
  __int64 v6; // rbx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, a3, (_DWORD)lpDeviceName, (__int64)lpTargetPath);
  result = DefineDosDeviceW(0xFu, lpDeviceName, lpTargetPath);
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    return WPP_SF_d(v6, 125, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, LastError);
  }
  return result;
}

```

## disassembly

```asm
0x180009004  mov     [rsp+arg_0], rbx
0x180009009  mov     [rsp+arg_8], rsi
0x18000900e  push    rdi
0x18000900f  sub     rsp, 30h
0x180009013  mov     rbx, rdx
0x180009016  mov     rdi, rcx
0x180009019  mov     rcx, cs:WPP_GLOBAL_Control
0x180009020  lea     rsi, WPP_GLOBAL_Control
0x180009027  cmp     rcx, rsi
0x18000902a  jz      short loc_180009048
0x18000902c  test    byte ptr [rcx+1Ch], 1
0x180009030  jz      short loc_180009048
0x180009032  mov     rcx, [rcx+10h]
0x180009036  mov     edx, 7Ch ; '|'
0x18000903b  mov     r9, rdi
0x18000903e  mov     [rsp+38h+var_18], rbx
0x180009043  call    WPP_SF_SS
0x180009048  mov     r8, rbx; lpTargetPath
0x18000904b  mov     rdx, rdi; lpDeviceName
0x18000904e  mov     ecx, 0Fh; dwFlags
0x180009053  call    cs:__imp_DefineDosDeviceW
0x18000905a  nop     dword ptr [rax+rax+00h]
0x18000905f  test    eax, eax
0x180009061  jnz     short loc_18000909E
0x180009063  mov     rbx, cs:WPP_GLOBAL_Control
0x18000906a  cmp     rbx, rsi
0x18000906d  jz      short loc_1800090C5
0x18000906f  test    byte ptr [rbx+1Ch], 2
0x180009073  jz      short loc_1800090C5
0x180009075  mov     rbx, [rbx+10h]
0x180009079  call    cs:__imp_GetLastError
0x180009080  nop     dword ptr [rax+rax+00h]
0x180009085  mov     edx, 7Dh ; '}'
0x18000908a  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180009091  mov     r9d, eax
0x180009094  mov     rcx, rbx
0x180009097  call    WPP_SF_d
0x18000909c  jmp     short loc_1800090C5
0x18000909e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090a5  cmp     rcx, rsi
0x1800090a8  jz      short loc_1800090C5
0x1800090aa  test    byte ptr [rcx+1Ch], 1
0x1800090ae  jz      short loc_1800090C5
0x1800090b0  mov     rcx, [rcx+10h]
0x1800090b4  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800090bb  mov     edx, 7Eh ; '~'
0x1800090c0  call    WPP_SF_
0x1800090c5  mov     rbx, [rsp+38h+arg_0]
0x1800090ca  mov     rsi, [rsp+38h+arg_8]
0x1800090cf  add     rsp, 30h
0x1800090d3  pop     rdi
0x1800090d4  retn
```
