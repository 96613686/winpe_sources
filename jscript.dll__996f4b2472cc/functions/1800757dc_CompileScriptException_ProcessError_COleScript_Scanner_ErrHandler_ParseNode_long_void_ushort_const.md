# CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)

- ea: `0x1800757dc`
- end: `0x1800759ab`
- name: `?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z`
- size: `463`
- prototype: `__int64 __fastcall(CompileScriptException *__hidden this, struct COleScript *, struct Scanner *, struct ErrHandler *, struct ParseNode *, unsigned int, char *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a510`
- `0x18006f530`

## callees

- `0x180004c64`
- `0x180007e68`
- `0x180033698`
- `0x180040d68`
- `0x1800757dc`
- `0x1800966aa`
- `0x1800966e0`

## import_xrefs

- `msvcrt!wcscspn` at `0x180075959`
- `msvcrt!wcscspn` at `0x180075959`
- `msvcrt!_snwprintf_s` at `0x18007589b`
- `msvcrt!_snwprintf_s` at `0x18007589b`

## pseudocode

```c
__int64 __fastcall CompileScriptException::ProcessError(
        CompileScriptException *this,
        struct COleScript *a2,
        struct Scanner *a3,
        struct ErrHandler *a4,
        struct ParseNode *a5,
        int a6,
        char *a7,
        const unsigned __int16 *a8)
{
  int v13; // ecx
  unsigned int v14; // r14d
  unsigned __int16 *ResourceString; // rax
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  const wchar_t *v20; // rbx
  unsigned int v21; // eax
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
  if ( a6 > 0 )
    *((_QWORD *)this + 12) = _SysAllocStringByteLen(a7, a6);
  v17 = (__int64)(*((_QWORD *)a3 + 4) - *((_QWORD *)a3 + 2)) >> 1;
  *(_DWORD *)this = v17;
  *((_DWORD *)this + 1) = (__int64)(*((_QWORD *)a3 + 5) - *((_QWORD *)a3 + 2)) >> 1;
  *((_DWORD *)this + 20) = *((_DWORD *)a3 + 102);
  v18 = (__int64)(*((_QWORD *)a3 + 3) - *((_QWORD *)a3 + 2)) >> 1;
  *((_DWORD *)this + 21) = v18;
  if ( (int)v18 >= 0 )
  {
    v19 = -1;
    do
      ++v19;
    while ( a8[v19] );
    if ( (int)v18 <= (int)v19 )
    {
      if ( (int)v17 < (int)v18 )
        *(_DWORD *)this = v18;
      v20 = &a8[(int)v18];
      v21 = wcscspn(v20, L"\n\r");
      *((_QWORD *)this + 11) = _SysAllocStringLen(v20, v21);
      return 2254848004LL;
    }
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800757dc  mov     [rsp+arg_10], rbx
0x1800757e1  push    rbp
0x1800757e2  push    rsi
0x1800757e3  push    rdi
0x1800757e4  push    r12
0x1800757e6  push    r13
0x1800757e8  push    r14
0x1800757ea  push    r15
0x1800757ec  sub     rsp, 0B0h
0x1800757f3  mov     rax, cs:__security_cookie
0x1800757fa  xor     rax, rsp
0x1800757fd  mov     [rsp+0E8h+var_48], rax
0x180075805  mov     ebp, [rsp+0E8h+arg_28]
0x18007580c  xor     r13d, r13d
0x18007580f  mov     r12, [rsp+0E8h+arg_30]
0x180075817  mov     rsi, r9
0x18007581a  mov     r15, [rsp+0E8h+arg_38]
0x180075822  mov     rbx, r8
0x180075825  mov     r14, rdx
0x180075828  mov     rdi, rcx
0x18007582b  test    rcx, rcx
0x18007582e  jnz     short loc_18007583C
0x180075830  mov     eax, [r9+100h]
0x180075837  jmp     loc_180075978
0x18007583c  xor     edx, edx; Val
0x18007583e  lea     r8d, [rdx+68h]; Size
0x180075842  call    memset_0
0x180075847  mov     eax, [rsi+100h]
0x18007584d  mov     [rdi+40h], eax
0x180075850  mov     ecx, [rsi+100h]
0x180075856  mov     eax, ecx
0x180075858  mov     r14d, [r14+0C8h]
0x18007585f  and     eax, 1FFF0000h
0x180075864  cmp     eax, 0A0000h
0x180075869  jnz     short loc_18007587F
0x18007586b  movzx   ecx, cx; int
0x18007586e  mov     edx, r14d; unsigned int
0x180075871  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x180075876  mov     [rdi+18h], rax
0x18007587a  test    rax, rax
0x18007587d  jnz     short loc_1800758C1
0x18007587f  mov     eax, [rdi+40h]
0x180075882  lea     r9, aErrorD; "error %d"
0x180075889  mov     edx, 32h ; '2'; BufferCount
0x18007588e  mov     [rsp+0E8h+var_C8], eax
0x180075892  lea     rcx, [rsp+0E8h+Buffer]; Buffer
0x180075897  lea     r8d, [rdx-1]; MaxCount
0x18007589b  call    cs:__imp__snwprintf_s
0x1800758a2  nop     dword ptr [rax+rax+00h]
0x1800758a7  lea     rcx, [rsp+0E8h+Buffer]; strIn
0x1800758ac  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x1800758b1  mov     [rdi+18h], rax
0x1800758b5  test    rax, rax
0x1800758b8  jnz     short loc_1800758C1
0x1800758ba  mov     dword ptr [rdi+40h], 8007000Eh
0x1800758c1  mov     edx, r14d; unsigned int
0x1800758c4  mov     ecx, 1000h; int
0x1800758c9  call    ?BstrGetResourceString@@YAPEAGJK@Z; BstrGetResourceString(long,ulong)
0x1800758ce  mov     [rdi+10h], rax
0x1800758d2  cmp     [rsp+0E8h+arg_20], r13
0x1800758da  jnz     loc_180075973
0x1800758e0  test    rbx, rbx
0x1800758e3  jz      loc_180075973
0x1800758e9  test    ebp, ebp
0x1800758eb  jle     short loc_1800758FB
0x1800758ed  mov     edx, ebp; unsigned int
0x1800758ef  mov     rcx, r12; char *
0x1800758f2  call    ?_SysAllocStringByteLen@@YAPEAGPEBDI@Z; _SysAllocStringByteLen(char const *,uint)
0x1800758f7  mov     [rdi+60h], rax
0x1800758fb  mov     rdx, [rbx+20h]
0x1800758ff  sub     rdx, [rbx+10h]
0x180075903  sar     rdx, 1
0x180075906  mov     [rdi], edx
0x180075908  mov     rax, [rbx+28h]
0x18007590c  sub     rax, [rbx+10h]
0x180075910  sar     rax, 1
0x180075913  mov     [rdi+4], eax
0x180075916  mov     eax, [rbx+198h]
0x18007591c  mov     [rdi+50h], eax
0x18007591f  mov     rax, [rbx+18h]
0x180075923  sub     rax, [rbx+10h]
0x180075927  sar     rax, 1
0x18007592a  mov     [rdi+54h], eax
0x18007592d  test    eax, eax
0x18007592f  js      short loc_1800759A4
0x180075931  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180075935  inc     rcx
0x180075938  cmp     [r15+rcx*2], r13w
0x18007593d  jnz     short loc_180075935
0x18007593f  cmp     eax, ecx
0x180075941  jg      short loc_1800759A4
0x180075943  cmp     edx, eax
0x180075945  jge     short loc_180075949
0x180075947  mov     [rdi], eax
0x180075949  cdqe
0x18007594b  lea     rdx, Control; "\n\r"
0x180075952  lea     rbx, [r15+rax*2]
0x180075956  mov     rcx, rbx; String
0x180075959  call    cs:__imp_wcscspn
0x180075960  nop     dword ptr [rax+rax+00h]
0x180075965  mov     edx, eax; unsigned int
0x180075967  mov     rcx, rbx; unsigned __int16 *
0x18007596a  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18007596f  mov     [rdi+58h], rax
0x180075973  mov     eax, 86664004h
0x180075978  mov     rcx, [rsp+0E8h+var_48]
0x180075980  xor     rcx, rsp; StackCookie
0x180075983  call    __security_check_cookie
0x180075988  mov     rbx, [rsp+0E8h+arg_10]
0x180075990  add     rsp, 0B0h
0x180075997  pop     r15
0x180075999  pop     r14
0x18007599b  pop     r13
0x18007599d  pop     r12
0x18007599f  pop     rdi
0x1800759a0  pop     rsi
0x1800759a1  pop     rbp
0x1800759a2  retn
0x1800759a4  mov     eax, 8000FFFFh
0x1800759a9  jmp     short loc_180075978
```
