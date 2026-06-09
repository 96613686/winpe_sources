# CMsftDiscRecorder2::GetVolumeHandle(void * &,uchar &)

- ea: `0x18002abd4`
- end: `0x18002ace0`
- name: `?GetVolumeHandle@CMsftDiscRecorder2@@AEAAJAEAPEAXAEAE@Z`
- size: `268`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, void **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180028d20`

## callees

- `0x18000f740`
- `0x1800140f4`
- `0x18002abd4`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ac13`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18002ac13`
- `OLEAUT32!__imp_SysFreeString` at `0x18002accd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002accd`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ac06`
- `OLEAUT32!__imp_SysStringLen` at `0x18002ac06`
- `KERNEL32!GetLastError` at `0x18002ac6d`
- `KERNEL32!GetLastError` at `0x18002ac6d`
- `KERNEL32!SetErrorMode` at `0x18002ac32`
- `KERNEL32!SetErrorMode` at `0x18002acc4`
- `KERNEL32!SetErrorMode` at `0x18002ac32`
- `KERNEL32!SetErrorMode` at `0x18002acc4`
- `KERNEL32!CreateFileW` at `0x18002ac5e`
- `KERNEL32!CreateFileW` at `0x18002ac5e`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetVolumeHandle(CMsftDiscRecorder2 *this, void **a2, unsigned __int8 *a3)
{
  OLECHAR *v4; // rcx
  unsigned int LastErrorAsHresultForceFailure; // ebx
  UINT v8; // eax
  WCHAR *v9; // rsi
  UINT v10; // ebp
  HANDLE FileW; // rax
  int v12; // edx
  Imapi2Utility *v13; // rcx

  *a2 = (void *)-1LL;
  v4 = (OLECHAR *)*((_QWORD *)this + 15);
  *a3 = 0;
  if ( v4 )
  {
    v8 = SysStringLen(v4);
    v9 = SysAllocStringLen(*((const OLECHAR **)this + 15), v8 - 1);
    if ( v9 )
    {
      LastErrorAsHresultForceFailure = 0;
      v10 = SetErrorMode(0x8001u);
      FileW = CreateFileW(v9, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
      *a2 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        if ( GetLastError() == 21 )
          *a3 = 1;
        LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v13, v12);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            161,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            LastErrorAsHresultForceFailure);
        }
      }
      SetErrorMode(v10);
      SysFreeString(v9);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return LastErrorAsHresultForceFailure;
}

```

## disassembly

```asm
0x18002abd4  push    rbx
0x18002abd6  push    rbp
0x18002abd7  push    rsi
0x18002abd8  push    rdi
0x18002abd9  push    r14
0x18002abdb  sub     rsp, 40h
0x18002abdf  mov     rbx, rcx
0x18002abe2  mov     qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x18002abe9  mov     rcx, [rcx+78h]; pbstr
0x18002abed  mov     rdi, r8
0x18002abf0  mov     byte ptr [r8], 0
0x18002abf4  mov     r14, rdx
0x18002abf7  test    rcx, rcx
0x18002abfa  jnz     short loc_18002AC06
0x18002abfc  mov     ebx, 80004005h
0x18002ac01  jmp     loc_18002ACD3
0x18002ac06  call    cs:__imp_SysStringLen
0x18002ac0c  mov     rcx, [rbx+78h]; strIn
0x18002ac10  lea     edx, [rax-1]; ui
0x18002ac13  call    cs:__imp_SysAllocStringLen
0x18002ac19  mov     rsi, rax
0x18002ac1c  test    rax, rax
0x18002ac1f  jnz     short loc_18002AC2B
0x18002ac21  mov     ebx, 8007000Eh
0x18002ac26  jmp     loc_18002ACD3
0x18002ac2b  mov     ecx, 8001h; uMode
0x18002ac30  xor     ebx, ebx
0x18002ac32  call    cs:__imp_SetErrorMode
0x18002ac38  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18002ac3d  lea     r8d, [rbx+3]; dwShareMode
0x18002ac41  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002ac49  xor     r9d, r9d; lpSecurityAttributes
0x18002ac4c  mov     edx, 0C0000000h; dwDesiredAccess
0x18002ac51  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002ac59  mov     rcx, rsi; lpFileName
0x18002ac5c  mov     ebp, eax
0x18002ac5e  call    cs:__imp_CreateFileW
0x18002ac64  mov     [r14], rax
0x18002ac67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ac6b  jnz     short loc_18002ACC2
0x18002ac6d  call    cs:__imp_GetLastError
0x18002ac73  cmp     eax, 15h
0x18002ac76  jnz     short loc_18002AC7B
0x18002ac78  mov     byte ptr [rdi], 1
0x18002ac7b  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x18002ac80  mov     ebx, eax
0x18002ac82  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac89  lea     rax, WPP_GLOBAL_Control
0x18002ac90  cmp     rcx, rax
0x18002ac93  jz      short loc_18002ACC2
0x18002ac95  test    byte ptr [rcx+0BCh], 4
0x18002ac9c  jz      short loc_18002ACC2
0x18002ac9e  cmp     byte ptr [rcx+0B9h], 3
0x18002aca5  jb      short loc_18002ACC2
0x18002aca7  mov     rcx, [rcx+0B0h]
0x18002acae  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002acb5  mov     edx, 0A1h
0x18002acba  mov     r9d, ebx
0x18002acbd  call    WPP_SF_d
0x18002acc2  mov     ecx, ebp; uMode
0x18002acc4  call    cs:__imp_SetErrorMode
0x18002acca  mov     rcx, rsi; bstrString
0x18002accd  call    cs:__imp_SysFreeString
0x18002acd3  mov     eax, ebx
0x18002acd5  add     rsp, 40h
0x18002acd9  pop     r14
0x18002acdb  pop     rdi
0x18002acdc  pop     rsi
0x18002acdd  pop     rbp
0x18002acde  pop     rbx
0x18002acdf  retn
```
