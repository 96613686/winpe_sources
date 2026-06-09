# IsPathUnc(ushort const *,int *)

- ea: `0x18002d6c0`
- end: `0x18002d798`
- name: `?IsPathUnc@@YAJPEBGPEAH@Z`
- size: `216`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002860`
- `0x1800034f0`
- `0x18002d6c0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002d74e`
- `msvcrt!_wcsnicmp` at `0x18002d74e`

## pseudocode

```c
__int64 __fastcall IsPathUnc(const unsigned __int16 *Src, int *a2)
{
  signed int PathCanonicalizationProof; // ebx
  void *v6[4]; // [rsp+20h] [rbp-268h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-248h]
  int v8; // [rsp+48h] [rbp-240h]
  __int16 v9; // [rsp+4Ch] [rbp-23Ch]
  int v10; // [rsp+50h] [rbp-238h]
  __int16 v11; // [rsp+60h] [rbp-228h] BYREF
  _BYTE v12[526]; // [rsp+62h] [rbp-226h] BYREF

  memset_0(v12, 0, 0x206u);
  v8 = 520;
  String1 = (wchar_t *)&v11;
  v9 = 256;
  v10 = 0;
  v11 = 0;
  if ( Src && a2 )
  {
    PathCanonicalizationProof = MakePathCanonicalizationProof(Src, v6);
    if ( PathCanonicalizationProof >= 0 )
      *a2 = _wcsnicmp(String1, L"\\\\?\\UNC\\", 8u) == 0;
  }
  else
  {
    PathCanonicalizationProof = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v6);
  return (unsigned int)PathCanonicalizationProof;
}

```

## disassembly

```asm
0x18002d6c0  mov     [rsp+arg_10], rbx
0x18002d6c5  push    rdi
0x18002d6c6  sub     rsp, 280h
0x18002d6cd  mov     rax, cs:__security_cookie
0x18002d6d4  xor     rax, rsp
0x18002d6d7  mov     [rsp+288h+var_18], rax
0x18002d6df  mov     rdi, rdx
0x18002d6e2  mov     rbx, rcx
0x18002d6e5  xor     edx, edx; Val
0x18002d6e7  lea     rcx, [rsp+288h+var_226]; void *
0x18002d6ec  mov     r8d, 206h; Size
0x18002d6f2  call    memset_0
0x18002d6f7  lea     rax, [rsp+288h+var_228]
0x18002d6fc  mov     [rsp+288h+var_240], 208h
0x18002d704  mov     [rsp+288h+String1], rax
0x18002d709  xor     eax, eax
0x18002d70b  mov     [rsp+288h+var_23C], 100h
0x18002d712  mov     [rsp+288h+var_238], 0
0x18002d71a  mov     [rsp+288h+var_228], ax
0x18002d71f  test    rbx, rbx
0x18002d722  jz      short loc_18002D765
0x18002d724  test    rdi, rdi
0x18002d727  jz      short loc_18002D765
0x18002d729  lea     rdx, [rsp+288h+var_268]; this
0x18002d72e  mov     rcx, rbx; Src
0x18002d731  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002d736  mov     ebx, eax
0x18002d738  test    eax, eax
0x18002d73a  js      short loc_18002D76A
0x18002d73c  mov     rcx, [rsp+288h+String1]; String1
0x18002d741  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18002d748  mov     r8d, 8; MaxCount
0x18002d74e  call    cs:__imp__wcsnicmp
0x18002d755  nop     dword ptr [rax+rax+00h]
0x18002d75a  xor     ecx, ecx
0x18002d75c  test    eax, eax
0x18002d75e  setz    cl
0x18002d761  mov     [rdi], ecx
0x18002d763  jmp     short loc_18002D76A
0x18002d765  mov     ebx, 80070057h
0x18002d76a  lea     rcx, [rsp+288h+var_268]; this
0x18002d76f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002d774  mov     eax, ebx
0x18002d776  mov     rcx, [rsp+288h+var_18]
0x18002d77e  xor     rcx, rsp; StackCookie
0x18002d781  call    __security_check_cookie
0x18002d786  mov     rbx, [rsp+288h+arg_10]
0x18002d78e  add     rsp, 280h
0x18002d795  pop     rdi
0x18002d796  retn
```
