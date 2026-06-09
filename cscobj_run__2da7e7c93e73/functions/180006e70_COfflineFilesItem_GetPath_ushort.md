# COfflineFilesItem::_GetPath(ushort * *)

- ea: `0x180006e70`
- end: `0x1800070d5`
- name: `?_GetPath@COfflineFilesItem@@IEAAJPEAPEAG@Z`
- size: `613`
- prototype: `int(COfflineFilesItem *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009820`
- `0x18000fa00`

## callees

- `0x180005d50`
- `0x180006e70`
- `0x180008550`
- `0x18000b7c0`
- `0x1800102a8`
- `0x18002ac30`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800070a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800070a2`
- `ntdll!RtlpEnsureBufferSize` at `0x180006f5f`
- `ntdll!RtlpEnsureBufferSize` at `0x180006f5f`
- `ntdll!RtlAppendPathElement` at `0x18000700c`
- `ntdll!RtlAppendPathElement` at `0x18000700c`
- `ntdll!RtlpApplyLengthFunction` at `0x18000703a`
- `ntdll!RtlpApplyLengthFunction` at `0x18000703a`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180007023`
- `ntdll!RtlInitUnicodeString` at `0x180006f24`
- `ntdll!RtlInitUnicodeString` at `0x180006ff5`
- `ntdll!RtlInitUnicodeString` at `0x180006f24`
- `ntdll!RtlInitUnicodeString` at `0x180006ff5`

## pseudocode

```c
__int64 __fastcall COfflineFilesItem::_GetPath(COfflineFilesItem *this, LPVOID *a2)
{
  const WCHAR *v5; // rdx
  USHORT Length; // r9
  unsigned __int16 v7; // dx
  unsigned __int64 v8; // r8
  int v9; // ecx
  int StringCopyForCom; // ebx
  unsigned __int64 v11; // rdx
  int appended; // eax
  NTSTATUS v13; // eax
  const unsigned __int16 *ConstBuffer; // rax
  unsigned int v15; // edi
  PUCHAR StaticBuffer; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v18[260]; // [rsp+30h] [rbp-D0h] BYREF
  int UnicodeStringOrUnicodeStringBuffer; // [rsp+238h] [rbp+138h] BYREF
  PUCHAR v20; // [rsp+240h] [rbp+140h]
  struct _RTL_BUFFER Buffer; // [rsp+248h] [rbp+148h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (const WCHAR *)*((_QWORD *)this + 70);
  Buffer.Buffer = (PUCHAR)v18;
  Buffer.StaticBuffer = (PUCHAR)v18;
  v20 = (PUCHAR)v18;
  Buffer.Size = 520;
  Buffer.StaticSize = 520;
  v18[0] = 0;
  UnicodeStringOrUnicodeStringBuffer = 34078720;
  if ( v5 == *((const WCHAR **)this + 71) )
    v5 = (const WCHAR *)*((_QWORD *)this + 69);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v5);
  Length = DestinationString.Length;
  v7 = 0;
  LOWORD(UnicodeStringOrUnicodeStringBuffer) = 0;
  v8 = DestinationString.Length + 2LL;
  if ( v8 > 0xFFFE )
  {
    v9 = -1073741562;
    goto LABEL_10;
  }
  if ( v8 <= Buffer.Size )
  {
LABEL_13:
    v20 = Buffer.Buffer;
    memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v7 >> 1)], DestinationString.Buffer, Length);
    v11 = (unsigned __int16)(DestinationString.Length + UnicodeStringOrUnicodeStringBuffer);
    LOWORD(UnicodeStringOrUnicodeStringBuffer) = v11;
    HIWORD(UnicodeStringOrUnicodeStringBuffer) = v11 + 2;
    *(_WORD *)&v20[2 * (v11 >> 1)] = 0;
    goto LABEL_14;
  }
  if ( RtlpEnsureBufferSize(0, &Buffer, v8) >= 0 )
  {
    v7 = UnicodeStringOrUnicodeStringBuffer;
    Length = DestinationString.Length;
    goto LABEL_13;
  }
  v9 = -1073741801;
LABEL_10:
  StringCopyForCom = ResultFromNtStatus(v9);
  if ( StringCopyForCom >= 0 )
  {
LABEL_14:
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 407);
    appended = RtlAppendPathElement(1, &UnicodeStringOrUnicodeStringBuffer, &DestinationString);
    if ( appended >= 0 || (StringCopyForCom = ResultFromNtStatus(appended), StringCopyForCom >= 0) )
    {
      StringCopyForCom = 0;
      v13 = RtlpApplyLengthFunction(
              0,
              0x38u,
              &UnicodeStringOrUnicodeStringBuffer,
              RtlGetLengthWithoutTrailingPathSeperators);
      if ( v13 < 0 )
        StringCopyForCom = ResultFromNtStatus(v13);
      if ( StringCopyForCom >= 0 )
      {
        ConstBuffer = CPath::_GetConstBuffer((CPath *)v18);
        StringCopyForCom = CscUtil_CreateStringCopyForCom(ConstBuffer, a2);
      }
    }
  }
  v15 = 0;
  StaticBuffer = Buffer.StaticBuffer;
  if ( StringCopyForCom < 0 )
    v15 = StringCopyForCom;
  if ( Buffer.Buffer && Buffer.Buffer != Buffer.StaticBuffer )
  {
    DestinationString.Buffer = (PWSTR)Buffer.Buffer;
    *(_QWORD *)&DestinationString.Length = 0;
    RtlFreeUnicodeString(&DestinationString);
    StaticBuffer = Buffer.StaticBuffer;
  }
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return v15;
}

```

## disassembly

```asm
0x180006e70  push    rbp
0x180006e72  push    rsi
0x180006e73  push    rdi
0x180006e74  lea     rbp, [rsp-180h]
0x180006e7c  sub     rsp, 280h
0x180006e83  mov     rax, cs:__security_cookie
0x180006e8a  xor     rax, rsp
0x180006e8d  mov     [rbp+190h+Buffer.ReservedForIMalloc], rax
0x180006e94  mov     rsi, rdx
0x180006e97  mov     rdi, rcx
0x180006e9a  test    rdx, rdx
0x180006e9d  jnz     short loc_180006EA9
0x180006e9f  mov     eax, 80004003h
0x180006ea4  jmp     loc_1800070BB
0x180006ea9  lea     rax, [rsp+290h+var_260]
0x180006eae  mov     qword ptr [rdx], 0
0x180006eb5  mov     rdx, [rdi+230h]
0x180006ebc  mov     ecx, 208h
0x180006ec1  mov     [rbp+190h+Buffer.Buffer], rax
0x180006ec8  lea     rax, [rsp+290h+var_260]
0x180006ecd  mov     [rbp+190h+Buffer.StaticBuffer], rax
0x180006ed4  lea     rax, [rsp+290h+var_260]
0x180006ed9  mov     [rbp+190h+var_50], rax
0x180006ee0  xor     eax, eax
0x180006ee2  mov     [rsp+290h+arg_10], rbx
0x180006eea  mov     [rbp+190h+Buffer.Size], rcx
0x180006ef1  mov     [rbp+190h+Buffer.StaticSize], rcx
0x180006ef8  mov     [rsp+290h+var_260], ax
0x180006efd  mov     [rbp+190h+UnicodeStringOrUnicodeStringBuffer], 2080000h
0x180006f07  cmp     rdx, [rdi+238h]
0x180006f0e  jnz     short loc_180006F17
0x180006f10  mov     rdx, [rdi+228h]; SourceString
0x180006f17  xorps   xmm0, xmm0
0x180006f1a  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x180006f1f  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180006f24  call    cs:__imp_RtlInitUnicodeString
0x180006f2a  movzx   r9d, [rsp+290h+DestinationString.Length]
0x180006f30  xor     edx, edx
0x180006f32  mov     word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer], dx
0x180006f39  lea     r8, [r9+2]; RequiredSize
0x180006f3d  cmp     r8, 0FFFEh
0x180006f44  jbe     short loc_180006F4D
0x180006f46  mov     ecx, 0C0000106h
0x180006f4b  jmp     short loc_180006F6E
0x180006f4d  cmp     r8, [rbp+190h+Buffer.Size]
0x180006f54  jbe     short loc_180006F8B
0x180006f56  lea     rdx, [rbp+190h+Buffer]; Buffer
0x180006f5d  xor     ecx, ecx; Flags
0x180006f5f  call    cs:__imp_RtlpEnsureBufferSize
0x180006f65  test    eax, eax
0x180006f67  jns     short loc_180006F7E
0x180006f69  mov     ecx, 0C0000017h; int
0x180006f6e  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180006f73  mov     ebx, eax
0x180006f75  test    eax, eax
0x180006f77  jns     short loc_180006FE1
0x180006f79  jmp     loc_180007068
0x180006f7e  movzx   edx, word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer]
0x180006f85  movzx   r9d, [rsp+290h+DestinationString.Length]
0x180006f8b  mov     rcx, [rbp+190h+Buffer.Buffer]
0x180006f92  movzx   eax, dx
0x180006f95  mov     rdx, [rsp+290h+DestinationString.Buffer]; Src
0x180006f9a  shr     rax, 1
0x180006f9d  mov     [rbp+190h+var_50], rcx
0x180006fa4  movzx   r8d, r9w; Size
0x180006fa8  lea     rcx, [rcx+rax*2]; void *
0x180006fac  call    memmove_0
0x180006fb1  movzx   eax, word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer]
0x180006fb8  add     ax, [rsp+290h+DestinationString.Length]
0x180006fbd  movzx   edx, ax
0x180006fc0  mov     word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer], dx
0x180006fc7  lea     eax, [rdx+2]
0x180006fca  shr     rdx, 1
0x180006fcd  mov     word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180006fd4  xor     ecx, ecx
0x180006fd6  mov     rax, [rbp+190h+var_50]
0x180006fdd  mov     [rax+rdx*2], cx
0x180006fe1  xorps   xmm0, xmm0
0x180006fe4  lea     rdx, [rdi+32Eh]; SourceString
0x180006feb  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x180006ff0  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180006ff5  call    cs:__imp_RtlInitUnicodeString
0x180006ffb  lea     r8, [rsp+290h+DestinationString]
0x180007000  mov     ecx, 1
0x180007005  lea     rdx, [rbp+190h+UnicodeStringOrUnicodeStringBuffer]
0x18000700c  call    cs:__imp_RtlAppendPathElement
0x180007012  test    eax, eax
0x180007014  jns     short loc_180007023
0x180007016  mov     ecx, eax; int
0x180007018  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000701d  mov     ebx, eax
0x18000701f  test    eax, eax
0x180007021  js      short loc_180007068
0x180007023  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x18000702a  lea     r8, [rbp+190h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x180007031  mov     edx, 38h ; '8'; Type
0x180007036  xor     ecx, ecx; Flags
0x180007038  xor     ebx, ebx
0x18000703a  call    cs:__imp_RtlpApplyLengthFunction
0x180007040  test    eax, eax
0x180007042  jns     short loc_18000704D
0x180007044  mov     ecx, eax; int
0x180007046  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000704b  mov     ebx, eax
0x18000704d  test    ebx, ebx
0x18000704f  js      short loc_180007068
0x180007051  lea     rcx, [rsp+290h+var_260]; this
0x180007056  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18000705b  mov     rcx, rax; unsigned __int16 *
0x18000705e  mov     rdx, rsi; unsigned __int16 **
0x180007061  call    ?CscUtil_CreateStringCopyForCom@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopyForCom(ushort const *,ushort * *)
0x180007066  mov     ebx, eax
0x180007068  mov     rcx, [rbp+190h+Buffer.Buffer]
0x18000706f  xor     edi, edi
0x180007071  mov     rax, [rbp+190h+Buffer.StaticBuffer]
0x180007078  test    ebx, ebx
0x18000707a  cmovs   edi, ebx
0x18000707d  mov     rbx, [rsp+290h+arg_10]
0x180007085  test    rcx, rcx
0x180007088  jz      short loc_1800070AF
0x18000708a  cmp     rcx, rax
0x18000708d  jz      short loc_1800070AF
0x18000708f  mov     [rsp+290h+DestinationString.Buffer], rcx
0x180007094  lea     rcx, [rsp+290h+DestinationString]; UnicodeString
0x180007099  mov     qword ptr [rsp+290h+DestinationString.Length], 0
0x1800070a2  call    cs:__imp_RtlFreeUnicodeString
0x1800070a8  mov     rax, [rbp+190h+Buffer.StaticBuffer]
0x1800070af  test    rax, rax
0x1800070b2  jz      short loc_1800070B9
0x1800070b4  xor     ecx, ecx
0x1800070b6  mov     [rax], cx
0x1800070b9  mov     eax, edi
0x1800070bb  mov     rcx, [rbp+190h+Buffer.ReservedForIMalloc]
0x1800070c2  xor     rcx, rsp; StackCookie
0x1800070c5  call    __security_check_cookie
0x1800070ca  add     rsp, 280h
0x1800070d1  pop     rdi
0x1800070d2  pop     rsi
0x1800070d3  pop     rbp
0x1800070d4  retn
```
