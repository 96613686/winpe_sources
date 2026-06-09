# UmfdHostReady

- ea: `0x140072600`
- end: `0x140072697`
- name: `UmfdHostReady`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140067a40`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140072679`
- `win32u!NtGdiExtEscape` at `0x140072679`

## pseudocode

```c
__int64 UmfdHostReady()
{
  _OWORD v1[3]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v2; // [rsp+70h] [rbp-28h] BYREF
  wchar_t v3; // [rsp+80h] [rbp-18h]

  memset(v1, 0, sizeof(v1));
  LODWORD(v1[0]) = 18;
  v2 = *(_OWORD *)L"UmfdHost";
  v3 = aUmfdhost[8];
  return ((__int64 (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, _OWORD *, int, _OWORD *))NtGdiExtEscape)(
           0,
           &v2,
           9,
           19,
           48,
           v1,
           48,
           v1);
}

```

## disassembly

```asm
0x140072600  mov     r11, rsp
0x140072603  sub     rsp, 98h
0x14007260a  mov     rax, cs:__security_cookie
0x140072611  xor     rax, rsp
0x140072614  mov     [rsp+98h+var_10], rax
0x14007261c  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x140072623  lea     rdx, [r11-28h]
0x140072627  xorps   xmm0, xmm0
0x14007262a  mov     ecx, 30h ; '0'
0x14007262f  movups  [rsp+98h+var_58], xmm0
0x140072634  mov     dword ptr [rsp+98h+var_58], 12h
0x14007263c  movups  [rsp+98h+var_48], xmm0
0x140072641  lea     r9d, [rcx-1Dh]
0x140072645  movups  [rsp+98h+var_38], xmm0
0x14007264a  lea     r8d, [rcx-27h]
0x14007264e  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140072655  movups  [rsp+98h+var_28], xmm0
0x14007265a  mov     [r11-18h], ax
0x14007265f  lea     rax, [r11-58h]
0x140072663  mov     [r11-60h], rax
0x140072667  lea     rax, [r11-58h]
0x14007266b  mov     [rsp+98h+var_68], ecx
0x14007266f  mov     [r11-70h], rax
0x140072673  mov     [rsp+98h+var_78], ecx
0x140072677  xor     ecx, ecx
0x140072679  call    cs:__imp_NtGdiExtEscape
0x14007267f  mov     rcx, [rsp+98h+var_10]
0x140072687  xor     rcx, rsp; StackCookie
0x14007268a  call    __security_check_cookie
0x14007268f  add     rsp, 98h
0x140072696  retn
```
