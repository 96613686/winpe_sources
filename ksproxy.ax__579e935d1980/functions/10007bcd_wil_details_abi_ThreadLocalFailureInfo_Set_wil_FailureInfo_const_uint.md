# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x10007bcd`
- end: `0x10007ce4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QAEXABUFailureInfo@3@I@Z`
- size: `279`
- prototype: `void __thiscall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x10007d55`

## callees

- `0x10006cf3`
- `0x100071a0`
- `0x10007bcd`
- `0x1000f192`
- `0x1000f205`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x10007c7a`
- `KERNEL32!GetProcessHeap` at `0x10007c7a`
- `KERNEL32!HeapFree` at `0x10007c84`
- `KERNEL32!HeapFree` at `0x10007c84`

## pseudocode

```c
void __thiscall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        unsigned int a3)
{
  unsigned int v4; // esi
  const wchar_t **p_message; // eax
  const char *pszFile; // ecx
  unsigned int v7; // ebx
  const char *pszModule; // ecx
  SIZE_T v9; // eax
  unsigned int *p_stringBufferSize; // ebx
  void *stringBuffer; // esi
  HANDLE ProcessHeap; // eax
  char *v13; // ecx
  char *v14; // esi
  void *v15; // eax
  void *v16; // eax
  void *v17; // eax
  wil::details *v18; // [esp+0h] [ebp-1Ch]
  const unsigned __int16 *v19; // [esp+4h] [ebp-18h]
  int v20; // [esp+Ch] [ebp-10h]
  const char **p_modulePath; // [esp+10h] [ebp-Ch]
  SIZE_T v22; // [esp+14h] [ebp-8h]
  void *v23; // [esp+18h] [ebp-4h]

  v4 = 1;
  this->sequenceId = a3;
  this->hr = a2->hr;
  this->fileName = 0;
  this->lineNumber = a2->uLineNumber;
  this->failureType = a2->type;
  this->modulePath = 0;
  p_modulePath = &this->modulePath;
  this->returnAddress = a2->returnAddress;
  this->callerReturnAddress = a2->callerReturnAddress;
  p_message = &this->message;
  this->message = 0;
  pszFile = a2->pszFile;
  v20 = (int)p_message;
  if ( pszFile )
    v7 = strlen(pszFile) + 1;
  else
    v7 = 1;
  pszModule = a2->pszModule;
  if ( pszModule )
    v4 = strlen(pszModule) + 1;
  v9 = v7 + v4 + wil::details::ResultStringSize(v18, v19);
  v22 = v9;
  p_stringBufferSize = &this->stringBufferSize;
  if ( !this->stringBuffer || *p_stringBufferSize < v9 )
  {
    v23 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v23 )
    {
      stringBuffer = this->stringBuffer;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, stringBuffer);
      this->stringBuffer = v23;
      *p_stringBufferSize = v22;
    }
  }
  v13 = (char *)this->stringBuffer;
  if ( v13 )
  {
    v14 = &v13[*p_stringBufferSize];
    v15 = (void *)wil::details::WriteResultString<char const *>(v13, (void *)a2->pszFile, (int)&this->fileName);
    v16 = (void *)wil::details::WriteResultString<char const *>(v15, (void *)a2->pszModule, (int)p_modulePath);
    v17 = (void *)wil::details::WriteResultString<unsigned short const *>(v16, (void *)a2->pszMessage, v20);
    memset(v17, 0, v14 - (_BYTE *)v17);
  }
}

```

## disassembly

```asm
0x10007bcd  mov     edi, edi
0x10007bcf  push    ebp
0x10007bd0  mov     ebp, esp
0x10007bd2  sub     esp, 10h
0x10007bd5  mov     edx, [ebp+arg_0]
0x10007bd8  mov     eax, [ebp+arg_4]
0x10007bdb  push    ebx; unsigned int
0x10007bdc  push    esi; unsigned int
0x10007bdd  push    edi; this
0x10007bde  mov     edi, ecx
0x10007be0  xor     esi, esi
0x10007be2  xor     ecx, ecx
0x10007be4  inc     esi
0x10007be5  mov     [edi+4], eax
0x10007be8  mov     eax, [edx+8]
0x10007beb  mov     [edi+8], eax
0x10007bee  mov     [edi+0Ch], ecx
0x10007bf1  mov     ax, [edx+28h]
0x10007bf5  mov     [edi+10h], ax
0x10007bf9  mov     al, [edx]
0x10007bfb  mov     [edi+12h], al
0x10007bfe  lea     eax, [edi+14h]
0x10007c01  mov     [eax], ecx
0x10007c03  mov     [ebp+var_C], eax
0x10007c06  mov     eax, [edx+50h]
0x10007c09  mov     [edi+18h], eax
0x10007c0c  mov     eax, [edx+54h]
0x10007c0f  mov     [edi+1Ch], eax
0x10007c12  lea     eax, [edi+20h]
0x10007c15  mov     [eax], ecx
0x10007c17  mov     ecx, [edx+24h]
0x10007c1a  mov     [ebp+var_10], eax
0x10007c1d  test    ecx, ecx
0x10007c1f  jnz     short loc_10007C25
0x10007c21  mov     ebx, esi
0x10007c23  jmp     short loc_10007C34
0x10007c25  lea     ebx, [ecx+1]
0x10007c28  mov     al, [ecx]
0x10007c2a  inc     ecx
0x10007c2b  test    al, al
0x10007c2d  jnz     short loc_10007C28
0x10007c2f  sub     ecx, ebx
0x10007c31  lea     ebx, [ecx+1]
0x10007c34  mov     ecx, [edx+4Ch]
0x10007c37  test    ecx, ecx
0x10007c39  jz      short loc_10007C4A
0x10007c3b  lea     esi, [ecx+1]
0x10007c3e  mov     al, [ecx]
0x10007c40  inc     ecx
0x10007c41  test    al, al
0x10007c43  jnz     short loc_10007C3E
0x10007c45  sub     ecx, esi
0x10007c47  lea     esi, [ecx+1]
0x10007c4a  mov     ecx, [edx+14h]
0x10007c4d  call    ?ResultStringSize@details@wil@@YGIPBG@Z; wil::details::ResultStringSize(ushort const *)
0x10007c52  add     eax, esi
0x10007c54  add     eax, ebx
0x10007c56  cmp     dword ptr [edi+24h], 0
0x10007c5a  mov     [ebp+var_8], eax
0x10007c5d  lea     ebx, [edi+28h]
0x10007c60  jz      short loc_10007C66
0x10007c62  cmp     [ebx], eax
0x10007c64  jnb     short loc_10007C95
0x10007c66  push    8
0x10007c68  mov     edx, eax
0x10007c6a  pop     ecx
0x10007c6b  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x10007c70  mov     [ebp+var_4], eax
0x10007c73  test    eax, eax
0x10007c75  jz      short loc_10007C95
0x10007c77  mov     esi, [edi+24h]
0x10007c7a  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x10007c80  push    esi; lpMem
0x10007c81  push    0; dwFlags
0x10007c83  push    eax; hHeap
0x10007c84  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x10007c8a  mov     eax, [ebp+var_4]
0x10007c8d  mov     [edi+24h], eax
0x10007c90  mov     eax, [ebp+var_8]
0x10007c93  mov     [ebx], eax
0x10007c95  mov     ecx, [edi+24h]; void *
0x10007c98  test    ecx, ecx
0x10007c9a  jz      short loc_10007CDD
0x10007c9c  mov     esi, [ebx]
0x10007c9e  lea     eax, [edi+0Ch]
0x10007ca1  mov     edi, [ebp+arg_0]
0x10007ca4  add     esi, ecx
0x10007ca6  push    eax; int
0x10007ca7  mov     edx, esi
0x10007ca9  push    dword ptr [edi+24h]; Src
0x10007cac  call    ??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x10007cb1  push    [ebp+var_C]; int
0x10007cb4  mov     edx, esi
0x10007cb6  mov     ecx, eax; void *
0x10007cb8  push    dword ptr [edi+4Ch]; Src
0x10007cbb  call    ??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x10007cc0  push    [ebp+var_10]; int
0x10007cc3  mov     edx, esi
0x10007cc5  mov     ecx, eax; void *
0x10007cc7  push    dword ptr [edi+14h]; Src
0x10007cca  call    ??$WriteResultString@PBG@details@wil@@YGPAEPAE0PBGPAPBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x10007ccf  sub     esi, eax
0x10007cd1  push    esi; Size
0x10007cd2  push    0; Val
0x10007cd4  push    eax; void *
0x10007cd5  call    _memset
0x10007cda  add     esp, 0Ch
0x10007cdd  pop     edi
0x10007cde  pop     esi
0x10007cdf  pop     ebx
0x10007ce0  leave
0x10007ce1  retn    8
```
