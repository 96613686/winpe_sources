# W3LOGSVC_APP_CONTEXT::SetContext(char const *,ulong,unsigned __int64,void *,int)

- ea: `0x1800047f8`
- end: `0x1800048e4`
- name: `?SetContext@W3LOGSVC_APP_CONTEXT@@QEAAXPEBDK_KPEAXH@Z`
- size: `236`
- prototype: `void __fastcall(W3LOGSVC_APP_CONTEXT *__hidden this, const char *, unsigned int, unsigned __int64, void *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001730`

## callees

- `0x180003044`
- `0x180005720`

## pseudocode

```c
void __fastcall W3LOGSVC_APP_CONTEXT::SetContext(
        W3LOGSVC_APP_CONTEXT *this,
        const char *a2,
        int a3,
        __int64 a4,
        void *a5,
        int a6)
{
  __int128 v8; // xmm0
  __int128 v9; // [rsp+20h] [rbp-38h] BYREF
  char v10; // [rsp+30h] [rbp-28h]

  *(_BYTE *)this = 49;
  v10 = 0;
  v9 = 0;
  *((_BYTE *)this + 1) = (a6 != 0) + 48;
  *(_OWORD *)((char *)this + 2) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 18) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 34) = *((_OWORD *)a2 + 2);
  *(_QWORD *)((char *)this + 49) = *(_QWORD *)(a2 + 47);
  _snprintf_s<17>(&v9, 17, "%08x", a3);
  *(_QWORD *)((char *)this + 57) = v9;
  _snprintf_s<17>(&v9, 17, "%016I64x", a4);
  *(_OWORD *)((char *)this + 65) = v9;
  _snprintf_s<17>(&v9, 17, "%016zx", (size_t)a5);
  v8 = v9;
  *((_BYTE *)this + 97) = 0;
  *(_OWORD *)((char *)this + 81) = v8;
}

```

## disassembly

```asm
0x1800047f8  mov     [rsp+arg_8], rbx
0x1800047fd  push    rbp
0x1800047fe  push    rsi
0x1800047ff  push    rdi
0x180004800  sub     rsp, 40h
0x180004804  mov     rax, cs:__security_cookie
0x18000480b  xor     rax, rsp
0x18000480e  mov     [rsp+58h+var_20], rax
0x180004813  mov     rbx, [rsp+58h+arg_20]
0x18000481b  xor     eax, eax
0x18000481d  cmp     [rsp+58h+arg_28], eax
0x180004824  xorps   xmm0, xmm0
0x180004827  mov     byte ptr [rcx], 31h ; '1'
0x18000482a  mov     rdi, r9
0x18000482d  mov     [rsp+58h+var_28], al
0x180004831  mov     rsi, rcx
0x180004834  movups  [rsp+58h+var_38], xmm0
0x180004839  setnz   al
0x18000483c  mov     r9d, r8d
0x18000483f  add     al, 30h ; '0'
0x180004841  lea     r8, a08x; "%08x"
0x180004848  mov     [rcx+1], al
0x18000484b  mov     ebp, 11h
0x180004850  movups  xmm0, xmmword ptr [rdx]
0x180004853  movups  xmmword ptr [rcx+2], xmm0
0x180004857  movups  xmm1, xmmword ptr [rdx+10h]
0x18000485b  movups  xmmword ptr [rcx+12h], xmm1
0x18000485f  movups  xmm0, xmmword ptr [rdx+20h]
0x180004863  movups  xmmword ptr [rcx+22h], xmm0
0x180004867  movsd   xmm1, qword ptr [rdx+2Fh]
0x18000486c  mov     edx, ebp
0x18000486e  movsd   qword ptr [rcx+31h], xmm1
0x180004873  lea     rcx, [rsp+58h+var_38]
0x180004878  call    ??$_snprintf_s@$0BB@@@YAHAEAY0BB@D_KPEBDZZ; _snprintf_s<17>(char (&)[17],unsigned __int64,char const *,...)
0x18000487d  mov     rax, qword ptr [rsp+58h+var_38]
0x180004882  lea     r8, a016i64x; "%016I64x"
0x180004889  mov     r9, rdi
0x18000488c  mov     [rsi+39h], rax
0x180004890  mov     edx, ebp
0x180004892  lea     rcx, [rsp+58h+var_38]
0x180004897  call    ??$_snprintf_s@$0BB@@@YAHAEAY0BB@D_KPEBDZZ; _snprintf_s<17>(char (&)[17],unsigned __int64,char const *,...)
0x18000489c  movups  xmm0, [rsp+58h+var_38]
0x1800048a1  mov     r9, rbx
0x1800048a4  lea     r8, a016zx; "%016zx"
0x1800048ab  mov     edx, ebp
0x1800048ad  lea     rcx, [rsp+58h+var_38]
0x1800048b2  movdqu  xmmword ptr [rsi+41h], xmm0
0x1800048b7  call    ??$_snprintf_s@$0BB@@@YAHAEAY0BB@D_KPEBDZZ; _snprintf_s<17>(char (&)[17],unsigned __int64,char const *,...)
0x1800048bc  movups  xmm0, [rsp+58h+var_38]
0x1800048c1  mov     byte ptr [rsi+61h], 0
0x1800048c5  movdqu  xmmword ptr [rsi+51h], xmm0
0x1800048ca  mov     rcx, [rsp+58h+var_20]
0x1800048cf  xor     rcx, rsp; StackCookie
0x1800048d2  call    __security_check_cookie
0x1800048d7  mov     rbx, [rsp+58h+arg_8]
0x1800048dc  add     rsp, 40h
0x1800048e0  pop     rdi
0x1800048e1  pop     rsi
0x1800048e2  pop     rbp
0x1800048e3  retn
```
