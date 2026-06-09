# CSSMappedStream::Open(CPropertySetStream *,long *)

- ea: `0x180038140`
- end: `0x1800382bd`
- name: `?Open@CSSMappedStream@@UEAAXPEAVCPropertySetStream@@PEAJ@Z`
- size: `381`
- prototype: `void __fastcall(CSSMappedStream *__hidden this, struct CPropertySetStream *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180038140`
- `0x180042800`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003820d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003820d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800382a2`

## pseudocode

```c
void __fastcall CSSMappedStream::Open(CSSMappedStream *this, struct CPropertySetStream *a2, int *a3)
{
  int v3; // eax
  void *v6; // rdi
  int v7; // eax
  unsigned int v8; // eax
  SIZE_T v9; // rcx
  LPVOID v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // r8
  int v14; // eax
  _BYTE v15[16]; // [rsp+40h] [rbp-78h] BYREF
  unsigned int cb; // [rsp+50h] [rbp-68h]
  int cb_4; // [rsp+54h] [rbp-64h]

  v3 = 0;
  *a3 = 0;
  if ( a2 )
  {
    *((_QWORD *)this + 5) = a2;
    v3 = *a3;
  }
  v6 = 0;
  if ( *((_QWORD *)this + 3) )
  {
    if ( v3 >= 0 )
      return;
    goto LABEL_17;
  }
  memset_0(v15, 0, 0x50u);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(**((_QWORD **)this + 2) + 96LL))(
         *((_QWORD *)this + 2),
         v15,
         1);
  *a3 = v7;
  if ( v7 < 0 )
    goto LABEL_17;
  if ( cb_4 || (v8 = cb, cb > 0x200000) )
  {
    *a3 = -2147286789;
    goto LABEL_19;
  }
  v9 = cb;
  *((_DWORD *)this + 9) = cb;
  *((_DWORD *)this + 8) = v8;
  v10 = CoTaskMemAlloc(v9);
  v6 = v10;
  if ( !v10 )
  {
    *a3 = -2147024882;
    goto LABEL_19;
  }
  v11 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 3) = v10;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v11 + 40LL))(v11, 0, 0, 0);
  *a3 = v12;
  if ( v12 < 0 )
  {
LABEL_17:
    if ( v6 )
      goto LABEL_18;
LABEL_19:
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    return;
  }
  v13 = *((unsigned int *)this + 9);
  if ( (_DWORD)v13 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *))(**((_QWORD **)this + 2) + 24LL))(
            *((_QWORD *)this + 2),
            *((_QWORD *)this + 3),
            v13,
            (char *)this + 32);
    *a3 = v14;
    if ( v14 < 0 )
      goto LABEL_17;
    if ( *((_DWORD *)this + 8) != *((_DWORD *)this + 9) )
    {
      *a3 = -2147286789;
LABEL_18:
      CoTaskMemFree(v6);
      goto LABEL_19;
    }
  }
}

```

## disassembly

```asm
0x180038140  mov     [rsp+arg_8], rbx
0x180038145  push    rsi
0x180038146  push    rdi
0x180038147  push    r14
0x180038149  sub     rsp, 0A0h
0x180038150  mov     rax, cs:__security_cookie
0x180038157  xor     rax, rsp
0x18003815a  mov     [rsp+0B8h+var_28], rax
0x180038162  xor     eax, eax
0x180038164  mov     dword ptr [r8], 0
0x18003816b  mov     rsi, r8
0x18003816e  mov     rbx, rcx
0x180038171  test    rdx, rdx
0x180038174  jnz     short loc_1800381AA
0x180038176  xor     edi, edi
0x180038178  cmp     [rcx+18h], rdi
0x18003817c  jz      short loc_1800381B3
0x18003817e  test    eax, eax
0x180038180  js      loc_18003829A
0x180038186  mov     rcx, [rsp+0B8h+var_28]
0x18003818e  xor     rcx, rsp; StackCookie
0x180038191  call    __security_check_cookie
0x180038196  mov     rbx, [rsp+0B8h+arg_8]
0x18003819e  add     rsp, 0A0h
0x1800381a5  pop     r14
0x1800381a7  pop     rdi
0x1800381a8  pop     rsi
0x1800381a9  retn
0x1800381aa  mov     [rcx+28h], rdx
0x1800381ae  mov     eax, [r8]
0x1800381b1  jmp     short loc_180038176
0x1800381b3  xor     edx, edx; Val
0x1800381b5  lea     rcx, [rsp+0B8h+var_78]; void *
0x1800381ba  lea     r8d, [rdx+50h]; Size
0x1800381be  call    memset_0
0x1800381c3  mov     rcx, [rbx+10h]
0x1800381c7  lea     rdx, [rsp+0B8h+var_78]
0x1800381cc  mov     r8d, 1
0x1800381d2  mov     rax, [rcx]
0x1800381d5  mov     rax, [rax+60h]
0x1800381d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381de  mov     [rsi], eax
0x1800381e0  test    eax, eax
0x1800381e2  js      loc_18003829A
0x1800381e8  cmp     dword ptr [rsp+0B8h+cb+4], edi
0x1800381ec  jnz     loc_180038292
0x1800381f2  mov     eax, dword ptr [rsp+0B8h+cb]
0x1800381f6  cmp     eax, 200000h
0x1800381fb  ja      loc_180038292
0x180038201  mov     ecx, eax; cb
0x180038203  lea     r14, [rbx+20h]
0x180038207  mov     [rbx+24h], ecx
0x18003820a  mov     [r14], eax
0x18003820d  call    cs:__imp_CoTaskMemAlloc
0x180038213  mov     rdi, rax
0x180038216  test    rax, rax
0x180038219  jnz     short loc_180038226
0x18003821b  mov     dword ptr [rsi], 8007000Eh
0x180038221  jmp     loc_1800382A8
0x180038226  mov     rcx, [rbx+10h]
0x18003822a  xor     r9d, r9d
0x18003822d  mov     [rbx+18h], rax
0x180038231  xor     r8d, r8d
0x180038234  mov     [rsp+0B8h+var_88], 0
0x18003823d  mov     rdx, [rsp+0B8h+var_88]
0x180038242  mov     rax, [rcx]
0x180038245  mov     rax, [rax+28h]
0x180038249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003824e  mov     [rsi], eax
0x180038250  test    eax, eax
0x180038252  js      short loc_18003829A
0x180038254  mov     r8d, [rbx+24h]
0x180038258  test    r8d, r8d
0x18003825b  jz      loc_180038186
0x180038261  mov     rcx, [rbx+10h]
0x180038265  mov     r9, r14
0x180038268  mov     rdx, [rbx+18h]
0x18003826c  mov     rax, [rcx]
0x18003826f  mov     rax, [rax+18h]
0x180038273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038278  mov     [rsi], eax
0x18003827a  test    eax, eax
0x18003827c  js      short loc_18003829A
0x18003827e  mov     eax, [rbx+24h]
0x180038281  cmp     [r14], eax
0x180038284  jz      loc_180038186
0x18003828a  mov     dword ptr [rsi], 800300FBh
0x180038290  jmp     short loc_18003829F
0x180038292  mov     dword ptr [rsi], 800300FBh
0x180038298  jmp     short loc_1800382A8
0x18003829a  test    rdi, rdi
0x18003829d  jz      short loc_1800382A8
0x18003829f  mov     rcx, rdi; pv
0x1800382a2  call    cs:__imp_CoTaskMemFree
0x1800382a8  mov     qword ptr [rbx+18h], 0
0x1800382b0  mov     qword ptr [rbx+20h], 0
0x1800382b8  jmp     loc_180038186
```
