# CFSVPProvider::RequestThreadpoolWork(void)

- ea: `0x18024ddb0`
- end: `0x18024de50`
- name: `?RequestThreadpoolWork@CFSVPProvider@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180080e04`
- `0x180080f80`
- `0x180081b24`

## callees

- `0x18004fce4`
- `0x18024ddb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024dde0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024dde0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18024ddd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18024ddd1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18024de3d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18024de3d`

## pseudocode

```c
__int64 __fastcall CFSVPProvider::RequestThreadpoolWork(_QWORD *pv)
{
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  struct _TP_WORK *v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( pv[3] )
    goto LABEL_12;
  ThreadpoolWork = CreateThreadpoolWork(
                     CFSVPProvider::EnsureThreadpoolTask_::_5_::_lambda_1_::_lambda_invoker_cdecl_,
                     pv,
                     0);
  pv[3] = ThreadpoolWork;
  if ( ThreadpoolWork )
    goto LABEL_12;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
  {
LABEL_12:
    if ( !*((_BYTE *)pv + 72) )
    {
      v6 = (struct _TP_WORK *)pv[3];
      *((_BYTE *)pv + 72) = 1;
      SubmitThreadpoolWork(v6);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\global\\fsvpprovider.cpp",
      (const char *)v4,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\global\\fsvpprovider.cpp",
      (const char *)v4,
      v8);
    return v4;
  }
}

```

## disassembly

```asm
0x18024ddb0  mov     [rsp+arg_0], rbx
0x18024ddb5  push    rdi; int
0x18024ddb6  sub     rsp, 20h
0x18024ddba  cmp     qword ptr [rcx+18h], 0
0x18024ddbf  mov     rdi, rcx
0x18024ddc2  jnz     short loc_18024DE2F
0x18024ddc4  mov     rdx, rcx; pv
0x18024ddc7  xor     r8d, r8d; pcbe
0x18024ddca  lea     rcx, _CFSVPProvider__EnsureThreadpoolTask____5____lambda_1____lambda_invoker_cdecl_; pfnwk
0x18024ddd1  call    cs:__imp_CreateThreadpoolWork
0x18024ddd7  mov     [rdi+18h], rax
0x18024dddb  test    rax, rax
0x18024ddde  jnz     short loc_18024DE2F
0x18024dde0  call    cs:__imp_GetLastError
0x18024dde6  mov     ebx, eax
0x18024dde8  test    eax, eax
0x18024ddea  jle     short loc_18024DDF5
0x18024ddec  movzx   ebx, ax
0x18024ddef  or      ebx, 80070000h
0x18024ddf5  test    ebx, ebx
0x18024ddf7  jns     short loc_18024DE2F
0x18024ddf9  mov     rcx, [rsp+28h]; this
0x18024ddfe  lea     r8, aOnecoreuapWind_161; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18024de05  mov     r9d, ebx; char *
0x18024de08  mov     edx, 3Bh ; ';'; void *
0x18024de0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024de12  mov     rcx, [rsp+28h]; this
0x18024de17  lea     r8, aOnecoreuapWind_161; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18024de1e  mov     r9d, ebx; char *
0x18024de21  mov     edx, 47h ; 'G'; void *
0x18024de26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024de2b  mov     eax, ebx
0x18024de2d  jmp     short loc_18024DE45
0x18024de2f  cmp     byte ptr [rdi+48h], 0
0x18024de33  jnz     short loc_18024DE43
0x18024de35  mov     rcx, [rdi+18h]; pwk
0x18024de39  mov     byte ptr [rdi+48h], 1
0x18024de3d  call    cs:__imp_SubmitThreadpoolWork
0x18024de43  xor     eax, eax
0x18024de45  mov     rbx, [rsp+28h+arg_0]
0x18024de4a  add     rsp, 20h
0x18024de4e  pop     rdi
0x18024de4f  retn
```
