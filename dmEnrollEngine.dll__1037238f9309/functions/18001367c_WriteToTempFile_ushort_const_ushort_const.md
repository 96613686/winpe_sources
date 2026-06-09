# WriteToTempFile(ushort const *,ushort const *)

- ea: `0x18001367c`
- end: `0x18001384d`
- name: `?WriteToTempFile@@YAJPEBG0@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004cac0`
- `0x18004d410`
- `0x18004ff88`
- `0x180050884`
- `0x18005a950`
- `0x18005f5e4`

## callees

- `0x180007120`
- `0x18000dd20`
- `0x18001367c`
- `0x1800140d0`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180032f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013813`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013813`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800137fd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800137fd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013773`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013773`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180013707`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180013707`

## string_xrefs

- `0x1800136e7`: `WriteToTempFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteToTempFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 result; // rax
  signed int v5; // eax
  HANDLE v6; // rbx
  signed int LastError; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-BCh] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[526]; // [rsp+72h] [rbp-8Eh] BYREF

  result = 0;
  if ( byte_1800B0798 )
  {
    v9 = 0;
    nNumberOfBytesToWrite = 0;
    v13 = 0;
    v10 = 0;
    NumberOfBytesWritten = 0;
    FileName = 0;
    memset_0(v16, 0, 0x206u);
    v14[0] = "WriteToTempFile";
    v14[1] = &v9;
    if ( (unsigned int)GetTempPath2W(260, &FileName) )
    {
      v9 = StringCchCatW(&FileName, 0x104u, a2);
      if ( v9 >= 0 )
      {
        v6 = CreateFileW(&FileName, 0xC0000000, 0, 0, 2u, 0, 0);
        if ( v6 == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v9 = LastError;
        }
        else
        {
          v9 = StringCchLengthW(a1, 0x7FFFFFFFu, &v13);
          if ( v9 >= 0 )
          {
            v9 = ULongLongToULong(v13, &v10);
            if ( v9 >= 0 )
            {
              v9 = ULongLongToULong(2LL * v10, &nNumberOfBytesToWrite);
              if ( v9 >= 0 && !WriteFile(v6, a1, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
                v9 = 0;
            }
          }
          if ( !v6 )
            goto LABEL_18;
        }
        CloseHandle(v6);
      }
    }
    else
    {
      v5 = GetLastError();
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      v9 = v5;
    }
LABEL_18:
    v8 = v9;
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v14);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18001367c  mov     [rsp-8+arg_10], rbx
0x180013681  mov     [rsp-8+arg_18], rdi
0x180013686  push    rbp
0x180013687  lea     rbp, [rsp-190h]
0x18001368f  sub     rsp, 290h
0x180013696  mov     rax, cs:__security_cookie
0x18001369d  xor     rax, rsp
0x1800136a0  mov     [rbp+190h+var_10], rax
0x1800136a7  xor     eax, eax
0x1800136a9  mov     rbx, rdx
0x1800136ac  cmp     cs:byte_1800B0798, al
0x1800136b2  mov     rdi, rcx
0x1800136b5  jz      loc_180013829
0x1800136bb  xor     edx, edx; Val
0x1800136bd  mov     [rsp+290h+var_250], eax
0x1800136c1  mov     r8d, 206h; Size
0x1800136c7  mov     [rsp+290h+nNumberOfBytesToWrite], eax
0x1800136cb  lea     rcx, [rsp+290h+var_21E]; void *
0x1800136d0  mov     [rsp+290h+var_240], rax
0x1800136d5  mov     [rsp+290h+var_24C], eax
0x1800136d9  mov     [rsp+290h+NumberOfBytesWritten], eax
0x1800136dd  mov     [rsp+290h+FileName], ax
0x1800136e2  call    memset_0
0x1800136e7  lea     rax, aWritetotempfil; "WriteToTempFile"
0x1800136ee  mov     ecx, 104h
0x1800136f3  mov     [rsp+290h+var_238], rax
0x1800136f8  lea     rdx, [rsp+290h+FileName]
0x1800136fd  lea     rax, [rsp+290h+var_250]
0x180013702  mov     [rsp+290h+var_230], rax
0x180013707  call    cs:__imp_GetTempPath2W
0x18001370d  test    eax, eax
0x18001370f  jnz     short loc_18001372C
0x180013711  call    cs:__imp_GetLastError
0x180013717  test    eax, eax
0x180013719  jle     short loc_180013723
0x18001371b  movzx   eax, ax
0x18001371e  or      eax, 80070000h
0x180013723  mov     [rsp+290h+var_250], eax
0x180013727  jmp     loc_180013819
0x18001372c  mov     r8, rbx; unsigned __int16 *
0x18001372f  lea     rcx, [rsp+290h+FileName]; unsigned __int16 *
0x180013734  mov     edx, 104h; unsigned __int64
0x180013739  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001373e  mov     [rsp+290h+var_250], eax
0x180013742  test    eax, eax
0x180013744  js      loc_180013819
0x18001374a  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x180013753  lea     rcx, [rsp+290h+FileName]; lpFileName
0x180013758  mov     [rsp+290h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180013760  xor     r9d, r9d; lpSecurityAttributes
0x180013763  xor     r8d, r8d; dwShareMode
0x180013766  mov     [rsp+290h+dwCreationDisposition], 2; dwCreationDisposition
0x18001376e  mov     edx, 0C0000000h; dwDesiredAccess
0x180013773  call    cs:__imp_CreateFileW
0x180013779  mov     rbx, rax
0x18001377c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013780  jnz     short loc_18001379A
0x180013782  call    cs:__imp_GetLastError
0x180013788  test    eax, eax
0x18001378a  jle     short loc_180013794
0x18001378c  movzx   eax, ax
0x18001378f  or      eax, 80070000h
0x180013794  mov     [rsp+290h+var_250], eax
0x180013798  jmp     short loc_180013810
0x18001379a  lea     r8, [rsp+290h+var_240]; unsigned __int64 *
0x18001379f  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800137a4  mov     rcx, rdi; unsigned __int16 *
0x1800137a7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800137ac  mov     [rsp+290h+var_250], eax
0x1800137b0  test    eax, eax
0x1800137b2  js      short loc_18001380B
0x1800137b4  mov     rcx, [rsp+290h+var_240]; unsigned __int64
0x1800137b9  lea     rdx, [rsp+290h+var_24C]; unsigned int *
0x1800137be  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800137c3  mov     [rsp+290h+var_250], eax
0x1800137c7  test    eax, eax
0x1800137c9  js      short loc_18001380B
0x1800137cb  mov     ecx, [rsp+290h+var_24C]
0x1800137cf  lea     rdx, [rsp+290h+nNumberOfBytesToWrite]; unsigned int *
0x1800137d4  add     rcx, rcx; unsigned __int64
0x1800137d7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800137dc  mov     [rsp+290h+var_250], eax
0x1800137e0  test    eax, eax
0x1800137e2  js      short loc_18001380B
0x1800137e4  mov     r8d, [rsp+290h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800137e9  lea     r9, [rsp+290h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800137ee  mov     rdx, rdi; lpBuffer
0x1800137f1  mov     qword ptr [rsp+290h+dwCreationDisposition], 0; lpOverlapped
0x1800137fa  mov     rcx, rbx; hFile
0x1800137fd  call    cs:__imp_WriteFile
0x180013803  test    eax, eax
0x180013805  jnz     short loc_18001380B
0x180013807  mov     [rsp+290h+var_250], eax
0x18001380b  test    rbx, rbx
0x18001380e  jz      short loc_180013819
0x180013810  mov     rcx, rbx; hObject
0x180013813  call    cs:__imp_CloseHandle
0x180013819  mov     ebx, [rsp+290h+var_250]
0x18001381d  lea     rcx, [rsp+290h+var_238]; this
0x180013822  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180013827  mov     eax, ebx
0x180013829  mov     rcx, [rbp+190h+var_10]
0x180013830  xor     rcx, rsp; StackCookie
0x180013833  call    __security_check_cookie
0x180013838  lea     r11, [rsp+290h+var_s0]
0x180013840  mov     rbx, [r11+20h]
0x180013844  mov     rdi, [r11+28h]
0x180013848  mov     rsp, r11
0x18001384b  pop     rbp
0x18001384c  retn
```
