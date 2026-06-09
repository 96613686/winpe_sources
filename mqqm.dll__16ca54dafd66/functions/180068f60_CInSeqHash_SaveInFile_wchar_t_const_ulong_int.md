# CInSeqHash::SaveInFile(wchar_t const *,ulong,int)

- ea: `0x180068f60`
- end: `0x180069103`
- name: `?SaveInFile@CInSeqHash@@UEAAJPEB_WKH@Z`
- size: `419`
- prototype: `__int64 __fastcall(CInSeqHash *__hidden this, LPCWSTR lpFileName, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000e558`
- `0x180011578`
- `0x1800261c0`
- `0x18002c61c`
- `0x180068ab0`
- `0x180068f60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180068fe8`
- `KERNEL32!GetLastError` at `0x180069076`
- `KERNEL32!GetLastError` at `0x180068fe8`
- `KERNEL32!GetLastError` at `0x180069076`
- `KERNEL32!CreateFileW` at `0x180068fd4`
- `KERNEL32!CreateFileW` at `0x180068fd4`
- `KERNEL32!FlushFileBuffers` at `0x18006906c`
- `KERNEL32!FlushFileBuffers` at `0x18006906c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInSeqHash::SaveInFile(CInSeqHash *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  void *v5; // rbx
  signed int LastError; // eax
  char v7; // di
  signed int v8; // ebx
  signed int v9; // eax
  bool v10; // sf
  HANDLE v12[7]; // [rsp+40h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 428) & 4) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 52), *((_DWORD *)this + 20));
  FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 4u, 0x80000080, 0);
  v5 = FileW;
  v12[0] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    else
      v8 = LastError;
    if ( v8 < 0 )
      LogMsgHR(v8, (wchar_t *)L"xactin", 0x29u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 42), v7);
  }
  else if ( (unsigned int)CInSeqHash::Save(this, FileW) )
  {
    if ( !FlushFileBuffers(v5) )
    {
      v9 = GetLastError();
      v10 = v9 < 0;
      if ( v9 > 0 )
      {
        v9 = (unsigned __int16)v9 | 0x80070000;
        v10 = v9 < 0;
      }
      if ( v10 )
        LogMsgHR(v9, (wchar_t *)L"xactin", 0x5C8u);
    }
    v8 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 42));
    v8 = -1072824281;
    LogMsgHR(-1072824281, (wchar_t *)L"xactin", 0x28u);
  }
  CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180068f60  push    rbx
0x180068f62  push    rbp
0x180068f63  push    rsi
0x180068f64  push    rdi
0x180068f65  sub     rsp, 58h
0x180068f69  mov     rsi, rdx
0x180068f6c  mov     rdi, rcx
0x180068f6f  lea     rbp, WPP_GLOBAL_Control
0x180068f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f7d  cmp     rcx, rbp
0x180068f80  jz      short loc_180068FAD
0x180068f82  test    byte ptr [rcx+1ACh], 4
0x180068f89  jz      short loc_180068FAD
0x180068f8b  mov     edx, 2Ch ; ','
0x180068f90  mov     eax, [rdi+50h]
0x180068f93  mov     [rsp+78h+dwCreationDisposition], eax; char
0x180068f97  mov     r9, rsi
0x180068f9a  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180068fa1  mov     rcx, [rcx+1A0h]; LoggerHandle
0x180068fa8  call    WPP_SF_Sd
0x180068fad  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180068fb6  mov     [rsp+78h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x180068fbe  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x180068fc6  xor     r9d, r9d; lpSecurityAttributes
0x180068fc9  xor     r8d, r8d; dwShareMode
0x180068fcc  mov     edx, 40000000h; dwDesiredAccess
0x180068fd1  mov     rcx, rsi; lpFileName
0x180068fd4  call    cs:__imp_CreateFileW
0x180068fda  mov     rbx, rax
0x180068fdd  mov     [rsp+78h+var_38], rax
0x180068fe2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068fe6  jnz     short loc_18006905A
0x180068fe8  call    cs:__imp_GetLastError
0x180068fee  mov     edi, eax
0x180068ff0  test    eax, eax
0x180068ff2  jg      short loc_180068FF8
0x180068ff4  mov     ebx, eax
0x180068ff6  jmp     short loc_180069001
0x180068ff8  movzx   ebx, di
0x180068ffb  or      ebx, 80070000h
0x180069001  test    ebx, ebx
0x180069003  jns     short loc_180069019
0x180069005  mov     r8d, 29h ; ')'; unsigned __int16
0x18006900b  lea     rdx, aXactin; "xactin"
0x180069012  mov     ecx, ebx; int
0x180069014  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180069019  mov     rcx, cs:WPP_GLOBAL_Control
0x180069020  cmp     rcx, rbp
0x180069023  jz      loc_1800690EE
0x180069029  test    byte ptr [rcx+15Ch], 1
0x180069030  jz      loc_1800690EE
0x180069036  mov     edx, 2Dh ; '-'
0x18006903b  mov     [rsp+78h+dwCreationDisposition], edi; char
0x18006903f  mov     r9, rsi
0x180069042  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180069049  mov     rcx, [rcx+150h]; LoggerHandle
0x180069050  call    WPP_SF_Sd
0x180069055  jmp     loc_1800690EE
0x18006905a  mov     rdx, rbx; void *
0x18006905d  mov     rcx, rdi; this
0x180069060  call    ?Save@CInSeqHash@@AEAAHPEAX@Z; CInSeqHash::Save(void *)
0x180069065  test    eax, eax
0x180069067  jz      short loc_1800690A4
0x180069069  mov     rcx, rbx; hFile
0x18006906c  call    cs:__imp_FlushFileBuffers
0x180069072  test    eax, eax
0x180069074  jnz     short loc_1800690A0
0x180069076  call    cs:__imp_GetLastError
0x18006907c  test    eax, eax
0x18006907e  jle     short loc_18006908A
0x180069080  movzx   eax, ax
0x180069083  or      eax, 80070000h
0x180069088  test    eax, eax
0x18006908a  jns     short loc_1800690A0
0x18006908c  mov     r8d, 5C8h; unsigned __int16
0x180069092  lea     rdx, aXactin; "xactin"
0x180069099  mov     ecx, eax; int
0x18006909b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800690a0  xor     ebx, ebx
0x1800690a2  jmp     short loc_1800690EE
0x1800690a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800690ab  cmp     rcx, rbp
0x1800690ae  jz      short loc_1800690D4
0x1800690b0  test    byte ptr [rcx+15Ch], 1
0x1800690b7  jz      short loc_1800690D4
0x1800690b9  mov     edx, 2Eh ; '.'
0x1800690be  mov     r9, rsi
0x1800690c1  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x1800690c8  mov     rcx, [rcx+150h]; LoggerHandle
0x1800690cf  call    WPP_SF_S
0x1800690d4  mov     r8d, 28h ; '('; unsigned __int16
0x1800690da  lea     rdx, aXactin; "xactin"
0x1800690e1  mov     ebx, 0C00E0027h
0x1800690e6  mov     ecx, ebx; int
0x1800690e8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800690ed  nop
0x1800690ee  lea     rcx, [rsp+78h+var_38]; this
0x1800690f3  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800690f8  mov     eax, ebx
0x1800690fa  add     rsp, 58h
0x1800690fe  pop     rdi
0x1800690ff  pop     rsi
0x180069100  pop     rbp
0x180069101  pop     rbx
0x180069102  retn
```
