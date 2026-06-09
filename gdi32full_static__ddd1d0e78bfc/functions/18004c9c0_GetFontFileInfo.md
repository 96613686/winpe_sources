# GetFontFileInfo

- ea: `0x18004c9c0`
- end: `0x18004ccea`
- name: `GetFontFileInfo`
- size: `810`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x18004c9c0`
- `0x18007f800`
- `0x1800a68e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ccd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ccd7`
- `ntdll!RtlFreeUnicodeString` at `0x18004ccb1`
- `ntdll!RtlFreeUnicodeString` at `0x18004ccb1`
- `ntdll!RtlpEnsureBufferSize` at `0x18004cae5`
- `ntdll!RtlpEnsureBufferSize` at `0x18004cae5`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18004cb5d`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18004cb5d`
- `ntdll!RtlNtStatusToDosError` at `0x18004ccc9`
- `ntdll!RtlNtStatusToDosError` at `0x18004ccc9`
- `win32u!NtGdiGetFontFileInfo` at `0x18004ca18`
- `win32u!NtGdiGetFontFileInfo` at `0x18004ca18`

## pseudocode

```c
__int64 __fastcall GetFontFileInfo(__int64 a1, __int64 a2, __int64 a3, unsigned __int64 a4, _QWORD *a5)
{
  ULONG FontFileInfo; // eax
  WCHAR *p_MinimumStaticBufferForTerminalNul; // rdx
  UCHAR *StaticBuffer; // rcx
  _WORD *v10; // rdi
  __int64 v11; // r8
  _WORD *v12; // rax
  signed int v13; // ebx
  USHORT Length; // bx
  PWSTR Buffer; // r12
  USHORT v16; // r9
  SIZE_T v17; // r8
  NTSTATUS v18; // eax
  USHORT v19; // r15
  unsigned __int64 v21; // rdx
  PWSTR v22; // rcx
  __int64 v23; // rax
  _WORD *v24; // rcx
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-D0h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+40h] [rbp-C0h] BYREF

  memset(&Path, 0, 56);
  FontFileInfo = NtGdiGetFontFileInfo(a1);
  if ( FontFileInfo )
    goto LABEL_42;
  Path.MinimumStaticBufferForTerminalNul = 0;
  Path.ByteBuffer.Size = 520;
  p_MinimumStaticBufferForTerminalNul = &Path.MinimumStaticBufferForTerminalNul;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.MinimumStaticBufferForTerminalNul;
  StaticBuffer = (UCHAR *)&Path.MinimumStaticBufferForTerminalNul;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.MinimumStaticBufferForTerminalNul;
  Path.ByteBuffer.StaticSize = 520;
  Path.String.Buffer = &Path.MinimumStaticBufferForTerminalNul;
  *(_DWORD *)&Path.String.Length = 34078720;
  UnicodeString = 0;
  v10 = (_WORD *)(a3 + 16);
  if ( v10 )
  {
    v11 = 0x7FFF;
    v12 = v10;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v13 = v11 == 0 ? 0xC000000D : 0;
    if ( !v11 )
      goto LABEL_15;
    Length = -2 - 2 * v11;
    Buffer = v10;
  }
  else
  {
    Buffer = UnicodeString.Buffer;
    Length = UnicodeString.Length;
  }
  v16 = 0;
  Path.String.Length = 0;
  v17 = Length + 2LL;
  if ( v17 > 0xFFFE )
  {
    v13 = -1073741562;
    goto LABEL_15;
  }
  if ( v17 <= 0x208 )
    goto LABEL_12;
  v18 = RtlpEnsureBufferSize(0, &Path.ByteBuffer, v17);
  p_MinimumStaticBufferForTerminalNul = (WCHAR *)Path.ByteBuffer.Buffer;
  if ( v18 >= 0 )
  {
    v16 = Path.String.Length;
LABEL_12:
    Path.String.Buffer = p_MinimumStaticBufferForTerminalNul;
    memmove_0(&p_MinimumStaticBufferForTerminalNul[(unsigned __int64)v16 >> 1], Buffer, Length);
    v19 = Path.String.Length + Length + 2;
    Path.String.Length += Length;
    Path.String.MaximumLength = v19;
    Path.String.Buffer[(unsigned __int64)Path.String.Length >> 1] = 0;
    v13 = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
    if ( v13 >= 0 )
    {
      if ( Path.String.Length > a4 )
      {
        if ( a5 )
          *a5 = Path.String.Length;
        v13 = -1073741789;
      }
      else
      {
        v21 = (a4 - 16) >> 1;
        if ( v21 )
        {
          if ( v21 > 0x7FFFFFFF )
          {
            v13 = -1073741811;
            *v10 = 0;
          }
          else
          {
            v22 = Path.String.Buffer;
            v23 = 2147483646;
            do
            {
              if ( !v23 )
                break;
              if ( !*v22 )
                break;
              *v10++ = *v22++;
              --v23;
              --v21;
            }
            while ( v21 );
            v24 = v10 - 1;
            if ( v21 )
              v24 = v10;
            v13 = v21 == 0 ? 0x80000005 : 0;
            *v24 = 0;
          }
        }
        else
        {
          v13 = -1073741811;
        }
      }
    }
    p_MinimumStaticBufferForTerminalNul = (WCHAR *)Path.ByteBuffer.Buffer;
    goto LABEL_14;
  }
  v13 = -1073741801;
LABEL_14:
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
LABEL_15:
  if ( p_MinimumStaticBufferForTerminalNul )
  {
    if ( p_MinimumStaticBufferForTerminalNul != (WCHAR *)StaticBuffer )
    {
      *(_QWORD *)&UnicodeString.Length = 0;
      UnicodeString.Buffer = p_MinimumStaticBufferForTerminalNul;
      RtlFreeUnicodeString(&UnicodeString);
      StaticBuffer = Path.ByteBuffer.StaticBuffer;
    }
    Path.ByteBuffer.Size = Path.ByteBuffer.StaticSize;
    Path.ByteBuffer.Buffer = StaticBuffer;
  }
  Path.String.Buffer = (PWSTR)StaticBuffer;
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  Path.String.MaximumLength = Path.ByteBuffer.StaticSize;
  Path.String.Length = 0;
  if ( v13 >= 0 )
    return 1;
  FontFileInfo = RtlNtStatusToDosError(v13);
LABEL_42:
  SetLastError(FontFileInfo);
  return 0;
}

```

## disassembly

```asm
0x18004c9c0  push    rbp
0x18004c9c2  push    rbx
0x18004c9c3  push    rsi
0x18004c9c4  push    rdi
0x18004c9c5  push    r12
0x18004c9c7  push    r13
0x18004c9c9  push    r14
0x18004c9cb  push    r15
0x18004c9cd  lea     rbp, [rsp-1A8h]
0x18004c9d5  sub     rsp, 2A8h
0x18004c9dc  mov     rax, cs:__security_cookie
0x18004c9e3  xor     rax, rsp
0x18004c9e6  mov     [rbp+1E0h+var_50], rax
0x18004c9ed  mov     rsi, [rbp+1E0h+arg_20]
0x18004c9f4  xorps   xmm0, xmm0
0x18004c9f7  xor     eax, eax
0x18004c9f9  mov     [rsp+2E0h+var_2C0], rsi
0x18004c9fe  movups  xmmword ptr [rsp+2E0h+Path.String.Length], xmm0
0x18004ca03  mov     [rsp+2E0h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x18004ca08  mov     r14, r9
0x18004ca0b  movups  xmmword ptr [rsp+2E0h+Path.ByteBuffer.Buffer], xmm0
0x18004ca10  mov     rdi, r8
0x18004ca13  movups  xmmword ptr [rsp+2E0h+Path.ByteBuffer.Size], xmm0
0x18004ca18  call    cs:__imp_NtGdiGetFontFileInfo
0x18004ca1f  nop     dword ptr [rax+rax+00h]
0x18004ca24  xor     r13d, r13d
0x18004ca27  test    eax, eax
0x18004ca29  jnz     loc_18004CCD5
0x18004ca2f  mov     [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul], r13w
0x18004ca34  mov     r10d, 208h
0x18004ca3a  mov     [rsp+2E0h+Path.ByteBuffer.Size], r10
0x18004ca3f  lea     rdx, [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul]
0x18004ca43  mov     [rsp+2E0h+Path.ByteBuffer.Buffer], rdx
0x18004ca48  lea     rcx, [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul]
0x18004ca4c  mov     [rsp+2E0h+Path.ByteBuffer.StaticBuffer], rcx
0x18004ca51  lea     rax, [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul]
0x18004ca55  mov     [rsp+2E0h+Path.ByteBuffer.StaticSize], r10
0x18004ca5a  xorps   xmm0, xmm0
0x18004ca5d  mov     [rsp+2E0h+Path.String.Buffer], rax
0x18004ca62  mov     r11d, 0FFFEh
0x18004ca68  mov     dword ptr [rsp+2E0h+Path.String.Length], 2080000h
0x18004ca70  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x18004ca75  add     rdi, 10h
0x18004ca79  jz      loc_18004CC59
0x18004ca7f  mov     r8d, 7FFFh
0x18004ca85  mov     rax, rdi
0x18004ca88  cmp     [rax], r13w
0x18004ca8c  jz      short loc_18004CA98
0x18004ca8e  add     rax, 2
0x18004ca92  sub     r8, 1
0x18004ca96  jnz     short loc_18004CA88
0x18004ca98  mov     rax, r8
0x18004ca9b  neg     rax
0x18004ca9e  sbb     ebx, ebx
0x18004caa0  not     ebx
0x18004caa2  and     ebx, 0C000000Dh
0x18004caa8  test    r8, r8
0x18004caab  jz      loc_18004CB79
0x18004cab1  add     r8w, r8w
0x18004cab5  mov     ebx, r11d
0x18004cab8  sub     bx, r8w
0x18004cabc  mov     r12, rdi
0x18004cabf  movzx   r15d, bx
0x18004cac3  mov     r9d, r13d
0x18004cac6  mov     [rsp+2E0h+Path.String.Length], r13w
0x18004cacc  lea     r8, [r15+2]; RequiredSize
0x18004cad0  cmp     r8, r11
0x18004cad3  ja      loc_18004CC68
0x18004cad9  cmp     r8, r10
0x18004cadc  jbe     short loc_18004CB04
0x18004cade  lea     rdx, [rsp+2E0h+Path.ByteBuffer]; Buffer
0x18004cae3  xor     ecx, ecx; Flags
0x18004cae5  call    cs:__imp_RtlpEnsureBufferSize
0x18004caec  nop     dword ptr [rax+rax+00h]
0x18004caf1  mov     rdx, [rsp+2E0h+Path.ByteBuffer.Buffer]
0x18004caf6  test    eax, eax
0x18004caf8  js      loc_18004CBE5
0x18004cafe  movzx   r9d, [rsp+2E0h+Path.String.Length]
0x18004cb04  movzx   eax, r9w
0x18004cb08  shr     rax, 1
0x18004cb0b  mov     [rsp+2E0h+Path.String.Buffer], rdx
0x18004cb10  movzx   r8d, bx; Size
0x18004cb14  lea     rcx, [rdx+rax*2]; void *
0x18004cb18  mov     rdx, r12; Src
0x18004cb1b  call    memmove_0
0x18004cb20  add     bx, [rsp+2E0h+Path.String.Length]
0x18004cb25  mov     r12d, 2
0x18004cb2b  add     r15w, [rsp+2E0h+Path.String.Length]
0x18004cb31  xor     r9d, r9d; Unknown
0x18004cb34  mov     rax, [rsp+2E0h+Path.String.Buffer]
0x18004cb39  add     r15w, r12w
0x18004cb3d  movzx   edx, bx
0x18004cb40  xor     r8d, r8d; PathType
0x18004cb43  mov     [rsp+2E0h+Path.String.Length], dx
0x18004cb48  xor     ecx, ecx; Flags
0x18004cb4a  shr     rdx, 1
0x18004cb4d  mov     [rsp+2E0h+Path.String.MaximumLength], r15w
0x18004cb53  mov     [rax+rdx*2], r13w
0x18004cb58  lea     rdx, [rsp+2E0h+Path]; Path
0x18004cb5d  call    cs:__imp_RtlNtPathNameToDosPathName
0x18004cb64  nop     dword ptr [rax+rax+00h]
0x18004cb69  mov     ebx, eax
0x18004cb6b  test    eax, eax
0x18004cb6d  jns     short loc_18004CBEC
0x18004cb6f  mov     rdx, [rsp+2E0h+Path.ByteBuffer.Buffer]
0x18004cb74  mov     rcx, [rsp+2E0h+Path.ByteBuffer.StaticBuffer]
0x18004cb79  test    rdx, rdx
0x18004cb7c  jz      short loc_18004CB96
0x18004cb7e  cmp     rdx, rcx
0x18004cb81  jnz     loc_18004CCA2
0x18004cb87  mov     rax, [rsp+2E0h+Path.ByteBuffer.StaticSize]
0x18004cb8c  mov     [rsp+2E0h+Path.ByteBuffer.Size], rax
0x18004cb91  mov     [rsp+2E0h+Path.ByteBuffer.Buffer], rcx
0x18004cb96  mov     [rsp+2E0h+Path.String.Buffer], rcx
0x18004cb9b  test    rcx, rcx
0x18004cb9e  jz      short loc_18004CBA4
0x18004cba0  mov     [rcx], r13w
0x18004cba4  movzx   eax, word ptr [rsp+2E0h+Path.ByteBuffer.StaticSize]
0x18004cba9  mov     [rsp+2E0h+Path.String.MaximumLength], ax
0x18004cbae  mov     [rsp+2E0h+Path.String.Length], r13w
0x18004cbb4  test    ebx, ebx
0x18004cbb6  js      loc_18004CCC7
0x18004cbbc  mov     eax, 1
0x18004cbc1  mov     rcx, [rbp+1E0h+var_50]
0x18004cbc8  xor     rcx, rsp; StackCookie
0x18004cbcb  call    __security_check_cookie
0x18004cbd0  add     rsp, 2A8h
0x18004cbd7  pop     r15
0x18004cbd9  pop     r14
0x18004cbdb  pop     r13
0x18004cbdd  pop     r12
0x18004cbdf  pop     rdi
0x18004cbe0  pop     rsi
0x18004cbe1  pop     rbx
0x18004cbe2  pop     rbp
0x18004cbe3  retn
0x18004cbe5  mov     ebx, 0C0000017h
0x18004cbea  jmp     short loc_18004CB74
0x18004cbec  movzx   eax, [rsp+2E0h+Path.String.Length]
0x18004cbf1  cmp     rax, r14
0x18004cbf4  ja      short loc_18004CC72
0x18004cbf6  lea     rdx, [r14-10h]
0x18004cbfa  shr     rdx, 1
0x18004cbfd  jz      loc_18004CC8B
0x18004cc03  cmp     rdx, 7FFFFFFFh
0x18004cc0a  ja      short loc_18004CC84
0x18004cc0c  mov     rcx, [rsp+2E0h+Path.String.Buffer]
0x18004cc11  mov     eax, 7FFFFFFEh
0x18004cc16  test    rax, rax
0x18004cc19  jz      short loc_18004CC38
0x18004cc1b  movzx   r8d, word ptr [rcx]
0x18004cc1f  test    r8w, r8w
0x18004cc23  jz      short loc_18004CC38
0x18004cc25  mov     [rdi], r8w
0x18004cc29  add     rcx, r12
0x18004cc2c  add     rdi, r12
0x18004cc2f  dec     rax
0x18004cc32  sub     rdx, 1
0x18004cc36  jnz     short loc_18004CC16
0x18004cc38  test    rdx, rdx
0x18004cc3b  lea     rcx, [rdi-2]
0x18004cc3f  cmovnz  rcx, rdi
0x18004cc43  neg     rdx
0x18004cc46  sbb     ebx, ebx
0x18004cc48  not     ebx
0x18004cc4a  and     ebx, 80000005h
0x18004cc50  mov     [rcx], r13w
0x18004cc54  jmp     loc_18004CB6F
0x18004cc59  mov     r12, [rsp+2E0h+UnicodeString.Buffer]
0x18004cc5e  movzx   ebx, [rsp+2E0h+UnicodeString.Length]
0x18004cc63  jmp     loc_18004CABF
0x18004cc68  mov     ebx, 0C0000106h
0x18004cc6d  jmp     loc_18004CB79
0x18004cc72  test    rsi, rsi
0x18004cc75  jz      short loc_18004CC7A
0x18004cc77  mov     [rsi], rax
0x18004cc7a  mov     ebx, 0C0000023h
0x18004cc7f  jmp     loc_18004CB6F
0x18004cc84  mov     ebx, 0C000000Dh
0x18004cc89  jmp     short loc_18004CC99
0x18004cc8b  mov     ebx, 0C000000Dh
0x18004cc90  test    rdx, rdx
0x18004cc93  jz      loc_18004CB6F
0x18004cc99  mov     [rdi], r13w
0x18004cc9d  jmp     loc_18004CB6F
0x18004cca2  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x18004cca7  mov     qword ptr [rsp+2E0h+UnicodeString.Length], r13
0x18004ccac  mov     [rsp+2E0h+UnicodeString.Buffer], rdx
0x18004ccb1  call    cs:__imp_RtlFreeUnicodeString
0x18004ccb8  nop     dword ptr [rax+rax+00h]
0x18004ccbd  mov     rcx, [rsp+2E0h+Path.ByteBuffer.StaticBuffer]
0x18004ccc2  jmp     loc_18004CB87
0x18004ccc7  mov     ecx, ebx; Status
0x18004ccc9  call    cs:__imp_RtlNtStatusToDosError
0x18004ccd0  nop     dword ptr [rax+rax+00h]
0x18004ccd5  mov     ecx, eax; dwErrCode
0x18004ccd7  call    cs:__imp_SetLastError
0x18004ccde  nop     dword ptr [rax+rax+00h]
0x18004cce3  xor     eax, eax
0x18004cce5  jmp     loc_18004CBC1
```
