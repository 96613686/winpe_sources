# CreateTiffFileForJob(_JOB_QUEUE *)

- ea: `0x14002efb8`
- end: `0x14002f162`
- name: `?CreateTiffFileForJob@@YAHPEAU_JOB_QUEUE@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14002f9f0`
- `0x1400314a8`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14002eb78`
- `0x14002efb8`
- `0x1400354bc`
- `0x140067168`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002f055`
- `KERNEL32!GetLastError` at `0x14002f098`
- `KERNEL32!GetLastError` at `0x14002f0f7`
- `KERNEL32!GetLastError` at `0x14002f055`
- `KERNEL32!GetLastError` at `0x14002f098`
- `KERNEL32!GetLastError` at `0x14002f0f7`
- `KERNEL32!SetLastError` at `0x14002f12d`
- `KERNEL32!SetLastError` at `0x14002f12d`
- `KERNEL32!DeleteFileW` at `0x14002f0d5`
- `KERNEL32!DeleteFileW` at `0x14002f0d5`

## pseudocode

```c
__int64 __fastcall CreateTiffFileForJob(struct _JOB_QUEUE *a1)
{
  DWORD LastError; // eax
  __int64 v4; // rax
  DWORD v5; // eax
  DWORD v6; // ebx
  char v7; // al
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  memset_0(FileName, 0, 0x208u);
  if ( !(unsigned int)CreateTiffFile(a1, L"FRT", FileName) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
    }
    return 0;
  }
  v4 = StringDup(FileName);
  *((_QWORD *)a1 + 9) = v4;
  if ( !v4 )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v5);
    }
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = GetLastError();
      WPP_SF_lSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *((_DWORD *)a1 + 8),
        (__int64)FileName,
        v7);
    }
    SetLastError(v6);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14002efb8  mov     [rsp+arg_8], rbx
0x14002efbd  mov     [rsp+arg_10], rbp
0x14002efc2  push    rdi
0x14002efc3  sub     rsp, 250h
0x14002efca  mov     rax, cs:__security_cookie
0x14002efd1  xor     rax, rsp
0x14002efd4  mov     [rsp+258h+var_18], rax
0x14002efdc  mov     rdi, rcx
0x14002efdf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002efe6  lea     rbp, WPP_GLOBAL_Control
0x14002efed  cmp     rcx, rbp
0x14002eff0  jz      short loc_14002F013
0x14002eff2  test    byte ptr [rcx+1Ch], 4
0x14002eff6  jz      short loc_14002F013
0x14002eff8  cmp     byte ptr [rcx+19h], 5
0x14002effc  jb      short loc_14002F013
0x14002effe  mov     rcx, [rcx+10h]
0x14002f002  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f009  mov     edx, 38h ; '8'
0x14002f00e  call    WPP_SF_
0x14002f013  xor     edx, edx; Val
0x14002f015  lea     rcx, [rsp+258h+FileName]; void *
0x14002f01a  mov     r8d, 208h; Size
0x14002f020  call    memset_0
0x14002f025  lea     r8, [rsp+258h+FileName]; unsigned __int16 *
0x14002f02a  mov     rcx, rdi; struct _JOB_QUEUE *
0x14002f02d  lea     rdx, aFrt; "FRT"
0x14002f034  call    ?CreateTiffFile@@YAHPEAU_JOB_QUEUE@@PEBGPEAGK@Z; CreateTiffFile(_JOB_QUEUE *,ushort const *,ushort *,ulong)
0x14002f039  test    eax, eax
0x14002f03b  jnz     short loc_14002F081
0x14002f03d  mov     rax, cs:WPP_GLOBAL_Control
0x14002f044  cmp     rax, rbp
0x14002f047  jz      short loc_14002F07A
0x14002f049  test    byte ptr [rax+1Ch], 4
0x14002f04d  jz      short loc_14002F07A
0x14002f04f  cmp     byte ptr [rax+19h], 2
0x14002f053  jb      short loc_14002F07A
0x14002f055  call    cs:__imp_GetLastError
0x14002f05b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f062  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f069  mov     edx, 39h ; '9'
0x14002f06e  mov     r9d, eax
0x14002f071  mov     rcx, [rcx+10h]
0x14002f075  call    WPP_SF_d
0x14002f07a  xor     eax, eax
0x14002f07c  jmp     loc_14002F13D
0x14002f081  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x14002f086  call    StringDup
0x14002f08b  mov     [rdi+48h], rax
0x14002f08f  test    rax, rax
0x14002f092  jnz     loc_14002F138
0x14002f098  call    cs:__imp_GetLastError
0x14002f09e  mov     ebx, eax
0x14002f0a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f0a7  cmp     rcx, rbp
0x14002f0aa  jz      short loc_14002F0D0
0x14002f0ac  test    byte ptr [rcx+1Ch], 4
0x14002f0b0  jz      short loc_14002F0D0
0x14002f0b2  cmp     byte ptr [rcx+19h], 2
0x14002f0b6  jb      short loc_14002F0D0
0x14002f0b8  mov     rcx, [rcx+10h]
0x14002f0bc  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f0c3  mov     edx, 3Ah ; ':'
0x14002f0c8  mov     r9d, eax
0x14002f0cb  call    WPP_SF_d
0x14002f0d0  lea     rcx, [rsp+258h+FileName]; lpFileName
0x14002f0d5  call    cs:__imp_DeleteFileW
0x14002f0db  test    eax, eax
0x14002f0dd  jnz     short loc_14002F12B
0x14002f0df  mov     rax, cs:WPP_GLOBAL_Control
0x14002f0e6  cmp     rax, rbp
0x14002f0e9  jz      short loc_14002F12B
0x14002f0eb  test    byte ptr [rax+1Ch], 4
0x14002f0ef  jz      short loc_14002F12B
0x14002f0f1  cmp     byte ptr [rax+19h], 2
0x14002f0f5  jb      short loc_14002F12B
0x14002f0f7  call    cs:__imp_GetLastError
0x14002f0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f104  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f10b  mov     r9d, [rdi+20h]
0x14002f10f  mov     edx, 3Bh ; ';'
0x14002f114  mov     [rsp+258h+var_230], eax
0x14002f118  lea     rax, [rsp+258h+FileName]
0x14002f11d  mov     [rsp+258h+var_238], rax
0x14002f122  mov     rcx, [rcx+10h]
0x14002f126  call    WPP_SF_lSl
0x14002f12b  mov     ecx, ebx; dwErrCode
0x14002f12d  call    cs:__imp_SetLastError
0x14002f133  jmp     loc_14002F07A
0x14002f138  mov     eax, 1
0x14002f13d  mov     rcx, [rsp+258h+var_18]
0x14002f145  xor     rcx, rsp; StackCookie
0x14002f148  call    __security_check_cookie
0x14002f14d  lea     r11, [rsp+258h+var_8]
0x14002f155  mov     rbx, [r11+18h]
0x14002f159  mov     rbp, [r11+20h]
0x14002f15d  mov     rsp, r11
0x14002f160  pop     rdi
0x14002f161  retn
```
