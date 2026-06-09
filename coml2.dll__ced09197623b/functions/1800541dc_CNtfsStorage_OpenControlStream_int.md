# CNtfsStorage::OpenControlStream(int)

- ea: `0x1800541dc`
- end: `0x1800543d5`
- name: `?OpenControlStream@CNtfsStorage@@IEAAJH@Z`
- size: `505`
- prototype: `__int64 __fastcall(CNtfsStorage *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180053aa4`

## callees

- `0x180033a00`
- `0x180033b54`
- `0x180033dd0`
- `0x18003e304`
- `0x180042800`
- `0x1800541dc`

## import_xrefs

- `ntdll!NtClose` at `0x180054300`
- `ntdll!NtClose` at `0x180054300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054367`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005435d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005435d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005429a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005429a`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::OpenControlStream(CNtfsStorage *this, int a2)
{
  unsigned int v4; // ebx
  int v5; // r9d
  void *v6; // rcx
  void *v7; // rbx
  int IsControlStreamExtant; // r14d
  unsigned int v9; // r8d
  int v10; // eax
  __int64 v11; // rsi
  signed int LastError; // eax
  __int16 v14; // ax
  GUID v15; // xmm0
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD Buffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[528]; // [rsp+70h] [rbp-90h] BYREF

  Handle = (HANDLE)-1LL;
  NumberOfBytesRead = 0;
  v4 = 0;
  memset(Buffer, 0, 24);
  CNtfsStreamName::CNtfsStreamName((CNtfsStreamName *)v21, L"{4c8cc155-6c1e-11d1-8e41-00c04fb9386d}");
  if ( *((_QWORD *)this + 14) != -1 )
    return v4;
  if ( !a2 && (*((_BYTE *)this + 72) & 3) == 0 )
  {
    v6 = (void *)*((_QWORD *)this + 13);
    if ( v6 != (void *)-1LL )
    {
      lpMem = 0;
      v18 = 0;
      if ( (int)EnumNtStreams(v6, (struct _FILE_STREAM_INFORMATION **)&lpMem, &v18, v5) >= 0 )
      {
        v7 = lpMem;
        IsControlStreamExtant = CNtfsStorage::IsControlStreamExtant((struct _FILE_STREAM_INFORMATION *)lpMem);
        if ( v7 )
          HeapFree(g_hHeap, 0, v7);
        if ( !IsControlStreamExtant )
          return 0;
      }
    }
  }
  v9 = *((_DWORD *)this + 18);
  if ( !a2 && (v9 & 3) != 0 )
    v9 |= 0x1000u;
  v10 = CNtfsStorage::OpenNtStream(this, (const struct CNtfsStreamName *)v21, v9, 1u, a2, &Handle);
  v4 = v10;
  if ( v10 == -2147287038 )
  {
    if ( !a2 && (*((_BYTE *)this + 72) & 3) == 0 )
      v4 = 0;
    goto LABEL_17;
  }
  if ( v10 < 0 )
  {
LABEL_17:
    v11 = (__int64)Handle;
    goto LABEL_18;
  }
  v11 = (__int64)Handle;
  memset(Buffer, 0, 24);
  if ( !ReadFile(Handle, Buffer, 0x18u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  v14 = 0;
  if ( NumberOfBytesRead == 24 )
  {
    if ( LOWORD(Buffer[0]) )
    {
      v4 = -2147286789;
      goto LABEL_18;
    }
    v15 = *(GUID *)((char *)Buffer + 8);
    *((_DWORD *)this + 31) = DWORD1(Buffer[0]);
    v14 = WORD1(Buffer[0]);
  }
  else
  {
    *((_DWORD *)this + 31) = 0;
    v15 = GUID_NULL;
  }
  *((_QWORD *)this + 14) = v11;
  v11 = -1;
  *((_WORD *)this + 60) = v14;
  *((GUID *)this + 8) = v15;
LABEL_18:
  if ( v11 != -1 )
    NtClose((HANDLE)v11);
  return v4;
}

```

## disassembly

```asm
0x1800541dc  mov     [rsp-8+arg_8], rbx
0x1800541e1  mov     [rsp-8+arg_10], rsi
0x1800541e6  push    rbp
0x1800541e7  push    rdi
0x1800541e8  push    r14
0x1800541ea  lea     rbp, [rsp-190h]
0x1800541f2  sub     rsp, 290h
0x1800541f9  mov     rax, cs:__security_cookie
0x180054200  xor     rax, rsp
0x180054203  mov     [rbp+1A0h+var_20], rax
0x18005420a  xor     eax, eax
0x18005420c  mov     [rsp+2A0h+Handle], 0FFFFFFFFFFFFFFFFh
0x180054215  mov     esi, edx
0x180054217  mov     [rsp+2A0h+var_240], rax
0x18005421c  mov     rdi, rcx
0x18005421f  mov     [rsp+2A0h+NumberOfBytesRead], eax
0x180054223  xorps   xmm0, xmm0
0x180054226  lea     rdx, a4c8cc1556c1e11; "{4c8cc155-6c1e-11d1-8e41-00c04fb9386d}"
0x18005422d  lea     rcx, [rsp+2A0h+var_230]; this
0x180054232  xor     ebx, ebx
0x180054234  movups  [rsp+2A0h+Buffer], xmm0
0x180054239  call    ??0CNtfsStreamName@@QEAA@PEBG@Z; CNtfsStreamName::CNtfsStreamName(ushort const *)
0x18005423e  cmp     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x180054243  jnz     loc_180054306
0x180054249  test    esi, esi
0x18005424b  jnz     short loc_1800542A9
0x18005424d  test    byte ptr [rdi+48h], 3
0x180054251  jnz     short loc_1800542A9
0x180054253  mov     rcx, [rdi+68h]; FileHandle
0x180054257  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005425b  jz      short loc_1800542A9
0x18005425d  lea     r8, [rsp+2A0h+var_260]; unsigned int *
0x180054262  mov     [rsp+2A0h+lpMem], rbx
0x180054267  lea     rdx, [rsp+2A0h+lpMem]; struct _FILE_STREAM_INFORMATION **
0x18005426c  mov     [rsp+2A0h+var_260], ebx
0x180054270  call    ?EnumNtStreams@@YAJPEAXPEAPEAU_FILE_STREAM_INFORMATION@@PEAKH@Z; EnumNtStreams(void *,_FILE_STREAM_INFORMATION * *,ulong *,int)
0x180054275  test    eax, eax
0x180054277  js      short loc_1800542A9
0x180054279  mov     rbx, [rsp+2A0h+lpMem]
0x18005427e  mov     rcx, rbx; struct _FILE_STREAM_INFORMATION *
0x180054281  call    ?IsControlStreamExtant@CNtfsStorage@@CAHPEAU_FILE_STREAM_INFORMATION@@@Z; CNtfsStorage::IsControlStreamExtant(_FILE_STREAM_INFORMATION *)
0x180054286  mov     r14d, eax
0x180054289  test    rbx, rbx
0x18005428c  jz      short loc_1800542A0
0x18005428e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180054295  mov     r8, rbx; lpMem
0x180054298  xor     edx, edx; dwFlags
0x18005429a  call    cs:__imp_HeapFree
0x1800542a0  test    r14d, r14d
0x1800542a3  jnz     short loc_1800542A9
0x1800542a5  xor     ebx, ebx
0x1800542a7  jmp     short loc_180054306
0x1800542a9  mov     r8d, [rdi+48h]
0x1800542ad  test    esi, esi
0x1800542af  jnz     short loc_1800542BC
0x1800542b1  test    r8b, 3
0x1800542b5  jz      short loc_1800542BC
0x1800542b7  bts     r8d, 0Ch; unsigned int
0x1800542bc  lea     rax, [rsp+2A0h+Handle]
0x1800542c1  mov     r9d, 1; unsigned int
0x1800542c7  mov     [rsp+2A0h+var_278], rax; void **
0x1800542cc  lea     rdx, [rsp+2A0h+var_230]; struct CNtfsStreamName *
0x1800542d1  mov     rcx, rdi; this
0x1800542d4  mov     dword ptr [rsp+2A0h+lpOverlapped], esi; int
0x1800542d8  call    ?OpenNtStream@CNtfsStorage@@AEAAJAEBVCNtfsStreamName@@KKHPEAPEAX@Z; CNtfsStorage::OpenNtStream(CNtfsStreamName const &,ulong,ulong,int,void * *)
0x1800542dd  mov     ebx, eax
0x1800542df  cmp     eax, 80030002h
0x1800542e4  jnz     short loc_18005432F
0x1800542e6  test    esi, esi
0x1800542e8  jnz     short loc_1800542F2
0x1800542ea  test    byte ptr [rdi+48h], 3
0x1800542ee  jnz     short loc_1800542F2
0x1800542f0  xor     ebx, ebx
0x1800542f2  mov     rsi, [rsp+2A0h+Handle]
0x1800542f7  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800542fb  jz      short loc_180054306
0x1800542fd  mov     rcx, rsi; Handle
0x180054300  call    cs:__imp_NtClose
0x180054306  mov     eax, ebx
0x180054308  mov     rcx, [rbp+1A0h+var_20]
0x18005430f  xor     rcx, rsp; StackCookie
0x180054312  call    __security_check_cookie
0x180054317  lea     r11, [rsp+2A0h+var_10]
0x18005431f  mov     rbx, [r11+28h]
0x180054323  mov     rsi, [r11+30h]
0x180054327  mov     rsp, r11
0x18005432a  pop     r14
0x18005432c  pop     rdi
0x18005432d  pop     rbp
0x18005432e  retn
0x18005432f  test    eax, eax
0x180054331  js      short loc_1800542F2
0x180054333  mov     rsi, [rsp+2A0h+Handle]
0x180054338  lea     r9, [rsp+2A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005433d  xor     eax, eax
0x18005433f  lea     rdx, [rsp+2A0h+Buffer]; lpBuffer
0x180054344  xorps   xmm0, xmm0
0x180054347  mov     [rsp+2A0h+var_240], rax
0x18005434c  mov     rcx, rsi; hFile
0x18005434f  mov     [rsp+2A0h+lpOverlapped], rax; lpOverlapped
0x180054354  movups  [rsp+2A0h+Buffer], xmm0
0x180054359  lea     r8d, [rax+18h]; nNumberOfBytesToRead
0x18005435d  call    cs:__imp_ReadFile
0x180054363  test    eax, eax
0x180054365  jnz     short loc_180054381
0x180054367  call    cs:__imp_GetLastError
0x18005436d  mov     ebx, eax
0x18005436f  test    eax, eax
0x180054371  jle     short loc_1800542F7
0x180054373  movzx   ebx, ax
0x180054376  or      ebx, 80070000h
0x18005437c  jmp     loc_1800542F7
0x180054381  xor     eax, eax
0x180054383  cmp     [rsp+2A0h+NumberOfBytesRead], 18h
0x180054388  jnz     short loc_1800543AE
0x18005438a  cmp     ax, word ptr [rsp+2A0h+Buffer]
0x18005438f  jz      short loc_18005439B
0x180054391  mov     ebx, 800300FBh
0x180054396  jmp     loc_1800542F7
0x18005439b  mov     eax, dword ptr [rsp+2A0h+Buffer+4]
0x18005439f  movups  xmm0, [rsp+2A0h+Buffer+8]
0x1800543a4  mov     [rdi+7Ch], eax
0x1800543a7  movzx   eax, word ptr [rsp+2A0h+Buffer+2]
0x1800543ac  jmp     short loc_1800543BC
0x1800543ae  mov     dword ptr [rdi+7Ch], 0
0x1800543b5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800543bc  mov     [rdi+70h], rsi
0x1800543c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800543c4  mov     [rdi+78h], ax
0x1800543c8  movdqu  xmmword ptr [rdi+80h], xmm0
0x1800543d0  jmp     loc_1800542F7
```
