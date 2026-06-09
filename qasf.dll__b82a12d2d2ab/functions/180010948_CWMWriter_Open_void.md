# CWMWriter::Open(void)

- ea: `0x180010948`
- end: `0x180010a98`
- name: `?Open@CWMWriter@@QEAAJXZ`
- size: `336`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f414`
- `0x180011580`

## callees

- `0x180001460`
- `0x180010948`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800109f8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800109f8`
- `WMVCore!WMCreateWriterNetworkSink` at `0x180010a18`
- `WMVCore!WMCreateWriterNetworkSink` at `0x180010a18`

## pseudocode

```c
HRESULT __fastcall CWMWriter::Open(CWMWriter *this)
{
  HRESULT result; // eax
  _WORD *v3; // rcx
  int v4; // edi
  IWMWriterNetworkSink *ppSink; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h] BYREF

  if ( !*((_QWORD *)this + 39) )
    return -2147467259;
  v3 = (_WORD *)*((_QWORD *)this + 36);
  if ( !v3 )
    return 0;
  if ( ((*v3 - 72) & 0xFFDF) != 0
    || ((v3[1] - 84) & 0xFFDF) != 0
    || ((v3[2] - 84) & 0xFFDF) != 0
    || ((v3[3] - 80) & 0xFFDF) != 0
    || v3[4] != 58
    || v3[5] != 47
    || v3[6] != 47 )
  {
    v4 = 0;
    *((_DWORD *)this + 54) = 1;
    return v4;
  }
  v6 = _o__wtoi(v3 + 7);
  if ( !v6 )
    v6 = 80;
  ppSink = 0;
  result = WMCreateWriterNetworkSink(&ppSink);
  if ( result >= 0 )
  {
    v4 = ((__int64 (__fastcall *)(IWMWriterNetworkSink *, int *))ppSink->lpVtbl->Open)(ppSink, &v6);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(_QWORD, IWMWriterNetworkSink *))(**((_QWORD **)this + 40) + 40LL))(
             *((_QWORD *)this + 40),
             ppSink);
    ((void (__fastcall *)(IWMWriterNetworkSink *))ppSink->lpVtbl->Release)(ppSink);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180010948  mov     [rsp+arg_8], rbx
0x18001094d  push    rdi
0x18001094e  sub     rsp, 40h
0x180010952  mov     rax, cs:__security_cookie
0x180010959  xor     rax, rsp
0x18001095c  mov     [rsp+48h+var_18], rax
0x180010961  mov     rbx, rcx
0x180010964  cmp     qword ptr [rcx+138h], 0
0x18001096c  jnz     short loc_180010978
0x18001096e  mov     eax, 80004005h
0x180010973  jmp     loc_180010A80
0x180010978  mov     rcx, [rcx+120h]
0x18001097f  test    rcx, rcx
0x180010982  jnz     short loc_18001098B
0x180010984  xor     eax, eax
0x180010986  jmp     loc_180010A80
0x18001098b  movzx   eax, word ptr [rcx]
0x18001098e  sub     ax, 48h ; 'H'
0x180010992  mov     edx, 0FFDFh
0x180010997  test    dx, ax
0x18001099a  jnz     loc_180010A72
0x1800109a0  movzx   eax, word ptr [rcx+2]
0x1800109a4  sub     ax, 54h ; 'T'
0x1800109a8  test    dx, ax
0x1800109ab  jnz     loc_180010A72
0x1800109b1  movzx   eax, word ptr [rcx+4]
0x1800109b5  sub     ax, 54h ; 'T'
0x1800109b9  test    dx, ax
0x1800109bc  jnz     loc_180010A72
0x1800109c2  movzx   eax, word ptr [rcx+6]
0x1800109c6  mov     edi, 50h ; 'P'
0x1800109cb  sub     ax, di
0x1800109ce  test    dx, ax
0x1800109d1  jnz     loc_180010A72
0x1800109d7  cmp     word ptr [rcx+8], 3Ah ; ':'
0x1800109dc  jnz     loc_180010A72
0x1800109e2  cmp     word ptr [rcx+0Ah], 2Fh ; '/'
0x1800109e7  jnz     loc_180010A72
0x1800109ed  cmp     word ptr [rcx+0Ch], 2Fh ; '/'
0x1800109f2  jnz     short loc_180010A72
0x1800109f4  add     rcx, 0Eh
0x1800109f8  call    cs:__imp__o__wtoi
0x1800109fe  mov     [rsp+48h+var_20], eax
0x180010a02  test    eax, eax
0x180010a04  jnz     short loc_180010A0A
0x180010a06  mov     [rsp+48h+var_20], edi
0x180010a0a  mov     [rsp+48h+ppSink], 0
0x180010a13  lea     rcx, [rsp+48h+ppSink]; ppSink
0x180010a18  call    cs:__imp_WMCreateWriterNetworkSink
0x180010a1e  test    eax, eax
0x180010a20  js      short loc_180010A80
0x180010a22  mov     rcx, [rsp+48h+ppSink]
0x180010a27  mov     rax, [rcx]
0x180010a2a  lea     rdx, [rsp+48h+var_20]
0x180010a2f  mov     rax, [rax+68h]
0x180010a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a38  mov     edi, eax
0x180010a3a  test    eax, eax
0x180010a3c  js      short loc_180010A58
0x180010a3e  mov     rcx, [rbx+140h]
0x180010a45  mov     rax, [rcx]
0x180010a48  mov     rdx, [rsp+48h+ppSink]
0x180010a4d  mov     rax, [rax+28h]
0x180010a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a56  mov     edi, eax
0x180010a58  mov     rcx, [rsp+48h+ppSink]
0x180010a5d  mov     rax, [rcx]
0x180010a60  mov     rax, [rax+10h]
0x180010a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a69  jmp     short loc_180010A7E
0x180010a6b  mov     eax, 8007007Eh
0x180010a70  jmp     short loc_180010A80
0x180010a72  xor     edi, edi
0x180010a74  mov     dword ptr [rbx+0D8h], 1
0x180010a7e  mov     eax, edi
0x180010a80  mov     rcx, [rsp+48h+var_18]
0x180010a85  xor     rcx, rsp; StackCookie
0x180010a88  call    __security_check_cookie
0x180010a8d  mov     rbx, [rsp+48h+arg_8]
0x180010a92  add     rsp, 40h
0x180010a96  pop     rdi
0x180010a97  retn
```
