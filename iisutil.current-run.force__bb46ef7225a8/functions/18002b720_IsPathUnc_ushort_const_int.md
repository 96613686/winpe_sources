# IsPathUnc(ushort const *,int *)

- ea: `0x18002b720`
- end: `0x18002b7f1`
- name: `?IsPathUnc@@YAJPEBGPEAH@Z`
- size: `209`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001f50`
- `0x180002b60`
- `0x18002b720`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002b7ae`
- `msvcrt!_wcsnicmp` at `0x18002b7ae`

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
0x18002b720  mov     [rsp+arg_10], rbx
0x18002b725  push    rdi
0x18002b726  sub     rsp, 280h
0x18002b72d  mov     rax, cs:__security_cookie
0x18002b734  xor     rax, rsp
0x18002b737  mov     [rsp+288h+var_18], rax
0x18002b73f  mov     rdi, rdx
0x18002b742  mov     rbx, rcx
0x18002b745  xor     edx, edx; Val
0x18002b747  lea     rcx, [rsp+288h+var_226]; void *
0x18002b74c  mov     r8d, 206h; Size
0x18002b752  call    memset_0
0x18002b757  lea     rax, [rsp+288h+var_228]
0x18002b75c  mov     [rsp+288h+var_240], 208h
0x18002b764  mov     [rsp+288h+String1], rax
0x18002b769  xor     eax, eax
0x18002b76b  mov     [rsp+288h+var_23C], 100h
0x18002b772  mov     [rsp+288h+var_238], 0
0x18002b77a  mov     [rsp+288h+var_228], ax
0x18002b77f  test    rbx, rbx
0x18002b782  jz      short loc_18002B7BF
0x18002b784  test    rdi, rdi
0x18002b787  jz      short loc_18002B7BF
0x18002b789  lea     rdx, [rsp+288h+var_268]; this
0x18002b78e  mov     rcx, rbx; Src
0x18002b791  call    ?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002b796  mov     ebx, eax
0x18002b798  test    eax, eax
0x18002b79a  js      short loc_18002B7C4
0x18002b79c  mov     rcx, [rsp+288h+String1]; String1
0x18002b7a1  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18002b7a8  mov     r8d, 8; MaxCount
0x18002b7ae  call    cs:__imp__wcsnicmp
0x18002b7b4  xor     ecx, ecx
0x18002b7b6  test    eax, eax
0x18002b7b8  setz    cl
0x18002b7bb  mov     [rdi], ecx
0x18002b7bd  jmp     short loc_18002B7C4
0x18002b7bf  mov     ebx, 80070057h
0x18002b7c4  lea     rcx, [rsp+288h+var_268]; this
0x18002b7c9  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b7ce  mov     eax, ebx
0x18002b7d0  mov     rcx, [rsp+288h+var_18]
0x18002b7d8  xor     rcx, rsp; StackCookie
0x18002b7db  call    __security_check_cookie
0x18002b7e0  mov     rbx, [rsp+288h+arg_10]
0x18002b7e8  add     rsp, 280h
0x18002b7ef  pop     rdi
0x18002b7f0  retn
```
