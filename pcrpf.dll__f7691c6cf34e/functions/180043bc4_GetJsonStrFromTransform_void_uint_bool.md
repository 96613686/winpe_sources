# GetJsonStrFromTransform(void *,uint,bool *)

- ea: `0x180043bc4`
- end: `0x180043d83`
- name: `?GetJsonStrFromTransform@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXIPEA_N@Z`
- size: `447`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *, int, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004b640`
- `0x18004b710`

## callees

- `0x18000c7a8`
- `0x18002b184`
- `0x180034430`
- `0x180034ff8`
- `0x180043bc4`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x180043c53`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x180043c74`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x180043c53`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x180043c74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043d2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043d2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043d3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043d3f`

## string_xrefs

- `0x180043d71`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall GetJsonStrFromTransform(_QWORD *a1, _BYTE *a2, int a3, char *a4)
{
  __int64 v7; // rcx
  unsigned int v8; // esi
  const char *v9; // r9
  CHAR *v10; // rbx
  const CHAR *v11; // r14
  void *v12; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  LPVOID *p_lpMem; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-18h] BYREF
  char v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  void *v20; // [rsp+98h] [rbp+48h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+58h] BYREF

  *a4 = 0;
  if ( a2 && a3 )
  {
    v7 = (unsigned int)(a3 - 1);
    if ( a2[v7] )
      LODWORD(v7) = a3;
    v8 = v7;
    wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
      &v20,
      (__int64)a2,
      (unsigned int)v7,
      a4);
    v10 = (CHAR *)v20;
    if ( !v20 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x1003,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    memcpy_0(v20, a2, v8);
    v11 = v10;
    if ( v8 )
    {
      while ( (unsigned int)_o_isspace(*(unsigned __int8 *)v11) )
      {
        ++v11;
        if ( !--v8 )
          goto LABEL_12;
      }
      while ( (unsigned int)_o_isspace((unsigned __int8)v11[--v8]) )
      {
        v11[v8] = 0;
        if ( !v8 )
          goto LABEL_12;
      }
      lpMem = 0;
      LODWORD(v20) = 0;
      p_lpMem = &lpMem;
      v17 = 0;
      v18 = 1;
      PpfhUtf8ToWide(v11, &v17, (int *)&v20);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&p_lpMem);
      v12 = lpMem;
      if ( lpMem )
      {
        if ( (int)v20 >= 2 && *(_WORD *)lpMem == 123 && *((_WORD *)lpMem + (int)v20 - 2) == 125 )
        {
          *a4 = 1;
          *a1 = v12;
          lpMem = 0;
        }
        else
        {
          *a1 = 0;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v12);
        }
      }
      else
      {
        *a1 = 0;
      }
    }
    else
    {
LABEL_12:
      *a1 = 0;
    }
    if ( v10 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v10);
    }
  }
  else
  {
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180043bc4  mov     [rsp-38h+arg_0], rbx
0x180043bc9  push    rbp
0x180043bca  push    rsi
0x180043bcb  push    rdi
0x180043bcc  push    r12
0x180043bce  push    r13
0x180043bd0  push    r14
0x180043bd2  push    r15
0x180043bd4  mov     rbp, rsp
0x180043bd7  sub     rsp, 50h
0x180043bdb  mov     r13, r9
0x180043bde  mov     r14, rdx
0x180043be1  mov     rdi, rcx
0x180043be4  xor     r15d, r15d
0x180043be7  mov     [rbp+var_30], r15d
0x180043beb  mov     [r9], r15b
0x180043bee  test    rdx, rdx
0x180043bf1  jz      loc_180043D52
0x180043bf7  test    r8d, r8d
0x180043bfa  jz      loc_180043D52
0x180043c00  mov     [rbp+var_28], r15
0x180043c04  lea     ecx, [r8-1]
0x180043c08  cmp     [rcx+rdx], r15b
0x180043c0c  cmovnz  ecx, r8d
0x180043c10  mov     esi, ecx
0x180043c12  mov     r8d, ecx
0x180043c15  lea     rcx, [rbp+arg_8]
0x180043c19  call    ??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z; wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)
0x180043c1e  mov     [rbp+var_30], 4
0x180043c25  mov     rcx, [rbp+38h]; this
0x180043c29  mov     rbx, [rbp+arg_8]
0x180043c2d  test    rbx, rbx
0x180043c30  jz      loc_180043D71
0x180043c36  mov     [rbp+var_28], rbx
0x180043c3a  mov     r8d, esi; Size
0x180043c3d  mov     rdx, r14; Src
0x180043c40  mov     rcx, rbx; void *
0x180043c43  call    memcpy_0
0x180043c48  mov     r14, rbx
0x180043c4b  test    esi, esi
0x180043c4d  jz      short loc_180043C94
0x180043c4f  movzx   ecx, byte ptr [r14]
0x180043c53  call    cs:__imp__o_isspace
0x180043c5a  nop     dword ptr [rax+rax+00h]
0x180043c5f  test    eax, eax
0x180043c61  jz      short loc_180043C6D
0x180043c63  inc     r14
0x180043c66  add     esi, 0FFFFFFFFh
0x180043c69  jnz     short loc_180043C4F
0x180043c6b  jmp     short loc_180043C90
0x180043c6d  dec     esi
0x180043c6f  movzx   ecx, byte ptr [rsi+r14]
0x180043c74  call    cs:__imp__o_isspace
0x180043c7b  nop     dword ptr [rax+rax+00h]
0x180043c80  test    eax, eax
0x180043c82  jz      short loc_180043C9C
0x180043c84  mov     byte ptr [rsi+r14], 0
0x180043c89  test    esi, esi
0x180043c8b  jnz     short loc_180043C6D
0x180043c8d  xor     r15d, r15d
0x180043c90  test    esi, esi
0x180043c92  jnz     short loc_180043C9F
0x180043c94  mov     [rdi], r15
0x180043c97  jmp     loc_180043D26
0x180043c9c  xor     r15d, r15d
0x180043c9f  mov     [rbp+lpMem], r15
0x180043ca3  mov     dword ptr [rbp+arg_8], r15d
0x180043ca7  lea     rax, [rbp+lpMem]
0x180043cab  mov     [rbp+var_20], rax
0x180043caf  mov     [rbp+var_18], r15
0x180043cb3  mov     [rbp+var_10], 1
0x180043cb7  lea     r8, [rbp+arg_8]; int *
0x180043cbb  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180043cbf  mov     rcx, r14; lpMultiByteStr
0x180043cc2  call    ?PpfhUtf8ToWide@@YAJPEBDPEAPEAGPEAH@Z; PpfhUtf8ToWide(char const *,ushort * *,int *)
0x180043cc7  nop
0x180043cc8  lea     rcx, [rbp+var_20]
0x180043ccc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180043cd1  mov     rsi, [rbp+lpMem]
0x180043cd5  test    rsi, rsi
0x180043cd8  jz      short loc_180043D4D
0x180043cda  mov     eax, dword ptr [rbp+arg_8]
0x180043cdd  cmp     eax, 2
0x180043ce0  jge     short loc_180043D07
0x180043ce2  mov     [rdi], r15
0x180043ce5  call    cs:__imp_GetProcessHeap
0x180043cec  nop     dword ptr [rax+rax+00h]
0x180043cf1  mov     rcx, rax; hHeap
0x180043cf4  mov     r8, rsi; lpMem
0x180043cf7  xor     edx, edx; dwFlags
0x180043cf9  call    cs:__imp_HeapFree
0x180043d00  nop     dword ptr [rax+rax+00h]
0x180043d05  jmp     short loc_180043D26
0x180043d07  cmp     word ptr [rsi], 7Bh ; '{'
0x180043d0b  jnz     short loc_180043CE2
0x180043d0d  add     eax, 0FFFFFFFEh
0x180043d10  movsxd  rcx, eax
0x180043d13  cmp     word ptr [rsi+rcx*2], 7Dh ; '}'
0x180043d18  jnz     short loc_180043CE2
0x180043d1a  mov     byte ptr [r13+0], 1
0x180043d1f  mov     [rdi], rsi
0x180043d22  mov     [rbp+lpMem], r15
0x180043d26  test    rbx, rbx
0x180043d29  jz      short loc_180043D55
0x180043d2b  call    cs:__imp_GetProcessHeap
0x180043d32  nop     dword ptr [rax+rax+00h]
0x180043d37  xor     edx, edx; dwFlags
0x180043d39  mov     r8, rbx; lpMem
0x180043d3c  mov     rcx, rax; hHeap
0x180043d3f  call    cs:__imp_HeapFree
0x180043d46  nop     dword ptr [rax+rax+00h]
0x180043d4b  jmp     short loc_180043D55
0x180043d4d  mov     [rdi], r15
0x180043d50  jmp     short loc_180043D26
0x180043d52  mov     [rcx], r15
0x180043d55  mov     rax, rdi
0x180043d58  mov     rbx, [rsp+50h+arg_0]
0x180043d60  add     rsp, 50h
0x180043d64  pop     r15
0x180043d66  pop     r14
0x180043d68  pop     r13
0x180043d6a  pop     r12
0x180043d6c  pop     rdi
0x180043d6d  pop     rsi
0x180043d6e  pop     rbp
0x180043d6f  retn
0x180043d71  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180043d78  mov     edx, 1003h; void *
0x180043d7d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
