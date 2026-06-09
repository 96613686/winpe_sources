# CFSVPProvider::RequestThreadpoolWork(void)

- ea: `0x18024dd90`
- end: `0x18024de30`
- name: `?RequestThreadpoolWork@CFSVPProvider@@AEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800583e4`
- `0x180058560`
- `0x180059104`

## callees

- `0x180042854`
- `0x18024dd90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024ddc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024ddc0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18024ddb1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18024ddb1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18024de1d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18024de1d`

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
0x18024dd90  mov     [rsp+arg_0], rbx
0x18024dd95  push    rdi; int
0x18024dd96  sub     rsp, 20h
0x18024dd9a  cmp     qword ptr [rcx+18h], 0
0x18024dd9f  mov     rdi, rcx
0x18024dda2  jnz     short loc_18024DE0F
0x18024dda4  mov     rdx, rcx; pv
0x18024dda7  xor     r8d, r8d; pcbe
0x18024ddaa  lea     rcx, _CFSVPProvider__EnsureThreadpoolTask____5____lambda_1____lambda_invoker_cdecl_; pfnwk
0x18024ddb1  call    cs:__imp_CreateThreadpoolWork
0x18024ddb7  mov     [rdi+18h], rax
0x18024ddbb  test    rax, rax
0x18024ddbe  jnz     short loc_18024DE0F
0x18024ddc0  call    cs:__imp_GetLastError
0x18024ddc6  mov     ebx, eax
0x18024ddc8  test    eax, eax
0x18024ddca  jle     short loc_18024DDD5
0x18024ddcc  movzx   ebx, ax
0x18024ddcf  or      ebx, 80070000h
0x18024ddd5  test    ebx, ebx
0x18024ddd7  jns     short loc_18024DE0F
0x18024ddd9  mov     rcx, [rsp+28h]; this
0x18024ddde  lea     r8, aOnecoreuapWind_161; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18024dde5  mov     r9d, ebx; char *
0x18024dde8  mov     edx, 3Bh ; ';'; void *
0x18024dded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024ddf2  mov     rcx, [rsp+28h]; this
0x18024ddf7  lea     r8, aOnecoreuapWind_161; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18024ddfe  mov     r9d, ebx; char *
0x18024de01  mov     edx, 47h ; 'G'; void *
0x18024de06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024de0b  mov     eax, ebx
0x18024de0d  jmp     short loc_18024DE25
0x18024de0f  cmp     byte ptr [rdi+48h], 0
0x18024de13  jnz     short loc_18024DE23
0x18024de15  mov     rcx, [rdi+18h]; pwk
0x18024de19  mov     byte ptr [rdi+48h], 1
0x18024de1d  call    cs:__imp_SubmitThreadpoolWork
0x18024de23  xor     eax, eax
0x18024de25  mov     rbx, [rsp+28h+arg_0]
0x18024de2a  add     rsp, 20h
0x18024de2e  pop     rdi
0x18024de2f  retn
```
