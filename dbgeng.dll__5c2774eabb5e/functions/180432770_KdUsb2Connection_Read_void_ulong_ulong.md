# KdUsb2Connection::Read(void *,ulong,ulong *)

- ea: `0x180432770`
- end: `0x180432976`
- name: `?Read@KdUsb2Connection@@UEAAJPEAXKPEAK@Z`
- size: `518`
- prototype: `int(KdUsb2Connection *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800db578`
- `0x1803f6e1c`
- `0x180431fe0`
- `0x180432770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1804328cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1804328cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18043291c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180432905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18043291c`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x180432817`
- `api-ms-win-core-misc-l1-1-0!Sleep` at `0x180432817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180432897`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180432897`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1804327fb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1804327fb`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1804328f1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1804328f1`

## string_xrefs

- `0x180432944`: `USB: Read %d bytes of %d\n`
- `0x1804328af`: `USB: Read error %d\n`
- `0x180432888`: `USB: Read error Not Connected, closing\n`
- `0x1804327c8`: `USB: Read opened\n`

## pseudocode

```c
__int64 __fastcall KdUsb2Connection::Read(KdUsb2Connection *this, void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v8; // ebx
  void **v9; // rsi
  const unsigned __int16 *v10; // rcx
  KdConnection *v11; // rcx
  DWORD LastError; // ebp
  signed int v13; // eax
  void *v14; // rcx
  signed int v15; // eax

  v8 = -2147467259;
  if ( a4 )
    *a4 = 0;
  v9 = (void **)((char *)this + 32);
  if ( !*((_QWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 47) < 2u )
      v10 = 0;
    else
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 22);
    v8 = OpenUSB2Channel(v10, v9);
    if ( v8 )
    {
      Sleep(0x1F4u);
      return v8;
    }
    LnkOut(0x80000000, L"USB: Read opened\n");
  }
  if ( !*((_DWORD *)this + 2110) )
  {
    if ( ReadFile(*v9, a2, a3, a4, (LPOVERLAPPED)((char *)this + 72)) )
    {
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        *((_DWORD *)this + 2110) = 1;
      }
      else
      {
        if ( GetLastError() )
        {
          v13 = GetLastError();
          v8 = v13;
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
        }
        else
        {
          v8 = -2147467259;
        }
        if ( LastError == 1167 )
        {
          LnkOut(0x80000000, L"USB: Read error Not Connected, closing\n");
          CloseHandle(*v9);
          *v9 = 0;
        }
        else
        {
          LnkOut(0x80000000, L"USB: Read error %d\n", LastError);
        }
      }
    }
    if ( !*((_DWORD *)this + 2110) )
      goto LABEL_30;
  }
  if ( WaitForSingleObject(*((HANDLE *)this + 12), 0x64u)
    || (v14 = *v9, *((_DWORD *)this + 2110) = 0, !GetOverlappedResult(v14, (LPOVERLAPPED)((char *)this + 72), a4, 1)) )
  {
    if ( !GetLastError() )
      return (unsigned int)-2147467259;
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
LABEL_30:
    if ( v8 )
      return v8;
    goto LABEL_31;
  }
  v8 = 0;
LABEL_31:
  if ( (*((_BYTE *)this + 56) & 1) != 0 )
    KdConnection::OutputIo(v11, L"USB: Read %d bytes of %d\n", a2, a3, *a4);
  *((_QWORD *)this + 18) += *a4;
  return v8;
}

```

## disassembly

```asm
0x180432770  push    rbx
0x180432772  push    rbp
0x180432773  push    rsi
0x180432774  push    rdi
0x180432775  push    r12
0x180432777  push    r14
0x180432779  push    r15
0x18043277b  sub     rsp, 30h
0x18043277f  mov     r14, r9
0x180432782  mov     r15d, r8d
0x180432785  mov     r12, rdx
0x180432788  mov     rdi, rcx
0x18043278b  mov     ebx, 80004005h
0x180432790  test    r9, r9
0x180432793  jz      short loc_18043279C
0x180432795  mov     dword ptr [r9], 0
0x18043279c  lea     rsi, [rcx+20h]
0x1804327a0  cmp     qword ptr [rsi], 0
0x1804327a4  jnz     short loc_1804327D9
0x1804327a6  cmp     dword ptr [rcx+0BCh], 2
0x1804327ad  jb      short loc_1804327B8
0x1804327af  mov     rcx, [rcx+0B0h]
0x1804327b6  jmp     short loc_1804327BA
0x1804327b8  xor     ecx, ecx; Src
0x1804327ba  mov     rdx, rsi; void **
0x1804327bd  call    ?OpenUSB2Channel@@YAJPEBGPEAPEAX@Z; OpenUSB2Channel(ushort const *,void * *)
0x1804327c2  mov     ebx, eax
0x1804327c4  test    eax, eax
0x1804327c6  jnz     short loc_180432812
0x1804327c8  lea     rdx, aUsbReadOpened; "USB: Read opened\n"
0x1804327cf  mov     ecx, 80000000h; unsigned int
0x1804327d4  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804327d9  cmp     dword ptr [rdi+20F8h], 0
0x1804327e0  jnz     loc_1804328C4
0x1804327e6  mov     rcx, [rsi]; hFile
0x1804327e9  lea     rax, [rdi+48h]
0x1804327ed  mov     r9, r14; lpNumberOfBytesRead
0x1804327f0  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x1804327f5  mov     r8d, r15d; nNumberOfBytesToRead
0x1804327f8  mov     rdx, r12; lpBuffer
0x1804327fb  call    cs:__imp_ReadFile
0x180432802  nop     dword ptr [rax+rax+00h]
0x180432807  test    eax, eax
0x180432809  jz      short loc_180432828
0x18043280b  xor     ebx, ebx
0x18043280d  jmp     loc_1804328BB
0x180432812  mov     ecx, 1F4h; dwMilliseconds
0x180432817  call    cs:__imp_Sleep
0x18043281e  nop     dword ptr [rax+rax+00h]
0x180432823  jmp     loc_180432964
0x180432828  call    cs:__imp_GetLastError
0x18043282f  nop     dword ptr [rax+rax+00h]
0x180432834  mov     ebp, eax
0x180432836  cmp     eax, 3E5h
0x18043283b  jnz     short loc_180432849
0x18043283d  mov     dword ptr [rdi+20F8h], 1
0x180432847  jmp     short loc_1804328BB
0x180432849  call    cs:__imp_GetLastError
0x180432850  nop     dword ptr [rax+rax+00h]
0x180432855  test    eax, eax
0x180432857  jnz     short loc_180432860
0x180432859  mov     ebx, 80004005h
0x18043285e  jmp     short loc_18043287B
0x180432860  call    cs:__imp_GetLastError
0x180432867  nop     dword ptr [rax+rax+00h]
0x18043286c  mov     ebx, eax
0x18043286e  test    eax, eax
0x180432870  jle     short loc_18043287B
0x180432872  movzx   ebx, ax
0x180432875  or      ebx, 80070000h
0x18043287b  mov     ecx, 80000000h; unsigned int
0x180432880  cmp     ebp, 48Fh
0x180432886  jnz     short loc_1804328AC
0x180432888  lea     rdx, aUsbReadErrorNo; "USB: Read error Not Connected, closing"...
0x18043288f  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432894  mov     rcx, [rsi]; hObject
0x180432897  call    cs:__imp_CloseHandle
0x18043289e  nop     dword ptr [rax+rax+00h]
0x1804328a3  mov     qword ptr [rsi], 0
0x1804328aa  jmp     short loc_1804328BB
0x1804328ac  mov     r8d, ebp
0x1804328af  lea     rdx, aUsbReadErrorD; "USB: Read error %d\n"
0x1804328b6  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804328bb  cmp     dword ptr [rdi+20F8h], 0
0x1804328c2  jz      short loc_180432937
0x1804328c4  mov     rcx, [rdi+60h]; hHandle
0x1804328c8  mov     edx, 64h ; 'd'; dwMilliseconds
0x1804328cd  call    cs:__imp_WaitForSingleObject
0x1804328d4  nop     dword ptr [rax+rax+00h]
0x1804328d9  test    eax, eax
0x1804328db  jnz     short loc_180432905
0x1804328dd  mov     rcx, [rsi]; hFile
0x1804328e0  lea     rdx, [rdi+48h]; lpOverlapped
0x1804328e4  lea     r9d, [rax+1]; bWait
0x1804328e8  mov     [rdi+20F8h], eax
0x1804328ee  mov     r8, r14; lpNumberOfBytesTransferred
0x1804328f1  call    cs:__imp_GetOverlappedResult
0x1804328f8  nop     dword ptr [rax+rax+00h]
0x1804328fd  test    eax, eax
0x1804328ff  jz      short loc_180432905
0x180432901  xor     ebx, ebx
0x180432903  jmp     short loc_18043293B
0x180432905  call    cs:__imp_GetLastError
0x18043290c  nop     dword ptr [rax+rax+00h]
0x180432911  test    eax, eax
0x180432913  jnz     short loc_18043291C
0x180432915  mov     ebx, 80004005h
0x18043291a  jmp     short loc_180432964
0x18043291c  call    cs:__imp_GetLastError
0x180432923  nop     dword ptr [rax+rax+00h]
0x180432928  mov     ebx, eax
0x18043292a  test    eax, eax
0x18043292c  jle     short loc_180432937
0x18043292e  movzx   ebx, ax
0x180432931  or      ebx, 80070000h
0x180432937  test    ebx, ebx
0x180432939  jnz     short loc_180432964
0x18043293b  test    byte ptr [rdi+38h], 1
0x18043293f  jz      short loc_18043295A
0x180432941  mov     eax, [r14]
0x180432944  lea     rdx, aUsbReadDBytesO; "USB: Read %d bytes of %d\n"
0x18043294b  mov     r9d, r15d; unsigned int
0x18043294e  mov     dword ptr [rsp+68h+lpOverlapped], eax; unsigned int
0x180432952  mov     r8, r12; void *
0x180432955  call    ?OutputIo@KdConnection@@QEAAXPEAGPEAXKK@Z; KdConnection::OutputIo(ushort *,void *,ulong,ulong)
0x18043295a  mov     eax, [r14]
0x18043295d  add     [rdi+90h], rax
0x180432964  mov     eax, ebx
0x180432966  add     rsp, 30h
0x18043296a  pop     r15
0x18043296c  pop     r14
0x18043296e  pop     r12
0x180432970  pop     rdi
0x180432971  pop     rsi
0x180432972  pop     rbp
0x180432973  pop     rbx
0x180432974  retn
```
