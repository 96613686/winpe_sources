# FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)

- ea: `0x140072518`
- end: `0x1400725fc`
- name: `?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z`
- size: `228`
- prototype: `unsigned int __fastcall(SC_HANDLE hSCObject, SC_HANDLE)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140072604`
- `0x140072e44`
- `0x140073750`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140072518`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x140072564`
- `ADVAPI32!CloseServiceHandle` at `0x1400725ae`
- `ADVAPI32!CloseServiceHandle` at `0x140072564`
- `ADVAPI32!CloseServiceHandle` at `0x1400725ae`
- `KERNEL32!GetLastError` at `0x14007256e`
- `KERNEL32!GetLastError` at `0x1400725b8`
- `KERNEL32!GetLastError` at `0x14007256e`
- `KERNEL32!GetLastError` at `0x1400725b8`

## pseudocode

```c
__int64 __fastcall FaxCloseService(SC_HANDLE hSCObject, SC_HANDLE a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD v6; // eax

  v4 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  if ( a2 )
  {
    if ( !CloseServiceHandle(a2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
    }
  }
  if ( hSCObject )
  {
    if ( !CloseServiceHandle(hSCObject) )
    {
      v6 = GetLastError();
      v4 = v6;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_db036311db36307996a98c23702218b2_Traceguids, v6);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140072518  push    rbx
0x14007251a  push    rsi
0x14007251b  push    rdi
0x14007251c  push    r14
0x14007251e  sub     rsp, 28h
0x140072522  mov     rdi, rdx
0x140072525  mov     rsi, rcx
0x140072528  xor     ebx, ebx
0x14007252a  mov     rcx, cs:WPP_GLOBAL_Control
0x140072531  lea     r14, WPP_GLOBAL_Control
0x140072538  cmp     rcx, r14
0x14007253b  jz      short loc_14007255C
0x14007253d  test    byte ptr [rcx+1Ch], 2
0x140072541  jz      short loc_14007255C
0x140072543  cmp     byte ptr [rcx+19h], 5
0x140072547  jb      short loc_14007255C
0x140072549  mov     rcx, [rcx+10h]
0x14007254d  lea     edx, [rbx+0Eh]
0x140072550  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072557  call    WPP_SF_
0x14007255c  test    rdi, rdi
0x14007255f  jz      short loc_1400725A6
0x140072561  mov     rcx, rdi; hSCObject
0x140072564  call    cs:__imp_CloseServiceHandle
0x14007256a  test    eax, eax
0x14007256c  jnz     short loc_1400725A6
0x14007256e  call    cs:__imp_GetLastError
0x140072574  mov     ebx, eax
0x140072576  mov     rcx, cs:WPP_GLOBAL_Control
0x14007257d  cmp     rcx, r14
0x140072580  jz      short loc_1400725A6
0x140072582  test    byte ptr [rcx+1Ch], 2
0x140072586  jz      short loc_1400725A6
0x140072588  cmp     byte ptr [rcx+19h], 2
0x14007258c  jb      short loc_1400725A6
0x14007258e  mov     rcx, [rcx+10h]
0x140072592  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072599  mov     edx, 0Fh
0x14007259e  mov     r9d, eax
0x1400725a1  call    WPP_SF_d
0x1400725a6  test    rsi, rsi
0x1400725a9  jz      short loc_1400725F0
0x1400725ab  mov     rcx, rsi; hSCObject
0x1400725ae  call    cs:__imp_CloseServiceHandle
0x1400725b4  test    eax, eax
0x1400725b6  jnz     short loc_1400725F0
0x1400725b8  call    cs:__imp_GetLastError
0x1400725be  mov     ebx, eax
0x1400725c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400725c7  cmp     rcx, r14
0x1400725ca  jz      short loc_1400725F0
0x1400725cc  test    byte ptr [rcx+1Ch], 2
0x1400725d0  jz      short loc_1400725F0
0x1400725d2  cmp     byte ptr [rcx+19h], 2
0x1400725d6  jb      short loc_1400725F0
0x1400725d8  mov     rcx, [rcx+10h]
0x1400725dc  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400725e3  mov     edx, 10h
0x1400725e8  mov     r9d, eax
0x1400725eb  call    WPP_SF_d
0x1400725f0  mov     eax, ebx
0x1400725f2  add     rsp, 28h
0x1400725f6  pop     r14
0x1400725f8  pop     rdi
0x1400725f9  pop     rsi
0x1400725fa  pop     rbx
0x1400725fb  retn
```
