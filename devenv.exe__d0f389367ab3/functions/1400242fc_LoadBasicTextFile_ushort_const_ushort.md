# LoadBasicTextFile(ushort const *,ushort * *)

- ea: `0x1400242fc`
- end: `0x1400246ac`
- name: `?LoadBasicTextFile@@YAJPEBGPEAPEAG@Z`
- size: `944`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400242a4`

## callees

- `0x140001020`
- `0x1400162c0`
- `0x1400242fc`
- `0x1400246b0`
- `0x1400248f0`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1400243de`
- `KERNEL32!MapViewOfFile` at `0x1400243de`
- `KERNEL32!CreateFileMappingW` at `0x1400243b5`
- `KERNEL32!CreateFileMappingW` at `0x1400243b5`
- `KERNEL32!UnmapViewOfFile` at `0x140024494`
- `KERNEL32!UnmapViewOfFile` at `0x1400244ac`
- `KERNEL32!UnmapViewOfFile` at `0x1400245a5`
- `KERNEL32!UnmapViewOfFile` at `0x140024494`
- `KERNEL32!UnmapViewOfFile` at `0x1400244ac`
- `KERNEL32!UnmapViewOfFile` at `0x1400245a5`
- `KERNEL32!ReadFile` at `0x1400244f3`
- `KERNEL32!ReadFile` at `0x1400244f3`
- `KERNEL32!CreateFileW` at `0x140024364`
- `KERNEL32!CreateFileW` at `0x140024364`
- `KERNEL32!GetFileSize` at `0x14002438b`
- `KERNEL32!GetFileSize` at `0x14002438b`
- `KERNEL32!CloseHandle` at `0x14002462e`
- `KERNEL32!CloseHandle` at `0x140024658`
- `KERNEL32!CloseHandle` at `0x14002462e`
- `KERNEL32!CloseHandle` at `0x140024658`
- `KERNEL32!HeapFree` at `0x1400245bd`
- `KERNEL32!HeapFree` at `0x1400245ed`
- `KERNEL32!HeapFree` at `0x1400245bd`
- `KERNEL32!HeapFree` at `0x1400245ed`
- `KERNEL32!HeapAlloc` at `0x1400244c4`
- `KERNEL32!HeapAlloc` at `0x1400244c4`
- `KERNEL32!GetProcessHeap` at `0x1400244b6`
- `KERNEL32!GetProcessHeap` at `0x1400245ad`
- `KERNEL32!GetProcessHeap` at `0x1400245dd`
- `KERNEL32!GetProcessHeap` at `0x1400244b6`
- `KERNEL32!GetProcessHeap` at `0x1400245ad`
- `KERNEL32!GetProcessHeap` at `0x1400245dd`
- `KERNEL32!GetLastError` at `0x140024375`
- `KERNEL32!GetLastError` at `0x1400245c3`
- `KERNEL32!GetLastError` at `0x1400245f3`
- `KERNEL32!GetLastError` at `0x140024622`
- `KERNEL32!GetLastError` at `0x140024636`
- `KERNEL32!GetLastError` at `0x140024375`
- `KERNEL32!GetLastError` at `0x1400245c3`
- `KERNEL32!GetLastError` at `0x1400245f3`
- `KERNEL32!GetLastError` at `0x140024622`
- `KERNEL32!GetLastError` at `0x140024636`
- `OLEAUT32!__imp_SysAllocString` at `0x140024648`
- `OLEAUT32!__imp_SysAllocString` at `0x140024648`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140024437`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140024547`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140024437`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140024547`
- `OLEAUT32!__imp_SysFreeString` at `0x140024479`
- `OLEAUT32!__imp_SysFreeString` at `0x140024589`
- `OLEAUT32!__imp_SysFreeString` at `0x140024479`
- `OLEAUT32!__imp_SysFreeString` at `0x140024589`

## pseudocode

```c
__int64 __fastcall LoadBasicTextFile(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  signed int LastError; // r14d
  signed int v4; // ebx
  HANDLE FileW; // rax
  void *v6; // rsi
  DWORD FileSize; // r12d
  HANDLE FileMappingW; // rax
  void *v9; // r15
  const unsigned __int8 *v10; // rax
  const unsigned __int8 *v11; // rsi
  UINT v12; // ebx
  unsigned __int16 *v13; // rax
  OLECHAR *v14; // rsi
  unsigned int v16; // [rsp+44h] [rbp-74h] BYREF
  UINT ui; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int16 *v18; // [rsp+50h] [rbp-68h]
  SIZE_T dwBytes; // [rsp+58h] [rbp-60h]
  HANDLE hFile; // [rsp+60h] [rbp-58h]
  HANDLE v21; // [rsp+68h] [rbp-50h]
  unsigned __int16 **v22; // [rsp+70h] [rbp-48h]
  LPCVOID lpBaseAddress; // [rsp+78h] [rbp-40h]

  v22 = a2;
  LastError = 0;
  v4 = -2147287038;
  v18 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  hFile = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    v6 = FileW;
    FileSize = GetFileSize(FileW, 0);
    LODWORD(dwBytes) = FileSize;
    if ( FileSize )
    {
      FileMappingW = CreateFileMappingW(v6, 0, 2u, 0, 0, 0);
      v9 = FileMappingW;
      v21 = FileMappingW;
      if ( FileMappingW )
      {
        v10 = (const unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        v11 = v10;
        lpBaseAddress = v10;
        if ( v10 )
        {
          v16 = 0;
          ui = 0;
          GetImageSignature(FileSize, v10, &v16);
          v4 = TextImageUnicodeSize(v16, FileSize, v11, &ui);
          if ( v4 >= 0 )
          {
            v12 = ui;
            v13 = SysAllocStringLen(0, ui);
            v14 = v13;
            v18 = v13;
            if ( v13 )
            {
              _mm_lfence();
              v4 = TextImageToUnicode(v16, 0, FileSize, (const unsigned __int8 *)lpBaseAddress, v12, v13);
              if ( v4 < 0 )
              {
                _mm_lfence();
                SysFreeString(v14);
                v18 = 0;
              }
            }
            else
            {
              v4 = -2147024882;
            }
          }
          UnmapViewOfFile(lpBaseAddress);
        }
        else
        {
          LastError = GetLastError();
        }
        CloseHandle(v9);
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      v18 = SysAllocString(&WindowName);
    }
    CloseHandle(hFile);
  }
  if ( LastError )
  {
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
  }
  *a2 = v18;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400242fc  mov     [rsp+arg_10], rbx
0x140024301  mov     [rsp+arg_18], rsi
0x140024306  push    rdi
0x140024307  push    r12
0x140024309  push    r13
0x14002430b  push    r14
0x14002430d  push    r15
0x14002430f  sub     rsp, 90h
0x140024316  mov     rax, cs:__security_cookie
0x14002431d  xor     rax, rsp
0x140024320  mov     [rsp+0B8h+var_30], rax
0x140024328  mov     r13, rdx
0x14002432b  mov     [rsp+0B8h+var_48], rdx
0x140024330  xor     edi, edi
0x140024332  mov     r14d, edi
0x140024335  mov     ebx, 80030002h
0x14002433a  mov     [rsp+0B8h+var_78], ebx
0x14002433e  mov     [rsp+0B8h+var_68], rdi
0x140024343  mov     [rsp+0B8h+hTemplateFile], rdi; hTemplateFile
0x140024348  mov     [rsp+0B8h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x140024350  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x140024358  xor     r9d, r9d; lpSecurityAttributes
0x14002435b  mov     edx, 80000000h; dwDesiredAccess
0x140024360  lea     r8d, [rdi+1]; dwShareMode
0x140024364  call    cs:__imp_CreateFileW
0x14002436a  mov     [rsp+0B8h+hFile], rax
0x14002436f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140024373  jnz     short loc_140024383
0x140024375  call    cs:__imp_GetLastError
0x14002437b  mov     r14d, eax
0x14002437e  jmp     loc_14002465E
0x140024383  xor     edx, edx; lpFileSizeHigh
0x140024385  mov     rsi, rax
0x140024388  mov     rcx, rax; hFile
0x14002438b  call    cs:__imp_GetFileSize
0x140024391  mov     r12d, eax
0x140024394  mov     dword ptr [rsp+0B8h+dwBytes], eax
0x140024398  test    eax, eax
0x14002439a  jz      loc_140024641
0x1400243a0  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], rdi; lpName
0x1400243a5  mov     [rsp+0B8h+dwCreationDisposition], edi; dwMaximumSizeLow
0x1400243a9  xor     r9d, r9d; dwMaximumSizeHigh
0x1400243ac  xor     edx, edx; lpFileMappingAttributes
0x1400243ae  lea     r8d, [r9+2]; flProtect
0x1400243b2  mov     rcx, rsi; hFile
0x1400243b5  call    cs:__imp_CreateFileMappingW
0x1400243bb  mov     r15, rax
0x1400243be  mov     [rsp+0B8h+var_50], rax
0x1400243c3  test    rax, rax
0x1400243c6  jz      loc_140024636
0x1400243cc  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rdi; dwNumberOfBytesToMap
0x1400243d1  xor     r9d, r9d; dwFileOffsetLow
0x1400243d4  xor     r8d, r8d; dwFileOffsetHigh
0x1400243d7  lea     edx, [r9+4]; dwDesiredAccess
0x1400243db  mov     rcx, rax; hFileMappingObject
0x1400243de  call    cs:__imp_MapViewOfFile
0x1400243e4  mov     rsi, rax
0x1400243e7  mov     [rsp+0B8h+lpBaseAddress], rax
0x1400243ec  test    rax, rax
0x1400243ef  jz      loc_140024622
0x1400243f5  mov     [rsp+0B8h+var_74], edi
0x1400243f9  mov     [rsp+0B8h+ui], edi
0x1400243fd  lea     r8, [rsp+0B8h+var_74]; unsigned int *
0x140024402  mov     rdx, rax; unsigned __int8 *
0x140024405  mov     ecx, r12d; unsigned int
0x140024408  call    ?GetImageSignature@@YAJKPEBEPEAK@Z; GetImageSignature(ulong,uchar const *,ulong *)
0x14002440d  mov     [rsp+0B8h+var_78], eax
0x140024411  lea     r9, [rsp+0B8h+ui]; unsigned int *
0x140024416  mov     r8, rsi; unsigned __int8 *
0x140024419  mov     edx, r12d; unsigned int
0x14002441c  mov     ecx, [rsp+0B8h+var_74]; unsigned int
0x140024420  call    ?TextImageUnicodeSize@@YAJKKPEBEPEAK@Z; TextImageUnicodeSize(ulong,ulong,uchar const *,ulong *)
0x140024425  mov     ebx, eax
0x140024427  mov     [rsp+0B8h+var_78], eax
0x14002442b  test    eax, eax
0x14002442d  js      short loc_14002448F
0x14002442f  mov     ebx, [rsp+0B8h+ui]
0x140024433  mov     edx, ebx; ui
0x140024435  xor     ecx, ecx; strIn
0x140024437  call    cs:__imp_SysAllocStringLen
0x14002443d  mov     rsi, rax
0x140024440  mov     [rsp+0B8h+var_68], rax
0x140024445  test    rax, rax
0x140024448  jz      short loc_140024486
0x14002444a  lfence
0x14002444d  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x140024452  mov     [rsp+0B8h+dwCreationDisposition], ebx; unsigned int
0x140024456  mov     r9, [rsp+0B8h+lpBaseAddress]; unsigned __int8 *
0x14002445b  mov     r8d, r12d; unsigned int
0x14002445e  xor     edx, edx; int
0x140024460  mov     ecx, [rsp+0B8h+var_74]; unsigned int
0x140024464  call    ?TextImageToUnicode@@YAJKHKPEBEKPEAG@Z; TextImageToUnicode(ulong,int,ulong,uchar const *,ulong,ushort *)
0x140024469  mov     ebx, eax
0x14002446b  mov     [rsp+0B8h+var_78], eax
0x14002446f  test    eax, eax
0x140024471  jns     short loc_14002448F
0x140024473  lfence
0x140024476  mov     rcx, rsi; bstrString
0x140024479  call    cs:__imp_SysFreeString
0x14002447f  mov     [rsp+0B8h+var_68], rdi
0x140024484  jmp     short loc_14002448F
0x140024486  mov     ebx, 8007000Eh
0x14002448b  mov     [rsp+0B8h+var_78], ebx
0x14002448f  mov     rcx, [rsp+0B8h+lpBaseAddress]; lpBaseAddress
0x140024494  call    cs:__imp_UnmapViewOfFile
0x14002449a  jmp     loc_14002462B
0x14002449f  and     [rsp+0B8h+NumberOfBytesRead], 0
0x1400244a7  mov     rcx, [rsp+0B8h+lpBaseAddress]; lpBaseAddress
0x1400244ac  call    cs:__imp_UnmapViewOfFile
0x1400244b2  mov     edi, dword ptr [rsp+0B8h+dwBytes]
0x1400244b6  call    cs:__imp_GetProcessHeap
0x1400244bc  mov     rcx, rax; hHeap
0x1400244bf  mov     r8d, edi; dwBytes
0x1400244c2  xor     edx, edx; dwFlags
0x1400244c4  call    cs:__imp_HeapAlloc
0x1400244ca  mov     [rsp+0B8h+lpBaseAddress], rax
0x1400244cf  test    rax, rax
0x1400244d2  jz      loc_14002460D
0x1400244d8  and     qword ptr [rsp+0B8h+dwCreationDisposition], 0
0x1400244de  lea     r9, [rsp+0B8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400244e6  mov     r8d, edi; nNumberOfBytesToRead
0x1400244e9  lea     rdx, [rsp+0B8h+lpBaseAddress]; lpBuffer
0x1400244ee  mov     rcx, [rsp+0B8h+hFile]; hFile
0x1400244f3  call    cs:__imp_ReadFile
0x1400244f9  test    eax, eax
0x1400244fb  jz      loc_1400245DD
0x140024501  and     [rsp+0B8h+var_74], 0
0x140024506  and     [rsp+0B8h+ui], 0
0x14002450b  lea     r8, [rsp+0B8h+var_74]; unsigned int *
0x140024510  mov     rdx, [rsp+0B8h+lpBaseAddress]; unsigned __int8 *
0x140024515  mov     ecx, edi; unsigned int
0x140024517  call    ?GetImageSignature@@YAJKPEBEPEAK@Z; GetImageSignature(ulong,uchar const *,ulong *)
0x14002451c  mov     [rsp+0B8h+var_78], eax
0x140024520  lea     r9, [rsp+0B8h+ui]; unsigned int *
0x140024525  mov     r8, [rsp+0B8h+lpBaseAddress]; unsigned __int8 *
0x14002452a  mov     edx, edi; unsigned int
0x14002452c  mov     ecx, [rsp+0B8h+var_74]; unsigned int
0x140024530  call    ?TextImageUnicodeSize@@YAJKKPEBEPEAK@Z; TextImageUnicodeSize(ulong,ulong,uchar const *,ulong *)
0x140024535  mov     ebx, eax
0x140024537  mov     [rsp+0B8h+var_78], eax
0x14002453b  test    eax, eax
0x14002453d  js      short loc_1400245A0
0x14002453f  mov     ebx, [rsp+0B8h+ui]
0x140024543  mov     edx, ebx; ui
0x140024545  xor     ecx, ecx; strIn
0x140024547  call    cs:__imp_SysAllocStringLen
0x14002454d  mov     rsi, rax
0x140024550  mov     [rsp+0B8h+var_68], rax
0x140024555  test    rax, rax
0x140024558  jz      short loc_140024597
0x14002455a  lfence
0x14002455d  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x140024562  mov     [rsp+0B8h+dwCreationDisposition], ebx; unsigned int
0x140024566  mov     r9, [rsp+0B8h+lpBaseAddress]; unsigned __int8 *
0x14002456b  mov     r8d, edi; unsigned int
0x14002456e  xor     edx, edx; int
0x140024570  mov     ecx, [rsp+0B8h+var_74]; unsigned int
0x140024574  call    ?TextImageToUnicode@@YAJKHKPEBEKPEAG@Z; TextImageToUnicode(ulong,int,ulong,uchar const *,ulong,ushort *)
0x140024579  mov     ebx, eax
0x14002457b  mov     [rsp+0B8h+var_78], eax
0x14002457f  test    eax, eax
0x140024581  jns     short loc_1400245A0
0x140024583  lfence
0x140024586  mov     rcx, rsi; bstrString
0x140024589  call    cs:__imp_SysFreeString
0x14002458f  and     [rsp+0B8h+var_68], 0
0x140024595  jmp     short loc_1400245A0
0x140024597  mov     ebx, 8007000Eh
0x14002459c  mov     [rsp+0B8h+var_78], ebx
0x1400245a0  mov     rcx, [rsp+0B8h+lpBaseAddress]; lpBaseAddress
0x1400245a5  call    cs:__imp_UnmapViewOfFile
0x1400245ab  jmp     short loc_1400245DB
0x1400245ad  call    cs:__imp_GetProcessHeap
0x1400245b3  mov     rcx, rax; hHeap
0x1400245b6  mov     r8, [rsp+0B8h+lpBaseAddress]; lpMem
0x1400245bb  xor     edx, edx; dwFlags
0x1400245bd  call    cs:__imp_HeapFree
0x1400245c3  call    cs:__imp_GetLastError
0x1400245c9  movzx   ebx, ax
0x1400245cc  or      ebx, 80070000h
0x1400245d2  test    eax, eax
0x1400245d4  cmovle  ebx, eax
0x1400245d7  mov     [rsp+0B8h+var_78], ebx
0x1400245db  jmp     short loc_140024611
0x1400245dd  call    cs:__imp_GetProcessHeap
0x1400245e3  mov     rcx, rax; hHeap
0x1400245e6  mov     r8, [rsp+0B8h+lpBaseAddress]; lpMem
0x1400245eb  xor     edx, edx; dwFlags
0x1400245ed  call    cs:__imp_HeapFree
0x1400245f3  call    cs:__imp_GetLastError
0x1400245f9  movzx   ebx, ax
0x1400245fc  or      ebx, 80070000h
0x140024602  test    eax, eax
0x140024604  cmovle  ebx, eax
0x140024607  mov     [rsp+0B8h+var_78], ebx
0x14002460b  jmp     short loc_140024611
0x14002460d  mov     ebx, [rsp+0B8h+var_78]
0x140024611  xor     edi, edi
0x140024613  mov     r14d, edi
0x140024616  mov     r15, [rsp+0B8h+var_50]
0x14002461b  mov     r13, [rsp+0B8h+var_48]
0x140024620  jmp     short loc_14002462B
0x140024622  call    cs:__imp_GetLastError
0x140024628  mov     r14d, eax
0x14002462b  mov     rcx, r15; hObject
0x14002462e  call    cs:__imp_CloseHandle
0x140024634  jmp     short loc_140024653
0x140024636  call    cs:__imp_GetLastError
0x14002463c  mov     r14d, eax
0x14002463f  jmp     short loc_140024653
0x140024641  lea     rcx, WindowName; psz
0x140024648  call    cs:__imp_SysAllocString
0x14002464e  mov     [rsp+0B8h+var_68], rax
0x140024653  mov     rcx, [rsp+0B8h+hFile]; hObject
0x140024658  call    cs:__imp_CloseHandle
0x14002465e  test    r14d, r14d
0x140024661  jz      short loc_140024674
0x140024663  movzx   ebx, r14w
0x140024667  or      ebx, 80070000h
0x14002466d  test    r14d, r14d
0x140024670  cmovle  ebx, r14d
0x140024674  mov     rax, [rsp+0B8h+var_68]
0x140024679  mov     [r13+0], rax
0x14002467d  mov     eax, ebx
0x14002467f  mov     rcx, [rsp+0B8h+var_30]
0x140024687  xor     rcx, rsp; StackCookie
0x14002468a  call    __security_check_cookie
0x14002468f  lea     r11, [rsp+0B8h+var_28]
0x140024697  mov     rbx, [r11+40h]
0x14002469b  mov     rsi, [r11+48h]
0x14002469f  mov     rsp, r11
0x1400246a2  pop     r15
0x1400246a4  pop     r14
0x1400246a6  pop     r13
0x1400246a8  pop     r12
0x1400246aa  pop     rdi
0x1400246ab  retn
```
