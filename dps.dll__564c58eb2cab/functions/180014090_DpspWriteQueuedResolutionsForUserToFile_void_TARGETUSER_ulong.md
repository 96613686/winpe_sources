# DpspWriteQueuedResolutionsForUserToFile(void *,__TARGETUSER *,ulong *)

- ea: `0x180014090`
- end: `0x18001419c`
- name: `?DpspWriteQueuedResolutionsForUserToFile@@YAJPEAXPEAU__TARGETUSER@@PEAK@Z`
- size: `268`
- prototype: `__int64 __fastcall(char *hFile, struct __TARGETUSER *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800141a4`

## callees

- `0x180009090`
- `0x180013e68`
- `0x180014090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014130`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014130`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001413f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001413f`

## string_xrefs

- `0x18001417a`: `DpspWriteQueuedResolutionsForUserToFile`

## pseudocode

```c
__int64 __fastcall DpspWriteQueuedResolutionsForUserToFile(char *hFile, struct __TARGETUSER *a2, unsigned int *a3)
{
  char *v3; // r14
  const FILETIME *v5; // rdi
  unsigned int v8; // ebx
  signed int LastError; // eax
  int Args; // eax
  int v11; // r8d
  char *v12; // rbp
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  v3 = (char *)a2 + 72;
  v5 = (const FILETIME *)*((_QWORD *)a2 + 9);
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      LOBYTE(Args) = v8;
      v11 = 1565;
      goto LABEL_19;
    }
  }
  else
  {
    v8 = 0;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspWriteQueuedResolutionsForUserToFile",
      1566,
      (int)L"Error = %d",
      87);
    return v8;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspWriteQueuedResolutionsForUserToFile",
      1567,
      (int)L"Error = %d",
      87);
    return v8;
  }
  if ( v5 == (const FILETIME *)v3 )
    return v8;
  while ( 1 )
  {
    v12 = (char *)*v5;
    if ( (v5[11].dwHighDateTime & 0x20) == 0 )
      goto LABEL_16;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(v5 + 15, &SystemTimeAsFileTime) <= 0 )
      goto LABEL_16;
    Args = DpspWriteQueuedResolutionToFile(hFile, v5);
    v8 = Args;
    if ( Args < 0 )
      break;
    ++*a3;
LABEL_16:
    v5 = (const FILETIME *)v12;
    if ( v12 == v3 )
      return v8;
  }
  v11 = 1581;
LABEL_19:
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
    (int)L"DpspWriteQueuedResolutionsForUserToFile",
    v11,
    (int)L"Error = %d",
    Args);
  return v8;
}

```

## disassembly

```asm
0x180014090  push    rbx
0x180014092  push    rbp
0x180014093  push    rsi
0x180014094  push    rdi
0x180014095  push    r14
0x180014097  push    r15
0x180014099  sub     rsp, 38h
0x18001409d  lea     rax, [rcx-1]
0x1800140a1  mov     qword ptr [rsp+68h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800140aa  lea     r14, [rdx+48h]
0x1800140ae  mov     rsi, r8
0x1800140b1  mov     rdi, [r14]
0x1800140b4  mov     rbp, rdx
0x1800140b7  mov     r15, rcx
0x1800140ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800140be  ja      short loc_1800140DF
0x1800140c0  xor     ebx, ebx
0x1800140c2  test    rbp, rbp
0x1800140c5  jnz     short loc_180014103
0x1800140c7  mov     ebx, 80070057h
0x1800140cc  mov     dword ptr [rsp+68h+Args], 57h ; 'W'
0x1800140d4  mov     r8d, 61Eh
0x1800140da  jmp     loc_180014173
0x1800140df  call    cs:__imp_GetLastError
0x1800140e5  mov     ebx, eax
0x1800140e7  test    eax, eax
0x1800140e9  jle     short loc_1800140F4
0x1800140eb  movzx   ebx, ax
0x1800140ee  or      ebx, 80070000h
0x1800140f4  test    ebx, ebx
0x1800140f6  jns     short loc_1800140C2
0x1800140f8  movzx   eax, bx
0x1800140fb  mov     r8d, 61Dh
0x180014101  jmp     short loc_18001416F
0x180014103  test    rsi, rsi
0x180014106  jnz     short loc_18001411D
0x180014108  mov     ebx, 80070057h
0x18001410d  mov     dword ptr [rsp+68h+Args], 57h ; 'W'
0x180014115  mov     r8d, 61Fh
0x18001411b  jmp     short loc_180014173
0x18001411d  cmp     rdi, r14
0x180014120  jz      short loc_18001418D
0x180014122  test    byte ptr [rdi+5Ch], 20h
0x180014126  mov     rbp, [rdi]
0x180014129  jz      short loc_18001415C
0x18001412b  lea     rcx, [rsp+68h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014130  call    cs:__imp_GetSystemTimeAsFileTime
0x180014136  lea     rcx, [rdi+78h]; lpFileTime1
0x18001413a  lea     rdx, [rsp+68h+SystemTimeAsFileTime]; lpFileTime2
0x18001413f  call    cs:__imp_CompareFileTime
0x180014145  test    eax, eax
0x180014147  jle     short loc_18001415C
0x180014149  mov     rdx, rdi; lpBuffer
0x18001414c  mov     rcx, r15; hFile
0x18001414f  call    ?DpspWriteQueuedResolutionToFile@@YAJPEAXPEAUINSTANCEINFO@@@Z; DpspWriteQueuedResolutionToFile(void *,INSTANCEINFO *)
0x180014154  mov     ebx, eax
0x180014156  test    eax, eax
0x180014158  js      short loc_180014166
0x18001415a  inc     dword ptr [rsi]
0x18001415c  mov     rdi, rbp
0x18001415f  cmp     rbp, r14
0x180014162  jnz     short loc_180014122
0x180014164  jmp     short loc_18001418D
0x180014166  movzx   eax, ax
0x180014169  mov     r8d, 62Dh; int
0x18001416f  mov     dword ptr [rsp+68h+Args], eax; Args
0x180014173  lea     r9, aErrorD; "Error = %d"
0x18001417a  lea     rdx, aDpspwritequeue_1; "DpspWriteQueuedResolutionsForUserToFile"
0x180014181  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180014188  call    WdipTraceError
0x18001418d  mov     eax, ebx
0x18001418f  add     rsp, 38h
0x180014193  pop     r15
0x180014195  pop     r14
0x180014197  pop     rdi
0x180014198  pop     rsi
0x180014199  pop     rbp
0x18001419a  pop     rbx
0x18001419b  retn
```
