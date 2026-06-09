# GetServerVariableAllHttp(W3_CONTEXT *,char const * *,ulong *)

- ea: `0x18002bbe0`
- end: `0x18002bce8`
- name: `?GetServerVariableAllHttp@@YAJPEAVW3_CONTEXT@@PEAPEBDPEAK@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800143d0`
- `0x18002bbe0`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002bc1b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002bc1b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002bcb5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002bcb5`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002bc4a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002bc9f`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002bc4a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002bc9f`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x18002bc8b`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x18002bc8b`

## pseudocode

```c
__int64 __fastcall GetServerVariableAllHttp(struct W3_CONTEXT *a1, const char **a2, unsigned int *a3)
{
  int AllHeaders; // ebx
  unsigned int v7; // edx
  __int64 v8; // rax
  char *v9; // rax
  const char *v10; // rbx
  unsigned int v12; // [rsp+20h] [rbp-268h] BYREF
  _BYTE v13[56]; // [rsp+28h] [rbp-260h] BYREF
  char v14[512]; // [rsp+60h] [rbp-228h] BYREF

  STRA::STRA((STRA *)v13, v14, 0x200u);
  AllHeaders = GetAllHeaders(*(const struct _HTTP_REQUEST_V2 **)(*((_QWORD *)a1 + 6) + 40LL), (struct STRA *)v13, 1);
  if ( AllHeaders >= 0 )
  {
    v7 = STRA::QueryCCH((STRA *)v13) + 1;
    v8 = *(_QWORD *)a1;
    v12 = v7;
    v9 = (char *)(*(__int64 (__fastcall **)(struct W3_CONTEXT *))(v8 + 144))(a1);
    v10 = v9;
    if ( v9 )
    {
      STRA::CopyToBuffer((STRA *)v13, v9, &v12);
      *a2 = v10;
      *a3 = STRA::QueryCCH((STRA *)v13);
      AllHeaders = 0;
    }
    else
    {
      AllHeaders = -2147024888;
    }
  }
  STRA::~STRA((STRA *)v13);
  return (unsigned int)AllHeaders;
}

```

## disassembly

```asm
0x18002bbe0  mov     [rsp+arg_18], rbx
0x18002bbe5  push    rsi
0x18002bbe6  push    rdi
0x18002bbe7  push    r14
0x18002bbe9  sub     rsp, 270h
0x18002bbf0  mov     rax, cs:__security_cookie
0x18002bbf7  xor     rax, rsp
0x18002bbfa  mov     [rsp+288h+var_28], rax
0x18002bc02  mov     r14, r8
0x18002bc05  mov     rsi, rdx
0x18002bc08  mov     rdi, rcx
0x18002bc0b  lea     rdx, [rsp+288h+var_228]
0x18002bc10  mov     r8d, 200h
0x18002bc16  lea     rcx, [rsp+288h+var_260]
0x18002bc1b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002bc22  nop     dword ptr [rax+rax+00h]
0x18002bc27  mov     rcx, [rdi+30h]
0x18002bc2b  lea     rdx, [rsp+288h+var_260]; struct STRA *
0x18002bc30  mov     r8d, 1; int
0x18002bc36  mov     rcx, [rcx+28h]; struct _HTTP_REQUEST_V2 *
0x18002bc3a  call    ?GetAllHeaders@@YAJPEBU_HTTP_REQUEST_V2@@PEAVSTRA@@H@Z; GetAllHeaders(_HTTP_REQUEST_V2 const *,STRA *,int)
0x18002bc3f  mov     ebx, eax
0x18002bc41  test    eax, eax
0x18002bc43  js      short loc_18002BCB0
0x18002bc45  lea     rcx, [rsp+288h+var_260]
0x18002bc4a  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002bc51  nop     dword ptr [rax+rax+00h]
0x18002bc56  mov     rcx, rdi
0x18002bc59  lea     edx, [rax+1]
0x18002bc5c  mov     rax, [rdi]
0x18002bc5f  mov     [rsp+288h+var_268], edx
0x18002bc63  mov     rax, [rax+90h]
0x18002bc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc6f  mov     rbx, rax
0x18002bc72  test    rax, rax
0x18002bc75  jnz     short loc_18002BC7E
0x18002bc77  mov     ebx, 80070008h
0x18002bc7c  jmp     short loc_18002BCB0
0x18002bc7e  lea     r8, [rsp+288h+var_268]
0x18002bc83  mov     rdx, rbx
0x18002bc86  lea     rcx, [rsp+288h+var_260]
0x18002bc8b  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x18002bc92  nop     dword ptr [rax+rax+00h]
0x18002bc97  lea     rcx, [rsp+288h+var_260]
0x18002bc9c  mov     [rsi], rbx
0x18002bc9f  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002bca6  nop     dword ptr [rax+rax+00h]
0x18002bcab  mov     [r14], eax
0x18002bcae  xor     ebx, ebx
0x18002bcb0  lea     rcx, [rsp+288h+var_260]
0x18002bcb5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002bcbc  nop     dword ptr [rax+rax+00h]
0x18002bcc1  mov     eax, ebx
0x18002bcc3  mov     rcx, [rsp+288h+var_28]
0x18002bccb  xor     rcx, rsp; StackCookie
0x18002bcce  call    __security_check_cookie
0x18002bcd3  mov     rbx, [rsp+288h+arg_18]
0x18002bcdb  add     rsp, 270h
0x18002bce2  pop     r14
0x18002bce4  pop     rdi
0x18002bce5  pop     rsi
0x18002bce6  retn
```
