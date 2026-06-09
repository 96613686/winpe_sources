# FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)

- ea: `0x1800055a0`
- end: `0x180005684`
- name: `?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z`
- size: `228`
- prototype: `unsigned int __fastcall(SC_HANDLE hSCObject, SC_HANDLE)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004e20`
- `0x18000568c`
- `0x180005a28`
- `0x180005b6c`

## callees

- `0x1800055a0`
- `0x180005eac`
- `0x180005ed4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800055f6`
- `KERNEL32!GetLastError` at `0x180005640`
- `KERNEL32!GetLastError` at `0x1800055f6`
- `KERNEL32!GetLastError` at `0x180005640`
- `ADVAPI32!CloseServiceHandle` at `0x1800055ec`
- `ADVAPI32!CloseServiceHandle` at `0x180005636`
- `ADVAPI32!CloseServiceHandle` at `0x1800055ec`
- `ADVAPI32!CloseServiceHandle` at `0x180005636`

## pseudocode

```c
__int64 __fastcall FaxCloseService(SC_HANDLE hSCObject, SC_HANDLE a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD v6; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  if ( a2 )
  {
    if ( !CloseServiceHandle(a2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
    }
  }
  if ( hSCObject )
  {
    if ( !CloseServiceHandle(hSCObject) )
    {
      v6 = GetLastError();
      v4 = v6;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_db036311db36307996a98c23702218b2_Traceguids, v6);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800055a0  push    rbx
0x1800055a2  push    rsi
0x1800055a3  push    rdi
0x1800055a4  push    r14
0x1800055a6  sub     rsp, 28h
0x1800055aa  mov     rdi, rdx
0x1800055ad  mov     rsi, rcx
0x1800055b0  xor     ebx, ebx
0x1800055b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055b9  lea     r14, WPP_GLOBAL_Control
0x1800055c0  cmp     rcx, r14
0x1800055c3  jz      short loc_1800055E4
0x1800055c5  test    byte ptr [rcx+1Ch], 2
0x1800055c9  jz      short loc_1800055E4
0x1800055cb  cmp     byte ptr [rcx+19h], 5
0x1800055cf  jb      short loc_1800055E4
0x1800055d1  mov     rcx, [rcx+10h]
0x1800055d5  lea     edx, [rbx+0Eh]
0x1800055d8  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1800055df  call    WPP_SF_
0x1800055e4  test    rdi, rdi
0x1800055e7  jz      short loc_18000562E
0x1800055e9  mov     rcx, rdi; hSCObject
0x1800055ec  call    cs:__imp_CloseServiceHandle
0x1800055f2  test    eax, eax
0x1800055f4  jnz     short loc_18000562E
0x1800055f6  call    cs:__imp_GetLastError
0x1800055fc  mov     ebx, eax
0x1800055fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180005605  cmp     rcx, r14
0x180005608  jz      short loc_18000562E
0x18000560a  test    byte ptr [rcx+1Ch], 2
0x18000560e  jz      short loc_18000562E
0x180005610  cmp     byte ptr [rcx+19h], 2
0x180005614  jb      short loc_18000562E
0x180005616  mov     rcx, [rcx+10h]
0x18000561a  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005621  mov     edx, 0Fh
0x180005626  mov     r9d, eax
0x180005629  call    WPP_SF_d
0x18000562e  test    rsi, rsi
0x180005631  jz      short loc_180005678
0x180005633  mov     rcx, rsi; hSCObject
0x180005636  call    cs:__imp_CloseServiceHandle
0x18000563c  test    eax, eax
0x18000563e  jnz     short loc_180005678
0x180005640  call    cs:__imp_GetLastError
0x180005646  mov     ebx, eax
0x180005648  mov     rcx, cs:WPP_GLOBAL_Control
0x18000564f  cmp     rcx, r14
0x180005652  jz      short loc_180005678
0x180005654  test    byte ptr [rcx+1Ch], 2
0x180005658  jz      short loc_180005678
0x18000565a  cmp     byte ptr [rcx+19h], 2
0x18000565e  jb      short loc_180005678
0x180005660  mov     rcx, [rcx+10h]
0x180005664  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18000566b  mov     edx, 10h
0x180005670  mov     r9d, eax
0x180005673  call    WPP_SF_d
0x180005678  mov     eax, ebx
0x18000567a  add     rsp, 28h
0x18000567e  pop     r14
0x180005680  pop     rdi
0x180005681  pop     rsi
0x180005682  pop     rbx
0x180005683  retn
```
