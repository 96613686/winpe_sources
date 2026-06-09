# IsDOSFileCorrupted

- ea: `0x180067668`
- end: `0x18006792a`
- name: `IsDOSFileCorrupted`
- size: `706`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18005c2f0`
- `0x1800643a0`

## callees

- `0x1800444e4`
- `0x180067668`

## import_xrefs

- `ntdll!NtRaiseHardError` at `0x1800678e2`
- `ntdll!NtRaiseHardError` at `0x1800678e2`
- `ntdll!RtlSetLastWin32Error` at `0x18006788e`
- `ntdll!RtlSetLastWin32Error` at `0x18006788e`
- `ntdll!RtlInitUnicodeString` at `0x1800678b1`
- `ntdll!RtlInitUnicodeString` at `0x1800678b1`
- `ntdll!_wcsicmp` at `0x1800677c1`
- `ntdll!_wcsicmp` at `0x1800677c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067903`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800676d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800676d7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180067714`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180067714`

## pseudocode

```c
__int64 __fastcall IsDOSFileCorrupted(PCWSTR SourceString, _DWORD *a2, ULONG *a3)
{
  unsigned int v4; // edi
  char CorruptDetectionState; // r12
  HANDLE FileW; // rax
  void *v9; // r15
  unsigned int v10; // ecx
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  WCHAR v15; // cx
  const wchar_t *v16; // r8
  PCWSTR v17; // rax
  unsigned int v18; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 Parameters; // [rsp+50h] [rbp-10h] BYREF
  unsigned int Buffer; // [rsp+A8h] [rbp+48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B0h] [rbp+50h] BYREF
  ULONG Response; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  CorruptDetectionState = GetCorruptDetectionState();
  if ( (CorruptDetectionState & 1) == 0 )
  {
    Buffer = 1515870810;
    NumberOfBytesRead = 0;
    FileW = CreateFileW(SourceString, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      *a3 = NtCurrentTeb()->LastErrorValue;
      *a2 = 1;
      return v4;
    }
    if ( !ReadFile(FileW, &Buffer, 4u, &NumberOfBytesRead, 0) )
    {
      *a3 = NtCurrentTeb()->LastErrorValue;
      *a2 = 2;
      goto LABEL_44;
    }
    v10 = Buffer;
    v11 = NumberOfBytesRead;
    *a3 = Buffer;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              if ( !v10 )
              {
                *a2 = 11;
                goto LABEL_41;
              }
              if ( v10 == -1 )
              {
                *a2 = 10;
                goto LABEL_41;
              }
              if ( (_BYTE)v10 != 60 )
                goto LABEL_44;
              v15 = *SourceString;
              if ( !*SourceString )
                goto LABEL_44;
              v16 = 0;
              v17 = SourceString;
              do
              {
                ++v17;
                if ( v15 == 46 )
                  v16 = v17;
                v15 = *v17;
              }
              while ( *v17 );
              if ( !v16 || _wcsicmp(v16, L"exe") )
                goto LABEL_44;
              v18 = Buffer >> 8;
              Buffer = v18;
              if ( (_BYTE)v18 == 63 || (_BYTE)v18 == 33 )
                goto LABEL_27;
              if ( (_BYTE)v18 )
              {
                if ( (unsigned __int8)(v18 - 65) <= 0x39u
                  && (unsigned __int8)(BYTE1(v18) - 65) <= 0x39u
                  && (unsigned __int8)(BYTE2(v18) - 65) <= 0x39u )
                {
                  goto LABEL_27;
                }
              }
              else if ( (unsigned __int8)(BYTE1(v18) - 32) <= 0x5Au && !BYTE2(v18) )
              {
LABEL_27:
                *a2 = 12;
                goto LABEL_41;
              }
            }
LABEL_44:
            CloseHandle(v9);
            return v4;
          }
        }
        if ( (_WORD)v10 )
        {
          if ( (_WORD)v10 != 0xFFFF )
            goto LABEL_44;
          *a2 = 7;
        }
        else
        {
          *a2 = 8;
        }
      }
      else if ( (_BYTE)v10 )
      {
        if ( (_BYTE)v10 != 0xFF )
          goto LABEL_44;
        *a2 = 5;
      }
      else
      {
        *a2 = 6;
      }
    }
    else
    {
      *a2 = 4;
    }
LABEL_41:
    v4 = 1;
    RtlSetLastWin32Error(0xC1u);
    if ( (CorruptDetectionState & 2) != 0 )
    {
      Response = 0;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      Parameters = (unsigned __int64)&DestinationString;
      NtRaiseHardError(-1073741566, 1u, 1u, &Parameters, 1u, &Response);
    }
    goto LABEL_44;
  }
  return v4;
}

```

## disassembly

```asm
0x180067668  mov     [rsp-38h+arg_0], rbx
0x18006766d  push    rbp
0x18006766e  push    rsi
0x18006766f  push    rdi
0x180067670  push    r12
0x180067672  push    r13
0x180067674  push    r14
0x180067676  push    r15
0x180067678  mov     rbp, rsp
0x18006767b  sub     rsp, 60h
0x18006767f  xor     r15d, r15d
0x180067682  mov     rsi, r8
0x180067685  mov     edi, r15d
0x180067688  mov     [rdx], r15d
0x18006768b  mov     [r8], r15d
0x18006768e  mov     rbx, rdx
0x180067691  mov     r14, rcx
0x180067694  call    GetCorruptDetectionState
0x180067699  lea     r13d, [r15+1]
0x18006769d  mov     r12d, eax
0x1800676a0  test    r13b, al
0x1800676a3  jnz     loc_18006790F
0x1800676a9  mov     [rsp+60h+hTemplateFile], r15; hTemplateFile
0x1800676ae  xor     r9d, r9d; lpSecurityAttributes
0x1800676b1  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800676b9  mov     r8d, r13d; dwShareMode
0x1800676bc  mov     edx, 80000000h; dwDesiredAccess
0x1800676c1  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x1800676c9  mov     rcx, r14; lpFileName
0x1800676cc  mov     [rbp+Buffer], 5A5A5A5Ah
0x1800676d3  mov     [rbp+NumberOfBytesRead], r15d
0x1800676d7  call    cs:__imp_CreateFileW
0x1800676de  nop     dword ptr [rax+rax+00h]
0x1800676e3  mov     r15, rax
0x1800676e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800676ea  jnz     short loc_1800676FE
0x1800676ec  mov     eax, gs:68h
0x1800676f4  mov     [rsi], eax
0x1800676f6  mov     [rbx], r13d
0x1800676f9  jmp     loc_18006790F
0x1800676fe  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067702  mov     qword ptr [rsp+60h+dwCreationDisposition], rdi; lpOverlapped
0x180067707  mov     r8d, 4; nNumberOfBytesToRead
0x18006770d  lea     rdx, [rbp+Buffer]; lpBuffer
0x180067711  mov     rcx, r15; hFile
0x180067714  call    cs:__imp_ReadFile
0x18006771b  nop     dword ptr [rax+rax+00h]
0x180067720  test    eax, eax
0x180067722  jz      loc_1800678F0
0x180067728  mov     ecx, [rbp+Buffer]
0x18006772b  mov     eax, [rbp+NumberOfBytesRead]
0x18006772e  mov     [rsi], ecx
0x180067730  xor     esi, esi
0x180067732  test    eax, eax
0x180067734  jz      loc_180067880
0x18006773a  sub     eax, r13d
0x18006773d  jz      loc_180067863
0x180067743  sub     eax, r13d
0x180067746  jz      loc_180067840
0x18006774c  sub     eax, r13d
0x18006774f  jz      loc_180067840
0x180067755  cmp     eax, r13d
0x180067758  jnz     loc_180067900
0x18006775e  test    ecx, ecx
0x180067760  jnz     short loc_18006776D
0x180067762  mov     dword ptr [rbx], 0Bh
0x180067768  jmp     loc_180067886
0x18006776d  cmp     ecx, 0FFFFFFFFh
0x180067770  jnz     short loc_18006777D
0x180067772  mov     dword ptr [rbx], 0Ah
0x180067778  jmp     loc_180067886
0x18006777d  cmp     cl, 3Ch ; '<'
0x180067780  jnz     loc_180067900
0x180067786  movzx   ecx, word ptr [r14]
0x18006778a  test    cx, cx
0x18006778d  jz      loc_180067900
0x180067793  mov     r8, rsi
0x180067796  mov     rax, r14
0x180067799  add     rax, 2
0x18006779d  cmp     cx, 2Eh ; '.'
0x1800677a1  jnz     short loc_1800677A6
0x1800677a3  mov     r8, rax
0x1800677a6  movzx   ecx, word ptr [rax]
0x1800677a9  test    cx, cx
0x1800677ac  jnz     short loc_180067799
0x1800677ae  test    r8, r8
0x1800677b1  jz      loc_180067900
0x1800677b7  lea     rdx, aExe_0; "exe"
0x1800677be  mov     rcx, r8; String1
0x1800677c1  call    cs:__imp__wcsicmp
0x1800677c8  nop     dword ptr [rax+rax+00h]
0x1800677cd  test    eax, eax
0x1800677cf  jnz     loc_180067900
0x1800677d5  mov     ecx, [rbp+Buffer]
0x1800677d8  shr     ecx, 8
0x1800677db  mov     [rbp+Buffer], ecx
0x1800677de  cmp     cl, 3Fh ; '?'
0x1800677e1  jz      short loc_180067806
0x1800677e3  cmp     cl, 21h ; '!'
0x1800677e6  jz      short loc_180067806
0x1800677e8  test    cl, cl
0x1800677ea  jnz     short loc_18006780E
0x1800677ec  mov     eax, ecx
0x1800677ee  shr     eax, 8
0x1800677f1  sub     al, 20h ; ' '
0x1800677f3  cmp     al, 5Ah ; 'Z'
0x1800677f5  ja      loc_180067900
0x1800677fb  shr     ecx, 10h
0x1800677fe  test    cl, cl
0x180067800  jnz     loc_180067900
0x180067806  mov     dword ptr [rbx], 0Ch
0x18006780c  jmp     short loc_180067886
0x18006780e  mov     al, cl
0x180067810  mov     dl, 41h ; 'A'
0x180067812  sub     al, dl
0x180067814  mov     r8b, 39h ; '9'
0x180067817  cmp     al, r8b
0x18006781a  ja      loc_180067900
0x180067820  mov     eax, ecx
0x180067822  shr     eax, 8
0x180067825  sub     al, dl
0x180067827  cmp     al, r8b
0x18006782a  ja      loc_180067900
0x180067830  shr     ecx, 10h
0x180067833  sub     cl, dl
0x180067835  cmp     cl, r8b
0x180067838  ja      loc_180067900
0x18006783e  jmp     short loc_180067806
0x180067840  test    cx, cx
0x180067843  jnz     short loc_18006784D
0x180067845  mov     dword ptr [rbx], 8
0x18006784b  jmp     short loc_180067886
0x18006784d  mov     eax, 0FFFFh
0x180067852  cmp     cx, ax
0x180067855  jnz     loc_180067900
0x18006785b  mov     dword ptr [rbx], 7
0x180067861  jmp     short loc_180067886
0x180067863  test    cl, cl
0x180067865  jnz     short loc_18006786F
0x180067867  mov     dword ptr [rbx], 6
0x18006786d  jmp     short loc_180067886
0x18006786f  cmp     cl, 0FFh
0x180067872  jnz     loc_180067900
0x180067878  mov     dword ptr [rbx], 5
0x18006787e  jmp     short loc_180067886
0x180067880  mov     dword ptr [rbx], 4
0x180067886  mov     ecx, 0C1h; LastError
0x18006788b  mov     edi, r13d
0x18006788e  call    cs:__imp_RtlSetLastWin32Error
0x180067895  nop     dword ptr [rax+rax+00h]
0x18006789a  test    r12b, 2
0x18006789e  jz      short loc_180067900
0x1800678a0  xorps   xmm0, xmm0
0x1800678a3  mov     [rbp+Response], esi
0x1800678a6  mov     rdx, r14; SourceString
0x1800678a9  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800678ad  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800678b1  call    cs:__imp_RtlInitUnicodeString
0x1800678b8  nop     dword ptr [rax+rax+00h]
0x1800678bd  lea     rax, [rbp+DestinationString]
0x1800678c1  mov     r8d, r13d; UnicodeStringParameterMask
0x1800678c4  mov     [rbp+Parameters], rax
0x1800678c8  lea     r9, [rbp+Parameters]; Parameters
0x1800678cc  lea     rax, [rbp+Response]
0x1800678d0  mov     edx, r13d; NumberOfParameters
0x1800678d3  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; Response
0x1800678d8  mov     ecx, 0C0000102h; ErrorStatus
0x1800678dd  mov     [rsp+60h+dwCreationDisposition], r13d; ValidResponseOptions
0x1800678e2  call    cs:__imp_NtRaiseHardError
0x1800678e9  nop     dword ptr [rax+rax+00h]
0x1800678ee  jmp     short loc_180067900
0x1800678f0  mov     ecx, gs:68h
0x1800678f8  mov     [rsi], ecx
0x1800678fa  mov     dword ptr [rbx], 2
0x180067900  mov     rcx, r15; hObject
0x180067903  call    cs:__imp_CloseHandle
0x18006790a  nop     dword ptr [rax+rax+00h]
0x18006790f  mov     rbx, [rsp+60h+arg_0]
0x180067917  mov     eax, edi
0x180067919  add     rsp, 60h
0x18006791d  pop     r15
0x18006791f  pop     r14
0x180067921  pop     r13
0x180067923  pop     r12
0x180067925  pop     rdi
0x180067926  pop     rsi
0x180067927  pop     rbp
0x180067928  retn
```
