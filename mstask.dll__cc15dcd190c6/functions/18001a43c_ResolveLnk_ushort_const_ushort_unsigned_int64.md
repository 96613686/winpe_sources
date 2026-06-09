# ResolveLnk(ushort const *,ushort *,unsigned __int64)

- ea: `0x18001a43c`
- end: `0x18001a5de`
- name: `?ResolveLnk@@YAXPEBGPEAG_K@Z`
- size: `418`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a5e4`

## callees

- `0x180001840`
- `0x18001a43c`
- `0x18001aa9a`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a498`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a498`

## pseudocode

```c
void __fastcall ResolveLnk(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 v4; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v6; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v7[592]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v8[264]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v9[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  *a2 = 0;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv) >= 0 )
  {
    v6 = 0;
    if ( (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v6) >= 0 )
    {
      memset_0(v9, 0, 0x208u);
      StringCchCopyW(v9, 0x104u, a1);
      if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, v9, 0) >= 0 )
      {
        StringCchCopyW(v8, 0x104u, a1);
        memset_0(v7, 0, sizeof(v7));
        if ( (*(int (__fastcall **)(LPVOID, unsigned __int16 *, __int64, _BYTE *, int))(*(_QWORD *)ppv + 24LL))(
               ppv,
               v8,
               260,
               v7,
               1) >= 0 )
        {
          v4 = -1;
          do
            ++v4;
          while ( v8[v4] );
          if ( v4 )
            StringCchCopyW(a2, 0x104u, v8);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
}

```

## disassembly

```asm
0x18001a43c  mov     [rsp-8+arg_10], rbx
0x18001a441  mov     [rsp-8+arg_18], rsi
0x18001a446  push    rbp
0x18001a447  push    rdi
0x18001a448  push    r14
0x18001a44a  lea     rbp, [rsp-5C0h]
0x18001a452  sub     rsp, 6C0h
0x18001a459  mov     rax, cs:__security_cookie
0x18001a460  xor     rax, rsp
0x18001a463  mov     [rbp+5D0h+var_20], rax
0x18001a46a  xor     esi, esi
0x18001a46c  lea     rax, [rsp+6D0h+var_6A0]
0x18001a471  mov     rbx, rdx
0x18001a474  mov     [rdx], si
0x18001a477  mov     rdi, rcx
0x18001a47a  mov     [rsp+6D0h+var_6A0], rsi
0x18001a47f  lea     r9, IID_IShellLinkW; riid
0x18001a486  mov     [rsp+6D0h+ppv], rax; ppv
0x18001a48b  lea     r8d, [rsi+1]; dwClsContext
0x18001a48f  xor     edx, edx; pUnkOuter
0x18001a491  lea     rcx, CLSID_ShellLink; rclsid
0x18001a498  call    cs:__imp_CoCreateInstance
0x18001a49e  test    eax, eax
0x18001a4a0  js      loc_18001A5B7
0x18001a4a6  mov     rcx, [rsp+6D0h+var_6A0]
0x18001a4ab  lea     r8, [rsp+6D0h+var_698]
0x18001a4b0  mov     [rsp+6D0h+var_698], rsi
0x18001a4b5  lea     rdx, IID_IPersistFile
0x18001a4bc  mov     rax, [rcx]
0x18001a4bf  mov     rax, [rax]
0x18001a4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4c7  test    eax, eax
0x18001a4c9  js      loc_18001A5A6
0x18001a4cf  xor     edx, edx; Val
0x18001a4d1  lea     rcx, [rbp+5D0h+var_230]; void *
0x18001a4d8  mov     r8d, 208h; Size
0x18001a4de  call    memset_0
0x18001a4e3  mov     r14d, 104h
0x18001a4e9  lea     rcx, [rbp+5D0h+var_230]; unsigned __int16 *
0x18001a4f0  mov     edx, r14d; unsigned __int64
0x18001a4f3  mov     r8, rdi; unsigned __int16 *
0x18001a4f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a4fb  mov     rcx, [rsp+6D0h+var_698]
0x18001a500  lea     rdx, [rbp+5D0h+var_230]
0x18001a507  xor     r8d, r8d
0x18001a50a  mov     rax, [rcx]
0x18001a50d  mov     rax, [rax+28h]
0x18001a511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a516  test    eax, eax
0x18001a518  js      short loc_18001A595
0x18001a51a  mov     r8, rdi; unsigned __int16 *
0x18001a51d  lea     rcx, [rbp+5D0h+var_440]; unsigned __int16 *
0x18001a524  mov     edx, r14d; unsigned __int64
0x18001a527  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a52c  xor     edx, edx; Val
0x18001a52e  lea     rcx, [rsp+6D0h+var_690]; void *
0x18001a533  mov     r8d, 250h; Size
0x18001a539  call    memset_0
0x18001a53e  mov     rcx, [rsp+6D0h+var_6A0]
0x18001a543  lea     r9, [rsp+6D0h+var_690]
0x18001a548  mov     r8d, r14d
0x18001a54b  mov     dword ptr [rsp+6D0h+ppv], 1
0x18001a553  lea     rdx, [rbp+5D0h+var_440]
0x18001a55a  mov     rax, [rcx]
0x18001a55d  mov     rax, [rax+18h]
0x18001a561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a566  test    eax, eax
0x18001a568  js      short loc_18001A595
0x18001a56a  lea     rcx, [rbp+5D0h+var_440]
0x18001a571  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a575  inc     rax
0x18001a578  cmp     [rcx+rax*2], si
0x18001a57c  jnz     short loc_18001A575
0x18001a57e  test    rax, rax
0x18001a581  jz      short loc_18001A595
0x18001a583  lea     r8, [rbp+5D0h+var_440]; unsigned __int16 *
0x18001a58a  mov     rdx, r14; unsigned __int64
0x18001a58d  mov     rcx, rbx; unsigned __int16 *
0x18001a590  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a595  mov     rcx, [rsp+6D0h+var_698]
0x18001a59a  mov     rax, [rcx]
0x18001a59d  mov     rax, [rax+10h]
0x18001a5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5a6  mov     rcx, [rsp+6D0h+var_6A0]
0x18001a5ab  mov     rax, [rcx]
0x18001a5ae  mov     rax, [rax+10h]
0x18001a5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5b7  mov     rcx, [rbp+5D0h+var_20]
0x18001a5be  xor     rcx, rsp; StackCookie
0x18001a5c1  call    __security_check_cookie
0x18001a5c6  lea     r11, [rsp+6D0h+var_10]
0x18001a5ce  mov     rbx, [r11+30h]
0x18001a5d2  mov     rsi, [r11+38h]
0x18001a5d6  mov     rsp, r11
0x18001a5d9  pop     r14
0x18001a5db  pop     rdi
0x18001a5dc  pop     rbp
0x18001a5dd  retn
```
