# PerfDiagOutput::CSqmPIIFilter::SqmGetFilenameFromPath(ushort const *)

- ea: `0x18004e378`
- end: `0x18004e46e`
- name: `?SqmGetFilenameFromPath@CSqmPIIFilter@PerfDiagOutput@@QEAAPEBGPEBG@Z`
- size: `246`
- prototype: `const unsigned __int16 *__fastcall(PerfDiagOutput::CSqmPIIFilter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18004e2cc`

## callees

- `0x18003b120`
- `0x18004a894`
- `0x18004e378`
- `0x1800b4890`
- `0x1800cf032`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004e3d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004e3d2`
- `SHELL32!SHGetFolderPathW` at `0x18004e40d`
- `SHELL32!SHGetFolderPathW` at `0x18004e40d`

## pseudocode

```c
wchar_t *__fastcall PerfDiagOutput::CSqmPIIFilter::SqmGetFilenameFromPath(
        PerfDiagOutput::CSqmPIIFilter *this,
        wchar_t *a2)
{
  PerfDiagOutput::CSqmPIIFilter *v4; // rcx
  const unsigned __int16 *v5; // rdx
  PerfDiagOutput::CSqmPIIFilter *v7; // rcx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !a2 || !*a2 )
    return a2;
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u)
    && (PerfDiagOutput::CSqmPIIFilter::StartsWith(v4, a2, Buffer)
     || SHGetFolderPathW(0, 38, 0, 0, Buffer) >= 0
     && (PerfDiagOutput::CSqmPIIFilter::StartsWith(v7, a2, Buffer)
      || *((_BYTE *)this + 40) && PerfDiagOutput::CIncludedBinariesExtensions::IsIncludedBinary(this, a2))) )
  {
    return (wchar_t *)PerfDiagOutput::GetFilenameFromPath(a2, v5);
  }
  else
  {
    return L"<PII>";
  }
}

```

## disassembly

```asm
0x18004e378  mov     [rsp+arg_10], rbx
0x18004e37d  mov     [rsp+arg_18], rsi
0x18004e382  push    rdi
0x18004e383  sub     rsp, 250h
0x18004e38a  mov     rax, cs:__security_cookie
0x18004e391  xor     rax, rsp
0x18004e394  mov     [rsp+258h+var_18], rax
0x18004e39c  xor     esi, esi
0x18004e39e  mov     rbx, rdx
0x18004e3a1  mov     rdi, rcx
0x18004e3a4  test    rdx, rdx
0x18004e3a7  jz      loc_18004E446
0x18004e3ad  cmp     [rdx], si
0x18004e3b0  jz      loc_18004E446
0x18004e3b6  xor     edx, edx; Val
0x18004e3b8  lea     rcx, [rsp+258h+Buffer]; void *
0x18004e3bd  mov     r8d, 208h; Size
0x18004e3c3  call    memset_0
0x18004e3c8  mov     edx, 104h; uSize
0x18004e3cd  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18004e3d2  call    cs:__imp_GetSystemWindowsDirectoryW
0x18004e3d8  test    eax, eax
0x18004e3da  jz      short loc_18004E43D
0x18004e3dc  lea     r8, [rsp+258h+Buffer]; unsigned __int16 *
0x18004e3e1  mov     rdx, rbx; unsigned __int16 *
0x18004e3e4  call    ?StartsWith@CSqmPIIFilter@PerfDiagOutput@@AEAA_NPEBG0@Z; PerfDiagOutput::CSqmPIIFilter::StartsWith(ushort const *,ushort const *)
0x18004e3e9  test    al, al
0x18004e3eb  jz      short loc_18004E3F7
0x18004e3ed  mov     rcx, rbx; Str
0x18004e3f0  call    ?GetFilenameFromPath@PerfDiagOutput@@YAPEBGPEBG@Z; PerfDiagOutput::GetFilenameFromPath(ushort const *)
0x18004e3f5  jmp     short loc_18004E449
0x18004e3f7  xor     r9d, r9d; dwFlags
0x18004e3fa  lea     rax, [rsp+258h+Buffer]
0x18004e3ff  xor     r8d, r8d; hToken
0x18004e402  mov     [rsp+258h+pszPath], rax; pszPath
0x18004e407  xor     ecx, ecx; hwnd
0x18004e409  lea     edx, [r9+26h]; csidl
0x18004e40d  call    cs:__imp_SHGetFolderPathW
0x18004e413  test    eax, eax
0x18004e415  js      short loc_18004E43D
0x18004e417  lea     r8, [rsp+258h+Buffer]; unsigned __int16 *
0x18004e41c  mov     rdx, rbx; unsigned __int16 *
0x18004e41f  call    ?StartsWith@CSqmPIIFilter@PerfDiagOutput@@AEAA_NPEBG0@Z; PerfDiagOutput::CSqmPIIFilter::StartsWith(ushort const *,ushort const *)
0x18004e424  test    al, al
0x18004e426  jnz     short loc_18004E3ED
0x18004e428  cmp     [rdi+28h], sil
0x18004e42c  jz      short loc_18004E43D
0x18004e42e  mov     rdx, rbx; unsigned __int16 *
0x18004e431  mov     rcx, rdi; this
0x18004e434  call    ?IsIncludedBinary@CIncludedBinariesExtensions@PerfDiagOutput@@QEAA_NPEBG@Z; PerfDiagOutput::CIncludedBinariesExtensions::IsIncludedBinary(ushort const *)
0x18004e439  test    al, al
0x18004e43b  jnz     short loc_18004E3ED
0x18004e43d  lea     rax, aPii; "<PII>"
0x18004e444  jmp     short loc_18004E449
0x18004e446  mov     rax, rbx
0x18004e449  mov     rcx, [rsp+258h+var_18]
0x18004e451  xor     rcx, rsp; StackCookie
0x18004e454  call    __security_check_cookie
0x18004e459  lea     r11, [rsp+258h+var_8]
0x18004e461  mov     rbx, [r11+20h]
0x18004e465  mov     rsi, [r11+28h]
0x18004e469  mov     rsp, r11
0x18004e46c  pop     rdi
0x18004e46d  retn
```
