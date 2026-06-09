# CInput::Open(char const *,CHmData *)

- ea: `0x180013c00`
- end: `0x180013e4a`
- name: `?Open@CInput@@QEAAHPEBDPEAVCHmData@@@Z`
- size: `586`
- prototype: `__int64 __fastcall(CInput *__hidden this, LPCSTR lpFileName, struct CHmData *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180047d2c`
- `0x180048910`
- `0x180054050`

## callees

- `0x180001728`
- `0x180003fc0`
- `0x180013b94`
- `0x180013c00`
- `0x18002b334`
- `0x18002b418`
- `0x180066cc0`
- `0x180068790`
- `0x180075c5a`

## import_xrefs

- `msvcrt!malloc` at `0x180013d8e`
- `msvcrt!malloc` at `0x180013d8e`
- `KERNEL32!lstrcmpiA` at `0x180013ccb`
- `KERNEL32!lstrcmpiA` at `0x180013ccb`
- `KERNEL32!CreateFileA` at `0x180013de6`
- `KERNEL32!CreateFileA` at `0x180013de6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInput::Open(CInput *this, LPCSTR lpFileName, const CHAR *a3)
{
  CHAR *v5; // rax
  CHAR *v6; // rdi
  const char *CompiledName; // rax
  const char *v8; // r14
  signed int v9; // esi
  unsigned int v10; // edi
  signed int v11; // r8d
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  _BYTE *v17; // rax
  HANDLE v18; // rax
  __int64 v19; // rcx
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-18h] BYREF
  PCSTR pszFirst; // [rsp+A0h] [rbp+40h] BYREF
  LPCSTR lpString1; // [rsp+A8h] [rbp+48h] BYREF

  pszFirst = a3;
  v20 = 0;
  CInput::Close(this);
  pszFirst = 0;
  if ( (unsigned int)IsCompiledHtmlFile(lpFileName, (struct CStr *)&pszFirst) )
  {
    v5 = (CHAR *)operator new(0xB0u);
    v6 = v5;
    lpString1 = v5;
    if ( v5 )
      memset_0(v5, 0, 0xB0u);
    else
      v6 = 0;
    *(_QWORD *)this = v6;
    lpString1 = 0;
    CompiledName = GetCompiledName(pszFirst, (struct CStr *)&lpString1);
    v8 = CompiledName;
    if ( !CompiledName || !*CompiledName )
      goto LABEL_16;
    v9 = 0;
    v10 = 1;
    v11 = g_cHmSlots;
    if ( (int)g_cHmSlots <= 0 )
      goto LABEL_18;
    do
    {
      v12 = *((_QWORD *)g_phmData + v9);
      if ( v12 )
      {
        v13 = lstrcmpiA(lpString1, *(LPCSTR *)(v12 + 136));
        v11 = g_cHmSlots;
        if ( !v13 )
          break;
      }
      ++v9;
    }
    while ( v9 < v11 );
    if ( v9 >= v11 )
    {
LABEL_18:
      if ( !(unsigned int)CFSClient::Initialize(*(CFSClient **)this, pszFirst) )
      {
LABEL_16:
        CInput::Close(this);
        CWStr::~CWStr((CWStr *)&lpString1);
LABEL_17:
        CWStr::~CWStr((CWStr *)&pszFirst);
        CWStr::~CWStr((CWStr *)&v20);
        return 0;
      }
    }
    else
    {
      _mm_lfence();
      v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)g_phmData + v9) + 128LL) + 1080LL);
      v15 = *(_QWORD *)this;
      if ( *(_DWORD *)(v14 + 120) )
      {
        CFSClient::Initialize((CFSClient *)v15, lpString1);
      }
      else
      {
        *(_QWORD *)(v15 + 88) = *(_QWORD *)(v14 + 152);
        *(_DWORD *)(v15 + 168) = 1;
      }
      if ( CFSClient::OpenStream(*(CFSClient **)this, v8, v11) < 0 )
        goto LABEL_16;
    }
    *((_QWORD *)this + 1) = 1;
    CWStr::~CWStr((CWStr *)&lpString1);
  }
  else
  {
    *(_QWORD *)this = 0;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = 0;
    v10 = 1;
    v18 = CreateFileA(lpFileName, 0x80000000, 1u, &SecurityAttributes, 3u, 0x8000000u, 0);
    *((_QWORD *)this + 1) = v18;
    if ( v18 == (HANDLE)-1LL )
    {
      CInput::Close(this);
      goto LABEL_17;
    }
  }
  v17 = malloc(0x4004u);
  *((_QWORD *)this + 2) = v17;
  if ( v17 )
  {
    v17[16385] = 0;
    v19 = *((_QWORD *)this + 2) + 0x4000LL;
    *((_QWORD *)this + 4) = v19;
    *((_QWORD *)this + 3) = v19;
    *((_DWORD *)this + 10) = 0;
  }
  else
  {
    CInput::Close(this);
    v10 = 0;
  }
  CWStr::~CWStr((CWStr *)&pszFirst);
  CWStr::~CWStr((CWStr *)&v20);
  return v10;
}

```

## disassembly

```asm
0x180013c00  mov     [rsp-28h+arg_0], rbx
0x180013c05  mov     [rsp-28h+pszFirst], r8
0x180013c0a  push    rbp
0x180013c0b  push    rsi
0x180013c0c  push    rdi
0x180013c0d  push    r14
0x180013c0f  push    r15
0x180013c11  mov     rbp, rsp
0x180013c14  sub     rsp, 60h
0x180013c18  mov     rsi, rdx
0x180013c1b  mov     rbx, rcx
0x180013c1e  xor     r15d, r15d
0x180013c21  mov     [rbp+var_20], r15
0x180013c25  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180013c2a  mov     [rbp+pszFirst], r15
0x180013c2e  lea     rdx, [rbp+pszFirst]; this
0x180013c32  mov     rcx, rsi; pszStart
0x180013c35  call    ?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z; IsCompiledHtmlFile(char const *,CStr *)
0x180013c3a  test    eax, eax
0x180013c3c  jz      loc_180013DAA
0x180013c42  mov     esi, 0B0h
0x180013c47  mov     ecx, esi; Size
0x180013c49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013c4e  mov     rdi, rax
0x180013c51  mov     [rbp+lpString1], rax
0x180013c55  test    rax, rax
0x180013c58  jz      short loc_180013C69
0x180013c5a  mov     r8d, esi; Size
0x180013c5d  xor     edx, edx; Val
0x180013c5f  mov     rcx, rax; void *
0x180013c62  call    memset_0
0x180013c67  jmp     short loc_180013C6C
0x180013c69  mov     rdi, r15
0x180013c6c  mov     [rbx], rdi
0x180013c6f  mov     [rbp+lpString1], r15
0x180013c73  lea     rdx, [rbp+lpString1]; struct CStr *
0x180013c77  mov     rcx, [rbp+pszFirst]; pszFirst
0x180013c7b  call    ?GetCompiledName@@YAPEBDPEBDPEAVCStr@@@Z; GetCompiledName(char const *,CStr *)
0x180013c80  mov     r14, rax
0x180013c83  test    rax, rax
0x180013c86  jz      loc_180013D3F
0x180013c8c  cmp     [rax], r15b
0x180013c8f  jz      loc_180013D3F
0x180013c95  mov     esi, r15d
0x180013c98  mov     edi, 1
0x180013c9d  mov     r8d, cs:?g_cHmSlots@@3HA; int g_cHmSlots
0x180013ca4  test    r8d, r8d
0x180013ca7  jle     loc_180013D6C
0x180013cad  movsxd  rcx, esi
0x180013cb0  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x180013cb7  mov     rdx, [rax+rcx*8]
0x180013cbb  test    rdx, rdx
0x180013cbe  jz      short loc_180013CDC
0x180013cc0  mov     rdx, [rdx+88h]; lpString2
0x180013cc7  mov     rcx, [rbp+lpString1]; lpString1
0x180013ccb  call    cs:__imp_lstrcmpiA
0x180013cd1  mov     r8d, cs:?g_cHmSlots@@3HA; unsigned int
0x180013cd8  test    eax, eax
0x180013cda  jz      short loc_180013CE3
0x180013cdc  add     esi, edi
0x180013cde  cmp     esi, r8d
0x180013ce1  jl      short loc_180013CAD
0x180013ce3  cmp     esi, r8d
0x180013ce6  jge     loc_180013D6C
0x180013cec  lfence
0x180013cef  movsxd  rcx, esi
0x180013cf2  mov     rax, cs:?g_phmData@@3PEAPEAVCHmData@@EA; CHmData * * g_phmData
0x180013cf9  mov     rcx, [rax+rcx*8]
0x180013cfd  mov     rax, [rcx+80h]
0x180013d04  mov     rax, [rax+438h]
0x180013d0b  mov     rcx, [rbx]; this
0x180013d0e  cmp     [rax+78h], r15d
0x180013d12  jz      short loc_180013D1F
0x180013d14  mov     rdx, [rbp+lpString1]; pszFirst
0x180013d18  call    ?Initialize@CFSClient@@QEAAHPEBD@Z; CFSClient::Initialize(char const *)
0x180013d1d  jmp     short loc_180013D30
0x180013d1f  mov     rax, [rax+98h]
0x180013d26  mov     [rcx+58h], rax
0x180013d2a  mov     [rcx+0A8h], edi
0x180013d30  mov     rdx, r14; char *
0x180013d33  mov     rcx, [rbx]; this
0x180013d36  call    ?OpenStream@CFSClient@@QEAAJPEBDK@Z; CFSClient::OpenStream(char const *,ulong)
0x180013d3b  test    eax, eax
0x180013d3d  jns     short loc_180013D7C
0x180013d3f  mov     rcx, rbx; this
0x180013d42  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180013d47  nop
0x180013d48  lea     rcx, [rbp+lpString1]; this
0x180013d4c  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180013d51  nop
0x180013d52  lea     rcx, [rbp+pszFirst]; this
0x180013d56  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180013d5b  nop
0x180013d5c  lea     rcx, [rbp+var_20]; this
0x180013d60  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180013d65  xor     eax, eax
0x180013d67  jmp     loc_180013E36
0x180013d6c  mov     rdx, [rbp+pszFirst]; pszFirst
0x180013d70  mov     rcx, [rbx]; this
0x180013d73  call    ?Initialize@CFSClient@@QEAAHPEBD@Z; CFSClient::Initialize(char const *)
0x180013d78  test    eax, eax
0x180013d7a  jz      short loc_180013D3F
0x180013d7c  mov     [rbx+8], rdi
0x180013d80  lea     rcx, [rbp+lpString1]; this
0x180013d84  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180013d89  mov     ecx, 4004h; Size
0x180013d8e  call    cs:__imp_malloc
0x180013d94  mov     [rbx+10h], rax
0x180013d98  test    rax, rax
0x180013d9b  jnz     short loc_180013E03
0x180013d9d  mov     rcx, rbx; this
0x180013da0  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180013da5  mov     edi, r15d
0x180013da8  jmp     short loc_180013E21
0x180013daa  mov     [rbx], r15
0x180013dad  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x180013db5  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], r15
0x180013db9  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], r15
0x180013dbd  mov     [rsp+60h+hTemplateFile], r15; hTemplateFile
0x180013dc2  mov     [rsp+60h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180013dca  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180013dd2  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180013dd6  mov     edi, 1
0x180013ddb  mov     r8d, edi; dwShareMode
0x180013dde  mov     edx, 80000000h; dwDesiredAccess
0x180013de3  mov     rcx, rsi; lpFileName
0x180013de6  call    cs:__imp_CreateFileA
0x180013dec  mov     [rbx+8], rax
0x180013df0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013df4  jnz     short loc_180013D89
0x180013df6  mov     rcx, rbx; this
0x180013df9  call    ?Close@CInput@@QEAAXXZ; CInput::Close(void)
0x180013dfe  jmp     loc_180013D52
0x180013e03  mov     [rax+4001h], r15b
0x180013e0a  mov     rcx, [rbx+10h]
0x180013e0e  add     rcx, 4000h
0x180013e15  mov     [rbx+20h], rcx
0x180013e19  mov     [rbx+18h], rcx
0x180013e1d  mov     [rbx+28h], r15d
0x180013e21  lea     rcx, [rbp+pszFirst]; this
0x180013e25  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180013e2a  nop
0x180013e2b  lea     rcx, [rbp+var_20]; this
0x180013e2f  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180013e34  mov     eax, edi
0x180013e36  mov     rbx, [rsp+60h+arg_0]
0x180013e3e  add     rsp, 60h
0x180013e42  pop     r15
0x180013e44  pop     r14
0x180013e46  pop     rdi
0x180013e47  pop     rsi
0x180013e48  pop     rbp
0x180013e49  retn
```
