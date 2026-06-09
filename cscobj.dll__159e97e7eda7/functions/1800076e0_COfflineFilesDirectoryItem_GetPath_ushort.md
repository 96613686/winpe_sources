# COfflineFilesDirectoryItem::GetPath(ushort * *)

- ea: `0x1800076e0`
- end: `0x180007945`
- name: `?GetPath@COfflineFilesDirectoryItem@@UEAAJPEAPEAG@Z`
- size: `613`
- prototype: `int(COfflineFilesDirectoryItem *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005d50`
- `0x1800076e0`
- `0x180008550`
- `0x18000b7c0`
- `0x1800102a8`
- `0x18002ac30`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180007912`
- `ntdll!RtlFreeUnicodeString` at `0x180007912`
- `ntdll!RtlpEnsureBufferSize` at `0x1800077cf`
- `ntdll!RtlpEnsureBufferSize` at `0x1800077cf`
- `ntdll!RtlAppendPathElement` at `0x18000787c`
- `ntdll!RtlAppendPathElement` at `0x18000787c`
- `ntdll!RtlpApplyLengthFunction` at `0x1800078aa`
- `ntdll!RtlpApplyLengthFunction` at `0x1800078aa`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180007893`
- `ntdll!RtlInitUnicodeString` at `0x180007794`
- `ntdll!RtlInitUnicodeString` at `0x180007865`
- `ntdll!RtlInitUnicodeString` at `0x180007794`
- `ntdll!RtlInitUnicodeString` at `0x180007865`

## pseudocode

```c
__int64 __fastcall COfflineFilesDirectoryItem::GetPath(COfflineFilesDirectoryItem *this, LPVOID *a2)
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
  v5 = (const WCHAR *)*((_QWORD *)this + 81);
  Buffer.Buffer = (PUCHAR)v18;
  Buffer.StaticBuffer = (PUCHAR)v18;
  v20 = (PUCHAR)v18;
  Buffer.Size = 520;
  Buffer.StaticSize = 520;
  v18[0] = 0;
  UnicodeStringOrUnicodeStringBuffer = 34078720;
  if ( v5 == *((const WCHAR **)this + 82) )
    v5 = (const WCHAR *)*((_QWORD *)this + 80);
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
    RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 451);
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
0x1800076e0  push    rbp
0x1800076e2  push    rsi
0x1800076e3  push    rdi
0x1800076e4  lea     rbp, [rsp-180h]
0x1800076ec  sub     rsp, 280h
0x1800076f3  mov     rax, cs:__security_cookie
0x1800076fa  xor     rax, rsp
0x1800076fd  mov     [rbp+190h+Buffer.ReservedForIMalloc], rax
0x180007704  mov     rsi, rdx
0x180007707  mov     rdi, rcx
0x18000770a  test    rdx, rdx
0x18000770d  jnz     short loc_180007719
0x18000770f  mov     eax, 80004003h
0x180007714  jmp     loc_18000792B
0x180007719  lea     rax, [rsp+290h+var_260]
0x18000771e  mov     qword ptr [rdx], 0
0x180007725  mov     rdx, [rdi+288h]
0x18000772c  mov     ecx, 208h
0x180007731  mov     [rbp+190h+Buffer.Buffer], rax
0x180007738  lea     rax, [rsp+290h+var_260]
0x18000773d  mov     [rbp+190h+Buffer.StaticBuffer], rax
0x180007744  lea     rax, [rsp+290h+var_260]
0x180007749  mov     [rbp+190h+var_50], rax
0x180007750  xor     eax, eax
0x180007752  mov     [rsp+290h+arg_10], rbx
0x18000775a  mov     [rbp+190h+Buffer.Size], rcx
0x180007761  mov     [rbp+190h+Buffer.StaticSize], rcx
0x180007768  mov     [rsp+290h+var_260], ax
0x18000776d  mov     [rbp+190h+UnicodeStringOrUnicodeStringBuffer], 2080000h
0x180007777  cmp     rdx, [rdi+290h]
0x18000777e  jnz     short loc_180007787
0x180007780  mov     rdx, [rdi+280h]; SourceString
0x180007787  xorps   xmm0, xmm0
0x18000778a  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x18000778f  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180007794  call    cs:__imp_RtlInitUnicodeString
0x18000779a  movzx   r9d, [rsp+290h+DestinationString.Length]
0x1800077a0  xor     edx, edx
0x1800077a2  mov     word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer], dx
0x1800077a9  lea     r8, [r9+2]; RequiredSize
0x1800077ad  cmp     r8, 0FFFEh
0x1800077b4  jbe     short loc_1800077BD
0x1800077b6  mov     ecx, 0C0000106h
0x1800077bb  jmp     short loc_1800077DE
0x1800077bd  cmp     r8, [rbp+190h+Buffer.Size]
0x1800077c4  jbe     short loc_1800077FB
0x1800077c6  lea     rdx, [rbp+190h+Buffer]; Buffer
0x1800077cd  xor     ecx, ecx; Flags
0x1800077cf  call    cs:__imp_RtlpEnsureBufferSize
0x1800077d5  test    eax, eax
0x1800077d7  jns     short loc_1800077EE
0x1800077d9  mov     ecx, 0C0000017h; int
0x1800077de  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800077e3  mov     ebx, eax
0x1800077e5  test    eax, eax
0x1800077e7  jns     short loc_180007851
0x1800077e9  jmp     loc_1800078D8
0x1800077ee  movzx   edx, word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer]
0x1800077f5  movzx   r9d, [rsp+290h+DestinationString.Length]
0x1800077fb  mov     rcx, [rbp+190h+Buffer.Buffer]
0x180007802  movzx   eax, dx
0x180007805  mov     rdx, [rsp+290h+DestinationString.Buffer]; Src
0x18000780a  shr     rax, 1
0x18000780d  mov     [rbp+190h+var_50], rcx
0x180007814  movzx   r8d, r9w; Size
0x180007818  lea     rcx, [rcx+rax*2]; void *
0x18000781c  call    memmove_0
0x180007821  movzx   eax, word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer]
0x180007828  add     ax, [rsp+290h+DestinationString.Length]
0x18000782d  movzx   edx, ax
0x180007830  mov     word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer], dx
0x180007837  lea     eax, [rdx+2]
0x18000783a  shr     rdx, 1
0x18000783d  mov     word ptr [rbp+190h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180007844  xor     ecx, ecx
0x180007846  mov     rax, [rbp+190h+var_50]
0x18000784d  mov     [rax+rdx*2], cx
0x180007851  xorps   xmm0, xmm0
0x180007854  lea     rdx, [rdi+386h]; SourceString
0x18000785b  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x180007860  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x180007865  call    cs:__imp_RtlInitUnicodeString
0x18000786b  lea     r8, [rsp+290h+DestinationString]
0x180007870  mov     ecx, 1
0x180007875  lea     rdx, [rbp+190h+UnicodeStringOrUnicodeStringBuffer]
0x18000787c  call    cs:__imp_RtlAppendPathElement
0x180007882  test    eax, eax
0x180007884  jns     short loc_180007893
0x180007886  mov     ecx, eax; int
0x180007888  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000788d  mov     ebx, eax
0x18000788f  test    eax, eax
0x180007891  js      short loc_1800078D8
0x180007893  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x18000789a  lea     r8, [rbp+190h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x1800078a1  mov     edx, 38h ; '8'; Type
0x1800078a6  xor     ecx, ecx; Flags
0x1800078a8  xor     ebx, ebx
0x1800078aa  call    cs:__imp_RtlpApplyLengthFunction
0x1800078b0  test    eax, eax
0x1800078b2  jns     short loc_1800078BD
0x1800078b4  mov     ecx, eax; int
0x1800078b6  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800078bb  mov     ebx, eax
0x1800078bd  test    ebx, ebx
0x1800078bf  js      short loc_1800078D8
0x1800078c1  lea     rcx, [rsp+290h+var_260]; this
0x1800078c6  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800078cb  mov     rcx, rax; unsigned __int16 *
0x1800078ce  mov     rdx, rsi; unsigned __int16 **
0x1800078d1  call    ?CscUtil_CreateStringCopyForCom@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopyForCom(ushort const *,ushort * *)
0x1800078d6  mov     ebx, eax
0x1800078d8  mov     rcx, [rbp+190h+Buffer.Buffer]
0x1800078df  xor     edi, edi
0x1800078e1  mov     rax, [rbp+190h+Buffer.StaticBuffer]
0x1800078e8  test    ebx, ebx
0x1800078ea  cmovs   edi, ebx
0x1800078ed  mov     rbx, [rsp+290h+arg_10]
0x1800078f5  test    rcx, rcx
0x1800078f8  jz      short loc_18000791F
0x1800078fa  cmp     rcx, rax
0x1800078fd  jz      short loc_18000791F
0x1800078ff  mov     [rsp+290h+DestinationString.Buffer], rcx
0x180007904  lea     rcx, [rsp+290h+DestinationString]; UnicodeString
0x180007909  mov     qword ptr [rsp+290h+DestinationString.Length], 0
0x180007912  call    cs:__imp_RtlFreeUnicodeString
0x180007918  mov     rax, [rbp+190h+Buffer.StaticBuffer]
0x18000791f  test    rax, rax
0x180007922  jz      short loc_180007929
0x180007924  xor     ecx, ecx
0x180007926  mov     [rax], cx
0x180007929  mov     eax, edi
0x18000792b  mov     rcx, [rbp+190h+Buffer.ReservedForIMalloc]
0x180007932  xor     rcx, rsp; StackCookie
0x180007935  call    __security_check_cookie
0x18000793a  add     rsp, 280h
0x180007941  pop     rdi
0x180007942  pop     rsi
0x180007943  pop     rbp
0x180007944  retn
```
