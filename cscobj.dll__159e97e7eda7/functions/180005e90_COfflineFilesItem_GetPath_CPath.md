# COfflineFilesItem::_GetPath(CPath *)

- ea: `0x180005e90`
- end: `0x180006008`
- name: `?_GetPath@COfflineFilesItem@@IEAAJPEAVCPath@@@Z`
- size: `376`
- prototype: `__int64 __fastcall(COfflineFilesItem *__hidden this, struct CPath *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010400`
- `0x180010834`
- `0x180010934`
- `0x180010ae8`
- `0x180010c64`

## callees

- `0x180005e90`
- `0x1800102a8`
- `0x18002ac30`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180005f03`
- `ntdll!RtlpEnsureBufferSize` at `0x180005f03`
- `ntdll!RtlAppendPathElement` at `0x180005f8c`
- `ntdll!RtlAppendPathElement` at `0x180005f8c`
- `ntdll!RtlpApplyLengthFunction` at `0x180005fa9`
- `ntdll!RtlpApplyLengthFunction` at `0x180005fa9`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180005f96`
- `ntdll!RtlInitUnicodeString` at `0x180005ec9`
- `ntdll!RtlInitUnicodeString` at `0x180005f79`
- `ntdll!RtlInitUnicodeString` at `0x180005ec9`
- `ntdll!RtlInitUnicodeString` at `0x180005f79`

## pseudocode

```c
__int64 __fastcall COfflineFilesItem::_GetPath(COfflineFilesItem *this, struct CPath *a2)
{
  const WCHAR *v4; // rdx
  __int64 Length; // r8
  _WORD *v6; // rdi
  __int64 v7; // rcx
  PWSTR Buffer; // rdx
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  int appended; // eax
  unsigned int v13; // ebx
  NTSTATUS v14; // eax
  __int64 result; // rax
  int v16; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  v4 = (const WCHAR *)*((_QWORD *)this + 70);
  if ( v4 == *((const WCHAR **)this + 71) )
    v4 = (const WCHAR *)*((_QWORD *)this + 69);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v4);
  Length = DestinationString.Length;
  v6 = (_WORD *)((char *)a2 + 520);
  *((_WORD *)a2 + 260) = 0;
  if ( (unsigned __int64)(Length + 2) > 0xFFFE )
  {
    v16 = -1073741562;
    goto LABEL_12;
  }
  if ( a2 != (struct CPath *)-536LL && (unsigned __int64)(Length + 2) <= *((_QWORD *)a2 + 69) )
    goto LABEL_7;
  if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)((char *)a2 + 536), Length + 2) < 0 )
  {
    v16 = -1073741801;
LABEL_12:
    result = ResultFromNtStatus(v16);
    if ( (int)result < 0 )
      return result;
    goto LABEL_8;
  }
  LOWORD(Length) = DestinationString.Length;
LABEL_7:
  v7 = *((_QWORD *)a2 + 67);
  Buffer = DestinationString.Buffer;
  v9 = (unsigned __int64)(unsigned __int16)*v6 >> 1;
  *((_QWORD *)a2 + 66) = v7;
  memmove_0((void *)(v7 + 2 * v9), Buffer, (unsigned __int16)Length);
  v10 = *((_QWORD *)a2 + 66);
  v11 = (unsigned __int16)(*v6 + DestinationString.Length);
  *v6 = v11;
  *((_WORD *)a2 + 261) = v11 + 2;
  *(_WORD *)(v10 + 2 * (v11 >> 1)) = 0;
LABEL_8:
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 407);
  appended = RtlAppendPathElement(1, (char *)a2 + 520, &DestinationString);
  if ( appended >= 0 || (result = ResultFromNtStatus(appended), (int)result >= 0) )
  {
    v13 = 0;
    v14 = RtlpApplyLengthFunction(0, 0x38u, (char *)a2 + 520, RtlGetLengthWithoutTrailingPathSeperators);
    if ( v14 < 0 )
      return (unsigned int)ResultFromNtStatus(v14);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x180005e90  mov     [rsp+arg_0], rbx
0x180005e95  mov     [rsp+arg_8], rsi
0x180005e9a  push    rdi
0x180005e9b  sub     rsp, 30h
0x180005e9f  mov     rsi, rdx
0x180005ea2  mov     rbx, rcx
0x180005ea5  mov     rdx, [rcx+230h]
0x180005eac  cmp     rdx, [rcx+238h]
0x180005eb3  jnz     short loc_180005EBC
0x180005eb5  mov     rdx, [rcx+228h]; SourceString
0x180005ebc  xorps   xmm0, xmm0
0x180005ebf  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180005ec4  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180005ec9  call    cs:__imp_RtlInitUnicodeString
0x180005ecf  movzx   r8d, [rsp+38h+DestinationString.Length]
0x180005ed5  lea     rdi, [rsi+208h]
0x180005edc  xor     eax, eax
0x180005ede  mov     [rdi], ax
0x180005ee1  lea     rax, [r8+2]
0x180005ee5  cmp     rax, 0FFFEh
0x180005eeb  ja      loc_180005FEF
0x180005ef1  lea     rdx, [rdi+10h]; Buffer
0x180005ef5  test    rdx, rdx
0x180005ef8  jnz     loc_180005FD0
0x180005efe  mov     r8, rax; RequiredSize
0x180005f01  xor     ecx, ecx; Flags
0x180005f03  call    cs:__imp_RtlpEnsureBufferSize
0x180005f09  test    eax, eax
0x180005f0b  js      loc_180005FF6
0x180005f11  movzx   r8d, [rsp+38h+DestinationString.Length]
0x180005f17  mov     rcx, [rsi+218h]
0x180005f1e  movzx   eax, word ptr [rdi]
0x180005f21  mov     rdx, [rsp+38h+DestinationString.Buffer]; Src
0x180005f26  shr     rax, 1
0x180005f29  mov     [rsi+210h], rcx
0x180005f30  movzx   r8d, r8w; Size
0x180005f34  lea     rcx, [rcx+rax*2]; void *
0x180005f38  call    memmove_0
0x180005f3d  movzx   eax, [rsp+38h+DestinationString.Length]
0x180005f42  add     ax, [rdi]
0x180005f45  mov     rcx, [rsi+210h]
0x180005f4c  movzx   edx, ax
0x180005f4f  mov     [rdi], dx
0x180005f52  lea     eax, [rdx+2]
0x180005f55  shr     rdx, 1
0x180005f58  mov     [rsi+20Ah], ax
0x180005f5f  xor     eax, eax
0x180005f61  mov     [rcx+rdx*2], ax
0x180005f65  xorps   xmm0, xmm0
0x180005f68  lea     rdx, [rbx+32Eh]; SourceString
0x180005f6f  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180005f74  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180005f79  call    cs:__imp_RtlInitUnicodeString
0x180005f7f  lea     r8, [rsp+38h+DestinationString]
0x180005f84  mov     rdx, rdi
0x180005f87  mov     ecx, 1
0x180005f8c  call    cs:__imp_RtlAppendPathElement
0x180005f92  test    eax, eax
0x180005f94  js      short loc_180005FE2
0x180005f96  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180005f9d  mov     r8, rdi; UnicodeStringOrUnicodeStringBuffer
0x180005fa0  mov     edx, 38h ; '8'; Type
0x180005fa5  xor     ecx, ecx; Flags
0x180005fa7  xor     ebx, ebx
0x180005fa9  call    cs:__imp_RtlpApplyLengthFunction
0x180005faf  test    eax, eax
0x180005fb1  js      short loc_180005FFD
0x180005fb3  mov     eax, ebx
0x180005fb5  jmp     short loc_180005FC0
0x180005fb7  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180005fbc  test    eax, eax
0x180005fbe  jns     short loc_180005F65
0x180005fc0  mov     rbx, [rsp+38h+arg_0]
0x180005fc5  mov     rsi, [rsp+38h+arg_8]
0x180005fca  add     rsp, 30h
0x180005fce  pop     rdi
0x180005fcf  retn
0x180005fd0  cmp     rax, [rsi+228h]
0x180005fd7  jbe     loc_180005F17
0x180005fdd  jmp     loc_180005EFE
0x180005fe2  mov     ecx, eax; int
0x180005fe4  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180005fe9  test    eax, eax
0x180005feb  js      short loc_180005FC0
0x180005fed  jmp     short loc_180005F96
0x180005fef  mov     ecx, 0C0000106h; int
0x180005ff4  jmp     short loc_180005FB7
0x180005ff6  mov     ecx, 0C0000017h
0x180005ffb  jmp     short loc_180005FB7
0x180005ffd  mov     ecx, eax; int
0x180005fff  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180006004  mov     ebx, eax
0x180006006  jmp     short loc_180005FB3
```
