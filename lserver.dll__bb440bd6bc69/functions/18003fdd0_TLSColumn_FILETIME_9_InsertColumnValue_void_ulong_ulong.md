# TLSColumn<_FILETIME,9>::InsertColumnValue(void *,ulong,ulong)

- ea: `0x18003fdd0`
- end: `0x18003feac`
- name: `?InsertColumnValue@?$TLSColumn@U_FILETIME@@$08@@UEAAJPEAXKK@Z`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18003fdd0`
- `0x18006c084`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18003fe38`
- `KERNEL32!GetSystemTime` at `0x18003fe38`
- `KERNEL32!CompareFileTime` at `0x18003fe23`
- `KERNEL32!CompareFileTime` at `0x18003fe23`
- `KERNEL32!SystemTimeToFileTime` at `0x18003fe4e`
- `KERNEL32!SystemTimeToFileTime` at `0x18003fe4e`

## pseudocode

```c
__int64 __fastcall TLSColumn<_FILETIME,9>::InsertColumnValue(__int64 a1, FILETIME *a2, int a3)
{
  _DWORD *v4; // rdx
  __int64 result; // rax
  unsigned int v7; // r9d
  FILETIME FileTime1; // [rsp+20h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  v4 = *(_DWORD **)(a1 + 8);
  SystemTime = 0;
  if ( !v4 )
    return 4294966267LL;
  if ( a3 == 8 && a2 )
  {
    FileTime1 = 0;
    if ( CompareFileTime(&FileTime1, a2) )
    {
      FileTime1 = *a2;
    }
    else
    {
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, &FileTime1);
      *a2 = FileTime1;
    }
    return JBColumn::InsertColumn(*(JBColumn **)(a1 + 8), &FileTime1, 8u, v7);
  }
  else
  {
    result = 4294966293LL;
    *v4 = -1003;
  }
  return result;
}

```

## disassembly

```asm
0x18003fdd0  mov     [rsp+arg_10], rbx
0x18003fdd5  push    rdi
0x18003fdd6  sub     rsp, 40h
0x18003fdda  mov     rax, cs:__security_cookie
0x18003fde1  xor     rax, rsp
0x18003fde4  mov     [rsp+48h+var_10], rax
0x18003fde9  mov     rbx, rdx
0x18003fdec  xorps   xmm0, xmm0
0x18003fdef  mov     rdx, [rcx+8]
0x18003fdf3  mov     rdi, rcx
0x18003fdf6  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x18003fdfb  test    rdx, rdx
0x18003fdfe  jnz     short loc_18003FE0A
0x18003fe00  mov     eax, 0FFFFFBFBh
0x18003fe05  jmp     loc_18003FE93
0x18003fe0a  cmp     r8d, 8
0x18003fe0e  jnz     short loc_18003FE8C
0x18003fe10  test    rbx, rbx
0x18003fe13  jz      short loc_18003FE8C
0x18003fe15  and     qword ptr [rsp+48h+FileTime1.dwLowDateTime], 0
0x18003fe1b  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x18003fe20  mov     rdx, rbx; lpFileTime2
0x18003fe23  call    cs:__imp_CompareFileTime
0x18003fe2a  nop     dword ptr [rax+rax+00h]
0x18003fe2f  test    eax, eax
0x18003fe31  jnz     short loc_18003FE69
0x18003fe33  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x18003fe38  call    cs:__imp_GetSystemTime
0x18003fe3f  nop     dword ptr [rax+rax+00h]
0x18003fe44  lea     rdx, [rsp+48h+FileTime1]; lpFileTime
0x18003fe49  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x18003fe4e  call    cs:__imp_SystemTimeToFileTime
0x18003fe55  nop     dword ptr [rax+rax+00h]
0x18003fe5a  mov     eax, [rsp+48h+FileTime1.dwLowDateTime]
0x18003fe5e  mov     [rbx], eax
0x18003fe60  mov     eax, [rsp+48h+FileTime1.dwHighDateTime]
0x18003fe64  mov     [rbx+4], eax
0x18003fe67  jmp     short loc_18003FE76
0x18003fe69  mov     eax, [rbx]
0x18003fe6b  mov     [rsp+48h+FileTime1.dwLowDateTime], eax
0x18003fe6f  mov     eax, [rbx+4]
0x18003fe72  mov     [rsp+48h+FileTime1.dwHighDateTime], eax
0x18003fe76  mov     rcx, [rdi+8]; this
0x18003fe7a  lea     rdx, [rsp+48h+FileTime1]; pvData
0x18003fe7f  mov     r8d, 8; cbData
0x18003fe85  call    ?InsertColumn@JBColumn@@QEAAHPEAXKK@Z; JBColumn::InsertColumn(void *,ulong,ulong)
0x18003fe8a  jmp     short loc_18003FE93
0x18003fe8c  mov     eax, 0FFFFFC15h
0x18003fe91  mov     [rdx], eax
0x18003fe93  mov     rcx, [rsp+48h+var_10]
0x18003fe98  xor     rcx, rsp; StackCookie
0x18003fe9b  call    __security_check_cookie
0x18003fea0  mov     rbx, [rsp+48h+arg_10]
0x18003fea5  add     rsp, 40h
0x18003fea9  pop     rdi
0x18003feaa  retn
```
