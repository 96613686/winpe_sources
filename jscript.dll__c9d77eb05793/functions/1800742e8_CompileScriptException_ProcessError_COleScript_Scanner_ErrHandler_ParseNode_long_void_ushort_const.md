# CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)

- ea: `0x1800742e8`
- end: `0x1800744b6`
- name: `?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z`
- size: `462`
- prototype: `__int64 __fastcall(CompileScriptException *__hidden this, struct COleScript *, struct Scanner *, struct ErrHandler *, struct ParseNode *, UINT len, LPCSTR psz, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d590`
- `0x18006e174`

## callees

- `0x180005a80`
- `0x18000ad40`
- `0x18002fdd4`
- `0x1800742e8`
- `0x18009429a`
- `0x1800942d0`

## import_xrefs

- `msvcrt!wcscspn` at `0x18007446b`
- `msvcrt!wcscspn` at `0x18007446b`
- `msvcrt!_snwprintf_s` at `0x1800743a7`
- `msvcrt!_snwprintf_s` at `0x1800743a7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180074403`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180074403`

## pseudocode

```c
__int64 __fastcall CompileScriptException::ProcessError(
        CompileScriptException *this,
        struct COleScript *a2,
        struct Scanner *a3,
        struct ErrHandler *a4,
        struct ParseNode *a5,
        int len,
        LPCSTR psz,
        const unsigned __int16 *a8)
{
  int v13; // ecx
  unsigned int v14; // r14d
  unsigned __int16 *ResourceString; // rax
  unsigned __int16 *v16; // rax
  BSTR v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // rbx
  unsigned int v22; // eax
  wchar_t Buffer[56]; // [rsp+30h] [rbp-B8h] BYREF

  if ( !this )
    return *((unsigned int *)a4 + 64);
  memset_0(this, 0, 0x68u);
  *((_DWORD *)this + 16) = *((_DWORD *)a4 + 64);
  v13 = *((_DWORD *)a4 + 64);
  v14 = *((_DWORD *)a2 + 50);
  if ( (v13 & 0x1FFF0000) != 0xA0000
    || (ResourceString = BstrGetResourceString((unsigned __int16)v13, v14), (*((_QWORD *)this + 3) = ResourceString) == 0) )
  {
    _snwprintf_s(Buffer, 0x32u, 0x31u, L"error %d", *((_DWORD *)this + 16));
    v16 = _SysAllocString(Buffer);
    *((_QWORD *)this + 3) = v16;
    if ( !v16 )
      *((_DWORD *)this + 16) = -2147024882;
  }
  *((_QWORD *)this + 2) = BstrGetResourceString(4096, v14);
  if ( a5 || !a3 )
    return 2254848004LL;
  if ( len > 0 )
  {
    v17 = 0;
    if ( (unsigned int)len < 0x7FFFFFFD )
      v17 = SysAllocStringByteLen(psz, len);
    *((_QWORD *)this + 12) = v17;
  }
  v18 = (__int64)(*((_QWORD *)a3 + 4) - *((_QWORD *)a3 + 2)) >> 1;
  *(_DWORD *)this = v18;
  *((_DWORD *)this + 1) = (__int64)(*((_QWORD *)a3 + 5) - *((_QWORD *)a3 + 2)) >> 1;
  *((_DWORD *)this + 20) = *((_DWORD *)a3 + 102);
  v19 = (__int64)(*((_QWORD *)a3 + 3) - *((_QWORD *)a3 + 2)) >> 1;
  *((_DWORD *)this + 21) = v19;
  if ( (int)v19 >= 0 )
  {
    v20 = -1;
    do
      ++v20;
    while ( a8[v20] );
    if ( (int)v19 <= (int)v20 )
    {
      if ( (int)v18 < (int)v19 )
        *(_DWORD *)this = v19;
      v21 = &a8[(int)v19];
      v22 = wcscspn(v21, L"\n\r");
      *((_QWORD *)this + 11) = _SysAllocStringLen(v21, v22);
      return 2254848004LL;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800742e8  mov     [rsp+arg_10], rbx
0x1800742ed  push    rbp
0x1800742ee  push    rsi
0x1800742ef  push    rdi
0x1800742f0  push    r12
0x1800742f2  push    r13
0x1800742f4  push    r14
0x1800742f6  push    r15
0x1800742f8  sub     rsp, 0B0h
0x1800742ff  mov     rax, cs:__security_cookie
0x180074306  xor     rax, rsp
0x180074309  mov     [rsp+0E8h+var_48], rax
0x180074311  mov     ebp, [rsp+0E8h+len]
0x180074318  xor     r13d, r13d
0x18007431b  mov     r12, [rsp+0E8h+psz]
0x180074323  mov     rsi, r9
0x180074326  mov     r15, [rsp+0E8h+arg_38]
0x18007432e  mov     rbx, r8
0x180074331  mov     r14, rdx
0x180074334  mov     rdi, rcx
0x180074337  test    rcx, rcx
0x18007433a  jnz     short loc_180074348
0x18007433c  mov     eax, [r9+100h]
0x180074343  jmp     loc_180074484
0x180074348  xor     edx, edx; Val
0x18007434a  lea     r8d, [rdx+68h]; Size
0x18007434e  call    memset_0
0x180074353  mov     eax, [rsi+100h]
0x180074359  mov     [rdi+40h], eax
0x18007435c  mov     ecx, [rsi+100h]
0x180074362  mov     eax, ecx
0x180074364  mov     r14d, [r14+0C8h]
0x18007436b  and     eax, 1FFF0000h
0x180074370  cmp     eax, 0A0000h
0x180074375  jnz     short loc_18007438B
0x180074377  movzx   ecx, cx; int
0x18007437a  mov     edx, r14d; unsigned int
0x18007437d  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180074382  mov     [rdi+18h], rax
0x180074386  test    rax, rax
0x180074389  jnz     short loc_1800743C7
0x18007438b  mov     eax, [rdi+40h]
0x18007438e  lea     r9, aErrorD; "error %d"
0x180074395  mov     edx, 32h ; '2'; BufferCount
0x18007439a  mov     [rsp+0E8h+var_C8], eax
0x18007439e  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x1800743a3  lea     r8d, [rdx-1]; MaxCount
0x1800743a7  call    cs:__imp__snwprintf_s
0x1800743ad  lea     rcx, [rsp+0E8h+Buffer]; strIn
0x1800743b2  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x1800743b7  mov     [rdi+18h], rax
0x1800743bb  test    rax, rax
0x1800743be  jnz     short loc_1800743C7
0x1800743c0  mov     dword ptr [rdi+40h], 8007000Eh
0x1800743c7  mov     edx, r14d; unsigned int
0x1800743ca  mov     ecx, 1000h; int
0x1800743cf  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x1800743d4  mov     [rdi+10h], rax
0x1800743d8  cmp     [rsp+0E8h+arg_20], r13
0x1800743e0  jnz     loc_18007447F
0x1800743e6  test    rbx, rbx
0x1800743e9  jz      loc_18007447F
0x1800743ef  test    ebp, ebp
0x1800743f1  jle     short loc_18007440D
0x1800743f3  mov     rax, r13
0x1800743f6  cmp     ebp, 7FFFFFFDh
0x1800743fc  jnb     short loc_180074409
0x1800743fe  mov     edx, ebp; len
0x180074400  mov     rcx, r12; psz
0x180074403  call    cs:__imp_SysAllocStringByteLen
0x180074409  mov     [rdi+60h], rax
0x18007440d  mov     rdx, [rbx+20h]
0x180074411  sub     rdx, [rbx+10h]
0x180074415  sar     rdx, 1
0x180074418  mov     [rdi], edx
0x18007441a  mov     rax, [rbx+28h]
0x18007441e  sub     rax, [rbx+10h]
0x180074422  sar     rax, 1
0x180074425  mov     [rdi+4], eax
0x180074428  mov     eax, [rbx+198h]
0x18007442e  mov     [rdi+50h], eax
0x180074431  mov     rax, [rbx+18h]
0x180074435  sub     rax, [rbx+10h]
0x180074439  sar     rax, 1
0x18007443c  mov     [rdi+54h], eax
0x18007443f  test    eax, eax
0x180074441  js      short loc_1800744AF
0x180074443  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180074447  inc     rcx
0x18007444a  cmp     [r15+rcx*2], r13w
0x18007444f  jnz     short loc_180074447
0x180074451  cmp     eax, ecx
0x180074453  jg      short loc_1800744AF
0x180074455  cmp     edx, eax
0x180074457  jge     short loc_18007445B
0x180074459  mov     [rdi], eax
0x18007445b  cdqe
0x18007445d  lea     rdx, Control; "\n\r"
0x180074464  lea     rbx, [r15+rax*2]
0x180074468  mov     rcx, rbx; String
0x18007446b  call    cs:__imp_wcscspn
0x180074471  mov     edx, eax; unsigned int
0x180074473  mov     rcx, rbx; unsigned __int16 *
0x180074476  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18007447b  mov     [rdi+58h], rax
0x18007447f  mov     eax, 86664004h
0x180074484  mov     rcx, [rsp+0E8h+var_48]
0x18007448c  xor     rcx, rsp; StackCookie
0x18007448f  call    __security_check_cookie
0x180074494  mov     rbx, [rsp+0E8h+arg_10]
0x18007449c  add     rsp, 0B0h
0x1800744a3  pop     r15
0x1800744a5  pop     r14
0x1800744a7  pop     r13
0x1800744a9  pop     r12
0x1800744ab  pop     rdi
0x1800744ac  pop     rsi
0x1800744ad  pop     rbp
0x1800744ae  retn
0x1800744af  mov     eax, 8000FFFFh
0x1800744b4  jmp     short loc_180074484
```
