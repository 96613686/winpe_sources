# PopupMessageEx2(ulong,ushort const *,ulong)

- ea: `0x140001f30`
- end: `0x14000209d`
- name: `?PopupMessageEx2@@YAXKPEBGK@Z`
- size: `365`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400023ac`

## callees

- `0x140001008`
- `0x140001014`
- `0x1400019ec`
- `0x140001bf0`
- `0x140001f30`
- `0x140002168`
- `0x140002cb0`
- `0x140002d40`

## pseudocode

```c
void __fastcall PopupMessageEx2(__int64 a1, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rbx
  __int64 v4; // rcx
  unsigned __int64 v5; // rbx
  HWND v6; // rdx
  LPARAM dwInitParam[2]; // [rsp+20h] [rbp-E0h] BYREF
  __m128i si128; // [rsp+30h] [rbp-D0h]
  void *Block; // [rsp+40h] [rbp-C0h]
  __int16 v10; // [rsp+48h] [rbp-B8h]
  void *v11; // [rsp+290h] [rbp+190h]
  unsigned __int16 v12[2000]; // [rsp+2A0h] [rbp+1A0h] BYREF

  dwInitParam[0] = (LPARAM)&CMessageDlg::`vftable';
  dwInitParam[1] = 0;
  Block = 0;
  v11 = 0;
  v10 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LoadStr(0x6Eu, v12, 0x7D0u, &qword_1400044B0);
  v2 = -1;
  do
    ++v2;
  while ( v12[v2] );
  v3 = (int)v2 + 1;
  Block = operator new(saturated_mul(v3, 2u));
  StringCchCopyW((unsigned __int16 *)Block, v3, v12);
  LoadStr(0x6Du, v12, 0x7D0u, &qword_1400044B0);
  v4 = -1;
  do
    ++v4;
  while ( v12[v4] );
  v5 = (int)v4 + 1;
  v11 = operator new(saturated_mul(v5, 2u));
  StringCchCopyW((unsigned __int16 *)v11, v5, v12);
  CDlg::_DoModalDlg((LPARAM)dwInitParam, v6, 112);
  dwInitParam[0] = (LPARAM)&CMessageDlg::`vftable';
  operator delete(Block);
  operator delete(v11);
}

```

## disassembly

```asm
0x140001f30  push    rbp
0x140001f32  push    rbx
0x140001f33  push    rsi
0x140001f34  push    rdi
0x140001f35  push    r14
0x140001f37  lea     rbp, [rsp-1150h]
0x140001f3f  mov     eax, 1250h
0x140001f44  call    _alloca_probe
0x140001f49  sub     rsp, rax
0x140001f4c  mov     rax, cs:__security_cookie
0x140001f53  xor     rax, rsp
0x140001f56  mov     [rbp+1170h+var_30], rax
0x140001f5d  movdqa  xmm0, cs:__xmm@0000000000007f040000000000000000
0x140001f65  lea     r14, ??_7CMessageDlg@@6B@; const CMessageDlg::`vftable'
0x140001f6c  xor     edi, edi
0x140001f6e  mov     [rsp+1270h+dwInitParam], r14
0x140001f73  lea     r9, qword_1400044B0; unsigned __int16 *
0x140001f7a  mov     [rsp+1270h+var_1248], rdi
0x140001f7f  mov     r8d, 7D0h; unsigned int
0x140001f85  mov     [rsp+1270h+Block], rdi
0x140001f8a  lea     rdx, [rbp+1170h+var_FD0]; unsigned __int16 *
0x140001f91  mov     [rbp+1170h+var_FE0], rdi
0x140001f98  lea     ecx, [rdi+6Eh]; uID
0x140001f9b  mov     [rsp+1270h+var_1228], di
0x140001fa0  movdqa  [rsp+1270h+var_1240], xmm0
0x140001fa6  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x140001fab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140001faf  lea     rcx, [rbp+1170h+var_FD0]
0x140001fb6  mov     rax, rsi
0x140001fb9  inc     rax
0x140001fbc  cmp     [rcx+rax*2], di
0x140001fc0  jnz     short loc_140001FB9
0x140001fc2  inc     eax
0x140001fc4  movsxd  rbx, eax
0x140001fc7  mov     eax, 2
0x140001fcc  mul     rbx
0x140001fcf  cmovb   rax, rsi
0x140001fd3  mov     rcx, rax; Size
0x140001fd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001fdb  lea     r8, [rbp+1170h+var_FD0]; unsigned __int16 *
0x140001fe2  mov     [rsp+1270h+Block], rax
0x140001fe7  mov     rdx, rbx; unsigned __int64
0x140001fea  mov     rcx, rax; unsigned __int16 *
0x140001fed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140001ff2  lea     r9, qword_1400044B0; unsigned __int16 *
0x140001ff9  mov     r8d, 7D0h; unsigned int
0x140001fff  lea     rdx, [rbp+1170h+var_FD0]; unsigned __int16 *
0x140002006  mov     ecx, 6Dh ; 'm'; uID
0x14000200b  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x140002010  lea     rdx, [rbp+1170h+var_FD0]
0x140002017  mov     rcx, rsi
0x14000201a  inc     rcx
0x14000201d  cmp     [rdx+rcx*2], di
0x140002021  jnz     short loc_14000201A
0x140002023  inc     ecx
0x140002025  mov     eax, 2
0x14000202a  movsxd  rbx, ecx
0x14000202d  mul     rbx
0x140002030  cmovb   rax, rsi
0x140002034  mov     rcx, rax; Size
0x140002037  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000203c  lea     r8, [rbp+1170h+var_FD0]; unsigned __int16 *
0x140002043  mov     [rbp+1170h+var_FE0], rax
0x14000204a  mov     rdx, rbx; unsigned __int64
0x14000204d  mov     rcx, rax; unsigned __int16 *
0x140002050  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140002055  mov     r8d, 70h ; 'p'; int
0x14000205b  lea     rcx, [rsp+1270h+dwInitParam]; dwInitParam
0x140002060  call    ?_DoModalDlg@CDlg@@IEAA_JPEAUHWND__@@H@Z; CDlg::_DoModalDlg(HWND__ *,int)
0x140002065  mov     rcx, [rsp+1270h+Block]; Block
0x14000206a  mov     [rsp+1270h+dwInitParam], r14
0x14000206f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002074  mov     rcx, [rbp+1170h+var_FE0]; Block
0x14000207b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002080  mov     rcx, [rbp+1170h+var_30]
0x140002087  xor     rcx, rsp; StackCookie
0x14000208a  call    __security_check_cookie
0x14000208f  add     rsp, 1250h
0x140002096  pop     r14
0x140002098  pop     rdi
0x140002099  pop     rsi
0x14000209a  pop     rbx
0x14000209b  pop     rbp
0x14000209c  retn
```
