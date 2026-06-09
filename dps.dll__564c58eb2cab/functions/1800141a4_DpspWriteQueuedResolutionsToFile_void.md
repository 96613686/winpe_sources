# DpspWriteQueuedResolutionsToFile(void *)

- ea: `0x1800141a4`
- end: `0x1800142ed`
- name: `?DpspWriteQueuedResolutionsToFile@@YAJPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180007d30`

## callees

- `0x180009090`
- `0x180014090`
- `0x1800141a4`
- `0x180017a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014272`
- `ntdll!RtlFirstEntrySList` at `0x1800141cc`
- `ntdll!RtlFirstEntrySList` at `0x1800141cc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180014267`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180014267`

## string_xrefs

- `0x1800142c8`: `DpspWriteQueuedResolutionsToFile`

## pseudocode

```c
__int64 __fastcall DpspWriteQueuedResolutionsToFile(HANDLE hFile)
{
  struct __TARGETUSER *EntrySList; // rdi
  signed int LastError; // eax
  signed int v4; // ebx
  int v5; // eax
  int v6; // r8d
  int Args; // eax
  struct __TARGETUSER *v8; // rbx
  signed int v9; // eax
  unsigned int Buffer; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+48h] [rbp+10h] BYREF

  v12 = 0;
  Buffer = 0;
  EntrySList = (struct __TARGETUSER *)RtlFirstEntrySList(&g_QueuedResolutionListHead);
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      LOBYTE(v5) = v4;
      v6 = 1694;
LABEL_18:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspWriteQueuedResolutionsToFile",
        v6,
        (int)L"Error = %d",
        v5);
      return (unsigned int)v4;
    }
  }
  Args = WdipWriteFile(hFile, (char *)&Buffer, 4u, &v12);
  v4 = Args;
  if ( Args >= 0 )
  {
    if ( EntrySList )
    {
      do
      {
        v8 = *(struct __TARGETUSER **)EntrySList;
        if ( (int)DpspWriteQueuedResolutionsForUserToFile((char *)hFile, EntrySList, &Buffer) < 0 )
          break;
        EntrySList = v8;
      }
      while ( v8 );
    }
    if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
    {
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      if ( v4 < 0 )
      {
        LOBYTE(v5) = v4;
        v6 = 1732;
        goto LABEL_18;
      }
    }
    v5 = WdipWriteFile(hFile, (char *)&Buffer, 4u, &v12);
    v4 = v5;
    if ( v5 < 0 )
    {
      v6 = 1741;
      goto LABEL_18;
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspWriteQueuedResolutionsToFile",
      1702,
      (int)L"Error = %d",
      Args);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800141a4  mov     rax, rsp
0x1800141a7  mov     [rax+18h], rbx
0x1800141ab  mov     [rax+20h], rsi
0x1800141af  push    rdi
0x1800141b0  sub     rsp, 30h
0x1800141b4  mov     rsi, rcx
0x1800141b7  mov     dword ptr [rax+10h], 0
0x1800141be  lea     rcx, g_QueuedResolutionListHead; ListHead
0x1800141c5  mov     dword ptr [rax+8], 0
0x1800141cc  call    cs:__imp_RtlFirstEntrySList
0x1800141d2  mov     rdi, rax
0x1800141d5  lea     rax, [rsi+1]
0x1800141d9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800141df  jnz     short loc_180014208
0x1800141e1  call    cs:__imp_GetLastError
0x1800141e7  mov     ebx, eax
0x1800141e9  test    eax, eax
0x1800141eb  jle     short loc_1800141F6
0x1800141ed  movzx   ebx, ax
0x1800141f0  or      ebx, 80070000h
0x1800141f6  test    ebx, ebx
0x1800141f8  jns     short loc_180014208
0x1800141fa  movzx   eax, bx
0x1800141fd  mov     r8d, 69Eh
0x180014203  jmp     loc_1800142BD
0x180014208  lea     r9, [rsp+38h+arg_8]
0x18001420d  mov     r8d, 4; nNumberOfBytesToWrite
0x180014213  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x180014218  mov     rcx, rsi; hFile
0x18001421b  call    WdipWriteFile
0x180014220  mov     ebx, eax
0x180014222  test    eax, eax
0x180014224  jns     short loc_180014238
0x180014226  movzx   ecx, ax
0x180014229  mov     r8d, 6A6h
0x18001422f  mov     dword ptr [rsp+38h+Args], ecx
0x180014233  jmp     loc_1800142C1
0x180014238  test    rdi, rdi
0x18001423b  jz      short loc_18001425C
0x18001423d  mov     rbx, [rdi]
0x180014240  lea     r8, [rsp+38h+Buffer]; unsigned int *
0x180014245  mov     rdx, rdi; struct __TARGETUSER *
0x180014248  mov     rcx, rsi; hFile
0x18001424b  call    ?DpspWriteQueuedResolutionsForUserToFile@@YAJPEAXPEAU__TARGETUSER@@PEAK@Z; DpspWriteQueuedResolutionsForUserToFile(void *,__TARGETUSER *,ulong *)
0x180014250  test    eax, eax
0x180014252  js      short loc_18001425C
0x180014254  mov     rdi, rbx
0x180014257  test    rbx, rbx
0x18001425a  jnz     short loc_18001423D
0x18001425c  xor     r9d, r9d; dwMoveMethod
0x18001425f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180014262  xor     edx, edx; lDistanceToMove
0x180014264  mov     rcx, rsi; hFile
0x180014267  call    cs:__imp_SetFilePointer
0x18001426d  cmp     eax, 0FFFFFFFFh
0x180014270  jnz     short loc_180014296
0x180014272  call    cs:__imp_GetLastError
0x180014278  mov     ebx, eax
0x18001427a  test    eax, eax
0x18001427c  jle     short loc_180014287
0x18001427e  movzx   ebx, ax
0x180014281  or      ebx, 80070000h
0x180014287  test    ebx, ebx
0x180014289  jns     short loc_180014296
0x18001428b  movzx   eax, bx
0x18001428e  mov     r8d, 6C4h
0x180014294  jmp     short loc_1800142BD
0x180014296  lea     r9, [rsp+38h+arg_8]
0x18001429b  mov     r8d, 4; nNumberOfBytesToWrite
0x1800142a1  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x1800142a6  mov     rcx, rsi; hFile
0x1800142a9  call    WdipWriteFile
0x1800142ae  mov     ebx, eax
0x1800142b0  test    eax, eax
0x1800142b2  jns     short loc_1800142DB
0x1800142b4  movzx   eax, ax
0x1800142b7  mov     r8d, 6CDh; int
0x1800142bd  mov     dword ptr [rsp+38h+Args], eax; Args
0x1800142c1  lea     r9, aErrorD; "Error = %d"
0x1800142c8  lea     rdx, aDpspwritequeue_0; "DpspWriteQueuedResolutionsToFile"
0x1800142cf  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800142d6  call    WdipTraceError
0x1800142db  mov     rsi, [rsp+38h+arg_18]
0x1800142e0  mov     eax, ebx
0x1800142e2  mov     rbx, [rsp+38h+arg_10]
0x1800142e7  add     rsp, 30h
0x1800142eb  pop     rdi
0x1800142ec  retn
```
