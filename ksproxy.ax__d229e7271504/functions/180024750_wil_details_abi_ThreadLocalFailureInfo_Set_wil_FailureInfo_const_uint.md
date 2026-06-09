# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180024750`
- end: `0x1800248cd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `381`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011530`

## callees

- `0x18001ffb0`
- `0x1800207f4`
- `0x180023d3c`
- `0x1800246b4`
- `0x1800246d8`
- `0x180024750`
- `0x180025c18`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800247f8`
- `KERNEL32!GetProcessHeap` at `0x1800247f8`
- `KERNEL32!HeapFree` at `0x18002480c`
- `KERNEL32!HeapFree` at `0x18002480c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        unsigned int a3)
{
  char **p_modulePath; // rbx
  const wchar_t **p_message; // rsi
  __int64 v7; // r15
  const char *v8; // rdx
  __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  unsigned __int64 *p_stringBufferSize; // rdi
  void *v13; // r12
  void *stringBuffer; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *pszMessage; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  this->sequenceId = a3;
  p_modulePath = (char **)&this->modulePath;
  p_message = &this->message;
  this->hr = a2->hr;
  this->fileName = 0;
  this->lineNumber = a2->uLineNumber;
  this->failureType = a2->type;
  this->modulePath = 0;
  this->returnAddress = a2->returnAddress;
  this->callerReturnAddress = a2->callerReturnAddress;
  this->message = 0;
  v7 = wil::details::ResultStringSize((wil::details *)a2->pszMessage, (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize((wil::details *)a2->pszFile, v8) + v7;
  v11 = wil::details::ResultStringSize((wil::details *)a2->pszModule, v10) + v9;
  p_stringBufferSize = &this->stringBufferSize;
  if ( !this->stringBuffer || *p_stringBufferSize < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      stringBuffer = this->stringBuffer;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, stringBuffer);
      this->stringBuffer = v13;
      p_modulePath = (char **)&this->modulePath;
      *p_stringBufferSize = v11;
    }
  }
  v16 = (char *)this->stringBuffer;
  if ( v16 )
  {
    v17 = &v16[*p_stringBufferSize];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, (wil::details *)a2->pszFile, (char **)&this->fileName);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, (wil::details *)a2->pszModule, p_modulePath);
    if ( v20 != v17
      && (pszMessage = (wil::details *)a2->pszMessage) != 0
      && *(_WORD *)pszMessage
      && (v22 = wil::details::ResultStringSize(pszMessage, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( p_message )
        *p_message = (const wchar_t *)v20;
      v20 += v24;
    }
    else if ( p_message )
    {
      *p_message = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x180024750  push    rbx
0x180024752  push    rbp
0x180024753  push    rsi
0x180024754  push    rdi
0x180024755  push    r12
0x180024757  push    r13
0x180024759  push    r14
0x18002475b  push    r15
0x18002475d  sub     rsp, 28h
0x180024761  mov     [rcx+4], r8d
0x180024765  lea     rbx, [rcx+20h]
0x180024769  mov     eax, [rdx+8]
0x18002476c  lea     rsi, [rcx+38h]
0x180024770  mov     [rcx+8], eax
0x180024773  xor     r12d, r12d
0x180024776  mov     [rcx+10h], r12
0x18002477a  mov     rbp, rcx
0x18002477d  movzx   eax, word ptr [rdx+40h]
0x180024781  mov     r14, rdx
0x180024784  mov     [rcx+18h], ax
0x180024788  mov     al, [rdx]
0x18002478a  mov     [rcx+1Ah], al
0x18002478d  mov     [rbx], r12
0x180024790  mov     rax, [rdx+88h]
0x180024797  mov     [rcx+28h], rax
0x18002479b  mov     rax, [rdx+90h]
0x1800247a2  mov     [rcx+30h], rax
0x1800247a6  mov     [rsi], r12
0x1800247a9  mov     rcx, [rdx+18h]; this
0x1800247ad  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800247b2  mov     rcx, [r14+38h]; this
0x1800247b6  mov     r15, rax
0x1800247b9  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800247be  mov     rcx, [r14+80h]; this
0x1800247c5  add     r15, rax
0x1800247c8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800247cd  add     r15, rax
0x1800247d0  lea     rdi, [rbp+48h]
0x1800247d4  cmp     [rbp+40h], r12
0x1800247d8  jz      short loc_1800247DF
0x1800247da  cmp     [rdi], r15
0x1800247dd  jnb     short loc_180024826
0x1800247df  mov     rdx, r15; dwBytes
0x1800247e2  mov     ecx, 8; dwFlags
0x1800247e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800247ec  mov     r12, rax
0x1800247ef  test    rax, rax
0x1800247f2  jz      short loc_180024823
0x1800247f4  mov     rbx, [rbp+40h]
0x1800247f8  call    cs:__imp_GetProcessHeap
0x1800247ff  nop     dword ptr [rax+rax+00h]
0x180024804  mov     r8, rbx; lpMem
0x180024807  xor     edx, edx; dwFlags
0x180024809  mov     rcx, rax; hHeap
0x18002480c  call    cs:__imp_HeapFree
0x180024813  nop     dword ptr [rax+rax+00h]
0x180024818  mov     [rbp+40h], r12
0x18002481c  lea     rbx, [rbp+20h]
0x180024820  mov     [rdi], r15
0x180024823  xor     r12d, r12d
0x180024826  mov     rcx, [rbp+40h]; Destination
0x18002482a  test    rcx, rcx
0x18002482d  jz      loc_1800248BB
0x180024833  mov     rdi, [rdi]
0x180024836  lea     r9, [rbp+10h]
0x18002483a  mov     r8, [r14+38h]
0x18002483e  add     rdi, rcx
0x180024841  mov     rdx, rdi
0x180024844  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180024849  mov     r8, [r14+80h]
0x180024850  mov     r9, rbx
0x180024853  mov     rdx, rdi
0x180024856  mov     rcx, rax; Destination
0x180024859  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002485e  mov     rbx, rax
0x180024861  cmp     rax, rdi
0x180024864  jz      short loc_1800248A3
0x180024866  mov     rcx, [r14+18h]; this
0x18002486a  test    rcx, rcx
0x18002486d  jz      short loc_1800248A3
0x18002486f  cmp     [rcx], r12w
0x180024873  jz      short loc_1800248A3
0x180024875  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002487a  mov     rdx, rdi
0x18002487d  mov     r14, rax
0x180024880  sub     rdx, rbx; DestinationSize
0x180024883  cmp     rdx, rax
0x180024886  jb      short loc_1800248A3
0x180024888  mov     r8, rcx; Source
0x18002488b  mov     r9, rax; SourceSize
0x18002488e  mov     rcx, rbx; Destination
0x180024891  call    memcpy_s
0x180024896  test    rsi, rsi
0x180024899  jz      short loc_18002489E
0x18002489b  mov     [rsi], rbx
0x18002489e  add     rbx, r14
0x1800248a1  jmp     short loc_1800248AB
0x1800248a3  test    rsi, rsi
0x1800248a6  jz      short loc_1800248AB
0x1800248a8  mov     [rsi], r12
0x1800248ab  sub     rdi, rbx
0x1800248ae  xor     edx, edx; Val
0x1800248b0  mov     r8, rdi; Size
0x1800248b3  mov     rcx, rbx; void *
0x1800248b6  call    memset_0
0x1800248bb  add     rsp, 28h
0x1800248bf  pop     r15
0x1800248c1  pop     r14
0x1800248c3  pop     r13
0x1800248c5  pop     r12
0x1800248c7  pop     rdi
0x1800248c8  pop     rsi
0x1800248c9  pop     rbp
0x1800248ca  pop     rbx
0x1800248cb  retn
```
