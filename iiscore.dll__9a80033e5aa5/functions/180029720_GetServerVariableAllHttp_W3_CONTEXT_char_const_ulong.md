# GetServerVariableAllHttp(W3_CONTEXT *,char const * *,ulong *)

- ea: `0x180029720`
- end: `0x180029809`
- name: `?GetServerVariableAllHttp@@YAJPEAVW3_CONTEXT@@PEAPEBDPEAK@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct W3_CONTEXT *, const char **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180013330`
- `0x180029720`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002975b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002975b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800297dd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800297dd`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180029784`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800297cd`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180029784`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800297cd`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800297bf`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800297bf`

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
0x180029720  mov     [rsp+arg_18], rbx
0x180029725  push    rsi
0x180029726  push    rdi
0x180029727  push    r14
0x180029729  sub     rsp, 270h
0x180029730  mov     rax, cs:__security_cookie
0x180029737  xor     rax, rsp
0x18002973a  mov     [rsp+288h+var_28], rax
0x180029742  mov     r14, r8
0x180029745  mov     rsi, rdx
0x180029748  mov     rdi, rcx
0x18002974b  lea     rdx, [rsp+288h+var_228]
0x180029750  mov     r8d, 200h
0x180029756  lea     rcx, [rsp+288h+var_260]
0x18002975b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180029761  mov     rcx, [rdi+30h]
0x180029765  lea     rdx, [rsp+288h+var_260]; struct STRA *
0x18002976a  mov     r8d, 1; int
0x180029770  mov     rcx, [rcx+28h]; struct _HTTP_REQUEST_V2 *
0x180029774  call    ?GetAllHeaders@@YAJPEBU_HTTP_REQUEST_V2@@PEAVSTRA@@H@Z; GetAllHeaders(_HTTP_REQUEST_V2 const *,STRA *,int)
0x180029779  mov     ebx, eax
0x18002977b  test    eax, eax
0x18002977d  js      short loc_1800297D8
0x18002977f  lea     rcx, [rsp+288h+var_260]
0x180029784  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002978a  mov     rcx, rdi
0x18002978d  lea     edx, [rax+1]
0x180029790  mov     rax, [rdi]
0x180029793  mov     [rsp+288h+var_268], edx
0x180029797  mov     rax, [rax+90h]
0x18002979e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297a3  mov     rbx, rax
0x1800297a6  test    rax, rax
0x1800297a9  jnz     short loc_1800297B2
0x1800297ab  mov     ebx, 80070008h
0x1800297b0  jmp     short loc_1800297D8
0x1800297b2  lea     r8, [rsp+288h+var_268]
0x1800297b7  mov     rdx, rbx
0x1800297ba  lea     rcx, [rsp+288h+var_260]
0x1800297bf  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x1800297c5  lea     rcx, [rsp+288h+var_260]
0x1800297ca  mov     [rsi], rbx
0x1800297cd  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800297d3  mov     [r14], eax
0x1800297d6  xor     ebx, ebx
0x1800297d8  lea     rcx, [rsp+288h+var_260]
0x1800297dd  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800297e3  mov     eax, ebx
0x1800297e5  mov     rcx, [rsp+288h+var_28]
0x1800297ed  xor     rcx, rsp; StackCookie
0x1800297f0  call    __security_check_cookie
0x1800297f5  mov     rbx, [rsp+288h+arg_18]
0x1800297fd  add     rsp, 270h
0x180029804  pop     r14
0x180029806  pop     rdi
0x180029807  pop     rsi
0x180029808  retn
```
