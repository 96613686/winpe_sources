# GetFontFileInfo

- ea: `0x180041070`
- end: `0x180041375`
- name: `GetFontFileInfo`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x180041070`
- `0x18007ac50`
- `0x1800a3520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041368`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041368`
- `ntdll!RtlFreeUnicodeString` at `0x18004134e`
- `ntdll!RtlFreeUnicodeString` at `0x18004134e`
- `ntdll!RtlpEnsureBufferSize` at `0x18004118f`
- `ntdll!RtlpEnsureBufferSize` at `0x18004118f`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180041201`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180041201`
- `ntdll!RtlNtStatusToDosError` at `0x180041360`
- `ntdll!RtlNtStatusToDosError` at `0x180041360`
- `win32u!NtGdiGetFontFileInfo` at `0x1800410c8`
- `win32u!NtGdiGetFontFileInfo` at `0x1800410c8`

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
0x180041070  push    rbp
0x180041072  push    rbx
0x180041073  push    rsi
0x180041074  push    rdi
0x180041075  push    r12
0x180041077  push    r13
0x180041079  push    r14
0x18004107b  push    r15
0x18004107d  lea     rbp, [rsp-1A8h]
0x180041085  sub     rsp, 2A8h
0x18004108c  mov     rax, cs:__security_cookie
0x180041093  xor     rax, rsp
0x180041096  mov     [rbp+1E0h+var_50], rax
0x18004109d  mov     rsi, [rbp+1E0h+arg_20]
0x1800410a4  xorps   xmm0, xmm0
0x1800410a7  xor     eax, eax
0x1800410a9  mov     [rsp+2E0h+var_2C0], rsi
0x1800410ae  movups  xmmword ptr [rsp+2E0h+Path.String.Length], xmm0
0x1800410b3  mov     [rsp+2E0h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x1800410b8  mov     r14, r9
0x1800410bb  movups  xmmword ptr [rsp+2E0h+Path.ByteBuffer.Buffer], xmm0
0x1800410c0  mov     rdi, r8
0x1800410c3  movups  xmmword ptr [rsp+2E0h+Path.ByteBuffer.Size], xmm0
0x1800410c8  call    cs:__imp_NtGdiGetFontFileInfo
0x1800410ce  xor     r13d, r13d
0x1800410d1  test    eax, eax
0x1800410d3  jnz     loc_180041366
0x1800410d9  mov     [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul], r13w
0x1800410de  mov     r10d, 208h
0x1800410e4  mov     [rsp+2E0h+Path.ByteBuffer.Size], r10
0x1800410e9  lea     rdx, [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul]
0x1800410ed  mov     [rsp+2E0h+Path.ByteBuffer.Buffer], rdx
0x1800410f2  lea     rcx, [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul]
0x1800410f6  mov     [rsp+2E0h+Path.ByteBuffer.StaticBuffer], rcx
0x1800410fb  lea     rax, [rbp+1E0h+Path.MinimumStaticBufferForTerminalNul]
0x1800410ff  mov     [rsp+2E0h+Path.ByteBuffer.StaticSize], r10
0x180041104  xorps   xmm0, xmm0
0x180041107  mov     [rsp+2E0h+Path.String.Buffer], rax
0x18004110c  mov     r11d, 0FFFEh
0x180041112  mov     dword ptr [rsp+2E0h+Path.String.Length], 2080000h
0x18004111a  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x18004111f  add     rdi, 10h
0x180041123  jz      loc_1800412F6
0x180041129  mov     r8d, 7FFFh
0x18004112f  mov     rax, rdi
0x180041132  cmp     [rax], r13w
0x180041136  jz      short loc_180041142
0x180041138  add     rax, 2
0x18004113c  sub     r8, 1
0x180041140  jnz     short loc_180041132
0x180041142  mov     rax, r8
0x180041145  neg     rax
0x180041148  sbb     ebx, ebx
0x18004114a  not     ebx
0x18004114c  and     ebx, 0C000000Dh
0x180041152  test    r8, r8
0x180041155  jz      loc_180041217
0x18004115b  add     r8w, r8w
0x18004115f  mov     ebx, r11d
0x180041162  sub     bx, r8w
0x180041166  mov     r12, rdi
0x180041169  movzx   r15d, bx
0x18004116d  mov     r9d, r13d
0x180041170  mov     [rsp+2E0h+Path.String.Length], r13w
0x180041176  lea     r8, [r15+2]; RequiredSize
0x18004117a  cmp     r8, r11
0x18004117d  ja      loc_180041305
0x180041183  cmp     r8, r10
0x180041186  jbe     short loc_1800411A8
0x180041188  lea     rdx, [rsp+2E0h+Path.ByteBuffer]; Buffer
0x18004118d  xor     ecx, ecx; Flags
0x18004118f  call    cs:__imp_RtlpEnsureBufferSize
0x180041195  mov     rdx, [rsp+2E0h+Path.ByteBuffer.Buffer]
0x18004119a  test    eax, eax
0x18004119c  js      loc_180041282
0x1800411a2  movzx   r9d, [rsp+2E0h+Path.String.Length]
0x1800411a8  movzx   eax, r9w
0x1800411ac  shr     rax, 1
0x1800411af  mov     [rsp+2E0h+Path.String.Buffer], rdx
0x1800411b4  movzx   r8d, bx; Size
0x1800411b8  lea     rcx, [rdx+rax*2]; void *
0x1800411bc  mov     rdx, r12; Src
0x1800411bf  call    memmove_0
0x1800411c4  add     bx, [rsp+2E0h+Path.String.Length]
0x1800411c9  mov     r12d, 2
0x1800411cf  add     r15w, [rsp+2E0h+Path.String.Length]
0x1800411d5  xor     r9d, r9d; Unknown
0x1800411d8  mov     rax, [rsp+2E0h+Path.String.Buffer]
0x1800411dd  add     r15w, r12w
0x1800411e1  movzx   edx, bx
0x1800411e4  xor     r8d, r8d; PathType
0x1800411e7  mov     [rsp+2E0h+Path.String.Length], dx
0x1800411ec  xor     ecx, ecx; Flags
0x1800411ee  shr     rdx, 1
0x1800411f1  mov     [rsp+2E0h+Path.String.MaximumLength], r15w
0x1800411f7  mov     [rax+rdx*2], r13w
0x1800411fc  lea     rdx, [rsp+2E0h+Path]; Path
0x180041201  call    cs:__imp_RtlNtPathNameToDosPathName
0x180041207  mov     ebx, eax
0x180041209  test    eax, eax
0x18004120b  jns     short loc_180041289
0x18004120d  mov     rdx, [rsp+2E0h+Path.ByteBuffer.Buffer]
0x180041212  mov     rcx, [rsp+2E0h+Path.ByteBuffer.StaticBuffer]
0x180041217  test    rdx, rdx
0x18004121a  jz      short loc_180041234
0x18004121c  cmp     rdx, rcx
0x18004121f  jnz     loc_18004133F
0x180041225  mov     rax, [rsp+2E0h+Path.ByteBuffer.StaticSize]
0x18004122a  mov     [rsp+2E0h+Path.ByteBuffer.Size], rax
0x18004122f  mov     [rsp+2E0h+Path.ByteBuffer.Buffer], rcx
0x180041234  mov     [rsp+2E0h+Path.String.Buffer], rcx
0x180041239  test    rcx, rcx
0x18004123c  jz      short loc_180041242
0x18004123e  mov     [rcx], r13w
0x180041242  movzx   eax, word ptr [rsp+2E0h+Path.ByteBuffer.StaticSize]
0x180041247  mov     [rsp+2E0h+Path.String.MaximumLength], ax
0x18004124c  mov     [rsp+2E0h+Path.String.Length], r13w
0x180041252  test    ebx, ebx
0x180041254  js      loc_18004135E
0x18004125a  mov     eax, 1
0x18004125f  mov     rcx, [rbp+1E0h+var_50]
0x180041266  xor     rcx, rsp; StackCookie
0x180041269  call    __security_check_cookie
0x18004126e  add     rsp, 2A8h
0x180041275  pop     r15
0x180041277  pop     r14
0x180041279  pop     r13
0x18004127b  pop     r12
0x18004127d  pop     rdi
0x18004127e  pop     rsi
0x18004127f  pop     rbx
0x180041280  pop     rbp
0x180041281  retn
0x180041282  mov     ebx, 0C0000017h
0x180041287  jmp     short loc_180041212
0x180041289  movzx   eax, [rsp+2E0h+Path.String.Length]
0x18004128e  cmp     rax, r14
0x180041291  ja      short loc_18004130F
0x180041293  lea     rdx, [r14-10h]
0x180041297  shr     rdx, 1
0x18004129a  jz      loc_180041328
0x1800412a0  cmp     rdx, 7FFFFFFFh
0x1800412a7  ja      short loc_180041321
0x1800412a9  mov     rcx, [rsp+2E0h+Path.String.Buffer]
0x1800412ae  mov     eax, 7FFFFFFEh
0x1800412b3  test    rax, rax
0x1800412b6  jz      short loc_1800412D5
0x1800412b8  movzx   r8d, word ptr [rcx]
0x1800412bc  test    r8w, r8w
0x1800412c0  jz      short loc_1800412D5
0x1800412c2  mov     [rdi], r8w
0x1800412c6  add     rcx, r12
0x1800412c9  add     rdi, r12
0x1800412cc  dec     rax
0x1800412cf  sub     rdx, 1
0x1800412d3  jnz     short loc_1800412B3
0x1800412d5  test    rdx, rdx
0x1800412d8  lea     rcx, [rdi-2]
0x1800412dc  cmovnz  rcx, rdi
0x1800412e0  neg     rdx
0x1800412e3  sbb     ebx, ebx
0x1800412e5  not     ebx
0x1800412e7  and     ebx, 80000005h
0x1800412ed  mov     [rcx], r13w
0x1800412f1  jmp     loc_18004120D
0x1800412f6  mov     r12, [rsp+2E0h+UnicodeString.Buffer]
0x1800412fb  movzx   ebx, [rsp+2E0h+UnicodeString.Length]
0x180041300  jmp     loc_180041169
0x180041305  mov     ebx, 0C0000106h
0x18004130a  jmp     loc_180041217
0x18004130f  test    rsi, rsi
0x180041312  jz      short loc_180041317
0x180041314  mov     [rsi], rax
0x180041317  mov     ebx, 0C0000023h
0x18004131c  jmp     loc_18004120D
0x180041321  mov     ebx, 0C000000Dh
0x180041326  jmp     short loc_180041336
0x180041328  mov     ebx, 0C000000Dh
0x18004132d  test    rdx, rdx
0x180041330  jz      loc_18004120D
0x180041336  mov     [rdi], r13w
0x18004133a  jmp     loc_18004120D
0x18004133f  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x180041344  mov     qword ptr [rsp+2E0h+UnicodeString.Length], r13
0x180041349  mov     [rsp+2E0h+UnicodeString.Buffer], rdx
0x18004134e  call    cs:__imp_RtlFreeUnicodeString
0x180041354  mov     rcx, [rsp+2E0h+Path.ByteBuffer.StaticBuffer]
0x180041359  jmp     loc_180041225
0x18004135e  mov     ecx, ebx; Status
0x180041360  call    cs:__imp_RtlNtStatusToDosError
0x180041366  mov     ecx, eax; dwErrCode
0x180041368  call    cs:__imp_SetLastError
0x18004136e  xor     eax, eax
0x180041370  jmp     loc_18004125F
```
