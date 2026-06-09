# RasGetBuffer

- ea: `0x180018160`
- end: `0x180018290`
- name: `RasGetBuffer`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180018160`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018206`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018206`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800181b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800181b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800181be`

## pseudocode

```c
__int64 __fastcall RasGetBuffer(_QWORD *a1, int *a2)
{
  _DWORD *v4; // rdi
  DWORD LastError; // eax
  DWORD v6; // ebx
  PVOID *v7; // rcx
  DWORD CurrentProcessId; // eax
  int v9; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v4 = LocalAlloc(0x40u, 0x608u);
  if ( v4 )
  {
    v6 = 0;
    CurrentProcessId = GetCurrentProcessId();
    v4[1] = CurrentProcessId;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        241,
        &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
        CurrentProcessId);
    }
    v9 = 1500;
    if ( (unsigned int)*a2 < 0x5DC )
      v9 = *a2;
    *a2 = v9;
    *a1 = v4 + 8;
    goto LABEL_18;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
  {
LABEL_18:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, LastError);
    goto LABEL_18;
  }
LABEL_19:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 242, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180018160  push    rbx
0x180018162  push    rsi
0x180018163  push    rdi
0x180018164  push    r14
0x180018166  push    r15
0x180018168  sub     rsp, 20h
0x18001816c  mov     rsi, rdx
0x18001816f  mov     r14, rcx
0x180018172  mov     rcx, cs:WPP_GLOBAL_Control
0x180018179  lea     r15, WPP_GLOBAL_Control
0x180018180  cmp     rcx, r15
0x180018183  jz      short loc_1800181A6
0x180018185  test    byte ptr [rcx+1Ch], 40h
0x180018189  jz      short loc_1800181A6
0x18001818b  cmp     byte ptr [rcx+19h], 6
0x18001818f  jb      short loc_1800181A6
0x180018191  mov     rcx, [rcx+10h]
0x180018195  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001819c  mov     edx, 0EFh
0x1800181a1  call    WPP_SF_
0x1800181a6  mov     edx, 608h; uBytes
0x1800181ab  mov     ecx, 40h ; '@'; uFlags
0x1800181b0  call    cs:__imp_LocalAlloc
0x1800181b6  mov     rdi, rax
0x1800181b9  test    rax, rax
0x1800181bc  jnz     short loc_180018204
0x1800181be  call    cs:__imp_GetLastError
0x1800181c4  mov     ebx, eax
0x1800181c6  test    eax, eax
0x1800181c8  jz      loc_180018252
0x1800181ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181d5  cmp     rcx, r15
0x1800181d8  jz      loc_180018282
0x1800181de  test    byte ptr [rcx+1Ch], 40h
0x1800181e2  jz      short loc_180018259
0x1800181e4  cmp     byte ptr [rcx+19h], 2
0x1800181e8  jb      short loc_180018259
0x1800181ea  mov     rcx, [rcx+10h]
0x1800181ee  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800181f5  mov     edx, 0F0h
0x1800181fa  mov     r9d, eax
0x1800181fd  call    WPP_SF_d
0x180018202  jmp     short loc_180018252
0x180018204  xor     ebx, ebx
0x180018206  call    cs:__imp_GetCurrentProcessId
0x18001820c  mov     [rdi+4], eax
0x18001820f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018216  cmp     rcx, r15
0x180018219  jz      short loc_18001823F
0x18001821b  test    byte ptr [rcx+1Ch], 40h
0x18001821f  jz      short loc_18001823F
0x180018221  cmp     byte ptr [rcx+19h], 5
0x180018225  jb      short loc_18001823F
0x180018227  mov     rcx, [rcx+10h]
0x18001822b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018232  mov     edx, 0F1h
0x180018237  mov     r9d, eax
0x18001823a  call    WPP_SF_d
0x18001823f  mov     eax, 5DCh
0x180018244  cmp     [rsi], eax
0x180018246  cmovb   eax, [rsi]
0x180018249  mov     [rsi], eax
0x18001824b  lea     rax, [rdi+20h]
0x18001824f  mov     [r14], rax
0x180018252  mov     rcx, cs:WPP_GLOBAL_Control
0x180018259  cmp     rcx, r15
0x18001825c  jz      short loc_180018282
0x18001825e  test    byte ptr [rcx+1Ch], 40h
0x180018262  jz      short loc_180018282
0x180018264  cmp     byte ptr [rcx+19h], 6
0x180018268  jb      short loc_180018282
0x18001826a  mov     rcx, [rcx+10h]
0x18001826e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018275  mov     edx, 0F2h
0x18001827a  mov     r9d, ebx
0x18001827d  call    WPP_SF_d
0x180018282  mov     eax, ebx
0x180018284  add     rsp, 20h
0x180018288  pop     r15
0x18001828a  pop     r14
0x18001828c  pop     rdi
0x18001828d  pop     rsi
0x18001828e  pop     rbx
0x18001828f  retn
```
