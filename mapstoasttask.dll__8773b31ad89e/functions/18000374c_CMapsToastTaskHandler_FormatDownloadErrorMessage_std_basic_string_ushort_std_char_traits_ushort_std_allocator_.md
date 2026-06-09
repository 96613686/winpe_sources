# CMapsToastTaskHandler::FormatDownloadErrorMessage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18000374c`
- end: `0x180003834`
- name: `?FormatDownloadErrorMessage@CMapsToastTaskHandler@@AEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `232`
- prototype: `__int64 __fastcall(const void *, _QWORD *, char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180005e60`

## callees

- `0x1800015b0`
- `0x1800020a4`
- `0x18000374c`
- `0x180005d40`
- `0x18000954c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800037b1`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800037b1`

## string_xrefs

- `0x1800037a2`: `CMapsToastTaskHandler::FormatDownloadErrorMessage`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::FormatDownloadErrorMessage(const void *a1, _QWORD *a2, char **a3)
{
  char **v3; // rbx
  int v5; // eax
  __int64 v6; // r8
  unsigned int v7; // esi
  unsigned __int64 v8; // rdx
  char *v9; // rdi
  __int64 v10; // rbx
  unsigned __int16 Src[1024]; // [rsp+20h] [rbp-828h] BYREF

  v3 = a3;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (char **)*a3;
  v5 = StringCchPrintfW(Src, 0x400u, (const unsigned __int16 *)a3, a2);
  if ( v5 >= 0 )
  {
    v7 = 0;
    v8 = -1;
    do
      ++v8;
    while ( Src[v8] );
    if ( v8 > (unsigned __int64)v3[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v3, v8, v6, Src);
    }
    else
    {
      if ( (unsigned __int64)v3[3] <= 7 )
        v9 = (char *)v3;
      else
        v9 = *v3;
      v3[2] = (char *)v8;
      v10 = 2 * v8;
      memmove_0(v9, Src, 2 * v8);
      *(_WORD *)&v9[v10] = 0;
    }
  }
  else
  {
    return (unsigned int)ZTraceReportOrigination(v5, "CMapsToastTaskHandler::FormatDownloadErrorMessage", 270, a1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000374c  mov     [rsp+arg_18], rbx
0x180003751  push    rbp
0x180003752  push    rsi
0x180003753  push    rdi
0x180003754  sub     rsp, 830h
0x18000375b  mov     rax, cs:__security_cookie
0x180003762  xor     rax, rsp
0x180003765  mov     [rsp+848h+var_28], rax
0x18000376d  cmp     qword ptr [rdx+18h], 7
0x180003772  mov     rbx, r8
0x180003775  mov     rdi, rcx
0x180003778  jbe     short loc_18000377D
0x18000377a  mov     rdx, [rdx]
0x18000377d  cmp     qword ptr [r8+18h], 7
0x180003782  jbe     short loc_180003787
0x180003784  mov     r8, [r8]; unsigned __int16 *
0x180003787  mov     r9, rdx
0x18000378a  lea     rcx, [rsp+848h+Src]; unsigned __int16 *
0x18000378f  mov     edx, 400h; unsigned __int64
0x180003794  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003799  xor     ebp, ebp
0x18000379b  test    eax, eax
0x18000379d  jns     short loc_1800037BB
0x18000379f  mov     r9, rdi
0x1800037a2  lea     rdx, aCmapstoasttask_0; "CMapsToastTaskHandler::FormatDownloadEr"...
0x1800037a9  mov     r8d, 10Eh
0x1800037af  mov     ecx, eax
0x1800037b1  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800037b7  mov     esi, eax
0x1800037b9  jmp     short loc_18000380F
0x1800037bb  mov     esi, ebp
0x1800037bd  lea     rax, [rsp+848h+Src]
0x1800037c2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800037c6  inc     rdx
0x1800037c9  cmp     [rax+rdx*2], bp
0x1800037cd  jnz     short loc_1800037C6
0x1800037cf  cmp     rdx, [rbx+18h]
0x1800037d3  ja      short loc_180003802
0x1800037d5  cmp     qword ptr [rbx+18h], 7
0x1800037da  jbe     short loc_1800037E1
0x1800037dc  mov     rdi, [rbx]
0x1800037df  jmp     short loc_1800037E4
0x1800037e1  mov     rdi, rbx
0x1800037e4  mov     [rbx+10h], rdx
0x1800037e8  mov     rcx, rdi; void *
0x1800037eb  lea     rbx, [rdx+rdx]
0x1800037ef  mov     r8, rbx; Size
0x1800037f2  lea     rdx, [rsp+848h+Src]; Src
0x1800037f7  call    memmove_0
0x1800037fc  mov     [rbx+rdi], bp
0x180003800  jmp     short loc_18000380F
0x180003802  lea     r9, [rsp+848h+Src]
0x180003807  mov     rcx, rbx
0x18000380a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000380f  mov     eax, esi
0x180003811  mov     rcx, [rsp+848h+var_28]
0x180003819  xor     rcx, rsp; StackCookie
0x18000381c  call    __security_check_cookie
0x180003821  mov     rbx, [rsp+848h+arg_18]
0x180003829  add     rsp, 830h
0x180003830  pop     rdi
0x180003831  pop     rsi
0x180003832  pop     rbp
0x180003833  retn
```
