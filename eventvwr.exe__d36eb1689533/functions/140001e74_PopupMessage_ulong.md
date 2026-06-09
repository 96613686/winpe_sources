# PopupMessage(ulong,...)

- ea: `0x140001e74`
- end: `0x140001f27`
- name: `?PopupMessage@@YAXKZZ`
- size: `179`
- prototype: `void(unsigned int, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400023ac`

## callees

- `0x140001008`
- `0x140001adc`
- `0x140002cb0`

## pseudocode

```c
void PopupMessage(UINT a1, ...)
{
  unsigned int v1; // [rsp+28h] [rbp-E0h]
  unsigned int v2; // [rsp+30h] [rbp-D8h]
  LPARAM dwInitParam[2]; // [rsp+58h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+68h] [rbp-A0h]
  void *Block; // [rsp+78h] [rbp-90h]
  __int16 v6; // [rsp+80h] [rbp-88h]
  void *v7; // [rsp+2C8h] [rbp+1C0h]
  __int64 v8; // [rsp+310h] [rbp+208h] BYREF
  va_list va; // [rsp+310h] [rbp+208h]
  const unsigned __int16 *v10; // [rsp+318h] [rbp+210h]
  const unsigned __int16 *v11; // [rsp+320h] [rbp+218h]
  va_list va1; // [rsp+328h] [rbp+220h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v8 = va_arg(va1, _QWORD);
  v10 = va_arg(va1, const unsigned __int16 *);
  v11 = va_arg(va1, const unsigned __int16 *);
  dwInitParam[1] = 0;
  dwInitParam[0] = (LPARAM)&CMessageDlg::`vftable';
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Block = 0;
  v7 = 0;
  v6 = 0;
  CMessageDlg::DoModalDialog(dwInitParam, (HINSTANCE)va, v10, v11, v1, v2, a1, va);
  dwInitParam[0] = (LPARAM)&CMessageDlg::`vftable';
  operator delete(Block);
  operator delete(v7);
}

```

## disassembly

```asm
0x140001e74  mov     rax, rsp
0x140001e77  mov     [rax+8], ecx
0x140001e7a  mov     [rax+10h], rdx
0x140001e7e  mov     [rax+18h], r8
0x140001e82  mov     [rax+20h], r9
0x140001e86  push    rbp
0x140001e87  push    rbx
0x140001e88  lea     rbp, [rax-1F8h]
0x140001e8f  sub     rsp, 2E8h
0x140001e96  mov     rax, cs:__security_cookie
0x140001e9d  xor     rax, rsp
0x140001ea0  mov     [rbp+1F0h+var_20], rax
0x140001ea7  movdqa  xmm0, cs:__xmm@0000000000007f010000000000000000
0x140001eaf  lea     rdx, [rbp+1F0h+arg_8]; HINSTANCE
0x140001eb6  xor     eax, eax
0x140001eb8  mov     [rsp+38h], rdx; char *
0x140001ebd  mov     [rsp+2F0h+var_2C0], ecx; unsigned int
0x140001ec1  lea     rbx, ??_7CMessageDlg@@6B@; const CMessageDlg::`vftable'
0x140001ec8  lea     rcx, [rsp+2F0h+dwInitParam]; dwInitParam
0x140001ecd  mov     qword ptr [rsp+2F0h+var_298], rax
0x140001ed2  mov     [rsp+2F0h+dwInitParam], rbx
0x140001ed7  movdqa  [rsp+2F0h+var_298+8], xmm0
0x140001edd  mov     [rsp+2F0h+Block], rax
0x140001ee2  mov     [rbp+1F0h+var_30], rax
0x140001ee9  mov     [rsp+2F0h+var_278], ax
0x140001eee  call    ?DoModalDialog@CMessageDlg@@QEAA_JPEAUHINSTANCE__@@PEBG1KKKPEAD@Z; CMessageDlg::DoModalDialog(HINSTANCE__ *,ushort const *,ushort const *,ulong,ulong,ulong,char *)
0x140001ef3  mov     rcx, [rsp+2F0h+Block]; Block
0x140001ef8  mov     [rsp+2F0h+dwInitParam], rbx
0x140001efd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001f02  mov     rcx, [rbp+1F0h+var_30]; Block
0x140001f09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001f0e  mov     rcx, [rbp+1F0h+var_20]
0x140001f15  xor     rcx, rsp; StackCookie
0x140001f18  call    __security_check_cookie
0x140001f1d  add     rsp, 2E8h
0x140001f24  pop     rbx
0x140001f25  pop     rbp
0x140001f26  retn
```
