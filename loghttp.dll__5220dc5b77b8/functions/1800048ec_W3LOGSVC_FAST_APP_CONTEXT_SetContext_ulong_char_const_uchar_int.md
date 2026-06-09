# W3LOGSVC_FAST_APP_CONTEXT::SetContext(ulong,char const *,uchar,int)

- ea: `0x1800048ec`
- end: `0x180004991`
- name: `?SetContext@W3LOGSVC_FAST_APP_CONTEXT@@QEAAXKPEBDEH@Z`
- size: `165`
- prototype: `void(W3LOGSVC_FAST_APP_CONTEXT *__hidden this, unsigned int, const char *, unsigned __int8, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001730`

## callees

- `0x180003080`
- `0x1800056e6`
- `0x1800056f2`
- `0x180005720`

## pseudocode

```c
void __fastcall W3LOGSVC_FAST_APP_CONTEXT::SetContext(
        W3LOGSVC_FAST_APP_CONTEXT *this,
        int a2,
        const char *a3,
        unsigned __int8 a4,
        int a5)
{
  __int64 v6; // rdi
  _QWORD v9[32]; // [rsp+20h] [rbp-138h] BYREF

  v6 = a4;
  memset_0(v9, 0, 0xF5u);
  *(_BYTE *)this = 50;
  *((_BYTE *)this + 1) = (a5 != 0) + 48;
  _snprintf_s<245>(v9, 245, "%08x", a2);
  *(_QWORD *)((char *)this + 2) = v9[0];
  *((_BYTE *)this + 10) = v6;
  memcpy_0((char *)this + 11, a3, (unsigned int)v6);
  *((_BYTE *)this + v6 + 11) = 0;
}

```

## disassembly

```asm
0x1800048ec  push    rbx
0x1800048ee  push    rbp
0x1800048ef  push    rsi
0x1800048f0  push    rdi
0x1800048f1  sub     rsp, 138h
0x1800048f8  mov     rax, cs:__security_cookie
0x1800048ff  xor     rax, rsp
0x180004902  mov     [rsp+158h+var_38], rax
0x18000490a  mov     rbp, r8
0x18000490d  movzx   edi, r9b
0x180004911  mov     ebx, edx
0x180004913  mov     rsi, rcx
0x180004916  xor     edx, edx; Val
0x180004918  lea     rcx, [rsp+158h+var_138]; void *
0x18000491d  mov     r8d, 0F5h; Size
0x180004923  call    memset_0
0x180004928  cmp     [rsp+158h+arg_20], 0
0x180004930  lea     r8, a08x; "%08x"
0x180004937  mov     byte ptr [rsi], 32h ; '2'
0x18000493a  lea     rcx, [rsp+158h+var_138]
0x18000493f  setnz   al
0x180004942  mov     r9d, ebx
0x180004945  add     al, 30h ; '0'
0x180004947  mov     edx, 0F5h
0x18000494c  mov     [rsi+1], al
0x18000494f  call    ??$_snprintf_s@$0PF@@@YAHAEAY0PF@D_KPEBDZZ; _snprintf_s<245>(char (&)[245],unsigned __int64,char const *,...)
0x180004954  mov     rax, [rsp+158h+var_138]
0x180004959  lea     rcx, [rsi+0Bh]; void *
0x18000495d  mov     r8d, edi; Size
0x180004960  mov     [rsi+2], rax
0x180004964  mov     rdx, rbp; Src
0x180004967  mov     [rsi+0Ah], dil
0x18000496b  call    memcpy_0
0x180004970  mov     byte ptr [rdi+rsi+0Bh], 0
0x180004975  mov     rcx, [rsp+158h+var_38]
0x18000497d  xor     rcx, rsp; StackCookie
0x180004980  call    __security_check_cookie
0x180004985  add     rsp, 138h
0x18000498c  pop     rdi
0x18000498d  pop     rsi
0x18000498e  pop     rbp
0x18000498f  pop     rbx
0x180004990  retn
```
