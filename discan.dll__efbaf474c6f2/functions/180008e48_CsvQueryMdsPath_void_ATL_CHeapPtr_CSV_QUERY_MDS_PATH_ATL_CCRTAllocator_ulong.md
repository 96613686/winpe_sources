# CsvQueryMdsPath(void *,ATL::CHeapPtr<_CSV_QUERY_MDS_PATH,ATL::CCRTAllocator> &,ulong &)

- ea: `0x180008e48`
- end: `0x180009082`
- name: `?CsvQueryMdsPath@@YAJPEAXAEAV?$CHeapPtr@U_CSV_QUERY_MDS_PATH@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z`
- size: `570`
- prototype: `__int64 __fastcall(HANDLE Handle, PVOID *, ULONG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001ec84`

## callees

- `0x180002dec`
- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x180008e48`
- `0x180037620`

## import_xrefs

- `msvcrt!realloc` at `0x180008fec`
- `msvcrt!realloc` at `0x180008fec`
- `msvcrt!malloc` at `0x180008f5b`
- `msvcrt!malloc` at `0x180008f5b`
- `ntdll!NtFsControlFile` at `0x180008fa8`
- `ntdll!NtFsControlFile` at `0x180008fa8`
- `ntdll!NtWaitForSingleObject` at `0x180008fbf`
- `ntdll!NtWaitForSingleObject` at `0x180008fbf`

## string_xrefs

- `0x180008e8e`: `CsvQueryMdsPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CsvQueryMdsPath(HANDLE Handle, PVOID *a2, ULONG *a3)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v8; // rdx
  USHORT v9; // dx
  USHORT v10; // ax
  ULONG OutputBufferLength; // ebx
  void *v12; // rax
  NTSTATUS Status; // ebx
  void *v14; // rax
  int v15; // ebx
  size_t Size[2]; // [rsp+50h] [rbp-19h] BYREF
  const char *v18; // [rsp+60h] [rbp-9h] BYREF
  int v19; // [rsp+68h] [rbp-1h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  __int128 InputBuffer; // [rsp+80h] [rbp+17h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v19 = 0;
  v18 = "CsvQueryMdsPath";
  v8 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v8 + 16) = "CsvQueryMdsPath";
  v9 = ++*(_WORD *)(v8 + 8);
  v10 = Length;
  if ( v9 < Length )
  {
    v10 = v9;
    Length = v9;
  }
  LOWORD(Size[0]) = v10;
  HIDWORD(Size[0]) = 0;
  Size[1] = (size_t)off_180047060;
  WORD1(Size[0]) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CsvQueryMdsPath");
  }
  OutputBufferLength = *a3;
  InputBuffer = 0;
  LODWORD(InputBuffer) = 8;
  IoStatusBlock = 0;
  if ( OutputBufferLength )
    goto LABEL_11;
  OutputBufferLength = 272;
  Size[0] = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(Size) < 0 || (v12 = malloc(Size[0]), (*a2 = v12) == 0) )
  {
LABEL_25:
    v15 = -2147024882;
    v19 = -2147024882;
    goto LABEL_26;
  }
  while ( 1 )
  {
    *a3 = OutputBufferLength;
LABEL_11:
    Status = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x902D4u, &InputBuffer, 0x10u, *a2, OutputBufferLength);
    if ( Status == 259 )
    {
      NtWaitForSingleObject(Handle, 0, 0);
      Status = IoStatusBlock.Status;
    }
    if ( Status != -1073741789 )
      break;
    OutputBufferLength = 2 * *a3;
LABEL_17:
    v14 = realloc(*a2, OutputBufferLength);
    if ( !v14 )
      goto LABEL_25;
    *a2 = v14;
  }
  if ( Status == -2147483643 )
  {
    OutputBufferLength = *((_DWORD *)*a2 + 2) + 12;
    goto LABEL_17;
  }
  v15 = Status | 0x10000000;
  v19 = v15;
  if ( v15 >= 0 )
  {
    v15 = 0;
    *a3 = IoStatusBlock.Information;
    v19 = 0;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      59,
      &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
      (unsigned int)v15);
  }
LABEL_26:
  CHResultImp::~CHResultImp((CHResultImp *)&v18);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180008e48  mov     [rsp-8+arg_18], rbx
0x180008e4d  push    rbp
0x180008e4e  push    rsi
0x180008e4f  push    rdi
0x180008e50  push    r13
0x180008e52  push    r14
0x180008e54  lea     rbp, [rsp-37h]
0x180008e59  sub     rsp, 0A0h
0x180008e60  mov     rax, cs:__security_cookie
0x180008e67  xor     rax, rsp
0x180008e6a  mov     [rbp+57h+var_30], rax
0x180008e6e  mov     rax, gs:58h
0x180008e77  mov     rsi, rdx
0x180008e7a  mov     r9d, cs:_tls_index
0x180008e81  mov     r14, rcx
0x180008e84  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180008e8b  mov     rdi, r8
0x180008e8e  lea     r8, aCsvquerymdspat; "CsvQueryMdsPath"
0x180008e95  mov     [rbp+57h+var_58], 0
0x180008e9c  mov     [rbp+57h+var_60], r8
0x180008ea0  mov     rdx, [rax+r9*8]
0x180008ea4  mov     eax, 10h
0x180008ea9  mov     [rax+rdx], r8
0x180008ead  mov     eax, 8
0x180008eb2  inc     word ptr [rax+rdx]
0x180008eb6  movzx   edx, word ptr [rax+rdx]
0x180008eba  movzx   eax, cx
0x180008ebd  cmp     dx, cx
0x180008ec0  cmovb   ax, dx
0x180008ec4  cmovb   cx, dx
0x180008ec8  mov     word ptr [rbp+57h+Size], ax
0x180008ecc  xor     eax, eax
0x180008ece  mov     dword ptr [rbp+57h+Size+4], eax
0x180008ed1  mov     rax, cs:off_180047060; "                                       "...
0x180008ed8  mov     [rbp+57h+var_68], rax
0x180008edc  mov     word ptr [rbp+57h+Size+2], cx
0x180008ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee7  lea     r13, WPP_GLOBAL_Control
0x180008eee  cmp     rcx, r13
0x180008ef1  jz      short loc_180008F16
0x180008ef3  test    byte ptr [rcx+1Ch], 1
0x180008ef7  jz      short loc_180008F16
0x180008ef9  cmp     byte ptr [rcx+19h], 5
0x180008efd  jb      short loc_180008F16
0x180008eff  mov     rcx, [rcx+10h]; LoggerHandle
0x180008f03  lea     r9, [rbp+57h+Size]
0x180008f07  mov     edx, 0Dh
0x180008f0c  mov     [rsp+0C0h+IoStatusBlock], r8; __int64
0x180008f11  call    WPP_SF_aZs
0x180008f16  mov     ebx, [rdi]
0x180008f18  xorps   xmm1, xmm1
0x180008f1b  xorps   xmm0, xmm0
0x180008f1e  movups  [rbp+57h+var_40], xmm1
0x180008f22  mov     dword ptr [rbp+57h+var_40], 8
0x180008f29  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180008f2d  test    ebx, ebx
0x180008f2f  jnz     short loc_180008F6F
0x180008f31  mov     ebx, 110h
0x180008f36  mov     [rbp+57h+Size], 0
0x180008f3e  mov     edx, ebx
0x180008f40  lea     rcx, [rbp+57h+Size]
0x180008f44  mov     r8d, 10h
0x180008f4a  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x180008f4f  test    eax, eax
0x180008f51  js      loc_18000904C
0x180008f57  mov     rcx, [rbp+57h+Size]; Size
0x180008f5b  call    cs:__imp_malloc
0x180008f61  mov     [rsi], rax
0x180008f64  test    rax, rax
0x180008f67  jz      loc_18000904C
0x180008f6d  mov     [rdi], ebx
0x180008f6f  mov     rax, [rsi]
0x180008f72  xor     r9d, r9d; ApcContext
0x180008f75  mov     [rsp+0C0h+OutputBufferLength], ebx; OutputBufferLength
0x180008f79  xor     r8d, r8d; ApcRoutine
0x180008f7c  mov     [rsp+0C0h+OutputBuffer], rax; OutputBuffer
0x180008f81  xor     edx, edx; Event
0x180008f83  mov     [rsp+0C0h+InputBufferLength], 10h; InputBufferLength
0x180008f8b  lea     rax, [rbp+57h+var_40]
0x180008f8f  mov     [rsp+0C0h+InputBuffer], rax; InputBuffer
0x180008f94  mov     rcx, r14; FileHandle
0x180008f97  lea     rax, [rbp+57h+var_50]
0x180008f9b  mov     [rsp+0C0h+FsControlCode], 902D4h; FsControlCode
0x180008fa3  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x180008fa8  call    cs:__imp_NtFsControlFile
0x180008fae  mov     ebx, eax
0x180008fb0  cmp     eax, 103h
0x180008fb5  jnz     short loc_180008FC8
0x180008fb7  xor     r8d, r8d; Timeout
0x180008fba  xor     edx, edx; Alertable
0x180008fbc  mov     rcx, r14; Handle
0x180008fbf  call    cs:__imp_NtWaitForSingleObject
0x180008fc5  mov     ebx, dword ptr [rbp+57h+var_50]
0x180008fc8  cmp     ebx, 0C0000023h
0x180008fce  jz      short loc_180008FE3
0x180008fd0  cmp     ebx, 80000005h
0x180008fd6  jnz     short loc_180008FFF
0x180008fd8  mov     rax, [rsi]
0x180008fdb  mov     ebx, [rax+8]
0x180008fde  add     ebx, 0Ch
0x180008fe1  jmp     short loc_180008FE7
0x180008fe3  mov     ebx, [rdi]
0x180008fe5  add     ebx, ebx
0x180008fe7  mov     rcx, [rsi]; Block
0x180008fea  mov     edx, ebx; Size
0x180008fec  call    cs:__imp_realloc
0x180008ff2  test    rax, rax
0x180008ff5  jz      short loc_18000904C
0x180008ff7  mov     [rsi], rax
0x180008ffa  jmp     loc_180008F6D
0x180008fff  or      ebx, 10000000h
0x180009005  mov     [rbp+57h+var_58], ebx
0x180009008  jge     short loc_18000903C
0x18000900a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009011  cmp     rcx, r13
0x180009014  jz      short loc_180009054
0x180009016  test    byte ptr [rcx+1Ch], 1
0x18000901a  jz      short loc_180009054
0x18000901c  cmp     byte ptr [rcx+19h], 2
0x180009020  jb      short loc_180009054
0x180009022  mov     rcx, [rcx+10h]
0x180009026  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000902d  mov     edx, 3Bh ; ';'
0x180009032  mov     r9d, ebx
0x180009035  call    WPP_SF_d
0x18000903a  jmp     short loc_180009054
0x18000903c  mov     eax, dword ptr [rbp+57h+var_50.Information]
0x18000903f  xor     ebx, ebx
0x180009041  mov     [rdi], eax
0x180009043  mov     [rbp+57h+var_58], 0
0x18000904a  jmp     short loc_180009054
0x18000904c  mov     ebx, 8007000Eh
0x180009051  mov     [rbp+57h+var_58], ebx
0x180009054  lea     rcx, [rbp+57h+var_60]; this
0x180009058  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000905d  mov     eax, ebx
0x18000905f  mov     rcx, [rbp+57h+var_30]
0x180009063  xor     rcx, rsp; StackCookie
0x180009066  call    __security_check_cookie
0x18000906b  mov     rbx, [rsp+0C0h+arg_18]
0x180009073  add     rsp, 0A0h
0x18000907a  pop     r14
0x18000907c  pop     r13
0x18000907e  pop     rdi
0x18000907f  pop     rsi
0x180009080  pop     rbp
0x180009081  retn
```
