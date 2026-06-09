# CNtfsVolume::_IsFileOnVolume(_UNICODE_STRING *,int *)

- ea: `0x180061b48`
- end: `0x180061d33`
- name: `?_IsFileOnVolume@CNtfsVolume@@AEAAJPEAU_UNICODE_STRING@@PEAH@Z`
- size: `491`
- prototype: `__int64 __fastcall(const wchar_t **this, struct _UNICODE_STRING *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18003c0a0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180016ea8`
- `0x180061b48`
- `0x180067afe`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180061c7d`
- `msvcrt!_wcsnicmp` at `0x180061c7d`
- `ntdll!RtlpEnsureBufferSize` at `0x180061bdf`
- `ntdll!RtlpEnsureBufferSize` at `0x180061bdf`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180061c41`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180061c41`
- `ntdll!RtlFreeUnicodeString` at `0x180061cd0`
- `ntdll!RtlFreeUnicodeString` at `0x180061cd0`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_IsFileOnVolume(const wchar_t **this, struct _UNICODE_STRING *a2, int *a3)
{
  SIZE_T v6; // r8
  unsigned __int64 v7; // rdx
  __int16 v8; // ax
  UCHAR *StaticBuffer; // rcx
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v13; // [rsp+24h] [rbp-DCh]
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-A8h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+68h] [rbp-98h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CNtfsVolume::_IsFileOnVolume", 1821, 1);
  memset_0(&Path.ByteBuffer.ReservedForIMalloc, 0, 0x208u);
  memset(&Path, 0, 56);
  *a3 = 0;
  v6 = a2->Length + 2LL;
  if ( v6 > 0xFFFE || RtlpEnsureBufferSize(0, &Path.ByteBuffer, v6) < 0 )
  {
    v8 = 1833;
  }
  else
  {
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)Path.String.Length >> 1)], a2->Buffer, a2->Length);
    v7 = (unsigned __int16)(a2->Length + Path.String.Length);
    Path.String.MaximumLength = v7 + 2;
    Path.String.Length = v7;
    Path.String.Buffer[v7 >> 1] = 0;
    if ( RtlNtPathNameToDosPathName(0, &Path, 0, 0) >= 0 )
    {
      if ( (int)SxGetUniqueVolumeForPath(Path.String.Buffer, (LPWSTR)&Path.ByteBuffer.ReservedForIMalloc, 0x104u) >= 0 )
      {
        if ( !_wcsnicmp((const wchar_t *)&Path.ByteBuffer.ReservedForIMalloc, this[6], *((unsigned int *)this + 14)) )
        {
          *a3 = 1;
          v12 = 0;
          goto LABEL_12;
        }
        v8 = 1852;
      }
      else
      {
        v8 = 1847;
      }
    }
    else
    {
      v8 = 1839;
    }
  }
  v13 = v8;
  v12 = 1;
LABEL_12:
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
  if ( Path.ByteBuffer.Buffer )
  {
    if ( Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
    {
      *(_QWORD *)&UnicodeString.Length = 0;
      UnicodeString.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
      RtlFreeUnicodeString(&UnicodeString);
      StaticBuffer = Path.ByteBuffer.StaticBuffer;
    }
    Path.ByteBuffer.Buffer = StaticBuffer;
    Path.ByteBuffer.Size = Path.ByteBuffer.StaticSize;
  }
  Path.String.Buffer = (PWSTR)StaticBuffer;
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  Path.String.Length = 0;
  Path.String.MaximumLength = Path.ByteBuffer.StaticSize;
  v10 = v12;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v10;
}

```

## disassembly

```asm
0x180061b48  push    rbp
0x180061b4a  push    rbx
0x180061b4b  push    rsi
0x180061b4c  push    rdi
0x180061b4d  push    r15
0x180061b4f  lea     rbp, [rsp-1C0h]
0x180061b57  sub     rsp, 2C0h
0x180061b5e  mov     rax, cs:__security_cookie
0x180061b65  xor     rax, rsp
0x180061b68  mov     [rbp+1E0h+var_30], rax
0x180061b6f  mov     rdi, r8
0x180061b72  mov     rsi, rdx
0x180061b75  mov     rbx, rcx
0x180061b78  mov     r15d, 1
0x180061b7e  mov     r9d, r15d; unsigned __int16
0x180061b81  mov     r8d, 71Dh; unsigned __int16
0x180061b87  lea     rdx, aCntfsvolumeIsf; "CNtfsVolume::_IsFileOnVolume"
0x180061b8e  lea     rcx, [rsp+2E0h+var_2C0]; this
0x180061b93  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180061b98  nop
0x180061b99  xor     edx, edx; Val
0x180061b9b  mov     r8d, 208h; Size
0x180061ba1  lea     rcx, [rbp+1E0h+Path.ByteBuffer.ReservedForIMalloc]; void *
0x180061ba5  call    memset_0
0x180061baa  xorps   xmm0, xmm0
0x180061bad  xor     eax, eax
0x180061baf  movups  xmmword ptr [rsp+2E0h+Path.String.Length], xmm0
0x180061bb4  movups  xmmword ptr [rsp+2E0h+Path.ByteBuffer.Buffer], xmm0
0x180061bb9  movups  xmmword ptr [rbp+1E0h+Path.ByteBuffer.Size], xmm0
0x180061bbd  mov     [rbp+1E0h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x180061bc1  mov     [rdi], eax
0x180061bc3  movzx   r8d, word ptr [rsi]
0x180061bc7  add     r8, 2; RequiredSize
0x180061bcb  cmp     r8, 0FFFEh
0x180061bd2  ja      loc_180061C9B
0x180061bd8  lea     rdx, [rsp+2E0h+Path.ByteBuffer]; Buffer
0x180061bdd  xor     ecx, ecx; Flags
0x180061bdf  call    cs:__imp_RtlpEnsureBufferSize
0x180061be5  test    eax, eax
0x180061be7  js      loc_180061C9B
0x180061bed  mov     rcx, [rsp+2E0h+Path.ByteBuffer.Buffer]
0x180061bf2  mov     [rsp+2E0h+Path.String.Buffer], rcx
0x180061bf7  movzx   r8d, word ptr [rsi]; Size
0x180061bfb  movzx   eax, [rsp+2E0h+Path.String.Length]
0x180061c00  shr     rax, 1
0x180061c03  lea     rcx, [rcx+rax*2]; void *
0x180061c07  mov     rdx, [rsi+8]; Src
0x180061c0b  call    memmove_0
0x180061c10  movzx   eax, [rsp+2E0h+Path.String.Length]
0x180061c15  add     ax, [rsi]
0x180061c18  movzx   edx, ax
0x180061c1b  lea     eax, [rdx+2]
0x180061c1e  mov     [rsp+2E0h+Path.String.MaximumLength], ax
0x180061c23  mov     [rsp+2E0h+Path.String.Length], dx
0x180061c28  shr     rdx, 1
0x180061c2b  xor     ecx, ecx; Flags
0x180061c2d  mov     rax, [rsp+2E0h+Path.String.Buffer]
0x180061c32  mov     [rax+rdx*2], cx
0x180061c36  xor     r9d, r9d; Unknown
0x180061c39  xor     r8d, r8d; PathType
0x180061c3c  lea     rdx, [rsp+2E0h+Path]; Path
0x180061c41  call    cs:__imp_RtlNtPathNameToDosPathName
0x180061c47  test    eax, eax
0x180061c49  jns     short loc_180061C52
0x180061c4b  mov     eax, 72Fh
0x180061c50  jmp     short loc_180061CA0
0x180061c52  mov     r8d, 104h; unsigned int
0x180061c58  lea     rdx, [rbp+1E0h+Path.ByteBuffer.ReservedForIMalloc]; lpszVolumeName
0x180061c5c  mov     rcx, [rsp+2E0h+Path.String.Buffer]; Src
0x180061c61  call    ?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z; SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)
0x180061c66  test    eax, eax
0x180061c68  jns     short loc_180061C71
0x180061c6a  mov     eax, 737h
0x180061c6f  jmp     short loc_180061CA0
0x180061c71  mov     r8d, [rbx+38h]; MaxCount
0x180061c75  mov     rdx, [rbx+30h]; String2
0x180061c79  lea     rcx, [rbp+1E0h+Path.ByteBuffer.ReservedForIMalloc]; String1
0x180061c7d  call    cs:__imp__wcsnicmp
0x180061c83  test    eax, eax
0x180061c85  jz      short loc_180061C8E
0x180061c87  mov     eax, 73Ch
0x180061c8c  jmp     short loc_180061CA0
0x180061c8e  mov     [rdi], r15d
0x180061c91  mov     [rsp+2E0h+var_2C0], 0
0x180061c99  jmp     short loc_180061CAA
0x180061c9b  mov     eax, 729h
0x180061ca0  mov     [rsp+2E0h+var_2BC], ax
0x180061ca5  mov     [rsp+2E0h+var_2C0], r15d
0x180061caa  mov     rax, [rsp+2E0h+Path.ByteBuffer.Buffer]
0x180061caf  mov     rcx, [rbp+1E0h+Path.ByteBuffer.StaticBuffer]
0x180061cb3  test    rax, rax
0x180061cb6  jz      short loc_180061CE7
0x180061cb8  cmp     rax, rcx
0x180061cbb  jz      short loc_180061CDA
0x180061cbd  mov     qword ptr [rsp+2E0h+UnicodeString.Length], 0
0x180061cc6  mov     [rsp+2E0h+UnicodeString.Buffer], rax
0x180061ccb  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x180061cd0  call    cs:__imp_RtlFreeUnicodeString
0x180061cd6  mov     rcx, [rbp+1E0h+Path.ByteBuffer.StaticBuffer]
0x180061cda  mov     [rsp+2E0h+Path.ByteBuffer.Buffer], rcx
0x180061cdf  mov     rax, [rbp+1E0h+Path.ByteBuffer.StaticSize]
0x180061ce3  mov     [rbp+1E0h+Path.ByteBuffer.Size], rax
0x180061ce7  mov     [rsp+2E0h+Path.String.Buffer], rcx
0x180061cec  test    rcx, rcx
0x180061cef  jz      short loc_180061CF6
0x180061cf1  xor     eax, eax
0x180061cf3  mov     [rcx], ax
0x180061cf6  xor     eax, eax
0x180061cf8  mov     [rsp+2E0h+Path.String.Length], ax
0x180061cfd  movzx   eax, word ptr [rbp+1E0h+Path.ByteBuffer.StaticSize]
0x180061d01  mov     [rsp+2E0h+Path.String.MaximumLength], ax
0x180061d06  mov     ebx, [rsp+2E0h+var_2C0]
0x180061d0a  lea     rcx, [rsp+2E0h+var_2C0]; this
0x180061d0f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180061d14  mov     eax, ebx
0x180061d16  mov     rcx, [rbp+1E0h+var_30]
0x180061d1d  xor     rcx, rsp; StackCookie
0x180061d20  call    __security_check_cookie
0x180061d25  add     rsp, 2C0h
0x180061d2c  pop     r15
0x180061d2e  pop     rdi
0x180061d2f  pop     rsi
0x180061d30  pop     rbx
0x180061d31  pop     rbp
0x180061d32  retn
```
