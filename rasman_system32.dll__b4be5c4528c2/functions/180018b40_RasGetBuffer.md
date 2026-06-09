# RasGetBuffer

- ea: `0x180018b40`
- end: `0x180018c83`
- name: `RasGetBuffer`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180018b40`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018bf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018bf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ba4`

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
0x180018b40  push    rbx
0x180018b42  push    rsi
0x180018b43  push    rdi
0x180018b44  push    r14
0x180018b46  push    r15
0x180018b48  sub     rsp, 20h
0x180018b4c  mov     rsi, rdx
0x180018b4f  mov     r14, rcx
0x180018b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b59  lea     r15, WPP_GLOBAL_Control
0x180018b60  cmp     rcx, r15
0x180018b63  jz      short loc_180018B86
0x180018b65  test    byte ptr [rcx+1Ch], 40h
0x180018b69  jz      short loc_180018B86
0x180018b6b  cmp     byte ptr [rcx+19h], 6
0x180018b6f  jb      short loc_180018B86
0x180018b71  mov     rcx, [rcx+10h]
0x180018b75  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018b7c  mov     edx, 0EFh
0x180018b81  call    WPP_SF_
0x180018b86  mov     edx, 608h; uBytes
0x180018b8b  mov     ecx, 40h ; '@'; uFlags
0x180018b90  call    cs:__imp_LocalAlloc
0x180018b97  nop     dword ptr [rax+rax+00h]
0x180018b9c  mov     rdi, rax
0x180018b9f  test    rax, rax
0x180018ba2  jnz     short loc_180018BF0
0x180018ba4  call    cs:__imp_GetLastError
0x180018bab  nop     dword ptr [rax+rax+00h]
0x180018bb0  mov     ebx, eax
0x180018bb2  test    eax, eax
0x180018bb4  jz      loc_180018C44
0x180018bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180018bc1  cmp     rcx, r15
0x180018bc4  jz      loc_180018C74
0x180018bca  test    byte ptr [rcx+1Ch], 40h
0x180018bce  jz      short loc_180018C4B
0x180018bd0  cmp     byte ptr [rcx+19h], 2
0x180018bd4  jb      short loc_180018C4B
0x180018bd6  mov     rcx, [rcx+10h]
0x180018bda  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018be1  mov     edx, 0F0h
0x180018be6  mov     r9d, eax
0x180018be9  call    WPP_SF_d
0x180018bee  jmp     short loc_180018C44
0x180018bf0  xor     ebx, ebx
0x180018bf2  call    cs:__imp_GetCurrentProcessId
0x180018bf9  nop     dword ptr [rax+rax+00h]
0x180018bfe  mov     [rdi+4], eax
0x180018c01  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c08  cmp     rcx, r15
0x180018c0b  jz      short loc_180018C31
0x180018c0d  test    byte ptr [rcx+1Ch], 40h
0x180018c11  jz      short loc_180018C31
0x180018c13  cmp     byte ptr [rcx+19h], 5
0x180018c17  jb      short loc_180018C31
0x180018c19  mov     rcx, [rcx+10h]
0x180018c1d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018c24  mov     edx, 0F1h
0x180018c29  mov     r9d, eax
0x180018c2c  call    WPP_SF_d
0x180018c31  mov     eax, 5DCh
0x180018c36  cmp     [rsi], eax
0x180018c38  cmovb   eax, [rsi]
0x180018c3b  mov     [rsi], eax
0x180018c3d  lea     rax, [rdi+20h]
0x180018c41  mov     [r14], rax
0x180018c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c4b  cmp     rcx, r15
0x180018c4e  jz      short loc_180018C74
0x180018c50  test    byte ptr [rcx+1Ch], 40h
0x180018c54  jz      short loc_180018C74
0x180018c56  cmp     byte ptr [rcx+19h], 6
0x180018c5a  jb      short loc_180018C74
0x180018c5c  mov     rcx, [rcx+10h]
0x180018c60  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018c67  mov     edx, 0F2h
0x180018c6c  mov     r9d, ebx
0x180018c6f  call    WPP_SF_d
0x180018c74  mov     eax, ebx
0x180018c76  add     rsp, 20h
0x180018c7a  pop     r15
0x180018c7c  pop     r14
0x180018c7e  pop     rdi
0x180018c7f  pop     rsi
0x180018c80  pop     rbx
0x180018c81  retn
```
