# IsDOSFileCorrupted

- ea: `0x180060dac`
- end: `0x18006103f`
- name: `IsDOSFileCorrupted`
- size: `659`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180056ed0`
- `0x18005e780`

## callees

- `0x18004093c`
- `0x180060dac`

## import_xrefs

- `ntdll!NtRaiseHardError` at `0x180061004`
- `ntdll!NtRaiseHardError` at `0x180061004`
- `ntdll!RtlSetLastWin32Error` at `0x180060fbc`
- `ntdll!RtlSetLastWin32Error` at `0x180060fbc`
- `ntdll!RtlInitUnicodeString` at `0x180060fd9`
- `ntdll!RtlInitUnicodeString` at `0x180060fd9`
- `ntdll!_wcsicmp` at `0x180060ef9`
- `ntdll!_wcsicmp` at `0x180060ef9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006101f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006101f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060e1b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060e1b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180060e52`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180060e52`

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
0x180060dac  mov     [rsp-38h+arg_0], rbx
0x180060db1  push    rbp
0x180060db2  push    rsi
0x180060db3  push    rdi
0x180060db4  push    r12
0x180060db6  push    r13
0x180060db8  push    r14
0x180060dba  push    r15
0x180060dbc  mov     rbp, rsp
0x180060dbf  sub     rsp, 60h
0x180060dc3  xor     r15d, r15d
0x180060dc6  mov     rsi, r8
0x180060dc9  mov     edi, r15d
0x180060dcc  mov     [rdx], r15d
0x180060dcf  mov     [r8], r15d
0x180060dd2  mov     rbx, rdx
0x180060dd5  mov     r14, rcx
0x180060dd8  call    GetCorruptDetectionState
0x180060ddd  lea     r13d, [r15+1]
0x180060de1  mov     r12d, eax
0x180060de4  test    r13b, al
0x180060de7  jnz     loc_180061025
0x180060ded  mov     [rsp+60h+hTemplateFile], r15; hTemplateFile
0x180060df2  xor     r9d, r9d; lpSecurityAttributes
0x180060df5  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180060dfd  mov     r8d, r13d; dwShareMode
0x180060e00  mov     edx, 80000000h; dwDesiredAccess
0x180060e05  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180060e0d  mov     rcx, r14; lpFileName
0x180060e10  mov     [rbp+Buffer], 5A5A5A5Ah
0x180060e17  mov     [rbp+NumberOfBytesRead], r15d
0x180060e1b  call    cs:__imp_CreateFileW
0x180060e21  mov     r15, rax
0x180060e24  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060e28  jnz     short loc_180060E3C
0x180060e2a  mov     eax, gs:68h
0x180060e32  mov     [rsi], eax
0x180060e34  mov     [rbx], r13d
0x180060e37  jmp     loc_180061025
0x180060e3c  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180060e40  mov     qword ptr [rsp+60h+dwCreationDisposition], rdi; lpOverlapped
0x180060e45  mov     r8d, 4; nNumberOfBytesToRead
0x180060e4b  lea     rdx, [rbp+Buffer]; lpBuffer
0x180060e4f  mov     rcx, r15; hFile
0x180060e52  call    cs:__imp_ReadFile
0x180060e58  test    eax, eax
0x180060e5a  jz      loc_18006100C
0x180060e60  mov     ecx, [rbp+Buffer]
0x180060e63  mov     eax, [rbp+NumberOfBytesRead]
0x180060e66  mov     [rsi], ecx
0x180060e68  xor     esi, esi
0x180060e6a  test    eax, eax
0x180060e6c  jz      loc_180060FAE
0x180060e72  sub     eax, r13d
0x180060e75  jz      loc_180060F95
0x180060e7b  sub     eax, r13d
0x180060e7e  jz      loc_180060F72
0x180060e84  sub     eax, r13d
0x180060e87  jz      loc_180060F72
0x180060e8d  cmp     eax, r13d
0x180060e90  jnz     loc_18006101C
0x180060e96  test    ecx, ecx
0x180060e98  jnz     short loc_180060EA5
0x180060e9a  mov     dword ptr [rbx], 0Bh
0x180060ea0  jmp     loc_180060FB4
0x180060ea5  cmp     ecx, 0FFFFFFFFh
0x180060ea8  jnz     short loc_180060EB5
0x180060eaa  mov     dword ptr [rbx], 0Ah
0x180060eb0  jmp     loc_180060FB4
0x180060eb5  cmp     cl, 3Ch ; '<'
0x180060eb8  jnz     loc_18006101C
0x180060ebe  movzx   ecx, word ptr [r14]
0x180060ec2  test    cx, cx
0x180060ec5  jz      loc_18006101C
0x180060ecb  mov     r8, rsi
0x180060ece  mov     rax, r14
0x180060ed1  add     rax, 2
0x180060ed5  cmp     cx, 2Eh ; '.'
0x180060ed9  jnz     short loc_180060EDE
0x180060edb  mov     r8, rax
0x180060ede  movzx   ecx, word ptr [rax]
0x180060ee1  test    cx, cx
0x180060ee4  jnz     short loc_180060ED1
0x180060ee6  test    r8, r8
0x180060ee9  jz      loc_18006101C
0x180060eef  lea     rdx, aExe_0; "exe"
0x180060ef6  mov     rcx, r8; String1
0x180060ef9  call    cs:__imp__wcsicmp
0x180060eff  test    eax, eax
0x180060f01  jnz     loc_18006101C
0x180060f07  mov     ecx, [rbp+Buffer]
0x180060f0a  shr     ecx, 8
0x180060f0d  mov     [rbp+Buffer], ecx
0x180060f10  cmp     cl, 3Fh ; '?'
0x180060f13  jz      short loc_180060F38
0x180060f15  cmp     cl, 21h ; '!'
0x180060f18  jz      short loc_180060F38
0x180060f1a  test    cl, cl
0x180060f1c  jnz     short loc_180060F40
0x180060f1e  mov     eax, ecx
0x180060f20  shr     eax, 8
0x180060f23  sub     al, 20h ; ' '
0x180060f25  cmp     al, 5Ah ; 'Z'
0x180060f27  ja      loc_18006101C
0x180060f2d  shr     ecx, 10h
0x180060f30  test    cl, cl
0x180060f32  jnz     loc_18006101C
0x180060f38  mov     dword ptr [rbx], 0Ch
0x180060f3e  jmp     short loc_180060FB4
0x180060f40  mov     al, cl
0x180060f42  mov     dl, 41h ; 'A'
0x180060f44  sub     al, dl
0x180060f46  mov     r8b, 39h ; '9'
0x180060f49  cmp     al, r8b
0x180060f4c  ja      loc_18006101C
0x180060f52  mov     eax, ecx
0x180060f54  shr     eax, 8
0x180060f57  sub     al, dl
0x180060f59  cmp     al, r8b
0x180060f5c  ja      loc_18006101C
0x180060f62  shr     ecx, 10h
0x180060f65  sub     cl, dl
0x180060f67  cmp     cl, r8b
0x180060f6a  ja      loc_18006101C
0x180060f70  jmp     short loc_180060F38
0x180060f72  test    cx, cx
0x180060f75  jnz     short loc_180060F7F
0x180060f77  mov     dword ptr [rbx], 8
0x180060f7d  jmp     short loc_180060FB4
0x180060f7f  mov     eax, 0FFFFh
0x180060f84  cmp     cx, ax
0x180060f87  jnz     loc_18006101C
0x180060f8d  mov     dword ptr [rbx], 7
0x180060f93  jmp     short loc_180060FB4
0x180060f95  test    cl, cl
0x180060f97  jnz     short loc_180060FA1
0x180060f99  mov     dword ptr [rbx], 6
0x180060f9f  jmp     short loc_180060FB4
0x180060fa1  cmp     cl, 0FFh
0x180060fa4  jnz     short loc_18006101C
0x180060fa6  mov     dword ptr [rbx], 5
0x180060fac  jmp     short loc_180060FB4
0x180060fae  mov     dword ptr [rbx], 4
0x180060fb4  mov     ecx, 0C1h; LastError
0x180060fb9  mov     edi, r13d
0x180060fbc  call    cs:__imp_RtlSetLastWin32Error
0x180060fc2  test    r12b, 2
0x180060fc6  jz      short loc_18006101C
0x180060fc8  xorps   xmm0, xmm0
0x180060fcb  mov     [rbp+Response], esi
0x180060fce  mov     rdx, r14; SourceString
0x180060fd1  lea     rcx, [rbp+DestinationString]; DestinationString
0x180060fd5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180060fd9  call    cs:__imp_RtlInitUnicodeString
0x180060fdf  lea     rax, [rbp+DestinationString]
0x180060fe3  mov     r8d, r13d; UnicodeStringParameterMask
0x180060fe6  mov     [rbp+Parameters], rax
0x180060fea  lea     r9, [rbp+Parameters]; Parameters
0x180060fee  lea     rax, [rbp+Response]
0x180060ff2  mov     edx, r13d; NumberOfParameters
0x180060ff5  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax; Response
0x180060ffa  mov     ecx, 0C0000102h; ErrorStatus
0x180060fff  mov     [rsp+60h+dwCreationDisposition], r13d; ValidResponseOptions
0x180061004  call    cs:__imp_NtRaiseHardError
0x18006100a  jmp     short loc_18006101C
0x18006100c  mov     ecx, gs:68h
0x180061014  mov     [rsi], ecx
0x180061016  mov     dword ptr [rbx], 2
0x18006101c  mov     rcx, r15; hObject
0x18006101f  call    cs:__imp_CloseHandle
0x180061025  mov     rbx, [rsp+60h+arg_0]
0x18006102d  mov     eax, edi
0x18006102f  add     rsp, 60h
0x180061033  pop     r15
0x180061035  pop     r14
0x180061037  pop     r13
0x180061039  pop     r12
0x18006103b  pop     rdi
0x18006103c  pop     rsi
0x18006103d  pop     rbp
0x18006103e  retn
```
