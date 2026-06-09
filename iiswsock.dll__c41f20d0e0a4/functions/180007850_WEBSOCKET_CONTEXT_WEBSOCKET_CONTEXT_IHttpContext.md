# WEBSOCKET_CONTEXT::WEBSOCKET_CONTEXT(IHttpContext *)

- ea: `0x180007850`
- end: `0x180007993`
- name: `??0WEBSOCKET_CONTEXT@@QEAA@PEAVIHttpContext@@@Z`
- size: `323`
- prototype: `WEBSOCKET_CONTEXT *__fastcall(WEBSOCKET_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008080`

## import_xrefs

- `iisutil!IISInitializeCriticalSection` at `0x1800078ec`
- `iisutil!IISInitializeCriticalSection` at `0x180007973`
- `iisutil!IISInitializeCriticalSection` at `0x1800078ec`
- `iisutil!IISInitializeCriticalSection` at `0x180007973`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000791f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000791f`

## pseudocode

```c
WEBSOCKET_CONTEXT *__fastcall WEBSOCKET_CONTEXT::WEBSOCKET_CONTEXT(WEBSOCKET_CONTEXT *this, struct IHttpContext *a2)
{
  char *v2; // rbx
  WEBSOCKET_CONTEXT *result; // rax

  *((_DWORD *)this + 2) = 1;
  v2 = (char *)this + 184;
  *((_DWORD *)this + 3) = 1480807255;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &WEBSOCKET_CONTEXT::`vftable';
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = &READ_CONTEXT::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 18) = &WEBSOCKET_IO_MANAGER::`vftable';
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = a2;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  IISInitializeCriticalSection((char *)this + 184);
  *((_QWORD *)v2 + 6) = v2 + 40;
  *((_QWORD *)v2 + 5) = v2 + 40;
  *((_DWORD *)this + 64) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_WORD *)this + 140) = 0;
  STRU::STRU((WEBSOCKET_CONTEXT *)((char *)this + 288));
  *((_QWORD *)this + 43) = a2;
  *((_DWORD *)this + 88) = 0;
  *((_DWORD *)this + 89) = 0;
  *((_DWORD *)this + 90) = 0;
  *((_DWORD *)this + 91) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_DWORD *)this + 93) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  IISInitializeCriticalSection((char *)this + 392);
  result = this;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 55) = 0;
  return result;
}

```

## disassembly

```asm
0x180007850  push    rbx
0x180007852  push    rbp
0x180007853  push    rsi
0x180007854  push    rdi
0x180007855  sub     rsp, 28h
0x180007859  xor     ebp, ebp
0x18000785b  mov     dword ptr [rcx+8], 1
0x180007862  lea     rbx, [rcx+0B8h]
0x180007869  mov     dword ptr [rcx+0Ch], 58435357h
0x180007870  lea     rax, ??_7WEBSOCKET_CONTEXT@@6B@; const WEBSOCKET_CONTEXT::`vftable'
0x180007877  mov     [rcx+28h], rbp
0x18000787b  mov     [rcx], rax
0x18000787e  mov     rsi, rcx
0x180007881  lea     rax, ??_7READ_CONTEXT@@6B@; const READ_CONTEXT::`vftable'
0x180007888  mov     [rcx+30h], rbp
0x18000788c  mov     [rcx+20h], rax
0x180007890  mov     rdi, rdx
0x180007893  lea     rax, ??_7WEBSOCKET_IO_MANAGER@@6B@; const WEBSOCKET_IO_MANAGER::`vftable'
0x18000789a  mov     [rcx+38h], rbp
0x18000789e  mov     [rcx+90h], rax
0x1800078a5  mov     [rcx+40h], ebp
0x1800078a8  mov     [rcx+48h], rbp
0x1800078ac  mov     [rcx+50h], rbp
0x1800078b0  mov     [rcx+58h], rbp
0x1800078b4  mov     [rcx+60h], ebp
0x1800078b7  mov     [rcx+68h], rbp
0x1800078bb  mov     [rcx+78h], rbp
0x1800078bf  mov     [rcx+80h], rbp
0x1800078c6  mov     [rcx+88h], rbp
0x1800078cd  mov     [rcx+98h], rdx
0x1800078d4  mov     [rcx+0A0h], rbp
0x1800078db  mov     [rcx+0A8h], ebp
0x1800078e1  mov     rcx, rbx
0x1800078e4  mov     [rbx+38h], rbp
0x1800078e8  mov     [rbx+40h], rbp
0x1800078ec  call    cs:__imp_IISInitializeCriticalSection
0x1800078f2  lea     rax, [rbx+28h]
0x1800078f6  mov     [rax+8], rax
0x1800078fa  lea     rcx, [rsi+120h]
0x180007901  mov     [rax], rax
0x180007904  mov     [rsi+100h], ebp
0x18000790a  mov     [rsi+108h], rbp
0x180007911  mov     [rsi+110h], rbp
0x180007918  mov     [rsi+118h], bp
0x18000791f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007925  mov     [rsi+158h], rdi
0x18000792c  lea     rcx, [rsi+188h]
0x180007933  mov     [rsi+160h], ebp
0x180007939  mov     [rsi+164h], ebp
0x18000793f  mov     [rsi+168h], ebp
0x180007945  mov     [rsi+16Ch], ebp
0x18000794b  mov     [rsi+170h], ebp
0x180007951  mov     [rsi+174h], ebp
0x180007957  mov     [rsi+178h], rbp
0x18000795e  mov     [rsi+180h], ebp
0x180007964  mov     [rsi+1B0h], rbp
0x18000796b  mov     [rsi+18h], rbp
0x18000796f  mov     [rsi+10h], rbp
0x180007973  call    cs:__imp_IISInitializeCriticalSection
0x180007979  mov     rax, rsi
0x18000797c  mov     [rsi+1C0h], rbp
0x180007983  mov     [rsi+1B8h], rbp
0x18000798a  add     rsp, 28h
0x18000798e  pop     rdi
0x18000798f  pop     rsi
0x180007990  pop     rbp
0x180007991  pop     rbx
0x180007992  retn
```
