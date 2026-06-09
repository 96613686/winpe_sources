# CHostContext::WaitUntilRpcIsReady(ushort const *)

- ea: `0x180025f3c`
- end: `0x180026082`
- name: `?WaitUntilRpcIsReady@CHostContext@@IEAAJPEBG@Z`
- size: `326`
- prototype: `int(CHostContext *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022624`

## callees

- `0x180007500`
- `0x180025f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180025f87`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180025f87`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025fb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002602d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002602d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025f77`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025f77`

## pseudocode

```c
__int64 __fastcall CHostContext::WaitUntilRpcIsReady(CHostContext *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  int i; // esi
  HANDLE v5; // rdi
  signed int v6; // eax
  signed int LastError; // eax
  int v8; // edx
  int v9; // r8d
  signed int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  signed int v14; // eax

  v2 = 0;
  for ( i = 0; i <= 10; ++i )
  {
    Sleep(500 * i);
    v5 = OpenEventW(0x100000u, 0, a2);
    if ( v5 )
    {
      v2 = 0;
      if ( WaitForSingleObject(v5, 0xFFFFFFFF) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v8,
            v9,
            41,
            &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
            v2);
      }
      if ( !CloseHandle(v5) )
      {
        v14 = GetLastError();
        v2 = v14;
        if ( v14 > 0 )
          v2 = (unsigned __int16)v14 | 0x80070000;
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v13 = 42;
          goto LABEL_23;
        }
      }
      return v2;
    }
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
  }
  if ( !v2 )
  {
    v10 = GetLastError();
    v2 = v10;
    if ( v10 > 0 )
      v2 = (unsigned __int16)v10 | 0x80070000;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v13 = 40;
LABEL_23:
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        v13,
        &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
        v2);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180025f3c  push    rbx
0x180025f3e  push    rbp
0x180025f3f  push    rsi
0x180025f40  push    rdi
0x180025f41  push    r12
0x180025f43  push    r14
0x180025f45  push    r15
0x180025f47  sub     rsp, 30h
0x180025f4b  xor     ebx, ebx
0x180025f4d  xor     edi, edi
0x180025f4f  xor     esi, esi
0x180025f51  mov     rbp, rdx
0x180025f54  mov     r14d, 80070000h
0x180025f5a  lea     r15, WPP_RECORDER_INITIALIZED
0x180025f61  lea     r12, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x180025f68  cmp     esi, 0Ah
0x180025f6b  jg      loc_180025FF9
0x180025f71  imul    ecx, esi, 1F4h; dwMilliseconds
0x180025f77  call    cs:__imp_Sleep
0x180025f7d  mov     r8, rbp; lpName
0x180025f80  xor     edx, edx; bInheritHandle
0x180025f82  mov     ecx, 100000h; dwDesiredAccess
0x180025f87  call    cs:__imp_OpenEventW
0x180025f8d  mov     rdi, rax
0x180025f90  test    rax, rax
0x180025f93  jnz     short loc_180025FAB
0x180025f95  call    cs:__imp_GetLastError
0x180025f9b  mov     ebx, eax
0x180025f9d  test    eax, eax
0x180025f9f  jle     short loc_180025FA7
0x180025fa1  movzx   ebx, ax
0x180025fa4  or      ebx, r14d
0x180025fa7  inc     esi
0x180025fa9  jmp     short loc_180025F5A
0x180025fab  xor     ebx, ebx
0x180025fad  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025fb0  mov     rcx, rdi; hHandle
0x180025fb3  call    cs:__imp_WaitForSingleObject
0x180025fb9  test    eax, eax
0x180025fbb  jz      short loc_18002602A
0x180025fbd  call    cs:__imp_GetLastError
0x180025fc3  mov     ebx, eax
0x180025fc5  test    eax, eax
0x180025fc7  jle     short loc_180025FCF
0x180025fc9  movzx   ebx, ax
0x180025fcc  or      ebx, r14d
0x180025fcf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180025fd6  jz      short loc_18002602A
0x180025fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fdf  mov     r9d, 29h ; ')'; int
0x180025fe5  mov     dword ptr [rsp+68h+var_40], ebx; char
0x180025fe9  mov     [rsp+68h+MessageGuid], r12; MessageGuid
0x180025fee  mov     rcx, [rcx+28h]; int
0x180025ff2  call    WPP_RECORDER_SF_D
0x180025ff7  jmp     short loc_18002602A
0x180025ff9  test    ebx, ebx
0x180025ffb  jnz     short loc_180026025
0x180025ffd  test    rdi, rdi
0x180026000  jnz     short loc_180025FAD
0x180026002  call    cs:__imp_GetLastError
0x180026008  mov     ebx, eax
0x18002600a  test    eax, eax
0x18002600c  jle     short loc_180026014
0x18002600e  movzx   ebx, ax
0x180026011  or      ebx, r14d
0x180026014  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002601b  jz      short loc_180026071
0x18002601d  mov     r9d, 28h ; '('
0x180026023  jmp     short loc_180026058
0x180026025  test    rdi, rdi
0x180026028  jz      short loc_180026071
0x18002602a  mov     rcx, rdi; hObject
0x18002602d  call    cs:__imp_CloseHandle
0x180026033  test    eax, eax
0x180026035  jnz     short loc_180026071
0x180026037  call    cs:__imp_GetLastError
0x18002603d  mov     ebx, eax
0x18002603f  test    eax, eax
0x180026041  jle     short loc_180026049
0x180026043  movzx   ebx, ax
0x180026046  or      ebx, r14d
0x180026049  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180026050  jz      short loc_180026071
0x180026052  mov     r9d, 2Ah ; '*'; int
0x180026058  mov     rcx, cs:WPP_GLOBAL_Control
0x18002605f  mov     dword ptr [rsp+68h+var_40], ebx; char
0x180026063  mov     [rsp+68h+MessageGuid], r12; MessageGuid
0x180026068  mov     rcx, [rcx+28h]; int
0x18002606c  call    WPP_RECORDER_SF_D
0x180026071  mov     eax, ebx
0x180026073  add     rsp, 30h
0x180026077  pop     r15
0x180026079  pop     r14
0x18002607b  pop     r12
0x18002607d  pop     rdi
0x18002607e  pop     rsi
0x18002607f  pop     rbp
0x180026080  pop     rbx
0x180026081  retn
```
